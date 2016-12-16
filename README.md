# easyui-manager
easyui后台管理系统

> pom.xml

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com</groupId>
  <artifactId>redis</artifactId>
  <packaging>pom</packaging>
  <version>1.0-SNAPSHOT</version>
    <modules>
        <module>forkjoin</module>
        <module>forktest</module>
        <module>lambda</module>
        <module>esayui</module>
    </modules>
    <name>redis Maven Webapp</name>
  <url>http://maven.apache.org</url>
    <dependencies>
        <dependency>
            <groupId>org.springframework.data</groupId>
            <artifactId>spring-data-redis</artifactId>
            <version>1.0.2.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>3.1.2.RELEASE</version>
        </dependency>


        <dependency>
            <groupId>redis.clients</groupId>
            <artifactId>jedis</artifactId>
            <version>2.1.0</version>
        </dependency>

        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.8.2</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>1.6.1</version>
        </dependency>
        <!-- 将现有的jakarta commons logging的调用转换成lsf4j的调用。 -->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>jcl-over-slf4j</artifactId>
            <version>1.6.1</version>
        </dependency>
        <!-- Hack：确保commons-logging的jar包不被引入，否则将和jcl-over-slf4j冲突 -->
        <dependency>
            <groupId>commons-logging</groupId>
            <artifactId>commons-logging</artifactId>
            <version>1.1.1</version>
            <scope>provided</scope>
        </dependency>
        <!-- slf4j的实现：logback，用来取代log4j。更快、更强！ -->
        <dependency>
            <groupId>ch.qos.logback</groupId>
            <artifactId>logback-classic</artifactId>
            <version>0.9.24</version>
            <scope>runtime</scope>
        </dependency>
    </dependencies>
  <build>
    <finalName>redis</finalName>
  </build>
</project>


> jdbc.properties

driver=com.mysql.jdbc.Driver

url=jdbc:mysql://localhost:3306/mybatis?useUnicode=true&characterEncoding=UTF-8

username=test1

password=123456

initialSize=5

maxActive=16

maxIdle=2

minIdle=1

maxWait=30000

> log4j.properties

log4j.rootCategory=INFO,stdout,R

log4j.appender.stdout=org.apache.log4j.ConsoleAppender

log4j.appender.stdout.layout=org.apache.log4j.PatternLayout

log4j.appender.stdout.layout.ConversionPattern=%d{yyyy-MM-dd HH:mm:ss,SSS}  %p %t %c - %m%n

log4j.appender.R=org.apache.log4j.RollingFileAppender

log4j.appender.R.File=${webapp.root}/logs/log.log

log4j.appender.R.MaxFileSize=10000KB

log4j.appender.R.MaxBackupIndex=100

log4j.appender.R.layout=org.apache.log4j.PatternLayout

log4j.appender.R.layout.ConversionPattern=%d{yyyy-MM-dd HH:mm:ss,SSS}  %p %t %c - %m%n

log4j.logger.com.sohu.fortune.talk=DEBUG

log4j.logger.org.apache.commons.httpclient=ERROR

> mybatis.cfg.xml

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE configuration PUBLIC "-//mybatis.org/DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd" >
<configuration>

</configuration>

> spring.xml

<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"

       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
       
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       
       xsi:schemaLocation="http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc-4.2.xsd
       
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
        
        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.2.xsd">

    <import resource="spring-mvc.xml"/>
    
    <import resource="spring-mybatis.xml"/>
    
</beans>

> spring-mvc.xml

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc-4.2.xsd
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.2.xsd">
    <!-- <mvc:view-controller path="/" view-name="index" /> -->

    <mvc:default-servlet-handler />

    <!-- 自动扫描该包，使SpringMVC认为包下用了@controller注解的类是控制器 -->
    <context:component-scan base-package="com.zui.controller" >
        <context:include-filter type="annotation" expression="org.springframework.stereotype.Controller"/>
    </context:component-scan>


    <!-- 启用默认配置 -->
    <mvc:annotation-driven>
        <mvc:message-converters register-defaults="true">
            <!-- 配置Fastjson支持 -->
            <bean
                    class="com.alibaba.fastjson.support.spring.FastJsonHttpMessageConverter">
                <property name="supportedMediaTypes">
                    <array>
                        <value>text/html;charset=UTF-8</value>
                        <value>application/json</value>
                    </array>
                </property>
                <property name="features">
                    <array>
                        <value>WriteMapNullValue</value>
                        <value>WriteNullStringAsEmpty</value>
                    </array>
                </property>
            </bean>
        </mvc:message-converters>
    </mvc:annotation-driven>


    <bean
            class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <!-- 这里的配置我的理解是自动给后面action的方法return的字符串加上前缀和后缀，变成一个 可用的url地址 -->
        <property name="prefix" value="/WEB-INF/" />
        <property name="suffix" value=".jsp" />
    </bean>

    <!-- 配置文件上传，如果没有使用文件上传可以不用配置，当然如果不配，那么配置文件中也不必引入上传组件包 -->
    <bean id="multipartResolver"
          class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
        <!-- 默认编码 -->
        <property name="defaultEncoding" value="utf-8" />
        <!-- 文件大小最大值 -->
        <property name="maxUploadSize" value="10485760000" />
        <!-- 内存中的最大值 -->
        <property name="maxInMemorySize" value="40960" />
    </bean>
</beans>

> spring-mybatis.xml

<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
       xmlns:tx="http://www.springframework.org/schema/tx" xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-4.2.xsd
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-4.2.xsd
        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.2.xsd">
    <!-- 自动扫描 -->
    <context:component-scan base-package="com.zui" />
    <!-- 引入配置文件 -->
    <bean id="propertyConfigurer"
          class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
        <property name="location" value="classpath:jdbc.properties" />
    </bean>

    <bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource"
          destroy-method="close">
        <property name="driverClassName" value="${driver}" />
        <property name="url" value="${url}" />
        <property name="username" value="${username}" />
        <property name="password" value="${password}" />
        <!-- 初始化连接大小 -->
        <property name="initialSize" value="${initialSize}"></property>
        <!-- 连接池最大数量 -->
        <property name="maxActive" value="${maxActive}"></property>
        <!-- 连接池最大空闲 -->
        <property name="maxIdle" value="${maxIdle}"></property>
        <!-- 连接池最小空闲 -->
        <property name="minIdle" value="${minIdle}"></property>
        <!-- 获取连接最大等待时间 -->
        <property name="maxWait" value="${maxWait}"></property>
    </bean>

    <!-- spring和MyBatis完美整合，不需要mybatis的配置映射文件 -->
    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <!-- 加载mybatis.cfg.xml文件 -->
        <property name="configLocation" value="classpath:mybatis.cfg.xml" />
        <!-- 自动扫描mapping.xml文件 -->
        <property name="mapperLocations" value="classpath:com/zui/mappers/*.xml"></property>
        <!-- 自动扫描需要定义类别名的包，将包内的JAVA类的类名作为类别名 -->
        <property name="typeAliasesPackage" value="com.zui.beans"></property>

        <property name="plugins">
            <array>
                <bean class="com.github.pagehelper.PageHelper">
                    <property name="properties">
                        <value>
                            dialect=mysql
                        </value>
                    </property>
                </bean>
            </array>
        </property>
    </bean>

    <!-- DAO接口所在包名，Spring会自动查找其下的类 -->
    <bean class="org.mybatis.spring.mapper.MapperScannerConfigurer">
        <property name="basePackage" value="com.zui.dao" />
        <property name="sqlSessionFactoryBeanName" value="sqlSessionFactory"></property>
    </bean>

    <!-- ================================事务相关控制================================================= -->
    <bean name="transactionManager"
          class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"></property>
    </bean>

    <tx:advice id="userTxAdvice" transaction-manager="transactionManager">
        <tx:attributes>
            <tx:method name="delete*" propagation="REQUIRED" read-only="false"
                       rollback-for="java.lang.Exception" no-rollback-for="java.lang.RuntimeException" />
            <tx:method name="insert*" propagation="REQUIRED" read-only="false"
                       rollback-for="java.lang.RuntimeException" />
            <tx:method name="update*" propagation="REQUIRED" read-only="false"
                       rollback-for="java.lang.Exception" />

            <tx:method name="find*" propagation="SUPPORTS" />
            <tx:method name="get*" propagation="SUPPORTS" />
            <tx:method name="select*" propagation="SUPPORTS" />
        </tx:attributes>
    </tx:advice>

    <aop:config>
        <aop:pointcut id="pc"
                      expression="execution(public * com.zui.service.*.*(..))" /> <!--把事务控制在Service层 -->
        <aop:advisor pointcut-ref="pc" advice-ref="userTxAdvice" />
    </aop:config>

</beans>

> web.xml

<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5"
         xmlns="http://java.sun.com/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
    http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

    <!-- 告知javaEE容器，有哪些内容需要添加到上下文中去 -->
    <context-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>classpath:spring.xml
            <!--/WEB-INF/classes/applicationContext.xml,-->
            <!-- /WEB-INF/classes/mvc-servlet.xml -->
        </param-value>
    </context-param>


    <!-- 加载LOG4J -->
    <!--<context-param>-->
        <!--<param-name>log4jConfigLocation</param-name>-->
        <!--<param-value>/WEB-INF/log4j.xml</param-value>-->
    <!--</context-param>-->

    <context-param>
        <param-name>log4jRefreshInterval</param-name>
        <param-value>60000</param-value>
    </context-param>

    <!-- 动态设置项目的运行路径 -->
    <context-param>
        <param-name>webAppRootKey</param-name>
        <param-value>ssm.root</param-value>
    </context-param>

    <!-- 配置静态资源 -->
    <servlet-mapping>
        <servlet-name>default</servlet-name>
        <url-pattern>/static/*</url-pattern>
    </servlet-mapping>


    <!-- 配置springmvc的前端控制器 -->
    <servlet>
        <servlet-name>mvc</servlet-name>
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <!-- 默认情况下：DispatcherServlet会寻找WEB-INF下，命名规范为[servlet-name]-servlet.xml文件。如：在上例中，它就会找/WEB-INF/spring-servlet.xml
                                                   如果需要修改，需要在web.xml中的<servlet>标记中增加 <init-param>。。。  </init-param>：-->
        <init-param>
            <param-name>contextConfigLocation</param-name>
            <param-value>classpath:spring-mvc.xml</param-value>
        </init-param>
    </servlet>
    <servlet-mapping>
        <servlet-name>mvc</servlet-name>
        <url-pattern>/</url-pattern>
    </servlet-mapping>

    <!-- spring框架提供的字符集过滤器 -->
    <!-- spring Web MVC框架提供了org.springframework.web.filter.CharacterEncodingFilter用于解决POST方式造成的中文乱码问题  -->
    <filter>
        <filter-name>encodingFilter</filter-name>
        <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
        <init-param>
            <param-name>encoding</param-name>
            <param-value>UTF-8</param-value>
        </init-param>
        <!-- force强制，促使 -->
        <init-param>
            <param-name>forceEncoding</param-name>
            <param-value>true</param-value>
        </init-param>
    </filter>
    <filter-mapping>
        <filter-name>encodingFilter</filter-name>
        <url-pattern>/*</url-pattern>
    </filter-mapping>

    <!-- 登录过滤器-->
    <!--<filter>-->
        <!--<filter-name>loginFilter</filter-name>-->
        <!--<filter-class>com.cy.ssm.filter.LoginFilter</filter-class>-->
    <!--</filter>-->
    <!--<filter-mapping>-->
        <!--<filter-name>loginFilter</filter-name>-->
        <!--<url-pattern>/*</url-pattern>-->
    <!--</filter-mapping>-->
    <!-- 监听器 -->
    <listener>
        <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
    </listener>

    <listener>
        <listener-class>org.springframework.web.util.Log4jConfigListener</listener-class>
    </listener>

    <welcome-file-list>
        <welcome-file>main.html</welcome-file>
    </welcome-file-list>
</web-app>

> Category.java

package com.zui.beans;

import java.io.Serializable;


public class Category implements Serializable
{
    private int id;
    private String name;
    private String type;

    public int getId()
    {
        return id;
    }

    public void setId(int id)
    {
        this.id = id;
    }

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }

    public String getType()
    {
        return type;
    }

    public void setType(String type)
    {
        this.type = type;
    }
}

> MainController.java

package com.zui.controller;

import com.zui.service.IService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.util.Map;

@Controller
@RequestMapping("/")
public class MainController
{
    @Autowired
    private IService categoryService;

    @ResponseBody
    @RequestMapping(value = "list")
    public Map<String, Object> getCategories(HttpServletRequest request,HttpServletResponse response) {
        int page=Integer.parseInt(request.getParameter("page"));
        int rows=Integer.parseInt(request.getParameter("rows"));
        String type=request.getParameter("type");
        return categoryService.query(type, page, rows);
    }
}

> Dao.java

package com.zui.dao;


import com.zui.beans.Category;

import java.util.List;

public interface Dao
{
   public List<Category> selectCategoryByType(String type);
}

> IService.java

package com.zui.service;

import java.util.Map;

public interface IService
{
    public Map<String,Object> query(String type, Integer pageNo, Integer pageSize);
}

> IServiceImpl.java

package com.zui.service;

import com.github.pagehelper.PageHelper;
import com.github.pagehelper.PageInfo;
import com.zui.beans.Category;
import com.zui.dao.Dao;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.HashMap;
import java.util.List;
import java.util.Locale;
import java.util.Map;

@Service
public class IServiceImpl implements IService
{
    @Autowired
    private Dao dao;

    @Override
    public Map<String, Object> query(String type, Integer pageNo, Integer pageSize)
    {
        pageNo = pageNo == null ? 1 : pageNo;
        pageSize = pageSize == null ? 10 : pageSize;
        PageHelper.startPage(pageNo, pageSize);
        List<Category> list = dao.selectCategoryByType(type);
        for (Category c : list)
        {
            System.out.println(c);
        }
        //用PageInfo对结果进行包装
        PageInfo<Category> page = new PageInfo<Category>(list);

        //测试PageInfo全部属性
        /*
        System.out.println(page.getPageNum());
        System.out.println(page.getPageSize());
        System.out.println(page.getStartRow());
        System.out.println(page.getEndRow());
        System.out.println(page.getTotal());
        System.out.println(page.getPages());
        System.out.println(page.getFirstPage());
        System.out.println(page.getLastPage());
        System.out.println(page.isHasPreviousPage());
        System.out.println(page.isHasNextPage());*/
        Map<String, Object> map = new HashMap<String, Object>();
        map.put("total", page.getTotal());
        map.put("rows", page.getList());
        return map;
    }
}

> Dao.xml

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org/DTD Mapper 3.0" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.zui.dao.Dao">

    <select id="selectCategoryByType" parameterType="java.lang.String" resultType="Category">
        select * from t_category where type=#{type}
    </select>

</mapper>



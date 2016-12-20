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
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <parent>
        <artifactId>redis</artifactId>
        <groupId>com</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>
    <artifactId>easyui</artifactId>
    <packaging>war</packaging>
    <name>easyui Maven Webapp</name>
    <url>http://maven.apache.org</url>
    <properties>
        <!-- spring版本号 -->
        <spring.version>4.2.5.RELEASE</spring.version>
        <!-- mybatis版本号 -->
        <mybatis.version>3.2.6</mybatis.version>
        <!-- log4j日志文件管理包版本 -->
        <slf4j.version>1.7.7</slf4j.version>
        <log4j.version>1.2.17</log4j.version>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.11</version>
            <scope>test</scope>
        </dependency>
        <!-- spring核心包 -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-web</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-oxm</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-tx</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-aop</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context-support</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-test</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <dependency>
            <groupId>aspectj</groupId>
            <artifactId>aspectjweaver</artifactId>
            <version>1.5.4</version>
        </dependency>
        <!-- mybatis核心包 -->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>${mybatis.version}</version>
        </dependency>
        <!-- mybatis/spring包 -->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
            <version>1.2.2</version>
        </dependency>
        <!-- 导入java ee jar 包 -->
        <dependency>
            <groupId>javax</groupId>
            <artifactId>javaee-api</artifactId>
            <scope>provided</scope>
            <version>7.0</version>
        </dependency>
        <!-- pagehelper分页 -->
        <dependency>
            <groupId>com.github.pagehelper</groupId>
            <artifactId>pagehelper</artifactId>
            <version>4.1.3</version>
        </dependency>
        <!-- 导入Mysql数据库链接jar包 -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>5.1.30</version>
        </dependency>
        <!-- 导入dbcp的jar包，用来在applicationContext.xml中配置数据库 -->
        <dependency>
            <groupId>commons-dbcp</groupId>
            <artifactId>commons-dbcp</artifactId>
            <version>1.2.2</version>
        </dependency>
        <!-- JSTL标签类 -->
        <dependency>
            <groupId>jstl</groupId>
            <artifactId>jstl</artifactId>
            <version>1.2</version>
        </dependency>
        <!-- 日志文件管理包 -->
        <!-- log start -->
        <dependency>
            <groupId>log4j</groupId>
            <artifactId>log4j</artifactId>
            <version>${log4j.version}</version>
        </dependency>


        <!-- 格式化对象，方便输出日志 -->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>fastjson</artifactId>
            <version>1.2.5</version>
        </dependency>

        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>${slf4j.version}</version>
        </dependency>

        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
            <version>${slf4j.version}</version>
        </dependency>
        <!-- log end -->

        <!-- 上传组件包 -->
        <dependency>
            <groupId>commons-fileupload</groupId>
            <artifactId>commons-fileupload</artifactId>
            <version>1.3.1</version>
        </dependency>
        <dependency>
            <groupId>commons-io</groupId>
            <artifactId>commons-io</artifactId>
            <version>2.4</version>
        </dependency>
        <dependency>
            <groupId>commons-codec</groupId>
            <artifactId>commons-codec</artifactId>
            <version>1.9</version>
        </dependency>
    </dependencies>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.1</version>
                <configuration>
                    <source>1.7</source>
                    <target>1.7</target>
                    <encoding>UTF8</encoding>
                </configuration>
            </plugin>

            <plugin>
                <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.1</version>
                <configuration>
                    <server>tomcat7</server>
                    <port>9999</port>
                </configuration>
            </plugin>
        </plugins>
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

> UserDao.xml

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org/DTD Mapper 3.0" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="com.zui.dao.UserDao">
    <!-- 自定义返回结果集 -->
    <!--<resulltType id="userMap" type="UserBean">-->
        <!--<id property="id" column="id" javaType="java.lang.Integer"></id>-->
        <!--<result property="username" column="username" javaType="java.lang.String"></result>-->
        <!--<result property="password" column="password" javaType="java.lang.String"></result>-->
        <!--<result property="account" column="account" javaType="java.lang.Double"></result>-->
    <!--</resulltType>-->
    <!--<resulltType id="userMap" type="User"></resulltType>-->
    <!--//查询-->
    <!--public User getUserById(String id);-->
    <select id="getUserById" resultType="User" parameterType="java.lang.String">
        select * from t_user where id=#{id}
    </select>
    <!--//查询全部-->
    <!--public List<User> getAllUser();-->
    <select id="getAllUser" resultType="User">
        select * from t_user
    </select>
    <!--//分页查询-->
    <!--public List<User> query();-->
    <select id="query" resultType="User">
        select * from t_user
    </select>
    <!--//增加-->
    <!--public void addUser(User user);-->
    <insert id="addUser" parameterType="User">
        insert into t_user values(#{id},#{username},#{password})
    </insert>
    <!--//修改-->
    <!--public void updateUser(User user);-->
    <update id="updateUser" parameterType="User">
        update t_user set username=#{username},password=#{password} where id=#{id}
    </update>
    <!--//删除-->
    <!--public void removeUser(User user);-->
    <delete id="removeUser" parameterType="User">
        delete t_user where id=#{id}
    </delete>
    <!--//根据id删除-->
    <!--public void removeUserById(String id);-->
    <delete id="removeUserById" parameterType="java.lang.String">
        delete t_user where id=#{id}
    </delete>

    <!--//批量删除-->
    <!--public void batchRemoveUser(List<String> userIds);-->
    <delete id="batchRemoveUser" parameterType="java.util.List">
        delete t_user where id in
        <foreach collection="userIds" item="id" separator="," open="(" close=")">
            #{id}
        </foreach>
    </delete>

    <!--//批量添加-->
    <!--public void batchAddUser(List<User> userList);-->
    <insert id="batchAddUser"  parameterType="java.util.List">
        insert into t_user
        <foreach collection="userLisr" item="user" separator=",">
            <if test="id = null">
                (uuid(),#{username},#{password})
            </if>
            <if test="id != null">
                (#{id},#{username},#{password})
            </if>
        </foreach>
    </insert>

    <!--&lt;!&ndash; 批量操作和foreach标签 &ndash;&gt;-->

    <!--<insert id="batchInsertUser" parameterType="java.util.List">-->
        <!--insert into t_user values-->
        <!--<foreach collection="users" item="users" separator=",">-->
            <!--(null,#{users.username},#{users.password},#{users.account})-->
        <!--</foreach>-->
    <!--</insert>-->


    <!--<delete id="batchDeleteUser">-->
        <!--delete from t_user where id in (-->
        <!--<foreach collection="list" item="list" separator=",">-->
            <!--#{id}-->
        <!--</foreach>-->
        <!--)-->
    <!--</delete>-->

    <!--&lt;!&ndash;collection 为用于遍历的元素（必选），支持数组、List、Set  &ndash;&gt;-->
    <!--&lt;!&ndash; item 表示集合中每一个元素进行迭代时的别名. &ndash;&gt;-->
    <!--&lt;!&ndash;separator表示在每次进行迭代之间以什么符号作为分隔 符.  &ndash;&gt;-->

    <!--&lt;!&ndash;#在生成SQL时，对于字符类型参数，会拼装引号-->
         <!--$在生成SQL时，不会拼装引号，可用于order by之类的参数拼装-->
      <!--&ndash;&gt;-->
    <!--<select id="pagerUser" parameterType="java.util.Map" resulltType="userMap">-->
        <!--select * from t_user where 1=1-->
        <!--<if test="username!=null">-->
            <!--and username like '%${username}%'-->
        <!--</if>-->
        <!--limit ${index},${pageSize}-->
    <!--</select>-->

    <!--<select id="countUser" parameterType="java.util.Map" resultType="int">-->
        <!--select count(*) from t_user where 1=1-->
        <!--<if test="username != null">-->
            <!--and username like '%${username}%'-->
        <!--</if>-->
    <!--</select>-->

</mapper>

> UserDao.java

package com.zui.dao;

import com.zui.beans.User;

import java.util.List;
import java.util.Map;


public interface UserDao
{
    //查询
    public User getUserById(String id);
    //查询全部
    public List<User> getAllUser();
    //分页查询
    public List<User> query();

    //增加
    public void addUser(User user);
    //修改
    public void updateUser(User user);
    //删除
    public void removeUser(User user);
    //根据id删除
    public void removeUserById(String id);

    //批量删除
    public void batchRemoveUser(List<String> userIds);
    //批量添加
    public void batchAddUser(List<User> userList);
}

> UserController.java

package com.zui.controller;

import com.zui.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

import javax.servlet.http.HttpServletRequest;
import java.util.Map;


@Controller
@RequestMapping("/user/")
public class UserController
{

    @Autowired
    private UserService userService;

    @ResponseBody
    @RequestMapping("remove")
    public void removeUser(){

    }

    @ResponseBody
    @RequestMapping("query")
    public Map<String,Object> getUserByPage(HttpServletRequest request){
        //当前页
        int pageNo=Integer.parseInt(request.getParameter("page"));
        //每页条数
        int pageSize=Integer.parseInt(request.getParameter("rows"));
        return userService.query(pageNo,pageSize);
    }

}

> UserService.java

package com.zui.service;

import com.zui.beans.User;

import java.util.List;
import java.util.Map;


public interface UserService
{
    //id查询
    public User getUserById(String id);
    //查询全部
    public List<User> getAllUser();
    //分页查询
    public Map<String,Object> query(Integer pageNo, Integer pageSize);

    //增加
    public void addUser(User user);
    //修改
    public void updateUser(User user);
    //删除
    public void removeUser(User user);
    //根据id删除
    public void removeUserById(String id);

    //批量删除
    public void batchRemoveUser(List<String> userIds);
    //批量添加
    public void batchAddUser(List<User> userList);

}

> UserServiceImpl.java

package com.zui.service;

import com.github.pagehelper.PageHelper;
import com.github.pagehelper.PageInfo;
import com.zui.beans.User;
import com.zui.dao.UserDao;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.HashMap;
import java.util.List;
import java.util.Map;

@Service
public class UserServiceImpl implements UserService
{
    @Autowired
    private UserDao userDao;


    @Override
    public User getUserById(String id)
    {
       return userDao.getUserById(id);
    }

    @Override
    public List<User> getAllUser()
    {
        return userDao.getAllUser();
    }

    @Override
    public Map<String, Object> query(Integer pageNo, Integer pageSize)
    {
        pageNo = pageNo == null ? 1 : pageNo;
        pageSize = pageSize == null ? 10 : pageSize;
        PageHelper.startPage(pageNo, pageSize);
        List<User> list = userDao.query();
        //用PageInfo对结果进行包装
        PageInfo<User> page = new PageInfo<User>(list);

        Map<String, Object> map = new HashMap<String, Object>();
        map.put("total", page.getTotal());
        map.put("rows", page.getList());
        return map;
    }

    @Override
    public void addUser(User user)
    {
        userDao.addUser(user);
    }

    @Override
    public void updateUser(User user)
    {
        userDao.updateUser(user);
    }

    @Override
    public void removeUser(User user)
    {
        userDao.removeUser(user);
    }

    @Override
    public void removeUserById(String id)
    {
        userDao.removeUserById(id);
    }

    @Override
    public void batchRemoveUser(List<String> userIds)
    {
        userDao.batchRemoveUser(userIds);
    }

    @Override
    public void batchAddUser(List<User> userList)
    {
        userDao.batchAddUser(userList);
    }
}

> userManage.html

<link rel="stylesheet" type="text/css" href="static/easyui/themes/default/easyui.css">
<link rel="stylesheet" type="text/css" href="static/easyui/themes/icon.css">
<script type="text/javascript" src="static/easyui/jquery-1.7.2.min.js"></script>
<script type="text/javascript" src="static/easyui/jquery.easyui.min.js"></script>
<script type="text/javascript" src="static/easyui/locale/easyui-lang-zh_CN.js"></script>
<script>
		$(function(){
		/**
			$('#table_user').datagrid({
				url: 'datagrid_user.json',
				title: '用户记录',
				width: 1050,
				height: 400,
				fitColumns: true,
				nowrap:false,
				columns:[[
					{field:'userid',title:'用户id',width:80},
					{field:'username',title:'用户名',width:120},
					{field:'rolename',title:'用户角色',width:240,align:'left'}
				]]
			});*/

			 $('#list_data').datagrid({
                title:'应用系统列表',
                iconCls:'icon-edit',//图标
                width: 700,
                height: 'auto',
                nowrap: false,
                striped: true,
                border: true,
                collapsible:false,//是否可折叠的
                fit: true,//自动大小
                url:'user/query',
                //sortName: 'code',
                //sortOrder: 'desc',
                remoteSort:false,
                idField:'fldId',
                singleSelect:false,//是否单选
                pagination:true,//分页控件
                rownumbers:true,//行号
                frozenColumns:[[
                    {field:'ck',checkbox:true}
                ]],
                toolbar: [{
                    text: '添加',
                    iconCls: 'icon-add',
                    handler: function() {
                        openDialog("add_dialog","add");
                    }
                }, '-', {
                    text: '修改',
                    iconCls: 'icon-edit',
                    handler: function() {
                        openDialog("add_dialog","edit");
                    }
                }, '-',{
                    text: '删除',
                    iconCls: 'icon-remove',
                    handler: function(){
                        delAppInfo();
                    }
                }],
            });
            //设置分页控件
            var p = $('#list_data').datagrid('getPager');
            $(p).pagination({
                pageSize: 10,//每页显示的记录条数，默认为10
                pageList: [5,10,15],//可以设置每页记录条数的列表
                beforePageText: '第',//页数文本框前显示的汉字
                afterPageText: '页    共 {pages} 页',
                displayMsg: '当前显示 {from} - {to} 条记录   共 {total} 条记录',
                /*onBeforeRefresh:function(){
                    $(this).pagination('loading');
                    alert('before refresh');
                    $(this).pagination('loaded');
                }*/
            });
		});

</script>
<!--<div class="toolbar">-->
    <!--&lt;!&ndash;<a id="btn_add" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-add'"><span class="l-btn-left"><span class="l-btn-text icon-add" style="padding-left: 20px;">添加</span></span></a>&ndash;&gt;-->
    <!--<a id="btn_add" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-add'">添加</a>-->
    <!--<a id="btn_remove" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-remove'">删除</a>-->
    <!--<a id="btn_save" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-save'">保存</a>-->
    <!--<a id="btn_reload" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-reload'">刷新</a>-->
    <!--<input type="text" id="input_search">-->
    <!--<a id="btn_search" href="#" class="easyui-linkbutton l-btn" data-options="iconCls:'icon-search'">搜索</a>-->
<!--</div>-->
<!--<hr></hr>-->
<!--<table id="table_user"></table>-->


<table id="list_data" cellspacing="0" cellpadding="0">
    <thead>
    <tr>
        <th field="id" width="100">id</th>
        <th field="username" width="100">用户名</th>
        <th field="password" width="100">角色列表</th>
    </tr>
    </thead>
</table>

> main.html

<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	<title>Complex Layout - jQuery EasyUI Demo</title>
	<link rel="stylesheet" type="text/css" href="static/easyui/themes/default/easyui.css">
	<link rel="stylesheet" type="text/css" href="static/easyui/themes/icon.css">
	<script type="text/javascript" src="static/easyui/jquery-1.7.2.min.js"></script>
	<script type="text/javascript" src="static/easyui/jquery.easyui.min.js"></script>
	<script type="text/javascript" src="static/easyui/locale/easyui-lang-zh_CN.js"></script>
	<script>
		$(function(){
			$('#tt2').datagrid({
				title:'My Title',
				iconCls:'icon-save',
				width:600,
				height:550,
				nowrap: false,
				striped: true,
				fit: true,
				url:'datagrid_data.json',
				sortName: 'code',
				sortOrder: 'desc',
				idField:'code',
				frozenColumns:[[
	                {field:'ck',checkbox:true},
	                {title:'code',field:'code',width:80,sortable:true}
				]],
				columns:[[
			        {title:'Base Information',colspan:3},
					{field:'opt',title:'Operation',width:100,align:'center', rowspan:2,
						formatter:function(value,rec){
							return '<span style="color:red">Edit Delete</span>';
						}
					}
				],[
					{field:'name',title:'Name',width:120},
					{field:'addr',title:'Address',width:120,rowspan:2,sortable:true},
					{field:'col4',title:'Col41',width:150,rowspan:2}
				]],
				pagination:true,
				rownumbers:true
			});
		});
	</script>
</head>
<body class="easyui-layout">
	<div data-options="region:'north',split:true" title="North Title" style="height:100px;padding:10px;">
		<p>The north content.</p>
	</div>
	<div data-options="region:'south',split:true" title="South Title" style="height:100px;padding:10px;background:#efefef;">
		<div class="easyui-layout" data-options="fit:true" style="background:#ccc;">
			<div data-options="region:'center'">sub center</div>
			<div data-options="region:'east',split:true" style="width:200px;">sub center</div>
		</div>
	</div>
	<div data-options="region:'east',iconCls:'icon-reload',split:true" title="Tree Menu" style="width:180px;">
		<ul class="easyui-tree" data-options="url:'tree_data.json'"></ul>
	</div>
	<div data-options="region:'west',split:true" title="West Menu" style="width:150px;padding1:1px;overflow:hidden;">
		<div class="easyui-accordion" data-options="fit:true,border:false">
            <style>
                #sys_mng li{margin-top:5px}
            </style>
			<div id="sys_mng" title="系统管理" style="padding:10px;overflow:auto;">
                <ul class="easyui-tree">
                    <li id="user_mng">
                        <span>用户管理</span>
                    </li>
                    <li>
                        <span>角色管理</span>
                    </li>
                    <li>
                        <span>权限管理</span>
                    </li>
                    <li>
                        <span>菜单管理</span>
                    </li>
                </ul>
			</div>
			<div title="Title2" data-options="selected:true" style="padding:10px;">
			</div>
			<div title="Title3" style="padding:10px">
			</div>
		</div>
	</div>
	<div data-options="region:'center'" title="Main Title" style="overflow:hidden;">
		<div id="div_tabs" class="easyui-tabs" data-options="fit:true,border:false">
			<div title="Tab1" style="padding:20px;overflow:hidden;">

			</div>
			<div title="Tab2" data-options="closable:true" style="padding:20px;"></div>
			<div title="Tab3" data-options="iconCls:'icon-reload',closable:true" style="overflow:hidden;padding:5px;">
                <div class="toolbar">
                    <a id="add" href="#" class="easyui-linkbutton" data-options="iconCls:'icon-add'">添加</a>
                    <a href="#" class="easyui-linkbutton" data-options="iconCls:'icon-remove'">删除</a>
                    <a href="#" class="easyui-linkbutton" data-options="iconCls:'icon-save'">保存</a>
                    <a href="#" class="easyui-linkbutton" data-options="iconCls:'icon-search'">搜索</a>
                </div>
				<table id="tt2"></table>
			</div>
		</div>
	</div>
</body>
<script>
    $(function(){
        //页面加载
        loadUI();
        //事件监听
        registerEvent();
    });

    function loadUI(){

    }

    function registerEvent(){
        $("div[node-id='user_mng']").bind("click",function(){
            addTab("用户管理",'userManage.html');
        });
    }

    //添加tab
    function addTab(title, url){
        if ($('#div_tabs').tabs('exists', title)){
                $('#div_tabs').tabs('select', title);
        } else {
            var content = '<iframe scrolling="auto" frameborder="0"  src="'+url+'" style="width:100%;height:100%;"></iframe>';
            $('#div_tabs').tabs('add',{
                title:title,
                content:content,
                closable:true
            });
        }
    }

</script>
</html>

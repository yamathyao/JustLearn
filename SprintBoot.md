# SpringBoot 核心功能

### 1.独立运行项目

SprintBoot 可以以 jar 包形式独立运行，运行一个 SpringBoot 项目只需要通过 java -jar xxx.jar 来运行。

### 2.内嵌 servlet 容器

SpringBoot 可以选择内嵌 tomcat，netty 或者 Undertow，这样无需以 war 包形式部署项目。

### 3.提供 starter 简化 Maven 配置

Spring 提供了一系列的 start pom 来简化 Maven 的依赖加载。例如，使用了 spring-boot-starter-web，会自动加入依赖包。

### 4.自动装配 Spring

SpringBoot 会根据在类路径中的 jar 包，类为 jar 包里面的类自动配置 Bean，这样会极大的减少要使用的配置。
当然 SpringBoot 只考虑大多数的开发场景，并不是所有的场景，若在实际开发中需要配置 Bean，而 SpringBoot 没有提供支持，则可以自定义配置。

### 5.准备生产的应用监控

SpringBoot 提供基于 http ssh telnet 对运行时的项目进行监控。

### 6.无代码生产和xml配置

SpringBoot 不是借助与代码生成来实现的，而是通过条件注解来实现的，这是 Spring4.x 提供的新特性。

# SpringBoot优缺点

### 优点

· 快速构建项目

· 对主流开发框架的无配置集成

· 项目可独立运行，无需外部依赖 Servlet 容器

· 提供运行时的应用监控

· 极大提高了并发，部署效率

· 与云计算的天然集成

# SpringBoot 特性

· 创建独立的 Spring 项目

· 内置 tomcat 和 Jetty 容器

· 提供 starter POMs 来简化 Maven 配置

· 提供来一系列大型项目中常见的非功能性特性，如安全，指标，健康检测，外部配置等。

· 完全没有代码生成和 xml 配置文件

# SpringBoot Cli

SpringBoot CLI 是 SpringBoot 提供的控制台命令工具。

# SpringBoot Maven 构建项目

spring-boot-starter-parent ：是一个特殊 Start、他用来提供相关的 Maven 依赖项，使用之后，常用的包依赖可以省去 version 标签。

# SpringBoot 几个常用的注解

（1） @RestController 和 @Controller 指定一个类，作为控制器的注解，并说明其区别。

（2） @RequestMapping 方法级别的映射注解。

（3） @EnableAutoConfiguration 和 @SpringBootApplication 是类级别注解，根据 Maven 依赖的 jar 来自动猜测完成正确的 Spring 的对应配置。
只要引入了 spring-boot-starter-web 的依赖，默认会自动配置 Spring MVC 和 Tomcat 容器。

（4） @Configuration 类级别的注解，一般这个注解，用来标识 main 方法所在的类，完成元数据 bean 的初始化。

（5） @ComponentScan 类级别的注解，自动扫描加载所有的 Spring 组件包括 Bean 注入，一般用在 main 方法所在的类上。

（6） @ImportResource 类级别注解，当必须使用一个 xml 的配置时，使用 @ImportResource 和 @Configuration 来标识这个文件资源的类。

（7） @Autowired 注解，一般结合 @ComponentScan 注解，来自动注入一个 Service 或 Dao 级别的 Bean。

（8） @Component 类级别注解，用来标识一个组件，用此注解标识后， SpringBoot 才会正确识别。

（9） SpringBoot 是如何管理事务的，直接 @Transactional 就行，在方法就是方法事务，类上就是类事务。

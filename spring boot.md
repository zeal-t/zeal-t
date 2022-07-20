## spring boot

#### 1.优点

![image-20220510104727010](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220510104727010.png)

#### 2,微服务

微服务：架构风格，是一种小型服务，可以通过http 的方式进行互通。

每一个功能元素都是一个可升级,替换的软件单元

#### 3.pom

父项目版本仲裁

```
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.6.6</version>
    <relativePath/> <!-- lookup parent from repository -->
</parent>


```

```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

spring-boot-starter场景使用器



```
@SpringBootApplication
@SpringBootConfiguration 标志是一个springboot的配置类
@EnableAutoConfiguration 自动配置
  @AutoConfigurationPackage
  自动配置包
   @Import({Registrar.class}) 底层注解；导入组件
  

```

给主配置类@SpringBootApplication所在包所有的以及所有子包的所有组件扫描到容器中

#### 4.配置

```yaml
server:
  port: 8082
spring:
  application:
    name: treatment
  datasource:
    username: root
    password: 123456
    url: jdbc:mysql://localhost:3306/interesting learn?useUnicode=true&characterEncoding=UTF-8
    driver-class-name: com.mysql.cj.jdbc.Driver
  web:
    resources:
      static-locations: classpath:/META-INF/resources/, classpath:/resources/, classpath:/static/, classpath:/public/, file:/E:/interesting-english/,file:/E:/interesting-english/word/

mybatis:
  mapper-locations: classpath:mapper/*.xml
  type-aliases-package: com.chz.entity
mybatis-plus:
  configuration:
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl
```

yml 文件，以数据为中心

@configurationpropertyies（perfix=“ ”）

map：{k1：v1，k2：v2}

list：

​     -1

![image-20220510152959519](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220510152959519.png)

配置文件优先级

![image-20220510164627703](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220510164627703.png)

![image-20220510165827177](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220510165827177.png)

命令行进行写配置 --server.port=8088

![image-20220510170409890](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220510170409890.png)
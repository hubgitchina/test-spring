- JPA变化包括：

  delete改为deleteById

  save(Iterable<S>)改为saveAll

  findOne改为getOne或findById

  PageRequest构建分页对象提交了方便的静态方法

  ```
  public static PageRequest of(int page, int size)
  ```

- druid pom依赖改为：

```
<dependency>
	<groupId>com.github.drtrang</groupId>
    <artifactId>druid-spring-boot2-starter</artifactId>
    <version>1.1.10.2</version>
</dependency>
```

- Spring Boot、SpringCloud变化：

  bootstrap.yml配置中不能引用application.yml中的变量，比如变量${spring.application.name}，可能遇到的问题是程序刚启动就自动退出，没有任何错误提示

ErrorController类package变化org.springframework.boot.web.servlet.error

application.yml中Server配置变化：
server.context-path变化为server.servlet.context-path

@EnableFeignClients注解package变为org.springframework.cloud.openfeign

@FeignClient注解package变为org.springframework.cloud.openfeign

- Spring cloud 依赖变化包括：


	   <!-- feign -->
	    <dependency>
	       	<groupId>org.springframework.cloud</groupId>
	    	<artifactId>spring-cloud-starter-openfeign</artifactId>
	    </dependency>	
		<!-- ribbon -->
		<dependency>
	        <groupId>org.springframework.cloud</groupId>
	        <artifactId>spring-cloud-starter-netflix-ribbon</artifactId>
	    </dependency>	
		<!-- hystrix -->
		<dependency>
	        <groupId>org.springframework.cloud</groupId>
	        <artifactId>spring-cloud-starter-netflix-hystrix</artifactId>
	    </dependency>		

- Zookeeper服务器版本要求为3.5以上

  ```
  docker pull zookeeper:3.5
  docker run -p 2181:2181 --name zk3.5 --restart always -d zookeeper:3.5
  ```



- 
  Spring Boot官方迁移指南

  https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.0-Migration-Guide

- Spring Cloud 升级到Finchley版本后需要注意的地方

  https://www.cnblogs.com/sunny3096/p/9792342.html
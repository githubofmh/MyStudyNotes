# Spring Boot 学习

## 目录结构

```
com
  +- example
    +- myproject
      +- Application.java
      |
      +- domain
      |  +- Customer.java
      |  +- CustomerRepository.java
      |
      +- service
      |  +- CustomerService.java
      |
      +- controller
      |  +- CustomerController.java
      |  
      | +- config
      |  +- swagerConfig.java
      |
```

1. ` Application.java`是项目的启动类
2. domain目录主要用于实体（Entity）与数据访问层（Repository）
3. service 层主要是业务类代码
4. controller 负责页面访问控制
5. config 目录主要放一些配置类

## @SpringBootApplication

可以看出大概可以把 `@SpringBootApplication `看作是 `@Configuration`、`@EnableAutoConfiguration`、`@ComponentScan ` 注解的集合。根据 SpringBoot官网，这三个注解的作用分别是：

- `@EnableAutoConfiguration`：启用 SpringBoot 的自动配置机制
- `@ComponentScan`： 扫描被`@Component` (`@Service`,`@Controller`)注解的bean，注解默认会扫描该类所在的包下所有的类。
- `@Configuration`：允许在上下文中注册额外的bean或导入其他配置类。

## Controller

### @RestController

@RestController是Spring 4 之后新加的注解，如果在Spring4之前开发 RESTful Web服务的话，你需要使用@Controller 并结合@ResponseBody注解，也就是说@Controller +@ResponseBody= @RestController

### @RequestBody  和  @RequestParam

- 在GET请求中，不能使用@RequestBody。
- 在POST请求，可以使用@RequestBody和@RequestParam，但是如果使用@RequestBody，对于参数转化的配置必须统一。

### @PathVariable

@PathVariable 是RSET风格

### @PathParam
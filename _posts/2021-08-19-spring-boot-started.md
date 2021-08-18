---
title: "Spring Boot? started?"
last_modified_at: 2021-08-19
toc: true
toc_sticky: true
categories:
  - java
tags:
  - springboot
---

# #SpringBoot #Start
## 2021.08.19
> SpringBoot 를 처음 접한게 언제였더라..  

2018년 즈음 이였다.  
Study를 했다거나 Side Project 를 하면서 접한건 아니였다.  

나는 그저 새로운 프로젝트 운영을 하게 되었고,  
그냥 그 프로젝트가 Spring Boot로 되어 있었다.

### SpringBoot
> Spring이면 Spring이지 Boot는 또 뭐야?

요즘 Java를 시작하는 사람들이 제일 처음 접하는 프레임웍이 아마 SpringBoot일 것 같다.
보편적으로 많이 사용하고있고, 많이 사용하는건 보편적으로 좋다. 응..?  

> 👉 [spring.io-spring-boot](https://spring.io/projects/spring-boot){:target="_blank"}

위 링크에 가보면 다음과 같은 특징을 가지고 있다고 한다.  

⭐️Tip : 일반적으로 특징은 중요도에 따라 두괄식으로 써져있을 확율이 높다.
{: .notice--info}

#### Features
- ⭐️ Create stand-alone Spring applications
- Embed Tomcat, Jetty or Undertow directly (no need to deploy WAR files)
- Provide opinionated 'starter' dependencies to simplify your build configuration
- Automatically configure Spring and 3rd party libraries whenever possible
- Provide production-ready features such as metrics, health checks, and externalized configuration
- Absolutely no code generation and no requirement for XML configuration

##### 정리하면
> stand-alone한 spring application이고   

- 웹서버도 내장되있고 
- 의존성 관리도 해주고
- 상태 체크도 외부 환경설정도 제공해주고
- 쓸데없는 코딩 안해도 되고
- 좋은거다.. 아 너무 좋다..

---

#### 시작! StartUp!
> 멀리 돌아왔다. SpringBoot Application을 실행해보자  

1. SpringBoot 프로젝트 생성
2. 시작!
  - [default](#startup---default)
  - [customizing](#startup---customizing)
  - [builder](#startup---builder)
3. 끝

##### [StartUp - default](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.spring-application){:target="_blank"}
👉 [github commit](https://github.com/angelsocer-g/spring-boot-started/commit/cb90f80151956181b0353ff011ffd1dab0030a65){:target="_blank"}
```java
@SpringBootApplication
public class SpringBootStartedApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringBootStartedApplication.class, args);
    }

}
```
##### [StartUp - Customizing](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.spring-application.customizing-spring-application){:target="_blank"}
👉 [github commit](https://github.com/angelsocer-g/spring-boot-started/commit/cb90f80151956181b0353ff011ffd1dab0030a65){:target="_blank"}
```java
@SpringBootApplication
public class SpringBootStartedApplication {

    public static void main(String[] args) {
        SpringApplication application = new SpringApplication(SpringBootStartedApplication.class);
        application.run(args);
    }

}
```
##### [StartUp - builder](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.spring-application.fluent-builder-api){:target="_blank"}
👉 [github commit](https://github.com/angelsocer-g/spring-boot-started/commit/696db3c3231003d2395b715257013723df0b6f1f){:target="_blank"}
```java
@SpringBootApplication
public class SpringBootStartedApplication {

    public static void main(String[] args) {
        new SpringApplicationBuilder()
                .sources(SpringBootStartedApplication.class)
                .run(args);
    }

}
```

## References
- [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot){:target="_blank"}
- [https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.spring-application](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html#features.spring-application){:target="_blank"}



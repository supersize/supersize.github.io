---
layout : single
title : "Spring Dependencies"
categories: Spring
tag: [Spring]
toc: true
---
#  Spring mvc 프로젝트 생성시 필요한 기본 의존성 들이 있다.
## Spring-beans 
    : 기본 중 기본 의존성. 객체생성, 설정, 의존성 주입 등을 한다.

## Spring-web
    : 스프링 웹앱을 위한 함수들을 제공.

## Spring-mvc
    : 스프링 웹앱을 위한 프레임워크 제공. MVC 아키텍쳐, 리퀘스트 매핑, 예외 처리 등
    <b>spring-mvc는 spring-beans와 spring-web 모두 필요하다!!!</b>
    


## ** 하지만 실무에선 spring-beans, spring-cre 선언 안하고 작업하는 경우를 많이 봤고 구글링 결과 
    google bard에 의하면
> Most Spring web-related dependencies, like spring-web and spring-webmvc, have spring-beans, spring-core as a transitive dependency. This means that when you include them in your 
>  project, Spring automatically downloads and includes spring-beans as well, even though it's not explicitly listed in your pom.xml.

    또한, 부모 pom.xml에서 상속 받으면 선언하지 않아도 되는 경우도 있고, 스프링 부트 같은 경우 "spring-boot-starter-web" 안에 대부분 필요한 의존성들이 들어있다고 한다.


# Spring Data JPA 
     : JPA(Java Persistence API) provides a higher-level abstraction layer for accessing relational databases.

    1. Spring-content 
        : entity mapping between domanin and repository, integration with spring security. 

    2. spring-orm 
        : This dependency is now deprecated since spring framwork 5.0 in favor of spring-data-jpa. ORM means object-relational mapping  

    3. spring-jdbc 
        : interacting with relational databases using JDBC by low-level access to database, which interacts with the database directly using Java code and SQL statements.
        spring-jdcb is usually Manual Connection Management, direct interaction with database, Manual Data Mapping. Spring-JDBC is good for perfomance optimazation.

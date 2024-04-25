---
layout : single
title : "스프링 프로젝트 구조"
categories: Spring
tag: [Spring]
toc: true
---
#  src/main/java 
비지니스 로직 등 자바 파일들이 저장됨.

# src/main/resources
static, template 폴더로 주로 나뉘고
static에는 정적파일 css, xml, properties 등 각종 설정 파일이 저장됨.
template에는 이메일 template 등이 쌓임.

# src 폴더 
src/main/webapp 디렉토리로 web에 관한 모든 것들이 저장되는 <b>루트 폴더</b>이다.
빌드시 src/main 내에 있는 파일들이 패키징된다.

1. src/main/webapp/resources 
    컨트롤러가 요청을 가로채지 않고 사용자가 바로 접근할 수 있도록 따로 설정해서 사용하는 곳.

2. src/main/webapp/WEB-INF/classes 
    컴파일된 파일들이 보관되는 곳 

3. src/main/webapp/WEB-INF/spring
    스프링 컨테이너를 생성하기 위한 스프링 환경설정 파일 (context)이 보관 되는 곳이다.

4. src/main/webapp/WEB-INF/view
View(UI)를 구현할 수 있는 JSP 파일이 들어있는 디렉토리이다. 이 폴더가 루트( / ) 의 기준점 이고 Controller에서 보낸 데이터를 ${}를 통해 사용할 수 있다.


5. web.xml 파일
WAS가 최초 구동시, 가장 먼저 읽는 파일로 웹 애플리케이션의 설정을 구성한다. 스프링의 context 경로, DispatcherSevlet 설정 등을 할 수 있다.



참고 : https://velog.io/@taesan/Spring-%ED%8F%B4%EB%8D%94-%EA%B5%AC%EC%A1%B0




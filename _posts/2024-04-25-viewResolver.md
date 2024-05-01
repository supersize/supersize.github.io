---
layout : single
title : "로컬에서 테스트시 localhost URL 문제, url에 포트 번호를 적는 건에 대하여"
categories: Spring
tag: [Spring]
toc: true
---
##  url을 localhost로 변경 후 이클립스에서 was 실행하자 url을 못찾는 상황 발생. 

구글링 중에 localhost는 "https"가아니라 "http"로 바꿔야한다는 것을 발견. 이대로 실행하니 작동하기 시작.


## 사이트 입력할 때 왜 포트번호는 생략하는 것인가??
### 구글 제미니에 문의 결과.
>대부분의 웹 사이트는 기본적인 HTTP(80) 또는 HTTPS(443) 포트를 사용합니다. 브라우저는 사용자가 포트 번호를 명시적으로 입력하지 않아도 기본 포트를 자동으로 사용하도록 설정되어 있습니다.
라고 한다. 

#### 추가적으로 기본 포트 번호는
> 8080 : http 서비스 포트
> 8443 or 443 : SSL (https)
> 8009 : apache httpd와 같은 웹서버와 내부 연결 포트, 웹서버 유무에 따라 처리
> 8005 : shutdown 포트

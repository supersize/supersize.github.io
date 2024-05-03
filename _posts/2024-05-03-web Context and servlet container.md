---
layout : single
title : "what's different between sevlet container and web context?"
categories: spring
tag: [spring]
toc: true
---
## I thought....
    web context is the most telling part of web container, but it is single web application within servlet container.
    Also, sevlet container can host several web contexts.

## Servlet container
    Sevlet container provides runtime environments for java servlet or jsp and maintains http request/response, sevlet lifecycle.
    Sevlet container includes apache tomcat, jetty, undertow etc.


## how application works : lifecycle of servlet container
    server -> my application is loaded within a sevlet container(typically WAR file) -> servlet instantiation -> init() method
    -> service() method : handling reqeust, response, GET, POST etc. -> destroy() method

    

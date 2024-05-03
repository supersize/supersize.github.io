---
layout : single
title : "How to get ContextPath in Jsp"
categories: jsp
tag: [jsp]
toc: true
---
## el tag  
    ${pageContext.request.contextPath}

## jstl
    c:url : <c:url value='/' />


## etc
    <c:set var="path" value="<%=request.getContextPath() %>" />
    ${path }

    

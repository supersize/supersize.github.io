---
layout: post
title: State개념에 대해 알아보자.
tags: ['react']
catagories: ['react']
excerpt : "State개념이란 무엇일까?"
author:
 - kim,jae-heyong
date: 2022-02-03
---
## 들어가며
리액트에서 이벤트 다루는 방법을 공부한다.

## 리액트에서 이벤트 다룰시 규칙
  * 이벤트는 반드시 camelCase로 작성되어야한다. ex) onclick => onClick
  * 이벤트 선언은 문자열 형식이 아니라 {}안에 넣어서 사용되어야 한다. ex) onClick="add()" =? onClick={add} 
  * 더이상 스크립트 진행을 막기위해 return false가 아니라 preventDefault를 사용해야한다.  예를들면
```javascript
<form onsubmit="console.log('You clicked submit.'); return false">
  <button type="submit">Submit</button>
</form>
// 가 아니라

function Form() {
  function handleSubmit(e) {
    e.preventDefault();
    console.log('You clicked submit.');
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
// 이런 형식으로 작성해야한다.
```
여기서 리액트의 장점이 보여진다. 

### cross-browser compatibility
cross-browser compatibility는 웹호환성을 말한다. 우리는 코딩을 하면서 많은 것들을 활용한다.(css, html, javascript 등) 이런 것들이 서로 충돌하지 않도록 하는 것이 크로스 브라우징(cross-browser compatibility)이다. 리액트는 기존 native events들과 전형 겹치지 않기 때문에 충돌을 걱정할 필요가 없는 장점이 있다.


## 마치며
점점 어려워진다...
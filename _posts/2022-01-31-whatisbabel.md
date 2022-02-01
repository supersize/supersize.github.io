---
layout: post
title: Babel은 무엇일까?
tags: ['react']
catagories: ['react']
excerpt : "Babel이란 무엇일까?."
author:
 - kim,jae-heyong
date: 2022-01-31
---
## 들어가며
리액트를 공부하면서 많은 사람들이 Babel을 사용하고 있다는 이야기를 들었다. 그리고 리액트에서 조차 Babel을 사용할 것을 권장한다. Babel을 처음 접한 나는 간단히 Babel의 개념과 사용법에 대해서 포스팅하려 한다.

## Babel이란?
Babel은 최신화 되지 않은 웹브라우져나 웹환경에서 자바스크립트를 2015 이후 ESMA로 자동 변환해주는 역할을 한다. 
<ul>
    <li>문법변환</li>
</ul>


```javascript
// Babel Input: ES2015 arrow function
[1, 2, 3].map(n => n + 1);

// Babel Output: ES5 equivalent
[1, 2, 3].map(function(n) {
  return n + 1;
});
```
이런 기능은 우리가 비록 최신 자바스크립트를 제공해주지 않는 오래된 브라우져에서 웹페이지를 로드 할 지라도, 페이지를 문제 없이 볼 수 있게 해준다는 장점이 있다.

## 마치며
간단히 Babel의 사용에 대해 알아 보았다.
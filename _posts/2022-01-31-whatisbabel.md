---
layout: post
title: Babel은 무엇일까?
tags: ['react']
catagories: ['react']
excerpt : "Babel이란 무엇일까?."
author:
 - kim,jae-heyong
date: 2022-01-25
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

## Virtual Dom은 어떻게 작동하는 것일까?
사실 Virtual Dom과 Real Dom의 프로퍼티들은 거의 동일하다. 하지만 분명한 차이 하나는 Virtual Dom의 스냅샷 기능이다. 위 내용 처럼 만약 1~10이 있는 List를 생성했다면 Virtual Dom은 스냅샷을 찍어 놓고 변화를 감지하여 바뀐 부분만 Real Dom에서 변경해준다.

## 마치며
리액트 공부를 시작했다. 아직 갈길이 멀다. 
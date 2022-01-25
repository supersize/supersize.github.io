---
layout: post
title: Virtual Dom과 Real Dom의 차이점.
tags: ['react']
catagories: ['react']
excerpt : "Virtual Dom과 Real Dom의 차이점을 알아보자."
author:
 - kim,jae-heyong
date: 2022-01-25
---
## 들어가며
리액트는 프레임워크라고 알고 있는 사람도 많지만 사실 라이브러리이다. 2013 페이스북이 발표했다. 컴포넌트 구성되어 재사용성이 뛰어나다는 장점이 있다. 하지만 가장 큰 특징 중 한가지를 뽑으라면 바로 Virtual Dom과 Real Dom일 것이다. 오늘은 이 둘에 대해서 포스팅 해보고 싶다.

## Virtual Dom과 Real Dom의 차이점?
먼저 Real Dom에 List가 있다고 가정해보자. 이 List에는 1~10까지 숫자가 있다. 하지만 나는 맨뒤 10을 11로 변경한다고 했을때, Real Dom에서는 List 전체를 다시 로드해야한다. 하지만 vitual Dom에서는 마지막으로 변경된 11만 다시 로드해준다. 그러기에 훨씬 빠르고 부하가 안가게 데이터를 처리 할 수 있다. 

## Virtual Dom은 어떻게 작동하는 것일까?
사실 Virtual Dom과 Real Dom의 프로퍼티들은 거의 동일하다. 하지만 분명한 차이 하나는 Virtual Dom의 스냅샷 기능이다. 위 내용 처럼 만약 1~10이 있는 List를 생성했다면 Virtual Dom은 스냅샷을 찍어 놓고 변화를 감지하여 바뀐 부분만 Real Dom에서 변경해준다.

## 마치며
리액트 공부를 시작했다. 아직 갈길이 멀다. 
---
layout: post
title: 리액트에서 componet는 무엇일까?
tags: ['react']
catagories: ['react']
excerpt : "component는 자바의 class와 비슷한 개념인가?."
author:
 - kim,jae-heyong
date: 2022-02-01
---
## 들어가며
자바를 첫 언어로 시작한 나에게 컴포넌트란 단어는 생소하다. 어찌보면 자바의 클래스라는 개념과 유사해보이기도한다. 자바에서 클래스, 인스턴스는 중요한 개념인 것 같이 리액트의 컴포넌트 또한 아주 중요한 개념이란 느낌을 받았다. 그래서 정리해본다. 

## 컴포넌트(Component)의 역할
컴포넌트(Component)는 작성자가 UI를 독립적이고 재사용할 수 있게 만든다. 즉, 각 컴포넌트들은 사용자의 목적에 맞게 호출 될수도 안될수도 있다. 개념적으론, 컴포넌트는 자바스크립트의 함수와 비슷하다. 함수가 임의 매개 변수들을 갖듯이 __컴포넌트도 "props"라는 임의 매개변수를 무조건 갖는다.__ 또한, 반드시 리액트 요소(React elements)를 반환해야한다.

## 함수형 컴포넌트와 클래스형 컴포넌트
### 함수형 컴포넌트
컴포넌트를 가장 간단하게 선언하는 방법은 자바스크립트 함수형식으로 선언하는 것이다.
```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
사용가능한 리액트 컴포넌트가 되기 위한 조건
  * 최소 한개의 매개변수가 존재해야한다. (리액트에선 'props'가 존재하니 꼭 매개변수를 넣어 주어야한다.)
  * 반드시 리액트 요소(React Element)를 반환해야한다. 

### 클래스형 컴포넌트
클래스형 컴포넌트는 ES6에서 사용된다.
```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
리액트 입장에선 함수형 컴포넌트 == 클래스형 컴포넌트 라고 한다. 자세한 이유는 다음 챕터에...

## 컴포넌트를 다루는 법(Rendering a Component)
### 사용자 정의 컴포넌트
리액트 컴포넌트는 매개변수와 리액트 요소 반환값이 반드시 필요하다. 위에서 거창하게(?) 컴포넌트를 선언 할 수 도 있지만, 컴포넌트의 반환값이 리액트 요소이기 때문에 컴포넌트를 사용자 임의에 맞게 변수에 담을 수 있다.
```javascript
const element = <Welcome name="Sara" />;
```
리액트 요소는 DOM 태그로 표현할 수 있고 태그의 속성은 파라메터로 표현 가능하다. 위 코드는 반환 값이 리액트 요소이자 태그이며 태그의 속성은 파라메터로 표현하였다.(이 개념을 이해하는데 약간의 시간이 소요 되었다.)
### 주의 사항 
컴포넌트는 항상 대문자로 시작해야한다. 리액트는 소문자로 시작하는 컴포넌트는 DOM tag로 인식한다. like '<div>'

## 매개변수는 반드시 읽기 전용이어야 한다.
컴포넌트를 함수형 혹은 클래스형으로 선언하든지 간에 그 컴포넌트의 매개변수는 수정되서는 안된다. 도한 컴포는트는 반드시 순수 함수(pure function)이어야한다. 
```javascript
function sum(a, b) {
  return a + b;
}
```
만약 sum(5, 5)를 하면 반환값은 10가 나온다. 이렇게 어디서 어떻게 선언하든 sum(5, 5)는 10이 나오는 것이 '순수 함수'이다.

```javascript
var c = 10;
function sum2(a,b){
    return a + b + c;
}
```
하지만 외부 변수가 개입한다면 sum2(5, 5)는 항상 10일수 없다. 왜냐하면 sum2의 반환값은 외부 변수에 의해 변동 될 것이기 때문이다. 

## 마치며
컴포넌트라는 개념을 처음 접했다. 컴포넌트의 모든 기능을 일일이 알아보지 않았지만 대략적인 개념을 잡을 수 있어서 나중에 개발하는데 도움이 될 것같다. 
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
리액트 컴포넌트에 이어서 State에 대해서 공부한다.

## State란?
우리는 이전에 Component에 대해서 공부했다. 컴포넌트의 특징은 "props"라는 임의 매개변수를 무조건 갖는다는 것이다. State는 컴포넌트와 비슷하다. State는 private하고 컴포넌트에 의해 완전히 통제된다. 

## 함수형 컴포넌트를 클래스형으로 변환하기. 
  1. React.Component를 상속받은 ES6 class를 기존 이름과 동일하게 생성한다.
  2. 아무것도 없는 render()을 생성한다.
  3. 함수형 컴포넌트에 있던 내용들을 render()안에 넣는다.
  4. props를 render()안에있는 this.props로 대체한다.
  5. 이미 선언된 빈 함수형 컴포넌트를 제거한다.

### 변경 전,
```javascript
  function Clock(props) {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {props.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }

  function tick() {
    ReactDOM.render(
      <Clock date={new Date()} />,
      document.getElementById('root')
    );
  }

  setInterval(tick, 1000);
``` 
### 변경 후,

```javascript
  class Clock extends React.Component {
    render() {
      return (
        <div>
          <h1>Hello, world!</h1>
          <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
        </div>
      );
    }
  }
``` 

뭐 이렇게 변경되었지만 딱히 달라지는건 없는 것 같다...
## 하지만 이제 부터 시작이다!
this.props.date를 this.state.dat로 변경하고, render()위에 생성자를 만들어준다. 그리고 그 생성자안에 this.state를 정의해준다.
```javascript
  class Clock extends React.Component {
    constructor(props) {
      super(props);
      this.state = {date: new Date()};
    }

    render() {
      return (
        <div>
          <h1>Hello, world!</h1>
          <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
        </div>
      );
    }
  }
``` 

### 생성자를 만들어서 Clock 클래스에 파라메터를 주지 않아도 된다.
```javascript
ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

## 'Mount'와 'Unmount'
'Mount'는 클래스형 혹은 함수형 컴포넌트가 맨처음으로 DOM에 랜더링 될때를 일컫는 용어이다.
반면, 'Unmount'는 그 컴포넌트가 제거될때 사용되는 말이다.

우린 마운드, 언마운트 될때 사용할 수 있는 코드를 추가할 수 있다.
```javascript
  componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }
```
이런 매서드들을 "생성주기 매서드(Lifecycle methods)"라 한다.

우리는 Clock을 매초마다 갱신해주기 위해 tick()를 추가하겠다.
```javascript
  tick() {
    this.setState({ // setState는 state를 set해주는 것 같다(?)
      date: new Date()
    });
  }
```

## State와 Lifecycle을 사용으로 얻을 수 있는 것!!
개념 정리하면서 들었던 의문은 '왜 이걸 사용하지?'였다. 컴포넌트의 속성 같으로 넣는게 훨씬 코드도 줄이고 편한데 말이다. 하지만 사용자에 의해서 계속해서 변할수 있는 데이터 즉, 고정되있는 데이터라면 굳이, 컴포넌트의 속성 같으로 넣어줄 필요가 없다. 클래서 안에서 고정적으로 작동하게 해주는 것이 안정적이다.

또한, State 개념에 대해서 정리하자면, State는 어떤 기능이나 함수를 말하는 것이 아니라, 값이 저장되는 방식을 말한다. 우리는 클래스 생성자에서 'this.state' 선언하여 많은 값들을 저장시킬수 있다. 그리고 state는 꼭 state일 필요는 없다 state2일수 도 있다.

## State 바르게 사용하기.
  1. State를 직접적으로 사용하지 말것.
  ```javascript
    // Wrong
    this.state.comment = 'Hello';
    // Correct
    this.setState({comment: 'Hello'});
  ```
  * setState()를 사용해서 값을 할당할 것. this.state에 값을 할당 할 수 있는 것은 오직 생성자 뿐이다.

  2. State 업데이트는 비동기 방식이다.
  * this.props와 this.state는 비동기식으로 업데이트 된다. 그래서 값 생성중엔 신뢰할 수 없는 경우도 생긴다.
  ```javascript
    // Wrong
    this.setState({
      counter: this.state.counter + this.props.increment,
    });
    // Correct
    this.setState((state, props) => ({
      counter: state.counter + props.increment
    }));
  ```
  * setState를 함수형으로 받으면 첫번째 파라미터는 바로 이전 state 값을 받아오고 이후 값은 현재 입력중인 props의 값을 받아온다.
  
  3. state 갱신은 병합된다.
  ```javascript
    constructor(props) {
      super(props);
      this.state = {
        posts: [],
        comments: []
      };
    }

    componentDidMount() {
      fetchPosts().then(response => {
        this.setState({
          posts: response.posts
        });
      });

      fetchComments().then(response => {
        this.setState({
          comments: response.comments
        });
      });
    }
  ```
  이런 세팅들은 서로 영향을 미치지 않고 각각 세팅해 줍니다.

## props와 state의 차이 점은 무엇일까?
props는 사용자에의해 입력될 데이터를 위해 사용될 목적이고, state는 내부에서 고정적으로 타인에의해 변형되지 않을 데이터를 사용하기 위핸 목적이있다.

## 마치며
State와 생명주기에 대해서 공부했다. 마지막 챕터에 데이터의 흐름(The Data Flows Down) 챕터가 있는데 간단히 요약하자면, 컴포넌트에 적용된 데이터는 자식 컴포넌트로 흘러 내려가는데, 그 흘러내려가느게 props, state, or hand-customized 된건지 알수 없다는 거다. 그래서 컴포넌트에 직접 데이터를 넣지 않는 이유기도 하다.
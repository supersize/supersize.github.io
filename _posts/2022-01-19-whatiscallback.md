---
layout: post
title: 콜백함수(Callback function)란 무엇일까?
tags: ['javascript']
catagories: ['javascript']
---
# 들어가며
개발을 하면서 콜백함수를 자주 접한다. 개념은 알고 있지만, 설명을 해보라면 쉽지 않을 것 같다. 콜백함수를 공부하면서 아직 머리 속에 정리가 안되어 있거나 추상적으로 자리잡고 있던 개념들을 없애기 위해 정리해본다.
<br><br><br><br>
# 콜백함수의 정의
콜백함수를 처음 접했을 땐, "callback?? 내가 뭔가 호출하면 return 값을 내가 설정한데로 처리해준다는 의미인가?"라고 생각했다. 또 이런 생각은 내 머리에서 쉽게 지워지지 않았다. 콜백함수란, 다른 함수의 파라메터로 던져진 함수인데, 이 때 던짐받은 함수 안에서 특정 행위가 완료됐을 때야 
비로소 작동한다. <u>**즉, 대기 타고 있다가 뭔가 실행되면 그 후 바로 실행된다는 의미**</u>다.  

아래는 모질라에서 가져온 예제 코드이다. 
```javascript
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```
processUserInput() 호출하면서 greeting()를 매개변수로 받는다. 하지만, 파라메터로 받은 greeting()함수는 실행 시점이 정해져있다(callback('Please enter your name.')). 만약, processUserInput() 함수 내에서 파라메터 callback을 선언하지 않았다면??? 'Hello Please enter your name.'은 출력되지 않았을 것이다.
<br><br><br><br>
# 마치며
사실 콜백함수를 자주 남발하면 콜백지옥에 빠지게 된다. 지금까지 콜백 지옥을 경험한적은 없지만... 이름 보안하기 위해서 promise() & deep() 함수가 사용된다고 한다. 더 공부해야겠다.
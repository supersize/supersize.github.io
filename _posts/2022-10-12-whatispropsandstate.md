---
    layout : single
    title : "What is props and state?"
    categories: React
    tag: [prorps, state, component, ]
---
#### I studyed about "props and state, and why ppl use them". I summerize here what I learned not to forget and to remind!

### "Component" you have to know before knowing "props and states"? 
1. what is <b>Component</b>?

> Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. <br/><br>
Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

// Component is similar to 'objedt' in Java
// But, component can be saved in variable 
// like
var element = <Welcoome name="Jae Hyeong" />

// the first character of component's name must be started by a capital letter.
// when saving components to variables, you can put some arguments and they are carried to the component and those arguments are used parameters as a 'props'. 
```
2. a function is a valid component if it returns react element.
```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>; // {props.name} is the react element
}
```

### Prop
1. Prop stands for "properties".
2. props are read-only variables extended by its parent(you can know it by referring to the upper codes).


### State
1. State is similar to props, but it is private and fully controlled by the component.

2. when you use "this.state", you are free to add additional field to the class manually if you need to store something that doesn't participate in the data flow.


|props|state|
|----|----|
|immutable|mutable|
|extended|stored local data|

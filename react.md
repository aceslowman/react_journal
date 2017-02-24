# React.JS

*This was written while working through tutorials at facebook.github.io, so expect some similarities in text. I will be going over this text in iterations, updating it with more of my own ideas, as I better understand React*

The browser DOM can be slow, and React.JS was created to address that issue, by creating and manipulating the DOM via JavaScript.

## Rendering elements

React elements are alternative to browser DOM elements, and are more efficient. We can *render* our react elements by passing the elements to the `ReactDOM.render(element,root)` function.

When you want to update an element in the ReactDOM, you don't update the element itself, you create a new element.

Finally, when you pass an element to React for rendering, it will only update what has changed. If you pass an element that already exists, character by character, fortunately nothing will render.

## Components and Props

Components are the core to making your ReactJS code more *modular*. They are essentially JavaScript functions, with some differences. For one, they accept *Props*, and they return *React elements*.

If you are already familiar with inheritance, it might help for you to see a component as a class that extends React.Component and returns the element.

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

is equivalent to:

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

A React element is not only DOM tags; the use of user-defined tags, such as `<Welcome name="Sara" />`, will call a function, named Welcome(), and any attributes of that tag are passed in as data to that function.

Here is an example of this:

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

**NOTE: as with classes in general, components should be named using a capital first letter.**

Components can also be called within each other, allowing you to combine multiple components into one component. Just have it return an element that includes your user-defined tags, which are the other components.

Components must have one root element, so if you are to combine components, wrap them in a single <div>, like this:

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

# React

## Hello world with React APIs

```js
const rootElement = document.getElementById("root");
const element = React.createElement(
  "div",
  { className: "container" },
  "Hello World"
);
ReactDOM.render(element, rootElement);
```

The element you want to create and then the children(any number possible). You can also write the children as `children` prop inside the the props object.

## JSX

```js
const element = <div className="container">Hello World</div>;

//OR

const props = {
  className: "container",
  children: "Hello world"
};
const element = <div {...props} />;

//OR, to override

const element = <div {...props} className="my__class_name" />;
```

Include babel standalone in the project and and change the script type to `text/babel` for on the fly compilation without any build system.

- `class` -> `className`
- Interpolation -- Insert any JS inside JSX

## Custom react components

```js
const message = props => <div>{props.msg}</div>;
const Message = props => <div>{props.msg}</div>;

//Can be used with createElement API
const element = (
  <div className="container">
    {React.createElement(message, { msg: "Hello World" })}
    {React.createElement(message, { msg: "Goodbye World" })}
    <Message msg="Hello World" />
  </div>
);
ReactDOM.render(element, rootElement);
```

## Validating props with PropTypes

```js
const SayHello = props => (
  <div>
    {" "}
    {props.firstName} {props.lastName}!{" "}
  </div>
);

const PropTypes = {
  string(props, propName, componentName) {
    if (typeof props[propName] !== "string") {
      return new Error(
        `Not valid type, string expected for ${props[propName]}`
      );
    }
  }
};

SayHello.propTypes = {
  firstName: PropTypes.string,
  lastName: PropTypes.string
};
//This implementation can be removed and react own prop type package can be used.
```

- Use `isRequired` for prop types which are required. E.g `firstName: PropTypes.string.isRequired`
- For class components, specify `propTypes` as static members of the class.
- For functional components, add `propTypes` key to the function.

## Conditional Rendering

Use ternary operators `?:` to conditionally render a component. Return `null` from `render()` method for no rendering at all.

## Re-rendering the components

React re-renders only the parts where the change is actually made.

## Styling React Components

Components can be styled with an object with keys camelCased corresponding to the CSS props.

```js
function Box({ style, ...rest }) {
  return (
    <div
      className="box box--small"
      style={{ paddingLeft: 20, ...style }}
      {...rest}
    />
  );
}

const element = (
  <div>
    <Box style={{ backgroundColor: "lightblue" }}>Small Box</Box>
  </div>
);
```

## Event Handling

The normal HTML event bindings are available with a camelCased name. For example, onClick, onBlur etc. Call a scoped function from here. The events are wrapped(proxy) by react. `event.nativeEvent` contains the original event.

## Component State

Create an initial state of the component. The `state` key in the component houses all the state variables accessible anywhere by calling `this.state`.

## Memory Leaks

Side note: `setState` function takes a callback.

Use `componentWillUnmount` to clear any timers, resources etc.

## Using class components

```js
class Counter extends React.Component {
    constructor(...args) {
        super(...args)
        this.state = {count : 0}
    }

    handleClick() {
        this.setState(({count}) => ({
                count: count + 1
        }))
    }

    render() {
        return (
            <button onClick = { this.handleClick.bind(this) } />
            {this.state.count}
        )
    }
}
```

Either use the function at `onClick` or bind the function with the object. You can also bind the function in the constructor `this.handleClick = this.handleClick.bind(this)`. Finally, public fields can also come handy. You can get rid of the constructor and use public class fields. Simply `state = {count : 0}` and bind the function there.

```js
class A extends React.Component {
  state = { count: 0 };
  handleClick = () => {
    //Code here
  };
}
```

## Using refs

```js
render() {
    return (
        <div ref = {node => (this.rootNode = node)} className = "root" />
    )
}
```

## Forms in react

```js
class NameForm extends React.Component {
    handleSubmit = (event) => {
        event.preventDefault()
        console.log(this.inputNode.value)
    }

    render() {
        return (
            <form onSubmit= {this.handleSubmit}>
                <label>
                    Name:
                    <input type="text" name="username" ref={node => (this.inputNode = node)} />
                </label>
                <button type"submit">Submit</button>
            </form>

        )
    }
}
```

For input elements like `input`, adding `value` attribute makes it a controlled component. In such state, typing in these components would not work. We need to add an `onChange` listener to update the values ourselves.

## Using keys for items in a list

```js
render() {
    return (
        <div>
            {
                App.allItems.map(item => (
                        <div key={item.id}> {item.value}</div>
                    )
                )
            }
        </div>
    )
}

---
```

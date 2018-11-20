# Redux

## The Single Immutable State

Redux uses a single immutable state for your entire application called the state tree.

## Actions

The state tree is read only.The only way to change the state tree is by dispatching an action. An action is a plain JS object with the `type` key which can't be undefined.

## The Reducer

The reducer is a pure function which takes the previous state and the action to perform and returns the next state. It keeps the references to unchanged complex objects which makes it fast. As a convention, if the state is undefined, the reducer returns the initial state. If it does not understand any of the action types, it should return the current state without modification.

## The store

The sore binds the above principles together. It has a `getState` method for the state. A `dispatch` method for the send actions to the store and a `subscribe` method for the listening to the store update events.

```js
// A simple store
 const createStore = (reducer) => {
     let state = {};
     let listeners = [];

     const getState = () => state;

     const subscribe = (listener) => {
         listeners.push(listener);
         return () => {
             listeners = listeners.filter(l => l !== listener);
         }
     }

     const dispatch(action) {
         state = reducer(state, action);
         listeners.forEach(l => l(state));
     }

     dispatch({});

     return {getState, dispatch, subscribe};

 }
```

## Array Sanity

- Avoid `push` and use `[...list, 0]` instead.
- Avoid `splice` and use `[...list.slice(0, index) ...list.slice(index+1)]`
- Avoid index mutation and use `[...list.slice(0, index) list[index]+1 ...list.slice(index + 1)]`

## Object Sanity

- Avoid mutating object fields and use `{...todo, completed: !todo.completed}` instead.

## Combining Reducers

Redux gives a utility function called `combinedReducers` which take different pure functions managing different parts of the state tree into one combined function. It takes an object with the keys corresponding to the keys of the state tree and values corresponding the functions managing that part of the state tree. For example.

```js
const { combinedReducers } = Redux;
const todo = combineReducers({
  todos: todos,
  visibilityFilter: visibilityFilter
});
```

Usually, we name the reducers after the state keys they manage. Using this convention, we can simplify the above code like this `combineReducers({todos, visibilityFilter})`.

A simple `combineReducer` can be implemented as follows.

```js
const combineReducers = reducers => {
  return (state = {}, action) => {
    return Object.keys(reducers).reduce((nextState, key) => {
      nextState[key] = reducer[key](state[key], action);
      return nextState;
    }, {});
  };
};
```

## The Provider

The provider component in the react-redux library provides a way to add context to all the components, irrespective of the depth. The context can then be accessed using `this.context` which typically contains the state.

## Containers with connect from React-Redux

A simple `mapStateToProps` function is required to update the props of the container with the changes in the store. The props may then be used to render the container or send it to the children.

Similarly, `mapDispatchToProps` function is used to dispatch actions to the store.

Use `mapStateToProps` and `mapDispatchToProps` as arguments to the `connect` method obtained from `react-redux` binding to generate the container component.

```js
//Connecting a component
const { connect } = ReactRedux;
const VisibleTodoList = connect(
  mapStateToProps,
  mapDispatchToProps
)(TodoList);
```

As a general idea, break the application into suitable presentational components, if there is too much boiler plate, passing the props and event handlers to the leaf components, consider making container components around them.

The container components will subscribe to the store themselves and update accordingly.

Sending `null` or falsy values in place of `mapStateToProps` and `mapDispatchToProps` has a default behavior of sending only `dispatch` method of the store to the container components. Therefore, the following pattern is quite common, `AddTodo = connect(null, null)(AddTodo)`.

The `props` of the container components that we generate using the `connect` method are available as the second argument of the `mapStateToProps` and `mapDispatchToProps` functions.

## Passing Store as Prop

A simple implementation to pass the store as context.

```js

class Provider extends Component {

    getChildContext() {
        return {
            store : this.props.store
        }
    }

    render() {
        return this.props.children;
    }
}

Provider.childContextTypes = {
    store : React.propTypes.object
};

const { createStore } = Redux;

ReactDOM.render(
    <Provider store = {createStore(todoApp)}>
        <TodoApp />
    </Provider>,
    document.getElementById('root')
);

//Finally in your receiving component
VisibleTodoList.contextTypes = {
    store : React.PropTypes.object
};

//Use in receiving container component
const {store} = this.context;

//Use in presentational components. Passed as the second argument, next to props.
AddTodo.contextTypes = {
    store : React.PropTypes.object
};
const AddTodo = (props, {store}) = {}

```

A similar `Provider` component is available in react-redux library.

---

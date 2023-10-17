#Actions
----
- An action is a plainJS obj that has a `type` field. Think of it as an event that describes something that happened in the app.

#Action Creator
----
- An action creator is a fn that creates and returns an action obj. We typically use these so we don't have to write the action obj by hand every time: 
```JavaScript
  const addTodo = text => {
    return {
      type: 'todos/todoAdded',
      payload: text
    }
  }
```

#Reducers
----
- A reducer is a fn that rx the current `state` and an `action` obj, decides how to update the state if necessary, and returns the new state: `(state, action ) => newState`. You can think of a reducer as an event listener which handles events based on the rx'd action (ev) type. 
- Reducers must always follow some specific fules:
  - They should only calc the new state value based on the `state` and `action` args. 
  - They are not allowed to modify the existing `state`. Instead, they must make immutable updates, by copying the existing `state` and making changes to the copied values.
  - They must not do any async logic, calc random values, or cause other 'side effects'. 

#Store
----
- The current Redux app state lives in this obj called the Store.
- The store is created by passing in a reducer, and has a method called `getState` to that returns the current state value:
```JavaScript
import {configureStore} from '@reduxjs/toolkit'
const store = configureStore({renducer: counterReducer})
console.log(store.getState())
// {value: 0}
```

#Dispatch
----
The Redux store has a method called `dispatch`. The only way to update the state is to call `store.dispatch()` and pass in an action obj.l 

[https://d33wubrfki0l68.cloudfront.net/01cc198232551a7e180f4e9e327b5ab22d9d14e7/b33f4/assets/images/reduxdataflowdiagram-49fa8c3968371d9ef6f2a1486bd40a26.gif](https://d33wubrfki0l68.cloudfront.net/01cc198232551a7e180f4e9e327b5ab22d9d14e7/b33f4/assets/images/reduxdataflowdiagram-49fa8c3968371d9ef6f2a1486bd40a26.gif)


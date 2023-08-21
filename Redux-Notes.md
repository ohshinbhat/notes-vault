Redux is a pattern and library for managing and updating application state, using events called "actions".
- The **state**, the source of truth that drives our app;
- The **actions**, the events that occur in the app based on user input, and trigger updates in the state
The `type` field should be a string that gives this action a descriptive name, like `"todos/todoAdded"`. We usually write that type string like `"domain/eventName"`, where the first part is the feature or category that this action belongs to, and the second part is the specific thing that happened.
An action object can have other fields with additional information about what happened. By convention, we put that information in a field called `payload`.
An **action creator** is a function that creates and returns an action object. We typically use these so we don't have to write the action object by hand every time:

```
const addTodo = text => {  return {    type: 'todos/todoAdded',    payload: text  }}
```

A **reducer** is a function that receives the current `state` and an `action` object, decides how to update the state if necessary, and returns the new state: `(state, action) => newState`. You can think of a reducer as an event listener which handles events based on the received action (event) type.

**The only way to update the state is to call `store.dispatch()` and pass in an action object**. The store will run its reducer function and save the new state value inside, and we can call `getState()` to retrieve the updated value. You can think of dispatching actions as "triggering an event" in the application.

![[Pasted image 20230821103624.png]]
The Redux store is created using the `configureStore` function from Redux Toolkit. `configureStore` requires that we pass in a `reducer` argument.
**A "slice" is a collection of Redux reducer logic and actions for a single feature in your app**, typically defined together in a single file.

## Redux Summary/Review

1. `store` - takes `reducer`
    * Use `combineReducers` to create a single `rootReducer`
1. `reducer`(s) - takes actions with `type` and `payload`
    * Can be split into more targeted reducers (that are then combined)
1. `constants` - "type" identifier for each `action`
    * Can live in `reducer.js` file _or_ in `constants.js`
    * You may create other constants for app domain logic
1. action creators - functions that can take (optional) parameter arguments and returns the created action with
    * `type` property that is an action `constant`,
    * and (optional) `payload` of whatever data is required
    for the store to complete the action
1. `connect` - a utility for interfacing `redux` store with `react` components
    * `mapStateToProps` - Function that will receive store state and returns 
    what props should be injected into component based on the state
    * `mapDispatchToProps` - Function that will receive the dispatch function and returns what action creating functions should be injected
    as props into the component
        1. Hand-roll your own functions, _or_
        1. Use `bindActionCreators` to wrap into dispatch functions, _or_
        1. **Pass an object literal** and `bindActionCreators` will be called on your
        behalf
    * `mergeProps` - Optional function that takes `stateProps` (from #1), `dispatchProps` (from #2), and `ownProps` (directly passed to the component
    by its parent). Return the actual props that will be injected into the component.

# Redux Cheat-Sheet

<!--First Video  -->
 ### Store (First principal)
- Whole state of the application in one application is stored in one object.
- Everything (actions, UI changes) that changes in the data is contained in an object called the state.

<!--Second Video -->
### Action (Second Principal)
- State is read only.  Changing state only happens with dispatching an action. Is a javascript object.
- Change to data/state.
- Action is representation of change of data.
- (Required) `type` which is a string.
```javascript
    type: "INCREMENT
```
- Components dispatch actions, type + text or something is sent.
- Components don't know how it happens. They just dispatch it.


<!--Third Video -->
### Pure v. Impure Functions
- Pure Functions -- No side effects.  Calculate values only from inputs.  They're predictable.
```javascript
    function square(x) {
        return x * x;
    }
    function squareAll(items) {
        return items.map(square);
    }
```
- example is pure because call to Array.prototype.map is returning a fresh array object.

- Impure -- Make calls, modifies values, makes network calls.
```javascript
    function squareItems(items) {
        for(var i = 0; i < items.length; i++) {
            items[i] = square(items[i]);
        }
    }
```
- example is impure because it is mutating it's argument.

<!--Fourth Video -->

### Reducer (Third Principal)
 - Takes Previous state of the whole application, Action as arguments and returns the next state.
```javascript
    // example
    reducer(prevState, action) {
        return nextState;
    }

    // More practical example
    function const counter = (state = 0, action) => {
        switch(action.type) {
            case 'INCREMENT':
                return state + 1;
            case 'DECREMENT':
                return state - 1;
            default:
                return state;
        }
    }
```
- This is a pure function. It returns a new object based off of the old object.
- If the dispatch type isn't defined it'll return the initial state that was passed to the reducer.

<!--Fifth Video-->
### Testing
-- Uses expect library to test.

<!--Sixth Video -->




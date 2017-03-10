# React.js Cheat Sheet
### Source of all truth [React Docs](https://facebook.github.io/react/docs/hello-world.html)

### React Elements:
- Are immutable: Once you've created an element, that's it.
    - You can't change it's children or attributes. You need to create a new one.

## Components
- Independent reusable pieces of UI. Takes in props (properties) and returns React Elements.
- If you use a component more than once you should make it an actual component.
- Building your own tag, like a custom directive or web component.

- ### Functional (Stateless Components):
    - example: 
    ```javascript
        <!--Defines a component that takes props as a parameter -->
        function Welcome(props) {
            // Returning React Element.
        return <h1>Hello, {props.name}</h1>;
        }
        <!-- Render the component with props-->
        ReactDOM.render(<Welcome name={"Benjamin} />)

        <!--Are both the same -->

        const welcome = (props) => {
            return <h1>Hello, {props.name}</h1>;
        }
    ```
- Only when you need the render() function.


- ### Stateful (Components): 
    - When you need life cycle components and manipulate state.

- ### Props
    - All React components must act like pure functions with respect to their props.  Props are immutable.  Don't change them.  Pass them around.
    
### Props (Properties)
- Supplies data to Component.
- Props are given in the above example. Name is the prop, the value is "Benjamin". Then, you can out the prop value within the component.

### Routing

- React Router (v4)
    - Show and hide components.  Everything is in the Router Component.
    - (Match and Miss, Browser Router) Components.

    ```javascript
        const Root = () => {
            return (
                <BrowserRouter>
                    <div>
                        <Match exactly pattern="/" component={Welcome}>
                        <Match exactly pattern="/store/:id" component={App}>
                        <Miss component={NotFound}/>
                    </div>
                </BrowserRouter>
            )
        }
    ```

#### defaultValue
- Puts default value in input field.

### Events and passing methods
- Look in the (synthetic events)[https://facebook.github.io/react/docs/events.html] documentation.

```javascript


```

### Binding Method to Classes
- Need to set context of this method on the class.

#### ref (reference input)
- Function refs moving forward.
```javascript
    ref={((input) => this.instance = input)}

```



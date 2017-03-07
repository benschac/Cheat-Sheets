# React.js Cheat Sheet
### Source of all truth [React Docs](https://facebook.github.io/react/docs/hello-world.html)

### React Elements:
- Are immutable: Once you've created an element, that's it.
    - You can't change it's children or attributes. You need to create a new one.

## Components
- Independent reusable pieces of UI. Takes in props (properties) and returns React Elements.
- If you use a component more than once you should make it an actual component.

- ### Functional (Components):
    - example: 
    ```javascript
        <!--Defines a component that takes props as a parameter -->
        function Welcome(props) {
            // Returning React Element.
        return <h1>Hello, {props.name}</h1>;
        }
        <!-- Render the component with props-->
        ReactDOM.render(<Welcome name={"Benjamin} />)
    ```

- ### Stateful (Components): 

- ### Props
    - All React components must act like pure functions with respect to their props.  Props are immutable.  Don't change them.  Pass them around.
    
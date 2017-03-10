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
        return <h1>Hello, {props.}</h1>;
        }
        <!-- Render the component with props-->
        ReactDOM.render(<Welcome ={"Benjamin} />)

        <!--Are both the same -->

        const welcome = (props) => {
            return <h1>Hello, {props.}</h1>;
        }
    ```
- Only when you need the render() function.


- ### Stateful (Components): 
    - When you need life cycle components and manipulate state.

- ### Props
    - All React components must act like pure functions with respect to their props.  Props are immutable.  Don't change them.  Pass them around.
    
### Props (Properties) 2/3 Data Values
- Supplies data to Component.
- Props are given in the above example.  is the prop, the value is "Benjamin". Then, you can out the prop value within the component.

### Routing

- [React Router](https://github.com/ReactTraining/react-router/tree/master/docs) (v4)
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
    - Imperative and Declarative API
    - You can give it a string.
    - You can give it a function that it can run.

    #### Context 3/3 Data Type: Is a special third data type that can be passed from the router.
    ```javascript

        Component.contextTypes = {
            router: React.propTypes.object
        }
        <!--Will be able to pass transition functions from router into Component-->
        class Component extends Component {
            getItem() {
                const uniqueId = this.instance.value
                <!--This will change the URL -->
                this.context.router.transitionTo(`store/${uniqueId}`);
            }
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
- This will grab the value inside of the input value and set it to an instance on the class.
```javascript
    <input ref={((input) => this.instance = input)} />
    
```

### State (1 /3 Data Values)
- Is a representation of all data in the application.
- It's one object that's holding all of the data.  That's state.
- If you want to change something it's changed in the state.

- Initial State:
```javascript
    this.state = {
        // put your values in here.
        // just a plain object here, nothing special to see here.
    }
```

- SetState:
```javascript
    <!--Copy Your state -->
    // all items from object, and puts it into a new one.
    addPlayer(player) {
        const player = {...this.state.players};
        const timeStamp = new Date.now();
        player[`player-${timeStamp}] = player 
        this.setState({
            player: player
        })
    }
    
```

- Example: setState from input form
```javascript

    class playerForm extends Component {
        createPlayer(event) {
            event.preventDefault();
            const player = {
                name : this.name .value,
                shot : this.shot.value,
                team : this.team.value,
                age : this.age.value,
                number : this.number.value,
            }

            this.props.addPlayer(player)
        }

        render() {
            return (
                <!--Saves onto the instance of the class object -->
                <form onSubmit={(e) => this.createPlayer(e)}>
                    <input ref={(input) => this. = input} />
                    <input ref={(input) => this.shot = input} />
                    <input ref={(input) => this.team = input} />
                    <input ref={(input) => this.age = input} />
                    <input ref={(input) => this.number = input} />
                </form>
            )
        }
    }
```



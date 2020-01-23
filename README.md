# Redux TodoMVC Example


## Popular State Management Solutions

- React

- Redux

- MobX

- Apollo and GraphQL

### Redux

- Most popular, features one-way data flow and immutability. 

### MobX

- Most likely to cater to those with a background in OOP, uses the observer pattern which allows the system to build a dependency 
tree among different parts of state.

### React

- Has it's own state management (useState, useContext)

## Why do we need state management? 

- Required when apps extend beyond basic functionality

- Manages business logic

### Presentation Logic

- How components appear on a page, agnostic towards the applications purpose. 

### Business Logic

- Logic that is associated with handling, manipulating, and storing business objects. 

- User account behavior, data fetching, application specific. 

### Considerations

- Businesss logic and controlling session management, re-rendering. State management allows for opinionated decisions based on what your busines logic requires. 


- When you don't use state management you may run into having to re-render entire components or application in order to update state. 

## Separating component and application state (in terms)

- React state (component state) Redux state(application state)

## Keeping business and presentation logic separate

- Pros: consolidated code

- Cons: Lack of flexibility to change a UI library. 

- There will alway be trade-offs, no matter what you decide. 

## Data fetching (API Calls)

- Introducing API calls is a common way to add complexity to an application 
- Built in React methods are usually sufficient for data fetching. 

### Remember react lifecycles

- Mounting (initiallization) -> (componentWillMount) -> (render) -> (compnentDidMount)
- Updating (componentWillReceiveProps) -> (shouldComponentUpdate) [T/F] -> (render) -> (componentDidUpdate)
- Unmounting (componentWillUnmount)

### Remember what your data looks like (JSON)

- Use what you need. 

### On prop drilling

- Your component should typically only contain the data it needs and nothing more, it serves as an anti-pattern elsewise.

### Using Context 

- Provider level ( I have the information )

- Consumer level (  1 component with specific need ) (  1 component with specific need ) (  1 component with specific need )

## Redux -- Flux Wars

### Two-Way data binding

- Template -(compile)--> View -(changes to view updates Model) --> Model -(changes to Model updates View)--> View

### One-Way data binding (always from view to model)

Flux:
- Action --> Dispatcher --> Store --> View
                                        |
                ^^^-------(Action)-------

- CONS? Model and view may not always be in sync :(

- Differences from Redux? Not a library. Multiple stores. Viewed as a PATTERN, it became too much to handle. 


### Enter Redux

- Immutable store: any time it's changed, a new copy is generated. 
- Stores and actions are pure functions, easier to test and reason about. 
- One store, one source of truth. 
- When weighing the benefit, or whether you need Redux, consider: 
- increased boiler plate, decreased access to state on your FE. 
- Use the right tool for the job!!!



State-(defines)->UI-(triggers)->Actions(sent to)->Reducer-(updates)->Store-(contains)->State === Predictable!


- Immutability is one of Redux's greatest strengths... meaning it does not modify a variable after it's created. 
- In redux, it means not mutating state directly. We would return a new state with the modified property
- you'll always need to extend an object exampleArray = [...exampleArray, 4] (applies to React State, as well)

- Overhead? A new state is created every time we call an action, which can be redundent and costly. 
- Shallow equality checking. 
- Immutable.JS with Redux for increased performance (example library) ...But useEffect...

- Philosophies: 
  1 Everything lives in redux (Store contains presentation and business logic)
  2 State should live as close to your components as possible (Presentational logic = React components Business logic = Redux store) 
  
- Seperating business and presentational logic makes it easier to swap out the presentational layer. 
- How data behaves vs how it appears on the screen. 



### Redux Middleware

- A structure to call third-party endpoints that happen after you dispatch an action and before the action reaches the reducer. 
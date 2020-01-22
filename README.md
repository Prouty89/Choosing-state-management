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
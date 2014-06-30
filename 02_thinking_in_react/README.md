# Thinking in React: Notes

http://facebook.github.io/react/docs/thinking-in-react.html

## Step 1: break the UI into a component hierarchy

- Use the *single responsibility principle* to decide where to break up
  components.
- Hopefully your underlying data structure will map nicely onto the components
  because they have the same information architecture.

## Step 2: Build a static version in React

- Don't use state for the static version (state is for things which change in
  time - not needed for static site)
- **one-way data flow** means data flows from the parent model downwards.


## Step 3: Identify minimal complete representation of UI state

- aim is to find out minimal mutable state & compute everything else on demand
- want to **minimize** state held in components
- anything that can be computed from other state is not state
- anything that doesn't change over time probably isn't state
- anything that is passed in from parent as props probably isn't state

## Step 4: Identify where state should live

- we know *what* the state is - but which component can modify it?
- one-way flow again: state needs to live above (parentally) all components
  which need access to that bit of state
- use `getInitialState()` method to define initial state
- components must only update their own state

## Step 5: Add inverse data flow

- there's an optional addon called `ReactLink` for two-way binding
- parent components give callbacks to child components which can be fired when
  parent state needs to change

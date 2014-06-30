# Thinking in React Video Notes

http://tagtree.tv/thinking-in-react

- 2 ways of building React apps: native JS or JSX
- normally you'd precompile React stuff
- needs a weird little comment to work
- bottom up approach makes most sense to author
- recommended approach is to make a prototype HTML page first
- JSX gives up the ability to write "html" inside the render function - allows
  copy and paste from prototype HTML
- renderComponent replaces the content of the given DOM element
- you need to set a unique key when you've an array of components
- stuff that doesn't look right is because of `class` vs `className` - `class`
  is protected word in Javascript
- "inverse data flow" means low down components bubble values up to the owner
  of the state, when then trickle it back down via props (properties)
- `SearchBar` bar HTML `value` field gets wired up to `{this.props.filterText}`
- `filterText` is passed down into `SearchBar` in the render function of
  parent from its state: `<SearchBar filterText={this.state.filterText} />`
- hook up change event on `SearchBar` to fire a callback into parent
- parent callback then uses `setState`
- something about ESX fat arrows and scope wrangling to give access to `props`: `var props = this.props`
- 

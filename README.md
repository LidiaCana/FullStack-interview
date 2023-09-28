# FullStack-interview

## React midle senior

1. What is prop drilling
Prop Drilling is the process by which data is passed from one component to deeply nested components. This becomes a problem as other components will contain data that they don’t need.

2. What is HOC

4. What is React.Lazy
5. What is React.memo
6. What is React.fragment
Avoid Adding Extra Nodes to the DOM React Fragments do not produce any extra elements in the DOM Fragment’s child components will be rendered without any wrapping DOM node.
```
function App() {
  return (
    <React.Fragment>
      <h1>Best App</h1>
      <p>Easy as pie!</p>
    </React.Fragment>
  );
}
```
or
```
function App() {
  return (
    <>
      <h1>Best App</h1>
      <p>Easy as pie!</p>
    </>
  );
}
```
7. What is re-reselect

# [Flow: A Static Type Checker for JavaScript](https://flow.org/)

## Type for data-qa attributes

Example:

```jsx
type PropsT = {|
  value: ?string,
  onChange: (value: string) => void,
  'data-qa'?: string,
|}
```

## Concept of ApiPropsT and PropsT

An `ApiPropsT` represents props that are being passed to the React component. A `PropsT` represents props that are being created **inside** the React component.

`PropsT` usually contains spread of `ApiPropsT`.

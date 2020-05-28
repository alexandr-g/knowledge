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

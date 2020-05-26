# [Jest](https://jestjs.io/)

## Links

- [Mocking Node modules](https://jestjs.io/docs/en/manual-mocks#mocking-node-modules)
- [mockFn.mockClear](https://jestjs.io/docs/en/mock-function-api.html#mockfnmockclear)
- [mockFn.mockReset](https://jestjs.io/docs/en/mock-function-api.html#mockfnmockreset)
- [expect.anything()](https://jestjs.io/docs/en/expect#expectanything)

### Asynchronous or time-based events (timers)

```js
describe('do some crazy stuff with timers.', () => {
  beforeEach(() => {
    // declare the intent of using timers
    jest.useFakeTimers()
  })

 it('should .', () => {
    // mock if needed
    const callback = jest.fn()

    // mount component

    // follow by expect before timers

    // execute timers
    jest.runAllTimers()

    // expect something after timers have been executed
    expect(callback).toHaveBeenCalledTimes(1)
  })
```

### Verify that function was called with multiple arguments

[`.toHaveBeenCalledWith(arg1, arg2, ...)`](https://jestjs.io/docs/en/expect#tohavebeencalledwitharg1-arg2-)

Also available under the alias: `.toBeCalledWith()`

### Verify that the same function was called multiple times with different arguments

```javascript
it('should be able to change access rights.', () => {
  expect(onUpdateAccess).not.toBeCalled()

  const newAccess = {
    ...report.access,
    view: {
      type: 'user',
      id: '3',
    },
  }

  component.find(Rights).prop('onChange')(newAccess)

  expect(onUpdateAccess).toBeCalledTimes(2)
  expect(onUpdateAccess).toBeCalledWith('edit', newAccess.edit)
  expect(onUpdateAccess).toBeCalledWith('view', newAccess.view)
})
```

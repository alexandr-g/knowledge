# [Jest](https://jestjs.io/)

## Links

- [Mocking Node modules](https://jestjs.io/docs/en/manual-mocks#mocking-node-modules)
- [mockFn.mockClear](https://jestjs.io/docs/en/mock-function-api.html#mockfnmockclear)
- [mockFn.mockReset](https://jestjs.io/docs/en/mock-function-api.html#mockfnmockreset)

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

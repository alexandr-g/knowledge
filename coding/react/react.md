# React

- [Render Props pattern](https://reactjs.org/docs/render-props.html)

## Hooks

`useRef()` - useRef returns **a mutable ref object** whose `.current` property is initialized to the passed argument (initialValue). The returned object will persist for the full lifetime of the component.

`useRef()` hook example to get an email and password from the login form.

```javascript
import React, { useRef } from 'react'
import { Link } from 'react-router-dom'

const Authentication = () => {
  const emailRef = useRef(null)
  const passwordRef = useRef(null)

  const handleSubmit = event => {
    event.preventDefault()

    console.log('--->', emailRef.current.value, passwordRef.current.value)
  }

  return (
    <div className='auth-page'>
      <div className='container page'>
        <div className='row'>
          <div className='col-md-6 offset-md-3 col-xs-12'>
            <h1 className='text-xs-center'>Sign in</h1>
            <p className='text-xs-center'>
              <Link to='/register'>Need an account?</Link>
            </p>
            <form onSubmit={handleSubmit}>
              <fieldset>
                <fieldset className='form-group'>
                  <input
                    type='email'
                    className='form-control form-control-lg'
                    placeholder='Email'
                    ref={emailRef}
                  />
                  <input
                    type='password'
                    className='form-control form-control-lg'
                    placeholder='Password'
                    ref={passwordRef}
                  />
                </fieldset>
                <button
                  className='btn btn-lg btn-primary pull-xs-right'
                  type='submit'
                >
                  Sign in
                </button>
              </fieldset>
            </form>
          </div>
        </div>
      </div>
    </div>
  )
}

export default Authentication
```

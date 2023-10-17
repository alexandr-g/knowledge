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
    <div className="auth-page">
      <div className="container page">
        <div className="row">
          <div className="col-md-6 offset-md-3 col-xs-12">
            <h1 className="text-xs-center">Sign in</h1>
            <p className="text-xs-center">
              <Link to="/register">Need an account?</Link>
            </p>
            <form onSubmit={handleSubmit}>
              <fieldset>
                <fieldset className="form-group">
                  <input
                    type="email"
                    className="form-control form-control-lg"
                    placeholder="Email"
                    ref={emailRef}
                  />
                  <input
                    type="password"
                    className="form-control form-control-lg"
                    placeholder="Password"
                    ref={passwordRef}
                  />
                </fieldset>
                <button
                  className="btn btn-lg btn-primary pull-xs-right"
                  type="submit"
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

## Create React App

### [Building a custom template](https://create-react-app.dev/docs/custom-templates/)

### Use Create React App local template from your template root folder

```bash
yarn create react-app demo --template file:.
```

### Create React App local template folder structure and **gitignore**

```jsx
README.md
template.json
package.json
template / README.md
gitignore // gitignore inside template folder should be without "." in front
public / index.html
src / index.js
```

## How to create custom Create React App (CRA) templates

I created a step by step guide on how to create your own templates. Check it

[View on Medium](https://medium.com/@alexgrischuk/how-to-create-custom-create-react-app-cra-templates-73a5196edeb)

[View blog post](https://grischuk.de/posts/how-to-create-custom-create-react-app-templates)

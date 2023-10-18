# Yarn

## Install a package/dev dependency for the specific workspace (monorepo)

```bash
yarn workspace package-name add react --dev
```

## Remove a package from a specific workspace (monorepo)

```bash
yarn workspace workspace-name remove package-name
```

Reference [yarn workspace](https://yarnpkg.com/lang/en/docs/cli/workspace/)

## Move a module from devDependencies to dependencies

```bash
yarn remove <module_name> --dev && yarn add <module_name>
```

## Move a module from dependencies to devDependencies

```bash
yarn remove <module_name> && yarn add <module_name> --dev
```

## How to test a package locally

### Without publishing it

To test changes to a local package without publishing it, you can use `npm link` or `yarn link` to create a symlink between your project and the local package. Here are the steps:

In the directory of the local package, run `npm link` or `yarn link` to create a symlink to the package in the global node_modules directory.

In the directory of your project, run `npm link <package-name>` or `yarn link <package-name>` to link the package to your project. Replace `<package-name>` with the name of your local package.

Make your changes to the local package code.

Run `npm run build` or `yarn build` in the local package directory to build the package.

Run your project and test the changes.

### Without publishing it and without using `yarn link` (using `file:` protocol and `package.json`)

You can reference a local package directly in the `package.json` file of your project using the file: protocol. Here's how you can do this:

In the directory of the local package, run `npm pack` or `yarn pack` to create a tarball of the package.

In the directory of your project, open the `package.json` file and add a dependency entry for the local package using the `file:` protocol. For example:

```json
{
  "dependencies": {
    "my-local-package": "file:/path/to/my-local-package-1.0.0.tgz"
  }
}
```

Replace `/path/to/my-local-package-1.0.0.tgz` with the path to the tarball created in step 1.

Run `npm install` or `yarn install` in the project directory to install the local package.

Make your changes to the local package code.

Run `npm run build` or `yarn build` in the local package directory to build the package.

Run your project and test the changes.

With this setup, *any changes you make to the local package will be reflected in your project immediately*, without the need to publish a new version of the package.

Note that referencing a local package using the `file:` protocol can sometimes cause issues with dependencies and versioning, so it's important to test your changes thoroughly before publishing a new version of the package. Additionally, be aware that referencing a local package using the `file:` protocol can sometimes cause issues with peer dependencies, so you may need to manually install any peer dependencies of the local package in your project.

#### file: protocol with relative path

Suppose your local package is located in a directory called my-local-package, which is one directory up from your project directory. You can reference the local package in your project's package.json file like this:

```json
{
  "dependencies": {
    "my-local-package": "file:../my-local-package"
  }
}
```

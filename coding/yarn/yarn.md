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

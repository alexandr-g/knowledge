# NPM

## Testing local package

#### For Example:

```bash
cd ~/projects/node-redis

npm link

cd ~/projects/node-bloggy

npm link redis # links to your local redis
```

#### To reinstall from your package.json:

```bash
npm unlink redis
npm install

sudo npm rm --global foo # This will uninstall the package.
```

#### To check whether a package is installed, the `npm ls` command can be used:

```bash
npm ls --global foo
```

## NPM package

### Increase patch version

```sh
npm version patch
```

### Publish

```sh
npm publish
```

## Global installation

### List all the globally installed packages

```sh
npm list -g --depth 0
```

### Uninstall globally installed package

```sh
npm -g uninstall <module_name>
```

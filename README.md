### TS CONFIGS

- Sucrase for transpiling and building
- Nodemon for hot-reload
- Eslint to enforce code style

## Sucrase and Nodemon

install sucrase and nodemon on devdeps :

```
yarn add -D sucrase nodmeon
```

Create a ndoemon json file to watch the ".ts" files in the "src" folder
and execute a command on change.

```json
{
  "watch": ["src"],
  "ext": "ts",
  "execMap": {
    "ts": "sucrase-node src/server.ts"
  }
}
```

## Eslint

install both @typescript-eslint/parser and @typescript-eslint/eslint-plugin:

```
yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

now you can run

```
yarn eslint --init
```

As this is a backend focused repo I'll choose to

1. enforce code style
2. use with node js
3. javascript modules(import/export)
4. no frontend framework
5. I'll use standardJS style guide
6. config file in js

After that you can delete the package-lock.json and run yarn again to catch up previous installings.

### Boosting eslint configuration

time to add our installed typescript parser. Add this line in your .eslintrc.js file:

```
parser: '@typescript-eslint/parser',
```

Add our installed plugin:

```
plugins: ["@typescript-eslint"],
```

Our extends array becomes like this:

```
extends: ["plugin:@typescript-eslint/recommended", "standard"],
```

## Prettier configuration

Prettier helps us fixing common errors and enforce patterns with eslint, so lets install it:

```
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
```

Now we can add the "prettier/@typescript-eslint" plugin to our eslint config file:

```js
 extends: [
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint",
    "standard"
  ],
```

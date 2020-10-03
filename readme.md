## Create mobile structure
- If react-native-cli intalled globally, uninstall it:
- > npm uninstall -g react-native-cli
- > yarn global remove react-native-cli
- Then install it locally:
- > yarn add react-native-cli
- Then install the boilerplate:
- > npx react-native init appgobarber --template react-native-template-typescript


## Editor config

```
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
```

## Eslint config to React Native

- > yarn add eslint -D
- > yarn eslint --init
  - To check syntax, find problems and enforce code style
  - Javascript modules (import/export)
  - React
  - Yes (to typescript)
  - Desmarcar (Browser e Node)
  - Use a popular style guide
  - Airbnb
  - JSON
  - No (to npm)

```bash
yarn add eslint-plugin-react@^7.19.0 @typescript-eslint/eslint-plugin@latest eslint-config-airbnb@latest eslint-plugin-import@^2.20.1 eslint-plugin-jsx-a11y@^6.2.3 eslint-plugin-react-hooks@^2.5.0 @typescript-eslint/parser@latest -D
```

- config .eslintignore

```
**/*.js
node_modules
build
```

- config .eslintc.json

```json
{
  "env": {
    "es6": true
  },
  "extends": [
    "plugin:react/recommended",
    "airbnb",
    "plugin:@typescript-eslint/recommended"
  ],
  "globals": {
    "Atomics": "readonly",
    "SharedArrayBuffer": "readonly",
    "__DEV__": "readonly"
  },
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": 2018,
    "sourceType": "module"
  },
  "plugins": ["react", "react-hooks", "@typescript-eslint"],
  "rules": {
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "react/jsx-filename-extension": [1, {"extensions": [".tsx"]}],
    "import/prefer-default-export": "off",
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "ts": "never",
        "tsx": "never"
      }
    ]
  },
  "settings": {
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

- > yarn add eslint-import-resolver-typescript -D

## Prettier
- Remova plugin do prettier se tiver instalado
- > yarn add prettier eslint-config-prettier eslint-plugin-prettier -D
- config eslintc.json **adicionando**
```json
{
  "extends": [
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
  ],
  "plugins": [
    "prettier"
  ],
  "rules": {
		"prettier/prettier": "error"
  },
}
```
- config prettier.config.js
```js
module.exports = {
  singleQuote: true,
  trailingComma: 'all',
  arrowParens: 'avoid',
}
```

## yarn commands
- > yarn start
- > yarn android
- > yarn cache clean

## Clean androind cache
- > cd android && ./gradlew cleanBuildCache

## ADB commands
- > adb kill-server
- > adb start-server
- > adb usb
- > adb reverse tcp:3333 tcp:3333
- > adb devices

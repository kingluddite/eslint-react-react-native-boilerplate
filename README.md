# Eslint
## Browser React

## Linting in VS Code for react
* Add Eslint to VS code
* Add these dependencies

`$ npm i -D eslint eslint-config-airbnb eslint-plugin-react`

* After installing them you will get an error from VS code and the reason for the error is you are missing an `.eslintrc` file
* Create this file using

`$ eslint --init`

* If you get an error then install eslint globally

`$ npm i -g eslint`

## Answer these questions like this:
* How do you want to configure ESLint? Use popular style guide, Airbnb
* Do you use React? Yes
* What format? Javascript
* Do yo want to upgrade: yes

**note** You should see it did this:

* created `.eslintrc`

```
module.exports = {
    "extends": "airbnb"
};
```

* Swap that info with this:

```
module.exports = {
  "parser": "babel-eslint",
  "env": {
      "browser": true,
      "es6": true
  },
  "settings": {
        "ecmascript": 6,
        "jsx": true
  },
  "parserOptions": {
      "ecmaVersion": 2017,
      "ecmaFeatures": {
          "experimentalObjectRestSpread": true,
          "experimentalDecorators": true,
          "jsx": true
      },
      "sourceType": "module"
  },
  "plugins": [
      "react",
  ],
  "extends": "airbnb",
  "rules": {
    "react/jsx-filename-extension": 0,
    "function-paren-newline": 0,
    "jsx-a11y/anchor-is-valid": [ "error", { "components": [ "Link" ], "specialLink": [ "to" ] } ]
  }
};
```

## vs code settings
* eslint - set eslint.autoFixOnSave: true
* f8 to show errors

## turn off eslint rules you don't want
* use f8 to find rule name
* open `.eslintrc.js` file and add rules

```
// MORE CODE
 rules: {
    "react/jsx-filename-extension": 0,
    "function-paren-newline": 0
  }
};
```

## disable for just one line
`this.setState({ // eslint-disable-line`

* or be specific with what you want to turn off

`this.setState({ // eslint-disable-line react/no-did/mount-set-state`

* turn off rule for entire file

`/* eslint-disable-line react/no-did-mount-set-state: 0 */`

## React Native Eslint
`$ npm install eslint-plugin-react-native`

### Config
```
* Add plugins section and specify ESLint-plugin-React (optional) and ESLint-plugin-react-native as a plugin

{
  "plugins": [
    "react",
    "react-native"
  ]
}
```

* If it is not already the case you must also configure ESLint to support JSX

```
{
  "ecmaFeatures": {
    "jsx": true
  }
}
```

* In order to whitelist all browser-like globals, add react-native/react-native to your config

```
{
  "env": {
    "react-native/react-native": true
  }
}
```

* Finally, enable all of the rules that you would like to use

```
{
  "rules": {
    "react-native/no-unused-styles": 2,
    "react-native/split-platform-components": 2,
    "react-native/no-inline-styles": 2,
    "react-native/no-color-literals": 2,
  }
}
```

* docs - https://www.npmjs.com/package/eslint-plugin-react-native

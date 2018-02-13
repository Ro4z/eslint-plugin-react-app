[![npm version](https://badge.fury.io/js/eslint-plugin-react-app.svg)](https://badge.fury.io/js/eslint-plugin-react-app)
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier) 

# eslint-plugin-react-app
This plugin exposes the ESLint configuration used by Create React App without the need of declaring all its dependencies.  
Use it if you need a simple and tested ESLint configuration without the need of installing a bunch of dependecies.  
It also works in React Native out of the box.  

## Setup
1. Install it using npm: `npm install --development eslint eslint-plugin-react-app`.
2. Extend `plugin:react-app/recommended` in your `.eslintrc`.  

Example `.eslintrc`:
```json
{
  "extends": [
    "plugin:react-app/recommended"
  ]
}
``` 

## Configuring the rules
You can configure the rules like every other plugin.
Just keep in mind that if you want to change a rule of an included plugin (for example of `eslint-plugin-react`) you must prefix the rule with `react-app/` (for preventing namespace collisions).  
For example:
```json
{
  "extends": [
    "plugin:react-app/recommended"
  ],
  "rules": {
    "react-app/react/react-in-jsx-scope": ["warn"]
  }
}
```

## Included plugins  
The currently included create-react-app plugins are the following:
- [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import)
- [eslint-plugin-flowtype](https://github.com/gajus/eslint-plugin-flowtype)
- [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y)
- [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)

## Known issues
Until [this PR](https://github.com/facebook/create-react-app/commit/bf02edbef2a20ff8af66b396d7ee6ae7901c45a0#diff-99286e999408ee6352bf548c6f8cb9fc) is released on `eslint-config-react-app` you'll get an eslint warning on a missing rule definition (`react-app/jsx-a11y/href-no-hash`).  
You can momentarily silence it by turning off the following eslint rule: 
```
{
  "extends": ["plugin:react-app/recommended"],
  "rules": {
    "react-app/jsx-a11y/href-no-hash": "off"
  }
}
```

## Acknowledgements  
Thanks to [fson](https://github.com/fson) and its [Create React App pull request](https://github.com/facebookincubator/create-react-app/pull/993) for the initial idea of this plugin.  
And obviously thanks to [gaeron](https://github.com/gaearon) and everyone who contributed to Create React App.  

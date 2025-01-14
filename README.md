# eslint-plugin-escompat

This plugin will report eslint errors for code which - if left untranspiled - will not work in some browsers.

This is useful if you indent to ship code without first using a transpiler, such as [Babel](https://babeljs.io).

This _wont_ lint for features that can be polyfilled. For that you can use [eslint-plugin-compat][epc].

## Installation

```bash
npm install --save-dev eslint-plugin-escompat
```

Add `"escompat"` to `.eslintrc` `"plugins"` section, add `"browser": true` to `"env"`, then configure the individual `"escompat/*"` rules.

Alternatively, you can use the `recommended` configuration which will do this for you, with the `"escompat/*"` rules reporting errors (as in the snippet above).
```js
// .eslintrc
{
  "extends": ["plugin:escompat/recommended"]
}
```

## Targeting Browsers

`eslint-plugin-escompat` uses the `browserslist` configuration in `package.json`

If you have a browserlist, is is safe to enable all of these rules - as any
that do not coincide with your chosen browsers will be turned off
automatically.

See [browserslist/browserslist](https://github.com/browserslist/browserslist) for configuration. Here's some examples:

```js
// Simple configuration (package.json)
{
  // ...
  "browserslist": ["last 1 versions", "not ie <= 8"],
}
```

```js
// Use development and production configurations (package.json)
{
  // ...
  "browserslist": {
    "development": ["last 2 versions"],
    "production": ["last 4 versions"]
  }
}
```

:bulb: You can also define browsers in a [separate browserslist file](https://github.com/browserslist/browserslist#config-file)

## Rules

 - [no-async-generator](./docs/no-async-generator.md)
 - [no-async-iteration](./docs/no-async-iteration.md)
 - [no-edge-destructure-bug](./docs/no-edge-destructure-bug.md)
 - [no-exponentiation-operator](./docs/no-exponentiation-operator.md)
 - [no-object-rest-spread](./docs/no-object-rest-spread.md)
 - [no-regexp-s-flag](./docs/no-regexp-s-flag.md)


## Inspiration
This project was largely inspired by the great [eslint-plugin-compat][epc] library.

[epc]: https://github.com/amilajack/eslint-plugin-compat

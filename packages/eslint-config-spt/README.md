# eslint-config-spt

A module to contain the Schibsted JavaScript linting rules for [ESLint](http://eslint.org/).

## How to use

```bash
npm install --save-dev eslint-config-spt
```

Then add the `extends` option to your `.eslintrc`:

```json
{
    "extends": "spt"
}
```

You can override specific settings by specifying them as normal. See <http://eslint.org/docs/developer-guide/shareable-configs> for more details.

### Prettier
Linting usually happens in to places.

1. In the editor.
1. In build tools.

By default this config uses Prettier in relaxed mode.  This means that errors will not show for rules that are covered by running `prettier --write`.  This allows people to code in their own style.  

However, it means that build tools, by default, also don't include the errors.  You may want errors to show in your build tools so you will need to specify the `prettier-strict` config as appropriate.  e.g. using the cli add `--config ./packages/eslint-config-spt/prettier-strict.js`.

If you would like code editors to show the errors as well, simply add `prettier-strict` to the `extends` config.

```json
{
    "extends": "spt",
    "extends": "spt/prettier-strict"
}
```

### ES6 Modules
If you use ES6 modules, install `eslint-config-spt-modules` as well.

### React
If you use React, install `eslint-config-spt-react` as well.

# eslint-config-spt

A module to contain the SPT JavaScript linting rules for [ESLint](http://eslint.org/).

## Contributing

If you want to contribute, [read more here](CONTRIBUTING.md).

## How to use

There are 4 modules:

1. `eslint-config-spt`, which is the base and standalone
1. `eslint-config-spt-modules` for inclusion with ES6 module files
1. `eslint-config-spt-node` for inclusion with Node files.
1. `eslint-config-spt-react` for inclusion with Node files, and requires `eslint-plugin-react`

The base package should be included in your root ``.eslintrc.*`.  

```bash
npm install --save-dev eslint-config-spt
```

Then add the `extends` option to your `.eslintrc`:

```json
{
    "extends": "spt",
    "root": true
}
```

The additional packages should be included as `extends` in directories containing
the relevant source type files.

## Intent

The intent of these packages is to provide a common set of rules for coding within
the Schibsted SPT codebases.  It is made up from a number of different packages
with predefined settings.  This will make transitioning between projects a
smoother experience.

### Why not just AirBnB?

While AirBnB is a popular configuration, there are a lot of valuable rules that
are not included in it.  Instead of having every project need to source these
additional rules, the `eslint-config-spt-*` packages provide these for you.

AirBnB is one of the included configurations in these packages.

## Prettier

These packages make use of [Prettier](https://github.com/prettier/prettier).  See
the README.md in `eslint-config-spt` for more details.

## Testing

We use Yarn for installation.
It is recommended to install Yarn using the native installation method for your environment.
See https://yarnpkg.com/en/docs/install
So don't do a `npm i -g yarn`. Use `brew update && brew install yarn` on mac
or see [yarn installation guide](https://yarnpkg.com/en/docs/install) for more info.
*For travis, we rely on [the existence of `yarn.lock` in the root]
(https://blog.travis-ci.com/2016-11-21-travis-ci-now-supports-yarn) to do the heavy work.*
Then simply run `npm t` from the root to test all packages in `packages` dir.

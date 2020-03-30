<h1 align="center">
  start
</h1>

<h3 align="center">
Base project template to help with a running start.<br/>
TypeScript, Prettier, ESLint, Jest (and TS-Jest)
</h3>

<p align="center">
  <a href="https://github.com/pqt/start/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Released under the MIT license." />
  </a>
  <a href="https://github.com/pqt/start/actions?workflow=status">
    <img src="https://github.com/pqt/start/workflows/status/badge.svg" alt="Current Github Action build status." />
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=pqtdev">
    <img src="https://img.shields.io/twitter/follow/pqtdev.svg?label=Follow%20@pqtdev" alt="Follow @pqtdev" />
  </a>
</p>

## Usage

Generate your own project by using this template. It will generate you a brand new project with this folder structure!

#### TypeScript

It transpiles any `.ts` and `.tsx` files in the `src` folder and builds them into a new `build` folder. [`rimraf`](https://www.npmjs.com/package/rimraf) is used to ensure the contents of the build folder are totally wiped out on each build.

#### Prettier

`npm run format` will trigger [`prettier`](https://www.npmjs.com/package/prettier) on all `.ts` files inside of the `src` folder, this includes files inside of the `__tests__` folder. There's also extra care taken to ensure the ESLint and Prettier configurations play nicely with each other.

As you add deeper folder nesting into the `src` folder, you will want to adjust your formatting scripts.

```json
"format": "prettier ./{src,src/__tests__}/{**,**/**}/*.ts --write",
"format:check": "prettier ./{src,src/__tests__}/{**,**/**}/*.ts --check",
```

#### ESLint

`npm run lint` will trigger [`eslint`](https://www.npmjs.com/package/eslint) on all `.ts` files inside of the `src` folder, this includes files inside of the `__tests__` folder. There's also extra care taken to ensure the ESLint and Prettier configurations play nicely with each other.

#### Jest

`npm run lint` will trigger [`jest`](https://www.npmjs.com/package/jest) on all the `.test.ts` files found in the `src/__tests__` folder. There's an example provided. It transforms the contents using `ts-jest` so feel free to use TypeScript in here as well. It's included in the build process, but explicitly ignored from being published to NPM using `.npmignore`.

#### Husky

Husky is included to assist in setting up git-hooks. Included is a very simple check. Configured directly in the `package.json` manifest.

```json
"husky": {
  "hooks": {
    "pre-push": "npm run format && npm run lint && npm run test"
  }
}
```

All this does is runs the check that your code is correctly formatted, the linter is happy and tests all pass, before the code is pushed to the repository. It **does not** interfere with you simply commiting to your local branches. Just prevents you from sharing broken code. This of course can be ignored using `git push --no-verify`.

## License

MIT

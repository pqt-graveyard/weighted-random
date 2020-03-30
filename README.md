<h1 align="center">
  weighted-random
</h1>

<h3 align="center">
Choose a random value from a fixed list of choices. Treat some values as more likely than others.
</h3>

<p align="center">
  <a href="https://github.com/pqt/weighted-random/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Released under the MIT license." />
  </a>
  <a href="https://github.com/pqt/weighted-random/actions?workflow=status">
    <img src="https://github.com/pqt/weighted-random/workflows/status/badge.svg" alt="Current Github Action build status." />
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=pqtdev">
    <img src="https://img.shields.io/twitter/follow/pqtdev.svg?label=Follow%20@pqtdev" alt="Follow @pqtdev" />
  </a>
</p>

## Installation

```
npm install @pqt/weighted-random
# OR
yarn add @pqt/weighted-random
```

## Usage

#### TypeScript

```ts
import { weightedRandom, Items } from "@pqt/weighted-random";

const items: Items = [
  ["Audi", 3],
  ["BMW", 1],
  ["Ferrari", 7],
  ["Lamborghini", 7],
  ["RAM", 4],
  ["Tesla", 6]
];

weightedRandom(items); // => "Lamborghini" (OR any of the other options with a variability based on weight)
```

#### JavaScript

```js
import { weightedRandom } from "@pqt/weighted-random";

weightedRandom([
  ["Audi", 3],
  ["BMW", 1],
  ["Ferrari", 7],
  ["Lamborghini", 7],
  ["RAM", 4],
  ["Tesla", 6]
]); // => "Lamborghini" (OR any of the other options with a variability based on weight)
```

## License

MIT

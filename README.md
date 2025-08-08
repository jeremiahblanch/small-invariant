# small-invariant 🔬💥

![types](https://img.shields.io/badge/types-typescript-blueviolet)
![npm bundle size](https://img.shields.io/bundlephobia/minzip/small-invariant)
![NPM Downloads](https://img.shields.io/npm/dm/small-invariant)

`small-invariant` is a fork of Alex Reardon's [`tiny-invariant`](https://github.com/alexreardon/tiny-invariant) that does not swallow error messages in production. `tiny-invariant` is great and deservedly popular, but if your production logs your error messages, eg to Sentry, then you want something more substantial than "Invariant failed".

For more information, view the readme for `tiny-invariant`.

The TL;DR is:

## What is `invariant`?

An `invariant` function takes a value, and if the value is `falsy` then the `invariant` function will throw.
If the value is `truthy`, then the function will not throw.

```ts
import invariant from 'small-invariant'

invariant(truthyValue, 'This should not throw!')

invariant(falsyValue, 'This will throw!')
// Error('Invariant failed: This will throw!');
```

## Type narrowing

`small-invariant` is useful for correctly narrowing types for `typescript`

```ts
const value: Person | null = { name: 'Alex' } // type of value == 'Person | null'
invariant(value, 'Expected value to be a person')
// type of value has been narrowed to 'Person'
```

## API

`(condition: any, message?: string | (() => string)) => void`

- `condition` is required and can be anything
- `message` optional `string` or a function that returns a `string` (`() => string`)

## Installation

```bash
# yarn
yarn add small-invariant

# npm
npm install small-invariant --save
```

## Builds

- We have a `es` (EcmaScript module) build
- We have a `cjs` (CommonJS) build
- We have a `umd` (Universal module definition) build in case you needed it

💥

# Development

IMPORTANT: While the library is supposed to work with Node 6 you will need to Node 8 or higher to run the tests.

## Setup

```
npm install
```

## Running the tests

```js
npm run test
```

Running them in watch mode

```js
npm run test -- --watch
```

## Running the browser tests

```js
npm run test:browser
```

# Design Decision

The purpose of this section is to introduce contributors to the philosophy and thinking behind the architecture and API design of this library.

### Isomorphic Use of the SDK

In order to allow various use-cases we want to make sure the SDK works not only in Node, but also in environments like a browser.

### Function Arguments

All public functions accept exactly one config argument. There are 3 major reasons why:
1. having one object with properties allows us to extend the API easily in the future
2. being explicit about the keys e.g. `functionId` or `event` helps developers to parse the code more easily
3. having one argument makes it easier for functional programming in JavaScript since currying is not needed

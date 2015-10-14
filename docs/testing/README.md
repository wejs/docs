# Testing

> Projects and plugins generated with yeoman generator-wejs have a default test structure with mocha, request and assert

See `mocha.js` documentation for more help in: https://mochajs.org/

## Test commands

### Run all tests

```sh
npm test
```

### Run selected tests

To run selected tests use mocha grep command like: 

Run only tests with `userFeature` text:

```sh
NODE_ENV=test LOG_LV=info ./node_modules/.bin/mocha test/bootstrap.js test/**/*.test.js -b -g 'userFeature'
```

## Examples

See we-core tests for working examples in: https://github.com/wejs/we-core/tree/master/test

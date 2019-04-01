# NodeTee
Simple test runner for Nodejs projects.

##Instruction

##### Define test with `Tee`
```js
const {Tee} = require('node-tee');

const myTee = Tee.new('Controller x');
myTee.case('Controller should pass', () => {
    assert(true, true);
});
module.exports = myTee;
```

##### Register `Tee` in `Pot`
```js
const {Pot} = require('node-tee');
const myTee = require('./myTee.path.js');

const myPot = Pot.new('My App');
myPot.register([myTee]);
myPot.run();
```
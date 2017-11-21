---
title: "We need a better Mocha"
layout: post
date: 2016-09-14 03:01:59
---
**I may be wrong on this one, and I'd LOVE to hear I am -- e-mail me at <brian.boyko@gmail.com> if you've come up with a solution.**

An issue I'm running into at work is that we're using unit testing to verify data results, as part of end-to-end testing.  Specifically, we want to make sure that the information in the database matches the information the front end puts out. 

But there's one big problem.  Mocha's describe() and it() functions *won't operate inside a .then() method.* (This isn't a problem just with Mocha, but it's probably the most used test suite, so we'll focus on Mocha for now.) 

Now, I can see why this would be the case - Mocha predates ES6 and native Promises. Still, this is extremely frustrating for front-end testing and other situations where you've got a whole bunch of asynchronous stuff to determine *what* tests to run.  

For example, let's say that you have a webpage.  Testing a single request is simple enough - you can use modules such as [chai-as-promised](https://github.com/domenic/chai-as-promised) to test values asynchronously. 

```javascript
// This works. 

import chai from 'chai'
import chaiAsPromised from 'chai-as-promised';
chai.use(chaiAsPromised);
const expect = chai.expect;
import request from 'superagent'

const swanson = () => new Promise((resolve, reject) => {
  request.get('http://ron-swanson-quotes.herokuapp.com/v2/quotes')
  .end((err, res) => {
    if(err) {
      reject(err);
    }
    console.log('Ron Swanson says: ', res.body)
    resolve(res);
  })
});

describe("swanson()", () => {
  it("gets a Ron Swanson quote", (done) => {
    expect(swanson().then((q) => q.body[0]))
      .to.eventually.be.a('string').notify(done);
  })
})
```

But what becomes a problem is when you the data you get *from* an asynchronous function tells you *what* tests need to be run. Here's a simple example:

```javascript
// THIS DOES NOT WORK

import chai from 'chai'
import chaiAsPromised from 'chai-as-promised';
chai.use(chaiAsPromised);
const expect = chai.expect;

const coinFlip = () => new Promise((resolve, reject) => {
  setTimeout(() => {
    let coin = Math.floor(Math.random * 2);
    let side = coin % 2 === 0 ? "heads" : "tails";
    resolve({coin, side})
  }, 200)
});

const battery = ({coin, side}) => {
  if(side === 'heads'){
    describe('HeadsTest', () => {
      it('should be heads', () => {
        expect(coin).to.equal(0)
      })
    })
  } else {
    describe('HeadsTest', () => {
      it('should be heads', () => {
        expect(coin).to.equal(1)
      })
    })
  }
}

coinFlip().then((flip) => battery(flip))
// result in terminal: 
// 0 passing (2ms)
```

Now, obviously, a coinflip app isn't very useful. But there are are times you're going to want to run different tests conditionally upon the results of a promise. 

At work, for example, one of our goals is to be able to ensure the integrity of our reports.  For example, at my work right now, for some of our 100+ reports, we make two requests to the server - one which asks solely for the length of the records, the other asks for the records themselves.  This way we can display "number of records" quickly to the user, rather than waiting for hundreds or thousands of records to download.  These two numbers should match.  Simple enough. Call one, .then() the other, .then() resolve that into a chai-as-promised expect/eventually, right? 

The problem arises when you realize that not every report is going to to ask for the number of records.  Some have average time, or median value, and while reports have a lot of similarities, they're different enough that you want to make sure that you're running the *right* tests on the *right* reports.  

At that point, you're looking at hard-coding tests for 100+ reports, manually. And that may be the way we have to do it, in the end. 

But I can't help but think that this is a simple enough problem that if Mocha was a little smarter, it would be able to handle these conditional tests and allow you to have the *computer* build the tests at runtime.  Isn't that what computers are for? Automating the boring stuff? 

Now, there are some tools built into mocha to help with some of these issues.  There's a "before()" and "beforeEach()" function.  There's also test.skip() and the --delay/run() tools. But every approach I have tried has met with the same problem - Mocha just wasn't designed to run tests conditionally. 

That's why I'm thinking it might be a good weekend project to fork Mocha and create a plugin or new testing suite with conditional testing built in.  In the meantime, we need a better Mocha. 

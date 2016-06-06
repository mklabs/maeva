# maeva

> Function helper to use ava syntax with mocha

---

From prometheo tests: https://github.com/mklabs/prometheo/blob/master/mocha/index.js

```js
let test = (name, suite) => {
  let t = Object.assign(assert, {
    get true () { return this.truethy },

    is (actual, expected, msg) {
      msg = msg || `${actual} ${expected}`;
      return this.ok.apply(this, msg);
    },

    truethy (val, msg) {
      return t.is(val, true, `${val} not truethy`)
    }
  });

  if (t.skipped) it(name);

  it(name, (done) => {
    let promise = suite(t);
    if (promise instanceof Promise) {
      console.log('promise', promise);
    }
    
    // todo handle promise / async stuff

    done();
  });
};
```

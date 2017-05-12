# deep-close-to

Node's `assert.deepEqual()` but with configurable comparator.
The default comparator compares the absolute difference to be below an epsilon, suitable for floats.

# example

``` js
var closeTo = require('deep-close-to');
console.dir([
    closeTo(
        { a : [ 2, 3 ], b : [ 4 ] },
        { a : [ 2, 3 ], b : [ 4 ] }
    ),
    closeTo(
        { x : 36/5, y : [6] },
        { x : 72/10, y : 6 }
    )
]);
```

# methods

``` js
var closeTo = require('deep-close-to')
```

## deepEqual(a, b, opts)

Compare objects `a` and `b`, returning whether they are equal according to a
recursive equality algorithm.

If `opts.strict` is `true`, use strict equality (`===`) to compare leaf nodes.
The default is to compare their absolute difference to be below 0.0000001.
`Number.EPSILON` was not used because numeric errors are often bigger than it.

# install

With [npm](http://npmjs.org) do:

```
npm install deep-close-to
```

# test

With [npm](http://npmjs.org) do:

```
npm test
```

# license

MIT. Derived largely from substack's [deep-equal](https://github.com/substack/node-deep-equal).

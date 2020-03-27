# expire-set
expire-set is a package that is basically a set - only that its values expire after a certain set time.
## Usage

Just use it as if you would be using a normal set:

```js
const ExpireSet = require("expire-set");
const timeout = 10000; // 10 seconds
const set = new ExpireSet(timeout);
set.add("fox");
console.log(set.has("fox")); // outputs true
setTimeout(() => {
	console.log(set.has("fox")); // outputs false
}, timeout + 6); // the library needs some time to do its magic
```

You can also use it with typescript:

```ts
import ExpireSet from "expire-set";
const timeout = 10000; // 10 seconds
const set = new Set<string>(timeout);
set.add("blah");
set.delete("blah");
```

## Methods
The following methods exist:
 - `set.size`: Returns the size of the ExpiredSet
 - `set.all`: Returns the ExpiredSet as a normal Set
 - `set.add(value)`: Adds a value to the ExpiredSet, returning itself
 - `set.has(value)`: Returns true/false, if the ExpiredSet has the value
 - `set.delete(value)`: Deletes a value of the ExpiredSet, returning itself


# klon

[![Build status](https://travis-ci.org/Hexagon/klon.svg)](https://travis-ci.org/Hexagon/klon) [![npm version](https://badge.fury.io/js/klon.svg)](https://badge.fury.io/js/klon)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://img.shields.io/badge/license-MIT-blue.svg)

JavaScript helper for deep cloning and deep merging objects as efficiently as possible. Supports and clones complex native objects as well as circular references.

# Installation

```npm install klon```

# Usage

```javascript
clone(source[, destination]);
```

**source** is the object to be copied.

**destination** (optional) is the new object, where all properties from source will be copied to.

```javascript
var clone = require('klon'),
	myObject1 = {
		a: 1,
		b: 2,
		c: {
			u: 14
		}
	},
	myObject2 = {
		c: [
			{ d: new Date() },
			{ e: "Hello" },
			{ f: "Hello" }
		]
	};

// Clone
var newObject1 = clone(myObject1);

// Extend newObject1 with myObject2
clone(myObject2, newObject1)

// Merge two objects into a new one
var newObject3 = clone(newObject2, clone(newObject1, {}) );

```


# License

MIT

<!--- Copyright (c) 2018 Gordon Williams, Pur3 Ltd. See the file LICENSE for copying permission. -->
Espruino Feature List
======================

<span style="color:red">:warning: **Please view the correctly rendered version of this page at https://www.espruino.com/Features. Links, lists, videos, search, and other features will not work correctly when viewed on GitHub** :warning:</span>

* KEYWORDS: Feature,Features,Compatability,ES5.ES6

What Follows is a table on JavaScript features and their implementation status in Espruino.

State is as follows:

* `-` not implemented.
* `Yes` implemented
* `Official` implemented, but only in boards that have enough memory. All [Official Espruino Boards](/Order) have these features.
* `1vxx` implemented in version `1vxx`

Summary
-------

Espruino implements a large amount of the [ES5 spec](http://ecma-international.org/ecma-262/5.1/) with parts of the
[ES6 spec](http://ecma-international.org/ecma-262/6.0/) where it is useful in
an embedded environment.

Some features are left out intentionally where:

* It would be too costly to implement them (eg. Unicode Strings)
* They're generally considered bad practice (eg. labels)

**Try Espruino for yourself online [in the emulator](https://www.espruino.com/ide/emulator.html)**

If you want a feature that isn't implemented [you can vote on this GitHub issue](https://github.com/espruino/Espruino/issues/1302)

Any features not listed here, or differences in Espruino that users should be aware of? Please [let us know!](https://github.com/espruino/EspruinoDocs/issues/new?title=info/Features.md)

General
-------

| Feature | Implementation Status |
|---------|-----------------------|
| Unicode Strings | - (8 bit strings only) |
| Regular Expressions | `1v95` `Official` (see below) |
| Labels | - |
| `Object.propertyIsEnumerable` | - |
| `with` keyword | - |
| Semicolon insertion on newlines | - `return\n42;` returns `42` in Espruino. |
| Function Hoisting | - |

**Note:** [Espruino executes code](/Performance) by parsing as
it executes. Function Hoisting wasn't implemented as it would require
two passes, which would slow down execution.

ES5
---

List of ES5 features from http://kangax.github.io/compat-table/es5/

| ES5 Feature | Implementation Status |
|---------|-----------------------|
| Strict Mode | - |
| Multiline String Literals | - |
| Accessors (Getters and Setters)  | `2v00`  `Official` |
| Trailing commas in object/array | `Yes` |
| Reserved words as property keys | `Yes` |
| Reserved words as Identifiers (`var of=1`) | - |
| `Object.create/defineProperty/defineProperties` | `Yes` |
| `Object.getPrototypeOf/keys` | `Yes` |
| `Object.seal/freeze/preventExtensions` | - |
| `Object.isSealed/isFrozen/isExtensible` | - |
| `Object.getOwnPropertyDescriptor/getOwnPropertyNames` | `Yes` |
| `Array.isArray` | `Yes` |
| `[].indexOf` | `Yes` |
| `[].lastIndexOf` | - |
| `[].every/some/forEach/map` | `Official` |
| `[].filter/reduce/reduceRight` | `Official` |
| `[].sort` | `Yes` |
| String property access (`"hi`[0]`) | `Yes` |
| `"".trim` | `Yes` |
| `Date.prototype.toISOString` | `Yes` |
| `Date.now()` | `Yes` |
| `Date.prototype.toJSON` | - |
| `Function.prototype.bind` | `Yes` |
| `JSON` | `Yes` |
| unassignable `undefined/NaN/Infinity` | `Yes` |
| Function.prototype.apply with non-arrays | `Yes` |
| parseInt ignores leading zeros | `Yes` |
| Function "prototype" non-enumerable | `Yes` |
| Arguments toStringTag is "Arguments" | - |
| Zero-width chars in identifiers | - |
| Unreserved words, eg `volatile` | `Yes` |
| Enumerable properties can be shadowed by non-enumerables | - |
| Thrown functions have proper "this" values | `Yes` |


ES6
---

List of ES6 features from http://es6-features.org:

| ES6 Feature | Implementation Status |
|---------|-----------------------|
| Constants | `2v14` (`const` is parsed but treated like `var` in earlier FW) |
| Block scoped Functions/Variables | `2v14` (`let` is parsed but treated like `var` in earlier FW) |
| Arrow Functions | `1v88` `Official` |
| Default Parameter Values | - |
| Rest/Spread | - |
| Template Literals | `1v88` `Official` |
| Template Literal Raw String access | - |
| Binary/Octal Literals | `Yes` |
| Unicode String/RegExp | - |
| RegExp Sticky Matching | - |
| Enhanced Object Properties | `2v14` (methods) |
| Destructing Assignment | - |
| Modules (`import`/`export`) | - |
| Class Definition | `1v96` `Official` |
| Class Inheritance, Base Class Access | `1v96` `Official` |
| Class Inheritance from Expressions | - |
| Class Static Members | `1v96` `Official` |
| Class Getters/Setters | `2v00` `Official` |
| Symbol Type | - |
| Iterators | - |
| Generators | - |
| Map/Set/WeakMap/WeakSet | - |
| Typed Arrays | `Yes` |
| `Object.assign` | `Yes` |
| `[].findIndex` | `2v00` `Official` |
| `"".repeat` | `2v00` `Official` |
| `"".startsWith/endsWith/includes` | `2v00` `Official` |
| `Number.isNaN/isFinite` | - (global `isNaN/isFinite` are implemented) |
| `Number.isSafeInteger` | - |
| `Number.EPSILON` | - |
| `Math.trunc` | - |
| `Math.sign` | `2v16` |
| Promises | `1v86` `Official` |
| Promise Combination | `1v90` `Official`  |
| Proxying / Reflection | - |
| Internationalization & Localization | - |


ES7/ES8
-------

| ES7 Feature | Implementation Status |
|-------------|----------------------|
| Array.prototype.includes | `2v05` `Official` |
| String.prototype.padStart/End | `2v08` `Official` |
| Exponentiation Operator | - |
| Async functions | - |
| Async generators | - |
| Object.getOwnPropertyDescriptors | - |
| Object.values/entries | `2v14` |
| Typed Objects | - |
| Trailing commas in function syntax | - |
| Object rest/spread properties | - |


Regular Expressions
-------------------

Espruino aims to support most commonly used RegExp contructs, however some parts of the spec are not implemented:

* [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions) other than `^` and `$`
* [Numeric quantifiers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Quantifiers) (eg `x{3}`)

There's a GitHub issue [concerning RegExp features here](https://github.com/espruino/Espruino/issues/1257)

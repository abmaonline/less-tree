# @abmaonline/less-tree

[![NPM version](http://img.shields.io/npm/v/@abmaonline/less-tree.svg?style=flat-square)](http://npmjs.org/package/@abmaonline/less-tree)
[![node](https://img.shields.io/badge/node.js-%3E=_6-green.svg?style=flat-square)](http://nodejs.org/download/)
[![License](http://img.shields.io/npm/l/@abmaonline/less-tree.svg?style=flat-square)](LICENSE)
[![npm download](https://img.shields.io/npm/dm/@abmaonline/less-tree.svg?style=flat-square)](https://npmjs.org/package/@abmaonline/less-tree)

Get less import vinyl file tree

Originally created by [LingyuCoder](https://github.com/LingyuCoder), but no longer available on github and made some changes to make it more robust.

## Installation

```bash
$ npm install --save @abmaonline/less-tree
```

## Usage

### Create Tree

```javascript
const lessTree = require('@abmaonline/less-tree');

// create less vinyl file tree
let root = lessTree('a.less');

root.children // => get tree children vinyl file object
```

### toTreeObject

```javascript
// get tree object
root.toTreeObject();
/*
{
  'b.less': {
    'd.less': {
      'sub/f.less': {}
    }
  },
  'c.less': {
    'd.less': {
      'sub/f.less': {}
    }
  },
  'sub/e.less': {}
}
*/
```

### toTreeString


```javascript
// get tree string
root.toTreeString();
/*
├─ b.less
│  └─ d.less
│     └─ sub/f.less
├─ c.less
│  └─ d.less
│     └─ sub/f.less
└─ sub/e.less
*/
```

## Todo

* tree walker
* ...

## Test

```bash
$ npm run test
$ npm run test-cov
```

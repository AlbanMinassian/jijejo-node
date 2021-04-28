# README

[![Build Status](https://travis-ci.com/AlbanMinassian/jijejo-node.svg?branch=master)](https://travis-ci.com/AlbanMinassian/jijejo-node)
[![Coverage Status](https://coveralls.io/repos/github/AlbanMinassian/jijejo-node/badge.svg?branch=master)](https://coveralls.io/github/AlbanMinassian/jijejo-node?branch=master)

[jijejo-node](https://github.com/AlbanMinassian/jijejo-node) is a javascript implementation of [jijejo-spec](https://github.com/AlbanMinassian/jijejo-spec) specifications.


Jijejo is a universal and easy api for all yours applications or libraries. Jijejo is a human and light alternative of [json:api](https://jsonapi.org/), [json-ld](https://json-ld.org/), [hal](http://stateless.co/hal_specification.html), [OpenAPI](https://swagger.io/specification/), [GraphQL](https://graphql.org/), [joi](https://github.com/hapijs/joi), [zod](https://github.com/vriad/zod), [yup](https://github.com/jquense/yup), [hydra](http://www.markus-lanthaler.com/hydra/) ... Back to basics to get ahead in your business. Read more by visiting [jijejo-spec](https://github.com/AlbanMinassian/jijejo-spec).

jijejo = (**j**)son (**i**)n + (**j**)son (**e**)rr + (**j**)son (**o**)ut

jijejo-node is the core used by [jijejo](https://github.com/AlbanMinassian/jijejo) package.

## install

```bash
npm install jijejo-node
```

## usage

```js
import { jsonin, jsonerr, jsonout, jicheck, jecheck, jocheck } from 'jijejo-node';
```


## about jijejo

### creates

#### jsonin

function to create jsonin.

```js
jsonin({"hello", "in"}) // return { meta:{}, in: {"hello", "in"}}
jsonin({"hello", "in"}, {"hello", "meta"}) // return { meta:{"hello", "meta"}, in: {"hello", "in"}}
```

#### jsonerr

function to create jsonerr.

```js
jsonerr({"hello", "err"}) // return { meta:{}, iserr: true, isout: false, err: {"hello", "err"}}
jsonerr({"hello", "err"}, {"hello", "meta"}) // return { meta:{"hello", "meta"}, iserr: true, isout: false, out: {"hello", "err"}}
```

#### jsonout

function to create jsonout.

```js
jsonout({"hello", "out"}) // return { meta:{}, iserr: false, isout: true, out: {"hello", "out"}}
jsonout({"hello", "out"}, {"hello", "meta"}) // return { meta:{"hello", "meta"}, iserr: false, isout: true, out: {"hello", "out"}}
```

### checks

#### jicheck = (j)son (i)n (check)

This function must verify jsonin basic attributs.

```js
jicheck({}); // return error because missing attribut in
jicheck({ in: {} }); // return ok, jsonin is valid
```

#### jecheck = (j)son (e)rr (check)

This function must verify jsonerr basic attributs.

```js
jecheck({ isout: true, iserr: true, err: {} }); // return error because isout==true
jecheck({ isout: false, iserr: true, err: {} }); // return ok, jsonerr is valid
```

#### jocheck = (j)son (o)ut (check)

This function must verify jsonout basic attributs.

```js
jocheck({ isout: true, iserr: true, out: {} }); // return error because iserr==true
jocheck({ isout: true, iserr: false, out: {} }); // return ok, jsonout is valid
```




## development

- `git clone https://github.com/AlbanMinassian/jijejo-node`
- `cd jijejo-node`
- `npm install`
- `npm run test`
- `npm run coverage`


## license

MIT

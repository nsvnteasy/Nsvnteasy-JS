# Nsvnteasy JS

Nsvnteasy Pure JS library for sending transactions from browser.

## Installation

```
npm install Nsvnteasy-js
```

## Tests

```
npm test
```

Tests written using mocha + schedule.js.

## Usage

Each function call has **secondSecret** parameter, this parameter is optional.

### Create transaction

Send 1000 NSC to 1859190791819301L

```js
var Nsvnteasy = require('Nsvnteasy-js');
var transaction = Nsvnteasy.transaction.createTransaction("1859190791819301L", 1000, "secret", "secondSecret");
```

### Create second signature transaction

```js
var Nsvnteasy = require('Nsvnteasy-js');
var transaction = Nsvnteasy.transaction.createTransaction("secret", "secondSecret");
```

### Create delegate transaction

```js
var Nsvnteasy = require('Nsvnteasy-js');
var transaction = Nsvnteasy.transaction.createDelegate("secret", "username", "secondSecret");
```

### Create vote transaction


```js
var Nsvnteasy = require('Nsvnteasy-js');
var transaction = createVote("secret", ["+58199578191950019299181920120128129"], "secondSecret");
```

### Peers Communication

All transactions are sent to `/api/peer/transactions` using the `POST` method.

Example:

```js
Method: POST
Content-Type: application/json

{
    "transaction" : {
        ...
    }
}
```

## License

The MIT License (MIT)

Copyright (c) 2018 Nsvnteasy

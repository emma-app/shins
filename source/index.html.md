---
title: Emma API - App
language_tabs:
  - javascript--nodejs: Node.js
  - javascript: Javascript
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="emma-api-app">Emma API - App v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API specification for the Emma App.

Base URLs:

* <a href="https://emma-app.com">https://emma-app.com</a>

<h1 id="emma-api-app-account">Account</h1>

Bank Account information.

## Gets Bank Account.

> Code samples

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://emma-app.com/accounts/{accountId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://emma-app.com/accounts/{accountId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /accounts/{accountId}`

<h3 id="gets-bank-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|integer|true|The account id.|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "userId": 0,
  "bankConnectionId": 0,
  "provider": "TRUELAYER",
  "name": "string",
  "availableBalance": 0,
  "postedBalance": 0,
  "creditCardBalance": 0,
  "currency": "string",
  "type": "CHECKING",
  "isHidden": true,
  "iban": "string",
  "swiftBic": "string",
  "accountNumber": "string",
  "sortCode": "string",
  "overdraftLimit": 0,
  "creditLimit": 0,
  "isOverdrawn": true,
  "leftFromOverdraft": 0,
  "hasBalanceHistory": true,
  "transactionsCount": 0,
  "isClosed": true,
  "nativeBalance": {
    "currency": "string",
    "postedBalance": 0,
    "availableBalance": 0,
    "overdraftLimit": 0,
    "leftFromOverdraft": 0,
    "creditCardBalance": 0,
    "creditLimit": 0
  },
  "iconUrl": "string"
}
```

<h3 id="gets-bank-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A bank account object.|[Account](#schemaaccount)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account does not exist.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error.|Inline|

<h3 id="gets-bank-account.-responseschema">Response Schema</h3>

Status Code **500**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|none|
|» message|string|true|none|none|
|» userMessage|string|false|none|none|
|» name|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Edit Bank Account.

> Code samples

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": 0,
  "userId": 0,
  "bankConnectionId": 0,
  "provider": "TRUELAYER",
  "name": "string",
  "availableBalance": 0,
  "postedBalance": 0,
  "creditCardBalance": 0,
  "currency": "string",
  "type": "CHECKING",
  "isHidden": true,
  "iban": "string",
  "swiftBic": "string",
  "accountNumber": "string",
  "sortCode": "string",
  "overdraftLimit": 0,
  "creditLimit": 0,
  "isOverdrawn": true,
  "leftFromOverdraft": 0,
  "hasBalanceHistory": true,
  "transactionsCount": 0,
  "isClosed": true,
  "nativeBalance": {
    "currency": "string",
    "postedBalance": 0,
    "availableBalance": 0,
    "overdraftLimit": 0,
    "leftFromOverdraft": 0,
    "creditCardBalance": 0,
    "creditLimit": 0
  },
  "iconUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://emma-app.com/accounts/{accountId}/edit',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://emma-app.com/accounts/{accountId}/edit',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /accounts/{accountId}/edit`

> Body parameter

```json
{
  "id": 0,
  "userId": 0,
  "bankConnectionId": 0,
  "provider": "TRUELAYER",
  "name": "string",
  "availableBalance": 0,
  "postedBalance": 0,
  "creditCardBalance": 0,
  "currency": "string",
  "type": "CHECKING",
  "isHidden": true,
  "iban": "string",
  "swiftBic": "string",
  "accountNumber": "string",
  "sortCode": "string",
  "overdraftLimit": 0,
  "creditLimit": 0,
  "isOverdrawn": true,
  "leftFromOverdraft": 0,
  "hasBalanceHistory": true,
  "transactionsCount": 0,
  "isClosed": true,
  "nativeBalance": {
    "currency": "string",
    "postedBalance": 0,
    "availableBalance": 0,
    "overdraftLimit": 0,
    "leftFromOverdraft": 0,
    "creditCardBalance": 0,
    "creditLimit": 0
  },
  "iconUrl": "string"
}
```

<h3 id="edit-bank-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|integer|true|The account id.|
|body|body|[Account](#schemaaccount)|false|Various bank account edits.|

> Example responses

> 500 Response

```json
{
  "statusCode": 0,
  "message": "string",
  "userMessage": "string",
  "name": "string"
}
```

<h3 id="edit-bank-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Successfully edited account.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Could not edit.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error.|Inline|

<h3 id="edit-bank-account.-responseschema">Response Schema</h3>

Status Code **500**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|none|
|» message|string|true|none|none|
|» userMessage|string|false|none|none|
|» name|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Toggle Account isHidden.

> Code samples

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "accountEdits": [
    {
      "id": 0,
      "isHidden": true
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://emma-app.com/accounts',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://emma-app.com/accounts',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PATCH /accounts`

> Body parameter

```json
{
  "accountEdits": [
    {
      "id": 0,
      "isHidden": true
    }
  ]
}
```

<h3 id="toggle-account-ishidden.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Account hidden edits.|
|» accountEdits|body|[[AccountEdit](#schemaaccountedit)]|true|none|
|»» id|body|integer|true|none|
|»» isHidden|body|boolean|true|none|

> Example responses

> 200 Response

```json
{
  "status": "Success"
}
```

<h3 id="toggle-account-ishidden.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Standard 200 success response.|Inline|

<h3 id="toggle-account-ishidden.-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create Manual Account.

> Code samples

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "type": "CHECKING",
  "balance": 0,
  "currency": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://emma-app.com/accounts',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://emma-app.com/accounts',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /accounts`

> Body parameter

```json
{
  "name": "string",
  "type": "CHECKING",
  "balance": 0,
  "currency": "string"
}
```

<h3 id="create-manual-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Information related to new manual account to create.|
|» name|body|string|true|New Account name.|
|» type|body|string|true|none|
|» balance|body|number|true|Posted balance of manual account.|
|» currency|body|string|false|Currency of the account (Defaults to user's primary currency).|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» type|CHECKING|
|» type|SAVINGS|
|» type|CREDITCARD|
|» type|CRYPTO|
|» type|INVESTMENT|
|» type|PENSION|
|» type|LOAN|
|» type|BUSINESS_CHECKING|
|» type|BUSINESS_SAVINGS|
|» type|CHIP_GOAL|
|» type|OTHER|
|» type|HIDDEN|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "userId": 0,
  "bankConnectionId": 0,
  "provider": "TRUELAYER",
  "name": "string",
  "availableBalance": 0,
  "postedBalance": 0,
  "creditCardBalance": 0,
  "currency": "string",
  "type": "CHECKING",
  "isHidden": true,
  "iban": "string",
  "swiftBic": "string",
  "accountNumber": "string",
  "sortCode": "string",
  "overdraftLimit": 0,
  "creditLimit": 0,
  "isOverdrawn": true,
  "leftFromOverdraft": 0,
  "hasBalanceHistory": true,
  "transactionsCount": 0,
  "isClosed": true,
  "nativeBalance": {
    "currency": "string",
    "postedBalance": 0,
    "availableBalance": 0,
    "overdraftLimit": 0,
    "leftFromOverdraft": 0,
    "creditCardBalance": 0,
    "creditLimit": 0
  },
  "iconUrl": "string"
}
```

<h3 id="create-manual-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New Manual Account.|[Account](#schemaaccount)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSaccountedit">AccountEdit</h2>

<a id="schemaaccountedit"></a>

```json
{
  "id": 0,
  "isHidden": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|isHidden|boolean|true|none|none|

<h2 id="tocSaccount">Account</h2>

<a id="schemaaccount"></a>

```json
{
  "id": 0,
  "userId": 0,
  "bankConnectionId": 0,
  "provider": "TRUELAYER",
  "name": "string",
  "availableBalance": 0,
  "postedBalance": 0,
  "creditCardBalance": 0,
  "currency": "string",
  "type": "CHECKING",
  "isHidden": true,
  "iban": "string",
  "swiftBic": "string",
  "accountNumber": "string",
  "sortCode": "string",
  "overdraftLimit": 0,
  "creditLimit": 0,
  "isOverdrawn": true,
  "leftFromOverdraft": 0,
  "hasBalanceHistory": true,
  "transactionsCount": 0,
  "isClosed": true,
  "nativeBalance": {
    "currency": "string",
    "postedBalance": 0,
    "availableBalance": 0,
    "overdraftLimit": 0,
    "leftFromOverdraft": 0,
    "creditCardBalance": 0,
    "creditLimit": 0
  },
  "iconUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|userId|integer|true|none|none|
|bankConnectionId|integer|false|none|none|
|provider|string|true|none|none|
|name|string|true|none|none|
|availableBalance|number|false|none|none|
|postedBalance|number|true|none|none|
|creditCardBalance|number|false|none|none|
|currency|string|true|none|none|
|type|string|true|none|none|
|isHidden|boolean|false|none|none|
|iban|string|false|none|none|
|swiftBic|string|false|none|none|
|accountNumber|string|false|none|none|
|sortCode|string|false|none|none|
|overdraftLimit|number|false|none|none|
|creditLimit|number|false|none|none|
|isOverdrawn|boolean|false|none|none|
|leftFromOverdraft|number|false|none|none|
|hasBalanceHistory|boolean|true|none|none|
|transactionsCount|integer|false|none|none|
|isClosed|boolean|true|none|none|
|nativeBalance|object|false|none|none|
|» currency|string|true|none|none|
|» postedBalance|number|true|none|none|
|» availableBalance|number|false|none|none|
|» overdraftLimit|number|false|none|none|
|» leftFromOverdraft|number|false|none|none|
|» creditCardBalance|number|false|none|none|
|» creditLimit|number|false|none|none|
|iconUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|provider|TRUELAYER|
|provider|SALTEDGE|
|provider|MONZO|
|provider|STARLING|
|provider|PAYPAL|
|provider|BINANCE|
|provider|BITFINEX|
|provider|BITTREX|
|provider|KRAKEN|
|provider|BITSTAMP|
|provider|BLOCKEXPLORER|
|provider|BLOCKCHAINDOTCOM|
|provider|BLOCKCYPHERETH|
|provider|ETHERSCAN|
|provider|COINBASE|
|provider|WEALTHSIMPLE|
|provider|PENSIONBEE|
|provider|CHIP|
|provider|PLAID|
|provider|MANUAL|
|provider|DUMMY|
|provider|SPLIT|
|type|CHECKING|
|type|SAVINGS|
|type|CREDITCARD|
|type|CRYPTO|
|type|INVESTMENT|
|type|PENSION|
|type|LOAN|
|type|BUSINESS_CHECKING|
|type|BUSINESS_SAVINGS|
|type|CHIP_GOAL|
|type|OTHER|
|type|HIDDEN|


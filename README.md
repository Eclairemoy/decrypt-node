# Decrypt Function
[Evervault](https://evervault.com) makes it easy to encrypt data at source, process it in a Function — a secure, serverless function — and never store it unencrypted.

This is a simple Evervault Function that will allow you to decrypt data.

## Getting started with Evervault

Evervault consists of two parts, encrypting your data at source, using either our Node SDK, or Browser and React SDKs and then sending that encrypted data to a Function to be processed securely.


## The steps
1. Encrypt your data at source, using one of our SDKs.
2. Process the encrypted data in a Function

### Encrypting at source
```javascript
// This example uses the Evervault Node SDK.
const Evervault = require('@evervault/sdk');

// Initialize the client with your App's API key
const evervault = new Evervault('<YOUR-API-KEY>');

// Encrypt your data
const encrypted = await evervault.encrypt({ name: 'Claude Shannon' });
```

### Process your encrypted data in a Function
You should encrypt this payload using either our Node SDK or Browser SDK, then run it in the Hello Function:

```javascript
// Process the encrypted data in a Function
const result = await evervault.run('<YOUR_FUNCTION_NAME>', encrypted);
```

## Understanding the Function
Since functions decrypts data automatically, it's just a few lines of code:

```javascript
exports.handler = async (data, context) => {
    return data
};
```

Or check it out in [index.js](./index.js).

--- 
If you want to know more about Evervault, check out our [documentation](https://docs.evervault.com).

# node-cfturnstile
Modified version of [node-hcaptcha](https://github.com/vastus/node-hcaptcha) to work with Cloudflare Turnstile **(WORK IN PROGRESS)**

## Install

```
npm install --save cfturnstile
```

## Usage

```js
const {verify} = require('cfturnstile');

const secret = 'my Turnstile secret from the Cloudflare dashboard';
const token = 'token from widget';

verify(secret, token)
  .then((data) => {
    if (data.success === true) {
      console.log('success!', data);
    } else {
      console.log('verification failed');
    }
  })
  .catch(console.error);

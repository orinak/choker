<img src="logo.png" align="right" height="60px"/>
<img align="right" width="0" height="48px" hspace="10"/>

# choker

[![Build Status](https://travis-ci.org/despan/choker.svg?branch=master)](https://travis-ci.org/despan/choker)
[![Coverage Status](https://coveralls.io/repos/github/despan/choker/badge.svg?branch=master)](https://coveralls.io/github/despan/choker?branch=master)
[![Published Version](https://img.shields.io/npm/v/choker)](https://www.npmjs.com/package/choker)
[![Commit Style](https://img.shields.io/badge/commits-conventional-blue.svg)](https://conventionalcommits.org)
[![Code Style](https://img.shields.io/badge/code%20style-standard-blue.svg)](http://standardjs.com)
[![GitHub](https://img.shields.io/github/license/despan/choker)](/LICENSE)

> throttle on limited rate

### Installation

```sh
npm install choker
```

### Usage

```js
const choker = require('choker')

const rate = {
  limit: 20,
  interval: 1000 // ms
}

async function sendSMS (data) {
  // perform request...
  return `Sent to ${data.to}`
}

const smsList = [
  { to: 777888, msg: 'hi' },
  // ...
]

choker(rate, sendSMS, smsList)
  .then(console.log)

// [
//   'Sent to 777888',
//   ...
// ]
```

### Development

```sh
# clone repo
git clone https://github.com/despan/choker

#
cd choker

# install dependencies
npm install
```

### Test

```sh
# run quick tests
npm run test

# test watching file changes
npm run test:watch
```

### Contributing

Check [Contributing Guide](/CONTRIBUTING.md).

## Acknowledgements

- Choker logo by Olena Panasovska from the Noun Project

## License

The MIT License

# pbkdf2-sha512 [![Join the chat at https://gitter.im/ZenyWay/pbkdf2-sha512](https://badges.gitter.im/ZenyWay/pbkdf2-sha512.svg)](https://gitter.im/ZenyWay/pbkdf2-sha512?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![NPM](https://nodei.co/npm/pbkdf2sha512.png?compact=true)](https://nodei.co/npm/pbkdf2sha512/)
[![build status](https://travis-ci.org/ZenyWay/pbkdf2-sha512.svg?branch=master)](https://travis-ci.org/ZenyWay/pbkdf2-sha512)
[![coverage status](https://coveralls.io/repos/github/ZenyWay/pbkdf2-sha512/badge.svg?branch=master)](https://coveralls.io/github/ZenyWay/pbkdf2-sha512)
[![Dependency Status](https://gemnasium.com/badges/github.com/ZenyWay/pbkdf2-sha512.svg)](https://gemnasium.com/github.com/ZenyWay/pbkdf2-sha512)

node crypto's async pbkdf2 promisified and with sane defaults.

# <a name="example"></a> example
```ts
import getPbkdf2OSha512 from 'pbkdf2sha512'
import debug = require('debug')
debug.enable('example:*')

const pbkdf2 = getPbkdf2OSha512({
  // generate random 64-byte long salt string, base64-encoded (default)
  iterations: 16384, // min 8192, default 65536
  length: 64 // min 32, max 64, default 64
  // digest is always 'sha512'
})

debug('example:')('digest passphrase...')

const key = pbkdf2('secret passphrase')
.then(debug('example:digest:'))
// { value: "...", spec: { encoding: "base64", salt: "...", iterations: 16384, length: 64, hmac: "sha512" }}
```
the files of this example are available [in this repository](./spec/example).

view a [live version of this example in the browser console](https://cdn.rawgit.com/ZenyWay/pbkdf2-sha512/v1.0.0/spec/example/index.html)
in the browser console,
or by cloning this repository and running the following commands from a terminal:
```bash
npm install
npm run example
```

# <a name="api"></a> API v1.0 stable
`ES5` and [`Typescript`](http://www.typescriptlang.org/) compatible.
coded in `Typescript 2`, transpiled to `ES5`.

for a detailed specification of the API,
[run the unit tests in your browser](https://cdn.rawgit.com/ZenyWay/pbkdf2-opgp-key/v1.0.0/spec/web/index.html).

# <a name="contributing"></a> CONTRIBUTING
see the [contribution guidelines](./CONTRIBUTING.md)

# <a name="license"></a> LICENSE
Copyright 2017 Stéphane M. Catala

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the [License](./LICENSE) for the specific language governing permissions and
Limitations under the License.

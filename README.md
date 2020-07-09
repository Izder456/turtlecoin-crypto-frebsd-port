![image](https://user-images.githubusercontent.com/34389545/35821974-62e0e25c-0a70-11e8-87dd-2cfffeb6ed47.png)

# TurtleCoin: Standalone Cryptography Library

[![NPM](https://nodei.co/npm/turtlecoin-crypto.png?downloads=true&stars=true)](https://nodei.co/npm/turtlecoin-crypto/)

![Prerequisite](https://img.shields.io/badge/node-%3E%3D6-blue.svg) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/turtlecoin/turtlecoin-crypto/graphs/commit-activity) [![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-yellow.svg)](https://github.com/turtlecoin/turtlecoin-crypto/blob/master/LICENSE) [![Twitter: TurtlePay](https://img.shields.io/twitter/follow/_TurtleCoin.svg?style=social)](https://twitter.com/_TurtleCoin)

#### Master Build Status
[![Build Status](https://github.com/turtlecoin/turtlecoin-crypto/workflows/CI%20Build%20Tests/badge.svg?branch=master)](https://github.com/turtlecoin/turtlecoin-crypto/actions)

#### Development Build Status
[![Build Status](https://github.com/turtlecoin/turtlecoin-crypto/workflows/CI%20Build%20Tests/badge.svg?branch=development)](https://github.com/turtlecoin/turtlecoin-crypto/actions)

This repository contains the necessary files to compile the cryptography library used within [TurtleCoin](https://turtlecoin.lol) as a standalone library that can be included in various other projects in a variety of development environments, including:

* Node.js >= 6.x
* C++
* C# (via C++ shared library & P/Invoke)
* Native Javascript
* WASM

## Javascript Library

**Note:** We build prebuilds of the Node.js native addon module as well as the WASM/JS binaries that are included for distribution with the NPM installed version of this package to speed up your development efforts.

### Dependencies

* [Node.js](https://nodejs.org) >= +6.x LTS (or Node v11)

#### Windows (if not using prebuilds)

##### Prerequisites

Read very careful if you want this to work right the first time.

1) Open a *Windows Powershell* console as **Administrator**

2) Run the command: `npm install -g windows-build-tools --vs2015`
   ***This will take a while. Sit tight.***

### Installation

```bash
npm install turtlecoin-crypto
```

### Intialization

#### TypeScript

```javascript
import { Crypto } from 'turtlecoin-crypto';
const TurtleCoinCrypto = new Crypto();
```

#### CommonJS

```javascript
const Crypto = require('turtlecoin-crypto').Crypto
const TurtleCoinCrypto = new Crypto()
```

#### Documentation

You can find the full TypeScript/JS documentation for this library [here](https://crypto.turtlecoin.dev).

## C++ Library

### How To Compile

#### Build Optimization

The CMake build system will, by default, create optimized *native* builds for your particular system type when you build the software. Using this method, the binaries created provide a better experience and all together faster performance.

However, if you wish to create *portable* binaries that can be shared between systems, specify `-DARCH=default` in your CMake arguments during the build process. Note that *portable* binaries will have a noticable difference in performance than *native* binaries. For this reason, it is always best to build for your particuar system if possible.

##### FreeBSD

Ensure you have the dependencies listed above.

```bash
git clone -b master --single-branch https://github.com/izder45/turtlecoin-crypto-freebsd-port
cd turtlecoin-crypto-freebsd-port
mkdir build
cd build
cmake ..
make
```

The following library files will be created in the `build` folder:

* `libturtlecoin-crypto-static.a`

## Native Javascript & WASM

### Prerequisites

You will need the following packages:

* CMake (2.8 or higher), make, and git.

### Compiling

```bash
git clone -b master --single-branch https://github.com/turtlecoin/turtlecoin-crypto
cd turtlecoin-crypto
bash ./build_js.sh
```

This script will install the necessary dependencies on your machine and then proceed to compile the library to Native Javascript and WASM.

The following library files will be created in the `jsbuild` folder:

* Native Javascript
  * `turtlecoin-crypto.js`
* WASM
  * `turtlecoin-crypto-wasm.js`

## Thanks
Cryptonote Developers, Bytecoin Developers, Monero Developers, Forknote Project, TurtleCoin Community

## Copypasta for license when editing files

Hi TurtleCoin contributor, thanks for forking and sending back Pull Requests. Extensive docs about contributing are in the works or elsewhere. For now this is the bit we need to get into all the files we touch. Please add it to the top of the files.

```
// Copyright (c) 2012-2017, The CryptoNote developers, The Bytecoin developers
// Copyright (c) 2014-2018, The Monero Project
// Copyright (c) 2018-2019, The TurtleCoin Developers
//
// Please see the included LICENSE file for more information.
```

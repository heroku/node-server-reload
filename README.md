# server-reload

Reload server files using a combination of Node's [cluster](https://nodejs.org/api/cluster.html) and Facebook's [watchman](https://facebook.github.io/watchman/).

## Installation

First, make sure you have [watchman](https://facebook.github.io/watchman/) installed and available on your `$PATH`. For instructions about how to install, [check the official guide](https://facebook.github.io/watchman/docs/install.html).

Install using NPM:

```
npm install @fnando/server-reload --save-dev
```

or [Yarn](https://yarnpkg.com/):

```
yarn add @fnando/server-reload --dev
```

## Usage

Imagine you have a file structure like this:

```
/Projects/foo-bar
├── package.json
├── src
│   └── server.js
└── yarn.lock

1 directory, 3 files
```

To use regular Node.js binary, call the `server-reload` binary:

```
./node_modules/.bin/server-reload \
    --pattern src/server \
    --pattern package.json \
    --entry src/server.js \
    --root $(pwd)
```

But if you need to transform your files using [Babel.js](https://babeljs.io), use `server-reload-babel` instead:

```
./node_modules/.bin/server-reload-babel \
    --pattern src/server \
    --pattern package.json \
    --entry src/server.js \
    --root $(pwd)
```

## License

(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

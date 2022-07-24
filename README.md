# Vite React Typescript for use with new IPFS ESM modules
- No transpiling into ipfsjs no require statement
- top level await for  `const ipfs = await create()`
- Big Integer literals in the target environment
## datastore-core-110-react-vite-example

Minimal reproduction of ipfs/js-datastore-core [#110](https://github.com/ipfs/js-datastore-core/issues/110) using vite react typescript
configured with es2022 for top level await for `const ipfs = await create()` from [here](https://github.com/ipfs/js-ipfs/blob/master/packages/ipfs-http-client/README.md#example-1)

```js
taylor  ~  misc  js-datastore-core  vite-project  npm run dev

> vite-project@0.0.0 dev
> vite


  VITE v3.0.2  ready in 357 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
✘ [ERROR] No matching export in "node_modules/datastore-core/esm/src/index.js" for import "Errors"

    node_modules/datastore-level/esm/src/index.js:4:2:
      4 │   Errors
        ╵   ~~~~~~

/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1605
  let error = new Error(`${text}${summary}`);
              ^

Error: Build failed with 1 error:
node_modules/datastore-level/esm/src/index.js:4:2: ERROR: No matching export in "node_modules/datastore-core/esm/src/index.js" for import "Errors"
    at failureErrorWithLog (/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1605:15)
    at /home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1251:28
    at runOnEndCallbacks (/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1034:63)
    at buildResponseToResult (/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1249:7)
    at /home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:1358:14
    at /home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:666:9
    at handleIncomingPacket (/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:763:9)
    at Socket.readFromStdout (/home/taylor/misc/js-datastore-core/vite-project/node_modules/esbuild/lib/main.js:632:7)
    at Socket.emit (node:events:527:28)
    at addChunk (node:internal/streams/readable:324:12) {
  errors: [
    {
      detail: undefined,
      id: '',
      location: {
        column: 2,
        file: 'node_modules/datastore-level/esm/src/index.js',
        length: 6,
        line: 4,
        lineText: '  Errors',
        namespace: '',
        suggestion: ''
      },
      notes: [],
      pluginName: '',
      text: 'No matching export in "node_modules/datastore-core/esm/src/index.js" for import "Errors"'
    }
  ],
  warnings: []
}

Node.js v17.9.1
```

# npmtest-tchannel

#### basic test coverage for  tchannel (v3.9.11)  [![npm package](https://img.shields.io/npm/v/npmtest-tchannel.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-tchannel) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-tchannel.svg)](https://travis-ci.org/npmtest/node-npmtest-tchannel)

#### network multiplexing and framing protocol for RPC or parser drag racing

[![NPM](https://nodei.co/npm/tchannel.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/tchannel)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-tchannel/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-tchannel/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-tchannel/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-tchannel/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-tchannel/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-tchannel/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-tchannel/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-tchannel/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-tchannel/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-tchannel/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-tchannel/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-tchannel/build/test-report.html](https://npmtest.github.io/node-npmtest-tchannel/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-tchannel/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-tchannel/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-tchannel/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-tchannel/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-tchannel/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-tchannel/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-tchannel/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-tchannel/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "tchannel",
    "description": "network multiplexing and framing protocol for RPC or parser drag racing",
    "author": "mranney@uber.com",
    "version": "3.9.11",
    "scripts": {
        "lint": "eslint $(git ls-files | grep '.js$')",
        "travis": "npm run check-licence && npm run lint -s && npm run travis-cover -s && npm run check-benchmark -s",
        "test": "npm run check-licence && npm run lint -s && npm run cover -s && npm run check-benchmark -s",
        "benchmark": "echo '!!! DEPRECATED: Better to just run 'node benchmarks' directly' >&2; node benchmarks",
        "hyperbahn-link-test": "./test/link_hyperbahn.sh",
        "tcurl-link-test": "./test/link_tcurl.sh",
        "check-benchmark": "node benchmarks -- -r 10000 -p 750",
        "take-benchmark": "make -C benchmarks take",
        "take-relay-benchmark": "make -C benchmarks take_relay",
        "take-trace-benchmark": "amke -C benchmarks take_trace",
        "cover": "npm run check-files && npm run test-cover && istanbul check-coverage",
        "travis-cover": "npm run check-files && npm run travis-test-cover && istanbul check-coverage",
        "check-files": "bash scripts/verify_included.sh",
        "test-cover": "istanbul cover --report html --print none test/index.js -- --color | faucet && istanbul report text",
        "travis-test-cover": "istanbul cover --report html --print none test/index.js -- --color && istanbul report text",
        "check-cover": "istanbul check-coverage",
        "view-cover": "opn coverage/index.html",
        "check-licence": "uber-licence --dry",
        "add-licence": "uber-licence"
    },
    "main": "channel",
    "repository": {
        "type": "git",
        "url": "git@github.com:uber/tchannel-node"
    },
    "dependencies": {
        "bufrw": "^1.2.1",
        "crc": "3.2.1",
        "error": "^7.0.1",
        "farmhash": "1.1.0",
        "json-stringify-safe": "^5.0.0",
        "metrics": "^0.1.8",
        "minimist": "^1.1.0",
        "process": "0.11.1",
        "raw-body": "^2.1.2",
        "ready-signal": "^1.1.1",
        "run-parallel": "^1.1.0",
        "run-series": "^1.1.2",
        "safe-json-parse": "^4.0.0",
        "sse4_crc32": "4.1.1",
        "tape-cluster": "2.1.0",
        "thriftrw": "^3.11.0",
        "xorshift": "^0.2.0",
        "xtend": "^4.0.0"
    },
    "devDependencies": {
        "async": "^0.9.0",
        "chalk": "^1.0.0",
        "child_pty": "3.0.1",
        "collect-parallel": "^1.0.1",
        "debug-logtron": "5.1.1",
        "duplexer": "^0.1.1",
        "eslint": "0.24.0",
        "eslint-config-perf-standard": "1.0.0",
        "faucet": "0.0.1",
        "format-stack": "4.1.1",
        "hexer": "^1.4.5",
        "istanbul": "^0.3.13",
        "itape": "^1.9.1",
        "lb_pool": "^1.6.3",
        "ldjson-stream": "^1.2.1",
        "loadtest": "1.2.14",
        "my-local-ip": "1.0.0",
        "once": "^1.3.1",
        "opn": "^1.0.1",
        "replr": "^1.0.4",
        "split2": "^0.2.1",
        "tape": "^4.0.0",
        "through2": "^0.6.3",
        "time-mock": "^0.1.2",
        "uber-licence": "^2.0.0",
        "uber-statsd-client": "1.3.2"
    },
    "pre-commit": [],
    "pre-commit.silent": true,
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

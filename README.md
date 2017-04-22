# npmdoc-gh-pages

#### api documentation for  [gh-pages (v0.12.0)](https://github.com/tschaub/gh-pages)  [![npm package](https://img.shields.io/npm/v/npmdoc-gh-pages.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gh-pages) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gh-pages.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gh-pages)

#### Publish to a gh-pages branch on GitHub (or any other branch on any other remote)

[![NPM](https://nodei.co/npm/gh-pages.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gh-pages)

- [https://npmdoc.github.io/node-npmdoc-gh-pages/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-gh-pages/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gh-pages/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tim Schaub",
        "url": "http://tschaub.net/"
    },
    "bin": {
        "gh-pages": "bin/gh-pages"
    },
    "bugs": {
        "url": "https://github.com/tschaub/gh-pages/issues"
    },
    "dependencies": {
        "async": "2.1.2",
        "commander": "2.9.0",
        "globby": "^6.1.0",
        "graceful-fs": "4.1.10",
        "q": "1.4.1",
        "q-io": "1.13.2",
        "rimraf": "^2.5.4"
    },
    "description": "Publish to a gh-pages branch on GitHub (or any other branch on any other remote)",
    "devDependencies": {
        "chai": "^3.5.0",
        "eslint": "^3.10.2",
        "eslint-config-tschaub": "^6.0.0",
        "mocha": "^3.1.2"
    },
    "directories": {},
    "dist": {
        "shasum": "d951e3ed98b85699d4b0418eb1a15b1a04988dc1",
        "tarball": "https://registry.npmjs.org/gh-pages/-/gh-pages-0.12.0.tgz"
    },
    "eslintConfig": {
        "extends": "tschaub"
    },
    "gitHead": "c6cd05dde53c061e605de4561269beb4ce5334d4",
    "homepage": "https://github.com/tschaub/gh-pages",
    "keywords": [
        "git",
        "gh-pages",
        "github"
    ],
    "license": "MIT",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "tschaub"
        },
        {
            "name": "markdalgleish"
        }
    ],
    "name": "gh-pages",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/tschaub/gh-pages.git"
    },
    "scripts": {
        "pretest": "eslint lib test bin/gh-pages",
        "test": "mocha --recursive test"
    },
    "version": "0.12.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

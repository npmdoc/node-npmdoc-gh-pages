# api documentation for  [gh-pages (v0.12.0)](https://github.com/tschaub/gh-pages)  [![npm package](https://img.shields.io/npm/v/npmdoc-gh-pages.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gh-pages) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gh-pages.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gh-pages)
#### Publish to a gh-pages branch on GitHub (or any other branch on any other remote)

[![NPM](https://nodei.co/npm/gh-pages.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gh-pages)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screenCapture.buildCi.browser.apidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gh-pages/build/apidoc.html)

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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gh-pages](#apidoc.module.gh-pages)
1.  [function <span class="apidocSignatureSpan">gh-pages.</span>clean ()](#apidoc.element.gh-pages.clean)
1.  [function <span class="apidocSignatureSpan">gh-pages.</span>publish (basePath, config, callback)](#apidoc.element.gh-pages.publish)



# <a name="apidoc.module.gh-pages"></a>[module gh-pages](#apidoc.module.gh-pages)

#### <a name="apidoc.element.gh-pages.clean"></a>[function <span class="apidocSignatureSpan">gh-pages.</span>clean ()](#apidoc.element.gh-pages.clean)
- description and source-code
```javascript
function clean() {
  rimraf.sync(getCacheDir());
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.publish"></a>[function <span class="apidocSignatureSpan">gh-pages.</span>publish (basePath, config, callback)](#apidoc.element.gh-pages.publish)
- description and source-code
```javascript
function publish(basePath, config, callback) {
  if (typeof config === 'function') {
    callback = config;
    config = {};
  }

  var defaults = {
    add: false,
    git: 'git',
    clone: getCacheDir(),
    dotfiles: false,
    branch: 'gh-pages',
    remote: 'origin',
    src: '**/*',
    only: '.',
    push: true,
    message: 'Updates',
    silent: false,
    logger: function() {}
  };

  // override defaults with any task options
  // TODO: Require Node >= 4 and use Object.assign
  var options = {};
  for (var d in defaults) {
    options[d] = defaults[d];
  }
  for (var c in config) {
    options[c] = config[c];
  }

  function log(message) {
    if (!options.silent) {
      options.logger(message);
    }
  }

  if (!callback) {
    callback = function(err) {
      if (err) {
        log(err.message);
      }
    };
  }

  function done(err) {
    try {
      callback(err);
    } catch (err2) {
      log('Publish callback threw: ', err2.message);
    }
  }

  try {
    if (!fs.statSync(basePath).isDirectory()) {
      done(new Error('The "base" option must be an existing directory'));
      return;
    }
  } catch (err) {
    done(err);
    return;
  }

  var files = globby.sync(options.src, {
    cwd: basePath,
    dot: options.dotfiles
  }).filter(function(file) {
    return !fs.statSync(path.join(basePath, file)).isDirectory();
  });

  if (!Array.isArray(files) || files.length === 0) {
    done(new Error('Files must be provided in the "src" property.'));
    return;
  }

  var only = globby.sync(options.only, {cwd: basePath});

  git.exe(options.git);

  var repoUrl;
  getRepo(options)
      .then(function(repo) {
        repoUrl = repo;
        log('Cloning ' + repo + ' into ' + options.clone);
        return git.clone(repo, options.clone, options.branch, options);
      })
      .then(function() {
        return getRemoteUrl(options.clone, options.remote)
            .then(function(url) {
              if (url !== repoUrl) {
                var message = 'Remote url mismatch.  Got "' + url + '" ' +
                    'but expected "' + repoUrl + '" in ' + options.clone +
                    '.  If you have changed your "repo" option, try ' +
                    'running the "clean" task first.';
                return Q.reject(new Error(message));
              } else {
                return Q.resolve();
              }
            });
      })
      .then(function() {
        // only required if someone mucks with the checkout between builds
        log('Cleaning');
        return git.clean(options.clone);
      })
      .then(function() {
        log('Fetching ' + options.remote);
        return git.fetch(options.remote, options.clone);
      })
      .then(function() {
        log('Checking out ' + options.remote + '/' +
            options.branch);
        return git.checkout(options.remote, options.branch,
            options.clone);
      })
      .then(function() {
        if (!options.add) {
          log('Removing files');
          return git.rm(only.join(' '), options.clone);
        } else {
          return Q.resolve();
        }
      })
      .then(function() {
        log('Copying files');
        return copy(files, basePath, options.clone);
      })
      .then(function() {
        log('Adding all');
        return git.add('.', options.clone);
      })
      .then(function() {
        if (options.user) {
          return git(['config', 'user.email', options.user.email],
              options.clone)
              .then(function() {
                return git(['config', 'user.name', options.user.name],
                    options.clone);
              });
        } else {
          return Q.resolve();
        }
      })
      .then(function() {
        log('Committing');
        return git.commit(options.message, options.clone);
      })
      .then(function() {
        if (options.tag) {
          log('Tagging');
          var deferred = Q.defer();
          git.tag(options.tag, options.clone)
            .then(function() {
              return deferred.resolve();
            }) ...
```
- example usage
```shell
...

## Basic Usage

'''js
var ghpages = require('gh-pages');
var path = require('path');

ghpages.publish(path.join(__dirname, 'dist'), function(err) { ... });
'''


## 'publish'

'''js
ghpages.publish(basePath, callback);
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

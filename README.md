# api documentation for  [gh-pages (v0.12.0)](https://github.com/tschaub/gh-pages)  [![npm package](https://img.shields.io/npm/v/npmdoc-gh-pages.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gh-pages) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gh-pages.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gh-pages)
#### Publish to a gh-pages branch on GitHub (or any other branch on any other remote)

[![NPM](https://nodei.co/npm/gh-pages.png?downloads=true)](https://www.npmjs.com/package/gh-pages)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gh-pages_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gh-pages/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-gh-pages/build/screen-capture.npmPackageListing.svg)



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
            "name": "tschaub",
            "email": "tim.schaub@gmail.com"
        },
        {
            "name": "markdalgleish",
            "email": "mark.john.dalgleish@gmail.com"
        }
    ],
    "name": "gh-pages",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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
1.  [function <span class="apidocSignatureSpan">gh-pages.</span>git (args, cwd)](#apidoc.element.gh-pages.git)
1.  [function <span class="apidocSignatureSpan">gh-pages.</span>publish (basePath, config, callback)](#apidoc.element.gh-pages.publish)
1.  object <span class="apidocSignatureSpan">gh-pages.</span>util

#### [module gh-pages.git](#apidoc.module.gh-pages.git)
1.  [function <span class="apidocSignatureSpan">gh-pages.</span>git (args, cwd)](#apidoc.element.gh-pages.git.git)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>add (files, cwd)](#apidoc.element.gh-pages.git.add)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>checkout (remote, branch, cwd)](#apidoc.element.gh-pages.git.checkout)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>clean (cwd)](#apidoc.element.gh-pages.git.clean)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>clone (repo, dir, branch, options)](#apidoc.element.gh-pages.git.clone)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>commit (message, cwd)](#apidoc.element.gh-pages.git.commit)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>exe (exe)](#apidoc.element.gh-pages.git.exe)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>fetch (remote, cwd)](#apidoc.element.gh-pages.git.fetch)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>init (cwd)](#apidoc.element.gh-pages.git.init)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>push (remote, branch, cwd)](#apidoc.element.gh-pages.git.push)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>reset (remote, branch, cwd)](#apidoc.element.gh-pages.git.reset)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>rm (files, cwd)](#apidoc.element.gh-pages.git.rm)
1.  [function <span class="apidocSignatureSpan">gh-pages.git.</span>tag (name, cwd)](#apidoc.element.gh-pages.git.tag)

#### [module gh-pages.util](#apidoc.module.gh-pages.util)
1.  [function <span class="apidocSignatureSpan">gh-pages.util.</span>byShortPath (a, b)](#apidoc.element.gh-pages.util.byShortPath)
1.  [function <span class="apidocSignatureSpan">gh-pages.util.</span>copy (files, base, dest)](#apidoc.element.gh-pages.util.copy)
1.  [function <span class="apidocSignatureSpan">gh-pages.util.</span>copyFile (obj, callback)](#apidoc.element.gh-pages.util.copyFile)
1.  [function <span class="apidocSignatureSpan">gh-pages.util.</span>dirsToCreate (files)](#apidoc.element.gh-pages.util.dirsToCreate)
1.  [function <span class="apidocSignatureSpan">gh-pages.util.</span>uniqueDirs (files)](#apidoc.element.gh-pages.util.uniqueDirs)



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

#### <a name="apidoc.element.gh-pages.git"></a>[function <span class="apidocSignatureSpan">gh-pages.</span>git (args, cwd)](#apidoc.element.gh-pages.git)
- description and source-code
```javascript
git = function (args, cwd) {
  return spawn(git, args, cwd);
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



# <a name="apidoc.module.gh-pages.git"></a>[module gh-pages.git](#apidoc.module.gh-pages.git)

#### <a name="apidoc.element.gh-pages.git.git"></a>[function <span class="apidocSignatureSpan">gh-pages.</span>git (args, cwd)](#apidoc.element.gh-pages.git.git)
- description and source-code
```javascript
git = function (args, cwd) {
  return spawn(git, args, cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.add"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>add (files, cwd)](#apidoc.element.gh-pages.git.add)
- description and source-code
```javascript
function add(files, cwd) {
  return spawn(git, ['add', files], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.checkout"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>checkout (remote, branch, cwd)](#apidoc.element.gh-pages.git.checkout)
- description and source-code
```javascript
function checkout(remote, branch, cwd) {
  var treeish = remote + '/' + branch;
  return spawn(git, ['ls-remote', '--exit-code', '.', treeish], cwd)
      .then(function() {
        // branch exists on remote, hard reset
        return spawn(git, ['checkout', branch], cwd)
            .then(function() {
              return clean(cwd);
            })
            .then(function() {
              return reset(remote, branch, cwd);
            });
      }, function(error) {
        if (error instanceof ProcessError && error.code === 2) {
          // branch doesn't exist, create an orphan
          return spawn(git, ['checkout', '--orphan', branch], cwd);
        } else {
          // unhandled error
          return Q.reject(error);
        }
      });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.clean"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>clean (cwd)](#apidoc.element.gh-pages.git.clean)
- description and source-code
```javascript
function clean(cwd) {
  return spawn(git, ['clean', '-f', '-d'], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.clone"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>clone (repo, dir, branch, options)](#apidoc.element.gh-pages.git.clone)
- description and source-code
```javascript
function clone(repo, dir, branch, options) {
  return fs.exists(dir).then(function(exists) {
    if (exists) {
      return Q.resolve();
    } else {
      return fs.makeTree(path.dirname(path.resolve(dir))).then(function() {
        var args = ['clone', repo, dir, '--branch', branch, '--single-branch', '--origin', options.remote];
        if (options.depth) {
          args.push('--depth', options.depth);
        }
        return spawn(git, args).fail(function(err) {
          // try again without banch options
          return spawn(git, ['clone', repo, dir, '--origin', options.remote]);
        });
      });
    }
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.commit"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>commit (message, cwd)](#apidoc.element.gh-pages.git.commit)
- description and source-code
```javascript
function commit(message, cwd) {
  return spawn(git, ['diff-index', '--quiet', 'HEAD', '.'], cwd)
      .then(function() {
        // nothing to commit
        return Q.resolve();
      })
      .fail(function() {
        return spawn(git, ['commit', '-m', message], cwd);
      });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.exe"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>exe (exe)](#apidoc.element.gh-pages.git.exe)
- description and source-code
```javascript
exe = function (exe) {
  git = exe;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.fetch"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>fetch (remote, cwd)](#apidoc.element.gh-pages.git.fetch)
- description and source-code
```javascript
function fetch(remote, cwd) {
  return spawn(git, ['fetch', remote], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.init"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>init (cwd)](#apidoc.element.gh-pages.git.init)
- description and source-code
```javascript
function init(cwd) {
  return spawn(git, ['init'], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.push"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>push (remote, branch, cwd)](#apidoc.element.gh-pages.git.push)
- description and source-code
```javascript
function push(remote, branch, cwd) {
  return spawn(git, ['push', '--tags', remote, branch], cwd);
}
```
- example usage
```shell
...
 * @return {Promise} A promise.
 */
function spawn(exe, args, cwd) {
var deferred = Q.defer();
var child = cp.spawn(exe, args, {cwd: cwd || process.cwd()});
var buffer = [];
child.stderr.on('data', function(chunk) {
  buffer.push(chunk.toString());
});
child.stdout.on('data', function(chunk) {
  deferred.notify(chunk);
});
child.on('close', function(code) {
  if (code) {
    var msg = buffer.join('') || 'Process failed: ' + code;
...
```

#### <a name="apidoc.element.gh-pages.git.reset"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>reset (remote, branch, cwd)](#apidoc.element.gh-pages.git.reset)
- description and source-code
```javascript
function reset(remote, branch, cwd) {
  return spawn(git, ['reset', '--hard', remote + '/' + branch], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.rm"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>rm (files, cwd)](#apidoc.element.gh-pages.git.rm)
- description and source-code
```javascript
function rm(files, cwd) {
  return spawn(git, ['rm', '--ignore-unmatch', '-r', '-f', files], cwd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.git.tag"></a>[function <span class="apidocSignatureSpan">gh-pages.git.</span>tag (name, cwd)](#apidoc.element.gh-pages.git.tag)
- description and source-code
```javascript
function tag(name, cwd) {
  return spawn(git, ['tag', name], cwd);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gh-pages.util"></a>[module gh-pages.util](#apidoc.module.gh-pages.util)

#### <a name="apidoc.element.gh-pages.util.byShortPath"></a>[function <span class="apidocSignatureSpan">gh-pages.util.</span>byShortPath (a, b)](#apidoc.element.gh-pages.util.byShortPath)
- description and source-code
```javascript
byShortPath = function (a, b) {
  var aParts = a.split(path.sep);
  var bParts = b.split(path.sep);
  var aLength = aParts.length;
  var bLength = bParts.length;
  var cmp = 0;
  if (aLength < bLength) {
    cmp = -1;
  } else if (aLength > bLength) {
    cmp = 1;
  } else {
    var aPart, bPart;
    for (var i = 0; i < aLength; ++i) {
      aPart = aParts[i];
      bPart = bParts[i];
      if (aPart < bPart) {
        cmp = -1;
        break;
      } else if (aPart > bPart) {
        cmp = 1;
        break;
      }
    }
  }
  return cmp;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.util.copy"></a>[function <span class="apidocSignatureSpan">gh-pages.util.</span>copy (files, base, dest)](#apidoc.element.gh-pages.util.copy)
- description and source-code
```javascript
copy = function (files, base, dest) {
  var deferred = Q.defer();

  var pairs = [];
  var destFiles = [];
  files.forEach(function(file) {
    var src = path.resolve(base, file);
    var relative = path.relative(base, src);
    var target = path.join(dest, relative);
    pairs.push({
      src: src,
      dest: target
    });
    destFiles.push(target);
  });

  async.eachSeries(dirsToCreate(destFiles), makeDir, function(err) {
    if (err) {
      return deferred.reject(err);
    }
    async.each(pairs, copyFile, function(err) {
      if (err) {
        return deferred.reject(err);
      } else {
        return deferred.resolve();
      }
    });
  });

  return deferred.promise;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.util.copyFile"></a>[function <span class="apidocSignatureSpan">gh-pages.util.</span>copyFile (obj, callback)](#apidoc.element.gh-pages.util.copyFile)
- description and source-code
```javascript
copyFile = function (obj, callback) {
  var called = false;
  function done(err) {
    if (!called) {
      called = true;
      callback(err);
    }
  }

  var read = fs.createReadStream(obj.src);
  read.on('error', function(err) {
    done(err);
  });

  var write = fs.createWriteStream(obj.dest);
  write.on('error', function(err) {
    done(err);
  });
  write.on('close', function(ex) {
    done();
  });

  read.pipe(write);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.util.dirsToCreate"></a>[function <span class="apidocSignatureSpan">gh-pages.util.</span>dirsToCreate (files)](#apidoc.element.gh-pages.util.dirsToCreate)
- description and source-code
```javascript
dirsToCreate = function (files) {
  return uniqueDirs(files).sort(byShortPath);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gh-pages.util.uniqueDirs"></a>[function <span class="apidocSignatureSpan">gh-pages.util.</span>uniqueDirs (files)](#apidoc.element.gh-pages.util.uniqueDirs)
- description and source-code
```javascript
uniqueDirs = function (files) {
  var dirs = {};
  files.forEach(function(filepath) {
    var parts = path.dirname(filepath).split(path.sep);
    var partial = parts[0];
    dirs[partial] = true;
    for (var i = 1, ii = parts.length; i < ii; ++i) {
      partial = path.join(partial, parts[i]);
      dirs[partial] = true;
    }
  });
  return Object.keys(dirs);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

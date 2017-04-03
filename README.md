# api documentation for  [gulp-rsync (v0.0.7)](https://github.com/jerrysu/gulp-rsync)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-rsync.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-rsync) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-rsync.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-rsync)
#### Rsync tasks for deploying gulp file structures

[![NPM](https://nodei.co/npm/gulp-rsync.png?downloads=true)](https://www.npmjs.com/package/gulp-rsync)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-rsync/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-rsync_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-rsync/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-rsync/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-rsync/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jerry Su",
        "email": "email@jerrysu.me"
    },
    "bugs": {
        "url": "https://github.com/jerrysu/gulp-rsync/issues"
    },
    "dependencies": {
        "better-assert": "^1.0.1",
        "gulp-util": "^3.0.0",
        "lodash.every": "^2.4.1",
        "lodash.isstring": "^2.4.1",
        "through2": "^0.6.1"
    },
    "description": "Rsync tasks for deploying gulp file structures",
    "devDependencies": {
        "chai": "^1.9.1",
        "mocha": "^1.21.4"
    },
    "directories": {},
    "dist": {
        "shasum": "745f316892f18bfeeade565ac3889b5a001fe9ba",
        "tarball": "https://registry.npmjs.org/gulp-rsync/-/gulp-rsync-0.0.7.tgz"
    },
    "gitHead": "2adb2e75e82ae9f2b00564dc56c9d6a4fa066c42",
    "homepage": "https://github.com/jerrysu/gulp-rsync",
    "keywords": [
        "gulpplugin",
        "rsync",
        "ssh",
        "deploy",
        "deployment"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ebaskoro",
            "email": "eki@baskoro.org"
        },
        {
            "name": "jerrysu",
            "email": "email@jerrysu.me"
        }
    ],
    "name": "gulp-rsync",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/jerrysu/gulp-rsync.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "0.0.7"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-rsync](#apidoc.module.gulp-rsync)
1.  [function <span class="apidocSignatureSpan">gulp-rsync.</span>rsync (config)](#apidoc.element.gulp-rsync.rsync)
1.  object <span class="apidocSignatureSpan">gulp-rsync.</span>rsync.prototype

#### [module gulp-rsync.rsync](#apidoc.module.gulp-rsync.rsync)
1.  [function <span class="apidocSignatureSpan">gulp-rsync.</span>rsync (config)](#apidoc.element.gulp-rsync.rsync.rsync)

#### [module gulp-rsync.rsync.prototype](#apidoc.module.gulp-rsync.rsync.prototype)
1.  [function <span class="apidocSignatureSpan">gulp-rsync.rsync.prototype.</span>command ()](#apidoc.element.gulp-rsync.rsync.prototype.command)
1.  [function <span class="apidocSignatureSpan">gulp-rsync.rsync.prototype.</span>execute (callback)](#apidoc.element.gulp-rsync.rsync.prototype.execute)



# <a name="apidoc.module.gulp-rsync"></a>[module gulp-rsync](#apidoc.module.gulp-rsync)

#### <a name="apidoc.element.gulp-rsync.rsync"></a>[function <span class="apidocSignatureSpan">gulp-rsync.</span>rsync (config)](#apidoc.element.gulp-rsync.rsync)
- description and source-code
```javascript
function rsync(config) {
  if (!(this instanceof rsync)) {
    return new rsync(config);
  }

  assert(typeof config === 'object');
  assert(!config.options || typeof config.options === 'object');
  this._options = config.options || {};
  var sources = config.source;
  if (!Array.isArray(sources)) {
    sources = [sources];
  }
  assert(sources.length > 0 && every(sources, isString));
  assert(sources.length === 1 || config.destination);
  this._sources = sources;
  assert(!config.destination || typeof config.destination === 'string');
  this._destination = config.destination;
  assert(!config.cwd || typeof config.cwd === 'string');
  this._cwd = config.cwd;
  assert(!config.stdoutHandler || typeof config.stdoutHandler === 'function');
  this._stdout = config.stdoutHandler;
  assert(!config.stderrHandler || typeof config.stderrHandler === 'function');
  this._stderr = config.stderrHandler;

  return this;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gulp-rsync.rsync"></a>[module gulp-rsync.rsync](#apidoc.module.gulp-rsync.rsync)

#### <a name="apidoc.element.gulp-rsync.rsync.rsync"></a>[function <span class="apidocSignatureSpan">gulp-rsync.</span>rsync (config)](#apidoc.element.gulp-rsync.rsync.rsync)
- description and source-code
```javascript
function rsync(config) {
  if (!(this instanceof rsync)) {
    return new rsync(config);
  }

  assert(typeof config === 'object');
  assert(!config.options || typeof config.options === 'object');
  this._options = config.options || {};
  var sources = config.source;
  if (!Array.isArray(sources)) {
    sources = [sources];
  }
  assert(sources.length > 0 && every(sources, isString));
  assert(sources.length === 1 || config.destination);
  this._sources = sources;
  assert(!config.destination || typeof config.destination === 'string');
  this._destination = config.destination;
  assert(!config.cwd || typeof config.cwd === 'string');
  this._cwd = config.cwd;
  assert(!config.stdoutHandler || typeof config.stdoutHandler === 'function');
  this._stdout = config.stdoutHandler;
  assert(!config.stderrHandler || typeof config.stderrHandler === 'function');
  this._stderr = config.stderrHandler;

  return this;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.gulp-rsync.rsync.prototype"></a>[module gulp-rsync.rsync.prototype](#apidoc.module.gulp-rsync.rsync.prototype)

#### <a name="apidoc.element.gulp-rsync.rsync.prototype.command"></a>[function <span class="apidocSignatureSpan">gulp-rsync.rsync.prototype.</span>command ()](#apidoc.element.gulp-rsync.rsync.prototype.command)
- description and source-code
```javascript
command = function () {
  var args = [];

  var shortOptions = [];
  var longOptions = [];

  for (var key in this._options) {
    var value = this._options[key];
    if (typeof value !== 'undefined' && value !== false) {
      if (key.length === 1 && value === true) {
        shortOptions.push(key);
      } else {
        var values = Array.isArray(value) ? value : [value];
        for (var i = 0, l = values.length; i < l; i++) {
          longOptions.push({key: key, value: values[i]});
        }
      }
    }
  }

  if (shortOptions.length > 0) {
    args.push('-' + shortOptions.join(''));
  }

  if (longOptions.length > 0) {
    args = args.concat(longOptions.map(function(option) {
      var single = option.key.length === 1;
      var output = (single ? '-' : '--') + option.key;
      if (typeof option.value !== 'boolean') {
        output += (single ? ' ' : '=') + escapeShellArg(option.value);
      }
      return output;
    }));
  }

  args = args.concat(this._sources.map(escapeShellArg));

  if (this._destination) {
    args.push(escapeShellArg(this._destination));
  }

  return 'rsync ' + args.join(' ');
}
```
- example usage
```shell
...
  args.push(escapeShellArg(this._destination));
}

return 'rsync ' + args.join(' ');
  },

  execute: function(callback) {
var command = this.command();

var childProcess;
if (process.platform === 'win32') {
  childProcess = spawn('cmd.exe', ['/s', '/c', '"' + command + '"'], {
    cwd: this._cwd,
    stdio: [process.stdin, 'pipe', 'pipe'],
    env: process.env,
...
```

#### <a name="apidoc.element.gulp-rsync.rsync.prototype.execute"></a>[function <span class="apidocSignatureSpan">gulp-rsync.rsync.prototype.</span>execute (callback)](#apidoc.element.gulp-rsync.rsync.prototype.execute)
- description and source-code
```javascript
execute = function (callback) {
  var command = this.command();

  var childProcess;
  if (process.platform === 'win32') {
    childProcess = spawn('cmd.exe', ['/s', '/c', '"' + command + '"'], {
      cwd: this._cwd,
      stdio: [process.stdin, 'pipe', 'pipe'],
      env: process.env,
      windowsVerbatimArguments: true
    });
  } else {
    childProcess = spawn('/bin/sh', ['-c', command], {
      cwd: this._cwd,
      stdio: 'pipe',
      env: process.env
    });
  }

  if (this._stdout) {
    childProcess.stdout.on('data', this._stdout);
  }

  if (this._stderr) {
    childProcess.stderr.on('data', this._stderr);
  }

  childProcess.on('close', function(code) {
    var error = null;
    if (code !== 0) {
      error = new Error('rsync exited with code ' + code);
    }

    if (typeof callback === 'function') {
      callback(error, command);
    }
  });

  return childProcess;
}
```
- example usage
```shell
...
  };
  config.stdoutHandler = handler;
  config.stderrHandler = handler;

  gutil.log('gulp-rsync:', 'Starting rsync to ' + destination + '...');
}

rsync(config).execute(function(error, command) {
  if (error) {
    this.emit('error', new PluginError('gulp-rsync', error.stack));
  }
  if (options.command) {
    gutil.log(command);
  }
  if (!options.silent) {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

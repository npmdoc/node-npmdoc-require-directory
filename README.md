# api documentation for  [require-directory (v2.1.1)](https://github.com/troygoode/node-require-directory/)  [![npm package](https://img.shields.io/npm/v/npmdoc-require-directory.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-require-directory) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-require-directory.svg)](https://travis-ci.org/npmdoc/node-npmdoc-require-directory)
#### Recursively iterates over specified directory, require()'ing each file, and returning a nested hash structure containing those modules.

[![NPM](https://nodei.co/npm/require-directory.png?downloads=true)](https://www.npmjs.com/package/require-directory)

[![apidoc](https://npmdoc.github.io/node-npmdoc-require-directory/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-require-directory_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-require-directory/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-require-directory/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-require-directory/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Troy Goode",
        "email": "troygoode@gmail.com",
        "url": "http://github.com/troygoode/"
    },
    "bugs": {
        "url": "http://github.com/troygoode/node-require-directory/issues/"
    },
    "contributors": [
        {
            "name": "Troy Goode",
            "email": "troygoode@gmail.com",
            "url": "http://github.com/troygoode/"
        }
    ],
    "dependencies": {},
    "description": "Recursively iterates over specified directory, require()'ing each file, and returning a nested hash structure containing those modules.",
    "devDependencies": {
        "jshint": "^2.6.0",
        "mocha": "^2.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "8c64ad5fd30dab1c976e2344ffe7f792a6a6df42",
        "tarball": "https://registry.npmjs.org/require-directory/-/require-directory-2.1.1.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "gitHead": "cc71c23dd0c16cefd26855303c16ca1b9b50a36d",
    "homepage": "https://github.com/troygoode/node-require-directory/",
    "keywords": [
        "require",
        "directory",
        "library",
        "recursive"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "troygoode",
            "email": "troygoode@gmail.com"
        }
    ],
    "name": "require-directory",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/troygoode/node-require-directory.git"
    },
    "scripts": {
        "lint": "jshint index.js test/test.js",
        "test": "mocha"
    },
    "version": "2.1.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module require-directory](#apidoc.module.require-directory)
1.  object <span class="apidocSignatureSpan">require-directory.</span>defaults

#### [module require-directory.defaults](#apidoc.module.require-directory.defaults)
1.  boolean <span class="apidocSignatureSpan">require-directory.defaults.</span>recurse
1.  [function <span class="apidocSignatureSpan">require-directory.defaults.</span>rename (name)](#apidoc.element.require-directory.defaults.rename)
1.  [function <span class="apidocSignatureSpan">require-directory.defaults.</span>visit (obj)](#apidoc.element.require-directory.defaults.visit)
1.  object <span class="apidocSignatureSpan">require-directory.defaults.</span>extensions



# <a name="apidoc.module.require-directory"></a>[module require-directory](#apidoc.module.require-directory)



# <a name="apidoc.module.require-directory.defaults"></a>[module require-directory.defaults](#apidoc.module.require-directory.defaults)

#### <a name="apidoc.element.require-directory.defaults.rename"></a>[function <span class="apidocSignatureSpan">require-directory.defaults.</span>rename (name)](#apidoc.element.require-directory.defaults.rename)
- description and source-code
```javascript
rename = function (name) {
  return name;
}
```
- example usage
```shell
...
  obj;

if (fs.statSync(joined).isDirectory() && options.recurse) {
  // this node is a directory; recurse
  files = requireDirectory(m, joined, options);
  // exclude empty directories
  if (Object.keys(files).length) {
    retval[options.rename(filename, joined, filename)] = files;
  }
} else {
  if (joined !== m.filename && checkFileInclusion(joined, filename, options)) {
    // hash node key shouldn't include file extension
    key = filename.substring(0, filename.lastIndexOf('.'));
    obj = m.require(joined);
    retval[options.rename(key, joined, filename)] = options.visit(obj, joined, filename) || obj;
...
```

#### <a name="apidoc.element.require-directory.defaults.visit"></a>[function <span class="apidocSignatureSpan">require-directory.defaults.</span>visit (obj)](#apidoc.element.require-directory.defaults.visit)
- description and source-code
```javascript
visit = function (obj) {
  return obj;
}
```
- example usage
```shell
...
        retval[options.rename(filename, joined, filename)] = files;
      }
    } else {
      if (joined !== m.filename && checkFileInclusion(joined, filename, options)) {
        // hash node key shouldn't include file extension
        key = filename.substring(0, filename.lastIndexOf('.'));
        obj = m.require(joined);
        retval[options.rename(key, joined, filename)] = options.visit(obj, joined, filename) || obj;
      }
    }
  });

  return retval;
}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

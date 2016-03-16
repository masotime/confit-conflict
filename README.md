"Test" project to demonstrate some inconsistent behavior in npm 3.x.

Reproduced under node 4.4.0 and npm 3.8.1

* `npm run test` will fail
* `npm run test2` will succeed.

# some details

When `babel-runtime` 5.x is defined as part of `devDependencies`, which is an explicit dependency of `confit` but using 4.x:

* npm 3.x will override the explicit dependency of the `confit` module
* npm 2.x doesn't have this issue

However, if you run `npm i` a second time, it will install the missing dependency.

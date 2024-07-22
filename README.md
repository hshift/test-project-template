# test-project-template
Template repository for creating new C project that needs to be tested

## Test Driven Development
This template is designed with Test Driven Development (TDD) in mind. For this
git repo CppUTest project is added as a submodule. Sub-dir Test contains this
unit testing framework as well as tests, mocks an etc. for the code.

So, if you are cloning it fresh you might wanna issue
`git submodule update --init`

### Installing CppUTest
To compile CppUTest you need following packages. Find them on your distro or
platform and install them:

`gcc g++ make git autoreconf libtool`

To compile CppUTest issue following:
```C
cd Test/cpputest
./autogen.sh
./configure
make
```

As as result there should be two files in `\lib` folder `libCppUTest.a` and  `libCppUTestExt.a`

### If git is complaining that submodule is "dirty"
```bash
git config --global diff.ignoreSubmodules dirty
```

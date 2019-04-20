# Contributing to sharp

Hello, thank you for your interest in helping!

## Submit a new bug report

Please create a [new issue](https://github.com/lovell/sharp/issues/new) containing the steps to reproduce the problem.

If you're having installation problems, please include the output of running `npm install --verbose sharp`.

New bugs are assigned a `triage` label whilst under investigation.

## Submit a new feature request

If a [similar request](https://github.com/lovell/sharp/labels/enhancement) exists,
it's probably fastest to add a comment to it about your requirement.

Implementation is usually straightforward if libvips
[already supports](https://libvips.github.io/libvips/API/current/func-list.html)
the feature you need.

## Submit a Pull Request to fix a bug

Thank you! To prevent the problem occurring again, please add unit tests that would have failed.

Please select the `master` branch as the destination for your Pull Request so your fix can be included in the next minor release.

Please squash your changes into a single commit using a command like `git rebase -i upstream/master`.

To test C++ changes, you can compile the module using `npm install` and then run the tests using `npm test`.

## Submit a Pull Request with a new feature

Please add JavaScript [unit tests](https://github.com/lovell/sharp/tree/master/test/unit) to cover your new feature.
A test coverage report for the JavaScript code is generated in the `coverage/lcov-report` directory.

Where possible, the functional tests use gradient-based perceptual hashes
based on [dHash](http://www.hackerfactor.com/blog/index.php?/archives/529-Kind-of-Like-That.html)
to compare expected vs actual images.

You deserve to add your details to the [list of contributors](https://github.com/lovell/sharp/blob/master/package.json#L5).

Any change that modifies the existing public API should be added to the relevant work-in-progress branch for inclusion in the next major release.

| Release | WIP branch |
| ------: | :--------- |
| v0.23.0 | vision     |
| v0.24.0 | wit        |

Please squash your changes into a single commit using a command like `git rebase -i upstream/<wip-branch>`.

### Add a new public method

The API tries to be as fluent as possible.
Image processing concepts follow the naming conventions from libvips and, to a lesser extent, ImageMagick.

Most methods have optional parameters and assume sensible defaults.
Please ensure backwards compatibility where possible.

Feel free to create a [new issue](https://github.com/lovell/sharp/issues/new) to gather feedback on a potential API change.

### Remove an existing public method

A method to be removed should be deprecated in the next major version then removed in the following major version.

By way of example, the `background()` method present in v0.20.0 was deprecated in v0.21.0 and removed in v0.22.0.

## Documentation

The public API is documented with [JSDoc](http://usejsdoc.org/) annotated comments.

These can be converted to Markdown by running:
```sh
npm run docs
```

Please include documentation updates in any Pull Request that modifies the public API.

## Run the tests

### Functional tests and static code analysis

```sh
npm test
```

### Memory leak tests

Requires [Valgrind](http://valgrind.org/).

```sh
npm run test-leak
```

## Finally

Please feel free to ask any questions via a
[new issue](https://github.com/lovell/sharp/issues/new).

If you're unable to post details publicly, please
[e-mail](https://github.com/lovell/sharp/blob/master/package.json#L4)
for private, paid consulting.
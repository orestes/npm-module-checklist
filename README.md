# npm-module-checklist
> Steps to check when starting, working and publishing a module to NPM

You can add the included [CHECKLIST.md](CHECKLIST.md) into your project,
or copy it into your README.md; then check items off as you go.
Use one of the two badges to let everyone know your module is solid.

[![npm checklist badge](https://img.shields.io/badge/follows-npm%20checklist-brightgreen.svg)](CHECKLIST.md)
[![badge alternate](https://img.shields.io/badge/%E2%98%B0-%E2%9C%93-brightgreen.svg)](CHECKLIST.md)

```
[![badge 1](https://img.shields.io/badge/follows-npm%20checklist-brightgreen.svg)](CHECKLIST.md)
[![badge 2](https://img.shields.io/badge/%E2%98%B0-%E2%9C%93-brightgreen.svg)](CHECKLIST.md)
```
Example: [manpm](https://github.com/bahmutov/manpm)

## Checklist

- [ ] watch the [egghead.io](https://egghead.io) series [How to Write an Open Source JavaScript Library](https://egghead.io/series/how-to-write-an-open-source-javascript-library);
it is extremely useful for any NPM project (OSS or closed-sourced).
- [ ] start unit testing right away, [pick your unit testing framework](http://glebbahmutov.com/blog/picking-javascript-testing-framework/)
- [ ] start linting code to prevent obvious problems, like misspelled variable.
[eslint](http://eslint.org/), [jshint](http://jshint.com/docs/), [jscs](http://jscs.info/) or all of them together
[gulp-lint-everything](https://github.com/bahmutov/gulp-lint-everything)
- [ ] run linting and unit tests on each commit locally. [pre-git](https://github.com/bahmutov/pre-git), [ghooks](https://www.npmjs.com/package/ghooks) and use [ban-sensitive-files](http://npm.im/ban-sensitive-files) to avoid committing sensative files (like private keys).
- [ ] use code quality as a service tool to fight creeping code complexity. [Codacy](https://codacy.com/),
[CodeClimate](https://codeclimate.com/), [BitHound](https://www.bithound.io/)
- [ ] validate commit message using [pre-git](https://github.com/bahmutov/pre-git) or [commitizen](https://www.npmjs.com/package/commitizen) with [validate-commit-msg](https://www.npmjs.com/package/validate-commit-msg). This
enables other tools, like intelligent release notes.
- [ ] use logging library to show more information during debugging or verbose mode.
[debug](https://github.com/visionmedia/debug), [logdown](https://github.com/caiogondim/logdown)
- [ ] show the project&#39;s GitHub open issues on demand or on commit using [git-issues](https://www.npmjs.com/package/git-issues)
- [ ] setup continuous integration server, like [TravisCI](https://travis-ci.org/) or [CircleCI](https://circleci.com/) (or wait until you set up [semantic-release](https://github.com/semantic-release/semantic-release) which will set up [TravisCI](https://travis-ci.org/) for you).
- [ ] [add badges](http://glebbahmutov.com/blog/tightening-node-project/) to the README to make broken unit tests or out of date dependencies visible
 - ci server badge
 - published NPM package info [NodeICO](https://nodei.co/)
 - production and dev dependencies being out of date [david-dm](https://david-dm.org/)
 - semantic release badge
 - code quality badges
 - insecure code or dependencies
- [ ] check module published size and white list only necessary files, [tutorial](http://glebbahmutov.com/blog/smaller-published-NPM-modules/)
- [ ] setup [semantic-release](https://github.com/semantic-release/semantic-release) to automate publishing
and avoid breaking [semver](http://semver.org/). This is [important](https://medium.com/javascript-scene/software-versions-are-broken-3d2dc0da0783#.h96ppopx3),
but is currently [broken](https://www.youtube.com/watch?v=tc2UgG5L7WM) in too many projects. Even this checklist is using semver!
- [ ] avoid surprizes by using exact versions of the top level dependencies.
Use [save-exact](https://docs.npmjs.com/misc/config#save-exact) NPM setting and [exact-semver](https://github.com/bahmutov/exact-semver) to enforce it.
- [ ] setup a script to reliably update out of date dependencies using [next-update](https://github.com/bahmutov/next-update#install)
 - [ ] setup automatic pull requests when newer versions of dependencies appear [greenkeeper.io](http://greenkeeper.io/)
- [ ] if writing a CLI tool, add a way to check if it is out of date and should be upgraded;
[update-notifier](https://github.com/yeoman/update-notifier)
- [ ] scan dependencies and code for known security vulnerabilities. [snyk](https://www.npmjs.com/package/snyk), [NodeSecurity](https://nodesecurity.io/)
- [ ] catch missing or invalid `package.json` values using [grunt-nice-package](https://github.com/bahmutov/grunt-nice-package)
or [fixpack](https://github.com/henrikjoreteg/fixpack)
- [ ] write simple installation commands for your module
- [ ] write &quot;quick intro&quot; example showing the main feature of your module
- [ ] add your example as metadata on your `package.json` so it shows on [Tonic](https://tonicdev.uservoice.com/knowledgebase/articles/765846-how-do-i-customize-the-example-for-my-npm-package)
- [ ] add CONTRIBUTING.md file with clear guidelines how others can add new features or fix bugs
in your module. [Atom editor](https://github.com/atom/atom/blob/master/CONTRIBUTING.md) and [lodash](https://github.com/lodash/lodash/blob/master/CONTRIBUTING.md) have excellent examples to follow.
When GitHub finds a CONTRIBUTING.md file it [shows a message](https://gipthub.com/blog/1184-contributing-guidelines) to anyone opening an issue.
- [ ] generate documentation automatically. [xplain](https://github.com/bahmutov/xplain) is my own tool for JS to HTML/Markdown
generation
- [ ] place most of the public API documentation in README file for simple retrieval.
This allows other developers to find relevant sections right from the command line [manpm](https://github.com/bahmutov/manpm)
or by looking up `npm home package-name`
- [ ] use a library to output the correct plural forms of words in the user messages [pluralize](https://github.com/blakeembrey/pluralize)

Source: [npm-module-checklist](https://github.com/bahmutov/npm-module-checklist)

## Advanced
If you include the separate checklist file, you can automatically insert / update it inside the README.
Setup the markdown update as a step in your build process using [update-markdown](https://github.com/bahmutov/update-markdown).

## Contributing
Everyone is welcome to submit pull requests with new content.
I just ask to check before submitting a new content that:


- it is not covered by an item that already is in the list.
- if there is an [open issue](https://github.com/bahmutov/npm-module-checklist/issues),
please reference it in your commit message.
You can even check the list of issues from command line before committing `npm run issues`.
- has links to an explanation *why it is a good idea* and tools that help accomplish it.
- Make sure to run `npm run build` once to update the checklist inside README.md

## Contributors

- Kent C. Dodds [@kentcdodds](https://github.com/kentcdodds)
- Gleb Bahmutov [@bahmutov](https://github.com/bahmutov)

### Small print
Author: Gleb Bahmutov &copy; 2015


- [@bahmutov](https://twitter.com/bahmutov)
- [glebbahmutov.com](http://glebbahmutov.com)
- [blog](http://glebbahmutov.com/blog/)

License: MIT - do anything with the code, but don&#39;t blame me if it does not work.

Spread the word: tweet, star on github, etc.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/npm-module-checklist/issues) on Github


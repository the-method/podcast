# Contributing to The Method

 * What file formats do we use?
 * What types of media do we accept?
 * How to contribute: step-by-step (phone & voice memo & What's App)
 * Language (layterms? time limit)
 * Who is the audience? Level of language? Educated non-specialist!
    * Examples of good language / tone + less good
* How to request an interview / give feedback
    * Email address + an issue 
* Transcription
    * How to transcribe audio contributions
        * Open an issue - Transcribe Episode 3 - someone says to do it
        * 

        * 

#### Table Of Contents

[What should I know before I get started?](#what-should-i-know-before-i-get-started)
  * [Code of Conduct](#code-of-conduct)

[How Can I Contribute?](#how-can-i-contribute)
  * [Contribute audio content](#contribute-audio-content)
  * [Contribute text content](#contribute-text-content)
  * [Transcribe audio](#transcribe-audio)
  * [Recommend someone to interview or review](#recommend-someone-to-interview-or-review)
  * [Contribute code, design, or functionality](#contribute-code,-design,-or-functionality)

[Styleguides](#styleguides)
  * [Contribute audio content](#git-commit-messages)
  * [JavaScript Styleguide](#javascript-styleguide)
  * [CoffeeScript Styleguide](#coffeescript-styleguide)
  * [Specs Styleguide](#specs-styleguide)
  * [Documentation Styleguide](#documentation-styleguide)

[Additional Notes](#additional-notes)
  * [Issue and Pull Request Labels](#issue-and-pull-request-labels)

## What should I know before I get started?

### Code of Conduct

This project adheres to the Contributor Covenant [code of conduct](CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code.
Please report unacceptable behavior to [contact.the.method@gmail.com](mailto:contact.the.method@gmail.com).

## How can I contribute?

### Contribute audio content

### Contribute text content

### Transcribe audio

### Recommend someone to interview or review

### Contribute code, design, or functionality

#### Pull requests

* Fill in [the required template](PULL_REQUEST_TEMPLATE.md)
* Include screenshots and animated GIFs in your pull request whenever possible.
* Follow the [JavaScript](#javascript-styleguide) and [CoffeeScript](#coffeescript-styleguide) styleguides.
* Include thoughtfully-worded, well-structured
  [Jasmine](http://jasmine.github.io/) specs in the `./spec` folder. Run them using `apm test`. See the [Specs Styleguide](#specs-styleguide) below.
* Document new code based on the
  [Documentation Styleguide](#documentation-styleguide)
* End files with a newline.
* Place requires in the following order:
    * Built in Node Modules (such as `path`)
    * Built in Atom and Electron Modules (such as `atom`, `remote`)
    * Local Modules (using relative paths)
* Place class properties in the following order:
    * Class methods and properties (methods starting with a `@`)
    * Instance methods and properties
* [Avoid platform-dependent code](http://flight-manual.atom.io/hacking-atom/sections/cross-platform-compatibility/)
* Using a plain `return` when returning explicitly at the end of a function.
    * Not `return null`, `return undefined`, `null`, or `undefined`

## Styleguides

### Git Commit Messages

* Use the present tense ("Add feature" not "Added feature")
* Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
* Limit the first line to 72 characters or less
* Reference issues and pull requests liberally
* When only changing documentation, include `[ci skip]` in the commit description
* Consider starting the commit message with an applicable emoji:
    * :art: `:art:` when improving the format/structure of the code
    * :racehorse: `:racehorse:` when improving performance
    * :non-potable_water: `:non-potable_water:` when plugging memory leaks
    * :memo: `:memo:` when writing docs
    * :penguin: `:penguin:` when fixing something on Linux
    * :apple: `:apple:` when fixing something on macOS
    * :checkered_flag: `:checkered_flag:` when fixing something on Windows
    * :bug: `:bug:` when fixing a bug
    * :fire: `:fire:` when removing code or files
    * :green_heart: `:green_heart:` when fixing the CI build
    * :white_check_mark: `:white_check_mark:` when adding tests
    * :lock: `:lock:` when dealing with security
    * :arrow_up: `:arrow_up:` when upgrading dependencies
    * :arrow_down: `:arrow_down:` when downgrading dependencies
    * :shirt: `:shirt:` when removing linter warnings

### JavaScript Styleguide

All JavaScript must adhere to [JavaScript Standard Style](http://standardjs.com/).

* Prefer the object spread operator (`{...anotherObj}`) to `Object.assign()`
* Inline `export`s with expressions whenever possible
  ```js
  // Use this:
  export default class ClassName {

  }

  // Instead of:
  class ClassName {

  }
  export default ClassName
  ```

### CoffeeScript Styleguide

* Set parameter defaults without spaces around the equal sign
    * `clear = (count=1) ->` instead of `clear = (count = 1) ->`
* Use spaces around operators
    * `count + 1` instead of `count+1`
* Use spaces after commas (unless separated by newlines)
* Use parentheses if it improves code clarity.
* Prefer alphabetic keywords to symbolic keywords:
    * `a is b` instead of `a == b`
* Avoid spaces inside the curly-braces of hash literals:
    * `{a: 1, b: 2}` instead of `{ a: 1, b: 2 }`
* Include a single line of whitespace between methods.
* Capitalize initialisms and acronyms in names, except for the first word, which
  should be lower-case:
  * `getURI` instead of `getUri`
  * `uriToOpen` instead of `URIToOpen`
* Use `slice()` to copy an array
* Add an explicit `return` when your function ends with a `for`/`while` loop and
  you don't want it to return a collected array.
* Use `this` instead of a standalone `@`
  * `return this` instead of `return @`

### Specs Styleguide

- Include thoughtfully-worded, well-structured
  [Jasmine](http://jasmine.github.io/) specs in the `./spec` folder.
- treat `describe` as a noun or situation.
- treat `it` as a statement about state or how an operation changes state.

#### Example

```coffee
describe 'a dog', ->
 it 'barks', ->
 # spec here
 describe 'when the dog is happy', ->
  it 'wags its tail', ->
  # spec here
```

### Documentation Styleguide

* Use [AtomDoc](https://github.com/atom/atomdoc).
* Use [Markdown](https://daringfireball.net/projects/markdown).
* Reference methods and classes in markdown with the custom `{}` notation:
    * Reference classes with `{ClassName}`
    * Reference instance methods with `{ClassName::methodName}`
    * Reference class methods with `{ClassName.methodName}`

#### Example

```coffee
# Public: Disable the package with the given name.
#
# * `name`    The {String} name of the package to disable.
# * `options` (optional) The {Object} with disable options (default: {}):
#   * `trackTime`     A {Boolean}, `true` to track the amount of time taken.
#   * `ignoreErrors`  A {Boolean}, `true` to catch and ignore errors thrown.
# * `callback` The {Function} to call after the package has been disabled.
#
# Returns `undefined`.
disablePackage: (name, options, callback) ->
```

## Additional Notes

### Issue and Pull Request Labels

This section lists the labels we use to help us track and manage issues and pull requests. Most labels are used across all Atom repositories, but some are specific to `atom/atom`.

[GitHub search](https://help.github.com/articles/searching-issues/) makes it easy to use labels for finding groups of issues or pull requests you're interested in. For example, you might be interested in [open issues across `atom/atom` and all Atom-owned packages which are labeled as bugs, but still need to be reliably reproduced](https://github.com/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Abug+label%3Aneeds-reproduction) or perhaps [open pull requests in `atom/atom` which haven't been reviewed yet](https://github.com/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+comments%3A0). To help you find issues and pull requests, each label is listed with search links for finding open items with that label in `atom/atom` only and also across all Atom repositories. We  encourage you to read about [other search filters](https://help.github.com/articles/searching-issues/) which will help you write more focused queries.

The labels are loosely grouped by their purpose, but it's not required that every issue have a label from every group or that an issue can't have more than one label from the same group.

Please open an issue on `atom/atom` if you have suggestions for new labels, and if you notice some labels are missing on some repositories, then please open an issue on that repository.

#### Type of Issue and Issue State

| Label name | `atom/atom` :mag_right: | `atom`‑org :mag_right: | Description |
| --- | --- | --- | --- |
| `enhancement` | [search][search-atom-repo-label-enhancement] | [search][search-atom-org-label-enhancement] | Feature requests. |
| `bug` | [search][search-atom-repo-label-bug] | [search][search-atom-org-label-bug] | Confirmed bugs or reports that are very likely to be bugs. |
| `question` | [search][search-atom-repo-label-question] | [search][search-atom-org-label-question] | Questions more than bug reports or feature requests (e.g. how do I do X). |
| `feedback` | [search][search-atom-repo-label-feedback] | [search][search-atom-org-label-feedback] | General feedback more than bug reports or feature requests. |
| `help-wanted` | [search][search-atom-repo-label-help-wanted] | [search][search-atom-org-label-help-wanted] | The Atom core team would appreciate help from the community in resolving these issues. |
| `beginner` | [search][search-atom-repo-label-beginner] | [search][search-atom-org-label-beginner] | Less complex issues which would be good first issues to work on for users who want to contribute to Atom. |
| `more-information-needed` | [search][search-atom-repo-label-more-information-needed] | [search][search-atom-org-label-more-information-needed] | More information needs to be collected about these problems or feature requests (e.g. steps to reproduce). |
| `needs-reproduction` | [search][search-atom-repo-label-needs-reproduction] | [search][search-atom-org-label-needs-reproduction] | Likely bugs, but haven't been reliably reproduced. |
| `blocked` | [search][search-atom-repo-label-blocked] | [search][search-atom-org-label-blocked] | Issues blocked on other issues. |
| `duplicate` | [search][search-atom-repo-label-duplicate] | [search][search-atom-org-label-duplicate] | Issues which are duplicates of other issues, i.e. they have been reported before. |
| `wontfix` | [search][search-atom-repo-label-wontfix] | [search][search-atom-org-label-wontfix] | The Atom core team has decided not to fix these issues for now, either because they're working as intended or for some other reason. |
| `invalid` | [search][search-atom-repo-label-invalid] | [search][search-atom-org-label-invalid] | Issues which aren't valid (e.g. user errors). |
| `package-idea` | [search][search-atom-repo-label-package-idea] | [search][search-atom-org-label-package-idea] | Feature request which might be good candidates for new packages, instead of extending Atom or core Atom packages. |
| `wrong-repo` | [search][search-atom-repo-label-wrong-repo] | [search][search-atom-org-label-wrong-repo] | Issues reported on the wrong repository (e.g. a bug related to the [Settings View package](https://github.com/atom/settings-view) was reported on [Atom core](https://github.com/atom/atom)). |

#### Topic Categories

| Label name | `atom/atom` :mag_right: | `atom`‑org :mag_right: | Description |
| --- | --- | --- | --- |
| `windows` | [search][search-atom-repo-label-windows] | [search][search-atom-org-label-windows] | Related to Atom running on Windows. |
| `linux` | [search][search-atom-repo-label-linux] | [search][search-atom-org-label-linux] | Related to Atom running on Linux. |
| `mac` | [search][search-atom-repo-label-mac] | [search][search-atom-org-label-mac] | Related to Atom running on macOS. |
| `documentation` | [search][search-atom-repo-label-documentation] | [search][search-atom-org-label-documentation] | Related to any type of documentation (e.g. [API documentation](https://atom.io/docs/api/latest/) and the [flight manual](http://flight-manual.atom.io/)). |
| `performance` | [search][search-atom-repo-label-performance] | [search][search-atom-org-label-performance] | Related to performance. |
| `security` | [search][search-atom-repo-label-security] | [search][search-atom-org-label-security] | Related to security. |
| `ui` | [search][search-atom-repo-label-ui] | [search][search-atom-org-label-ui] | Related to visual design. |
| `api` | [search][search-atom-repo-label-api] | [search][search-atom-org-label-api] | Related to Atom's public APIs. |
| `uncaught-exception` | [search][search-atom-repo-label-uncaught-exception] | [search][search-atom-org-label-uncaught-exception] | Issues about uncaught exceptions, normally created from the [Notifications package](https://github.com/atom/notifications). |
| `crash` | [search][search-atom-repo-label-crash] | [search][search-atom-org-label-crash] | Reports of Atom completely crashing. |
| `auto-indent` | [search][search-atom-repo-label-auto-indent] | [search][search-atom-org-label-auto-indent] | Related to auto-indenting text. |
| `encoding` | [search][search-atom-repo-label-encoding] | [search][search-atom-org-label-encoding] | Related to character encoding. |
| `network` | [search][search-atom-repo-label-network] | [search][search-atom-org-label-network] | Related to network problems or working with remote files (e.g. on network drives). |
| `git` | [search][search-atom-repo-label-git] | [search][search-atom-org-label-git] | Related to Git functionality (e.g. problems with gitignore files or with showing the correct file status). |

#### `atom/atom` Topic Categories

| Label name | `atom/atom` :mag_right: | `atom`‑org :mag_right: | Description |
| --- | --- | --- | --- |
| `editor-rendering` | [search][search-atom-repo-label-editor-rendering] | [search][search-atom-org-label-editor-rendering] | Related to language-independent aspects of rendering text (e.g. scrolling, soft wrap, and font rendering). |
| `build-error` | [search][search-atom-repo-label-build-error] | [search][search-atom-org-label-build-error] | Related to problems with building Atom from source. |
| `error-from-pathwatcher` | [search][search-atom-repo-label-error-from-pathwatcher] | [search][search-atom-org-label-error-from-pathwatcher] | Related to errors thrown by the [pathwatcher library](https://github.com/atom/node-pathwatcher). |
| `error-from-save` | [search][search-atom-repo-label-error-from-save] | [search][search-atom-org-label-error-from-save] | Related to errors thrown when saving files. |
| `error-from-open` | [search][search-atom-repo-label-error-from-open] | [search][search-atom-org-label-error-from-open] | Related to errors thrown when opening files. |
| `installer` | [search][search-atom-repo-label-installer] | [search][search-atom-org-label-installer] | Related to the Atom installers for different OSes. |
| `auto-updater` | [search][search-atom-repo-label-auto-updater] | [search][search-atom-org-label-auto-updater] | Related to the auto-updater for different OSes. |
| `deprecation-help` | [search][search-atom-repo-label-deprecation-help] | [search][search-atom-org-label-deprecation-help] | Issues for helping package authors remove usage of deprecated APIs in packages. |
| `electron` | [search][search-atom-repo-label-electron] | [search][search-atom-org-label-electron] | Issues that require changes to [Electron](https://electron.atom.io) to fix or implement. |

#### Pull Request Labels

| Label name | `atom/atom` :mag_right: | `atom`‑org :mag_right: | Description
| --- | --- | --- | --- |
| `work-in-progress` | [search][search-atom-repo-label-work-in-progress] | [search][search-atom-org-label-work-in-progress] | Pull requests which are still being worked on, more changes will follow. |
| `needs-review` | [search][search-atom-repo-label-needs-review] | [search][search-atom-org-label-needs-review] | Pull requests which need code review, and approval from maintainers or Atom core team. |
| `under-review` | [search][search-atom-repo-label-under-review] | [search][search-atom-org-label-under-review] | Pull requests being reviewed by maintainers or Atom core team. |
| `requires-changes` | [search][search-atom-repo-label-requires-changes] | [search][search-atom-org-label-requires-changes] | Pull requests which need to be updated based on review comments and then reviewed again. |
| `needs-testing` | [search][search-atom-repo-label-needs-testing] | [search][search-atom-org-label-needs-testing] | Pull requests which need manual testing. |

[search-atom-repo-label-enhancement]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aenhancement
[search-atom-org-label-enhancement]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aenhancement
[search-atom-repo-label-bug]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Abug
[search-atom-org-label-bug]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Abug
[search-atom-repo-label-question]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aquestion
[search-atom-org-label-question]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aquestion
[search-atom-repo-label-feedback]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Afeedback
[search-atom-org-label-feedback]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Afeedback
[search-atom-repo-label-help-wanted]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Ahelp-wanted
[search-atom-org-label-help-wanted]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Ahelp-wanted
[search-atom-repo-label-beginner]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Abeginner
[search-atom-org-label-beginner]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Abeginner
[search-atom-repo-label-more-information-needed]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Amore-information-needed
[search-atom-org-label-more-information-needed]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Amore-information-needed
[search-atom-repo-label-needs-reproduction]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aneeds-reproduction
[search-atom-org-label-needs-reproduction]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aneeds-reproduction
[search-atom-repo-label-triage-help-needed]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Atriage-help-needed
[search-atom-org-label-triage-help-needed]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Atriage-help-needed
[search-atom-repo-label-windows]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Awindows
[search-atom-org-label-windows]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Awindows
[search-atom-repo-label-linux]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Alinux
[search-atom-org-label-linux]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Alinux
[search-atom-repo-label-mac]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Amac
[search-atom-org-label-mac]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Amac
[search-atom-repo-label-documentation]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Adocumentation
[search-atom-org-label-documentation]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Adocumentation
[search-atom-repo-label-performance]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aperformance
[search-atom-org-label-performance]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aperformance
[search-atom-repo-label-security]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Asecurity
[search-atom-org-label-security]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Asecurity
[search-atom-repo-label-ui]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aui
[search-atom-org-label-ui]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aui
[search-atom-repo-label-api]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aapi
[search-atom-org-label-api]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aapi
[search-atom-repo-label-crash]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Acrash
[search-atom-org-label-crash]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Acrash
[search-atom-repo-label-auto-indent]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aauto-indent
[search-atom-org-label-auto-indent]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aauto-indent
[search-atom-repo-label-encoding]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aencoding
[search-atom-org-label-encoding]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aencoding
[search-atom-repo-label-network]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Anetwork
[search-atom-org-label-network]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Anetwork
[search-atom-repo-label-uncaught-exception]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Auncaught-exception
[search-atom-org-label-uncaught-exception]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Auncaught-exception
[search-atom-repo-label-git]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Agit
[search-atom-org-label-git]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Agit
[search-atom-repo-label-blocked]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Ablocked
[search-atom-org-label-blocked]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Ablocked
[search-atom-repo-label-duplicate]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aduplicate
[search-atom-org-label-duplicate]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aduplicate
[search-atom-repo-label-wontfix]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Awontfix
[search-atom-org-label-wontfix]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Awontfix
[search-atom-repo-label-invalid]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Ainvalid
[search-atom-org-label-invalid]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Ainvalid
[search-atom-repo-label-package-idea]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Apackage-idea
[search-atom-org-label-package-idea]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Apackage-idea
[search-atom-repo-label-wrong-repo]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Awrong-repo
[search-atom-org-label-wrong-repo]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Awrong-repo
[search-atom-repo-label-editor-rendering]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aeditor-rendering
[search-atom-org-label-editor-rendering]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aeditor-rendering
[search-atom-repo-label-build-error]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Abuild-error
[search-atom-org-label-build-error]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Abuild-error
[search-atom-repo-label-error-from-pathwatcher]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aerror-from-pathwatcher
[search-atom-org-label-error-from-pathwatcher]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aerror-from-pathwatcher
[search-atom-repo-label-error-from-save]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aerror-from-save
[search-atom-org-label-error-from-save]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aerror-from-save
[search-atom-repo-label-error-from-open]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aerror-from-open
[search-atom-org-label-error-from-open]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aerror-from-open
[search-atom-repo-label-installer]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Ainstaller
[search-atom-org-label-installer]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Ainstaller
[search-atom-repo-label-auto-updater]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Aauto-updater
[search-atom-org-label-auto-updater]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aauto-updater
[search-atom-repo-label-deprecation-help]: https://github.com/issues?q=is%3Aopen+is%3Aissue+repo%3Aatom%2Fatom+label%3Adeprecation-help
[search-atom-org-label-deprecation-help]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Adeprecation-help
[search-atom-repo-label-electron]: https://github.com/issues?q=is%3Aissue+repo%3Aatom%2Fatom+is%3Aopen+label%3Aelectron
[search-atom-org-label-electron]: https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3Aatom+label%3Aelectron
[search-atom-repo-label-work-in-progress]: https://github.com/pulls?q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+label%3Awork-in-progress
[search-atom-org-label-work-in-progress]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3Aatom+label%3Awork-in-progress
[search-atom-repo-label-needs-review]: https://github.com/pulls?q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+label%3Aneeds-review
[search-atom-org-label-needs-review]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3Aatom+label%3Aneeds-review
[search-atom-repo-label-under-review]: https://github.com/pulls?q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+label%3Aunder-review
[search-atom-org-label-under-review]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3Aatom+label%3Aunder-review
[search-atom-repo-label-requires-changes]: https://github.com/pulls?q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+label%3Arequires-changes
[search-atom-org-label-requires-changes]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3Aatom+label%3Arequires-changes
[search-atom-repo-label-needs-testing]: https://github.com/pulls?q=is%3Aopen+is%3Apr+repo%3Aatom%2Fatom+label%3Aneeds-testing
[search-atom-org-label-needs-testing]: https://github.com/pulls?q=is%3Aopen+is%3Apr+user%3Aatom+label%3Aneeds-testing

[beginner]:https://github.com/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+label%3Abeginner+label%3Ahelp-wanted+user%3Aatom+sort%3Acomments-desc
[help-wanted]:https://github.com/issues?q=is%3Aopen+is%3Aissue+label%3Ahelp-wanted+user%3Aatom+sort%3Acomments-desc+-label%3Abeginner

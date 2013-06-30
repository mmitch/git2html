git2html
========


## About

`git2html` is used to render a single file's changelog from git to static HTML files.
I wrote it to do some code review on small Perl scripts.
Current status is "works for me", git2html is propably not the right tool to track changes within 2000+ lines of code :)

## Invocation

    git2html [-h|--help] [-o <output directory>] [-c <charset>] [-t <tabwidth>] <sourcefile>

`<sourcefile>` must be part of a non-bare local git repository.
This file's changelog will be converted to HTML over all available branches.

The generated files will be created in the `output directory` (`./out`
by default) relative to your current working directory.
**BEWARE:** This directory and all it's contents will be silently overwritten!

The `charset` will be used in the HTML charset meta header.  Default is `utf-8`.

The `tabwidth` will be used to expand tabs in the source file.  Default is `8`.

## Example

This [live demo](http://www.cgarbs.de/stuff/git2html-test/) is generated nightly from the
[git2html-test](https://github.com/mmitch/git2html-test/) demo repository
using the most current version of `git2html`.

## Prerequisites

The following Perl modules are needed:

* `Algorithm::Diff`
* `Cwd` (should be part of Perl base install)
* `File::Path` (should be part of Perl base install)
* `HTML::Entities`

The following executables are needed:

* `git` (obviously)
* `expand` from coreutils

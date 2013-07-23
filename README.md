git2html
========

## About

`git2html` is used to render a single file's changelog from git to static HTML files.
I wrote it to do some code reviews on small Perl scripts.
Current status is "works for me".
`git2html` is propably not the right tool to track changes within 2000+ lines of code :)

## Copyright

git2html - render a single file's changelog from git to static HTML files  
Copyright (C) 2013  Christian Garbs <mitch@cgarbs.de>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

## Invocation

    git2html [-h|--help] [-x]
             [-o <output directory>] [-c <charset>] [-t <tabwidth>]
             [ [-i <branch>] ... ]
             <sourcefile>

`<sourcefile>` must be part of a non-bare local git repository.
This file's changelog will be converted to HTML over all available branches.

The generated files will be created in the `output directory` (`./out`
by default) relative to your current working directory.
**BEWARE:** This directory and all it's contents will be silently overwritten!

The `charset` will be used in the HTML charset meta header.  Default is `utf-8`.

The `tabwidth` will be used to expand tabs in the source file.  Default is `8`.

`-i <branch>` ignores the given branch in the output.  This parameter
can be used multiple times to suppress multiple branches.

`-x` will use an external CSS file instead of inlining the CSS in every file.

`-h`, `--help` or no parameters at all will show a short help text.

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

## Links

* [git2html](https://github.com/mmitch/git2html-test/)
* [git2html live demo](http://www.cgarbs.de/stuff/git2html-test/)
* [git2html demo source](https://github.com/mmitch/git2html-test/)

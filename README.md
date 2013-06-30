git2html
========


## About

`git2html` is used to render a single file's changelog from git to static HTML files.
I wrote it to do some code review on small Perl scripts.
Current status is "works for me", git2html is propably not the right tool to track changes within 2000+ lines of code :)

## Invocation

    git2html <filename>
    
`<filename>` must be part of a non-bare local git repository.
This file's changelog will be converted to HTML over all available branches.

The generated files will be created in the directory `./out` relative to your current working directory.
**BEWARE THAT THIS DIRECTORY AND ALL IT'S CONTENTS WILL BE SILENTLY OVERWRITTEN!**

## Example

This [live demo](http://www.cgarbs.de/stuff/git2html-test/) is generated nightly from the
[git2html-test](https://github.com/mmitch/git2html-test/) demo repository
using the most current version of `git2html`.

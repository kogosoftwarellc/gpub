gpub
======================

Deploy script for github sites.

## Process

1. clean the working copy.
1. checkout the source branch.
1. install npm dependencies.
1. run `npm run-script build`.
1. move `dist/` to a temporary directory.
1. checkout dist branch.
1. remove contents.
1. copy `dist/` contents
1. commit changes
1. push to remote dist branch
1. checkout source branch

## Prerequisites

* You'll execute this script as a user with push/pull access to the repository.
* Your project is compatible with npm.
* You have a `build` script defined in your `package.json`.
* You have git installed.
* Your gulp script outputs a `dist` directory.
* If you're on a mac, you'll need to have GNU's `readlink` on your path (google homebrew gnu readlink for more info).

## Usage

`gpub [OPTIONS]`

### Options

* `--repo-dir <path>` (required) - `<path>` must be a directory.
* `--src-branch <branch>` (defaults to `master`) - `<branch>` must be an existing branch.
* `--dist-branch <branch>` (defaults to `gh-pages`) - `<branch>` must be an existing branch.

### Example

`gpub --repo-dir /tmp/some-repo-dir --src-branch src --dist-branch master`

## License

ISC

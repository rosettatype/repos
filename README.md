# repos

Quick and dirty Python script to track multiple Git repositories and easily fetch updates for them.

It stores a list of repositories in a file `.repos` in your home folder, so you can refer to them with simple short names or all together.

You might want to consider using [Pug](https://github.com/ashur/pug) which is prettier and more versatile. I just felt like Python.


## Usage

For all commands except `repos list`, you can use special name `all` to process all tracked repos (e.g. `repos pull all`). For `pull/up` and `push` this uses only repos that are enabled (see below).

Add repo to the list:

``` bash
$ repos add <name> <path>
```

Add all repos in subdirectories of <path> to the list, names are generated automatically from the relative path:

``` bash
$ repos add all <path>
```

Remove repo with <name> from the list:

``` bash
$ repos rm <name>
```

Pull updates for repo <name> (uses: `git pull` and `git submodule update --init --recursive`):

``` bash
$ repos pull <name>
```

or identical:

``` bash
$ repos up <name>
```

Push updates for repo <name> (uses: `git push origin master`):

``` bash
$ repos push <name>
```

Enable repo so it is processed when `all` is used as a name (default is enabled):

``` bash
$ repos enable <name>
```

Disable repo so it is not processed when `all` is used as a name:

``` bash
$ repos disable <name>
```

Show repo details:

``` bash
$ repos show <name>
```

Show list of all tracked repos:

``` bash
$ repos list
```

Note: this is a result of my procrastination. Do not expect me to make it less dirty.

Requires Python 2.5 or higher I guess.

# lein-git-deps

*A Leiningen task that will pull dependencies in via git*

## Usage

Dependencies should be listed in project.clj under the ``:git-dependencies`` key. They can be provided as:

 * url
 * url & any param applicable for ``git checkout``, like a commit id or a branch name.
 * url, commit, and a map of options

You will also need to include the plugin in your ``project.clj``

```clojure
:plugins [[lein-git-deps "0.0.3"]]
:git-dependencies [["https://github.com/you/cool-hack.git"]]
```

### Emacs / clojure-jack-in

For Emacs users, using ``M-x clojure-jack-in`` does not currently
download the Git dependencies as it does normal dependencies. You must
manually run ``lein git-deps`` from the command line in your project
directory to get the Git dependencies installed.


### Deploying your own fork

Using Git-based dependencies is rather fragile and only really
suitable for development. The code you're pulling from GitHub can
change at any time, without warning. If you're deploying code to
production or releasing it publicly, it's better to base your code on
a stable known-target release. Getting the upstream maintainer of the
original library to release a new official version is best, but this
is not always possible if the original author is not around or if the
project has a slow release cycle.

In the case where pushing an updated version of the mainline release
is not possible, fork the project and package up your own
release. Then, you can either deploy it on your local system with
``lein install``, create a private Maven repository and publish it
there, or publish it to Clojars with a different group-id.

Detailed instructions on how to do these things can be found at
[https://github.com/technomancy/leiningen/blob/stable/doc/DEPLOY.md](https://github.com/technomancy/leiningen/blob/stable/doc/DEPLOY.md).

## Background

Original code extracted from the excellent ClojureScript One Project:

* https://github.com/brentonashworth/one
* https://github.com/brentonashworth/one/blob/master/src/leiningen/git_deps.clj

This version was forked and updated from the following:

* [https://github.com/torsten/lein-git-deps](https://github.com/torsten/lein-git-deps), which in turn was forked from the following (original) repo:
* [https://github.com/tobyhede/lein-git-deps](https://github.com/tobyhede/lein-git-deps)


## License

<pre>
Copyright &copy; 2012 Toby Hede
Copyright &copy; 2012 Brenton Ashworth and Relevance, Inc
Copyright &copy; 2015 Torsten Becker
Copyright &copy; 2016 Duncan McGreggor
</pre>

Distributed under the Eclipse Public License, the same as Clojure uses. See the file LICENSE.


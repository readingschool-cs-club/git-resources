Common Git CLI commands
=======================

If you're a command-line purist like me (or in-training) then you'll
want to know your way around Git's command-line interface. Overall,
given some understanding of how Git works, daily use is incredibly
simple. This file aims to aid understanding of Git's rather large CLI
interface and offer tips for common commands.

*Note: This document does NOT address the meanings of words or concepts.
It assuemes knowledege of branches, commits, checking-out and the rest.*


Basic bare-minimum commands
---------------------------

The integral commands you need to know to operate any Git repo are `git
add` and `git commit`:

  * `git add [-A]`: Stages the given files.

<!--
I use this so much that I've aliased it to `git a`.
-->

Passing the `-A` option stages *all* files. Useful if you've added tons
of files and want to add most of them (see [Unstaging](#unstaging) for
unstaging files).

  * `git commit [-m]`: Makes a commit.
  
Opens the commit message dialog in your default editor (located in the
environment variable $EDITOR).

The `-m` option allows you to specify the commit message without an
editor. It takes one argument as the commit message, so **quote your
message!** Example:

    git commit -m Added another nice juicy feature

This would NOT work. Quote as follows:

    git commit -m "Added another nice juicy feature"

  * `git status`: Show information about the working tree (i.e. the
    current Git status of your directory)

This is a VERY important command that you should run lots of times while
adding and committing files to make sure that you commit the right
stuff


Common collaboration commands
-----------------------------

This stuff is required for working with other people on a project. It
uses two of Git's most outstanding features: branches and merging.

  * `git branch [branch-name]`: Creates a new branch.

More often, though, you'll want this nice shortcut:

  * `git checkout -b [branch-name]`: Creates a new branch and checks it
    out.


Merging
-------

A merge in Git is required when history diverges or when you're trying
to merge two branches. *(Actually, in the latter, the former has usually
occurred.)* They *can* get messy, but they probably won't if we all work
cleanly.

    git checkout master
    git merge feature-branch

would merge the branch `feature-branch` into `master`.


Resolving conflicts
-------------------

Conflict resolution is the aforementioned messy part of merging. If
you're not sure what you're doing, you might mess up your merge commit,
so be careful!

For now, if Git complains about conflicts, please just push the branch
to the remote and make a GitHub pull request:

    git checkout [your-branch]
    git push origin [your-branch]

Then on GitHub, click the 'branches' menu and find your pushed branch.
Click it, then click the 'Pull Request' button that shows up and make
the PR.


Unstaging
---------

Suppose you want to stage 99 of 100 files. A possible lazy method (in a
positive way) is to do `git add -A` then unstage the file you don't want
to commit. This is simple:

    git add -A
    git reset HEAD unwanted-file.md
    git commit -m "..."

`git status` actually tells you the command to use in different
circumstances (since it's different in a new repo).


When in doubt...
----------------

Ask what Git thinks:

    git status

[RTFM](!Wikipedia):

    git command help
    man git command

Git has some absolutely fantastic documentation -- ***use it!***

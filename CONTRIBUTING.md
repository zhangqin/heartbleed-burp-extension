# How to contribute #

We'd love to accept your patches and contributions to this project.  There are
a just a few small guidelines you need to follow.


## Contributor License Agreement ##

Contributions to any Google project must be accompanied by a Contributor
License Agreement.  This is not a copyright **assignment**, it simply gives
Google permission to use and redistribute your contributions as part of the
project.

  * If you are an individual writing original source code and you're sure you
    own the intellectual property, then you'll need to sign an [individual
    CLA][].

  * If you work for a company that wants to allow you to contribute your work,
    then you'll need to sign a [corporate CLA][].

You generally only need to submit a CLA once, so if you've already submitted
one (even if it was for a different project), you probably don't need to do it
again.

[individual CLA]: https://developers.google.com/open-source/cla/individual
[corporate CLA]: https://developers.google.com/open-source/cla/corporate


## Submitting a patch ##

  1. It's generally best to start by opening a new issue describing the bug or
     feature you're intending to fix.  Even if you think it's relatively minor,
     it's helpful to know what people are working on.  Mention in the initial
     issue that you are planning to work on that bug or feature so that it can
     be assigned to you.

  1. Follow the normal process of [forking][] the project, and setup a new
     branch to work in.  It's important that each group of changes be done in
     separate branches in order to ensure that a pull request only includes the
     commits related to that bug or feature.

  1. Do your best to have [well-formed commit messages][] for each change.
     This provides consistency throughout the project, and ensures that commit
     messages are able to be formatted properly by various git tools.

  1. Finally, push the commits to your fork and submit a [pull request][].

[forking]: https://help.github.com/articles/fork-a-repo
[well-formed commit messages]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[squash]: http://git-scm.com/book/en/Git-Tools-Rewriting-History#Squashing-Commits
[pull request]: https://help.github.com/articles/creating-a-pull-request


## Other notes on code organization ##

Currently, everything is defined in the main `github` package, with API methods
broken into separate service objects.  These services map directly to how
the [GitHub API documentation][] is organized, so use that as your guide for
where to put new methods.

Sub-service (e.g. [Repo Hooks][]) implementations are split into separate files
based on the APIs they provide. These files are named service_api.go (e.g.
repos_hooks.go) to describe the API to service mappings.

[GitHub API documentation]: http://developer.github.com/v3/
[Repo Hooks]: http://developer.github.com/v3/repos/hooks/
[![Melpa Status](http://melpa.org/packages/inheritenv-badge.svg)](http://melpa.org/#/inheritenv)
[![Melpa Stable Status](http://stable.melpa.org/packages/inheritenv-badge.svg)](http://stable.melpa.org/#/inheritenv)
[![Build Status](https://github.com/purcell/inheritenv/workflows/CI/badge.svg)](https://github.com/purcell/inheritenv/actions)
<a href="https://www.patreon.com/sanityinc"><img alt="Support me" src="https://img.shields.io/badge/Support%20Me-%F0%9F%92%97-ff69b4.svg"></a>

# Make Emacs temp buffers inherit buffer-local environment variables

There's a fairly common pitfall when Emacs libraries run background
processes on behalf of a user: the library should honour any
environment variables set buffer-locally, but many such libraries run
processes in temporary buffers that do not inherit the calling
buffer's environment.

An example is the Emacs built-in command
`shell-command-to-string`. Whatever buffer-local `process-environment`
(or `exec-path`) the user has set, that command will always use the
Emacs-wide default. This is *specified* behaviour, but not *expected*
or *helpful*, particularly if one uses a library like
[envrc](https://github.com/purcell/envrc) with `direnv`.

`inheritenv` provides a couple of tools for dealing with this
issue:

1. Library authors can wrap code that plans to execute processes in
   temporary buffers with the `inheritenv` macro.
2. Users can modify commands like `shell-command-to-string` using the
   `inheritenv-add-advice` macro.

## Installation

### Manual

Ensure `inheritenv.el` is in a directory on your load-path, and add
the following to your `~/.emacs` or `~/.emacs.d/init.el`:

```elisp
(require 'inheritenv)
```

### MELPA

If you're an Emacs 24 user or you have a recent version of
`package.el` you can install `inheritenv` from the
[MELPA](http://melpa.org) repository. The version of
`inheritenv` there will always be up-to-date.

## About

Author: Steve Purcell <steve at sanityinc dot com>

Homepage: https://github.com/purcell/inheritenv

<hr>

[💝 Support this project and my other Open Source work](https://www.patreon.com/sanityinc)

[💼 LinkedIn profile](https://uk.linkedin.com/in/stevepurcell)

[✍ sanityinc.com](https://www.sanityinc.com/)

[🐦 @sanityinc](https://twitter.com/sanityinc)

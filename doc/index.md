<p align="center">
  <img src="https://raw.github.com/clojure-emacs/cider/master/logo/cider-logo-w640.png" alt="CIDER Logo"/>
</p>

CIDER is the **C**lojure(Script) **I**nteractive **D**evelopment **E**nvironment
that **R**ocks!

CIDER extends Emacs with support for interactive programming in Clojure. The
features are centered around `cider-mode`, an Emacs minor-mode that complements
[clojure-mode][]. While `clojure-mode` supports editing Clojure source files,
`cider-mode` adds support for interacting with a running Clojure process for
compilation, debugging, definition and documentation lookup, running tests and
so on.

!!! Note

    CIDER was originally inspired by the powerful Common Lisp interactive
    development environment [SLIME][]. In the beginning we started by
    adapting SLIME's core functionality to Clojure, but over the course of time
    CIDER became pretty different from SLIME in many areas. Check out
    [this presentation](https://www.youtube.com/watch?v=4X-1fJm25Ww&list=PLZdCLR02grLoc322bYirANEso3mmzvCiI&index=6)
    if you'd like to know more about CIDER's early history.

**Please consider
[supporting financially its ongoing development](about/contributing.md#funding).**

## Overview

CIDER aims to provide an interactive development experience similar to the one
you'd get when programming in Emacs Lisp, Common Lisp (with [SLIME][] or [Sly][]),
Scheme (with [Geiser][]) and Smalltalk.

Programmers are expected to program in a very dynamic and incremental manner,
constantly re-evaluating existing Clojure definitions and adding new ones to
their running applications. You never stop/start a Clojure application while
using CIDER - you're constantly interacting with it and changing it.

You can find more details about the typical CIDER workflow in the
[Interactive Programming](interactive_programming.md) section. While we're a bit
short on video tutorials, you can check out this
[into to CIDER](https://www.youtube.com/watch?v=aYA4AAjLfT0) to get a
feel about what do we mean by an "Interactive Development Environment".

CIDER's built on top of [nREPL][], the Clojure networked REPL server.

CIDER's basic architecture looks something like this:

<p align="center">
  <img src="images/cider_architecture.png" width="600" />
</p>

Clojure code gets executed by an nREPL server. CIDER sends requests to the
server and processes its responses. The server's functionality is augmented by
additional [nREPL middleware][cider-nrepl], designed specifically to address the needs of an
interactive development environment like CIDER.


!!! Note

    Much of the nREPL middleware we originally
    developed for CIDER is editor-agnostic and is being used by other Clojure
    development environments as well (e.g. [vim-fireplace][] & [calva][]).

CIDER packs plenty of features. Here are some of them (in no particular order):

* [Powerful REPL](using_the_repl.md)
* [Interactive code evaluation](interactive_programming.md)
* Compilation notes (error and warning highlighting)
* [Human-friendly stacktraces](navigating_stacktraces.md)
* [Smart code completion](code_completion.md)
* Definition lookup
* Documentation lookup
* Resource lookup
* Apropos
* [Debugger](debugging.md)
* [Value inspector](miscellaneous_features.md#value-inspection)
* [Function tracing](miscellaneous_features.md#tracing-function-execution)
* [Interactive macroexpansion](miscellaneous_features.md#macroexpansion)
* Enhanced Clojure font-locking and indentation
* [Grimoire](http://conj.io/) integration
* [`clojure.test` integration](running_tests.md)
* [Smart code reloading](miscellaneous_features.md#code-reloading)
* [Pretty-printing of results](pretty_printing.md)
* [Classpath browser](miscellaneous_features.md#classpath-browser)
* [Namespace browser](miscellaneous_features.md#namespace-browser)
* [REPL history browser](miscellaneous_features.md#repl-history-browser)
* nREPL session management
* [Scratchpad](miscellaneous_features.md#using-a-scratchpad)
* [Minibuffer code evaluation](miscellaneous_features.md#evaluating-clojure-code-in-the-minibuffer)
* Integration with [company-mode][]
* [Support for working with multiple REPLs](managing_connections.md)

![CIDER Screenshot](images/cider-overview.png)

[nREPL]: https://github.com/nrepl/nrepl
[SLIME]: https://github.com/slime/slime
[Sly]: https://github.com/capitaomorte/sly
[Geiser]: https://github.com/jaor/geiser
[company-mode]: http://company-mode.github.io/
[leiningen]: http://leiningen.org/
[boot]: http://boot-clj.com/
[piggieback]: https://github.com/nrepl/piggieback
[vim-fireplace]: https://github.com/tpope/vim-fireplace
[calva]: https://github.com/BetterThanTomorrow/calva
[cider-nrepl]: https://github.com/clojure-emacs/cider-nrepl
[clojure-mode]: https://github.com/clojure-emacs/clojure-mode
[which-key]: https://github.com/justbur/emacs-which-key

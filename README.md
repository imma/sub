Starting a sub-command chain
============================

Symlink or copy `exec/sub` into `bin/command`; this is the public entry
point into the sub-commands, and `bin` can be put into `$PATH`.

Implementating the top level command
====================================

`bin/command` searches for an implementation of `command`.  The default
is searched in `exec/command-default` or any `command-default` in the
`$PATH`.

Implementation a sub-command
============================

`command xxx` searches for `exec/command-xxx` or `command-xxx` in
`$PATH`.

Implementation boilerplate
==========================

Implementation scripts contain a `main` function and sources the
`exec/sub` script (exposed via `$_SUB` variable). 

Here's an example:

    function main {
      uname -a
    }

    source "$_SUB" "$BASH_SOURCE" "$@"


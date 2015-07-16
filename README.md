Implementation boilerplate
==========================

Implementation scripts contain a `main` function and sources the
`sub` script (put into `$PATH`).  The scripts should be put in `exec` in
the project repo or searcheable in `$PATH`.

Here's an example:

    function main {
      uname -a
    }

    source sub "$0" "$@"


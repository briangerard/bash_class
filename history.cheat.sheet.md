# History Manipulation Cheat Sheet #

* `set -o vi`
    * sets vi keybindings for commandline editing
* `set -o emacs`
    * same, for emacs (default)

* `fc`
    * opens immediately previous command in $EDITOR

* `^foo^bar^`
    * substitutes "bar" for "foo" in the immediately previous
      command and executes the resulting command
* `!!:s/foo/bar/`
    * same
* `!1234:s/foo/bar`
    * same substitution, but on command number 1234 (as
      listed in history).


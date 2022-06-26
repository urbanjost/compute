### fpm-tools : [compute](https://urbanjost.github.io/compute/)

Build compute(1) using fpm(1):
```bash
git clone https://github.com/urbanjost/compute
cd compute
fpm install
compute --help
```

See [M_calculator](https://urbanjost.github.io/M_calculator/)
for a complete discussion of the allowed expressions.

NAME
====

**compute**(1f) - \[MATH\] evaluate a calculator expression (LICENSE:PD)

SYNOPSIS
========

**compute** \[\[STRING\] \[-**-trail** *FILENAME*\] \[
**-verbose**\]\]\|\[ **-help**\|**-version**\]

DESCRIPTION
===========

Given any expression call the **CALCULATOR**(3f) calculator function and
evaluate it. If no expression is present on the command line, read
expressions from stdin until a line composed of a **period**(".") or end
of data is encountered.

Expressions are similar to Fortran77 syntax except powers are processed
from left to right, and string variable names start with a dollar-sign,
and all numeric values are assumed to be DOUBLEPRECISION.

OPTIONS
=======

***STRING***

:   calculator expression to evaluate

****--trail** *FILENAME***

:   record actions on a trail file.

****--verbose****

:   echo the input as well as the computed values

****--help****

:   display this help and exit

****--version****

:   output version information and exit

EXAMPLES
========

Sample commands:

        $ compute '(sin(30.33333)*2)**2+40.0/2.3-1.23e3'
        $ compute funcs|more

        $ compute --trail record.txt
        a=10
        # The redo(3f) command is used for command recall and history
        # by entering an exclamation on a line by itself or by following
        # the exclamation by a space and an optional initial command for
        # redo(3f). Enter "?" at the redo(3f) prompt for help using the
        # command line history editor.

        # enter a long calculation
        b=sin(a)**2+3.4e2+100-11*2/55.6
        # use redo(3f) to change "sin" to "cos". Enter return to execute
        # the changed line
        ! c/sin/cos

        # system commands can be called if prefixed by exclamation
        !ls

        # exit using a period on a line by itself
        .

        # a simple non-nesting alternate input file can be read
        <myfile

        funcs # list available functions
        dump  # list current variables

SEE ALSO
========

See the **man**(1) page for **M\_calculator**(3fm) for a more detailed
description of the **CALCULATOR**(3f) routine.

AUTHOR
======

John S. Urban

LICENSE
=======

Public License



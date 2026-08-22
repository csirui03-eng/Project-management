---
apdl: "*MSG"
method: msg
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.msg
generated: 2026-08-22
tags: [mapdl-command]
---

# *MSG

PyMAPDL: `mapdl.msg(lab='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', **kwargs)`

Writes an output message via the Mechanical APDL message subroutine.

## Parameters

**lab**

Label for output and termination control:

- `INFO` - Writes the message with no heading (default).
- `NOTE` - Writes the message with a "NOTE" heading.
- `WARN` - Writes the message with a "WARNING" heading. Also writes the message to the errors file, `JobnameERR`.
- `ERROR` - Writes the message with a "ERROR" heading and causes run termination (if batch) at earliest "clean exit" point. Also writes the message to the errors file, `JobnameERR`.
- `FATAL` - Writes the message with a "FATAL ERROR" heading and causes run termination immediately. Also writes the message to the errors file, `JobnameERR`.
- `UI` - Writes the message with a "NOTE" heading and displays it in the message dialog box. This option is most useful in GUI mode.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**: Numeric or alphanumeric character values to be included in message. Values may be the results of parameter evaluations. All numeric values are assumed to be double precision. The FORTRAN nearest integer (NINT) function is used to form integers for the %I specifier.

## Notes

Allows writing an output message via the Mechanical APDL message subroutine. Also allows run termination control. This command is used only when contained in a prepared file read into the Mechanical APDL program (that is, [[use|*USE]], [[input|/INPUT]], etc.). A message format must immediately follow the **\*MSG** command (on a separate line, without parentheses, as described below).

The message format may be up to 80 characters long, consisting of text strings and predefined "data descriptors" between the strings where numeric or alphanumeric character data are to be inserted. The normal descriptors are %I for integer data, %G for double precision data, %C for alphanumeric character data, and %/ for a line break. The corresponding FORTRAN data descriptors are I9, 1PG16.9 and A8, respectively. Each descriptor must be preceded by a blank. There must be one data descriptor for each specified value (8 maximum) in the order of the specified values.

Enhanced descriptions may also be used:

(table not available in the PyMAPDL source, see the Ansys help page)

Do not begin **\*MSG** format lines with `*IF`, `*ELSE`, `*ELSEIF`, or `*ENDIF`. If the last nonblank character of the message format is an ampersand (&), a second line will also be read as a continuation of the format. Up to nine continuations (ten total lines) may be read. If normal descriptions are used, then consecutive blanks are condensed into one blank upon output, and a period is appended. Up to ten lines of output of 72 characters each may be produced (using the %/ descriptor). Two examples follow.

Here is an example of the **\*MSG** command and a format to print a message with two integer values and one real value:

``` apdl
*MSG, INFO, 'Inner',25,1.2,148
Radius ( %C) = %I, Thick = %G, Length = %I
```

The output line is:

``` apdl
Radius (Inner) = 25, Thick = 1.2, Length = 148.
```

Here is an example illustrating multiline displays in GUI message windows:

``` apdl
*MSG,UI,Vcoilrms,THTAv,Icoilrms,THTAi,Papprnt,Pelec,PF,indctnc
Coil RMS voltage, RMS current, apparent pwr, actual pwr, pwr factor: %/&
Vcoil = %G V (electrical angle = %G DEG) %/&
Icoil = %G A (electrical angle = %G DEG) %/&
APPARENT POWER = %G W %/&
ACTUAL POWER = %G W %/&
Power factor: %G %/&
Inductance = %G %/&
VALUES ARE FOR ENTIRE COIL (NOT JUST THE MODELED SECTOR)
```

The [[uis|/UIS]],MSGPOP command controls which messages are displayed in the message dialog box when the GUI is active. All messages produced by the **\*MSG** command are subject to the [[uis|/UIS]] specification, with one exception, If `Lab` = UI, the message will be displayed in the dialog box regardless of the [[uis|/UIS]] specification.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSG.html

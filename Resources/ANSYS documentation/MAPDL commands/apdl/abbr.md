---
apdl: "*ABBR"
method: abbr
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.abbreviations.Abbreviations.abbr
generated: 2026-08-22
tags: [mapdl-command]
---

# *ABBR

PyMAPDL: `mapdl.abbr(abbr='', string='', **kwargs)`

Defines an abbreviation.

## Parameters

**abbr**: The abbreviation (up to 8 alphanumeric characters) used to represent the string `String`. If `Abbr` is the same as an existing Mechanical APDL command, the abbreviation overrides. Avoid using an `Abbr` which is the same as an Mechanical APDL command.

**string**: String of characters (60 maximum) represented by `Abbr`. Cannot include a \$ or any of the commands `C***`, [[com|/COM]], [[gopr|/GOPR]], [[nopr|/NOPR]], [[quit|/QUIT]], [[ui|/UI]], or [[end|*END]]. Parameter names and commands of the `*DO` and Use the `*IF` groups may not be abbreviated. If `String` is blank, the abbreviation is deleted. To abbreviate multiple commands, create an "unknown command" macro or define `String` to execute a macro file ( [[use|*USE]] ) containing the desired commands.

## Notes

Once the abbreviation `Abbr` is defined, you can issue it at the beginning of a command line and follow it with a blank (or with a comma and appended data), and the program will substitute the string `String` for `Abbr` as the line is executed. Up to 100 abbreviations may exist at any time and are available throughout the program. Abbreviations may be redefined or deleted at any time.

Use [[starstatus|*STATUS]] to display the current list of abbreviations. For abbreviations repeated with `*REPEAT`, substitution occurs before the repeat increments are applied. There are a number of abbreviations that are predefined by the program (these can be deleted by using the blank `String` option described above). Note that `String` will be written to the `FileLOG`.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ABBR.html

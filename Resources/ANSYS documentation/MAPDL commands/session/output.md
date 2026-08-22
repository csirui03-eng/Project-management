---
apdl: "/OUTPUT"
method: output
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.output
generated: 2026-08-22
tags: [mapdl-command]
---

# /OUTPUT

PyMAPDL: `mapdl.output(fname='', ext='', loc='', **kwargs)`

Redirects text output to a file or to the screen.

## Parameters

**fname**: Filename and directory path (248 character maximum, including directory) to which text output will be redirected (defaults to `Jobname` if `Ext` is specified). For interactive runs, `Fname` = TERM (or blank) redirects output to the screen. For batch runs, `Fname` = blank (with all remaining command arguments blank) redirects output to the default system output file.

**ext**: Filename extension (eight-character maximum).

**loc**

Location within a file to which output will be written:

- `(blank)` - Output is written starting at the top of the file (default).
- `APPEND` - Output is appended to the existing file.

## Notes

Text output includes responses to every command and GUI function, notes, warnings, errors, and other informational messages. Upon execution of **/OUTPUT**, `Fname`, `Ext`, `...`, all subsequent text output is redirected to the file `Fname.Ext`. To redirect output back to the default location, issue **/OUTPUT** (no arguments).

When using the GUI, output from list operations ( [[nlist|NLIST]], [[dlist|DLIST]], etc.) is always sent to a list window regardless of the **/OUTPUT** setting. The output can then be saved on a file or copied to the **/OUTPUT** location using the File menu in the list window.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OUTPUT.html

---
apdl: "/CWD"
method: cwd
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.cwd
generated: 2026-08-22
tags: [mapdl-command]
---

# /CWD

PyMAPDL: `mapdl.cwd(dirpath='', **kwargs)`

Changes the current working directory.

## Parameters

**dirpath**: The full path name of the new working directory.

## Notes

After issuing the /CWD command, all new files opened with no default directory specified (via the [[file|FILE]], [[copy|/COPY]], or [[resume|RESUME]] commands, for example) default to the new `DIRPATH` directory.

## Examples

Change MAPDL's working directory to `"C:/temp"`. This assumes that MAPDL running on Windows.

``` python
>>> mapdl.cwd("C:/temp")
```

MAPDL on Linux example:

``` python
>>> mapdl.cwd("/tmp/")
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CWD_sl.html

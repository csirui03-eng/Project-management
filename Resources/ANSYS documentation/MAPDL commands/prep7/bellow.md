---
apdl: "BELLOW"
method: bellow
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.bellow
generated: 2026-08-22
tags: [mapdl-command]
---

# BELLOW

PyMAPDL: `mapdl.bellow(nloc='', leng='', stiff='', flex='', elem='', **kwargs)`

Defines a bellows in a piping run.

## Parameters

**nloc**: Node where bellows is to be placed. Defaults to current run starting point (RUN).

**leng**: Length of bellows (defaults to average pipe OD).

**stiff**: Axial stiffness value (defaults to that of equivalent straight pipe).

**flex**: Bending flexibility factor (defaults to 1.0).

**elem**: Element number to be assigned to bellows (defaults to the previous maximum element number (MAXEL) + 1).

## Notes

Defines a bellows (straight-pipe element PIPE16 with adjusted specifications and loadings) at a given location in a piping run.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BELLOW.html

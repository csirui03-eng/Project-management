---
apdl: "GAPF"
method: gapf
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26._set_up.SetUp.gapf
generated: 2026-08-22
tags: [mapdl-command]
---

# GAPF

PyMAPDL: `mapdl.gapf(nvar='', num='', name='', **kwargs)`

Defines the gap force data to be stored in a variable.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to `NV` on [[numvar|NUMVAR]] ). Overwrites any existing results for this variable.

**num**: Number identifying gap number for which the gap force is to be stored. Issue the [[gplist|GPLIST]] command to display gap numbers.

**name**: Thirty-two character name for identifying the item on the printout and displays (defaults to the name **GAPF** ).

## Notes

Defines the gap force data to be stored in a variable. Applicable only to the expansion pass of the mode-superposition linear transient dynamic ( [[antype|ANTYPE]],TRANS) analysis. The data is usually on `FnameRDSP`.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GAPF.html

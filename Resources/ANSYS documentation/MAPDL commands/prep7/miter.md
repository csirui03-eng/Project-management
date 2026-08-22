---
apdl: "MITER"
method: miter
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.miter
generated: 2026-08-22
tags: [mapdl-command]
---

# MITER

PyMAPDL: `mapdl.miter(nel1='', nel2='', rad='', ndiv='', estrt='', einc='', **kwargs)`

Defines a mitered bend in a piping run.

## Parameters

**nel1**, **nel2**: Element numbers of the two intersecting straight pipes. Defaults to the last two straight pipe elements nearest the intersection of the last two runs.

**rad**: Bend radius. If LR, use long radius standard (1.5 x OD) (default). If SR, use short radius standard (1.0 x OD).

**ndiv**: Number of divisions (elements) along bend (defaults to 2). A node is generated at the end of each division.

**estrt**: Number to be assigned to first element of bend (defaults to MAXEL + 1).

**einc**: Element number increment (defaults to 1).

## Notes

Defines a mitered bend of piecewise straight-pipe PIPE16 elements in place of the intersection of two previously defined straight pipe elements (RUN). This command is similar to the BEND command except that straight pipe elements are used to form the bend instead of curved (elbow) elements. (See the RUN and BEND command descriptions in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MITER.html

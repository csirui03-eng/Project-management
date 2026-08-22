---
apdl: "FSPLOT"
method: fsplot
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fsplot
generated: 2026-08-22
tags: [mapdl-command]
---

# FSPLOT

PyMAPDL: `mapdl.fsplot(nloc='', nev='', item='', **kwargs)`

Displays a fatigue stress item for a fatigue location and event.

## Parameters

**nloc**: Display stresses associated with location `NLOC`.

**nev**: Display stresses associated with event `NEV`.

**item**

Display stresses associated with item number `ITEM`. Items are as follows:

- `1-6` - SX, SY, SZ, SXY, SYZ, SXZ total stress components
- `7` - Temperature
- `8-13` - SX, SY, SZ, SXY, SYZ, SXZ membrane-plus-bending stress components.
- `14` - Time

## Notes

Displays a fatigue stress item as a function of loading number for a particular fatigue location and event.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSPLOT.html

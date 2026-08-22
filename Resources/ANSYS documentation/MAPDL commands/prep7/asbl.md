---
apdl: "ASBL"
method: asbl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.asbl
generated: 2026-08-22
tags: [mapdl-command]
---

# ASBL

PyMAPDL: `mapdl.asbl(na='', nl='', keepa='', keepl='', **kwargs)`

Subtracts lines from areas.

## Parameters

**na**: Area (or areas, if picking is used) to be subtracted from. If ALL, use all selected areas. If P, graphical picking is enabled (valid only in the GUI) and remaining fields are ignored. A component name may also be substituted for `NA`.

**nl**: Line (or lines, if picking is used) to subtract. If ALL, use all selected lines. A component name may also be substituted for `NL`.

**keepa**

Specifies whether `NA` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA` areas after **ASBL** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA` areas after **ASBL** operation (override [[boptn|BOPTN]] command settings).

**keepl**

Specifies whether `NL` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL` lines after **ASBL** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL` lines after **ASBL** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new areas by subtracting the regions common to both the areas and lines (the intersection) from the `NA` areas. The intersection will be a line(s). See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASBL.html

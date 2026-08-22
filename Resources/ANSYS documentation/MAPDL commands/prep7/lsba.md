---
apdl: "LSBA"
method: lsba
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lsba
generated: 2026-08-22
tags: [mapdl-command]
---

# LSBA

PyMAPDL: `mapdl.lsba(nl='', na='', sepo='', keepl='', keepa='', **kwargs)`

Subtracts areas from lines.

## Parameters

**nl**: Line (or lines, if picking is used) to be subtracted from. If ALL, use all selected lines. If `NL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL`.

**na**: Area (or areas, if picking is used) to be subtracted. If ALL, use all selected areas. A component name may also be substituted for `NA`.

**sepo**

Behavior if the intersection of the lines and the areas is a keypoint or keypoints:

- `(blank)` - The resulting lines will share keypoint(s) where they touch.
- `SEPO` - The resulting lines will have separate, but coincident keypoint(s) where they touch.

**keepl**

Specifies whether `NL` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL` lines after **LSBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL` lines after **LSBA** operation (override [[boptn|BOPTN]] command settings).

**keepa**

Specifies whether `NA` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete areas after **LSBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep areas after **LSBA** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new lines by subtracting the regions common to both `NL` lines and `NA` areas (the intersection) from the `NL` lines. The intersection can be a line(s) or keypoint(s). If the intersection is a keypoint and `SEPO` is blank, the `NL` line is divided at the keypoint and the resulting lines will be connected, sharing a common keypoint where they touch. If `SEPO` is set to SEPO, `NL` is divided into two unconnected lines with separate keypoints where they touch. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSBA.html

---
apdl: "LSBL"
method: lsbl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lsbl
generated: 2026-08-22
tags: [mapdl-command]
---

# LSBL

PyMAPDL: `mapdl.lsbl(nl1='', nl2='', sepo='', keep1='', keep2='', **kwargs)`

Subtracts lines from lines.

## Parameters

**nl1**: Line (or lines, if picking is used) to be subtracted from. If ALL, use all selected lines. Lines specified in this argument are not available for use in the `NL2` argument. If P, graphical picking is enabled (valid only in the GUI) and all remaining fields are ignored. A component name may also be substituted for `NL1`.

**nl2**: Line (or lines, if picking is used) to subtract. If ALL, use all selected lines (except those included in the `NL1` argument). A component name may also be substituted for `NL2`.

**sepo**

Behavior if the intersection of the `NL1` lines and the `NL2` lines is a keypoint or keypoints:

- `(blank)` - The resulting lines will share keypoint(s) where they touch.
- `SEPO` - The resulting lines will have separate, but coincident keypoint(s) where they touch.

**keep1**

Specifies whether `NL1` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL1` lines after **LSBL** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL1` lines after **LSBL** operation (override [[boptn|BOPTN]] command settings).

**keep2**

Specifies whether `NL2` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL2` lines after **LSBL** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL2` lines after **LSBL** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new lines by subtracting the regions common to both `NL1` and `NL2` lines (the intersection) from the `NL1` lines. The intersection can be a line(s) or point(s). If the intersection is a point and `SEPO` is blank, the `NL1` line is divided at the point and the resulting lines will be connected, sharing a common keypoint where they touch. If `SEPO` is set to SEPO, `NL1` is divided into two unconnected lines with separate keypoints where they touch. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. **LSBL**,ALL,ALL will have no effect since all the lines (in `NL1` ) will be unavailable as `NL2` lines.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSBL.html

---
apdl: "LSBV"
method: lsbv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lsbv
generated: 2026-08-22
tags: [mapdl-command]
---

# LSBV

PyMAPDL: `mapdl.lsbv(nl='', nv='', sepo='', keepl='', keepv='', **kwargs)`

Subtracts volumes from lines.

## Parameters

**nl**: Line (or lines, if picking is used) to be subtracted from. If ALL, use all selected lines. If `NL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL`.

**nv**: Volume (or volumes, if picking is used) to be subtracted. If ALL, use all selected volumes. A component name may also be substituted for `NV`.

**sepo**

Behavior if the intersection of the `NL` lines and the `NV` volumes is a keypoint or keypoints:

- `(blank)` - The resulting lines will share keypoint(s) where they touch.
- `SEPO` - The resulting lines will have separate, but coincident keypoint(s) where they touch.

**keepl**

Specifies whether `NL` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL` lines after **LSBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL` lines after **LSBV** operation (override [[boptn|BOPTN]] command settings).

**keepv**

Specifies whether `NV` volumes are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NV` volumes after **LSBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NV` volumes after **LSBV** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new lines by subtracting the regions common to both `NL` lines and `NV` volumes (the intersection) from the `NL` lines. The intersection can be a line(s) or point(s). If the intersection is a point and `SEPO` is blank, the `NL1` line is divided at the point and the resulting lines will be connected, sharing a common keypoint where they touch. If `SEPO` is set to SEPO, `NL1` is divided into two unconnected lines with separate keypoints where they touch. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. [[lsbl|LSBL]],ALL,ALL will have no effect since all the lines (in `NL1` ) will be unavailable as `NL2` lines.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSBV.html

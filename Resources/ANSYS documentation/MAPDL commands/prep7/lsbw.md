---
apdl: "LSBW"
method: lsbw
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lsbw
generated: 2026-08-22
tags: [mapdl-command]
---

# LSBW

PyMAPDL: `mapdl.lsbw(nl='', sepo='', keep='', **kwargs)`

Subtracts the intersection of the working plane from lines (divides lines).

## Parameters

**nl**: Line (or lines, if picking is used) to be subtracted from. If `NL` = ALL, use all selected lines. If `NL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be input for `NL`.

**sepo**

Behavior of the created boundary.

- `(blank)` - The resulting lines will share keypoint(s) where they touch.
- `SEPO` - The resulting lines will have separate, but coincident keypoint(s).

**keep**

Specifies whether `NL` lines are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NL` lines after **LSBW** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NL` lines after **LSBW** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new lines by subtracting the intersection of the working plane from the `NL` lines. The intersection will be a keypoint(s). The working plane must not be in the same plane as the `NL` line(s). If `SEPO` is blank, the `NL` line is divided and the resulting lines will be connected, sharing a common keypoint where they touch. If `SEPO` is set to SEPO, `NL` is divided into two unconnected lines with separate keypoints. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. Areas that completely contain the input lines will be updated if the lines are divided by this operation.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSBW.html

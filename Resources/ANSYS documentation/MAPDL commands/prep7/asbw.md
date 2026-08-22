---
apdl: "ASBW"
method: asbw
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.asbw
generated: 2026-08-22
tags: [mapdl-command]
---

# ASBW

PyMAPDL: `mapdl.asbw(na='', sepo='', keep='', **kwargs)`

Subtracts the intersection of the working plane from areas (divides areas).

## Parameters

**na**: Area (or areas, if picking is used) to be subtracted from. If `NA` = ALL, use all selected areas. If `NA` = P, graphical picking is enabled (valid only in the GUI). A component name may also be input for `NA`.

**sepo**

Behavior of the created boundary.

- `(blank)` - The resulting areas will share line(s) where they touch.
- `SEPO` - The resulting areas will have separate, but coincident line(s).

**keep**

Specifies whether `NA` areas are to be deleted.

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA` areas after **ASBW** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA` areas after **ASBW** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new areas by subtracting the intersection of the working plane from the `NA` areas. The intersection will be a line(s). The working plane must not be in the same plane as the `NA` area(s). If `SEPO` is blank, the `NA` area is divided at the line and the resulting areas will be connected, sharing a common line where they touch. If `SEPO` is set to SEPO, `NA` is divided into two unconnected areas with separate lines. The SEPO option may cause unintended consequences if any keypoints exist along the cut plane. See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Issuing the **ASBW** command under certain conditions may generate a topological degeneracy error. Do not issue the command if:

- A sphere or cylinder has been scaled. (A cylinder must be scaled unevenly in the XY plane.)
- A sphere or cylinder has not been scaled but the work plane has been rotated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASBW.html

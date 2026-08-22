---
apdl: "VSBW"
method: vsbw
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vsbw
generated: 2026-08-22
tags: [mapdl-command]
---

# VSBW

PyMAPDL: `mapdl.vsbw(nv='', sepo='', keep='', **kwargs)`

Subtracts intersection of the working plane from volumes (divides volumes).

## Parameters

**nv**: Volume (or volumes, if picking is used) to be subtracted from. If `NV` = ALL, use all selected volumes. If `NV` = P, graphical picking is enabled (valid only in the GUI). A component name may also be input for `NV`.

**sepo**

Behavior of the created boundary.

- `(blank)` - The resulting volumes will share area(s) where they touch.
- `SEPO` - The resulting volumes will have separate, but coincident area(s).

**keep**

Specifies whether `NV` volumes are to be deleted.

- `(blank)` - Use the setting of `KEEP` on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NV` volumes after **VSBW** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NV` volumes after **VSBW** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new volumes by subtracting the intersection of the working plane from the `NV` volumes. The intersection will be an area(s). If `SEPO` is blank, the volume is divided at the area and the resulting volumes will be connected, sharing a common area where they touch. If `SEPO` is set to SEPO, the volume is divided into two unconnected volumes with separate areas. The SEPO option may cause unintended consequences if any keypoints exist along the cut plane. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Issuing the **VSBW** command under certain conditions may generate a topological degeneracy error. Do not issue the command if:

- A sphere or cylinder has been scaled. (A cylinder must be scaled unevenly in the XY plane.)
- A sphere or cylinder has not been scaled but the work plane has been rotated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSBW.html

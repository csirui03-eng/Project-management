---
apdl: "VSBA"
method: vsba
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vsba
generated: 2026-08-22
tags: [mapdl-command]
---

# VSBA

PyMAPDL: `mapdl.vsba(nv='', na='', sepo='', keepv='', keepa='', **kwargs)`

Subtracts areas from volumes.

## Parameters

**nv**: Volume (or volumes, if picking is used) to be subtracted from. If ALL, use all selected volumes. If P, graphical picking is enabled (valid only in the GUI) and remaining fields are ignored. A component name may also be substituted for `NV`.

**na**: Area (or areas, if picking is used) to subtract. If ALL, use all selected areas. A component name may also be substituted for `NA`.

**sepo**

Behavior of the touching boundary:

- `(blank)` - The resulting volumes will share area(s) where they touch.
- `SEPO` - The resulting volumes will have separate, but coincident area(s) where they touch.

**keepv**

Specifies whether `NV` volumes are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NV` volumes after **VSBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NV` volumes after **VSBA** operation (override [[boptn|BOPTN]] command settings).

**keepa**

Specifies whether `NA` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA` areas after **VSBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA` areas after **VSBA** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new volumes by subtracting the regions common to both the volumes and areas (the intersection) from the `NV` volumes. The intersection will be an area(s). If `SEPO` is blank, the volume is divided at the area and the resulting volumes will be connected, sharing a common area where they touch. If `SEPO` is set to SEPO, the volume is divided into two unconnected volumes with separate areas where they touch. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSBA.html

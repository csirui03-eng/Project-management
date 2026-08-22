---
apdl: "ASBV"
method: asbv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.asbv
generated: 2026-08-22
tags: [mapdl-command]
---

# ASBV

PyMAPDL: `mapdl.asbv(na='', nv='', sepo='', keepa='', keepv='', **kwargs)`

Subtracts volumes from areas.

## Parameters

**na**: Area (or areas, if picking is used) to be subtracted from. If ALL, use all selected areas. If P, graphical picking is enabled (valid only in the GUI) and remaining fields are ignored. A component name may also be substituted for `NA`.

**nv**: Volume (or volumes, if picking is used) to subtract. If ALL, use all selected volumes. A component name may also be substituted for `NV`.

**sepo**

Behavior if the intersection of the areas and the volumes is a line or lines:

- `(blank)` - The resulting areas will share line(s) where they touch.
- `SEPO` - The resulting areas will have separate, but coincident line(s) where they touch.

**keepa**

Specifies whether `NA` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA` areas after **ASBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA` areas after **ASBV** operation (override [[boptn|BOPTN]] command settings).

**keepv**

Specifies whether `NV` volumes are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete volumes after **ASBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep volumes after **ASBV** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new areas by subtracting the regions common to both `NA` areas and `NV` volumes (the intersection) from the `NA` areas. The intersection can be an area(s) or line(s). If the intersection is a line and `SEPO` is blank, the `NA` area is divided at the line and the resulting areas will be connected, sharing a common line where they touch. If `SEPO` is set to SEPO, `NA` is divided into two unconnected areas with separate lines where they touch. See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASBV.html

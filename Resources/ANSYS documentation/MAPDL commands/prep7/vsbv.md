---
apdl: "VSBV"
method: vsbv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vsbv
generated: 2026-08-22
tags: [mapdl-command]
---

# VSBV

PyMAPDL: `mapdl.vsbv(nv1='', nv2='', sepo='', keep1='', keep2='', **kwargs)`

Subtracts volumes from volumes.

## Parameters

**nv1**: Volume (or volumes, if picking is used) to be subtracted from. If ALL, use all selected volumes. Volumes specified in set `NV2` are removed from set `NV1`. If P, graphical picking is enabled (valid only in the GUI) and remaining fields are ignored. A component name may also be substituted for `NV1`.

**nv2**: Volume (or volumes, if picking is used) to subtract. If ALL, use all selected volumes (except those included in the `NV1` argument). A component name may also be substituted for `NV2`.

**sepo**

Behavior if the intersection of the `NV1` volumes and the `NV2` volumes is an area or areas:

- `(blank)` - The resulting volumes will share area(s) where they touch.
- `SEPO` - The resulting volumes will have separate, but coincident area(s) where they touch.

**keep1**

Specifies whether `NV1` volumes are to be deleted:

- `(blank)` - Use the setting of `KEEP` on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NV1` volumes after **VSBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NV1` volumes after **VSBV** operation (override [[boptn|BOPTN]] command settings).

**keep2**

Specifies whether `NV2` volumes are to be deleted:

- `(blank)` - Use the setting of `KEEP` on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NV2` volumes after **VSBV** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NV2` volumes after **VSBV** operation (override [[boptn|BOPTN]] command settings).

## Notes

Generates new volumes by subtracting the regions common to both `NV1` and `NV2` volumes (the intersection) from the `NV1` volumes. The intersection can be a volume(s) or area(s). If the intersection is an area and `SEPO` is blank, the `NV1` volume is divided at the area and the resulting volumes will be connected, sharing a common area where they touch. If `SEPO` is set to SEPO, `NV1` is divided into two unconnected volumes with separate areas where they touch. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. **VSBV**,ALL,ALL will have no effect because all the volumes in set `NV1` will have been moved to set `NV2`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSBV.html

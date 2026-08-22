---
apdl: "VINV"
method: vinv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vinv
generated: 2026-08-22
tags: [mapdl-command]
---

# VINV

PyMAPDL: `mapdl.vinv(nv1='', nv2='', nv3='', nv4='', nv5='', nv6='', nv7='', nv8='', nv9='', **kwargs)`

Finds the intersection of volumes.

## Parameters

**nv1**, **nv2**, **nv3**, **nv4**, **nv5**, **nv6**, **nv7**, **nv8**, **nv9**: Numbers of volumes to be intersected. If `NV1` = ALL, `NV2` to `NV9` are ignored, and the intersection of all selected volumes is found. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1`.

## Notes

Finds the common (not pairwise) intersection of volumes. The common intersection is defined as the regions shared (in common) by **all** volumes listed on this command. New volumes will be generated where the original volumes intersect. If the regions of intersection are only areas, new areas will be generated instead. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VINV.html

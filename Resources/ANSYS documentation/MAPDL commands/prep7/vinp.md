---
apdl: "VINP"
method: vinp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vinp
generated: 2026-08-22
tags: [mapdl-command]
---

# VINP

PyMAPDL: `mapdl.vinp(nv1='', nv2='', nv3='', nv4='', nv5='', nv6='', nv7='', nv8='', nv9='', **kwargs)`

Finds the pairwise intersection of volumes.

## Parameters

**nv1**, **nv2**, **nv3**, **nv4**, **nv5**, **nv6**, **nv7**, **nv8**, **nv9**: Numbers of volumes to be intersected pairwise. If `NV1` = ALL, `NV2` to `NV9` are ignored and the pairwise intersection of all selected volumes is found. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1`.

## Notes

Finds the pairwise intersection of volumes. The pairwise intersection is defined as all regions shared by any two or more volumes listed on this command. New volumes will be generated where the original volumes intersect pairwise. If the regions of pairwise intersection are only areas, new areas will be generated. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VINP.html

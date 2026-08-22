---
apdl: "VADD"
method: vadd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vadd
generated: 2026-08-22
tags: [mapdl-command]
---

# VADD

PyMAPDL: `mapdl.vadd(nv1='', nv2='', nv3='', nv4='', nv5='', nv6='', nv7='', nv8='', nv9='', **kwargs)`

Adds separate volumes to create a single volume.

## Parameters

**nv1**, **nv2**, **nv3**, **nv4**, **nv5**, **nv6**, **nv7**, **nv8**, **nv9**: Numbers of volumes to be added. If `NV1` = ALL, add all selected volumes and ignore `NV2` to `NV9`. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1`.

## Notes

Adds separate volumes to create a single volume. The original volumes (and their corresponding areas, lines and keypoints) will be deleted by default ( [[boptn|BOPTN]] ). See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. Concatenated entities are not valid with this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VADD.html

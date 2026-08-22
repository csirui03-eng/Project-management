---
apdl: "VMESH"
method: vmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.vmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# VMESH

PyMAPDL: `mapdl.vmesh(nv1='', nv2='', ninc='', **kwargs)`

Generates nodes and volume elements within volumes.

## Parameters

**nv1**, **nv2**, **ninc**: Mesh volumes from `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and all selected volumes ( [[vsel|VSEL]] ) are meshed. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

## Notes

Missing nodes required for the generated elements are created and assigned the lowest available numbers ( [[numstr|NUMSTR]] ). During a batch run and if elements already exist, a mesh abort will write an alternative database file ( `File.DBE` ) for possible recovery.

Tetrahedral mesh expansion ( [[mopt|MOPT]],TETEXPND, `Value` ) is supported for both the **VMESH** and [[fvmesh|FVMESH]] commands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VMESH.html

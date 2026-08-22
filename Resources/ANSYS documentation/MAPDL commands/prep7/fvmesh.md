---
apdl: "FVMESH"
method: fvmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.fvmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# FVMESH

PyMAPDL: `mapdl.fvmesh(keep='', **kwargs)`

Generates nodes and tetrahedral volume elements from detached exterior area elements (facets).

## Parameters

**keep**

Specifies whether to keep the area elements after the tetrahedral meshing operation is complete.

- `0` - Delete area elements (default).
- `1` - Keep area elements.

## Notes

The **FVMESH** command generates a tetrahedral volume mesh from a selected set of detached exterior area elements (facets). (Detached elements have no solid model associativity.) The area elements can be triangular-shaped, quadrilateral-shaped, or a mixture of the two.

The **FVMESH** command is in contrast to the [[vmesh|VMESH]] command, which requires a volume to be input.

The main tetrahedra mesher ( [[mopt|MOPT]],VMESH,MAIN) is the only tetrahedra mesher that supports the **FVMESH** command. The alternate tetrahedra mesher ( [[mopt|MOPT]],VMESH,ALTERNATE) does not support **FVMESH**. `MESH200` elements do not support **FVMESH**.

Tetrahedral mesh expansion ( [[mopt|MOPT]],TETEXPND, `Value` ) is supported for both the **FVMESH** and [[vmesh|VMESH]] commands. Tet-mesh expansion is the only mesh control supported by **FVMESH**.

Triangle- or quadrilateral-shaped elements may be used as input to the **FVMESH** command. Where quadrilaterals are used, the default behavior is for the pyramid-shaped elements to be formed at the boundary when the appropriate element type is specified. See the [[mopt|MOPT]],PYRA command for details.

The **FVMESH** command does not support multiple "volumes." If you have multiple volumes in your model, select the surface elements for one "volume," while making sure that the surface elements for the other volumes are deselected. Then use **FVMESH** to generate a mesh for the first volume. Continue this procedure by selecting one volume at a time and meshing it, until all of the volumes in the model have been meshed.

If an error occurs during the meshing operation, the area elements are kept even if `KEEP` = 0.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FVMESH.html

---
apdl: "CZMESH"
method: czmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.czmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# CZMESH

PyMAPDL: `mapdl.czmesh(ecomps1='', ecomps2='', kcn='', kdir='', value='', cztol='', **kwargs)`

Create and mesh an interface area composed of cohesive zone elements.

## Parameters

**ecomps1**: Component name or number for the group of plane or solid structural elements adjacent to the interface being meshed.

**ecomps2**: Component name or number for the opposing (from `ecomps1` ) group of plane or solid structural elements adjacent to the interface being meshed.

**kcn**: Coordinate system number for the separation surface and normal direction. (if `ecomps1` and `ecomps2` not specified)

**kdir**: Direction (x, y, or z) normal to separation surface in the `KCN` coordinate system (if `ecomps1` and `ecomps2` not specified).

**value**: Coordinate value along the `KDIR` axis at which to locate the interface (if `ecomps1` and `ecomps2` not specified).

**cztol**

Optional absolute tolerance about `VALUE` (if `ecomps1` and `ecomps2` not specified). Allows nodes occurring slightly above or below the separation to be grouped properly. The following expression represents the default value:

(equation not available in the PyMAPDL source, see the Ansys help page)

## Notes

**CZMESH** is used on a mesh with shared nodes at the interface.

If `ecomps1` and `ecomps2` are specified, the **CZMESH** command creates/meshes interface elements ( `INTER202`, `INTER203`, `INTER204`, `INTER205` ) along the boundary between the two components or groups of elements.

The elements in each of the components or groups of elements share nodes with each other and also with the interface elements. This one-element thick boundary of interface elements splits the body between the two components or groups of elements.

Subsequent separation (delamination and failure) of the interface zone results in an increasing displacement between the nodes (within the interface element) along the cohesive zone elements. Unless otherwise specified, the **CZMESH** command analyzes the configuration and geometry of the adjacent structural elements and provides the appropriate interface element.

The **CZMESH** operation copies any nodal temperatures that you have defined on the split surface of the original mesh from the original nodes to the newly created coincident duplicate nodes. Displacements, forces, and other boundary conditions, however, are not copied; therefore, apply boundary conditions and loadings after issuing **CZMESH**.

If using **CZMESH** to generate interface elements ( `INTER202` and `INTER205` ) in a [VCCT- based crack-growth simulation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_STR_VCCT.html#vcctsimassum), be aware that those elements do not support degenerate shapes. Examine the resulting mesh, therefore, to verify correct element connectivity around the crack tip.

This command does not support mesh regions with non-solid elements (such as surface-effect and shell elements).

This command is valid for structural analyses only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CZMESH.html

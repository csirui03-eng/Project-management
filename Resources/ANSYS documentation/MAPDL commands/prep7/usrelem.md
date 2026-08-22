---
apdl: "USRELEM"
method: usrelem
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.usrelem
generated: 2026-08-22
tags: [mapdl-command]
---

# USRELEM

PyMAPDL: `mapdl.usrelem(nnodes='', ndim='', keyshape='', nreal='', nsavevars='', nrsltvar='', keyansmat='', nintpnts='', kestress='', keysym='', **kwargs)`

Specifies the characteristics of the user-defined element `USER300`.

## Parameters

**nnodes**: The number of nodes.

**ndim**: The number of dimensions (of nodal coordinates). Valid values are 2 or 3.

**keyshape**

One of the following element shape options:

- `ANYSHAPE` - Any shape (that is, no specified shape). This value is the default.
- `POINT` - Point.
- `LINE` - Straight line.
- `TRIAN` - Triangle.
- `QUAD` - Quadrilateral. This shape can be degenerated to a triangle.
- `TET` - Tetrahedron.
- `BRICK` - Brick. This shape can be degenerated to a wedge, pyramid, or tetrahedron.

**nreal**: The number of real constants.

**nsavevars**: The number of saved variables.

**nrsltvar**: The number of variables saved in results files.

**keyansmat**

Key for element formulation control:

- `0` - Create your own material codes within the element formulation. In this case, the real constants are available to input material properties. You can also input linear material properties via [[mp|MP]] and [[mpdata|MPDATA]] commands.
- `1` - Use standard material routines or the UserMat subroutine to form structural material data. Material properties must be input in the standard way (as you would for non-user-defined elements). This value is invalid when KeyShape = ANYSHAPE.

**nintpnts**: The maximum number of integration points (used when `KEYANSMAT` = 1).

**kestress**

Key for the element stress state (used when `KEYANSMAT` = 1):

- `0` - Plane stress elements.
- `1` - Axisymmetric elements.
- `2` - Plane strain elements.
- `3` - 3D solid elements.
- `4` - 3D solid-shell elements.
- `5` - Generalized plane strain elements.
- `6` - Beam elements.
- `7` - Link/truss elements.
- `8` - 3D shell elements.
- `9` - Axisymmetric shell elements.

**keysym**

Key for specifying whether element stiffness matrices are symmetric or unsymmetric:

- `0` - Symmetric.
- `1` - Unsymmetric.

## Notes

The **USRELEM** command specifies the characteristics of the user-defined element `USER300`.

Although you can intersperse other commands as necessary for your analysis, issue the **USRELEM** command as part of the following general sequence of commands:

Issue the [[et|ET]] command for element `USER300`, followed by the related [[type|TYPE]] command.

Issue both the **USRELEM** and [[usrdof|USRDOF]] commands (in either order).

Define your element using `USER300`.

The number of real constants ( `NREAL` ) can refer to geometry quantities, material quantities, or any parameters for element formulation.

ANSYS saves variables in the `.esav` file to preserve element data when you specify a positive `NSAVEVARS` value. When `KEYANSMAT` = 0, all variables of both material and kinematic formulation are saved. When `KEYANSMAT` = 1, only the variables for kinematic formulation (such as deformation gradient tensor) are saved; in this case, the material routine saves all necessary material data automatically.

Element data saved in results files ( `NRSLTVAR` ) are accessible only as nonsummable miscellaneous data. ANSYS saves stress and total strain data for structural elements in the `.rst` file automatically (as it does for equivalent variables such as thermal gradient and thermal flux in thermal elements); therefore, `NRSLTVAR` does not need to include stress and total strain data.

To learn more about creating user-defined elements, see [Creating a New Element](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Hlp_P_UPFNEWEL.html#upfcreateelem2)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USRELEM.html

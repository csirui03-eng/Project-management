---
apdl: "SETRAN"
method: setran
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.superelements.Superelements.setran
generated: 2026-08-22
tags: [mapdl-command]
---

# SETRAN

PyMAPDL: `mapdl.setran(sename='', kcnto='', inc='', file='', ext='', dx='', dy='', dz='', norot='', **kwargs)`

Creates a superelement from an existing superelement.

## Parameters

**sename**: The name (case-sensitive) of the file containing the original superelement matrix created by the generation pass ( `Sename.SUB` ). The default is the current `Jobname`. If `Sename` is a number, it is the element number of a previously defined superelement in the current use pass.

**kcnto**: The reference number of the coordinate system to where the superelement is to be transferred. The default is the global Cartesian system. Transfer occurs from the active coordinate system.

**inc**: The node offset. The default is zero. All new element node numbers are offset from those on the original by `INC`.

**file**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. This field requires input.

**ext**: Filename extension (eight-character maximum). The extension defaults to SUB.

**dx**, **dy**, **dz**: Node location increments in the global Cartesian coordinate system. Defaults to zero.

**norot**

Node rotation key:

- `0` - The nodal coordinate systems of the transferred superelement rotate into the `KCNTO` system. (That is, the nodal coordinate systems rotate with the superelement.) The superelement matrices remain unchanged. This value is the default.
- `1` - The nodal coordinate systems do not rotate. (That is, they remain fixed in their original global orientation.) The superelement matrices and load vectors are modified if any rotations occur.

## Notes

The **SETRAN** command creates a superelement from an existing superelement and writes the new element to a file. You can then issue an [[se|SE]] command to read the new element (during the [use pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/an9Auq1d6ldm.html#advobsl5jla062999) ).

You can create a superelement from an original by:

- Transferring the original's geometry from the active coordinate system into another coordinate system ( `KCNTO` )
- Offsetting its geometry in the global Cartesian coordinate system ( `DX`, `DY`, and `DZ` )
- Offsetting its node numbers ( `INC` ).

A combination of methods is valid. If you specify both the geometry transfer and the geometry offset, the transfer occurs first.

If you specify rotation of the transferred superelement's nodal coordinate systems into the `KCNTO` system ( `NOROT` = 0), the rotated nodes cannot be coupled via the [[cp|CP]] command; in this case, issue the [[ce|CE]] command instead. If you specify no rotation of the nodal coordinate systems ( `NOROT` = 1) for models with displacement degrees of freedom, and `KCNTO` is not the active system, the superelement `Sename` must have six MDOF at each node that has MDOF; therefore, only elements with all six structural DOFs are valid in such cases.

There is no limit to the number of copies that can be made of a superelement, provided the copies are all generated from the same original superelement. However, nested copies are limited to five. In other words, the total number of different `Sename` usages on the **SETRAN** and [[sesymm|SESYMM]] commands is limited to five.

This command is not supported if the original superelement matrix was created in a component mode synthesis analysis generation pass with the element results calculation activated ( `Elcalc` = YES on [[cmsopt|CMSOPT]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SETRAN.html

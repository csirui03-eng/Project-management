---
apdl: "UPGEOM"
method: upgeom
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.upgeom
generated: 2026-08-22
tags: [mapdl-command]
---

# UPGEOM

PyMAPDL: `mapdl.upgeom(factor='', lstep='', sbstep='', fname='', ext='', upesys='', **kwargs)`

Adds displacements from a previous analysis and updates the geometry to the deformed configuration.

## Parameters

**factor**: Multiplier for displacements being added to coordinates. The value 1.0 adds the full value of the displacements to the geometry of the finite element model. Defaults to 1.0.

**lstep**: Load step number of data to be imported. Defaults to the last load step.

**sbstep**: Substep number of data to be imported. Defaults to the last substep.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The field must be input (no default).

**ext**: Filename extension (eight-character maximum). The extension must be `RST`.

**upesys**

Update behavior for the element coordinate system ( [[esys|ESYS]] ):

0 - Do not update the element coordinate system (default).

1 - Update the element coordinate system to match the material orientation from a previous analysis.

## Notes

This command updates the geometry of the finite element model according to the displacement results of the previous analysis and creates a revised geometry at the deformed configuration. This command works on all nodes (default) or on a selected set of nodes. If this command is issued repeatedly, it creates a revised geometry of the finite element model in a cumulative fashion, that is, it adds displacement results on the previously generated deformed geometry. The solid model geometry is not updated by this command.

When **UPGEOM** is issued, the current finite element model is overwritten by finite element information from the results file. For this reason, it is important that the finite element information in the results file matches the finite element model in which the nodal coordinates are being updated. No changes should be made to the model before the **UPGEOM** command is issued.

`UPESYS` = 1 is available for homogeneous structural solid elements ( `SOLID185`, `SOLID186`, and `SOLID187` ) only and generates only Cartesian coordinate systems. The option is especially useful when conducting a [loop test](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strnonlininversesol.html#figlooptest) when orthotropic material is used. For more information, see [Nonlinear Static Analysis with Inverse Solving](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strnonlininversesol.html#strinvsolvlimit)

> [!WARNING]
> Orientation nodes for beams and pipes always have zero displacements. Therefore, although this command may alter the locations of other beam and pipe nodes, it has no effect on orientation nodes. Carefully inspect the element coordinate systems on the updated model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UPGEOM.html

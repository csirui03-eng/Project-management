---
apdl: "IGESOUT"
method: igesout
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.igesout
generated: 2026-08-22
tags: [mapdl-command]
---

# IGESOUT

PyMAPDL: `mapdl.igesout(fname='', ext='', att='', **kwargs)`

Writes solid model data to a file in IGES Version 5.1 format.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to IGES if `Fname` is blank.

**att**

Attribute key:

- `0` - Do not write assigned numbers and attributes of the solid model entities to the IGES file (default).
- `1` - Write assigned numbers and attributes of solid model entities (keypoints, lines, areas, volumes) to the IGES file. Attributes include MAT, TYPE, REAL, and ESYS specifications as well as associated solid model loads and meshing (keypoint element size, number of line divisions and spacing ratio) specifications.

## Notes

Causes the selected solid model data to be written to a coded file in the IGES Version 5.1 format. Previous data on this file, if any, are overwritten.

Keypoints that are not attached to any line are written to the output file as IGES entity 116 (Point).

Lines that are not attached to any area are written to the output file as either IGES Entity 100 (Circular Arc), 110 (Line), or 126 (Rational B-Spline Curve) depending upon whether the Mechanical APDL entity was defined as an arc, straight line, or spline.

Areas are written to the output file as IGES Entity 144 (Trimmed Parametric Surface).

Volumes are written to the output file as IGES entity 186 (Manifold Solid B-Rep Object).

Solid model entities to be written must have all corresponding lower level entities selected (use [[allsel|ALLSEL]],BELOW,ALL) before issuing command.

Concatenated lines and areas are not written to the IGES file; however, the entities that comprise the concatenated entities are written.

> [!WARNING]
> Section properties assigned to areas, lines and other solid model entities are not maintained when the model is exported via **IGESOUT**.
>
> Issuing **IGESOUT** after generating a beam mesh with orientation nodes causes the orientation keypoints specified for the line ( [[latt|LATT]] ) to no longer be associated with the line and are therefore not written out to the IGES file. The line does not recognize that orientation keypoints were ever assigned to it. Therefore, **IGESOUT** does not support (for beam meshing) any line operation relying on solid model associativity. (For example, meshing the areas adjacent to the meshed line, plotting the line that contains the orientation nodes, or clearing the mesh from the line that contains orientation nodes may not work as expected.) For more information about beam meshing, see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IGESOUT.html

---
apdl: "SECWRITE"
method: secwrite
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# SECWRITE

PyMAPDL: `mapdl.secwrite(fname='', ext='', elem_type='', **kwargs)`

Creates an ASCII file containing user mesh section information.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname` if `Fname` is left blank.

**ext**: Filename extension (eight-character maximum). The extension defaults to SECT if `Ext` is left blank.

**elem_type**: Element type attribute pointer ( [[et|ET]] ) for the elements that are part of the section. See [[secread|SECREAD]] for a detailed description.

## Notes

Before creating a user mesh file, first create a model using 2D meshing. Use `PLANE183` or `MESH200` with KEYOPT(1) = 7 (quadrilateral with 8 nodes option) to model the cells. **SECWRITE** creates an ASCII file that contains information about the nodes and cells that describe a beam section. For detailed information on how to create a user mesh file, see [Creating Custom Cross Sections with a User-defined Mesh](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR15_4.html#) in the [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECWRITE.html

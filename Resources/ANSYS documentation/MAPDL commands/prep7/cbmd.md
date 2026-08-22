---
apdl: "CBMD"
method: cbmd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.cbmd
generated: 2026-08-22
tags: [mapdl-command]
---

# CBMD

PyMAPDL: `mapdl.cbmd(row='', c_r__r='', c_r__rplus1='', c_r__rplus2='', c_r__rplus3='', c_r__rplus4='', c_r__rplus5='', **kwargs)`

Specifies preintegrated section mass matrix for composite-beam sections.

## Parameters

**row**: Row number of the matrix.

**c_r__r**, **c_r__rplus1**, **c_r__rplus2**, **c_r__rplus3**, **c_r__rplus4**, **c_r__rplus5**: Upper triangle of the cross-section mass matrix **\[C\]**.

## Notes

With a unit beam length, the section mass matrix relates the resultant forces and torques to accelerations and angular accelerations as follows (applicable to the local element coordinate system):

(equation not available in the PyMAPDL source, see the Ansys help page)

The **CBMD** command, one of several [composite beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#), specifies the section mass matrix (submatrix \[ **C** \] data) for a composite beam section. The section data defined is associated with the section most recently defined ( [[sectype|SECTYPE]] ) at the specified temperature ( [[cbtmp|CBTMP]] ).

Unspecified values default to zero.

Related commands are [[cbtmp|CBTMP]], [[cbte|CBTE]], and [[cbmx|CBMX]].

For complete information, see [Using Preintegrated Composite Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CBMD.html

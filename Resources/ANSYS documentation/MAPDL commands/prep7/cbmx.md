---
apdl: "CBMX"
method: cbmx
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.cbmx
generated: 2026-08-22
tags: [mapdl-command]
---

# CBMX

PyMAPDL: `mapdl.cbmx(row='', s_r__r='', s_r__rplus1='', s_r__rplus2='', s_r__rplus3='', s_r__rplus4='', s_r__rplus5='', s_r__rplus6='', **kwargs)`

Specifies preintegrated cross-section stiffness for composite beam sections.

## Parameters

**row**: Row number of the matrix.

**s_r__r**, **s_r__rplus1**, **s_r__rplus2**, **s_r__rplus3**, **s_r__rplus4**, **s_r__rplus5**, **s_r__rplus6**: Upper triangle of the cross-section stiffness matrix **\[S\]**.

## Notes

The behavior of beam elements is governed by the generalized-stress/generalized-strain relationship of the [form](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#) :

(equation not available in the PyMAPDL source, see the Ansys help page)

The **CBMX** command, one of several [composite beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#), specifies the cross-section stiffness matrix (submatrix \[ **S** \] data) for a composite beam section. The section data defined is associated with the section most recently defined ( [[sectype|SECTYPE]] ) at the specified temperature ( [[cbtmp|CBTMP]] ).

Unspecified values default to zero.

Related commands are [[cbtmp|CBTMP]], [[cbte|CBTE]], and [[cbmd|CBMD]].

For complete information, see [Using Preintegrated Composite Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CBMX.html

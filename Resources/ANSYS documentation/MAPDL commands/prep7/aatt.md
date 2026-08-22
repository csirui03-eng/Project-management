---
apdl: "AATT"
method: aatt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.aatt
generated: 2026-08-22
tags: [mapdl-command]
---

# AATT

PyMAPDL: `mapdl.aatt(mat='', real='', type_='', esys='', secn='', **kwargs)`

Associates element attributes with the selected, unmeshed areas.

## Parameters

**mat**: The material number to be associated with selected, unmeshed areas.

**real**: The real constant set number to be associated with selected, unmeshed areas.

**type_**: The type number to be associated with selected, unmeshed areas.

**esys**: The coordinate system number to be associated with selected, unmeshed areas.

**secn**: The section number to be associated with selected unmeshed areas.

## Notes

Areas subsequently generated from the areas will also have these attributes. These element attributes will be used when the areas are meshed. If an area does not have attributes associated with it (by this command) at the time it is meshed, the attributes are obtained from the then current [[mat|MAT]], [[real|REAL]], [[type|TYPE]], [[esys|ESYS]], and [[secnum|SECNUM]] command settings. Reissue the **AATT** command (before areas are meshed) to change the attributes. A zero (or blank) argument removes the corresponding association. If any of the arguments `MAT`, `REAL`, `TYPE`, `ESYS`, or `SECN` are defined as -1, then that value will be left unchanged in the selected set.

In some cases, Mechanical APDL can proceed with an area meshing operation even when no logical element type has been assigned via **AATT**, `TYPE` or [[type|TYPE]]. For more information, see the discussion on setting element attributes in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_5.html#modmeshvaidck31400) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AATT.html

---
apdl: "VATT"
method: vatt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.vatt
generated: 2026-08-22
tags: [mapdl-command]
---

# VATT

PyMAPDL: `mapdl.vatt(mat='', real='', type_='', esys='', secnum='', **kwargs)`

Associates element attributes with the selected, unmeshed volumes.

## Parameters

**mat**, **real**, **type_**, **esys**, **secnum**: Material number, real constant set number, type number, coordinate system number, and section number to be associated with selected, unmeshed volumes.

## Notes

These element attributes will be used when the volumes are meshed. If a volume does not have attributes associated with it (by this command) at the time it is meshed, the attributes are obtained from the then current [[mat|MAT]], [[real|REAL]], [[type|TYPE]], [[esys|ESYS]], and [[secnum|SECNUM]] command settings. Reissue the **VATT** command (before volumes are meshed) to change the attributes. A zero (or blank) argument removes the corresponding association.

If any of the arguments `MAT`, `REAL`, `TYPE`, `ESYS` or `SECNUM` are defined as -1, then that value will be left unchanged in the selected set.

In some cases, the program can proceed with a volume meshing operation even when no logical element type has been assigned via **VATT**, `TYPE` or [[type|TYPE]]. For more information, see the discussion on setting element attributes in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) of the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VATT.html

---
apdl: "KATT"
method: katt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.katt
generated: 2026-08-22
tags: [mapdl-command]
---

# KATT

PyMAPDL: `mapdl.katt(mat='', real='', type_='', esys='', **kwargs)`

Associates attributes with the selected, unmeshed keypoints.

## Parameters

**mat**, **real**, **type_**, **esys**: Material number, real constant set number, type number, and coordinate system number to be associated with selected, unmeshed keypoints.

## Notes

Keypoints subsequently generated from the keypoints will also have these attributes. These element attributes will be used when the keypoints are meshed. If a keypoint does not have attributes associated with it (by this command) at the time it is meshed, the attributes are obtained from the then current [[mat|MAT]], [[real|REAL]], [[type|TYPE]], and [[esys|ESYS]] command settings. Reissue the **KATT** command (before keypoints are meshed) to change the attributes. A zero (or blank) argument removes the corresponding association.

If any of the arguments `MAT`, `REAL`, `TYPE`, or `ESYS` are defined as -1, then that value will be left unchanged in the selected set.

In some cases, Mechanical APDL can proceed with a keypoint meshing operation even when no logical element type has been assigned via **KATT**, `TYPE` or [[type|TYPE]]. For more information, see the discussion on setting element attributes in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) eshing Your Solid Model in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KATT.html

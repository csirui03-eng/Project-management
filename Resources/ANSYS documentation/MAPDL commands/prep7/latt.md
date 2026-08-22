---
apdl: "LATT"
method: latt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.latt
generated: 2026-08-22
tags: [mapdl-command]
---

# LATT

PyMAPDL: `mapdl.latt(mat='', real='', type_='', kb='', ke='', secnum='', **kwargs)`

Associates element attributes with the selected, unmeshed lines.

## Parameters

**mat**, **real**, **type_**: Material number, real constant set number, and type number to be associated with selected, unmeshed lines.

**kb**, **ke**: Beginning and ending orientation keypoints to be associated with selected, unmeshed lines. Mechanical APDL uses the location of these keypoints to determine how to orient beam cross sections during beam meshing. Beam elements may be created along a line with a constant orientation by specifying only one orientation keypoint ( `KB` ), or a pre-twisted beam may be created by selecting different orientation keypoints at each end of the line ( `KB` and `KE` ). (For a line bounded by two keypoints ( `KP1` and `KP2` ), the orientation vector at the beginning of the line extends from `KP1` to `KB`, and the orientation vector at the end of the line extends from `KP2` to `KE`. The orientation vectors are used to compute the orientation nodes of the elements.)

**secnum**: Section identifier to be associated with selected, unmeshed lines. For details, see the description of the [[sectype|SECTYPE]] and [[secnum|SECNUM]] commands.

## Notes

The element attributes specified by the **LATT** command will be used when the lines are meshed.

Lines subsequently generated from the lines will also have the attributes specified by `MAT`, `REAL`, `TYPE`, and `SECNUM`. If a line does not have these attributes associated with it (by this command) at the time it is meshed, the attributes are obtained from the then current [[mat|MAT]], [[real|REAL]], [[type|TYPE]], and [[secnum|SECNUM]] command settings.

In contrast, the values specified by `KB` and `KE` apply only to the selected lines; t hat is, lines subsequently generated from these lines will not share these attributes. Similarly, if a line does not have `KB` and `KE` attributes associated with it via the **LATT** command at the time it is meshed, Mechanical APDL cannot obtain the attributes from elsewhere. See the discussion on beam meshing in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information.

Reissue the **LATT** command (before lines are meshed) to change the attributes. A zero (or blank) argument removes the corresponding association. If any of the arguments are defined as -1, then that value will be left unchanged in the selected set.

In some cases, Mechanical APDL can proceed with a line meshing operation even when no logical element type has been assigned via **LATT**, `TYPE` or [[type|TYPE]]. See [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information about setting element attributes.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LATT.html

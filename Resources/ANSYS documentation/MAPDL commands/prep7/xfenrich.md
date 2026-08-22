---
apdl: "XFENRICH"
method: xfenrich
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.xfenrich
generated: 2026-08-22
tags: [mapdl-command]
---

# XFENRICH

PyMAPDL: `mapdl.xfenrich(enrichmentid='', compname='', mat_id='', method='', radius='', snaptoler='', **kwargs)`

Defines parameters associated with crack propagation using XFEM

## Parameters

**enrichmentid**: An alphanumeric name assigned to identify the enrichment. The name can contain up to 32 characters and must begin with an alphabetic character. Alphabetic characters, numbers, and underscores are valid.

**compname**: Name of the element set component for which initial cracks are defined and possibly propagated.

**mat_id**: Material ID number referring to cohesive zone material behavior on the initial crack. If 0 or not specified, the initial crack is assumed to be free of cohesive zone behavior. Used only with the phantom-node XFEM method ( `Method` ).

**method**

PHAN - Use [phantom-node-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig2) XFEM (default).

SING - Use [singularity-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig1) XFEM.

**radius**: Radius defining the region around the crack tip encompassing the set of elements to be influenced by the crack-tip singularity effects. Default = 0.0. Used only in singularity-based XFEM.

**snaptoler**: Snap tolerance to snap the crack tip to the closest crack face along the extension direction. Default = 1.0E-6. Used only in singularity-based XFEM.

## Notes

If `MAT_ID` is specified, the cohesive zone behavior is described by the [bilinear cohesive law](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/cozonemats.html#eq882acced-35ea-449a-9f59-1a8f1175f44c).

If issuing multiple **XFENRICH** commands, the element components ( `CompName` ) should not intersect (that is, the element components should not have any common elements between them).

When multiple **XFENRICH** commands are issued in an analysis, combining the phantom-node-based method ( `Method` = PHAN) and the singularity-based method ( `Method` = SING) is not valid. Only one XFEM method per analysis is allowed.

This command is valid in PREP7 ( [[prep7|/PREP7]] ) only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XFENRICH.html

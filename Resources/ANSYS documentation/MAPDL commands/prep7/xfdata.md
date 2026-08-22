---
apdl: "XFDATA"
method: xfdata
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.xfdata
generated: 2026-08-22
tags: [mapdl-command]
---

# XFDATA

PyMAPDL: `mapdl.xfdata(enrichmentid='', lsm='', elemnum='', nodenum='', phi='', psi='', **kwargs)`

Defines a crack in the model by specifying nodal level set values

## Parameters

**enrichmentid**: Name of the enrichment specified via the associated [[xfenrich|XFENRICH]] command.

**lsm**: Indicates that level set values are being specified (default).

**elemnum**: Element number.

**nodenum**: Node number associated with the specified element `ELNUM`.

**phi**: Signed normal distance of the node from the crack.

**psi**: Signed normal distance of the node from the crack tip (or crack front). Used only in the [singularity-based](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemfig1) XFEM method.

## Notes

Issue the **XFDATA** command multiple times as needed to specify nodal level set values for all nodes of an element.

This command is valid in PREP7 ( [[prep7|/PREP7]] ) only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XFDATA.html

---
apdl: "XFCRKMESH"
method: xfcrkmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.xfcrkmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# XFCRKMESH

PyMAPDL: `mapdl.xfcrkmesh(enrichmentid='', elemcomp='', nodecomp='', **kwargs)`

Defines a crack in the model when the crack surface is discretized by `MESH200` elements

## Parameters

**enrichmentid**: Name of the enrichment specified via the associated [[xfenrich|XFENRICH]] command.

**elemcomp**: Name of the element component consisting of `MESH200` elements that form the crack surface.

**nodecomp**: Name of the node component consisting of the crack front nodes of the crack surface.

## Notes

Used in an [XFEM-based crack analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences), this command defines a crack in the model when the crack surface is discretized by `MESH200` elements. For more informatiom, see [MESH200 Element Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#)

Issue the **XFCRKMESH** command multiple times as needed to define multiple crack surfaces in the model.

This command is valid in PREP7 ( [[prep7|/PREP7]] ) only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XFCRKMESH.html

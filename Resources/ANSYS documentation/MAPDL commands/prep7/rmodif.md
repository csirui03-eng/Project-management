---
apdl: "RMODIF"
method: rmodif
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.rmodif
generated: 2026-08-22
tags: [mapdl-command]
---

# RMODIF

PyMAPDL: `mapdl.rmodif(nset='', stloc='', v1='', v2='', v3='', v4='', v5='', v6='', **kwargs)`

Modifies real constant sets.

## Parameters

**nset**

Number of existing real constant set to be modified.

The labels CONT and GCN are also valid input for defining or modifying real constants associated with contact elements (see [[rmodif#Notes|Notes).]]

**stloc**: Starting location in table for modifying data. For example, if `STLOC` = 1, data input in the `V1` field is the first constant in the set. If `STLOC` = 7, data input in the `V1` field is the seventh constant in the set, etc. Must be greater than zero.

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**: New values assigned to constants in the next five locations. If blank, the value remains unchanged.

## Notes

Allows modifying (or adding) real constants to an existing set ( [[r|R]] ) at any location.

Specify `NSET` = CONT to define or modify real constants for all real constant sets associated with contact elements in pair-based contact definitions. Specify `NSET` = GCN to define or modify real constants for real constant sets that were previously assigned by the [[gcdef|GCDEF]] command; that is, real constants used in [general contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html) interactions.

This command is also valid in SOLUTION. For important information about using this command within the solution phase, see in the [Advanced Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advoceanloading.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RMODIF.html

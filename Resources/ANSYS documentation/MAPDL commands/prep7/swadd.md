---
apdl: "SWADD"
method: swadd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.swadd
generated: 2026-08-22
tags: [mapdl-command]
---

# SWADD

PyMAPDL: `mapdl.swadd(ecomp='', shrd='', ncm1='', ncm2='', ncm3='', ncm4='', ncm5='', ncm6='', ncm7='', ncm8='', ncm9='', **kwargs)`

Adds more surfaces to an existing spot weld set.

## Parameters

**ecomp**: Name of an existing spot weld set that was previously defined using [[swgen|SWGEN]].

**shrd**: Search radius. Defaults to 4 times the spot weld radius defined for the spot weld set ( `SWRD` on [[swgen|SWGEN]] ).

**ncm1**, **ncm2**, **ncm3**, **ncm4**, **ncm5**, **ncm6**, **ncm7**, **ncm8**, **ncm9**: Surfaces to be added to the spot weld set. Each surface can be input as a predefined node component or a meshed area number.

## Notes

This command adds surfaces to an existing spot weld set defined by the [[swgen|SWGEN]] command. You can add additional surfaces by repeating the **SWADD** command. However, the maximum number of allowable surfaces (including the 2 surfaces used for the original set defined by [[swgen|SWGEN]] ) for each spot weld set is 11. See [Adding Surfaces to a Basic Set](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_spwdset.html#ctecreordersurf) for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SWADD.html

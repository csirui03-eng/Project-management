---
apdl: "SWLIST"
method: swlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.swlist
generated: 2026-08-22
tags: [mapdl-command]
---

# SWLIST

PyMAPDL: `mapdl.swlist(ecomp='', **kwargs)`

Lists spot weld sets.

## Parameters

**ecomp**: Name of an existing spot weld set that was previously defined using [[swgen|SWGEN]]. If `Ecomp` = ALL (default), all spot weld sets are listed.

## Notes

This command lists spot weld node, beam, and contact pair information for all defined spot weld sets, or for the specified set. To ensure that all defined spotwelds are listed, issue [[cmsel|CMSEL]],ALL (to select all components) before issuing the **SWLIST** command.

When **SWLIST** is issued in POST1, the beam forces and moments are output. For the case of a deformable spot weld, the stresses are also output in the beam local coordinate system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SWLIST.html

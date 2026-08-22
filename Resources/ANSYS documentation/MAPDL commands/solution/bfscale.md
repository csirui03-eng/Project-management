---
apdl: "BFSCALE"
method: bfscale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfscale
generated: 2026-08-22
tags: [mapdl-command]
---

# BFSCALE

PyMAPDL: `mapdl.bfscale(lab='', fact='', tbase='', **kwargs)`

Scales body-force loads at nodes.

## Parameters

**lab**

Valid body load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**fact**: Scale factor for the nodal body load values. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor. The scale factor is not applied to body load phase angles.

**tbase**: Base temperature for temperature difference. Used only with `Lab` = TEMP. Scale factor is applied to the temperature difference ( `T` - `TBASE` ) and then added to `TBASE`. `T` is the current temperature.

## Notes

Scales body-force loads in the database on the selected nodes. Issue the [[bflist|BFLIST]] command to list the nodal body loads. Solid model boundary conditions are not scaled by this command, but boundary conditions on the FE model are scaled. Such scaled FE boundary conditions may still be overwritten by unscaled solid model boundary conditions if a subsequent boundary condition transfer occurs.

**BFSCALE** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFSCALE.html

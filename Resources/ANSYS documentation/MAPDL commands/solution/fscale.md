---
apdl: "FSCALE"
method: fscale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.fscale
generated: 2026-08-22
tags: [mapdl-command]
---

# FSCALE

PyMAPDL: `mapdl.fscale(rfact='', ifact='', **kwargs)`

Scales force load values in the database.

## Parameters

**rfact**: Scale factor for the real component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**ifact**: Scale factor for the imaginary component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

## Notes

Scales force load (force, heat flow, etc.) values in the database. Scaling applies to the previously defined values for the selected nodes ( [[nsel|NSEL]] ) and the selected force labels ( [[dofsel|DOFSEL]] ). Issue [[flist|FLIST]] command to review results. Solid model boundary conditions are not scaled by this command, but boundary conditions on the FE model are scaled. Such scaled FE boundary conditions may still be overwritten by unscaled solid model boundary conditions if a subsequent boundary condition transfer occurs.

**FSCALE** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSCALE.html

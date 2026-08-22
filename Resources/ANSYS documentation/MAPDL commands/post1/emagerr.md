---
apdl: "EMAGERR"
method: emagerr
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.emagerr
generated: 2026-08-22
tags: [mapdl-command]
---

# EMAGERR

PyMAPDL: `mapdl.emagerr(**kwargs)`

Calculates the relative error in an electrostatic or electromagnetic field analysis.

## Notes

The relative error is an approximation of the mesh discretization error associated with a solution. It is based on the discrepancy between the unaveraged, element-nodal field values and the averaged, nodal field values. The calculation is valid within a material boundary and does not consider the error in continuity of fields across dissimilar materials.

For electrostatics, the field values evaluated are the electric field strength (EFSUM) and the electric flux density (DSUM). A relative error norm of each is calculated on a per-element basis and stored in the element table ( [[etable|ETABLE]] ) with the labels EF_ERR and D_ERR. Normalized error values EFN_ERR and DN_ERR are also calculated and stored in the element table. Corresponding quantities for electromagnetics are H_ERR, B_ERR, HN_ERR, and BN_ERR, which are calculated from the magnetic field intensity (HSUM) and the magnetic flux density (BSUM). The normalized error value is the relative error norm value divided by the peak element-nodal field value for the currently selected elements.

Use the [[pletab|PLETAB]] and [[pretab|PRETAB]] commands to plot and list the error norms and normalized error values.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMAGERR.html

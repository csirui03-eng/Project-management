---
apdl: "SENERGY"
method: senergy
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.senergy
generated: 2026-08-22
tags: [mapdl-command]
---

# SENERGY

PyMAPDL: `mapdl.senergy(opt='', antype='', **kwargs)`

Determines the stored magnetic energy or co-energy.

## Parameters

**opt**

Item to be calculated:

- `0` - Stored magnetic energy.
- `1` - Stored magnetic co-energy.

**antype**

Analysis type:

- `0` - Static or transient.
- `1` - Harmonic.

## Notes

**SENERGY** invokes a Mechanical APDL macro which calculates the stored magnetic energy or co- energy for all selected elements. (For a harmonic analysis, the macro calculates a time-averaged (rms) stored energy.)

A summary table listing the energy by material number is generated. The energy density is also calculated and stored on a per-element basis in the element table ( [[etable|ETABLE]] ) with the label MG_ENG (energy density) or MG_COENG (co-energy density). The macro erases all other items in the element table and retains only the energy density or co-energy density.

Issue [[pletab|PLETAB]] and [[pretab|PRETAB]] to plot and list the energy density.

The macro is valid for static and low-frequency magnetic field formulations.

The macro will not calculate stored energy and co-energy for the following cases:

- Orthotropic nonlinear permanent magnets.
- Orthotropic nonlinear permeable materials.
- Temperature dependent materials.

**SENERGY** is restricted to MKSA units.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SENERGY.html

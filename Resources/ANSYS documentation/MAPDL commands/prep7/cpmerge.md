---
apdl: "CPMERGE"
method: cpmerge
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cpmerge
generated: 2026-08-22
tags: [mapdl-command]
---

# CPMERGE

PyMAPDL: `mapdl.cpmerge(lab='', **kwargs)`

Merges different couple sets with duplicate degrees of freedom into one couple set.

## Parameters

**lab**: Degree of freedom label for coupled nodes (in the nodal coordinate system). Valid labels are: Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations) (in radians). Thermal labels: TEMP, TBOT, TE2, TE3,..., TTOP (temperature). Fluid labels: PRES (pressure); VX, VY, or VZ (velocities). Electric labels: VOLT (voltage); EMF (electromotive force drop); CURR (current). Magnetic labels: MAG (scalar magnetic potential); AZ (vector magnetic potential); CURR (current). Diffusion label: CONC (concentration). The degree of freedom set is determined from all element types defined and the [[dof|DOF]] command, if used.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPMERGE.html

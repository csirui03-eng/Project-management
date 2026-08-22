---
apdl: "CPINTF"
method: cpintf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cpintf
generated: 2026-08-22
tags: [mapdl-command]
---

# CPINTF

PyMAPDL: `mapdl.cpintf(lab='', toler='', **kwargs)`

Defines coupled degrees of freedom at an interface.

## Parameters

**lab**: Degree of freedom label for coupled nodes (in the nodal coordinate system). If ALL, use all appropriate labels except HDSP. Valid labels are: Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations, in radians), HDSP (hydrostatic pressure). Thermal labels: TEMP, TBOT, TE2, TE3,..., TTOP (temperature). Fluid labels: PRES (pressure); VX, VY, or VZ (velocities). Electric labels: VOLT (voltage); EMF (electromotive force drop); CURR (current). Magnetic labels: MAG (scalar magnetic potential); AZ (vector magnetic potential); CURR (current). Diffusion label: CONC (concentration).

**toler**: Tolerance for coincidence (based on maximum coordinate difference in each global Cartesian direction for node locations and on angle differences for node orientations). Defaults to 0.0001. Only nodes within the tolerance are considered to be coincident for coupling.

## Notes

Defines coupled degrees of freedom between coincident nodes (within a tolerance). May be used, for example, to "button" together elements interfacing at a seam, where the seam consists of a series of node pairs. One coupled set is generated for each selected degree of freedom for each pair of coincident nodes. For more than two coincident nodes in a cluster, a coupled set is generated from the lowest numbered node to each of the other nodes in the cluster. Coupled sets are generated only within (and not between) clusters. If fewer than all nodes are to be checked for coincidence, use the [[nsel|NSEL]] command to select nodes. Coupled set reference numbers are incremented by one from the highest previous set number. Use [[cplist|CPLIST]] to display the generated sets. Only nodes having the same nodal coordinate system orientations ("coincident" within a tolerance) are included. Use the [[ceintf|CEINTF]] command to connect nodes by constraint equations instead of by coupling. Use the [[eintf|EINTF]] command to connect nodes by line elements instead of by coupling.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPINTF.html

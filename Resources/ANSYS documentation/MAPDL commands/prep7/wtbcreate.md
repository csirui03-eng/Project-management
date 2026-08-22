---
apdl: "WTBCREATE"
method: wtbcreate
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.wtbcreate
generated: 2026-08-22
tags: [mapdl-command]
---

# WTBCREATE

PyMAPDL: `mapdl.wtbcreate(iel='', node='', damp='', **kwargs)`

Creates a `USER300` element to model the turbine for full aeroelastic coupling analysis and specifies relevant settings for the analysis.

## Parameters

**iel**: Element number (next available number by default).

**node**: Node number connecting support structure and turbine.

**damp**

Damping option for the turbine:

- `0` - Damping matrix obtained from the aeroelastic code plus Rayleigh damping (default).
- `1` - Rayleigh damping only.
- `2` - Damping from the aeroelastic code only.

## Notes

**WTBCREATE** invokes a predefined Mechanical APDL macro that automatically generates a turbine element and issue relevant data commands that are necessary to run a full aeroelastic coupling analysis. For detailed information on how to perform a fully coupled aeroelastic analysis, see [Fully Coupled Wind Turbine Example in Mechanical APDL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/advaerorefs.html)

The generated `USER300` turbine element will have 9 nodes with node numbers NODE, NMAX+1, NMAX+2,..., NMAX+8, where NMAX is the maximum node number currently in the model.

There are six freedoms on the first node of the element: UX, UY, UZ, ROTX, ROTY, ROTZ, and these are true structural freedoms. For all the other nodes (that is, nodes 2 to 9), only the translational freedoms (UX, UY, UZ) are used. These are generalized freedoms that are internal to the turbine element and are used by the aeroelastic code only.

The element type integer of the `USER300` element is the current maximum element type integer plus one.

The command will also set up the analysis settings appropriate for a full aeroelastic coupling analysis. These include full Newton-Raphson solution ( [[nropt|NROPT]],FULL) and a [[usrcal|USRCAL]] command to activate the relevant user routines.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/None

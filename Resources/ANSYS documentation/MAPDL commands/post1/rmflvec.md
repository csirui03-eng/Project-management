---
apdl: "RMFLVEC"
method: rmflvec
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.rmflvec
generated: 2026-08-22
tags: [mapdl-command]
---

# RMFLVEC

PyMAPDL: `mapdl.rmflvec(**kwargs)`

Writes eigenvectors of fluid nodes to a file for use in damping parameter extraction.

## Notes

**RMFLVEC** extracts the modal information from the modal results file for all nodes specified in a node component called 'FLUN'. This component should include all nodes which are located at the fluid-structural interface. Mode shapes, element normal orientation, and a scaling factor are computed and stored in a file `Jobname.EFL`. For damping parameter extraction, use the [[dmpext|DMPEXT]] command macro. See for more information on thin film analyses.

`FLUID136` and `FLUID138` are used to model the fluid interface. Both the structural and fluid element types must be active. The fluid interface nodes must be grouped into a component 'FLUN'. A results file of the last modal analysis must be available.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RMFLVEC.html

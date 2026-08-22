---
apdl: "MCHECK"
method: mcheck
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mcheck
generated: 2026-08-22
tags: [mapdl-command]
---

# MCHECK

PyMAPDL: `mapdl.mcheck(lab='', **kwargs)`

Checks mesh connectivity.

## Parameters

**lab**

Operation:

- `ESEL` - Unselects the valid elements.

## Notes

Wherever two area or volume elements share a common face, **MCHECK** verifies that the way the elements are connected to the face is consistent with their relative normals or integrated volumes. (This may detect folds or otherwise overlapping elements.)

**MCHECK** verifies that the element exterior faces form simply-connected closed surfaces. (This may detect unintended cracks in a mesh.)

**MCHECK** warns if the number of element facets in a 2D loop or 3D shell is not greater than a computed limit. This limit is the smaller of either three times the number of faces on one element, or one-tenth the total number of element faces in the model. (This may detect holes in the middle of a mesh.)

The **MCHECK** command will perform a number of validity checks on the selected elements, including: **Normal check:** Wherever two area elements share a common edge, **MCHECK** verifies that the ordering of the nodes on each element is consistent with their relative normals.

**Volume check:** Wherever two volume elements share a common face, **MCHECK** verifies that the sign of the integrated volume of each element is consistent.

**Closed surface check:** **MCHECK** verifies that the element exterior faces form simply- connected closed surfaces (this may detect unintended cracks in a mesh).

**Check for holes in the mesh:** **MCHECK** warns if the number of element faces surrounding an interior void in the mesh is small enough to suggest one or more accidentally omitted elements, rather than a deliberately formed hole. For this test, the number of faces around the void is compared to the smaller of a) three times the number of faces on one element, or b) one-tenth the total number of element faces in the model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MCHECK.html

---
apdl: "MODMSH"
method: modmsh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.modmsh
generated: 2026-08-22
tags: [mapdl-command]
---

# MODMSH

PyMAPDL: `mapdl.modmsh(lab='', **kwargs)`

Controls the relationship of the solid model and the FE model.

## Parameters

**lab**

Relationship key:

- `STAT` - Gives status of command (default). This applies only to the CHECK option (no status is provided for the DETACH option).
- `NOCHECK` - Deactivates the checking of the solid model and the finite element model. Allows elements and nodes generated with the mesh commands to be modified directly ( [[emodif|EMODIF]], [[nmodif|NMODIF]], [[edele|EDELE]], [[ndele|NDELE]], etc.). Also deactivates solid model hierarchical checking so that areas attached to volumes may be deleted etc.
- `CHECK` - Reactivates future checking of the solid model.
- `DETACH` - Releases all associativity between the current solid model and finite element model. Mechanical APDL deletes any element attributes that were assigned to the affected solid model entities through default attributes (that is, through the [[type|TYPE]], [[real|REAL]], [[mat|MAT]], [[secnum|SECNUM]], and [[esys|ESYS]] command settings and a subsequent meshing operation). However, attributes that were assigned directly to the solid model entities (via the [[katt|KATT]], [[latt|LATT]], [[aatt|AATT]], and [[vatt|VATT]] commands) are not deleted.

## Notes

Affects the relationship of the solid model (keypoints, lines, areas, volumes) and the finite element model (nodes, elements, and boundary conditions).

Specify `Lab` = NOCHECK carefully. By deactivating checking, the solid model database can be corrupted by subsequent operations.

After specifying `Lab` = DETACH, it is no longer possible to select or define finite element model items in terms of the detached solid model or to clear the mesh.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODMSH.html

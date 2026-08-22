---
apdl: "PMAP"
method: pmap
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.pmap
generated: 2026-08-22
tags: [mapdl-command]
---

# PMAP

PyMAPDL: `mapdl.pmap(form='', discon='', **kwargs)`

Creates mapping of the path geometry by defining path interpolation division points.

## Parameters

**form**

Defines the mapping method:

- `UNIFORM` - Maps uniform divisions (specified on the `nDiv` argument of the [[path|PATH]] command) between specified points. This is the default.
- `ACCURATE` - Map geometry using a small division at the beginning and end of each segment. This gives you accurate derivatives, integrals, tangents, and normals for curves which do not have continuous slopes at the specified points. To create nonuniform divisions, the `nDiv` argument of the [[path|PATH]] command must be greater than 2.

**discon**: Sets mapping for discontinuities in the field. The divisions are modified to put a point just before and just after the discontinuity. The valid label is MAT, for a material discontinuity. No discontinuity is the default. Discontinuity mapping involves the NOAV option on the [[pdef|PDEF]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PMAP.html

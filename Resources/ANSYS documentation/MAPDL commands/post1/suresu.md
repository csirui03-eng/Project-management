---
apdl: "SURESU"
method: suresu
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.suresu
generated: 2026-08-22
tags: [mapdl-command]
---

# SURESU

PyMAPDL: `mapdl.suresu(fname='', fext='', fdir='', **kwargs)`

Read a set of surface definitions and result items from a file and make them the current set.

## Parameters

**fname**: Eight character name.

**fext**: Extension name.

**fdir**: Optional path specification.

## Notes

Reading (and therefore resuming) surface and result definitions from a file overwritea any existing surface definitions.

Reading surfaces back into the postprocessor ( [[post1|/POST1]] ) does not insure that the surfaces (and their results) are appropriate for the model currently residing in [[post1|/POST1]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SURESU.html

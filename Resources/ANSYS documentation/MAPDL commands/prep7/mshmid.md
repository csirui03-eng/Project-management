---
apdl: "MSHMID"
method: mshmid
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mshmid
generated: 2026-08-22
tags: [mapdl-command]
---

# MSHMID

PyMAPDL: `mapdl.mshmid(key='', **kwargs)`

Specifies placement of midside nodes.

## Parameters

**key**

Key indicating placement of midside nodes:

- `0` - Midside nodes (if any) of elements on a region boundary follow the curvature of the boundary line or area (the default).
- `1` - Place midside nodes of all elements so that element edges are straight. Allows coarse mesh along curves.
- `2` - Do not create midside nodes (elements will have removed midside nodes).

## Notes

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSHMID.html

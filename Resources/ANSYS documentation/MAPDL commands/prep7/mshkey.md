---
apdl: "MSHKEY"
method: mshkey
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mshkey
generated: 2026-08-22
tags: [mapdl-command]
---

# MSHKEY

PyMAPDL: `mapdl.mshkey(key='', **kwargs)`

Specifies whether free meshing or mapped meshing should be used to mesh a model.

## Parameters

**key**

Key indicating the type of meshing to be used:

- `0` - Use free meshing (the default).
- `1` - Use mapped meshing.
- `2` - Use mapped meshing if possible; otherwise, use free meshing. If you specify **MSHKEY**,2, SmartSizing will be inactive even while free meshing non-map-meshable areas.

## Notes

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSHKEY.html

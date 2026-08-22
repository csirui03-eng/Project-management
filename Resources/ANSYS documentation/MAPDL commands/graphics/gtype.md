---
apdl: "/GTYPE"
method: gtype
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gtype
generated: 2026-08-22
tags: [mapdl-command]
---

# /GTYPE

PyMAPDL: `mapdl.gtype(wn='', label='', key='', **kwargs)`

Controls the entities that the [[gplot|GPLOT]] command displays.

## Parameters

**wn**: Window number (or ALL) to which this command applies (defaults to 1)

**label**

This represents the type of entity to display:

- `NODE` - Nodes
- `ELEM` - Elements
- `KEYP` - Keypoints
- `LINE` - Lines
- `AREA` - Areas
- `VOLU` - Volumes
- `GRPH` - Graph displays

**key**

Switch:

- `0` - Turns the entity type off.
- `1` - Turns the entity type on.

## Notes

The **/GTYPE** command controls which entities the [[gplot|GPLOT]] command displays. NODE, ELEM, KEYP, LINE, AREA, and VOLU are on by default. When ELEM is activated, you can control the type of element displayed via the [[gcmd|/GCMD]] command (which also controls the type of graph display). When the GRPH entity type is activated, all other entity types are deactivated. Conversely, when any of the NODE, ELEM, KEYP, LINE, AREA, and VOLU entity types are active, the GRPH entity type is deactivated.

The **/GTYPE** command gives you several options for multi-window layout:

- One window
- Two windows (left and right or top and bottom of the screen)
- Three windows (two at the top and one at the bottom of the screen, or one top and two bottom windows
- Four windows (two at the top and two at the bottom)

Once you choose a window layout, you can choose one of the following: multiple plots, replotting, or no redisplay.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GTYPE.html

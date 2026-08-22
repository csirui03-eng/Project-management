---
apdl: "VSWEEP"
method: vsweep
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.vsweep
generated: 2026-08-22
tags: [mapdl-command]
---

# VSWEEP

PyMAPDL: `mapdl.vsweep(vnum='', srca='', trga='', lsmo='', **kwargs)`

Fills an existing unmeshed volume with elements by sweeping the mesh from an adjacent area through the volume.

## Parameters

**vnum**

Number identifying the volume that is to be meshed by **VSWEEP**. If `VNUM` = P, graphical picking is enabled, you will be prompted to choose the volume or volumes based on the setting of [[extopt|EXTOPT]],VSWE,AUTO. This argument is required.

"ALL" is a valid input value that when selected sends all the selected volumes to the sweeper. If `VNUM` = ALL, each volume that can be swept will be and those not able to be swept will be unmeshed or meshed with tets depending upon the setting of [[extopt|EXTOPT]],VSWE,TETS.

A component name is a valid input value. All volumes that are part of the specified component will be sent to the sweeper.

**srca**

Number identifying the source area. This is the area whose mesh will provide the pattern for the volume elements. (If you do not mesh the source area prior to volume sweeping, the program meshes it internally when you initiate volume sweeping.) The program sweeps the pattern of the area elements through the volume to create the mesh of volume elements. You cannot substitute a component name for `SRCA`.

This argument is optional. If `VNUM` = ALL or is a component containing more than one volume, `SRCA` is ignored. If `SRCA` is not provided or if it is ignored, **VSWEEP** attempts to automatically determine which area should be the target area.

**trga**

Number identifying the target area. This is the area that is opposite the source area specified by `SRCA`. You cannot substitute a component name for `TRGA`.

This argument is optional. If `VNUM` = ALL or component containing more than one volume, `TRGA` is ignored. If `TRGA` is not provided or if it is ignored, **VSWEEP** attempts to automatically determine which area should be the target area.

**lsmo**

Value specifying whether the program should perform line smoothing during volume sweeping. (The value of this argument controls line smoothing for the **VSWEEP** command only; it has no effect on the setting of the [[mopt|MOPT]] command's LSMO option.) This argument is optional.

- `0` - Do not perform line smoothing. This is the default.
- `1` - Always perform line smoothing. This setting is not recommended for large models due to speed considerations.

## Notes

If the source mesh consists of quadrilateral elements, the program fills the volume with hexahedral elements. If the source mesh consists of triangles, the program fills the volume with wedges. If the source mesh consists of a combination of quadrilaterals and triangles, the program fills the volume with a combination of hexahedral and wedge elements.

In the past, you may have used the [[vrotat|VROTAT]], [[vext|VEXT]], [[voffst|VOFFST]], and/or [[vdrag|VDRAG]] commands to extrude a meshed area into a meshed volume. However, those commands create the volume and the volume mesh simultaneously. In contrast, the **VSWEEP** command is intended for use in an existing unmeshed volume. This makes **VSWEEP** particularly useful when you have imported a solid model that was created in another program, and you want to mesh it in Mechanical APDL.

For related information, see the description of the [[extopt|EXTOPT]] command (although [[extopt|EXTOPT]] sets volume sweeping options, it does not affect element spacing). Also see the detailed discussion of volume sweeping in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_5.html#modmeshvaidck31400) of the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSWEEP.html

---
apdl: "/AN3D"
method: an3d
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.annotation.Annotation.an3d
generated: 2026-08-22
tags: [mapdl-command]
---

# /AN3D

PyMAPDL: `mapdl.an3d(kywrd='', key='', **kwargs)`

Specifies 3D annotation functions

## Parameters

**kywrd**, **key**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AN3D.html) for further information.

## Notes

Because 3D annotation is applied in relation to the XYZ coordinates of the anchor, you can transform your model, and the annotation will maintain the spatial relationship with the model. This works within reason, and there are instances where changing the perspective or the size of the model will change the apparent relationship between the annotation and the model.

The overall 3D dimensions of your model are defined by a bounding box. If portions of your model's bounding box lie outside of the visible area of your graphics window (if you are zoomed in on a specific area of your model), it can affect the placement of your 3D annotations. Zooming out will usually overcome this problem.

3D annotation is valid for the Cartesian ( [[csys|CSYS]],0) coordinate system only. If you want to annotate a model you created in another coordinate system, use 2D annotation (note that 2D annotations do not remain anchored for dynamic rotations or transformations).

When you apply user defined bitmaps, the size of the annotation can vary. Use the options menu of the 3D annotation widget to adjust the size and placement of your bitmaps.

You cannot use the "!" and "\$" characters in Mechanical APDL text annotation.

The GUI generates this command during 3D annotation operations and inserts the command into the log file ( `Jobname.LOG` ). You should NOT type this command directly during a Mechanical APDL session (although the command can be included in an input file for batch input or for use with the [[input|/INPUT]] command).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AN3D.html

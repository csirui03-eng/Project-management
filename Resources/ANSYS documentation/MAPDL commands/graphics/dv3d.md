---
apdl: "/DV3D"
method: dv3d
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.dv3d
generated: 2026-08-22
tags: [mapdl-command]
---

# /DV3D

PyMAPDL: `mapdl.dv3d(lab='', key='', **kwargs)`

Sets 3D device option modes.

## Parameters

**lab**

Mode label:

- `ACCU` - Activating the accumulation buffer for OpenGL graphics, providing faster model rotation when shaded backgrounds are in use. This feature is off by default.
- `ACTR` - Label term to designate the cursor position as the center for automatic dynamic rotational center capability. The subsequent `Key` value (see below) turns this capability on and off. This feature is on by default. (Available for OpenGL displays only.)
- `ANIM` - Animation mode. The ANIM option allows you to create animation frames in pixmap mode instead of display list mode. This may improve large model performance, but it eliminates local manipulation while animation is in progress. This feature is on by default.
- `ANTI` - Label term to control Anti-aliasing, a smoothing technique for your graph plots. (see below) The subsequent `Key` value turns this capability on and off. The default for this feature is off. (Available for OpenGL displays only).
- `CNTR` - Switches banded contours on (1) or off (0) for your 3D contour display. The default is 1 (ON). Other contour parameters such as number of contours or the increment and range are defined using the [[contour|/CONTOUR]] command. When either 9 or 128 contours are specified via [[contour|/CONTOUR]], this command is ignored and a smooth contour is always displayed.
- `DGEN` - Local manipulation degenerate mode. You access the DGEN option to set wire-frame local manipulation mode for 3D devices (device dependent). This feature is off by default.
- `DLIST` - With DLIST, you can specify whether screen updates and redraws will be performed using the Mechanical APDL display list (off), or the 3D device's display list (on). DLIST is on by default for Windows systems, but off for Linux.
- `DELS` - You use DELS to suppress contour display screen overwrites when [[noerase|/NOERASE]] is active. This prevents the bleed-through that occurs when you overlay contour plots.
- `TRIS` - Triangle strip mode. Tri-stripping provides faster 3D display capabilities and is on by default. Some display enhancements, such as texturing, are adversely affected by tri-stripping. You can turn off tri-stripping in order to improve these display functions. Be sure to turn tri- stripping on after the desired output is obtained.

**key**

The following key options apply to `Lab` = ACCU:

- `0` - (OFF) The accumulation buffer is not accessed. (default)
- `1` - (ON) Access to the buffer is enabled.

The following key options apply to `Lab` = ACTR:

- `0` - (OFF) The cursor position has no effect on the existing rotational center for dynamic operations.

- `1` - (ON) The rotational center for dynamic rotations in OpenGL is determined by the position of the mouse cursor on (or within 15 pixels of) the model. Any rotations that are initiated with the cursor more than 15 pixels from the model will occur about the midpoint of the Z-axis at that point in space. If the Z-buffer has not been refreshed the Z-axis will have an infinite value, and rotations will appear to occur about an extremely long Z-axis. This behavior stops when the graphics window is refreshed or replotted. (default)

  Note that when using the GUI in 3D mode, when ACTR = 1, the `Rotational Center` option is grayed out under Utility Menu\> PlotCtrls\> View Setting because the rotational center is determined strictly by the position of the mouse cursor.

The following key options apply to `Lab` = ANIM:

- `0` - Display list animation. The object can be dynamically manipulated while animating. No legend, countour or annotation items are displayed. (see Notes, below)

- `1` - On Linux, device-dependent pixmap animation is used. On the PC, bitmap animation is provided (default). When you animate in this mode, you cannot dynamically manipulate your model (see Notes, below).

- `2` - On the PC only, this option provides AVI animation which uses the AVI movie player.

  Although you can create animations of multiple Mechanical APDL window schemes, animations created with OpenGL display lists ( **/DV3D**, ANIM, 0) do not retain the windowing scheme information. You CAN save multiple windows via the X11/WIN32 drivers, or via the OpenGL driver with **/DV3D**, ANIM, KEY in effect (where KEY is not zero).

The following key options apply to `Lab` = ANTI

- `0` - (OFF) Anti-aliasing is not active (default).
- `1` - (ON) The anti-aliasing technique will be applied to smooth the lines in your displays (valid for OpenGL only).

The following key options apply to `Lab` = DGEN:

- `0` - Normal manipulation.
- `1` - Wireframe Manipulation.

The following key options apply to `Lab` = DLIST:

- `0` - (OFF) The Mechanical APDL display list is used for plotting and dynamic graphics manipulation (Linux default).
- `1` - (ON) The local (3D device) display list is used for plotting and dynamic rotation (Windows default).

The following key options apply to `Lab` = TRIS:

- `0` - (OFF) Tri-stripping is off.
- `1` - (ON) Tri-stripping is on (default).

## Notes

Mechanical APDL uses display list animation for its 3D models. This memory resident array method interfaces with the OpenGL model information to allow the program to efficiently pan, zoom, rotate and dynamically manipulate your model during animation. The logo, legend, contour and other annotation items are produced in 2D and will not appear when **/DV3D**, ANIM, 0 is in effect. To display these items, use **/DV3D**, ANIM, 1. All screen data will be displayed, but manipulation of the model will not be possible.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DV3D.html

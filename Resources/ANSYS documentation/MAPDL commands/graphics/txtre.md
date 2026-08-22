---
apdl: "/TXTRE"
method: txtre
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.txtre
generated: 2026-08-22
tags: [mapdl-command]
---

# /TXTRE

PyMAPDL: `mapdl.txtre(lab='', num='', n1='', n2='', ninc='', **kwargs)`

Controls application of texture to selected items.

## Parameters

**lab**

You can apply texture according to the following labels:

- `ELEM` - Apply texture to elements `N1` through `N2` in steps of `NINC`.
- `AREA` - Apply texture to areas `N1` through `N2` in steps of `NINC`.
- `VOLU` - Apply texture to volumes `N1` through `N2` in steps of `NINC`.
- `CM` - Apply texture to the component named in `N1`. `N2` and `NINC` are ignored.
- `ON, OFF` - Sets the specified texture display on or off. All other fields are ignored.

\* `File` - If Lab = File, the command format is **/TXTRE**, File, `Key_Index`, `Fname`, `Fext`, `--`, `Format` (This variant of the command is applicable to 2D drivers).

> - `Key_Index` - The texture index associated with the file. If the number fifty-one (51) is used, the imported bitmap will be used as the window's logo.
> - `Fname` - File name and directory path (248 characters maximum, including the characters needed for the

directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. \* `Fext` - Filename extension (eight-character maximum). \* `Format` - The file format. If `Format` = 0, the file is a pixmap (Linux) or Bitmap (PC). The file cannot contain a compressed image, and the PC file must be 8 or 24 bit BI_RGB format. If `Format` = 1 or JPEG, then the file is in JPEG (Joint Photographic Experts Group) format. If `Format` = 2 or PNG, then the file is in PNG (Portable Network Graphics) format.

**num**

Select the texture index number from the following list:

- `0` - No Texturing
- `1` - Aluminum
- `2` - Aluminum, Brushed
- `3` - Steel With Bumps
- `4` - Steel, Embossed
- `5` - Iron
- `6` - Steel, Pattern
- `7` - Steel, Riveted
- `8` - Steel, Scratched
- `9` - Tin
- `10` - Metal
- `11` - Steel, Etched
- `12` - Metal, Hot
- `13` - Iron, Grainy
- `14` - Metal, Rusty
- `15` - Brick
- `16` - Block
- `17` - Wood
- `18` - Wood, Light
- `19` - Wood, Walnut
- `20` - Plastic, Hard Blue
- `21` - Plastic, Light Blue
- `22` - Plastic, Hard Red
- `31` - Gold
- `32` - Brass
- `33` - Silver
- `34` - Plastic, Black
- `35` - Plastic, Ivory
- `36` - Plastic, Blue
- `37` - Plastic, Red
- `38` - Plastic, Yellow
- `39` - Plastic, Green
- `40` - Plastic, Brown

**n1**, **n2**, **ninc**: Apply texture to `Lab` items numbered `N1` through `N2` in steps of `NINC` (defaults to 1). If `Lab` = CM, then N1 is used to for the component name and `N2` and `NINC` are ignored. If `Lab` = ELEM, AREA, or VOLU and `N1` = blank or ALL, then the specified texture will be applied to all entities of type `Lab`. If `N1` = P, then graphical picking is enabled.

## Notes

This command is available for 3D Open GL devices. 2D devices are supported **only** for the `Lab` = File variation of the command, allowing imported bitmaps to be used for texturing and annotation. Textures can affect the speed of many of your display operations. You can increase the speed by temporarily turning the textures off ( Utility Menu\> PlotCtrls\> Style\> Texturing(3D)\> Display Texturing ). This menu selection toggles your textures on and off. When textures are toggled off, all of the texture information is retained and reapplied when texturing is toggled back on.

For some displays, the texture will appear distorted because of a technique used to enhance 3D displays ( [[dv3d|/DV3D]],TRIS,1). Disabling this function ( [[dv3d|/DV3D]],TRIS,0) will improve the quality of some texture displays. Disabling the TRIS option of the [[dv3d|/DV3D]] command will slow down 3D displays significantly. Be sure to reapply the TRIS option after you obtain a satisfactory output.

Specifying **/TXTRE**,DEFA removes all texturing.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TXTRE.html

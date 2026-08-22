---
apdl: "ASKIN"
method: askin
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.askin
generated: 2026-08-22
tags: [mapdl-command]
---

# ASKIN

PyMAPDL: `mapdl.askin(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nl7='', nl8='', nl9='', **kwargs)`

Generates an area by "skinning" a surface through guiding lines.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**, **nl7**, **nl8**, **nl9**: The additional guiding lines for the skinned area (up to 9 total lines, including `NL1`, if using keyboard entry). If negative (and `NL1` is negative), the line beginning and end will be temporarily interchanged for the skinning operation (see below).

## Notes

Generates an area by "skinning" a surface through specified guiding lines. The lines act as a set of "ribs" over which a surface is "stretched." Two opposite edges of the area are framed by the first ( `NL1` ) and last ( NLn ) guiding lines specified. The other two edges of the area are framed by splines-fit lines which the program automatically generates through the ends of all guiding lines. The interior of the area is shaped by the interior guiding lines. Once the area has been created, only the four edge lines will be attached to it. In rare cases, it may be necessary to change the default algorithm used by the **ASKIN** command (see below).

When skinning from one guiding line to the next, the program can create the transition area in one of two ways: one more spiraled and one less spiraled ("flatter"). By default, the program attempts to produce the flatter transition, instead of the more spiraled transition. This algorithm can be changed by inputting `NL1` as a negative number, in which case the program connects all the keypoints at the line "beginnings" ( [[psymb|/PSYMB]],LDIR command) as one edge of the area, and all the line "ends" as the opposite edge, irrespective of the amount of spiraling produced in each transition area.

To further control the geometry of the area (if `NL1` is negative), the beginning and end of any specified line (other than `NL1` ) can be temporarily interchanged (for the skinning operation only) by inputting that line number as negative. See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASKIN.html

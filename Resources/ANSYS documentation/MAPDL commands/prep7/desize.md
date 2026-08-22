---
apdl: "DESIZE"
method: desize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.desize
generated: 2026-08-22
tags: [mapdl-command]
---

# DESIZE

PyMAPDL: `mapdl.desize(minl='', minh='', mxel='', angl='', angh='', edgmn='', edgmx='', adjf='', adjm='', **kwargs)`

Controls default element sizes.

**Command default:**

Default settings as described for each argument are used.

## Parameters

**minl**: Minimum number of elements that will be attached to a line when using lower-order elements (defaults to 3 elements per line). If `MINL` = DEFA, all arguments will be set back to default values. If `MINL` = `STAT`, list status of command (Including on/off status). If `MINL` = OFF, deactivate default element sizing. If `MINL` = ON, reactivate default element sizing.

**minh**: Minimum number of elements that will be attached to a line when using higher-order elements. Defaults to 2 elements per line.

**mxel**: Maximum number of elements that will be attached to a single line (lower or higher-order elements). Defaults to 15 elements per line for h-elements. To deactivate this limit, specify a large number (such as 9999).

**angl**: Maximum spanned angle per lower-order element for curved lines. Defaults to 15 degrees per element.

**angh**: Maximum spanned angle per higher-order element for curved lines. Defaults to 28 degrees per element.

**edgmn**: Minimum element edge length. Defaults to no minimum edge length. The `MINL` or `MINH` argument can override this value.

**edgmx**: Maximum element edge length. Defaults to no maximum edge length. The `MXEL` argument can override this value.

**adjf**: Target aspect ratio for adjacent line. Used only when free meshing. Defaults to 1.0, which attempts to create equal-sided h-elements.

**adjm**: Target aspect ratio for adjacent line. Used only when map meshing. Defaults to 4.0, which attempts to create rectangular h-elements.

## Notes

**DESIZE** settings are usually used for mapped meshing. They are also used for free meshing if SmartSizing is turned off ( [[smrtsize|SMRTSIZE]],OFF), which is the default. Even when SmartSizing is on, some **DESIZE** settings (such as maximum and minimum element edge length) can affect free mesh density. The default settings of the **DESIZE** command are used only when no other element size specifications ( [[kesize|KESIZE]], [[lesize|LESIZE]], [[esize|ESIZE]] ) exist for a certain line.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DESIZE.html

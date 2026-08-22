---
apdl: "EXTOPT"
method: extopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.extopt
generated: 2026-08-22
tags: [mapdl-command]
---

# EXTOPT

PyMAPDL: `mapdl.extopt(lab='', val1='', val2='', val3='', val4='', **kwargs)`

Controls options relating to the generation of volume elements from area elements.

## Parameters

**lab**

Label identifying the control option. The meanings of `Val1`, `Val2`, and `Val3` will vary depending on `Lab`.

- `ON` - Sets carryover of the material attributes, real constant attributes, and element coordinate system attributes of the pattern area elements to the generated volume elements. Sets the pattern area mesh to clear when volume generations are done. `Val1`, `Val2`, and `Val3` are ignored.

- `OFF` - Removes all settings associated with this command. `Val1`, `Val2`, and `Val3` are ignored.

- `STAT` - Shows all settings associated with this command. `Val1`, `Val2`, `Val3`, and `Val4` are ignored.

- `ATTR` - Sets carryover of particular pattern area attributes (materials, real constants, and element coordinate systems) of the pattern area elements to the generated volume elements. (See .) `Val1` can be:

  - `0` - Sets volume elements to use current [[mat|MAT]] command settings.
  - `1` - Sets volume elements to use material attributes of the pattern area elements.

  > `Val2` can be:

  - `0` - Sets volume elements to use current [[real|REAL]] command settings.
  - `1` - Sets volume elements to use real constant attributes of the pattern area elements.

  > `Val3` can be:

  - `0` - Sets volume elements to use current [[esys|ESYS]] command settings.
  - `1` - Sets volume elements to use element coordinate system attributes of the pattern area elements.

  > `Val4` can be:

  - `0` - Sets volume elements to use current [[secnum|SECNUM]] command settings.
  - `1` - Sets volume elements to use section attributes of the pattern area elements.

- `ESIZE` - Val1 sets the number of element divisions in the direction of volume generation or volume sweep. For [[vdrag|VDRAG]] and [[vsweep|VSWEEP]], `Val1` is overridden by the [[lesize|LESIZE]] command `NDIV` setting. `Val2` sets the spacing ratio (bias) in the direction of volume generation or volume sweep. If positive, `Val2` is the nominal ratio of last division size to first division size (if \> 1.0, sizes increase, if \< 1.0, sizes decrease). If negative, `Val2` is the nominal ratio of center division(s) size to end divisions size. Ratio defaults to 1.0 (uniform spacing). `Val3` and `Val4` are ignored.

- `ACLEAR` - Sets clearing of pattern area mesh. (See .) `Val1` can be:

  - `0` - Sets pattern area to remain meshed when volume generation is done.
  - `1` - Sets pattern area mesh to clear when volume generation is done. `Val2`, `Val3`, and `Val4` are ignored.

- `VSWE` - Indicates that volume sweeping options will be set using `Val1` and `Val2`. Settings specified with **EXTOPT**, `VSWE` will be used the next time the [[vsweep|VSWEEP]] command is invoked. If `Lab` = VSWE, `Val1` becomes a label. `Val1` can be:

  - `AUTO` - Indicates whether you will be prompted for the source and target used by [[vsweep|VSWEEP]] or if VSWE should automatically determine the source and target. If `Val1` = AUTO, `Val2` is ON by default. VSWE will automatically determine the source and target for [[vsweep|VSWEEP]]. You will be allowed to pick more than one volume for sweeping. When `Val2` = OFF, the application prompts you for the source and target for [[vsweep|VSWEEP]]. You will only be allowed to pick one volume for sweeping.

  - `TETS` - Indicates whether [[vsweep|VSWEEP]] will tet mesh non-sweepable volumes or leave them unmeshed. If `Val1` = TETS, `Val2` is OFF by default. Non-sweepable volumes will be left unmeshed. When `Val2` = ON, the non-sweepable volumes will be tet meshed if the assigned element type supports tet shaped elements.

    `Val3` is ignored for Lab = VSWE.

**val1**, **val2**, **val3**, **val4**: Additional input values as described under each option for `Lab`.

## Notes

**EXTOPT** controls options relating to the generation of volume elements from pattern area elements using the [[vext|VEXT]], [[vrotat|VROTAT]], [[voffst|VOFFST]], [[vdrag|VDRAG]], and [[vsweep|VSWEEP]] commands. (When using [[vsweep|VSWEEP]], the pattern area is referred to as the source area.)

Enables carryover of the attributes of the pattern area elements to the generated volume elements when you are using [[vext|VEXT]], [[vrotat|VROTAT]], [[voffst|VOFFST]], or [[vdrag|VDRAG]]. (When using [[vsweep|VSWEEP]], since the volume already exists, use the [[vatt|VATT]] command to assign attributes before sweeping.)

When you are using [[vext|VEXT]], [[vrotat|VROTAT]], [[voffst|VOFFST]], or [[vdrag|VDRAG]], enables clearing of the pattern area mesh when volume generations are done. (When you are using [[vsweep|VSWEEP]], if selected, the area meshes on the pattern (source), target, and/or side areas clear when volume sweeping is done.)

Neither **EXTOPT**,VSWE,AUTO nor **EXTOPT**,VSWE,TETS will be affected by **EXTOPT**,ON or **EXTOPT**, OFF.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXTOPT.html

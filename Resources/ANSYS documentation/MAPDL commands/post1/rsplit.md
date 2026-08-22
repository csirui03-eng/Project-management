---
apdl: "RSPLIT"
method: rsplit
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.rsplit
generated: 2026-08-22
tags: [mapdl-command]
---

# RSPLIT

PyMAPDL: `mapdl.rsplit(option='', label='', name1='', name2='', name3='', name4='', name5='', name6='', name7='', name8='', name9='', name10='', name11='', name12='', name13='', name14='', name15='', name16='', **kwargs)`

Creates one or more results file(s) from the current results file based on subsets of elements.

**Command default:** Write all data available for the element subset.

## Parameters

**option**

Specify which results to include for the subset of elements.

- `ALL` - Write all nodal and element results based on the subset of elements (default).
- `EXT` - Write only the nodal and element results that are on the exterior surface of the element subset. The results data will be averaged as in PowerGraphics (see [[avres|AVRES]] ) when this results file is brought into POST1. Only valid for solid elements.

**label**

Define where the element subset is coming from.

- `ALL` - Use all selected element components ( [[cmsel|CMSEL]] ) (default).
- `ESEL` - Use the currently selected ( [[esel|ESEL]] ) set of elements. `Name1` defines the results file name.
- `LIST` - Use `Name1` to `Name16` to list the element component and/or assembly names (that contain element components).

**name1**, **name2**, **name3**, **name4**, **name5**, **name6**, **name7**, **name8**, **name9**, **name10**, **name11**, **name12**, **name13**, **name14**, **name15**, **name16**: Up to 16 element component and/or assembly names (that contain element components).

## Notes

Results files will be named based on the element component or assembly name, for example, `Cname.rst`, except for the ESEL option, for which you must specify the results file name (no extension) using the `Name1` field. Note that the `.rst` filename will be written in all uppercase letters ( `CNAME.rst` ) (unless using the ESEL option); when you read the file, you must specify the filename using all uppercase letters (that is, `file`,CNAME). You may repeat the **RSPLIT** command as often as needed. All results sets on the results file are processed. Use [[aux3|/AUX3]] to produce a results file with just a subset of the results sets.

Use [[inres|INRES]] to limit the results data written to the results files.

The subset geometry is also written so that no database file is required to postprocess the subset results files. You must not resume any database when postprocessing one of these results files. The input results file must have geometry written to it (that is, do not use [[config|/CONFIG]],NORSTGM,1).

Applied forces and reaction forces are not apportioned if their nodes are shared by multiple element subsets. Their full values are written to each results file.

Each results file renumbers its nodes and elements starting with 1.

This feature is useful when working with large models. For more information on the advantages and uses of the **RSPLIT** command, see [Splitting Large Results Files](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSPLIT.html

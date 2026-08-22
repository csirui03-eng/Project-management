---
apdl: "/MPLIB"
method: mplib
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mplib
generated: 2026-08-22
tags: [mapdl-command]
---

# /MPLIB

PyMAPDL: `mapdl.mplib(r_w_opt='', path='', **kwargs)`

Sets the default material library read and write paths.

## Parameters

**r_w_opt**

Determines what path is being set. Possible values are:

- `READ` - Set the read path.
- `WRITE` - Set the write path.
- `STAT` - Report what read and write paths are currently in use.

**path**: The directory path to be used for material library files.

## Notes

The **/MPLIB** command sets two path strings used in conjunction with the material library feature and the [[mpread|MPREAD]] and [[mpwrite|MPWRITE]] commands.

For [[mpread|MPREAD]], when you use the `LIB` option and no directory path is given in the file name, the command searches for the file in these locations: the current working directory, the user's home directory, the user-specified material library directory (as defined by the **/MPLIB**,READ, `PATH` command), and `/ansys_dir/matlib`.

For [[mpwrite|MPWRITE]], when you use the `LIB` option and the directory portion of the specification for the material library file is blank, the command writes the material library file to the directory specified by the **/MPLIB**,WRITE, `PATH` command (if that path has been set). If the path has not been set, the default is to write the file to the current working directory.

The Material Library files supplied with the distribution media are meant for demonstration purposes only. These files are not intended for use in customer applications.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPLIB.html

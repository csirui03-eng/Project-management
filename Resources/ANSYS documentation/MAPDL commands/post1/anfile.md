---
apdl: "/ANFILE"
method: anfile
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anfile
generated: 2026-08-22
tags: [mapdl-command]
---

# /ANFILE

PyMAPDL: `mapdl.anfile(lab='', fname='', ext='', **kwargs)`

Saves or resumes an animation sequence to or from a file.

## Parameters

**lab**

Label type.

- `SAVE` - Save the current animation to a file.
- `RESUME` - Resume an animation from a file.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to ANIM if `Fname` is blank.

## Notes

This command saves an animation to a file from local terminal segments or resumes an animation from a file to local terminal segments. See the [[seg|/SEG]] command for details on segment storage. See the [[ancntr|ANCNTR]] macro for a convenient method of storing graphics frames in terminal memory segments. This command is device dependent and is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANFILE.html

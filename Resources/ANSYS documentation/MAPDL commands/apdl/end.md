---
apdl: "*END"
method: end
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.end
generated: 2026-08-22
tags: [mapdl-command]
---

# *END

PyMAPDL: `mapdl.end(**kwargs)`

Closes a macro file.

## Notes

Closes a file opened with [[create|*CREATE]]. The **\*END** command is an 8-character command (to differentiate it from `*ENDIF` ). If you add commented text on that same line but do not allow enough spaces between **\*END** and the "!" that indicates the comment text, the **\*END** will attempt to interpret the "!" as the 8th character and will fail.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_END.html

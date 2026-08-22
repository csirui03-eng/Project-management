---
apdl: "ERNORM"
method: ernorm
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.ernorm
generated: 2026-08-22
tags: [mapdl-command]
---

# ERNORM

PyMAPDL: `mapdl.ernorm(key='', **kwargs)`

Controls error estimation calculations.

**Command default:**

Error estimation calculations are performed by default unless PowerGraphics is enabled ( [[graphics|/GRAPHICS]],POWER).

## Parameters

**key**

Control key:

- `ON` - Perform error estimation (default). This option is not valid for PowerGraphics.
- `OFF` - Do not perform error estimation.

## Notes

Especially for thermal analyses, program speed increases if error estimation is suppressed. Therefore, it might be desirable to use error estimation only when needed. The value of the **ERNORM** key is not saved on `file.db`. Consequently, you need to reissue the **ERNORM** key after a [[resume|RESUME]] if you wish to deactivate error estimation again.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ERNORM.html

---
apdl: "FORM"
method: form
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_dump.BinaryFileDump.form
generated: 2026-08-22
tags: [mapdl-command]
---

# FORM

PyMAPDL: `mapdl.form(lab='', **kwargs)`

Specifies the format of the file dump.

## Parameters

**lab**

Format:

- `RECO` - Basic record description only (minimum output) (default).
- `TEN` - Same as RECO plus the first ten words of each record.
- `LONG` - Same as RECO plus all words of each record.

## Notes

Specifies the format of the file dump (from the [[dump|DUMP]] command).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FORM.html

---
apdl: "PARRES"
method: parres
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.parres
generated: 2026-08-22
tags: [mapdl-command]
---

# PARRES

PyMAPDL: `mapdl.parres(lab='', fname='', ext='', **kwargs)`

Reads parameters from a file.

## Parameters

**lab**

Read operation:

- `NEW` - Replace current parameter set with these parameters (default).
- `CHANGE` - Extend current parameter set with these parameters, replacing any that already exist.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to PARM if `Fname` is blank.

## Notes

Reads parameters from a coded file. The parameter file may have been written with the [[parsav|PARSAV]] command. The parameters read may replace or change the current parameter set.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PARRES.html

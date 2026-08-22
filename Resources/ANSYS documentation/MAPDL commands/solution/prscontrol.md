---
apdl: "PRSCONTROL"
method: prscontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.prscontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# PRSCONTROL

PyMAPDL: `mapdl.prscontrol(key='', **kwargs)`

Specifies whether to include pressure load stiffness in the element stiffness formation.

## Parameters

**key**

Pressure load stiffness key. In general, use the default setting. Use a non-default setting only if you encounter convergence difficulties. Pressure load stiffness is automatically included when using eigenvalue buckling analyses ( [[antype|ANTYPE]],BUCKLE), equivalent to `Key` = INCP. For all other types of analyses, valid arguments for `Key` are:

- `NOPL` - Pressure load stiffness not included for any elements.
- `(blank) (default)` - Include pressure load stiffness for elements `SURF153`, `SURF154`, `SURF156`, `SURF159`, `SHELL181`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, `BEAM188`, `BEAM189`, `FOLLW201`, `SHELL208`, `SHELL209`, `SOLID272`, `SOLID273`, `SHELL281`, `SOLID285`, `PIPE288`, `PIPE289`, and `ELBOW290`.

## Notes

This command is rarely needed. The default settings are recommended for most analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRSCONTROL.html

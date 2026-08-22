---
apdl: "SETFGAP"
method: setfgap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.setfgap
generated: 2026-08-22
tags: [mapdl-command]
---

# SETFGAP

PyMAPDL: `mapdl.setfgap(gap='', ropt='', pamb='', acf1='', acf2='', pref='', mfp='', **kwargs)`

Updates or defines the real constant table for squeeze film elements.

## Parameters

**gap**: Gap separation.

**ropt**

Real constant set option.

- `0` - Creates separate real constant sets for each selected element with the specified real constant values (default).
- `1` - Updates existing real constant sets. The gap separation is updated from displacement results in the database. Other real constants are updated as specified in the command input parameters.

**pamb**: Ambient pressure.

**acf1**, **acf2**: Accommodation factor 1 and 2.

**pref**: Reference pressure for mean free path.

**mfp**: Mean free path.

## Notes

This command is used for large signal cases to update the gap separation real constant on a per- element basis. Issue this command prior to solution using the default `ROPT` value to initialize real constant sets for every fluid element. After a solution, you can re-issue the command to update the real constant set for a subsequent analysis. See for more information on thin film analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SETFGAP.html

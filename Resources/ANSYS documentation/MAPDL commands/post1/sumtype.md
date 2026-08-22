---
apdl: "SUMTYPE"
method: sumtype
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.sumtype
generated: 2026-08-22
tags: [mapdl-command]
---

# SUMTYPE

PyMAPDL: `mapdl.sumtype(label='', **kwargs)`

Sets the type of summation to be used in the following load case operations.

## Parameters

**label**

Summation type

- `COMP` - Combine element component stresses only. Stresses such as average nodal stresses, principal stresses, equivalent stresses, and stress intensities are derived from the combined element component stresses. Default.
- `PRIN` - Combine principal stress, equivalent stress, and stress intensity directly as stored on the results file. Component stresses are not available with this option.

## Notes

Issue **SUMTYPE**,PRIN when you want to have a load case operation ( [[lcoper|LCOPER]] ) act on the principal / equivalent stresses instead of the component stresses. Also issue **SUMTYPE**,PRIN when you want to read in load cases ( [[lcase|LCASE]] ). Note that the **SUMTYPE** setting is not maintained between /POS T1 sessions.

**SUMTYPE**,PRIN also causes principal nodal values to be the average of the contributing principal element nodal values (see [[avprin|AVPRIN]],1).

`BEAM188` and `BEAM189` elements compute principal stress, equivalent stress, and stress intensity values on request instead of storing them on the results file; **SUMTYPE**,PRIN does not apply for these elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUMTYPE.html

---
apdl: "EMIS"
method: emis
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiation_matrix_method.RadiationMatrixMethod.emis
generated: 2026-08-22
tags: [mapdl-command]
---

# EMIS

PyMAPDL: `mapdl.emis(mat='', evalu='', **kwargs)`

Specifies emissivity as a material property for the Radiation Matrix method.

**Command default:**

Since there is no command default value for emissivity, you must issue **EMIS** to specify it. Otherwise, an error message appears. If you issue **EMIS** without defining a numerical value, emissivity defaults to 0.

## Parameters

**mat**: Material number associated with this emissivity (500 maximum). Defaults to 1.

**evalu**: Emissivity for this material (0.0 \< `EVALU` (equation omitted) 1.0). Enter a very small number for zero.

## Notes

Specifies emissivity as a material property for the Radiation Matrix method. This material property can then be associated with each element.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMIS.html

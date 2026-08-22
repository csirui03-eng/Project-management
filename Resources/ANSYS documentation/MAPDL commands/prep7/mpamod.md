---
apdl: "MPAMOD"
method: mpamod
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpamod
generated: 2026-08-22
tags: [mapdl-command]
---

# MPAMOD

PyMAPDL: `mapdl.mpamod(mat='', deftemp='', **kwargs)`

Modifies temperature-dependent secant coefficients of thermal expansion.

## Parameters

**mat**: Material number for which the secant coefficients of thermal expansion (SCTE's) are to be modified. Defaults to 1.

**deftemp**: Definition temperature at which the existing SCTE-versus-temperature tables were defined. Defaults to zero.

## Notes

This command converts temperature-dependent SCTE data (properties ALPX, ALPY, ALPZ) from the definition temperature ( `DEFTEMP` ) to the reference temperature defined by [[mp|MP]],REFT or [[tref|TREF]]. If both the [[mp|MP]],REFT and [[tref|TREF]] commands have been issued, the reference temperature defined by the [[mp|MP]],REFT command will be used.

This command does not apply to the instantaneous coefficients of thermal expansion (properties CTEX, CTEY, CTEZ) or to the thermal strains (properties THSX, THSY, THSZ).

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPAMOD.html

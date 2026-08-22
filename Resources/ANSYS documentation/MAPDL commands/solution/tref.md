---
apdl: "TREF"
method: tref
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.tref
generated: 2026-08-22
tags: [mapdl-command]
---

# TREF

PyMAPDL: `mapdl.tref(tref='', **kwargs)`

Defines the reference temperature for thermal strain calculations.

## Parameters

**tref**

Reference temperature for thermal expansion.

If the uniform temperature ( [[tunif|TUNIF]] ) is not specified, it is also set to this value.

## Notes

Defines the reference temperature for the thermal strain calculations in structural analyses. Thermal strains are given by α \* (T - TREF), where α is the coefficient of thermal expansion. Input the strain via ALPX, ALPY, ALPZ (the secant or mean coefficient value), or CTEX, CTEY, CTEZ (the instantaneous coefficient value), or the thermal strain value (THSX, THSY, THSZ). T is the element temperature. If α is temperature-dependent, `TREF` should be in the range of temperatures you define using the [[mptemp|MPTEMP]] command.

Reference temperatures may also be input per material by specifying a value on the [[mp|MP]] material property command:

[[mp|MP]],REFT, `MAT`, `C0`.

Only a constant (non-temperature-dependent) value is valid. The value input on the **TREF** command applies to all materials not having a specified material property definition.

To convert temperature-dependent secant coefficients of thermal expansion (SCTE) data (properties ALPX, ALPY, ALPZ) from the definition temperature to the reference temperature defined via a **TREF** (or [[mp|MP]],REFT) command, issue the [[mpamod|MPAMOD]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TREF.html

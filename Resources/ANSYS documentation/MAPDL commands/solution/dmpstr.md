---
apdl: "DMPSTR"
method: dmpstr
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.dmpstr
generated: 2026-08-22
tags: [mapdl-command]
---

# DMPSTR

PyMAPDL: `mapdl.dmpstr(coeff='', dmpsfreqtab='', **kwargs)`

Sets constant structural damping data.

**Command default:**

Use damping as defined by [Damping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR1D.html#strelemdamp)

## Parameters

**coeff**: Constant structural damping coefficient.

**dmpsfreqtab**: Average excitation frequency table (Hz) for the calculation of equivalent viscous damping from structural damping input ( **DMPSTR** and [[mp|MP]],DMPS) in a full transient analysis. Enclose the table name in percent signs (%) and use the [[dim|*DIM]] command to define the table with primary variable TIME. To define a constant frequency instead of a table, see [[trnopt|TRNOPT]].

## Notes

Sets a constant structural (or hysteretic) damping coefficient for use in these analysis types:

- Harmonic ( [[antype|ANTYPE]],HARMIC) - full, [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros), or mode-superposition
- Modal ( [[antype|ANTYPE]],MODAL) with [[modopt|MODOPT]],UNSYM, DAMP, or QRDAMP.

> 

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

**DMPSTR** is also supported in transient ( [[antype|ANTYPE]],TRANS) analyses (full or QRDAMP mode- superposition) as an equivalent viscous damping when an average excitation frequency is specified. For a full or mode-superposition transient, specify a constant excitation frequency as `DMPSFreq` on the [[trnopt|TRNOPT]] command. For a full transient, you can alternatively specify a table of frequencies using `DMPSFreqTab` on this command. `DMPSFreqTab` overwrites `DMPSFreq` on [[trnopt|TRNOPT]].

Note that for structures with multiple materials, [[mp|MP]],DMPS can also be used to specify constant structural material damping on a per material basis. If both **DMPSTR** and [[mp|MP]],DMPS are specified, the damping effects are additive.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DMPSTR.html

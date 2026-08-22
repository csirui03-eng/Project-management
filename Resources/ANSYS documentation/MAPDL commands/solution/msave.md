---
apdl: "MSAVE"
method: msave
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.msave
generated: 2026-08-22
tags: [mapdl-command]
---

# MSAVE

PyMAPDL: `mapdl.msave(key='', **kwargs)`

Sets the solver memory saving option. This option only applies to the PCG solver (including PCG Lanczos).

## Parameters

**key**

Activation key:

- `0 or OFF` - Use global assembly for the stiffness matrix (and mass matrix, when using PCG Lanczos) of the entire model.
- `1 or ON` - Use an element-by-element approach when possible to save memory during the solution. In this case, the global stiffness (and mass) matrix is not assembled; element stiffness (and mass) is regenerated during PCG or PCG Lanczos iterations.

## Notes

**MSAVE**,ON only applies to and is the default for parts of the model using the following element types with linear material properties that meet the conditions listed below.

- `SOLID186` (Structural Solid only)
- `SOLID187`

The following conditions must also be true:

- The PCG solver has been specified.
- Small strains are assumed ( [[nlgeom|NLGEOM]],OFF).
- No prestress effects ( [[pstres|PSTRES]] ) are included.
- All nodes on the supported element types must be defined (that is, the midside nodes cannot be removed using the [[emid|EMID]] command).
- For elements with thermally dependent material properties, **MSAVE**,ON applies only to elements with uniform temperatures prescribed.
- The default element coordinate system must be used.

If you manually force **MSAVE**,ON by including it in the input file, the model can include the following additional conditions:

- The analysis can be a modal analysis using the PCG Lanczos method ( [[modopt|MODOPT]],LANPCG).
- Large deflection effects ( [[nlgeom|NLGEOM]],ON) can be included for `SOLID186` and/or `SOLID187` elements.
- `SOLID185` (brick shapes and KEYOPT(2) = 3 only) elements can be included for small strains ( [[nlgeom|NLGEOM]],OFF).

All other element types or other parts of the model that don't meet the above criteria will be solved using global assembly ( **MSAVE**,OFF). This command can result in memory savings of up to 70 percent over the global assembly approach for the part of the model that meets the criteria. Depending on the hardware (for example, processor speed, memory bandwidth, etc.), the solution time may increase or decrease when this feature is used.

This memory-saving feature runs in parallel when multiple processors are used with the [[config|/CONFIG]] command or in a distributed-memory parallel (DMP) solution. The gain in performance with using multiple processors with this feature turned on should be similar to the default case when this feature is turned off. Performance also improves when using the uniform reduced integration option for `SOLID186` elements.

This command does not support the layered option of the SOLID185 and `SOLID186` elements.

When using **MSAVE**,ON with the [[pcgopt|PCGOPT]] command, note the following restrictions:

- For static and modal analyses, **MSAVE**,ON is not valid when using a `Lev_Diff` value of 5 on the [[pcgopt|PCGOPT]] command; `Lev_Diff` is automatically reset to 2.
- For modal analyses, **MSAVE**,ON is not valid with the `StrmCk` option of the [[pcgopt|PCGOPT]] command; `Strmck` is set to OFF.
- For all analysis types, **MSAVE**,ON is not valid when the Lagrange multiplier option ( `LM_Key` ) of the [[pcgopt|PCGOPT]] command is set to ON; the **MSAVE** activation key is set to OFF.
- For linear perturbation static and modal analyses, **MSAVE**,ON is not valid; the **MSAVE** activation key is set to OFF.
- For static analyses, **MSAVE**,ON is not valid when the `Fallback` option of the [[pcgopt|PCGOPT]] command is enabled; `Fallback` is automatically reset to OFF.

When using **MSAVE**,ON for modal analyses, no `.FULL` file will be created. The `.FULL` file may be necessary for subsequent analyses (for example, harmonic, transient mode- superposition, or spectrum analyses). To generate the `.FULL` file, rerun the modal analysis using the [[wrfull|WRFULL]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSAVE.html

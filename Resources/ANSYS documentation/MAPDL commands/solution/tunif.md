---
apdl: "TUNIF"
method: tunif
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.tunif
generated: 2026-08-22
tags: [mapdl-command]
---

# TUNIF

PyMAPDL: `mapdl.tunif(temp='', **kwargs)`

Assigns a uniform temperature to all nodes.

## Parameters

**temp**: Uniform temperature assigned to the nodes. If a `TEMP` value is not specified, the uniform temperature is set to zero.

## Notes

**TUNIF** is a convenient form of the more general [[bfunif|BFUNIF]] command.

In a transient or nonlinear thermal analysis, the uniform temperature is used during the first iteration of a solution as follows:

- as the starting nodal temperature, except where temperatures are explicitly specified ( [[d|D]], [[dk|DK]] )
- to evaluate temperature-dependent material properties.

In a structural analysis, the uniform temperature is used as the  
default temperature for thermal strain calculations and material property evaluation, except where body load

temperatures are specified ( [[bf|BF]], [[bfe|BFE]], [[bfk|BFK]], [[ldread|LDREAD]] ). In other scalar field analyses, the uniform temperature is used for material property evaluation.

Because **TUNIF** (or [[bfunif|BFUNIF]],TEMP) is step-applied in the first iteration, issue a [[bf|BF]],ALL,TEMP, `Value` command to ramp on a uniform temperature load.

The command default sets the uniform temperature to the reference temperature defined via the [[tref|TREF]] command only (and not the [[mp|MP]],REFT command).

If using the command default to set the uniform temperature (to the reference temperature set via [[tref|TREF]] ), you can convert temperature-dependent secant coefficients of thermal expansion (SCTEs) from the definition temperature to the uniform temperature. To do so, issue the [[mpamod|MPAMOD]] command.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TUNIF.html

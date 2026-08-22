---
apdl: "CMACEL"
method: cmacel
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.cmacel
generated: 2026-08-22
tags: [mapdl-command]
---

# CMACEL

PyMAPDL: `mapdl.cmacel(cm_name='', cmacel_x='', cmacel_y='', cmacel_z='', **kwargs)`

Specifies the translational acceleration of an element component

## Parameters

**cm_name**: The name of the element component.

**cmacel_x**, **cmacel_y**, **cmacel_z**: Acceleration of the element component `CM_NAME` in the global Cartesian X, Y, and Z axis directions, respectively.

## Notes

The **CMACEL** command specifies the translational acceleration of the element component in each of the global Cartesian (X, Y, and Z) axis directions.

Components for which you want to specify acceleration loading must consist of elements only. The elements you use cannot be part of more than one component, and elements that share nodes cannot exist in different element components. You cannot apply the loading to an assembly of element components.

To simulate gravity (by using inertial effects), accelerate the structure in the direction opposite to gravity. For example, apply a positive `CMACELY` to simulate gravity acting in the negative Y direction. Units are length/time <sup>2</sup>.

You can define the acceleration for the following analyses types:

- Static ( [[antype|ANTYPE]],STATIC)
- Harmonic ( [[antype|ANTYPE]],HARMIC), full, [VT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) \[ \], [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros) \[ \], or mode-superposition method
- Transient ( [[antype|ANTYPE]],TRANS), [full](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_4.html#strnote11tlm71999) or mode-superposition method
- Substructure ( [[antype|ANTYPE]],SUBSTR)

> 

Loads for VT and Krylov methods are supported as long as they are not:

- complex tabulated loads (constant or trapezoidal loads in tabulated form are supported)
- used in conjunction with Rotordynamics ( [[coriolis|CORIOLIS]],on).

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

Accelerations are combined with the element mass matrices to form a body-force load vector term. Units of acceleration and mass must be consistent to give a product of force units.

The **CMACEL** command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `CMACEL_X`, `CMACEL_Y`, and `CMACEL_Z` input values ( [[dim|*DIM]] ) as a function of both time and frequency for full transient and harmonic analyses.

Related commands for inertia loads are [[acel|ACEL]], [[cgloc|CGLOC]], [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], [[domega|DOMEGA]], [[omega|OMEGA]], [[cmomega|CMOMEGA]], and [[cmdomega|CMDOMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

This command is also valid in [[prep7|/PREP7]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMACEL.html

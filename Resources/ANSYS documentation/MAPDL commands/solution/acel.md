---
apdl: "ACEL"
method: acel
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.acel
generated: 2026-08-22
tags: [mapdl-command]
---

# ACEL

PyMAPDL: `mapdl.acel(acel_x='', acel_y='', acel_z='', **kwargs)`

Specifies the linear acceleration of the global Cartesian reference frame for the analysis.

## Parameters

**acel_x**, **acel_y**, **acel_z**: Linear acceleration of the reference frame along global Cartesian X, Y, and Z axes, respectively.

## Notes

In the absence of any other loads or supports, the acceleration of the structure in each of the global Cartesian (X, Y, and Z) axes would be equal in magnitude but opposite in sign to that applied in the **ACEL** command. Thus, to simulate gravity (by using inertial effects), accelerate the reference frame with an **ACEL** command in the direction opposite to gravity.

You can define the acceleration for the following analyses types:

- Static ( [[antype|ANTYPE]],STATIC)
- Harmonic ( [[antype|ANTYPE]],HARMIC), full, [VT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) \[ \], [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros) \[ \], or mode-superposition
- Transient ( [[antype|ANTYPE]],TRANS), [full](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_4.html#strnote11tlm71999) or mode-superposition
- Substructure ( [[antype|ANTYPE]],SUBSTR).

Loads for VT and Krylov methods are supported as long as they are not:

- complex tabulated loads (constant or trapezoidal loads in tabulated form are supported)
- used in conjunction with Rotordynamics ( [[coriolis|CORIOLIS]],on).

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

For all transient dynamic ( [[antype|ANTYPE]],TRANS) analyses, accelerations are combined with the element mass matrices to form a body-force load vector term. The element mass matrix may be formed from a mass input constant or from a nonzero density (DENS) property, depending upon the element type.

For analysis type [[antype|ANTYPE]],HARMIC, the acceleration is assumed to be the real component with a zero imaginary component.

Units of acceleration and mass must be consistent to give a product of force units.

The **ACEL** command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `ACEL_X`, `ACEL_Y`, and `ACEL_Z` input values ( [[dim|*DIM]] ) as a function of both time and frequency for full transient and harmonic analyses.

Related commands for rotational effects are [[cmacel|CMACEL]], [[cgloc|CGLOC]], [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], [[domega|DOMEGA]], [[omega|OMEGA]], [[cmomega|CMOMEGA]], and [[cmdomega|CMDOMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

This command is also valid in [[prep7|/PREP7]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ACEL.html

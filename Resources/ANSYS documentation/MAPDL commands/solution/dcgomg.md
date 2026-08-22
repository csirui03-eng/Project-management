---
apdl: "DCGOMG"
method: dcgomg
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.dcgomg
generated: 2026-08-22
tags: [mapdl-command]
---

# DCGOMG

PyMAPDL: `mapdl.dcgomg(dcgox='', dcgoy='', dcgoz='', **kwargs)`

Specifies the rotational acceleration of the global origin.

## Parameters

**dcgox**, **dcgoy**, **dcgoz**: Rotational acceleration of the global origin about the acceleration system X, Y, and Z axes.

## Notes

Specifies the rotational acceleration of the global origin about each of the acceleration coordinate system axes ( [[cgloc|CGLOC]] ). Rotational accelerations may be defined in these analysis types:

- Static ( [[antype|ANTYPE]],STATIC)
- Harmonic ( [[antype|ANTYPE]],HARMIC) - full, [VT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) \[ \], [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros) \[ \], or mode-superposition
- Transient ( [[antype|ANTYPE]],TRANS) - [full](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_4.html#strnote11tlm71999) or mode-superposition
- Substructuring ( [[antype|ANTYPE]],SUBSTR)
- Modal ( [[antype|ANTYPE]],MODAL)

> 

Loads for VT and Krylov methods are supported as long as they are not:

- complex tabulated loads (constant or trapezoidal loads in tabulated form are supported)
- used in conjunction with Rotordynamics ( [[coriolis|CORIOLIS]],on).

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

See [Acceleration Effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool1.html#) <sup>2</sup>.

The **DCGOMG** command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `DCGOMG_X`, `DCGOMG_Y`, and `DCGOMG_Z` input values ( [[dim|*DIM]] ) for full transient and harmonic analyses.

Related commands are [[acel|ACEL]], [[cgloc|CGLOC]], [[cgomga|CGOMGA]], [[domega|DOMEGA]], and [[omega|OMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DCGOMG.html

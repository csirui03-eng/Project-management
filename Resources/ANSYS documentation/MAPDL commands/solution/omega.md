---
apdl: "OMEGA"
method: omega
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.omega
generated: 2026-08-22
tags: [mapdl-command]
---

# OMEGA

PyMAPDL: `mapdl.omega(omegx='', omegy='', omegz='', **kwargs)`

Specifies the rotational velocity of the structure.

## Parameters

**omegx**, **omegy**, **omegz**: Rotational velocity of the structure about the global Cartesian X, Y, and Z axes.

## Notes

This command specifies the rotational velocity of the structure about each of the global Cartesian axes (right-hand rule). Rotational velocities may be defined in these analysis types:

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

The command supports tabular boundary conditions (`TABNAME_X`, `TABNAME_Y`, and `TABNAME_Z`) for `OMEGA_X`, `OMEGA_Y`, and `OMEGA_Z` input values ( [[dim|*DIM]] ) for full transient and harmonic analyses.

Rotational velocities are combined with the element mass matrices to form a body-force load vector term. Units are radians/time. Related commands are [[acel|ACEL]], [[cgloc|CGLOC]], [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], and [[domega|DOMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

If you have applied the Coriolis effect ( [[coriolis|CORIOLIS]] ) using a [stationary reference frame](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTGENDYNEQ.html#rotintrogendyneq2), this command takes the gyroscopic damping matrix into account for the elements listed in the **Stationary Reference Frame** heading in the notes section of the [[coriolis|CORIOLIS]] command. The element axis must pass through the global Cartesian origin. The program verifies that the rotation vector axis is parallel to the axis of the element; if not, the gyroscopic effect is not applied. After issuing **OMEGA** when the Coriolis or gyroscopic effect is present, a subsequently issued [[cmomega|CMOMEGA]] command has no effect.

The load interpolation setting ( [[kbc|KBC]] ) applies to the rotational velocity, in particular the `OMGSQRDKEY` option for quadratic interpolation.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OMEGA.html

---
apdl: "HROCEAN"
method: hrocean
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.hrocean
generated: 2026-08-22
tags: [mapdl-command]
---

# HROCEAN

PyMAPDL: `mapdl.hrocean(type_='', nphase='', **kwargs)`

Perform the harmonic ocean wave procedure (HOWP).

## Parameters

**type_**

Specifies how to include ocean wave information in a harmonic analysis:

- `HARMONIC` - Performs a harmonic analysis using both real and imaginary load vectors calculated via the [harmonic ocean wave procedure (HOWP)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc4.html#eq63629e12-76f7-4f52-97a7-ce8593b3f24e). This behavior is the default. This option performs a harmonic analysis running at a frequency determined by the wave period (specified via [[octable|OCTABLE]] command input).
- `STATIC` - Performs a static analysis using both real and imaginary load vectors (calculated via HOWP). This option works by performing a harmonic analysis running at a frequency of 0.0.
- `OFF` - Deactivates a previously activated HOWP and performs a standard harmonic analysis.

**nphase**: Positive number specifying the number of phases to calculate forces. This value must be at least 8. The default value is 20.

## Notes

The **HROCEAN** command applies ocean wave information (obtained via the [[ocdata|OCDATA]] and [[octable|OCTABLE]] commands) in a harmonic analysis ( [[antype|ANTYPE]],HARMIC) as real and imaginary forces.

You can apply only one ocean load at a time.

The applied frequency in the harmonic ( `Type` = HARMONIC) analysis is based on the wave period input on the [[octable|OCTABLE]] command (and not on [[harfrq|HARFRQ]] command input, which cannot be used). Phase-shift input on the [[octable|OCTABLE]] command is ignored.

HOWP does not generate a damping matrix. If you require a damping matrix, you must add it separately.

The command applies to regular wave types only (Airy with one wave component, Wheeler with one wave component, Stokes, and stream function). Irregular wave types are not supported. For information about wave types, see [Hydrodynamic Loads](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_et8.html#thy_dynpresshead)

The program calculates the forces on each load component of each element at `NPHASE` solutions, spread evenly over one wave cycle. Then, the minimum and maximum, and the phase between them, are calculated. The command uses the resulting information to generate the real and imaginary loads.

HOWP cannot be used with stress stiffening.

HOWP works with the full harmonic analysis method ( [[hropt|HROPT]],FULL) only.

For more information, see [Harmonic Ocean Wave Procedure (HOWP)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc4.html#eq63629e12-76f7-4f52-97a7-ce8593b3f24e)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HROCEAN.html

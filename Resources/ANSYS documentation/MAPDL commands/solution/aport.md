---
apdl: "APORT"
method: aport
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.aport
generated: 2026-08-22
tags: [mapdl-command]
---

# APORT

PyMAPDL: `mapdl.aport(portnum='', label='', kcn='', pres='', phase='', val1='', val2='', val3='', val4='', **kwargs)`

Specifies input data for plane wave and acoustic duct ports.

## Parameters

**portnum**: Port number. This number is associated with an exterior port or interior port previously specified by the [[sf|SF]] and [[bf|BF]] family of commands, respectively. The number must be between 1 and 50.

**label**

- `PLAN` - Incident plane wave.
- `RECT` - Rectangular duct.
- `CIRC` - Circular duct.
- `COAX` - Coaxial duct.
- `LIST` - List the port settings. If `PortNum` = ALL, list the port settings for all defined ports.
- `DELE` - Delete defined ports. If `PortNum` = ALL, delete all defined ports.

**kcn**: A previously-defined local ( `KCN` \>10) or global ( `KCN` = 0) Cartesian coordinate system number used to specify the geometric properties of the duct. Defaults to the global Cartesian coordinate system (0). The local Z-direction must be the direction of wave propagation. The origin of the local coordinate system must be centered about the face of the duct port without considering symmetry.

**pres**: Zero-to-peak amplitude of the pressure. If blank, the port will appear as a matching impedance.

**phase**: Phase angle of the applied pressure in degrees. Defaults to 0.

**val1**, **val2**, **val3**, **val4**

Additional input. The meaning of `VAL1` through `VAL4` varies depending on the specified `Label`.

`Label` = PLAN:

- `VAL1` - (equation omitted) angle from positive X-axis to positive Y-axis in the local Cartesian coordinates ( `KCN` ).
- `VAL2` - (equation omitted) angle away from positive Z-axis in the local Cartesian coordinates ( `KCN` ).
- `VAL3-VAL4` - Not used.

`Label` = RECT:

- `VAL1` - Width of the rectangular duct.
- `VAL2` - Height of the rectangular duct.
- `VAL3` - Mode index for pressure variation along the width (defaults to 0).
- `VAL4` - Mode index for pressure variation along the height (defaults to 0).

`Label` = CIRC:

- `VAL1` - Radius of the circular duct.
- `VAL2` - Not used.
- `VAL3` - Mode index for pressure variation along the azimuth (defaults to 0).
- `VAL4` - Mode index for pressure variation along the radii (defaults to 0).

`Label` = COAX:

- `VAL1` - Inner radius of the coaxial duct.
- `VAL2` - Outer radius of the coaxial duct.
- `VAL3` - Mode index for pressure variation along the azimuth (defaults to 0).
- `VAL4` - Mode index for pressure variation along the radii (defaults to 0).

## Notes

Use the **APORT** command to launch a specified analytic acoustic mode into a guided duct.

The low-order `FLUID30` element does not support the higher modes in the coaxial duct ( `Label` = COAX).

For more information, see [Specified Mode Excitation in an Acoustic Duct](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_excit_src.html#) [Analytic Port Modes in a Duct](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thyacous_proprad.html#eq897eb704-ab8d-4c80-aa70-eeda53797cc5)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_aport.html

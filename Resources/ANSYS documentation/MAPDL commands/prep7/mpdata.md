---
apdl: "MPDATA"
method: mpdata
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpdata
generated: 2026-08-22
tags: [mapdl-command]
---

# MPDATA

PyMAPDL: `mapdl.mpdata(lab='', mat='', sloc='', c1='', c2='', c3='', c4='', c5='', c6='', **kwargs)`

Defines property data to be associated with the temperature table.

## Parameters

**lab**

Valid property label. Applicable labels are listed under "Material Properties" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

- `ALPD` - Mass matrix multiplier for damping.
- `ALPX` - Secant coefficients of thermal expansion (also ALPY, ALPZ). (See also [[mpamod|MPAMOD]] command for adjustment to reference temperature).
- `BETD` - Stiffness matrix multiplier for damping.
- `BETX` - Coefficient of diffusion expansion (also BETY, BETZ)
- `C` - Specific heat.
- `CREF` - Reference concentration (may not be temperature dependent)
- `CSAT` - Saturated concentration
- `CTEX` - Instantaneous coefficients of thermal expansion (also CTEY, CTEZ).
- `DENS` - Mass density.
- `DMPS` - Constant material damping coefficient.
- `DXX` - Diffusivity coefficients (also DYY, DZZ)
- `EMIS` - Emissivity.
- `ENTH` - Enthalpy.
- `EX` - Elastic moduli (also EY, EZ).
- `GXY` - Shear moduli (also GYZ, GXZ).
- `HF` - Convection or film coefficient.
- `KXX` - Thermal conductivities (also KYY, KZZ).
- `LSST` - Dielectric loss tangent.
- `MGXX` - Magnetic coercive forces (also MGYY, MGZZ).
- `MU` - Coefficient of friction.
- `MURX` - Magnetic relative permeabilities (also MURY, MURZ).
- `NUXY` - Minor Poisson's ratios (also NUYZ, NUXZ).
- `PERX` - Electric relative permittivities (also PERY, PERZ).
- `PRXY` - Major Poisson's ratios (also PRYZ, PRXZ).
- `QRATE` - Heat generation rate.
- `REFT` - Reference temperature (may not be temperature dependent).
- `RH` - Hall Coefficient.
- `RSVX` - Electrical resistivities (also RSVY, RSVZ).
- `SBKX` - Seebeck coefficients (also SBKY, SBKZ).
- `SONC` - Sonic velocity.
- `THSX` - Thermal strain (also THSY, THSZ).
- `VISC` - Viscosity.

**mat**: Material reference number to be associated with the elements (defaults to 1 if you specify zero or no material number).

**sloc**, **c1**, **c2**, **c3**, **c4**, **c5**, **c6**: Property data values assigned to six locations starting with `SLOC`. If a value is already in this location, it is redefined. A blank (or zero) value for `C1` resets the previous value in `SLOC` to zero. A value of zero can only be assigned by `C1`. Blank (or zero) values for `C2` to `C6` leave the corresponding previous values unchanged.

## Notes

Defines a table of property data to be associated with the temperature table. Repeat **MPDATA** command for additional values (100 maximum). Temperatures must be defined first ( [[mptemp|MPTEMP]] ). Also stores assembled property function table (temperature and data) in virtual space.

This command is also valid in SOLUTION.

Ansys Mechanical Enterprise The command **MPDATA**,LSST is only available to the Ansys Mechanical Enterprise product family (Ansys Mechanical Enterprise, Ansys Mechanical Enterprise PrepPost, and Ansys Mechanical Enterprise Solver).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPDATA.html

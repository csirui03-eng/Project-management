---
apdl: "EMUNIT"
method: emunit
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.emunit
generated: 2026-08-22
tags: [mapdl-command]
---

# EMUNIT

PyMAPDL: `mapdl.emunit(lab='', value='', **kwargs)`

Specifies the system of units for magnetic field problems.

**Command default:**

Rationalized MKS system of units (meters, amperes, henries, webers, etc.). Free-space permeability is set to 4 πe-7 Henries/meter, free-space permittivity is set to 8.85e-12 Farads/meter.

## Parameters

**lab**

Label specifying the type of units:

- `MKS` - Rationalized MKS system of units (meters, amperes, henries, webers, etc.). Free-space permeability is set to 4 πe-7 henries/meter. Free-space permittivity is set to 8.85 e-12 F/m.
- `MUZRO` - User defined system of units. Free-space permeability is set to the value input for `VALUE`. Other units must correspond to the permeability units. Relative permeability may be altered to absolute values.
- `EPZRO` - User defined system of units. Free-space permittivity is set to the value input for VALUE. Other units must correspond to the permittivity units.

**value**: User value of free-space permeability (defaults to 1) if `Lab` = MUZRO, or free-space permittivity (defaults to 1) if `Lab` = EPZRO.

## Notes

Specifies the system of units to be used for electric and magnetic field problems. The free-space permeability and permittivity values may be set as desired. These values are used with the relative property values ( [[mp|MP]] ) to establish absolute property values. If the magnetic source field strength (H<sub>s</sub> ) has already been calculated ( [[biot|BIOT]] ), switching **EMUNIT** will not change the values.

For micro-electromechanical systems (MEMS), where dimensions are on the order of microns, see the conversion factors in [System of Units](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU1_3.html#couthermelesmksvfa) in the [Coupled-Field Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU_N4.html).

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMUNIT.html

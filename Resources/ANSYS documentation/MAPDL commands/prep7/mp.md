---
apdl: "MP"
method: mp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mp
generated: 2026-08-22
tags: [mapdl-command]
---

# MP

PyMAPDL: `mapdl.mp(lab='', mat='', c0='', c1='', c2='', c3='', c4='', **kwargs)`

Defines a linear material property as a constant or a function of temperature.

## Parameters

**lab**

Valid material property label. Applicable labels are listed under "Material Properties" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

- `ALPD` - Mass matrix multiplier for damping.

- `ALPX` - Secant coefficients of thermal expansion (also ALPY, ALPZ).

- `BETD` - Stiffness matrix multiplier for damping.

- `BETX` - Coefficient of diffusion expansion (also BETY, BETZ)

- `BVIS` - Bulk viscosity

- `C` - Specific heat

- `CREF` - Reference concentration (may not be temperature dependent)

- `CSAT` - Saturated concentration

- `CTEX` - Instantaneous coefficients of thermal expansion (also CTEY, CTEZ)

- `CVH` - Heat coefficient at constant volume per unit of mass

- `DENS` - Mass density.

- `DMPR` - Damping ratio.

- `DMPS` - Constant structural damping coefficient.

- `DXX` - Diffusivity coefficients (also DYY, DZZ)

- `EMIS` - Emissivity. For default behavior, see Notes.

- `ENTH` - Enthalpy. See Considerations for Enthalpy.

- `EX` - Elastic moduli (also EY, EZ)

- `GXY` - Shear moduli (also GYZ, GXZ)

- `HF` - Convection or film coefficient

- `KXX` - Thermal conductivities (also KYY, KZZ)

- `LSST` - Electric loss tangent

- `LSSM` - Magnetic loss tangent

- `MGXX` - Magnetic coercive forces (also MGYY, MGZZ)

- `MURX` - Magnetic relative permeabilities (also MURY, MURZ)

- `MU` - Coefficient of friction

- `NUXY` - Minor Poisson's ratios (also NUYZ, NUXZ) (NUXY = ν<sub>yx</sub>, as described in [Stress-Strain Relationships](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_str1.html#eq84e81ad6-8b11-4580 - 8034-9e5f20df8c23)

- `PERX` - Electric relative permittivities (also PERY, PERZ)

  If you enter permittivity values less than 1 for `SOLID5`, `PLANE13`, or `SOLID98`, the program interprets the values as absolute permittivity. Values input for `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, or `SOLID227` are always interpreted as relative permittivity.

- `PRXY` - Major Poisson's ratios (also PRYZ, PRXZ) (PRXY = ν<sub>xy</sub>, as described in [Stress-Strain Relationships](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_str1.html#eq84e81ad6-8b11-4580 - 8034-9e5f20df8c23)

- `QRATE` - Heat generation rate for thermal mass element `MASS71`. Fraction of plastic work converted to heat (Taylor-Quinney coefficient) or fraction of viscoelastic loss converted to heat for coupled- field elements `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227`.

- `REFT` - Reference temperature. Must be defined as a constant; C1 through C4 are ignored.

- `RH` - Hall Coefficient.

- `RSVX` - Electrical resistivities (also RSVY, RSVZ).

- `SBKX` - Seebeck coefficients (also SBKY, SBKZ).

- `SONC` - Sonic velocity.

- `THSX` - Thermal strain (also THSY, THSZ).

- `VISC` - Viscosity.

**mat**: Material reference number to be associated with the elements (defaults to the current MAT setting ( [[mat|MAT]] )).

**c0**: Material property value, or if a property-versus-temperature polynomial is being defined, the constant term in the polynomial. `C0` can also be a table name (`tabname`); if `C0` is a table name, `C1` through `C4` are ignored.

**c1**, **c2**, **c3**, **c4**: Coefficients of the linear, quadratic, cubic, and quartic terms, respectively, in the property- versus-temperature polynomial. Leave blank (or set to zero) for a constant material property.

## Notes

**MP** defines a linear material property as a constant or in terms of a fourth order polynomial as a function of temperature. (See the [[tb|TB]] command for nonlinear material property input.) Linear material properties typically require a single substep for solution, whereas nonlinear material properties require multiple substeps.

If the constants C1 - C4 are input, the polynomial

Property = `C0` + `C1` (T) + `C2` (T) <sup>2</sup> + `C3` (T) <sup>3</sup> + `C4` (T) <sup>4</sup>

is evaluated at discrete temperature points with linear interpolation between points (that is, a piecewise linear representation) and a constant-valued extrapolation beyond the extreme points. First-order properties use two discrete points (±9999°). The [[mptemp|MPTEMP]] or [[mptgen|MPTGEN]] commands must be used for second and higher order properties to define appropriate temperature steps. To ensure that the number of temperatures defined via the [[mptemp|MPTEMP]] and [[mptgen|MPTGEN]] commands is minimally sufficient for a reasonable representation of the curve, Mechanical APDL generates an error message if the number is less than N, and a warning message if the number is less than 2N. The value N represents the highest coefficient used; for example, if C3 is nonzero and C4 is zero, a cubic curve is being used which is defined using 4 coefficients so that N = 4.

Some elements (for example, `FLUID116` ) support tabular input for material properties. Use the [[dim|*DIM]] command to create the table of property values as a function of the independent variables. Then input this table name ( `C0` = `tabname`) when defining the property via the **MP** command. Tabular material properties are calculated before the first iteration (that is, using initial values ( [[ic|IC]] )). For a list of elements that support tabular material properties and associated primary variables, see [Defining Linear Material Properties Using Tabular Input](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/ansmatdeflin.html#fntbdatareqd)

When defining a reference temperature ( **MP**,REFT), you can convert temperature-dependent secant coefficients of thermal expansion (SCTE) data from the definition temperature to the reference temperature. To do so, issue the [[mpamod|MPAMOD]] command.

This command is also valid in SOLUTION.

### Considerations for Enthalpy ( `Lab` = ENTH)

- To ensure correct results, you must define enthalpy over a large enough temperature range to span all computed temperatures during the solution. The [[tb|TB]] command does not extrapolate enthalpy values beyond the specified temp range like the **MP** command does.
- If both the [[tb|TB]] and **MP** commands are used to specify enthalpy values, enthalpy values defined via the [[tb|TB]] command are used and those defined via the **MP** command are ignored.

### Default behavior for Emissivity ( `Lab` = EMIS)

There is no command default value for emissivity, and you must specify it by issuing **MP**,EMIS. Otherwise, an error message appears. If you issue **MP**,EMIS without specifying `C0`, `C1`, `C2`, `C3`, `C4` values, emissivity defaults to 0.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MP.html

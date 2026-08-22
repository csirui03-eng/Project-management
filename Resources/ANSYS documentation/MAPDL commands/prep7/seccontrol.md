---
apdl: "SECCONTROL"
method: seccontrol
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.seccontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# SECCONTROL

PyMAPDL: `mapdl.seccontrol(val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', val10='', val11='', val12='', val13='', **kwargs)`

Supplements or overrides default section properties.

## Parameters

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**, **val10**, **val11**, **val12**, **val13**: Values, such as the length of a side or the numbers of cells along the width, that describe the geometry of a section. See the [[seccontrol#Notes|SECCONTROL]] section of this command description for details about these values for the various section types.

## Notes

The **SECCONTROL** command is divided into these operation types: Beams, Links, Pipes, Shells, and Reinforcings.

Values are associated with the most recently issued [[sectype|SECTYPE]] command. The data required is determined by the section type and is different for each type.

**SECCONTROL** overrides the program-calculated transverse-shear stiffness.

The command does not apply to thermal shell elements `SHELL131` and `SHELL132` or thermal solid elements `SOLID278` and `SOLID279`.

**Beams**

### Type: BEAM

- Data to provide in the value fields ( `VAL1` through `VAL4` ):

\* `TXZ` - User transverse shear stiffness. .. flat-table :

``` text
* -- - Unused field.
```

- `TXY` - User transverse shear stiffness.
- `ADDMAS` - Added mass per unit length.

**Links**

### Type: LINK

- Data to provide in the value fields ( `VAL1`, `VAL2`, `VAL3`, `VAL4`, `VAL5`, `VAL6` ):
- `ADDMAS` - Added mass per unit length.
- `TENSKEY` - Flag specifying tension and compression, tension only, or compression only (not valid for `CABLE280` :
- 0 - Tension and compression (default).

\* 1 - Tension only. .. flat-table :

``` text
* -1 - Compression only.
```

- `CV1`, `CV2` - [Damping coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_LINK180.html#eqe20b311a-4d50-4c25-a2a3-ce500a7b0382).
- `CV3` - Compressive stiffness scaling factor (for `CABLE280` only). The ratio between compressive stiffness and tensile stiffness. Default - 1.0e-5. Maximum - 1.0.
- `CV4` - Viscous regularization factor (for `CABLE280` only). Default - 0.05. Maximum - 1.0.

**Pipes**

### Type: PIPE

- Data to provide in the value field ( `VAL1` ):
- `ADDMAS` - Added mass per unit length. Use this value to account for extra hardware only.
- **Notes**
- Other masses are handled as follows:
- The mass of the internal fluid is accounted for by `M` <sub>int</sub> on the [[secdata|SECDATA]] command.
- The mass of the outer covering (insulation) is accounted for by `M` <sub>ins</sub> on the [[secdata|SECDATA]] command.
- The mass of the external fluid is accounted for by `MATOC` on the [[ocdata|OCDATA]] command.

**Shells**

### Type: SHELL

- Data to provide in the value fields ( `VAL1` through `VAL8` ):
- `E` 11 - User transverse-shear stiffness.
- `E` 22 - User transverse-shear stiffness.
- `E` 12 - User transverse-shear stiffness.
- `ADDMAS` - Added mass-per-unit area.
- `HMEMSCF` - Hourglass-control membrane-scale factor.
- `HBENSCF` - Hourglass-control bending-scale factor.
- `DRLSTIF` - Drill-stiffness scale factor.
- `BENSTIF` - Bending-stiffness scale factor ( `SHELL181` and `SHELL281` ).

**Reinforcing**

### Type: REINF

- Data to provide in the value fields ( `VAL1`, `VAL2`, `VAL3` ):
- `TENSKEY` - Flag specifying tension-and-compression, tension-only, or compression-only reinforcing behavior (valid for structural reinforcing analysis):
- 0 - Tension and compression (default).

\* 1 - Tension only. .. flat-table :

``` text
* -1 - Compression only.
* -------------
```

- `REMBASE` - Flag specifying how base-element material is handled:
- 0 - Retain base-element material in the space occupied by the reinforcing fibers (default).

\* 1 - Remove base-element material in the space occupied by the reinforcing fibers. .. flat-table :

``` text
* -------------
```

- `STSSTATE` - Flag specifying the reinforcing stress state or heat flow:
- For smeared reinforcing:
- 0 - Uniaxial-stress state (for structural reinforcing analysis) or uniaxial heat flow (for thermal reinforcing analysis). Only `kxx` is required. (Default.)
- 1 - Plane-stress state (for structural reinforcing analysis) or anisotropic heat flow (for thermal reinforcing analysis). Both kxx and kyy are specified.
- 2 - Plane-stress state with transverse shear stiffness. Valid for 3D smeared structural reinforcing analysis.
- 3 - Plane-stress state with transverse shear stiffness and bending stiffness. Valid for 3D smeared structural reinforcing analysis with solid base elements.
- For discrete reinforcing:
- 0 - Uniaxial stiffness, or uniaxial heat flow for thermal reinforcing analysis. (Default.)
- 1 - Uniaxial, bending, and torsional stiffness with square cross section. Valid for 3D structural reinforcing analysis with solid base elements.
- **Notes**
- `REMBASE` = 1 typically leads to more accurate models. (The base material must support 1D stress states.) For structural-reinforcing analysis, the base-element material consists of mass, stiffness, and body force. For thermal-reinforcing analysis, the base-element material consists of damping, conduction, and heat generation, and the base-element surface loads (convection and heat flux) are not subtracted. This option is not valid when the base-element material is anisotropic.
- For smeared reinforcing with `STSSTATE` = 0, the equivalent thickness h of the smeared reinforcing layer is determined by h = `A` / `S`, where `A` is the cross-section area of a single fiber and `S` is the distance between two adjacent fibers. (See [[secdata|SECDATA]].)
- `STSSTATE` = 1 to 3 is suitable for homogenous reinforcing layers (membrane) and applies to smeared reinforcing only ( [[sectype|SECTYPE]],,REINF,SMEAR). For smeared reinforcing with `STSSTATE` = 1 to 3, discrete reinforcing with `STSSTATE` = 1, `TENSKEY` is ignored, and the default tension and compression behaviors apply to the reinforcing layers; also, the cross-section area input `A` is the thickness of the reinforcing layers and the distance input `S` is ignored. (See [[secdata|SECDATA]] and [REINF265 Structural/Thermal Input Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_REINF265.html#reinf265inpsummary)
- For discrete reinforcing with `STSSTATE` = 1 or smeared reinforcing with `STSSTATE` = 3, bending or torsional reinforcing stiffness may not be captured adequately when using reinforcing with overly refined high-order base tetrahedral elements ( `SOLID187` or degenerated `SOLID186` ) and the stiffness ratio between reinforcing and base elements is excessive (\> 100x).
- Specified `TENSKEY`, `REMBASE` and `STSSTATE` values apply to all fibers defined in the current section.
- For more information, see [Element Embedding](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECCONTROL.html

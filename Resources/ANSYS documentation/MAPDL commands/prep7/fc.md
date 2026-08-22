---
apdl: "FC"
method: fc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.fc
generated: 2026-08-22
tags: [mapdl-command]
---

# FC

PyMAPDL: `mapdl.fc(mat='', lab1='', lab2='', data1='', data2='', data3='', data4='', data5='', data6='', **kwargs)`

Provides failure criteria information and activates a data table to input temperature-dependent stress and strain limits.

## Parameters

**mat**: Material reference number. You can define failure criteria for up to 250 different materials.

**lab1**

Type of data.

- `TEMP` - Temperatures. Each of the materials you define can have a different set of temperatures to define the failure criteria.
- `EPEL` - Strains.
- `S` - Stresses.

**lab2**

Specific criteria. Not used if `Lab1` = TEMP.

- `XTEN` - Allowable tensile stress or strain in the x-direction. (Must be positive.)
- `XCMP` - Allowable compressive stress or strain in the x-direction. (Defaults to negative of XTEN.)
- `YTEN` - Allowable tensile stress or strain in the y-direction. (Must be positive.)
- `YCMP` - Allowable compressive stress or strain in the y-direction. (Defaults to negative of YTEN.)
- `ZTEN` - Allowable tensile stress or strain in the z-direction. (Must be positive.)
- `ZCMP` - Allowable compressive stress or strain in the z-direction. (Defaults to negative of ZTEN.)
- `XY` - Allowable XY stress or shear strain. (Must be positive.)
- `YZ` - Allowable YZ stress or shear strain. (Must be positive.)
- `XZ` - Allowable XZ stress or shear strain. (Must be positive.)
- `XYCP` - XY coupling coefficient (Used only if `Lab1` = S). Defaults to -1.0. \[ \]
- `YZCP` - YZ coupling coefficient (Used only if `Lab1` = S). Defaults to -1.0. \[ \]
- `XZCP` - XZ coupling coefficient (Used only if `Lab1` = S). Defaults to -1.0. \[ \]
- `XZIT` - XZ tensile inclination parameter for Puck failure index (default = 0.0)
- `XZIC` - XZ compressive inclination parameter for Puck failure index (default = 0.0)
- `YZIT` - YZ tensile inclination parameter for Puck failure index (default = 0.0)
- `YZIC` - YZ compressive inclination parameter for Puck failure index (default = 0.0)
- `G1G2` - Fracture toughness ratio between GI (mode I) and GII (mode II)
- `ETAL` - Longitudinal friction coefficient
- `ETAT` - Transverse friction coefficient
- `APL0` - Fracture angle under pure transverse compression (default to 53) \[ \]

Entering a blank or a zero for XYCP, YZCP, or XZCP triggers the default value of -1.0. To specify an effective zero, use a small, nonzero value (such as 1E-14) instead. For more information, see .

Entering a blank or a zero ALP0 triggers the default value of 53. To specify an effective zero, use a small, nonzero value (such as 1E-14) instead. For more information, see .

**data1**, **data2**, **data3**, **data4**, **data5**, **data6**

Description of `DATA1` through `DATA6`.

- `T1, T2, T3, T4, T5, T6` - Temperature at which limit data is input. Used only when `Lab1` = TEMP.
- `V1, V2, V3, V4, V5, V6` - Value of limit stress or strain at temperature T1 through T6. Used only when `Lab1` = S or EPEL.

## Notes

The data table can be input in either PREP7 or POST1. This table is used only in POST1. When you postprocess failure criteria results defined via the **FC** command ( [[plesol|PLESOL]], [[presol|PRESOL]], [[plnsol|PLNSOL]], [[prnsol|PRNSOL]], [[prrsol|PRRSOL]], etc.), the active coordinate system must be the coordinate system of the material being analyzed. You do this using [[rsys|RSYS]], SOLU. For layered applications, you also use the [[layer|LAYER]] command. See the specific element documentation in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) for information about defining your coordinate system for layers.

Some plotting and printing functions will not support Failure Criteria for your PowerGraphics displays. This could result in minor changes to other data when Failure Criteria are applied. See the appropriate plot or print command documentation for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FC.html

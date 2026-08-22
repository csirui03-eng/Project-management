---
apdl: "TBFT"
method: tbft
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.tbft
generated: 2026-08-22
tags: [mapdl-command]
---

# TBFT

PyMAPDL: `mapdl.tbft(oper='', matid='', option1='', option2='', option3='', option4='', option5='', option6='', option7='', option10='', **kwargs)`

Performs [material curve-fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html) operations.

## Parameters

**oper**

The operation to perform:

- `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
- `FADD` - Define a constitutive model.
- `FDEL` - Delete a constitutive model.
- `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
- `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
- `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature- dependent coefficients.
- `AINI` - Automatically initialize coefficients based on elastic properties and experimental data.
- `SOLVE` - Solve for coefficients.
- `PSOLVE` - Custom multistep solve for coefficients.
- `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
- `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
- `EADD` - Add experimental data.
- `EDEL` - Delete experimental data.
- `Other Operations` - - - - - - - - - - - - - - - - - - - - -
- `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` ).

**matid**: Material reference identification number. (Same as [[tb|TB]], `MATID`.) Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

**option1**

AML - For curve-fitting function operations ( `Oper` = Operation Set 1), this value specifies the category.

UNIA - For adding or deleting your experiment (Operation Set 2), this value specifies the experimental data type.

**option2**

For curve-fitting function operations ( `Oper` = Operation Set 1), this value specifies the constitutive model type. The only valid value is GENR (generic).

To obtain experimental data ( `Oper` = EADD in Operation Set 2) from a file, specify any valid file name. (You can either specify the entire `path` `filename` . `extension` string here and leave `Option3` and `Option4` blank, or specify `filename` here, `extension` in `Option3`, and `path` in `Option4`.)

**option3**

For curve-fitting function operations ( `Oper` = Operation Set 1), specify a unique name for your curve-fitting model.

For obtaining experimental data ( Oper = EADD in Operation Set 2) from a file specified in Option2, specify the file extension.

**option4**

When fixing a specific coefficient to a desired value ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

For `Oper` = SET, see *Set Operations*.

You can also specify `TREF` to indicate the reference temperature, or `COMP` for a partial/complete solution (only for bulk, only for shear, or all coefficients).

If `Oper` = SOLVE, this value specifies the curve-fitting procedure. Valid values are 0 for non- normalized least squares curve-fitting procedure, and 1 for normalized least squares curve- fitting procedure.

For obtaining experimental data ( Oper = EADD) from a file specified in Option2, specify the path in which the file resides.

**option5**

For `Oper` = SET, refer to the following table:

### Set Operations

| Purpose | Option4 | Option5 |
|----|----|----|
| Set the value of the coefficient | Index of coefficient | Value of coefficient |
| Set temperature dependency ON/OFF | TDEP | 1 - ON 0 - OFF |
| Set reference temperature | TREF | Temperature value |

If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

If you are specifying a coefficient to be held constant ( `Oper` = FIX):

- 1 - Fix the specified coefficient.
- 0 - Allow the specified coefficient to vary (disable fixing).

**option6**: If `Oper` = SOLVE, specify the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.

**option7**: If `Oper` = SOLVE, specify the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.

**option10**: If `Oper` = SOLVE, enables parameter scaling when set to 1. Default = 0. Used for creep material curve-fitting.

## Notes

*\*TBFT Specifications for Hyperelastic Models*\*

**TBFT**, `Oper`, `MATID`, `Option1`, `Option2`, `Option3`, `Option4`, `Option5`, `Option6`, `Option7`

- `Oper` - The operation to perform:
  - `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
  - `FADD` - Define a constitutive model for parameter fitting and import all parameters (defined previously via [[tb|TB]] and [[tbdata|TBDATA]] ).
  - `FDEL` - Delete a constitutive model.
  - `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
  - `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
  - `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature dependent coefficients.
  - `SOLVE` - Solve for coefficients.
  - `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
  - `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
  - `EADD` - Add experimental data.
  - `EDEL` - Delete experimental data.
  - `Other Operations` - - - - - - - - - - - - - - - - - - - - -
  - `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` )
- `MATID` - Material reference identification number (same as `MAT` argument used in the [[tb|TB]] command). Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

\* `Option1` - For curve-fit function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE or FIX) this value specifies the category (AML).

> For adding or deleting your experiment ( `Oper` = EADD or EDEL), this value specifies the experimental data type. **Valid options:** UNIA (default), BIAX, SHEA, SSHE,and VOLU.

- `Option2` - For curve-fit function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE, or FIX), set this value to GENR.

  When you need to specify a file name from which to get experimental data ( `Oper` = EADD), place that string here. Valid value is any file name string. You can enter the entire `path\filename.extension` string and leave the next two values ( `Option3` and `Option4` ) blank, or you can specify the name here, the extension in the next value, and the path following.

- `Option3` - For `Oper` = FADD, FDEL, FSET, CDEL, SET, SOLVE or FIX, set this value to a user- defined name (to be used consistently in the curve-fitting process).

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the file extension.

- `Option4` - When you are working on a specific coefficient ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

  For `Oper` = SET, see , below.

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the directory/path specification.

  If `Oper` = SOLVE, this value specifies the curve-fitting procedure. Valid values are 0 for non- normalized least squares curve-fitting procedure, and 1 for normalized least squares curve-fitting procedure.

\* `Option5` - When you are working on a specific coefficient ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to N, where N is the total number of coefficients. Default = 1.

> For `Oper` = SET, see , below.
>
> #### Set Operations
>
> | Purpose | Option4 | Option5 |
> |----|----|----|
> | Set the value of the coefficient. | Index of coefficient | Value of that coefficient |
> | Set temperature dependency ON/OFF Specify temperature data in the same specified via [[tref|TREF]]. | TDEP | 1 - ON 0 - OFF |
> | Set reference temperature | TREF | Temperature value |
>
> If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

- `Option6` - If `Oper` = SOLVE, specifies the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.
- `Option7` - If `Oper` = SOLVE, specifies the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.

For the supported list of material models, see.

This table summarizes the format for hyperelastic curve-fitting operations via **TBFT** :

### Hyperelastic Model Command Summary

(table not available in the PyMAPDL source, see the Ansys help page)

*\*TBFT Specifications for Viscoelastic Models*\*

**TBFT**, `Oper`, `MATID`, `Option1`, `Option2`, `Option3`, `Option4`, `Option5`, `Option6`, `Option7`

- `Oper` - The operation to perform:
  - `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
  - `FADD` - Define a constitutive model.
  - `FDEL` - Delete a constitutive model.
  - `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
  - `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
  - `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature dependent coefficients.
  - `SOLVE` - Solve for coefficients.
  - `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
  - `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
  - `EADD` - Add experimental data.
  - `EDEL` - Delete experimental data.
  - `Other Operations` - - - - - - - - - - - - - - - - - - - - -
  - `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` )
- `MATID` - Material reference identification number (same as `MAT` argument used in the [[tb|TB]] command). Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

\* `Option1` - For curve-fitting function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE, or FIX), this value is set to AML.

> For adding or deleting your experiment ( `Oper` = EADD or EDEL), this value specifies the experiment type. **Valid options:** SDEC (Shear Modulus vs. Time/Freq) or BDEC (Bulk Modulus vs. Time/Freq).

- `Option2` - For curve-fitting function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE, or FIX), this value is set to GENR.

  When you need to specify a file name from which to get experimental data ( `Oper` = EADD), place that string here. Valid value is any file name string. You can enter the entire `path\filename.extension` string and leave the next two values ( `Option3` and `Option4` ) blank, or you can specify the name here, the extension in the next value, and the path following.

- `Option3` - For `Oper` = FADD, FDEL, FSET, CDEL, SET, SOLVE, or FIX, set this value to any user-defined name (to be used consistently during the curve-fitting process).

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the file extension.

- `Option4` - When you are working on a specific coefficient ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

  For `Oper` = SET, see below.

  You can also specify `TREF` to indicate the reference temperature.

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the directory/path specification.

  If `Oper` = SOLVE, this value specifies the curve-fitting procedure. Valid values are 0 for non- normalized least squares curve-fitting procedure, and 1 for normalized least squares curve-fitting procedure.

- `Option5` - For `Oper` = SET, see below.

  #### Set Operations

  | Purpose | Option4 | Option5 |
  |----|----|----|
  | Set the value of the coefficient | Index of coefficient | Value of coefficient |
  | Set temperature dependency ON/OFF | TDEP | 1 for ON and 0 for OFF |
  | Set reference temperature | TREF | Temperature value |

  If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

  If you are specifying a coefficient to be held constant ( `Oper` = FIX):

  - 1 - Fix the specified coefficient.
  - 0 - Allow the specified coefficient to vary (disable fixing).

- `Option6` - If `Oper` = SOLVE, specifies the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.

- `Option7` - If `Oper` = SOLVE, specifies the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.

This table summarizes the format for viscoelastic curve-fitting operations via **TBFT** :

### Viscoelastic Model Command Summary

(table not available in the PyMAPDL source, see the Ansys help page)

*\*TBFT Specifications for Chaboche Kinematic Hardening Plasticity Models*\*

**TBFT**, `Oper`, `MATID`, `Option1`, `Option2`, `Option3`, `Option4`, `Option5`, `Option6`, `Option7`, -, -, `Option10`

- `Oper` - The operation to perform:

  - `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
  - `FCASE` - Define a case/constitutive model for plasticity.
  - `FADD` - Define a constitutive model.
  - `FDEL` - Delete a constitutive model.
  - `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
  - `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
  - `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature- dependent coefficients.
  - `SOLVE` - Solve for coefficients.
  - `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
  - `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
  - `EADD` - Add experimental data.
  - `EDEL` - Delete experimental data.
  - `Other Operations` - - - - - - - - - - - - - - - - - - - - -
  - `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` ).

- `MATID` - Material reference identification number (same as `MAT` argument used in the [[tb|TB]] command). Valid value is any number greater than zero (default = 1) but less than 100,000.

- `Option1` - For `Oper` = FCASE, set to either NEW or FINI. The command **TBFT**,FCASE, `MATID`,NEW initializes a new curve-fitting case. (The **TBFT**,FADD commands described next are always issued between **TBFT**,FCASE, `MATID`,NEW and **TBFT**,FCASE, `MATID`,FINI commands.) After issuing **TBFT**,FCASE, `MATID`,FINI, the Chaboche model is created and is ready to be used to perform other curve-fitting operations. For more information, see [Material Curve-Fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html)

  For `Oper` = FADD, set to PLAS to add options/parameters for the new case being created (via **TBFT**,FCASE, `MATID`,NEW, which must be issued before the **TBFT**,FADD command). This operation specifies the order of the Chaboche kinematic model.

  For other curve-fitting function operations ( `Oper` = FDEL, FSET, SET, CDEL, SOLVE or FIX), set to CASE.

  For adding or deleting your experiment ( `Oper` = EADD or EDEL), this option specifies the experiment type. The only valid option is UNIA (plastic strain vs. true stress).

- `Option2` - For `Oper` = FCASE (defining your Chaboche case), set to CPLA.

  For `Oper` = FDEL, FSET, SET, CDEL, SOLVE, or FIX (curve-fitting function operations), this value specifies the case name being operated on.

  For `Oper` = FADD (specifying options for the plasticity model), valid options are:

  - CHAB - Chaboche kinematic hardening (required for any defined curve-fitting case)
  - BISO - Bilinear isotropic hardening (optional)
  - MISO - Multilinear isotropic hardening (optional)
  - VOCE - Nonlinear isotropic hardening, Voce model (optional)
  - The **TBFT**,FADD command can be issued twice, once to specify the order of the Chaboche model, and again to specify the isotropic hardening option. (Only one of the options BISO, MISO or VOCE can be used in a single curve-fitting case, and none of those options are required.)

  For `Oper` = EADD (specifying a file name from which to get experimental data), place that string here. A valid entry is any file name string. You can either:

  - Enter the entire `path\filename.extension` string and leave the next two values ( `Option3` and `Option4` ) blank, or
  - Specify the name here, the extension in the next value, and the path in the following value.

- `Option3` - For `Oper` = FCASE, this value specifies the case name.

  For `Oper` = FADD, this value specifies either:

  - The order of the Chaboche kinematic hardening model ( `Option2` = CHAB), or
  - The number of terms in the MISO model ( `Option2` = MISO).

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value contains the file extension.

- `Option4` - When fixing a specific coefficient to a desired value ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

  For `Oper` = SET, see .

  You can also specify `TREF` to indicate the reference temperature, or `COMP` for a partial/complete solution (only for bulk, only for shear, or all coefficients).

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value contains the directory/path specification.

  If `Oper` = SOLVE, this value specifies the normalized/non-normalized option. This option is not available for Chaboche curve-fitting.

- `Option5` - For `Oper` = SET, refer to the following table.

  #### Set Operations

  | Purpose | Option4 | Option5 |
  |----|----|----|
  | Set the value of the coefficient | Index of coefficient | Value of coefficient |
  | Set temperature dependency ON/OFF | TDEP | 1 for ON and 0 for OFF |
  | Set reference temperature | TREF | Temperature value |

  If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

  If you are specifying a coefficient to be held constant ( `Oper` = FIX):

  - 1 - Fix the specified coefficient.
  - 0 - Allow the specified coefficient to vary (disable fixing).

- `Option6` - If `Oper` = SOLVE, specifies the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.

- `Option7` - If `Oper` = SOLVE, specifies the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.

- `-` - Reserved for future use.

- `-` - Reserved for future use.

- `Option10` - If `Oper` = SOLVE, enables parameter scaling when set to 1. Default = 0. Used for Chaboche material curve-fitting.

This table summarizes the format for Chaboche curve-fitting operations via **TBFT** :

### Chaboche Model Command Summary

(table not available in the PyMAPDL source, see the Ansys help page)

*\*TBFT Specifications for Creep Models*\*

**TBFT**, `Oper`, `MATID`, `Option1`, `Option2`, `Option3`, `Option4`, `Option5`, `Option6`, `Option7`, -, -, `Option10`

- `Oper` - The operation to perform:

  - `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
  - `FADD` - Define a constitutive model.
  - `FDEL` - Delete a constitutive model.
  - `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
  - `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
  - `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature dependent coefficients.
  - `SOLVE` - Solve for coefficients.
  - `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
  - `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
  - `EADD` - Add experimental data.
  - `EDEL` - Delete experimental data.
  - `Other Operations` - - - - - - - - - - - - - - - - - - - - -
  - `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` )

- `MATID` - Material reference identification number (same as `MAT` argument used in the [[tb|TB]] command). Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

- `Option1` - For curve-fit function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE or FIX) this value specifies the category (CREEP).

  For adding or deleting your experiment ( `Oper` = EADD or EDEL), this value specifies the experimental data type (CREEP).

- `Option2` - For curve-fit function operations ( `Oper` = FADD, FDEL, FSET, SET, CDEL, SOLVE, or FIX), this value specifies constitutive model type. The valid values are listed in *Creep Options* below.

  When you need to specify a file name from which to get experimental data ( `Oper` = EADD), place that string here. Valid value is any file name string. You can enter the entire `path\filename.extension` string and leave the next two values ( `Option3` and `Option4` ) blank, or you can specify the name here, the extension in the next value, and the path following.

- `Option3` - If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the file extension.

- `Option4` - When you are working on a specific coefficient ( `Oper` = FIX), this value, specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

  For `Oper` = SET, see , below.

  If a file name for experimental data is being specified in `Option2` ( `Oper` = EADD), this value will contain the directory/path specification.

  If `Oper` = SOLVE, this value specifies the curve-fitting procedure. Valid values are 0 for non- normalized least squares curve-fitting procedure, and 1 for normalized least squares curve-fitting procedure.

\* `Option5` - If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

> If you are specifying a coefficient to be held constant ( `Oper` = FIX):
>
> - 1 - Fix the specified coefficient.
> - 0 - Allow the specified coefficient to vary (disable fixing).
>
> For `Oper` = SET, see , below.
>
> #### Set Operations
>
> | Purpose | Option4 | Option5 |
> |----|----|----|
> | Set the value of the coefficient | Index of coefficient | Value of coefficient |
> | Set temperature dependency ON When TDEP is OFF, the Arrhenius term (C4) in the strain-hardening creep equation is calculated. Because [[tbtemp|TBTEMP]] is not included in the curve-fitting, the experimental data (in absolute temperature) must be provided via `/TEMP`. /OFF When TDEP is ON, the Arrhenius term is set to 0 and the constants are calculated separately for each temperature. The curve-fitting process uses [[tbtemp|TBTEMP]]. You must provide the experimental data using the same units as specified via [[tref|TREF]]. | TDEP | 1 - ON 0 - OFF |
> | Set reference temperature | TREF | Temperature value |

- `Option6` - If `Oper` = SOLVE, specifies the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.
- `Option7` - If `Oper` = SOLVE, specifies the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.
- `-` - Reserved for future use.
- `-` - Reserved for future use.
- `Option10` - If `Oper` = SOLVE, enables parameter scaling when set to 1. Default = 0. Used for creep material curve-fitting.

#### Creep Options

| Category | Name | Option |
|----------|------|--------|
| CREEP    | SHAR | NA     |
| CREEP    | THAR | NA     |
| CREEP    | GEXP | NA     |
| CREEP    | GGRA | NA     |
| CREEP    | GBLA | NA     |
| CREEP    | MTHA | NA     |
| CREEP    | MSHA | NA     |
| CREEP    | GGAR | NA     |
| CREEP    | EXPO | NA     |
| CREEP    | NORT | NA     |
| CREEP    | PSTH | NA     |
| CREEP    | PSRP | NA     |
| CREEP    | GTHA | NA     |

This table summarizes the format for creep curve-fitting operations via **TBFT** :

### Creep Model Command Summary

(table not available in the PyMAPDL source, see the Ansys help page)

*\*TBFT Specifications for Thermomechanical Fatigue (TMF)and Plasticity Model Combinations*\*

**TBFT**, `Oper`, `MATID`, `Option1`, `Option2`, `Option3`, `Option4`, `Option5`, `Option6`, `Option7`

- `Oper` - The operation to perform:

  - `Operation Set 1 (Curve-Fitting)` - - - - - - - - - - - - - - - - - - - - -
  - `FADD` - Define a constitutive model.
  - `FDEL` - Delete a constitutive model.
  - `FSET` - Write data related to a constitutive model to the database (same as [[tb|TB]] command).
  - `SET` - Initialize coefficients of a constitutive model for nonlinear curve-fitting procedure.
  - `CDEL` - Deletes coefficients at current reference temperature. Applicable only for temperature- dependent coefficients.
  - `AINI` - Automatically initialize coefficients based on elastic properties and experimental data.
  - `SOLVE` - Solve for coefficients.
  - `PSOLVE` - Custom multistep solve for coefficients.
  - `FIX` - Fix (hold constant) the coefficient you specify in `Option4`.
  - `Operation Set 2 (Experimental Data)` - - - - - - - - - - - - - - - - - - - - -
  - `EADD` - Add experimental data.
  - `EDEL` - Delete experimental data.
  - `Other Operations` - - - - - - - - - - - - - - - - - - - - -
  - `LIST` - List all data associated with the material model represented by the material ID number ( `MATID` ).

- `MATID` - Material reference identification number. (Same as [[tb|TB]], `MATID`.) Valid value is any number `n`, where 0 \< `n` \< 100,000. Default = 1.

- `Option1` - AML - For curve-fitting function operations ( `Oper` = Operation Set 1), this value specifies the category.

  UNIA - For adding or deleting your experiment (Operation Set 2), this value specifies the experimental data type.

- `Option2` - For curve-fitting function operations ( `Oper` = Operation Set 1), this value specifies the constitutive model type. The only valid value is GENR (generic).

  To obtain experimental data ( `Oper` = EADD in Operation Set 2) from a file, specify any valid file name. (You can either specify the entire `path` `filename` . `extension` string here and leave `Option3` and `Option4` blank, or specify `filename` here, `extension` in `Option3`, and `path` in `Option4`.)

- `Option3` - For curve-fitting function operations ( `Oper` = Operation Set 1), specify a unique name for your curve-fitting model.

  For obtaining experimental data ( Oper = EADD in Operation Set 2) from a file specified in Option2, specify the file extension.

- `Option4` - When fixing a specific coefficient to a desired value ( `Oper` = FIX), this value specifies the index of that coefficient. Valid values vary from 1 to `n`, where `n` is the total number of coefficients. Default = 1.

  For `Oper` = SET, see *Set Operations*.

  You can also specify `TREF` to indicate the reference temperature, or `COMP` for a partial/complete solution (only for bulk, only for shear, or all coefficients).

  If `Oper` = SOLVE, this value specifies the curve-fitting procedure. Valid values are 0 for non- normalized least squares curve-fitting procedure, and 1 for normalized least squares curve-fitting procedure.

  For obtaining experimental data ( Oper = EADD) from a file specified in Option2, specify the path in which the file resides.

- `Option5` - For `Oper` = SET, refer to the following table:

  #### Set Operations

  | Purpose | Option4 | Option5 |
  |----|----|----|
  | Set the value of the coefficient | Index of coefficient | Value of coefficient |
  | Set temperature dependency ON/OFF | TDEP | 1 - ON 0 - OFF |
  | Set reference temperature | TREF | Temperature value |

  If `Oper` = SOLVE, use this value to specify the number of iterations to be used in the calculation of the coefficients. Valid value is any positive integer. Default = 1000.

  If you are specifying a coefficient to be held constant ( `Oper` = FIX):

  - 1 - Fix the specified coefficient.
  - 0 - Allow the specified coefficient to vary (disable fixing).

- `Option6` - If `Oper` = SOLVE, specify the allowed tolerance in residual change to stop an iteration. Valid value is 0.0 to 1.0. Default = 0.0.

- `Option7` - If `Oper` = SOLVE, specify the allowed tolerance in coefficient change to stop an iteration. Valid value is 0 to 1. Default = 0.

### Supported Material Models

(table not available in the PyMAPDL source, see the Ansys help page)

The **TBFT** command provides tools for comparing experimental material data to the program- provided calculated data for various nonlinear material options. Based on curve-fitting comparisons and error norms, choose the model to use during the solution phase of the analysis according to the best fit. All of the capabilities of the **TBFT** command are accessible interactively via the standard material GUI. For more information, see [Material Curve-Fitting](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html)

Display material model data associated with both the [[tb|TB]] command and the **TBFT**,FSET command via [[tblist|TBLIST]],ALL,ALL.

Material model data associated with the most recent [[tb|TB]] or **TBFT**,FSET command overwrites previous data.

Display material model data associated with both the [[tb|TB]] command and the **TBFT**,FSET command via [[tblist|TBLIST]],ALL,ALL.

The capability to fix coefficients ( `Option4` = FIX) applies only to nonlinear curve fitting (as listed in.

The uniaxial, biaxial, and shear experimental data use engineering stress. The volumetric data uses true stress. See the [Material Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/nonguimatprops.html) for details about experimental data for creep and viscoelasticity.

The hyperelastic option AML,GENR is a generalized framework where the parameters (defined prior to issuing **TBFT** ) are imported directly from [[tb|TB]] and [[tbdata|TBDATA]]. Parameter-fitting uses this framework for the [thermomechanical fatigue](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_TMFMCF.html#advtmvcfexamples), [geomechanical](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/Hlp_AM_GMCF.html#gmcfexamps), and [TNM](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/aQw8sq22dldm.html#mathypertnmrefs) material models.

**TBFT** does not support saving to ( [[save|SAVE]] ) and resuming from ( [[resume|RESUME]] ) the database file. You must therefore rerun the curve-fitting analysis and then replot ( [[tbfplot|TBFPLOT]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBFT.html

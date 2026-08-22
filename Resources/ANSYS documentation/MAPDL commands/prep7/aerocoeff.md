---
apdl: "AEROCOEFF"
method: aerocoeff
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.aerocoeff
generated: 2026-08-22
tags: [mapdl-command]
---

# AEROCOEFF

PyMAPDL: `mapdl.aerocoeff(aeromodetype='', aeromappedfilenames='', aerospecs='', aeroscalar='', nblades='', autofileread='', **kwargs)`

Computes the aero-damping and stiffness coefficients and writes them to an APDL array.

**Command default:**

No defaults are available for the **AEROCOEFF** command.

## Parameters

**aeromodetype**

Mode type to be used.

- `BLADE` - Non-cyclic cantilevered blade mode (default)

**aeromappedfilenames**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AEROCOEFF.html) for further information.

**aerospecs**: Name of numerical array containing data organized to correspond to the `AeroMappedFiles` array. See the [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_AEROCOEFF.html#eqa9a6f813-34bd-4f85-8d90-03fa1e97fbae) section for specific information that must be in the array.

**aeroscalar**: Scaling value(s) to handle any modal scaling difference between structural and CFD modes. The values can be entered as a scalar or 1-dimensional array. (each scaling value defaults to 1)

**nblades**: Number of blades.

**autofileread**

Key to automatically read and use values from CFD file header.

- `0 (OFF or NO)` - Do not read scaling values or nodal diameter from the CFD file header. (default)
- `1 (ON or YES)` - Read scaling values (labeled `Mode Multiplier` in CFD file) from CFD file header. The scaling values read will be used in calculations and the `AeroScalar` input will be ignored. The nodal diameter values will be used to cross check the value of i (input through `AeroSpecs` array).

## Notes

The **AEROCOEFF** command is designed to [generate an array of aerodynamic coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_aero_coupling.html#) that can be used in a cyclic mode-superposition harmonic response analysis using the [[cycfreq|CYCFREQ]] ,AERO command to represent aerodynamic stiffness and damping. These aerodynamic coefficients can also be used in a damped modal analysis phase ( [[cycfreq|CYCFREQ]],MODAL) of a cyclic mode- superposition harmonic solve. An APDL array called `Jobname` AeroArray is generated using the **AEROCOEFF** command. This array is compatible with the array needed for the [[cycfreq|CYCFREQ]],AERO command.

The format of the written array follows that of the [[cycfreq|CYCFREQ]],AERO command. The array is formatted as follows:

(equation not available in the PyMAPDL source, see the Ansys help page)

where

- (equation omitted) = the i <sup>th</sup> interblade phase angle (IBPA)
- (equation omitted) = the m <sup>th</sup> vibrating blade mode
- (equation omitted) = the n <sup>th</sup> blade mode generating the pressure oscillations
- (equation omitted) and (equation omitted) = the real and imaginary coefficients.

Prior to issuing the **AEROCOEFF** command, a non-cyclic cantilevered blade modal analysis must be run, either stress-free or prestressed using linear perturbation. For more information, see [Modal Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html) **AEROCOEFF** command are the same as those needed for modal restart as described in [Modal Analysis Restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#modalrestex)

The `AeroSpecs` values are specified in a 3×r array ( [[dim|*DIM]] ), wherer is a positive integer equal to the number of interblade phase angles and the pressure modes solved for in the CFD analysis. Each row has the structure:

(equation not available in the PyMAPDL source, see the Ansys help page)

where

- (equation omitted) = the i <sup>th</sup> interblade phase angle (IBPA)
- (equation omitted) = the m <sup>th</sup> vibrating blade mode

\* (equation omitted) = the n <sup>th</sup> blade mode generating the pressure oscillations At least one aerodynamic damping coefficient must be specified for each IBPA (equal to the number of blades) while keeping (equation omitted) and (equation omitted) constant. If a value is not specified, the program writes an array value of zero for both (equation omitted) and (equation omitted). The values of (equation omitted) and (equation omitted) are relative to the modes computed in the required modal analysis.

The number of `AeroScalar` values must be equal to the number of pressure modes ( (equation omitted) from `AeroSpecs` ). If the number of `AeroScalar` values is greater than 1, the values must be entered by defining an (equation omitted) array ( [[dim|*DIM]] ) and entering the array name in the `AeroScalar` field. For a discussion of how `AeroScalar` values are computed, see [Scaling Aerodynamic Coupling Coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_aero_coupling.html#)

The value for `nBlades` should be equal to the number of sectors of the system. If there are multiple blades per cyclic sector, then the combination of blades on the single sector will have an aero coefficient value. In this case, each blade will not have a distinct aero coefficient.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AEROCOEFF.html

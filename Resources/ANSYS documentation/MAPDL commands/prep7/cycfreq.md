---
apdl: "CYCFREQ"
method: cycfreq
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.cycfreq
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCFREQ

PyMAPDL: `mapdl.cycfreq(option='', value1='', value2='', value3='', value4='', value5='', **kwargs)`

Specifies solution options for a cyclic symmetry mode-superposition harmonic analysis.

**Command default:**

No defaults are available for the **CYCFREQ** command. You must specify an `Option` label when issuing this command. Other values which may be necessary depend upon which `Option` label you specify.

## Parameters

**option**

One of the following options:

- `AERO` - Specify the array containing the aerodynamic damping coefficients.
  - `Value1` - The name of the array containing the aerodynamic stiffness damping coefficients.
- `BLADE` - Blade information required for a mistuning or aerodamping analysis.
  - `Value1` - The name of the nodal component containing the blade boundary nodes at the blade-to- disk interface. Also include boundary nodes at any shroud interfaces.
  - `Value2` - The name of the element component containing the blade elements.
  - `Value3` - The number of blade modes to include in the CMS reduction.
  - `Value4` - The lower bound of the frequency range of interest. This value is optional.
  - `Value5` - The upper bound of the frequency range of interest. This value is optional.
- `DEFAULT` - Set the default cyclic harmonic solution settings.
- `EO` - Excitation engine order.
  - `Value1` - An integer value indicating the the excitation order. The loadings on the other sectors will be related to the loading on the base sector based on the engine order phase shift.
  - `Value2` - The name of the Mechanical APDL array containing the modal forces corresponding to the modes kept in the mode-superpostion analysis.
- `MIST` - Mistuning parameters.
  - `Value1` - The type of mistuning:
    - `K` - Stiffness (frequency) mistuning
  - `Value2` - The name of the array containing the stiffness mistuning parameters.
- `MODAL` - Specifies if a damped modal analysis should be performed on the reduced system.
  - `Value1` - On/Off key.
    - `0 (OFF or NO)` - No modal solution. Perform the harmonic solution.
    - `1 (ON or YES)` - Perform a damped modal analysis of the reduced system in order to obtain the complex frequencies. The harmonic solution is not performed.
  - `Value2` - Number of modes for the damped modal analysis.
  - `Value3` - The beginning, or lower end, of the frequency range of interest (in Hz).
  - `Value4` - The ending, or upper end, of the frequency range of interest (in Hz).
- `RESTART` - Defines the point at which to restart the harmonic analysis.
  - `Value1` - The restart point:
    - `OFF` - No restart (default)
    - `SWEEP` - Restart for a new frequency sweep range ( [[harfrq|HARFRQ]] )
    - `MIST` - Restart for new mistuning parameters (new mistuning arrays)
- `USER` - Causes the program to call for a user-defined solution.
  - `Value1-5` - Values passed down to the user-defined solution.
- `STATUS` - List the harmonic solution option settings active for the cyclic model.

**value1**, **value2**, **value3**, **value4**, **value5**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCFREQ.html) for further information.

## Notes

The program solves a cyclically symmetric model (set up via the [[cyclic|CYCLIC]] command during preprocessing) at the harmonic indices specified via the [[cycopt|CYCOPT]] command.

When `Option` = AERO, the aerodynamic coefficients are specified in a 5×(N×r) array ( [[dim|*DIM]] ), where N is the number of blades and r can be any positive integer. Each column has the structure:

(equation not available in the PyMAPDL source, see the Ansys help page)

where:

- (equation omitted) = the i <sup>th</sup> interblade phase angle (IBPA)
- (equation omitted) = the m <sup>th</sup> vibrating blade mode
- (equation omitted) = the n <sup>th</sup> blade mode generating the pressure oscillations

\* (equation omitted) and (equation omitted) = the real and imaginary  
coefficients.

One aerodynamic damping coefficient must be specified for each IBPA (equal to the number of blades) while keeping m and n constant.

The following table shows how the IBPA index ( (equation omitted) ) relates to other quantities for a system with 22 blades:

(table not available in the PyMAPDL source, see the Ansys help page)

The **CYCFREQ**,AERO command is only valid if **CYCFREQ**,BLADE is also specified. The blade mode numbers, m and n, are relative to the values kept in the **CYCFREQ**,BLADE command.

For constant (frequency-independent) mistuning, the stiffness parameters are specified in an N×1 array ( [[dim|*DIM]] ) where N is the number of blades.

For stiffness mistuning, each row entry represents the deviation of Young's modulus from nominal, (equation omitted) (or equivalently, the ratio of the frequency deviationsquared). Each frequency can also be independently mistuned, in whichcase the array is NtimesM, where M is the number of blade frequencies( `Value3` of **CYCFREQ**,BLADE). The entries in each row therefore correspond to the ratio of the mistuned frequency to the tuned frequency squared minus one:

(equation not available in the PyMAPDL source, see the Ansys help page)

The USER option activates the solution macro `CYCMSUPUSERSOLVE.MAC`. The normal solution is skipped. You may implement your own mistuning solution using APDL and APDL Math operations, or call your own program for the solution.

The **CYCFREQ** command is valid in the preprocessing and solution stages of an analysis.

The **CYCFREQ**,MODAL,ON command writes modal frequencies to the output file. No other postprocessing is available for this modal solve.

When using **CYCFREQ**,RESTART, only mistuning parameters or frequency range may be changed. All other changes in parameters are ignored. This type of restart can only be performed by exiting the current mistuning solution using [[finish|FINISH]] and re-entering the solution phase using [[slashsolu|/SOLU]] and then calling the desired **CYCFREQ**,RESTART command.

To learn more about analyzing a cyclically symmetric structure, see the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

**Example Usage**

[Analysis and Solution Controls section of the Technology Showcase Example Problem: Forced-response analysis of a mistuned bladed disk with aerodamping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_tec/tecmistuninganalysis.html#tecmistuning_nonlinmsup_mistuned).

For an example demonstrating how to apply modal loads directly in the cyclic harmonic analysis step of a mode-superposition harmonic cyclic symmetry analysis, see.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCFREQ.html

---
apdl: "/CYCEXPAND"
method: cycexpand
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.cycexpand
generated: 2026-08-22
tags: [mapdl-command]
---

# /CYCEXPAND

PyMAPDL: `mapdl.cycexpand(wn='', option='', value1='', value2='', **kwargs)`

Graphically expands displacements, stresses and strains of a cyclically symmetric model.

## Parameters

**wn**: The window number to which the expansion applies. Valid values are 1 through 5. The default value is 1. The window number applies only to the AMOUNT argument.

**option**

One of the following options:

- `ON` - Activates cyclic expansion using the previous settings (if any). If no previous settings exist, this option activates the default settings. This option is default.

- `DEFAULT` - Resets cyclic expansion to the default settings.

- `OFF` - Deactivates cyclic expansion.

- `STATUS` - Lists the current cyclic expansion settings.

- `AMOUNT` - The number of repetitions or the total angle.

  - `Value1` - NREPEAT
  - `Value2` - The number of repetitions. The default is the total number of sectors in 360 degrees.

  or

  - `Value1` - ANGLE
  - `Value2` - The total angle in degrees. The default is 360.

- `WHAT` - A specified portion or subset of the model to expand:

  - `Value1` - The component name of the elements to expand. The default is all selected components.

- `EDGE` - Sector edge display key. Possible `Value1` settings are:

  - `-1` - Suppresses display of edges between sectors even if the cyclic count varies between active windows. This setting is not valid for cyclic mode-superposition (MSUP) harmonic analyses.

    > [!WARNING]
    > Plots with fewer than the maximum number of repetitions may have missing element faces at the sector boundaries.

  - `0 or OFF` - Averages stresses or strains across sector boundaries. This value is the default (although the default reverts to 1 or ON if the cyclic count varies between active windows).

  - `1 or ON` - No averaging of stresses or strains occurs, and sector boundaries are shown on the plot. This setting is not valid for cyclic MSUP harmonic analyses.

- `PHASEANG` - Possible `Value1` settings are:

  - `n` - The phase angle shift in degrees. The valid range for `n` is 0 through 360. The default is 0. For a modal solution, this value is typically the phase angle obtained via the [[cycphase|CYCPHASE]] command. The expanded modal results are printed or displayed for the specified phase angle shift.
  - `AMPLITUDE (or, n ≥ 360)` - The amplitude is reported, except for the following circumstances where the amplitude solution is not valid:
    - non-component results (such as equivalent stress)
    - modal analyses (no amplitude is calculated, and the expanded modal results are printed or displayed at a phase angle of 360º).
  - `SWEEP` - For a mode-superposition harmonic solution, the maximum values across a phase angle sweep are reported.

**value1**, **value2**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCEXPAND_sl.html) for further information.

## Notes

In preprocessing, the **/CYCEXPAND** command verifies a cyclically symmetric model by graphically expanding it partially or through the full 360 degrees.

For the postprocessing plot nodal solution ( [[plnsol|PLNSOL]] ) operation, the command graphically expands displacements, stresses and strains of a cyclically symmetric model partially or though the full 360 degrees by combining the real (original nodes and elements) and imaginary (duplicate nodes and elements) parts of the solution.

For the print nodal solution ( [[prnsol|PRNSOL]] ) operation, the command expands the printed output of displacements or stresses on a sector-by-sector basis. To learn more about specific [[prnsol|PRNSOL]] behaviors in cyclic analyses, see [Using the /CYCEXPAND Command](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#)

Use of the **/CYCEXPAND** command does not change the database. The command does not modify the geometry, nodal displacements or element stresses.

The command affects element and result plots only. It has no effect on operations other than plot element solution ( [[plesol|PLESOL]] ), plot nodal solution ( [[plnsol|PLNSOL]] ), print nodal solution ( [[prnsol|PRNSOL]] ), and calculate harmonic solution ( [[cyccalc|CYCCALC]] ). Operations other than [[plesol|PLESOL]], [[plnsol|PLNSOL]], [[prnsol|PRNSOL]], or [[cyccalc|CYCCALC]] work on the unprocessed real and imaginary parts of a cyclic symmetry solution

If you issue a **/CYCEXPAND**, OFF command, you cannot then expand the model by simply issuing another **/CYCEXPAND** command (for example, to specify an NREPEAT value for the number of repetitions). In such a case, you must specify **/CYCEXPAND**, ON, which activates expansion using the previous settings (if any) or the default settings.

The command requires PowerGraphics and will turn PowerGraphics on ( [[graphics|/GRAPHICS]], POWER ) if not already active. Any setting which bypasses PowerGraphics (for example, [[pbf|/PBF]] ) also bypasses cyclic expansion; in such cases, the **/CYCEXPAND** command displays unprocessed real and imaginary results.

The [[cycphase|CYCPHASE]] command uses full model graphics ( [[graphics|/GRAPHICS]], FULL ) to compute peak values. Because of this, there may be slight differences between max/min values obtained with [[cycphase|CYCPHASE]], and those obtained via **/CYCEXPAND**, which uses power graphics ( [[graphics|/GRAPHICS]], POWER ).

For PHASEANG = AMPLITUDE (or 360) with a cyclic full harmonic solution, the only appropriate coordinate system is the solution coordinate system ( [[rsys|RSYS]],SOLU).

Load case operations ( [[lcoper|LCOPER]] ) are not valid during a cyclic expansion using **/CYCEXPAND**.

To learn more about analyzing a cyclically symmetric structure, see the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCEXPAND_sl.html

---
apdl: "OCTABLE"
method: octable
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.octable
generated: 2026-08-22
tags: [mapdl-command]
---

# OCTABLE

PyMAPDL: `mapdl.octable(val1='', val2='', val3='', val4='', val5='', val6='', val7='', **kwargs)`

Defines an ocean load using table data.

## Parameters

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**: Values describing the basic ocean load, a current condition, or a wave condition.

## Notes

The **OCTABLE** specifies table data that defines the ocean load. The terms `VAL1`, `VAL2`, etc. are specialized according to the input set required for the given ocean load.

The program interprets the data input via the **OCTABLE** command within the context of the most recently issued [[octype|OCTYPE]] command.

There is no limit to the number of data input.

Input values in the order indicated.

This command is also valid in PREP7.

You can define the following ocean data types:

- Basic ocean data to provide in the value fields:
- `IndVar`, `--`, `CDy`, `CDz`, `CT`, `CMy`, `CMz`
- where

\* `IndVar` = Independent variable for the table inputs. This value is dependent on the `Ktable`  
value specified via the [[ocdata|OCDATA]] command. If `Ktable` = Z, enter this value in descending order on each **OCTABLE** command. If `Ktable` = RE, enter this value field in ascending order.

- \- = Reserved.
- `CDy` = Drag coefficient in the element y direction (normal).
- `CDz` = Drag coefficient in the element z direction (normal). This value defaults to `CDy`.
- `CT` = Drag coefficient in the element x direction (tangential).
- `CMy` = Coefficient of inertia in the element y direction. If no value is specified, and `Cay` is specified, this value defaults to `Cay` + 1.0. If neither this value nor `Cay` is specified, both values default to 0.0.
- `CMz` = Coefficent of inertia in the element z direction. If no value is specified, and `CMy` is specified on the same **OCTABLE** command, this value defaults to `CMy`. If neither this value nor `CMy` is specified, and `Caz` is specified, this value defaults to `Caz` + 1.0. If neither this value nor `Caz` is specified, both values default to 0.0.
- Current data to provide in the value fields:
- `Dep`, `W`, `Th`, `Te`
- where
- `Dep` = Depth of the drift current being input. Input these values in ascending order from one command to the next.
- If the current is constant, only one **OCTABLE** command is necessary and `Dep` is not required.
- For [Ocean Data Type: Wave ( OCTYPE,WAVE)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_OCTABLE.html#octablewavespectinput) waves, the current profile is stretched or compressed linearly up to 10 percent.
- The first `Dep` value (representing the mean sea level) must be zero. The last `Dep` value (representing the mud line) must be equal to the `DEPTH` value input on the [[ocdata|OCDATA]] command.
- The Cartesian Z values used to locate nodes, etc. decrease as one moves from the ocean surface to the sea floor, but the `Dep` values increase. See .
- `Dep` is not affected by changes to `Zmsl` on the [[ocdata|OCDATA]] command, as that value simply relocates the origin.
- `W` = Velocity of the drift current at this location.
- `Th` = Angle of the drift current from the global Cartesian X axis toward the global Cartesian Y axis (in degrees) at this location.
- `Te` = Temperature at this location.

When specifying an ocean wave type, issue the **OCTABLE** command to input either wave location data or [Wave Spectrum Input Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_OCTABLE.html#eq74124840-ae99-4778 - 8938-c48ecc8cdee7) wave spectrum data.

- Wave location data to provide in the value fields (valid only when `KWAVE` = 0 through 3, or 8, on the [[ocdata|OCDATA]] command):
- `H`, `T`, `Ps`, `L`, `NORDER`, `KPRCO`
- where
- `H` = Wave height (peak-to-trough).
- `T` = Wave period.
- `Ps` = Phase shift (in degrees)
- `L` = Wavelength. An optional value used only when `KWAVE` = 0 or 1 (and ignored for all other `KWAVE` types).
- `NORDER` = Order used by stream function wave theory ( `KWAVE` = 3). This value is optional.
- `KPRCO` = Key for printing (1) or not printing (0 and default) the calculated dimensionless coefficients of the stream function wave theory ( `KWAVE` = 3). This value is optional.

**Hints for Wave Location Input:**

- The [[time|TIME]] command is not used, except perhaps to identify the load case.
- The phase shift ( `Ps` ) determines the wave position (that is, the point at which the load is to be applied).
- When using the Stokes fifth-order ( `KWAVE` = 2) or stream function ( `KWAVE` = 3) wave type, issue only one **OCTABLE** command.
- The valid range of the order of the stream function ( `NORDER` ) is 3 through 50. If no value is specified, the program determines a value automatically.
- When using the diffracted wave type ( `KWAVE` = 8), an [[ocread|OCREAD]] command is also required to read in the hydrodynamic data from the [hydrodynamic analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advOLexample.html).
- Wave spectrum data to provide in the value fields (valid only when `KWAVE` = 5 through 7 on the [[ocdata|OCDATA]] command):
- **SPECTRUM= 0** (Pierson-Moskowitz spectrum)
- `HS`, `TP`, `NWC`
- where
- `HS` = Significant wave height of the spectrum.
- `TP` = Peak period for the spectrum.
- `NWC` = Number of wave components (1 (equation omitted) `NWC` (equation omitted) 1000) to model the spectrum. (Default= 50.)
- **SPECTRUM= 1** (JONSWAP spectrum)
- `HS`, `TP`, `GAMMA`, `NWC`
- where
- `HS` = Significant wave height of the spectrum.
- `TP` = Peak period for the spectrum.
- `GAMMA` = Peak enhancement factor for the spectrum. (Default = 3.3.)
- `NWC` = Number of wave components (1 (equation omitted) `NWC` (equation omitted) 1000) to model the spectrum. (Default= 50.)
- **SPECTRUM= 2** (User-defined spectrum)
- `w`, `s`, `NWC`
- `w` = Angular frequency (rad/s).
- `s` = Spectral energy density (Length <sup>2</sup> / (rad/s))
- `NWC` = Number of wave components (1 (equation omitted) `NWC` (equation omitted) 1000) to model the spectrum. (Default= 50.)

**Hints for Wave Spectrum Input:**

- When defining a Pierson-Moskowitz or JONSWAP spectrum ( `SPECTRUM` = 0 or 1, respectively, on the [[ocdata|OCDATA]] command), issue only one **OCTABLE** command.
- When defining a Pierson-Moskowitz or JONSWAP spectrum for Shell new wave ( `KWAVE` = 6 on the [[ocdata|OCDATA]] command), `HS` is calculated from the maximum wave crest amplitude ( `AMPMAX` on the [[ocdata|OCDATA]] command) if no value is specified. For further information, see [Hydrodynamic Loads](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_et8.html#thy_dynpresshead)
- For a user-defined spectrum ( `SPECTRUM` = 2 on the [[ocdata|OCDATA]] command), issue an **OCTABLE** command for each frequency data point defining the spectrum. Specify the frequency data in ascending order. The number of wave components ( `NWC` ) is required on the first **OCTABLE** command only.

An ocean zone is a local space where you can override global ocean-loading parameters.

Ocean zone data to provide in the value fields:

- `Z`, -, `CDy`, `CDz`, `CT`, `CMy`, `CMz`, `Mbio`, `Tbio`

where

- `Z` = Z level for the coefficients specified on this command.
- `--` = Reserved.
- `CDy` = Drag coefficient in the element y direction (normal).
- `CDz` = Drag coefficient in the element z direction (normal). This value defaults to `CDy`.
- `CT` = Drag coefficient in the element x direction (tangential).
- `CMy` = Coefficient of inertia in the element y direction.
- `CMz` = Coefficient of inertia in the element z direction. This value defaults to `CMy`.
- `Mbio` = Material ID of biofouling.
- `Tbio` = Thickness of biofouling.

Ocean zone values specified via the **OCTABLE** command override global ocean-loading parameters.

Arguments not specified default to the global values specified for the basic ocean type ( [[octype|OCTYPE]],BASIC). Therefore, the relationship between `Ca` and `CM` values ( `Ca` = `CM` - 1.0) is not applied to ocean zones.

The **OCTABLE** command is not valid for a pipe-type ocean zone ( [[oczone|OCZONE]],PIP).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCTABLE.html

---
apdl: "AWAVE"
method: awave
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.awave
generated: 2026-08-22
tags: [mapdl-command]
---

# AWAVE

PyMAPDL: `mapdl.awave(wavenum='', wavetype='', opt1='', opt2='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', val10='', val11='', val12='', val13='', **kwargs)`

Specifies input data for an acoustic incident wave.

## Parameters

**wavenum**: Wave number. You specify the integer number for an acoustic incident wave inside or outside the model. The number must be between 1 and 20.

**wavetype**

Wave type:

- `PLAN` - Planar incident wave
- `MONO` - Monopole or pulsating sphere incident wave
- `DIPO` - Dipole incident wave
- `BACK` - Back enclosed loudspeaker
- `BARE` - Bare loudspeaker
- `STATUS` - Displays the status of the acoustic wave settings if `Wavenum` = a number between 1 and 20 or ALL.
- `DELE` - Deletes the acoustic wave settings if `Wavenum` = a number between 1 and 20 or ALL.

**opt1**

- `PRES` - Pressure
- `VELO` - Velocity

**opt2**

- `EXT` - Incident wave outside the model.
- `INT` - Incident wave inside the model. This option is only available for pure scattered pressure formulation.

For `Wavetype` = PLAN, only `Opt2` = EXT is available.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**, **val10**, **val11**, **val12**, **val13**

If `Wavetype` = PLAN, MONO, DIPO, BACK, or BARE:

- `VAL1` - Amplitude of pressure or normal velocity to the sphere surface.
- `VAL2` - Phase angle of the applied pressure or velocity (in degrees). Defaults to 0 degrees.

If `Wavetype` = PLAN:

- `VAL3` - Incident ϕ angle from x axis toward y axis.
- `VAL4` - Incident θ angle from z axis toward y axis.
- `VAL5` - Not used.

If `Wavetype` = MONO, DIPO, BACK, or BARE:

- `VAL3 - VAL5` - Global Cartesian coordinate values of source position.

If  
`Wavetype` = PLAN, MONO, DIPO, BACK, or BARE:

- `VAL6` - Mass density of base medium (defaults to 1.2041 kg/m3).
- `VAL7` - Speed of sound in base medium (defaults to 343.24 m/s).
- `VAL8` - Radius of pulsating sphere (not used for `Wavetype` = PLAN).
- `VAL9` - Dipole length (only available for `Wavetype` = DIPO, BARE).
- `VAL10 - VAL12` - Unit vector of dipole axis from the positive to the negative. Only available for `Wavetype` = DIPO, BARE.
- `VAL13` - Port number if the incident power is required on the port

## Notes

Use the [[asol|ASOL]] command to activate the scattered field algorithm and the [[ascres|ASCRES]] command for output control with the scattered field algorithm. Refer to [Acoustics](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thyacous_poroelastic.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AWAVE.html

---
apdl: "RESP"
method: resp
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.resp
generated: 2026-08-22
tags: [mapdl-command]
---

# RESP

PyMAPDL: `mapdl.resp(ir='', lftab='', ldtab='', spectype='', dampratio='', dtime='', tmin='', tmax='', inputtype='', **kwargs)`

Generates a response spectrum.

## Parameters

**ir**: Arbitrary reference number assigned to the response spectrum results (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with these results.

**lftab**: Reference number of variable containing frequency table (created with [[filldata|FILLDATA]] or [[data|DATA]] command). The frequency table defines the number and frequency of oscillating systems used to determine the response spectrum. The frequency interval need not be constant over the entire range. Frequencies must be input in ascending order.

**ldtab**: Reference number of variable containing the input time-history.

**spectype**

Defines the type of response spectrum to be calculated:

- `0 or 1` - Displacement (relative to base excitation)
- `2` - Velocity (relative to base excitation)
- `3` - Acceleration response spectrum (absolute)
- `4` - Pseudo-velocity
- `5` - Pseudo-acceleration

**dampratio**: Ratio of viscous damping to critical damping (input as a decimal number).

**dtime**

Integration time step. This value should be equal to or greater than the integration time step used in the initial transient analysis performed to generate the input time-history ( `LDTAB` ).

`DTIME` defaults to a value of 1/(20\*FMAX), where FMAX is the highest frequency in the frequency table ( `LFTAB` ) except when the time-history is read from the reduced displacement ( `RDSP` ) file following a mode-superposition transient analysis without an expansion pass. In this case, `DTIME` defaults to the time step value used in the analysis.

**tmin**, **tmax**: Specifies a subset of the input time-history ( `LDTAB` ) to be used in the response spectrum calculation. Defaults to the full time range.

**inputtype**

Defines the type of the input time-history:

- `0` - Displacement (default)
- `1` - Acceleration

## Notes

This command generates a response spectrum from a displacement or acceleration time-history and frequency data. The response spectrum is defined as the maximum response of single degree of freedom systems of varying frequency (or period) to a given input support excitation.

A response spectrum analysis ( [[antype|ANTYPE]], SPECTR with [[spopt|SPOPT]], SPRS or MPRS) requires a response spectrum input. This input can be determined from the response spectrum printout or display of this command.

If a response spectrum is to be calculated from a given displacement (or acceleration) time-history, the displacement time-history may be input to a single one-element reduced linear transient dynamic ( [[antype|ANTYPE]],TRANS) analysis, so that the calculated output (which should be the same as the input) will be properly located on the file.

The integration time step (argument `DTIME` on the **RESP** command) and the damping coefficient (argument `dampRatio` ) are constant over the frequency range. The number of calculations done per response spectrum curve is the product of the number of input solution points ( `TMAX` - `TMIN` )/ `DTIME` and the number of frequency points (frequencies located in variable `LFTAB` ).

Input solution points requested (using `DTIME` and the frequency range) at a time not corresponding to an actual displacement solution time on the file are linearly interpolated with respect to the existing points.

For the theory of the response spectrum calculation, see [POST26 - Response Spectrum Generator (RESP)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post11.html#postimestep)

For an example of the command usage, see [Generating a Response Spectrum](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BASP26add.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESP.html

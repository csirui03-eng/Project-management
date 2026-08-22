---
apdl: "PRAS"
method: pras
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.pras
generated: 2026-08-22
tags: [mapdl-command]
---

# PRAS

PyMAPDL: `mapdl.pras(lab='', ldstep='', substep='', freqb='', freqe='', logopt='', val1='', val2='', val3='', val4='', val5='', val6='', **kwargs)`

Prints a specified acoustic quantity during postprocessing of an acoustic analysis.

## Parameters

**lab**

The acoustic quantity to calculate:

- `SIMP` - Specific acoustic impedance on the selected surface.
- `AIMP` - Acoustic impedance on the selected surface.
- `MIMP` - Mechanical impedance on the selected surface.
- `PRES` - Average pressure on the selected surface.
- `FORC` - Force on the selected surface.
- `POWE` - Acoustic power on the selected surface.
- `ERP` - Equivalent radiated power on the selected structural surface (valid only for `SHELL181`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, `SOLID225`, `SOLID226`, `SOLID227`, and `SHELL281` ).
- `ERPL` - Equivalent radiated power level on the selected structural surface (valid only for `SHELL181`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, `SOLID225`, `SOLID226`, `SOLID227`, and `SHELL281` ).
- `BSPL` - Frequency-band sound pressure level on selected nodes.
- `BSPA` - A-weighted frequency-band sound pressure level on selected nodes.
- `MENE` - Acoustic potential energy on the selected elements.
- `KENE` - Acoustic kinetic energy on the selected elements.
- `TENE` - Acoustic total energy on the selected elements.
- `PL2V` - Average square of the L2 norm of pressure on the selected elements.
- `LWIN` - Input sound power level on defined port.
- `LWOUT` - Output sound power level on defined driven port.
- `RL` - Return loss on defined port.
- `ALPHA` - Absorption coefficient on defined port.
- `TL` - Transmission loss on defined ports.
- `PALL` - All port-related parameters (LWIN, LWOUT, RL, ALPHA, TL).
- `DFSTL` - Transmission loss of random acoustic analysis.
- `DFSPW` - Radiated power in random acoustic analysis.
- `DALL` - All random acoustic related parameters (DFSTL, DFSPW).

**ldstep**

Specified load step. Defaults to the load step number specified on the [[set|SET]] command, or defaults to 1 if [[set|SET]] has not been issued. This default applies to all `Lab` values except DFSTL, DFSPW, and DALL.

- `n` - Load step number.
- `ALL` - All load steps.
- `AVG or 0` - Average result of multiple samplings in a random acoustic analysis (see the [[msolve|MSOLVE]] command). This option is used only for `Lab` = DFSTL, DFSPW, and DALL, and it is the default for these labels.

**substep**

Specified substep. Defaults to the substep number specified on the [[set|SET]] command, or defaults to ALL (all substeps at the specified load step) if [[set|SET]] has not been issued. For `Lab` = BSPL or BSPA, ALL is the only valid value.

- `n` - Substep number.
- `ALL` - All substeps.

**freqb**

Frequency value representing one of the following:

- Beginning frequency of the frequency range ( `FREQB` to `FREQE` ) for the defined load step(s) and substeps ( `SUBSTEP` = ALL). If a `SUBSTEP` value is specified, `FREQB` is invalid.
- Central frequency of octave bands, used when `LogOpt` = OB1, OB2, OB3, OB6, OB12, or OB24 and `FREQE` is blank.

**freqe**: Ending frequency of the frequency range ( `FREQB` to `FREQE` ) for the defined load step(s) and substeps ( `SUBSTEP` = ALL). If blank, `FREQE` is set to `FREQB`. If a `SUBSTEP` value is specified, `FREQE` is invalid.

**logopt**

Octave bands:

- `OB0` - Narrow bands (default).
- `OB1` - Octave bands.
- `OB2` - 1/2 octave bands.
- `OB3` - 1/3 octave bands.
- `OB6` - 1/6 octave bands.
- `OB12` - 1/12 octave bands.
- `OB24` - 1/24 octave bands.

**val1**: Input port number for `Lab` = LWIN, LWOUT, RL, ALPHA, TL, or PALL.

**val2**: Output port number for `Lab` = TL or PALL.

**val3**: Reference power for `Lab` = LWIN, LWOUT, PALL or EPRL (defaults to 1x10 <sup>-12</sup> W).

**val4**: Fluid mass density for `Lab` = ERP or ERPL (defaults to 1.2041 kg/m <sup>3</sup> ).

**val5**: Speed of sound in the fluid for `Lab` = ERP or ERPL (defaults to 343.25 m/s).

**val6**: Radiation efficiency for `Lab` = ERP or ERPL (defaults to 1).

## Notes

The **PRAS** command lists the specified acoustic quantity on the selected exterior surface, the energy on selected elements, or the sound pressure level over frequency bands. The calculation is based on the pressure and velocity solution or the frequency-band sound pressure level (SPL).

The total pressure and velocity are used if the selected surface is the excitation source surface. To calculate the incoming and outgoing acoustic power and other sound power parameters on the input and output surfaces, issue the [[sf|SF]],,PORT command in the preprocessor to define port numbers.

The sound pressure level of the octave bands and general frequency band (defined via the [[harfrq|HARFRQ]] command) is calculated at the selected nodes in the model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRAS.html

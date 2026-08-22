---
apdl: "HARFRQ"
method: harfrq
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.harfrq
generated: 2026-08-22
tags: [mapdl-command]
---

# HARFRQ

PyMAPDL: `mapdl.harfrq(freqb='', freqe='', logopt='', freqarr='', toler='', **kwargs)`

Defines the frequency range in a harmonic analysis.

## Parameters

**freqb**: Frequency (Hz) at the beginning of the `FREQB` to `FREQE` range (if `FREQE` \> `FREQB` ). If `FREQE` is blank, the solution is done only at frequency `FREQB` (the central frequency of octave bands, when `LogOpt` = OB1, OB2, OB3, OB6, OB12 or OB24).

**freqe**: Frequency at end of this range. For non-logarithm spacing ( `LogOpt` is blank), solutions are done at an interval of ( `FREQE` - `FREQB` ) / `NSBSTP`, ending at `FREQE`, and no solution is done at the beginning of the frequency range, `FREQB`. `NSBSTP` is input via the [[nsubst|NSUBST]] command. See the [[expsol|EXPSOL]] command documentation for expansion pass solutions.

**logopt**

Logarithm frequency span. Solutions are done at an interval of (log( `FREQE` ) - log( `FREQB` )) / ( `NSBSTP` -1), ( `NSBSTP` \>1). The central frequency or beginning frequency is used for `NSBSTP` = 1. Valid values are:

- `OB1` - Octave band.
- `OB2` - 1/2 octave band.
- `OB3` - 1/3 octave band.
- `OB6` - 1/6 octave band.
- `OB12` - 1/12 octave band.
- `OB24` - 1/24 octave band.
- `LOG` - General logarithm frequency span.

**freqarr**: An array containing frequency values (Hz). Combined with the tolerance argument, `Toler`, these values are merged with values calculated based on the specifications from `FREQB`, `FREQE`, and `LogOpt`, as well `NSBSTP` on the [[nsubst|NSUBST]] command and `Clust` on the [[hrout|HROUT]] command. Enclose the array name in percent (%) signs (for example, **HARFRQ**,,,,,%arrname%). Use [[dim|*DIM]] to define the array.

**toler**: Tolerance to determine if a user input frequency value in `FREQARR` is a duplicate and can be ignored. Two frequency values are considered duplicates if their difference is less than the frequency range multiplied by the tolerance. The default value is 1 x 10 <sup>-5</sup>.

## Notes

Defines the frequency range for loads in the harmonic analysis ( [[antype|ANTYPE]],HARMIC).

Do not use this command for a [harmonic ocean wave analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc4.html#eq63629e12-76f7-4f52-97a7-ce8593b3f24e) ( [[hrocean|HROCEAN]] ).

When frequencies are user-defined, the array `FREQARR` must be one-dimensional and contain positive values. User-defined frequency input is not supported when the [frequency-sweep](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) method is used ( [[hropt|HROPT]],VT ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HARFRQ.html

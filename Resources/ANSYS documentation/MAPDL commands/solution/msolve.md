---
apdl: "MSOLVE"
method: msolve
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.msolve
generated: 2026-08-22
tags: [mapdl-command]
---

# MSOLVE

PyMAPDL: `mapdl.msolve(numslv='', val1='', val2='', lab='', angfix='', **kwargs)`

Starts multiple solutions for an acoustic analysis.

## Parameters

**numslv**: Number of multiple solutions (load steps). This number corresponds to the number of random samplings for the diffuse sound field in a random acoustic analysis, or the incident angles of the plane wave when the Floquet periodic boundary condition is present. Default = 1.

**val1**

The meaning of `VAL1` depends on the `Lab` value.

For `Lab` = DSF, `VAL1` is the norm convergence tolerance defined by comparing the averaged radiated diffuse sound power of two multiple sampling sets over the frequency range for the diffuse sound field (default = 0.05).

For `Lab` = APHI or ATHETA, `VAL1` is the beginning angle for the incident angle sweep of the plane wave (default = 0).

**val2**

The meaning of `VAL2` depends on the `Lab` value.

For `Lab` = DSF, `VAL2` is the interval of the norm convergence check for the diffuse sound field (default = 5).

For `Lab` = APHI or ATHETA, `VAL2` is the ending angle for the incident angle sweep of the plane wave (default = 0).

**lab**

Label indicating the type of acoustic analysis:

- `DSF` - Diffuse sound field with multiple solutions (default).
- `APHI` - Plane wave angle sweep with fixed (equation omitted) angle and varied (equation omitted) angle (see the [[aport|APORT]] command).
- `ATHETA` - Plane wave angle sweep with fixed (equation omitted) angle and varied (equation omitted) angle (see the [[aport|APORT]] command).

**angfix**: The value of the fixed incident angle for the plane wave angle sweep (used only when `Lab` = APHI or ATHETA).

## Notes

The **MSOLVE** command starts multiple solutions (load steps) for a random acoustic analysis with multiple samplings or for the angle sweep of the incident plane wave with the Floquet periodic boundary condition, as described below.

**Random Acoustic Analysis (** `Lab` = DSF)

Use `Lab` = DSF for a random acoustic analysis. The process is controlled by the norm convergence tolerance ( `VAL1` ) or the number of multiple solutions ( `NUMSLV` ) if the solution steps reach the defined number.

The program checks the norm convergence by comparing two averaged sets of radiated sound powers with the interval `VAL2` over the frequency range. For example, if `VAL2` = 5, the averaged values from 5 solutions are compared with the averaged values from 10 solutions, then the averaged values from 10 solutions are compared with the averaged values from 15 solutions, and so on.

The incident diffuse sound field is defined via the [[dfswave|DFSWAVE]] command.

The average result of multiple solutions with different samplings is calculated via the [[pras|PRAS]] or [[plas|PLAS]] command.

**Plane Wave Incident Angle Sweep (** `Lab` = APHI or ATHETA)

Use `Lab` = APHI or ATHETA to perform an angle sweep for the incident plane wave defined by the [[aport|APORT]] command. The process is controlled by the number of multiple solutions ( `NUMSLV` ). The plane wave port must be defined with the default values of incident angles prior to the **MSOLVE** command.

The sound power parameters are calculated over the sweeping angles during postprocessing by the [[pras|PRAS]] or [[plas|PLAS]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSOLVE.html

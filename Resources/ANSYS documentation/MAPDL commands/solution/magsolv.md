---
apdl: "MAGSOLV"
method: magsolv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.magsolv
generated: 2026-08-22
tags: [mapdl-command]
---

# MAGSOLV

PyMAPDL: `mapdl.magsolv(opt='', nramp='', cnvcsg='', cnvflux='', neqit='', biot='', cnvtol='', **kwargs)`

Specifies magnetic solution options and initiates the solution.

## Parameters

**opt**

Static magnetic solution option:

- `0` - Vector potential (MVP) or edge formulation (default).
- `1` - Combined vector potential and reduced scalar potential (MVP-RSP).
- `2` - Reduced scalar potential (RSP).
- `3` - Difference scalar potential (DSP).
- `4` - General scalar potential (GSP).

**nramp**: Number of ramped substeps for the first load step of a nonlinear MVP or MVP-RSP solution. Defaults to 3. If `NRAMP` = -1, ignore the ramped load step entirely. `NRAMP` is ignored for linear magnetostatics.

**cnvcsg**: Tolerance value on the program-calculated reference value for the magnetic current-segment convergence. Used for the MVP, the MVP-RSP, and the edge formulation solution options ( `OPT` = 0 and 1). Defaults to 0.001.

**cnvflux**: Tolerance value on the program-calculated reference value for the magnetic flux convergence. Used for all scalar potential solution options ( `OPT` = 2, 3, 4). Defaults to 0.001.

**neqit**: Maximum number of equilibrium iterations per load step. Defaults to 25.

**biot**

Option to force execution of a Biot-Savart integral solution ( [[biot|BIOT]],NEW) for the scalar potential options. Required if multiple load steps are being performed with different current source primitives ( `SOURC36` elements).

- `0` - Do not force execution of Biot-Savart calculation (default); Biot-Savart is automatically calculated only for the first solution.
- `1` - Force execution of Biot-Savart calculation.

**cnvtol**: Sets the convergence tolerance for AMPS reaction. Defaults to 1e-3.

## Notes

**MAGSOLV** invokes a Mechanical APDL macro which specifies magnetic solution options and initiates the solution. The macro is applicable to any Mechanical APDL magnetostatic analysis using the magnetic vector potential (MVP), reduced scalar potential (RSP), difference scalar potential (DSP), general scalar potential (GSP), or combined MVP-RSP formulation options. Results are only stored for the final converged solution. (In POST1, issue [[starset|*SET]],LIST to identify the load step of solution results.) The macro internally determines if a nonlinear analysis is required based on magnetic material properties.

If you use the `BIOT` option and issue [[save|SAVE]] after solution or postprocessing, the Biot- Savart calculations are saved to the database, but will be overwritten upon normal exit from the program. To save this data after issuing [[save|SAVE]], use the `/EXIT`,NOSAVE command. You can also issue the `/EXIT`,SOLU command to exit Mechanical APDL and save all solution data, including the Biot-Savart calculations, in the database. Otherwise, when you issue [[resume|RESUME]], the Biot-Savart calculation will be lost (resulting in a zero solution).

The MVP, MVP-RSP, and edge formulation options perform a two-load-step solution sequence. The first load step ramps the applied loads over a prescribed number of substeps ( `NRAMP` ), and the second load step calculates the converged solution. For linear problems, only a single load step solution is performed. The ramped load step can be bypassed by setting `NRAMP` to -1.

The RSP option solves in a single load step using the adaptive descent procedure. The DSP option uses two load steps, and the GSP solution uses three load steps.

The following analysis options and nonlinear options are controlled by this macro: [[kbc|KBC]], [[neqit|NEQIT]], [[nsubst|NSUBST]], [[cnvtol|CNVTOL]], [[nropt|NROPT]], [[magopt|MAGOPT]], and [[outres|OUTRES]].

You cannot use constraint equations with `OPT` = 4.

When the `BIOT` option is on ( `BIOT` = 1), Distributed-Memory Parallel (DMP) restrictions may apply. For more information, see the [[biot|BIOT]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAGSOLV.html

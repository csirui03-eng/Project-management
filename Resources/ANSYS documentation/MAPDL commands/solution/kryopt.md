---
apdl: "KRYOPT"
method: kryopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.kryopt
generated: 2026-08-22
tags: [mapdl-command]
---

# KRYOPT

PyMAPDL: `mapdl.kryopt(maxdim='', restol='', **kwargs)`

Specifies solution options for a Krylov method harmonic analysis.

## Parameters

**maxdim**: Maximum dimension of subspace. The default size is automatically determined by the program (ranges around 50).

**restol**: Tolerance used to verify the L-2 norm values of calculated residuals and issue a warning if `RESTOL` is exceeded throughout the entire frequency range. Default = 0.05.

## Notes

This command is used to specify solution options for a harmonic analysis solved with the Krylov method ( `Method` = KRYLOV on [[hropt|HROPT]], see also [Frequency-Sweep Harmonic Analysis via the Krylov Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros)

Increasing subspace size ( `MAXDIM` ) improves solution accuracy with the trade-off of increased computational cost and additional memory requirements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KRYOPT.html

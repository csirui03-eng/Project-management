---
apdl: "PLMC"
method: plmc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plmc
generated: 2026-08-22
tags: [mapdl-command]
---

# PLMC

PyMAPDL: `mapdl.plmc(lstep='', sbstep='', timfrq='', kimg='', hibeg='', hiend='', **kwargs)`

Plots the modal coordinates from a mode-superposition solution.

## Parameters

**lstep**, **sbstep**: Plot the solution identified as load step `LSTEP` and substep `SBSTEP`

**timfrq**: As an alternative to `LSTEP` and `SBSTEP`, plot the solution at the time value `TIMFRQ` (for [[antype|ANTYPE]],TRANS) or frequency value `TIMFRQ` (for [[antype|ANTYPE]],HARMIC). `LSTEP` and `SBSTEP` should be left blank.

**kimg**

Key for plotting real or imaginary solution. Valid only for [[antype|ANTYPE]],HARMIC.

- `0 (or blank)` - Plot the real solution (default).
- `1` - Plot the imaginary solution.
- `2` - Plot the amplitude.

**hibeg**, **hiend**: For cyclic symmetry solutions, plot the solutions in the harmonic index solution range `HIbeg` to `HIend`. Defaults to all harmonic indices (all modes).

## Notes

**PLMC** plots a histogram of the modal coordinates (the factors which modes may be multiplied by to obtain their contribution to the response) at a certain time point (transient analyses) or frequency point (harmonic analyses). The absolute values of the modal coordinates are plotted. Use [[xrange|/XRANGE]] to plot only modes in a certain range, if desired.

For transient analyses, a `.rdsp` None file must be available. For harmonic analyses, a `.rfrq` None file must be available. The content of these files depends on the [[outres|OUTRES]] command settings. Note that the default for mode-superposition transient analysis is to write the reduced displacement file every 4th substep. For more information, see Command Default in the [[outres|OUTRES]] command description.

For a cyclic harmonic mode-superposition analysis, use the [[cycfiles|CYCFILES]] command to identify the `.rfrq` None and modal `.rst` None file. For other analyses, use the [[file|FILE]] command to specify the `.rdsp` or `.rfrq` file.

You may limit the plot to display only those modes in a certain harmonic index range. The modes having the same harmonic index are each plotted in a unique color. If there are less than 10 harmonic indices, they are identified in the graphics legend.

This is a graphical representation of the optional `Jobname.mcf` text file (see the [[trnopt|TRNOPT]] and [[hropt|HROPT]] commands). To print the modal coordinates, use the [[prmc|PRMC]] command. For more information on modal coordinates, see [Mode-Superposition Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool9.html#thy_antools_resresp) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

**Example Usage**

[Example Mode-Superposition Harmonic Cyclic Symmetry Analysis with Mistuning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_ex_msupharm.html#cycsym_ex_msupharm_steps)

Example: Forced Response with Mistuning and Aero Coupling

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLMC.html

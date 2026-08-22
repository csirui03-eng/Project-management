---
apdl: "CNTR"
method: cntr
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cntr
generated: 2026-08-22
tags: [mapdl-command]
---

# CNTR

PyMAPDL: `mapdl.cntr(option='', key='', **kwargs)`

Redirects contact pair output quantities to a text file.

**Command default:**

Contact pair output quantities are written to the output file ( `Jobname.OUT` ) or to the screen, as specified by the [[output|/OUTPUT]] command.

## Parameters

**option**

Output option:

- `OUT` - Contact output control.

**key**

Control key:

- `NO` - Write contact information to the output file or to the screen (default).
- `YES` - Write contact information to the `Jobname.CNM` file.

## Notes

Issue the command **CNTR**,OUT,YES to redirect contact pair output quantities to the `Jobname.CNM` file.

To ensure that the contact information is written to `Jobname.CNM`, reissue **CNTR**,OUT,YES each time you reenter the solution processor ( [[slashsolu|/SOLU]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CNTR.html

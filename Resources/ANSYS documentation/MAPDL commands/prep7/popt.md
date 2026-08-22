---
apdl: "POPT"
method: popt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.popt
generated: 2026-08-22
tags: [mapdl-command]
---

# POPT

PyMAPDL: `mapdl.popt(lop1='', **kwargs)`

Selects the piping analysis standard for a piping run.

**Command default:**

ANSI B31.1.

## Parameters

**lop1**

Option label:

- `B31.1` - for ANSI B31.1.
- `NC` - for ASME Section III NC, Class 2.

## Notes

Selects the piping analysis standard for a piping run (RUN). Affects only the flexibility and stress intensification factors applied to the curved pipe elements. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_POPT.html

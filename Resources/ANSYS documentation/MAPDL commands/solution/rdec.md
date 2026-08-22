---
apdl: "RDEC"
method: rdec
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.rdec
generated: 2026-08-22
tags: [mapdl-command]
---

# RDEC

PyMAPDL: `mapdl.rdec(option='', reduc='', nplace='', **kwargs)`

Defines the decimation parameters used by the radiosity solver method.

## Parameters

**option**

Command options:

- `DEFINE` - Defines the decimation parameters (default).
- `STAT` - Shows the status/listing. Other command options are ignored.

**reduc**: Approximate reduction in the number of surface elements. Valid range is from 0.0 (no decimation, the default) to 1.0. This number is a factor applied to the initial number of element radiosity surfaces.

**nplace**

Node placement algorithm

- `OPTI` - Optimal placement. An edge is collapsed by moving both nodes (I and J in the figure below) to a new location.

- `SUBS` - Subset placement. An edge is collapsed by moving one node to another one. In the figure below, node I is moved to node J.

  (figure omitted, see the Ansys help page)

## Notes

The **RDEC** command sets decimation parameters. These parameters are used by the next [[rsurf|RSURF]] command to generate radiosity surface elements.

Decimation is the process of simplifying a fine surface mesh into a coarse one. This process is accomplished by a sequence of edge collapses.

The maximum degree of decimation (1.0) is unreachable. The real degree of decimation is always less than 1.0 because the decimated mesh must always consist of at least one element.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RDEC.html

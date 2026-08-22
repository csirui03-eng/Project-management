---
apdl: "FELIST"
method: felist
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.felist
generated: 2026-08-22
tags: [mapdl-command]
---

# FELIST

PyMAPDL: `mapdl.felist(nev1='', nev2='', ninc='', **kwargs)`

Lists the fatigue event parameters.

## Parameters

**nev1**, **nev2**, **ninc**: List event parameters from `NEV1` (defaults to 1) to `NEV2` (defaults to `NEV1` ) in steps of `NINC` (defaults to 1). If `NEV1` = ALL, `NEV2` and `NINC` are ignored and all events are listed.

## Notes

Fatigue event parameters are defined via the FE command.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FELIST.html

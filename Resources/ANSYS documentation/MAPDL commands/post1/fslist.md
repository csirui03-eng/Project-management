---
apdl: "FSLIST"
method: fslist
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fslist
generated: 2026-08-22
tags: [mapdl-command]
---

# FSLIST

PyMAPDL: `mapdl.fslist(nloc1='', nloc2='', ninc='', nev='', nlod='', **kwargs)`

Lists the stresses stored for fatigue evaluation.

## Parameters

**nloc1**, **nloc2**, **ninc**: List stresses from `NLOC1` (defaults to 1) to `NLOC2` (defaults to `NLOC1` ) in steps of `NINC` (defaults to 1). If `NLOC1` = ALL, `NLOC2` and `NINC` are ignored and stresses for all locations are listed.

**nev**: Event number for stress listing (defaults to ALL).

**nlod**: Loading number for stress listing (defaults to ALL).

## Notes

Stresses may be listed per location, per event, per loading, or per stress condition. Use FELIST and FLLIST if only event and location parameters (no stresses) are to be listed.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSLIST.html

---
apdl: "RLIST"
method: rlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.rlist
generated: 2026-08-22
tags: [mapdl-command]
---

# RLIST

PyMAPDL: `mapdl.rlist(nset1='', nset2='', ninc='', **kwargs)`

Lists the real constant sets.

## Parameters

**nset1**, **nset2**, **ninc**: List real constant sets from `NSET1` to `NSET2` (defaults to `NSET1` ) in steps of `NINC` (defaults to 1). If `NSET1` = ALL (default), ignore `NSET2` and `NINC` and list all real constant sets ( [[r|R]] ).

## Notes

The real constant sets listed contain only those values specifically set by the user. Default values for real constants set automatically within the various elements are not listed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RLIST.html

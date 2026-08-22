---
apdl: "PRVAR"
method: prvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.listing.Listing.prvar
generated: 2026-08-22
tags: [mapdl-command]
---

# PRVAR

PyMAPDL: `mapdl.prvar(nvar1='', nvar2='', nvar3='', nvar4='', nvar5='', nvar6='', **kwargs)`

Lists variables vs. time (or frequency).

## Parameters

**nvar1**, **nvar2**, **nvar3**, **nvar4**, **nvar5**, **nvar6**: Variables to be displayed, defined either by the reference number or a unique thirty-two character name. If duplicate names are used the command will print the data for the lowest- numbered variable with that name.

## Notes

Lists variables vs. time (or frequency). Up to six variables may be listed across the line. Time column output format can be changed using the [[format|/FORMAT]] command arguments `Ftype`, `NWIDTH`, and `DSIGNF`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRVAR.html

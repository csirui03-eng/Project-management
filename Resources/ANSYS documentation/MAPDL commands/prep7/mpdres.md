---
apdl: "MPDRES"
method: mpdres
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpdres
generated: 2026-08-22
tags: [mapdl-command]
---

# MPDRES

PyMAPDL: `mapdl.mpdres(labf='', matf='', labt='', matt='', **kwargs)`

Reassembles existing material data with the temperature table.

## Parameters

**labf**: Material property label associated with `MATF`.

**matf**: Material reference number of property to restore from virtual space.

**labt**: Material property label associated with `MATT` (defaults to label associated with `MATF` ).

**matt**: Material reference number assigned to generated property (defaults to `MATF` ).

## Notes

Restores into the database (from virtual space) a data table previously defined ( [[mp|MP]] ) for a particular property, assembles data with current database temperature table, and stores back in virtual space as a new property.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPDRES.html

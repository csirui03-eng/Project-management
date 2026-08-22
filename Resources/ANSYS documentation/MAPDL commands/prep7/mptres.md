---
apdl: "MPTRES"
method: mptres
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mptres
generated: 2026-08-22
tags: [mapdl-command]
---

# MPTRES

PyMAPDL: `mapdl.mptres(lab='', mat='', **kwargs)`

Restores a temperature table previously defined.

## Parameters

**lab**: Material property label ( [[mp|MP]] ).

**mat**: Material reference number.

## Notes

Restores into the database (from virtual space) a temperature table previously defined ( [[mp|MP]] ) for a particular property. The existing temperature table in the database is erased before this operation.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPTRES.html

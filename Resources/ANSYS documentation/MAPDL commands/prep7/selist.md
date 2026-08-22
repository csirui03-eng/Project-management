---
apdl: "SELIST"
method: selist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.superelements.Superelements.selist
generated: 2026-08-22
tags: [mapdl-command]
---

# SELIST

PyMAPDL: `mapdl.selist(sename='', kopt='', kint='', **kwargs)`

Lists the contents of a superelement matrix file.

## Parameters

**sename**: The name (case-sensitive) of the superelement matrix file created by the substructure generation pass ( `Sename.SUB` ). Defaults to the current `Jobname`. If a number, it is the element number of the superelement as used in the use pass.

**kopt**

List key:

- `0` - List summary data only.
- `1` - List contents, except load vectors and matrices.
- `2` - List contents, except matrices.
- `3` - List full contents. Be aware that the listing may be extensive.

**kint**

Integer printout format key:

- `OFF` - Default.
- `ON` - Long format for large integers.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SELIST.html

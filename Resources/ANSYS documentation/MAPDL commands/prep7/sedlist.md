---
apdl: "SEDLIST"
method: sedlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.superelements.Superelements.sedlist
generated: 2026-08-22
tags: [mapdl-command]
---

# SEDLIST

PyMAPDL: `mapdl.sedlist(sename='', kopt='', **kwargs)`

Lists the DOF solution of a superelement after the use pass.

## Parameters

**sename**: Name of the superelement in `Jobname.DSUB` to be listed. If a number, it is the element number of the superelement as used in the use pass. If ALL, list results for all superelements.

**kopt**

List key:

- `0` - List summary data only.
- `1` - List full contents. Be aware that the listing may be extensive.

## Notes

Lists the degree of freedom solution of a superelement after the substructure use pass. Results may be listed for any superelement on `FileDSUB`.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEDLIST.html

---
apdl: "RDELE"
method: rdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.rdele
generated: 2026-08-22
tags: [mapdl-command]
---

# RDELE

PyMAPDL: `mapdl.rdele(nset1='', nset2='', ninc='', lchk='', **kwargs)`

Deletes real constant sets.

## Parameters

**nset1**, **nset2**, **ninc**: Delete real constant sets from `NSET1` to `NSET2` (defaults to `NSET1` ) in steps of `NINC` (defaults to 1). If `NSET1` = ALL, ignore `NSET2` and `NINC` and all real constant sets are deleted.

**lchk**

Specifies the level of element-associativity checking:

- `NOCHECK` - No element-associativity check occurs. This option is the default.
- `WARN` - When a section, material, or real constant is associated with an element, the program issues a message warning that the necessary entity has been deleted.
- `CHECK` - The command terminates, and no section, material, or real constant is deleted if it is associated with an element.

## Notes

Deletes real constant sets defined with the [[r|R]] command.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RDELE.html

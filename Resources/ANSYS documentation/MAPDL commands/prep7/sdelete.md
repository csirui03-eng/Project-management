---
apdl: "SDELETE"
method: sdelete
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sdelete
generated: 2026-08-22
tags: [mapdl-command]
---

# SDELETE

PyMAPDL: `mapdl.sdelete(sfirst='', slast='', sinc='', knoclean='', lchk='', **kwargs)`

Deletes sections from the database.

## Parameters

**sfirst**: First section ID to be deleted; defaults to first available section in the database.

**slast**: Last section ID to be deleted; defaults to last available section in the database.

**sinc**: Increment of the section ID; defaults to 1.

**knoclean**

Pretension element cleanup key (pretension sections only).

- `0` - Perform cleanup of `PRETS179` pretension elements (delete pretension elements and reconnect elements split during [[psmesh|PSMESH]] ).
- `1` - Do not perform cleanup.

**lchk**

Specifies the level of element-associativity checking:

- `NOCHECK` - No element-associativity check occurs. This option is the default.
- `WARN` - When a section, material, or real constant is associated with an element, the program issues a message warning that the necessary entity has been deleted.
- `CHECK` - The command terminates, and no section, material, or real constant is deleted if it is associated with an element.

## Notes

Deletes one or more specified sections and their associated data from the Mechanical APDL database.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SDELETE.html

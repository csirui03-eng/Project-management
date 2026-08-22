---
apdl: "LREVERSE"
method: lreverse
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lreverse
generated: 2026-08-22
tags: [mapdl-command]
---

# LREVERSE

PyMAPDL: `mapdl.lreverse(lnum='', noeflip='', **kwargs)`

Reverses the normal of a line, regardless of its connectivity or mesh status.

## Parameters

**lnum**: Line number of the line whose normal direction is to be reversed. If `LNUM` = ALL, the normals of all selected lines will be reversed. If `LNUM` = P, graphical picking is enabled. A component name may also be substituted for `LNUM`.

**noeflip**

Indicates whether you want to change the normal direction of the existing elements on the reversed line(s) so that they are consistent with each line's new normal direction.

- `0` - Make the normal direction of existing elements on the reversed line(s) consistent with each line's new normal direction (default).
- `1` - Do not change the normal direction of existing elements on the reversed line(s).

## Notes

You cannot use the **LREVERSE** command to change the normal direction of any element that has a body or surface load. We recommend that you apply all of your loads only after ensuring that the element normal directions are acceptable.

Real constants (such as nonuniform shell thickness and tapered beam constants) may be invalidated by an element reversal.

For more information, see [Revising Your Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD8_6.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LREVERSE.html

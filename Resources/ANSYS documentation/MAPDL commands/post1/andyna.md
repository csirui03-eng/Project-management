---
apdl: "ANDYNA"
method: andyna
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.andyna
generated: 2026-08-22
tags: [mapdl-command]
---

# ANDYNA

PyMAPDL: `mapdl.andyna(delay='', ncycl='', start='', end='', inc='', autocontourkey='', **kwargs)`

Produces an animated sequence of contour values through substeps.

## Parameters

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

**start**: Number of the starting substep (defaults to 1).

**end**: Number of the ending substep (defaults to the maximum substep).

**inc**: Increment between substeps (defaults to 1).

**autocontourkey**: Auto-scales contour values, based on the overall subset range of values (defaults to 0, no auto- scaling).

## Notes

**ANDYNA** involves a Mechanical APDL macro which produces an animation of contour values through all the substeps of the last plot action command. This command operates only on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANDYNA**, you can replay the animated sequence by issuing [[anim|ANIM]].

The command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANDYNA.html

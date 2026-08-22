---
apdl: "ANISOS"
method: anisos
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anisos
generated: 2026-08-22
tags: [mapdl-command]
---

# ANISOS

PyMAPDL: `mapdl.anisos(nfram='', delay='', ncycl='', **kwargs)`

Produces an animated sequence of an isosurface.

## Parameters

**nfram**: Number of frames captures (defaults to 9).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

## Notes

**ANISOS** invokes a Mechanical APDL macro which produces an animation of an isosurface of the last plot action command (for example, [[plnsol|PLNSOL]],S,EQV). The **ANISOS** command operates only on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANISOS**, you can replay the animated sequence by issuing the [[anim|ANIM]] command.

This command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANISOS.html

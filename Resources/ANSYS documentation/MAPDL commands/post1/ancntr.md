---
apdl: "ANCNTR"
method: ancntr
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.ancntr
generated: 2026-08-22
tags: [mapdl-command]
---

# ANCNTR

PyMAPDL: `mapdl.ancntr(nfram='', delay='', ncycl='', **kwargs)`

Produces an animated sequence of a contoured deformed shape.

## Parameters

**nfram**: Number of frames captures (defaults to 5).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

## Notes

**ANCNTR** involves a Mechanical APDL macro which produces an animation of a contoured deformed shape of the last plot action command. This command operates only on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANCNTR**, you can replay the animated sequence by issuing the [[anim|ANIM]] command.

The command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANCNTR.html

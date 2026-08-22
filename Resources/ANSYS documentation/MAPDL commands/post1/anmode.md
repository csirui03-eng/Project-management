---
apdl: "ANMODE"
method: anmode
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anmode
generated: 2026-08-22
tags: [mapdl-command]
---

# ANMODE

PyMAPDL: `mapdl.anmode(nfram='', delay='', ncycl='', kaccel='', **kwargs)`

Produces an animated sequence of a mode shape.

## Parameters

**nfram**: Number of frames captures (defaults to 5).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

**kaccel**

Acceleration type:

- `0` - Linear acceleration.
- `1` - Sinusoidal acceleration.

## Notes

**ANMODE** invokes a Mechanical APDL macro which produces an animation of mode shape of the last plot action command (for example, [[pldisp|PLDISP]] ). The **ANMODE** command operates only on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANMODE**, you can replay the animated sequence by issuing the [[anim|ANIM]] command.

This command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANMODE.html

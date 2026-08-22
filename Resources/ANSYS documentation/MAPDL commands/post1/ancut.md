---
apdl: "ANCUT"
method: ancut
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.ancut
generated: 2026-08-22
tags: [mapdl-command]
---

# ANCUT

PyMAPDL: `mapdl.ancut(nfram='', delay='', ncycl='', qoff='', ktop='', topoff='', node1='', node2='', node3='', **kwargs)`

Produces an animated sequence of Q-slices.

## Parameters

**nfram**: Number of frames captures (defaults to 5).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

**qoff**: Q-slice working plane increment (defaults to.1 half screens).

**ktop**: Topological effect on or off (YES or NO; default is NO).

**topoff**: Topological offset (default is.1 half screens).

**node1**: Node 1 for start of the Q-slice.

**node2**: Node 2 for direction of the Q-slice.

**node3**: Node 3 for plane of the Q-slice.

## Notes

**ANCUT** involves a Mechanical APDL macro which produces an animation of Q-slices of the last plot action command. This command operates only on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANCUT**, you can replay the animated sequence by issuing the [[anim|ANIM]] command.

The command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANCUT.html

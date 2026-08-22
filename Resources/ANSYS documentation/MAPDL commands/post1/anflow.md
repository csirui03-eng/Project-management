---
apdl: "ANFLOW"
method: anflow
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anflow
generated: 2026-08-22
tags: [mapdl-command]
---

# ANFLOW

PyMAPDL: `mapdl.anflow(nfram='', delay='', ncycl='', time='', spacing='', size='', length='', **kwargs)`

Produces an animated sequence of a charged particle traveling in an electric or magnetic field.

## Parameters

**nfram**: Number of frames captured (defaults to 5).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Non-UI mode only.

**time**: Total Trace Time (seconds) (defaults to 0, which is the full flow trace).

**spacing**: Particle spacing in seconds (defaults to 0).

**size**: Particle size (defaults to 0, which is a line).

**length**: Particle length fraction (defaults to.1).

## Notes

**ANFLOW** invokes a Mechanical APDL macro which produces an animation of charged particle motion in an electric or magnetic field by the last plot action command (that is, [[pltrac|PLTRAC]] ). This command is only operational on graphic display platforms supporting the [[seg|/SEG]] command. After executing **ANFLOW**, you can replay the animated sequence by issuing the [[anim|ANIM]] command. This command is functional only in the Postprocessor.

The `TIME` option lets you set the time interval of forward travel for the trace. The `SPACING` option is used to define the particle spacing in seconds from adjacent particles in the stream line. The `SIZE` variable sets the radius of the particle. The `LENGTH` variable is used to define the particle length fraction. By default, the `LENGTH` is set to.1, which means the particle occupies 10% of the trace region and the other 90% is a color-code line. The `SPACING` and `LENGTH` variables only make sense when the `SIZE` variable is nonzero (that is, the particle is bigger than the line).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANFLOW.html

---
apdl: "TRTIME"
method: trtime
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.trtime
generated: 2026-08-22
tags: [mapdl-command]
---

# TRTIME

PyMAPDL: `mapdl.trtime(time='', spacing='', offset='', size='', length='', **kwargs)`

Defines the options used for the [[pltrac|PLTRAC]] (charged particle trace) command.

## Parameters

**time**: Total Trace Time (seconds) (defaults to 0, which is the full particle trace).

**spacing**: Particle spacing in seconds (defaults to 0).

**offset**: Particle offset in seconds (defaults to 0). It is used internally in the [[anflow|ANFLOW]] macro to produce an animation of charged particle motion in an electric or magnetic field.

**size**: Particle size (defaults to 0, which is a line).

**length**: Particle length fraction (defaults to.1).

## Notes

The **TRTIME** command varies the type of [[pltrac|PLTRAC]] display produced. Charged particle traces follow a particle's path in the forward and backward direction of travel. The DOF selected determines the color of the particle trace. `SPACING` defines the particle spacing in seconds from adjacent particles in the stream line. `OFFSET` defines the offset in seconds from the spacing set by the `SPACING` argument.

`LENGTH` defines the particle length fraction. The default value (.1), means the particle occupies 10% of the trace region, and the other 90% is a color-coded line.

`SIZE` sets the radius of the particle. Use `SPACING`, `OFFSET` and `LENGTH` only when `SIZE` is nonzero (that is, the particle is bigger than the line).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRTIME.html

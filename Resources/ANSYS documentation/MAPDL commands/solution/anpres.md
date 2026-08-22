---
apdl: "ANPRES"
method: anpres
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.anpres
generated: 2026-08-22
tags: [mapdl-command]
---

# ANPRES

PyMAPDL: `mapdl.anpres(nfram='', delay='', ncycl='', refframe='', **kwargs)`

Produces an animated sequence of the time-harmonic pressure variation of an engine-order excitation in a cyclic harmonic analysis.

## Parameters

**nfram**: Number of frame captures per cycle. Defaults to 3 times the number of sectors.

**delay**: Time delay (seconds) during animation. Defaults to 0.1 seconds.

**ncycl**: Number of animation cycles. Defaults to 5.

**refframe**

Reference frame for the model rotation.

- `0` - Rotating reference frame (default). The model remains fixed in space and the pressure revolve around the model.
- `1` - Stationary reference frame. The model rotates and the pressure locations remain fixed in space.

## Notes

**ANPRES** invokes a macro which produces an animated sequence of the time-harmonic applied pressure in the case of a mode-superposition harmonic analysis ( [[antype|ANTYPE]],HARMIC with [[cycopt|CYCOPT]],MSUP,ON). The engine-order excitation must also have been specified ( [[cycfreq|CYCFREQ]],EO). While pressure loads are not accepted as valid loading in a mode-superposition analysis (they must be applied in the modal analysis and the modal load vector applied in the mode- superposition analysis) you can apply them for the purposes of this animation.

For `RefFrame` = 1 (stationary reference frame), the rotational velocity from the Linear Perturbation step, or the current [[omega|OMEGA]] or [[cgomga|CGOMGA]] value, is used to determine the rotation direction about the cyclic cylindrical axis, otherwise a positive rotation is assumed.

You may use [[hbc|/HBC]],,ON to hide overlapping pressure faces, and use [[gline|/GLINE]],,-1 to suppress the element outlines if desired.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANPRES.html

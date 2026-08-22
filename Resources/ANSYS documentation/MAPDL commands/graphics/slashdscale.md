---
apdl: "/DSCALE"
method: slashdscale
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.scaling.Scaling.slashdscale
generated: 2026-08-22
tags: [mapdl-command]
---

# /DSCALE

PyMAPDL: `mapdl.slashdscale(wn='', dmult='', **kwargs)`

Sets the displacement multiplier for displacement displays.

**Command default:**

The default value is AUTO or 0 except when:

- Large deflection effects are included ( [[nlgeom|NLGEOM]],ON) and it is not a modal analysis; then the default is 1.
- It is a spectrum analysis ( [[antype|ANTYPE]],SPECTR); then the default is OFF.
- The amplitude of a time-harmonic solution is computed using the [[hrcplx|HRCPLX]] command (OMEGAT font FamName="Agency FB"? ≥ /\_font? 360 font FamName="Agency FB"? ° /\_font? ); then the default is OFF.
- The amplitude of a complex modal or harmonic solution is stored into the database using the [[set|SET]] command ( `KIMG` = AMPL); then the default is OFF.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**dmult**

- `AUTO or 0` - Scale displacements automatically so that maximum displacement (vector amplitude) displays as 5 percent of the maximum model length, as measured in the global Cartesian X, Y, or Z directions.
- `1` - Do not scale displacements (that is, scale displacements by 1.0, true to geometry). Often used with large deflection results.
- `FACTOR` - Scale displacements by numerical value input for FACTOR.
- `OFF` - Remove displacement scaling (that is, scale displacements by 0.0, no distortion).
- `USER` - Set `DMULT` to that used for last display (useful when last `DMULT` value was automatically calculated).

## Notes

If Multi-Plots are not being displayed, and the current device is a 3D device ( [[show|/SHOW]],3D), then the displacement scale in all active windows will be the same, even if separate **/DSCALE** commands are issued for each active window. For efficiency, the program maintains a single data structure (segment) containing only one displacement scale. The program displays the same segment (displacement scale) in all windows. Only the view settings will be different in each of the active windows.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSCALE_sl.html

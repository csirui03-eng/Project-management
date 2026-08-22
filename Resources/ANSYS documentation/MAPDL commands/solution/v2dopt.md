---
apdl: "V2DOPT"
method: v2dopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.v2dopt
generated: 2026-08-22
tags: [mapdl-command]
---

# V2DOPT

PyMAPDL: `mapdl.v2dopt(geom='', ndiv='', hidopt='', nzone='', **kwargs)`

Specifies 2D/axisymmetric view factor calculation options.

**Command default:**

By default, a planar geometry is assumed ( `GEOM` = 0) and the hidden viewing option is used ( `HIDOPT` = 0).

The view factor algorithm sets the number of rays as follows, depending on whether a planar or axisymmetric geometry is specified:

- For `GEOM` = 0, `HIDOPT` = 0 and `NZONE` = 0, the number of zones used in view the factor calculation is 200.
- For `GEOM` = 1, `HIDOPT` = 0, and `NZONE` = 0, the number of zones used in the view factor calculation is 20.

## Parameters

**geom**

Choice of geometry:

- `0` - Planar (default).
- `1` - Axisymmetric

**ndiv**

Number of divisions for axisymmetric geometry (that is, the number of circumferential segments). Default is 50. There is no maximum limit if `HIDOPT` = 0; the maximum is 90 if `HIDOPT` = 1. If `NDIV` is ≤ 6, it is reset to 50.

For more information, see [View Factors of Axisymmetric Bodies](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_heat5.html#thyeq2viewbodynov1901)

**hidopt**

Viewing option:

- `0` - Hidden (default).
- `1` - Non-hidden

**nzone**

Number of zones (that is, the number of rays emanating from a surface) for view factor calculation. This is used if `HIDOPT` = 0.

If `NZONE` is blank, it is set to 0 and the view factor algorithm sets the number of rays. (See Command Default below.)

If `NZONE` is \< 0 or \> 1000, it is set to 200.

## Notes

**V2DOPT** sets 2D view factor calculation options for the radiosity solver method. For 2D view factor calculations, the ray-emanation method is used.

The geometry type can be either 2D planar (default) or axisymmetric. For the axisymmetric case, you can define the number of circumferential segments (defaults to 20). You can also specify the hidden or non-hidden viewing option (defaults to hidden) and the number of zones for the view factor calculation. For more information, see [Process for Using the Radiosity Solver Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4_7.html#theapploadtlm61499620)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_V2DOPT.html

---
apdl: "ANHARM"
method: anharm
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anharm
generated: 2026-08-22
tags: [mapdl-command]
---

# ANHARM

PyMAPDL: `mapdl.anharm(nfram='', delay='', ncycl='', nperiod='', cms_antype='', cms_modopt='', **kwargs)`

Produces an animated sequence of time-harmonic results or complex mode shapes.

## Parameters

**nfram**: Number of frame captures per cycle. Defaults to 12.

**delay**: Time delay (seconds) during animation. Defaults to 0.1 seconds.

**ncycl**: Number of animation cycles. Defaults to 5. Not available in the GUI.

**nperiod**: Period number for the second set of frames showing the decay or growth of a mode shape. Only applies to complex mode shape animation. Defaults to 1, animating the decay or growth on the first period. Issue -1 to animate without decay or growth.

**cms_antype**

Analysis type performed in the CMS use pass. No default.

- `MODAL` - Modal analysis
- `HARMIC` - Harmonic analysis

**cms_modopt**

Mode extraction method selected in the CMS use pass. No default.

- `UNSYM` - Unsymmetric matrix
- `DAMP` - Damped system
- `QRDAMP` - Damped system using QR algorithm

## Notes

**ANHARM** invokes a Mechanical APDL macro which produces an animated sequence of:

- Time-harmonic results in the case of a harmonic analysis ( [[antype|ANTYPE]],HARMIC)
- Complex mode shapes in the case of a modal analysis ( [[antype|ANTYPE]],MODAL).

In both cases, the results are those of the last plot action (for example, [[plnsol|PLNSOL]],B,SUM).

The animation converts the complex solution variables (real and imaginary sets) into time varying results over one period. For example, if `NFRAM` = 12, then the frame captures are in increments of 30 degree phase angles.

A second set of `NFRAM` frames will be generated for damped eigenmodes from complex eigensolvers to visualize any exponential decay or growth of the oscillations. The second set generated will display frames from the period number specified by `NPERIOD`.

In a CMS analysis, the **ANHARM** command can be used after the CMS expansion pass or the use pass. To use **ANHARM** after the expansion pass, you must indicate whether a modal analysis or a harmonic analysis was performed in the CMS use pass by setting `CMS_ANTYPE` to either MODAL or HARMIC. If the use pass was a modal analysis, you must also set the `CMS_MODOPT` field to indicate the mode extraction method that was used (UNSYM, DAMP, or QRDAMP). If `CMS_MODOPT` = QRDAMP, it is assumed that `CPXMOD` was set to ON in the [[modopt|MODOPT]] command to request complex eigenmodes. If the **ANHARM** command is used after the use pass, it is not necessary to set the `CMS_ANTYPE` or `CMS_MODOPT` arguments.

For more information about complex results postprocessing, see [POST1 and POST26 - Complex Results Postprocessing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post15.html#thyeq1cdmplxres6a)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANHARM.html

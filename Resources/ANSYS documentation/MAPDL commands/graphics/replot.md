---
apdl: "/REPLOT"
method: replot
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.replot
generated: 2026-08-22
tags: [mapdl-command]
---

# /REPLOT

PyMAPDL: `mapdl.replot(label='', **kwargs)`

Reissues the last display command.

## Parameters

**label**

Controls the type of replot.

- `RESIZE` - Issued internally when a graphics window resize occurs (Default).
- `FAST` - Only applicable for 3D devices that allow a fast redisplay for changes in the view characteristics only.

## Notes

Reissues the last display command ( [[nplot|NPLOT]], [[eplot|EPLOT]], [[kplot|KPLOT]], [[plnsol|PLNSOL]], [[plvar|PLVAR]], etc.), along with its parameters, for convenience. The current display specifications are used.

When the last display command is invalid in a given processor, **/REPLOT** is also invalid in that processor. However, if you attempt a **/REPLOT** and the last display command is invalid in the current processor, Mechanical APDL generates an element display ( [[eplot|EPLOT]] ) instead, as long as the last display command was [[plnsol|PLNSOL]], [[plesol|PLESOL]], or [[pldisp|PLDISP]].

> Example: **/REPLOT** Replaced by [[eplot|EPLOT]] Automatically
>
> [[plnsol|PLNSOL]], used to display solution results as continuous contours, is a valid command in the POST1 general postprocessor.
>
> If you issue [[plnsol|PLNSOL]] followed by **/REPLOT** while in POST1, **/REPLOT** effectively reissues your earlier [[plnsol|PLNSOL]] command, along with its parameters.
>
> If you then exit POST1, enter the PREP7 preprocessor, and again issue **/REPLOT**, the program uses [[eplot|EPLOT]] internally instead.
>
> The command substitution occurs because [[plnsol|PLNSOL]] is not a valid command in PREP7.

When you click one of the buttons on the [Pan, Zoom, Rotate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_PanZoom.html#wpanzoomk) dialog box to manipulate the view of a model, **/REPLOT** is issued internally. Thus, the substitution of **/REPLOT** with [[eplot|EPLOT]] as described above may also occur for operations that you perform via with the [Pan, Zoom, Rotate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_PanZoom.html#wpanzoomk) dialog box.

**/REPLOT** does not show boundary conditions if they are applied only to a solid model and the last display command (such as [[eplot|EPLOT]] ) displays the finite element model. To show boundary conditions, the following options are available:

- Issue **/REPLOT** after you issue [[sbctran|SBCTRAN]] to transfer solid model boundary conditions to the finite element model.
- Issue **/REPLOT** after you issue a solid model display command (such as [[vplot|VPLOT]] ).

This command is valid in any processor (except as noted above).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REPLOT.html

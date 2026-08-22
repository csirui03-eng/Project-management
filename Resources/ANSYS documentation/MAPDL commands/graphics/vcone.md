---
apdl: "/VCONE"
method: vcone
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.vcone
generated: 2026-08-22
tags: [mapdl-command]
---

# /VCONE

PyMAPDL: `mapdl.vcone(wn='', phi='', **kwargs)`

Defines the view cone angle for perspective displays.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**phi**: View cone angle (0.0 to 85.°) to define perspective. Use `PHI` = 45.0° for typical perspective. Increase angle for more perspective, decrease angle for less. If the distance ( [[dist|/DIST]] ) is not specified, it will be automatically calculated to give full window magnification. If the distance is also specified, `PHI` controls both the perspective and the magnification. The larger the angle, the more the perspective and the less the magnification. Defaults to 0.0 (no perspective).

## Notes

Perspective shows the true depth of the object in the display. A variable magnification results since the back plane of the object is further from the observer than the front plane. The largest magnification occurs at the front plane. With perspective, the magnification factor (MAGF) is not only a function of the distance from the object, but also the window shape and the perspective (or view cone) angle Φ as follows:

(equation not available in the PyMAPDL source, see the Ansys help page)

where (equation omitted), for square windows, is thelargest in-plane vertical or horizontal dimension, d is the distance fromthe observer to the plane of (equation omitted) (usuallythe front plane of the object), and (equation omitted) is the view cone angle (definedwith the **/VCONE** command). The bigger the cone angle, the more the perspective. The magnification factor proportionally decreases with increasing Φ. The distance can be defined with the [[dist|/DIST]] or the [[focus|/FOCUS]] command. Note, the distance input on the [[dist|/DIST]] command is equal to d only if the focus point is located on the plane of (equation omitted). It is recommended that if a general perspective is desired(that is, not any specific cone angle), use (equation omitted) = 45.0 (since TAN(45.0) = 1.0)and let the d value be automatically calculated for full window magnification.

Note that any number of [[dist|/DIST]], [[focus|/FOCUS]], and **/VCONE** combinations can be used to produce the same magnification. Distances less than the object depth will produce views from within the object.

A magnification factor of 1.0 just fills the window. If the automatic scaling option is used ( [[auto|/AUTO]] ), the magnification factor is fixed at 0.91 (to allow a 10% margin around the object) and d is automatically calculated for the given **/VCONE** and [[focus|/FOCUS]] values. Any value of Φ between 0.0 and 85.0 (usually 45.0) may be used to activate the perspective. Views from inside the object are not possible when d is automatically calculated (use manual scaling ( [[user|/USER]] ) along with [[dist|/DIST]] specification).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VCONE.html

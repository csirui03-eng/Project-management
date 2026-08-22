---
apdl: "RPOLY"
method: rpoly
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.rpoly
generated: 2026-08-22
tags: [mapdl-command]
---

# RPOLY

PyMAPDL: `mapdl.rpoly(nsides='', lside='', majrad='', minrad='', **kwargs)`

Creates a regular polygonal area centered about the working plane origin.

## Parameters

**nsides**: Number of sides in the regular polygon. Must be greater than 2.

**lside**: Length of each side of the regular polygon.

**majrad**: Radius of the major (or circumscribed) circle of the polygon. Not used if `LSIDE` is input.

**minrad**: Radius of the minor (or inscribed) circle of the polygon. Not used if `LSIDE` or `MAJRAD` is input.

## Notes

Defines a regular polygonal area on the working plane. The polygon will be centered about the working plane origin, with the first keypoint defined at θ = 0°. The area will be defined with `NSIDES` keypoints and `NSIDES` lines. See the [[rpr4|RPR4]] and [[poly|POLY]] commands for other ways to create polygons.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RPOLY.html

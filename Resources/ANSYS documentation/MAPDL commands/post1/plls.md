---
apdl: "PLLS"
method: plls
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.plls
generated: 2026-08-22
tags: [mapdl-command]
---

# PLLS

PyMAPDL: `mapdl.plls(labi='', labj='', fact='', kund='', viewup='', **kwargs)`

Displays element table items as contoured areas along elements.

## Parameters

**labi**: Label of element table item ( [[etable|ETABLE]] ) for node I magnitude.

**labj**: Label of element table item for node J magnitude.

**fact**: Scale factor for display (defaults to 1). A negative scaling factor may be used to invert the display.

**kund**

Undisplaced shape key:

- `0` - Display selected items on undeformed shape.
- `1` - Display selected items on deformed shape.

**viewup**

View Up key:

- `0` - Ignore the view-up ( [[vup|/VUP]] ) vector when calculating trapezoid orientation (default).
- `1` - Use the view-up ( [[vup|/VUP]] ) vector to calculate trapezoid orientation.

## Notes

Displays selected items (such as shears and moments) as a contoured area (trapezoid) display along line elements and 2D axisymmetric shell elements (such as shear and moment diagrams). Three sides of the trapezoid are formed by the element (one side) and lines at nodes I and J of length proportional to the item magnitude and displayed normal to the element and the viewing direction (the two parallel sides).

When `ViewUP` = 1, the trapezoid is oriented within the plane created by the element and the global Cartesian coordinate system reference orientation (/VUP or view up) vector. In this case, the program does not perform the calculation involving the element and view direction.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLLS.html

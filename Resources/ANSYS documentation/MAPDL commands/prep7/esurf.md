---
apdl: "ESURF"
method: esurf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.esurf
generated: 2026-08-22
tags: [mapdl-command]
---

# ESURF

PyMAPDL: `mapdl.esurf(xnode='', tlab='', shape='', **kwargs)`

Generates elements overlaid on the free faces of selected nodes.

## Parameters

**xnode**

Node number that is used only in the following two cases:

- `XNODE` is a single extra node number (ID) used for generating SURF151 or SURF152 elements when KEYOPT(5)=1.
- `XNODE` is a single pressure node number (ID) used for generating `HSFLD241` or `HSFLD242` elements.

There is no default. `XNODE` must be specified for the above cases. If `XNODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A parameter or parametric expression can be substituted for `XNODE`.

**tlab**

Generates target, contact, and hydrostatic fluid elements with correct direction of normals.

This option is valid only with `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA177`, `HSFLD241`, and `HSFLD242` elements.

- `TOP` - Generates target and contact elements over beam and shell elements, or hydrostatic fluid elements over shell elements, with the normals the same as the underlying beam and shell elements (default).

- `BOTTOM` - Generates target and contact elements over beam and shell elements, or hydrostatic fluid elements over shell elements, with the normals opposite to the underlying beam and shell elements.

  If target or contact elements and hydrostatic fluid elements are defined on the same underlying shell elements, you only need to use this option once to orient the normals opposite to the underlying shell elements.

- `REVERSE` - Reverses the direction of the normals on existing selected target elements, contact elements, and hydrostatic fluid elements.

  If target or contact elements and hydrostatic fluid elements are defined on the same underlying shell elements, you only need to use this option once to reverse the normals for all selected elements.

**shape**

Used to specify the element shape for target element `TARGE170` ( `Shape` = LINE or POINT) or `TARGE169` elements ( `Shape` = POINT).

- `(blank)` - The target element takes the same shape as the external surface of the underlying element (default).
- `LINE` - Generates LINE or PARA (parabolic) segments on exterior of selected 3D elements.
- `POINT` - Generates POINT segments on selected nodes.

## Notes

The **ESURF** command generates elements of the currently active element type overlaid on the free faces of existing elements. For example, surface elements (such as `SURF151`, `SURF152`, `SURF153`, `SURF154`, or `SURF159` ) can be generated over solid elements (such as `PLANE55`, `SOLID70`, `PLANE182`, `SOLID185`, or `SOLID272`, respectively).

Element faces are determined from the selected node set ( [[nsel|NSEL]] ) and the load faces for that element type. The operation is similar to that used for generating element loads from selected nodes via the [[sf|SF]],ALL command, except that elements (instead of loads) are generated. All nodes on the face must be selected for the face to be used. For shell elements, only face one of the element is available. If nodes are shared by adjacent selected element faces, the faces are not free and no element is generated.

Elements created by **ESURF** are oriented such that their surface load directions are consistent with those of the underlying elements. Carefully check generated elements and their orientations.

Generated elements use the existing nodes and the active [[mat|MAT]], [[type|TYPE]], [[real|REAL]], and [[esys|ESYS]] attributes. The exception is when `Tlab` = REVERSE. The reversed target and contact elements have the same attributes as the original elements. If the underlying elements are solid elements, `Tlab` = TOP or BOTTOM has no effect.

When the command generates a target element, the shape is by default the same as that of the underlying element. Issue **ESURF**,,,LINE or **ESURF**,,,POINT to generate LINE, PARA, and POINT segments.

The **ESURF** command can also generate the 2D or 3D node-to-surface element `CONTA175`, based on the selected node components of the underlying solid elements. When used to generate `CONTA175` elements, all **ESURF** arguments are ignored. (If `CONTA175` is the active element type, the path Main Menu\> Preprocessor\> Modeling\> Create\> Elements\> Node-to-Surf uses **ESURF** to generate elements.)

To generate `SURF151` or `SURF152` elements that have two extra nodes from `FLUID116` elements, KEYOPT(5) for `SURF151` or `SURF152` is first set to 0 and **ESURF** is issued. Then KEYOPT(5) for `SURF151` or `SURF152` is set to 2 and [[mstole|MSTOLE]] is issued. For more information, see [Using the Surface Effect Elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE2_5.html#) in the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html).

For hydrostatic fluid elements `HSFLD241` and `HSFLD242`, the **ESURF** command generates triangular (2D) or pyramid-shaped (3D) elements with bases that are overlaid on the faces of selected 2D or 3D solid or shell elements. The single vertex for all generated elements is at the pressure node specified as `XNODE`. The generated elements fill the volume enclosed by the solid or shell elements. The nodes on the overlaid faces have translational degrees of freedom, while the pressure node shared by all generated elements has a single hydrostatic pressure degree of freedom, HDSP (see `HSFLD241` and `HSFLD242` for more information about the pressure node).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESURF.html

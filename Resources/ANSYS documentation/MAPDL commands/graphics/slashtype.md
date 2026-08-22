---
apdl: "/TYPE"
method: slashtype
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.slashtype
generated: 2026-08-22
tags: [mapdl-command]
---

# /TYPE

PyMAPDL: `mapdl.slashtype(wn='', type_='', **kwargs)`

Defines the type of display.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**type_**

Display type. Defaults to ZBUF for raster mode displays or BASIC for vector mode displays:

- `BASIC or 0` - Basic display (no hidden or section operations).
- `SECT or 1` - Section display (plane view). Use the [[cplane|/CPLANE]] command to define the cutting plane.
- `HIDC or 2` - Centroid hidden display (based on item centroid sort).
- `HIDD or 3` - Face hidden display (based on face centroid sort).
- `HIDP or 4` - Precise hidden display (like HIDD but with more precise checking). Because all facets are sorted, this mode can be extremely slow, especially for large models.
- `CAP or 5` - Capped hidden display (same as combined SECT and HIDD with model in front of section plane removed).
- `ZBUF or 6` - Z-buffered display (like HIDD but using software Z-buffering).
- `ZCAP or 7` - Capped Z-buffered display (same as combined SECT and ZBUF with model in front of section plane removed).
- `ZQSL or 8` - QSLICE Z-buffered display (same as SECT but the edge lines of the remaining 3D model are shown).
- `HQSL or 9` - QSLICE precise hidden display (like ZQSL but using precise hidden).

## Notes

Defines the type of display, such as section display or hidden-line display. Use the [[device|/DEVICE]] command to specify either raster or vector mode.

The SECT, CAP, ZCAP, ZQSL, and HQSL options produce section displays. The section or "cutting" plane is specified on the [[cplane|/CPLANE]] command as either normal to the viewing vector at the focus point (default), or as the working plane.

When you use PowerGraphics, the section display options (Section, Slice, and Capped) use different averaging techniques for the interior and exterior results. Because of the different averaging schemes, anomalies may appear at the transition areas. In many cases, the automatically computed MIN and MAX values will differ from the full range of interior values. You can lessen the effect of these anomalies by issuing [[avres|AVRES]],,FULL ( Main Menu\> General Post Proc\> Options for Outp ). This command sets your legend's automatic contour interval range according to the minimum and maximum results found throughout the entire model.

With PowerGraphics active ( [[graphics|/GRAPHICS]],POWER), the averaging scheme for surface data with interior element data included ( [[avres|AVRES]],,FULL) and multiple facets per edge ( [[efacet|/EFACET]] ,2 or [[efacet|/EFACET]],4) will yield differing minimum and maximum contour values depending on the Z-Buffering options ( **/TYPE**,,6 or **/TYPE**,,7). When the Section data is not included in the averaging schemes ( **/TYPE**,,7), the resulting absolute value for the midside node is significantly smaller.

The HIDC, HIDD, HIDP, ZBUF, ZQSL, and HQSL options produce displays with "hidden" lines removed. Hidden lines are lines obscured from view by another element, area, etc. The choice of non-Z- buffered hidden-line procedure types is available only for raster mode ( [[device|/DEVICE]] ) displays. For vector mode displays, all non-Z-buffered "hidden-line" options use the same procedure (which is slightly different from the raster procedures). Both geometry and postprocessing displays may be of the hidden-line type. Interior stress contour lines within solid elements can also be removed as hidden lines, leaving only the stress contour lines and element outlines on the visible surfaces. Midside nodes of elements are ignored on postprocessing displays. Overlapping elements will not be displayed.

The ZBUF, ZCAP, and ZQSL options use a specific hidden-line technique called software Z-buffering. This technique allows a more accurate display of overlapping surfaces (common when using Boolean operations or [[eshape|/ESHAPE]] on element displays), and allows smooth shaded displays on all interactive graphics displays. Z-buffered displays can be performed faster than HIDP and CAP type displays for large models. See also the [[light|/LIGHT]], [[shade|/SHADE]], and [[gfile|/GFILE]] commands for additional options when Z-buffering is used.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TYPE_sl.html

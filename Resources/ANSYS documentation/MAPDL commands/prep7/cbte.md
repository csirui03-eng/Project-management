---
apdl: "CBTE"
method: cbte
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.cbte
generated: 2026-08-22
tags: [mapdl-command]
---

# CBTE

PyMAPDL: `mapdl.cbte(alpha='', **kwargs)`

Specifies a thermal expansion coefficient for a composite beam section.

## Parameters

**alpha**: Coefficient of thermal expansion for the cross section.

## Notes

The **CBTE** command, one of several [composite beam section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#), specifies a thermal expansion coefficient for a beam section. The value specified is associated with the section most recently defined ( [[sectype|SECTYPE]] ) at the specified temperature ( [[cbtmp|CBTMP]] ).

Unspecified values default to zero.

Related commands are [[cbtmp|CBTMP]], [[cbmx|CBMX]], and [[cbmd|CBMD]].

For complete information, see [Using Preintegrated Composite Beam Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CBTE.html

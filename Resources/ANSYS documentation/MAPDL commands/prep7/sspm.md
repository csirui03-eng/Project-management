---
apdl: "SSPM"
method: sspm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sspm
generated: 2026-08-22
tags: [mapdl-command]
---

# SSPM

PyMAPDL: `mapdl.sspm(dens='', t='', **kwargs)`

Specifies mass density for a preintegrated shell section.

## Parameters

**dens**



**t**: Temperature.

## Notes

The **SSPM** command, one of several [preintegrated shell section commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#membraneoptionnote), specifies the mass density (assuming a unit thickness) for a preintegrated shell section. The value specified is associated with the section most recently defined (via the [[sectype|SECTYPE]] command).

Related commands are [[sspa|SSPA]], [[sspb|SSPB]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssmt|SSMT]], and [[ssbt|SSBT]].

For complete information, see [Creating a Preintegrated General Shell Section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSPM.html

---
apdl: "SECOFFSET"
method: secoffset
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secoffset
generated: 2026-08-22
tags: [mapdl-command]
---

# SECOFFSET

PyMAPDL: `mapdl.secoffset(location='', offset1='', offset2='', cg_y='', cg_z='', sh_y='', sh_z='', **kwargs)`

Defines the section offset for cross sections.

## Parameters

**location**, **offset1**, **offset2**, **cg_y**, **cg_z**, **sh_y**, **sh_z**: The location of the nodes in the section. All are dependent on the type. See the [[secoffset#Notes|SECOFFSET]] section for information about the values for the various section types.

## Notes

The **SECOFFSET** command is divided into four types: [Beams](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SECOFFSET.html#SECOFFSET.fig.1) Beams, Pipes, Shells, and Preintegrated General Shells.

The offsets defined by the **SECOFFSET** command are associated with the section most recently defined using the [[sectype|SECTYPE]] command. Not all **SECOFFSET** location values are valid for each subtype.

For the thermal shell elements, `SHELL131` and `SHELL132`, the node offset specified by **SECOFFSET** is used in thermal contact analyses. Otherwise, the **SECOFFSET** command has no effect on the solution for these elements and is used only for visualization purposes.

This command is not valid with thermal solid elements `SOLID278` and `SOLID279`.

For beam elements `BEAM188` / `BEAM189` and pipe elements `PIPE288` / `PIPE289` in the XY plane, an offset is not allowed if it causes the elements to be nonsymmetric about the XY plane.

**Beams**

### Type: BEAM

Argument data to provide:

`Location`, `OFFSETY`, `OFFSETZ`, `CG-Y`, `CG-Z`, `SH-Y`, `SH-Z`

- `Location` -

  - `CENT` - Beam node will be offset to centroid (default).
  - `SHRC` - Beam node will be offset to shear center.
  - `ORIGIN` - Beam node will be offset to origin of the cross section.
  - `USER` - Beam node will be offset to the location specified by `OFFSETY` and `OFFSETZ`.

- `OFFSETY, OFFSETZ` - Values that locate the node with respect to the default origin of the cross section when the `Location` argument is set to USER. Valid only when USER is set.

  The following figure illustrates the offsets for a channel cross section, and shows the relative locations of SHRC and CENT.

  (figure omitted, see the Ansys help page)

- `CG-Y, CG-Z, SH-Y, SH-Z` - Override the program-calculated centroid and shear centroid locations.

  This option should only be used by advanced users modeling composite cross sections.

**Pipes**

### Type: PIPE

Argument data to provide:

`OFFSETY`, `OFFSETZ`

- `OFFSETY, OFFSETZ` - Values that locate the node with respect to the center of the pipe.

**Shells**

### Type: SHELL

Argument data to provide:

`Location`, `OFFSET`

- `Location` -

  - `TOP` - Shell node will be offset to top of the section.
  - `MID` - Shell node will be offset to midplane of the section (default).
  - `BOT` - Shell node will be offset to bottom of the section.
  - `USER` - Shell node will be offset to the location specified by `OFFSET`.

- `OFFSET` - Value that locates the node with respect to the default origin (midplane) of the section. Valid only when `Location` = USER.

  The offset alters only the reference surface of the shell elements (that is, where the nodes are located). It does not change the physical dimensions of the shell itself; the volume and mass remain constant when an offset is specified.

**Preintegrated General Shells**

### Type: GENS

Argument data to provide:

`Location`, `OFFSET`

- `Location` -

  - `MID` - Shell node will be offset to midplane of the section (default).
  - `USER` - Shell node will be offset to the location specified by `OFFSET`.

- `OFFSET` - Value that locates the node with respect to the default origin (midplane) of the section. Valid only when `Location` = USER.

  The offset alters only the reference surface of the shell elements (that is, where the nodes are located).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECOFFSET.html

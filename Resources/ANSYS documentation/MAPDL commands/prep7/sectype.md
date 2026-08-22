---
apdl: "SECTYPE"
method: sectype
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.sectype
generated: 2026-08-22
tags: [mapdl-command]
---

# SECTYPE

PyMAPDL: `mapdl.sectype(secid='', type_='', subtype='', name='', refinekey='', **kwargs)`

Associates section type information with a section ID number.

## Parameters

**secid**: Section identification number. If `SECID` is blank or zero, the `SECID` number is incremented by one from the highest section ID number currently defined in the database. (See [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SECTYPE.html#SECTYPE.prodres) Notes for `SECID` input specific to general contact.)

**type_**

- `AXIS` - Define the axis for a general axisymmetric section.
- `BEAM` - Defines a beam section. This option has a `Subtype`.
- `COMB` - Defines a composite (temperature-dependent) beam section. This option has a `Subtype`.
- `CONTACT` - Defines a contact section. This option has a `Subtype`.
- `GENB` - Defines a nonlinear general (temperature-dependent) beam section. This option has a `Subtype`.
- `GENS` - Defines a preintegrated general (temperature-dependent) shell section.
- `JOINT` - Defines a joint section. This option has a `Subtype`.
- `LINK` - Defines a link section.
- `PIPE` - Defines a pipe section.
- `PRETENSION` - Defines a pretension section.
- `REINF` - Defines a reinforcing section. This option has a `Subtype`.
- `SHELL` - Defines a shell section.
- `SUPPORT` - Additive manufacturing support. This option has a `Subtype`.
- `TAPER` - Defines a tapered beam or pipe section. The sections at the end points must be topologically identical.

**subtype**

When `Type` = BEAM, the possible beam sections that can be defined for `Subtype` are: This command contains some tables and extra information which can be inspected in the original documentation pointed above.

The following figure shows the shape of each cross section subtype:

(figure omitted, see the Ansys help page)

When `Type` = COMB, the only possible [composite-beam section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#) that can be defined for `Subtype` is:

(table not available in the PyMAPDL source, see the Ansys help page)

When `Type` = CONTACT, the possible contact sections that can be defined for `Subtype` are:

(table not available in the PyMAPDL source, see the Ansys help page)

When `Type` = GENB, the possible [nonlinear general beam sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) that can be defined for `Subtype` are:

(table not available in the PyMAPDL source, see the Ansys help page)

When `Type` = JOINT, the possible joint sections that can be defined for `Subtype` are:

(table not available in the PyMAPDL source, see the Ansys help page)

When `Type` = REINF, the possible reinforcing sections that can be defined for `Subtype` are:

(table not available in the PyMAPDL source, see the Ansys help page)

When `Type` = SUPPORT, the possible support sections that can be defined for `Subtype` are:

(table not available in the PyMAPDL source, see the Ansys help page)

**name**: An eight-character name for the section. `Name` can be a string such as "W36X210" or "HP13X73" for beam sections. Section name can consist of letters and numbers, but cannot contain punctuation, special characters, or spaces.

**refinekey**: Sets mesh refinement level for thin-walled beam sections. Valid values are 0 (the default - no mesh refinement) through 5 (high level of mesh refinement). This value has meaning only when `Type` = BEAM.

## Notes

**SECTYPE** sets the section ID number, section type, and subtype for a section. A previously- defined section with the same identification number will be redefined. The geometry data describing this section type is defined by a subsequent [[secdata|SECDATA]] command. Define the offsets (if applicable) by a subsequent [[secoffset|SECOFFSET]] command. The [[slist|SLIST]] command lists the section properties, and the [[secplot|SECPLOT]] command displays the section to scale. The [[secnum|SECNUM]] command assigns the section ID number to any subsequently-defined elements.

When defining a section for contact elements ( `Type` = CONTACT) that are used in a [general contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html) definition, a section number representing a general contact surface can be specified. Alternatively, you may define a subset of a region by inputting a valid label for `SECID` (ALL_EDGE, ALL_FACE, ALL_VERT, ALL_TOP,or ALL_BOT), or by inputting a node component name with or without a component name extension (EDGE, FACE, VERT, TOP, or BOT). For more information, see in the [Contact Technology Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_flpressexamp.html).

For a beam section ( `Type` = BEAM), a subsequent [[secdata|SECDATA]] command builds a numeric model using a nine-node cell for determining the properties ( `Ixx`, `Iyy`, etc.) of the section and for the solution to the Poisson's equation for torsional behavior. See [Beam Analysis and Cross Sections](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR15_6.html) in the [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html) for examples using the section commands.

For a [nonlinear general beam section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRNGBS.html#strngbscons) ( `Type` = GENB), the `Subtype` and `REFINEKEY` options do not apply. Subsequent commands are necessary to define the section: [[bsax|BSAX]], [[bsm1|BSM1]], [[bsm2|BSM2]], [[bstq|BSTQ]], [[bss1|BSS1]], [[bss2|BSS2]], [[bsmd|BSMD]], and [[bste|BSTE]] are available. All other section commands are ignored for this section type.

For a [preintegrated composite-beam section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PREBEAMSECT_5.html#) ( `Type` = COMB), the `REFINEKEY` options do not apply. Subsequent commands are necessary to define the section: [[cbtmp|CBTMP]], [[cbmx|CBMX]], [[cbmd|CBMD]], and [[cbte|CBTE]] are available. All other section commands are ignored for this section type.

For a [tapered beam or pipe section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR15_4.html#) ( `Type` = TAPER), two subsequent [[secdata|SECDATA]] commands are required (one for each end section). Section ends must be topologically identical (same `Subtype`, number of cells and material IDs). For a tapered pipe section, end sections must have the same number of cells around the circumference and along the pipe wall, and the same shell section ID for a composite pipe wall.

For a [preintegrated general shell section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_PRESHELL_5.html#strpreshcons) ( `Type` = GENS), the `Subtype` and `REFINEKEY` options do not apply. Subsequent commands are necessary to define the section: [[sspa|SSPA]], [[sspb|SSPB]], [[sspd|SSPD]], [[sspe|SSPE]], [[ssmt|SSMT]], [[ssbt|SSBT]], and [[sspm|SSPM]] are available. All other section commands are ignored for this section type.

The PRETENSION section options of the **SECTYPE** and [[secdata|SECDATA]] commands are documented primarily to aid your understanding of the data written by the [[cdwrite|CDWRITE]] command. Ansys, Inc. recommends that you generate pretension sections via the [[psmesh|PSMESH]] command.

For a reinforcing section ( `Type` = REINF), each subsequent [[secdata|SECDATA]] command defines the material, geometry, and orientation of one discrete reinforcing fiber ( `Subtype` = DISC) or one smeared reinforcing surface ( `Subtype` = SMEAR). When referenced by a `MESH200` element, only one [[secdata|SECDATA]] command is valid.

A subsequent [[secdata|SECDATA]] command defines the geometry data describing this section type.

To display elements with shapes determined from the section definition, issue the [[eshape|/ESHAPE]] command.

Ansys Mechanical Pro **SECTYPE**,COMB is not valid.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECTYPE.html

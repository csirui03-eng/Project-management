---
apdl: "SLIST"
method: slist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.slist
generated: 2026-08-22
tags: [mapdl-command]
---

# SLIST

PyMAPDL: `mapdl.slist(sfirst='', slast='', sinc='', details='', type_='', **kwargs)`

Summarizes the section properties for all defined sections in the current session.

## Parameters

**sfirst**: First section ID to be summarized. Default = First available section in the database.

**slast**: Last section ID to be summarized. Default = Last available section in the database.

**sinc**: Increment of the section ID. Default = 1.

**details**

Determines the content of the summarized information for beam, pipe, shell, and reinforcing sections.

- `BRIEF` - For beams, lists only the section integrated properties (such as Area, Iyy, and Iyz ). This option is the default.

  For [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html), lists only the input reinforcing properties (such as material, cross-section area, fiber spacing, and input fiber location parameters).

- `FULL` - For beams, lists the section integrated properties, as well as the section nodal coordinates, section cell connectivity information, and section cell integration point coordinates. For shells, the section stiffness (membrane, bending, membrane-bending coupling and transverse shear) are printed.

  The shell section stiffness listed considers elastic behavior of materials at reference temperature only. The elements that use the section data may alter the transverse shear stiffness based on slenderness considerations (in addition to the shear correction factors shown).

  Section stiffness terms listed via the FULL option do not include section offsets. The program accounts for section offsets during the solution phase of the analysis.

  For predefined reinforcing sections used by the standard method, lists the complete information of reinforcing fibers or surfaces (including material ID, cross-section area, fiber spacing, orientation, and locations in natural coordinates). For predefined section reinforcing used by the mesh-independent method, lists section properties to generate the fibers or surfaces (including material ID, cross-section area, fiber spacing, and orientation) For reinforcing sections generated ( [[ereinf|EREINF]] ) via the mesh-independent method, lists element ID, material ID, and locations in natural coordinates.

- `GROUP` - If a section calls other sections, this option lists those sections too.

**type_**: The section type. Valid arguments are ALL (default) or any valid section type ( [[sectype|SECTYPE]] ).

## Notes

By default, the command lists information about all sections. You can limit the output to specific section types via the `Type` key.

When ocean loading is present, the command lists beam section properties used by ocean loading.

Following is example output from the **SLIST**,,,,BRIEF command for a rectangular beam section subtype ( [[sectype|SECTYPE]],,BEAM,RECT):

``` apdl
LIST SECTION ID SETS     1 TO     1 BY     1

  SECTION ID NUMBER:         1
  BEAM SECTION TYPE:     Rectangle
  BEAM SECTION NAME IS:
  BEAM SECTION DATA SUMMARY:
   Area                 =  6.0000
   Iyy                  =  4.5000
   Iyz                  = 0.11281E-15
   Izz                  =  2.0000
   Warping Constant     = 0.23299
   Torsion Constant     =  4.7330
   Center of Gravity Y  =-0.30973E-16
   Center of Gravity Z  = 0.15376E-15
   Shear Center Y       =-0.22957E-13
   Shear Center Z       = 0.31281E-13

   Beam Section is offset to CENTROID of cross section
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SLIST.html

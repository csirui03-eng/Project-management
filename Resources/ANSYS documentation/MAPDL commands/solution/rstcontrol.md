---
apdl: "RSTCONTROL"
method: rstcontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.rstcontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# RSTCONTROL

PyMAPDL: `mapdl.rstcontrol(type_='', cname='', method='', methoditem='', **kwargs)`

Controls whether element single value results are written to the results file.

## Parameters

**type_**

Solution format for database and file-write control:

- `AUTO` - Write element output quantities (STRS, EPEL, EPPL, EPCR, EPTH) in single value form for those element types that support it, and in element nodal form for all other element types (default). See [Element Single Value Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#)
- `ELSV` - Write element output quantities only in single value form. If the single value form is not supported by the element types in the model, none of the applicable results (STRS, EPEL, EPPL, EPCR, EPTH) will be available.
- `ELND` - Write all element output quantities only in element nodal form.
- `ERASE` - Reset **RSTCONTROL** specifications to their default values.
- `STAT` - List the current **RSTCONTROL** specifications.

**cname**: Name of the component (created via [[cm|CM]] ) defining the selected set of elements for which this specification is active. If no name is entered, the specification applies to all elements.

**method**

For single value results, `Method` controls how the integration point values of each element are reduced to one value:

- `AVG` - Use a simple average of values from all integration points (default).
- `MAXE` - Use only the integration point corresponding to the maximum equivalent (EQV) stress or strain quantity specified by `MethodItem`.
- `MAXP` - Use only the integration point corresponding to the maximum 1st principal stress or strain quantity specified by `MethodItem`.
- `MAXS` - Use only the integration point corresponding to the maximum shear stress or strain quantity specified by `MethodItem`.

**methoditem**

The quantity used to determine the integration point where single value results are reported. Only valid when `Method` = MAXE, MAXP, or MAXS.

- `STRS` - Choose the integration point based on stress.
- `EPEL` - Choose the integration point based on elastic strain.
- `EPPL` - Choose the integration point based on plastic strain.
- `EPCR` - Choose the integration point based on creep strain.
- `EPTH` - Choose the integration point based on thermal strain.

## Notes

**RSTCONTROL** is an optional output control command that specifies whether element nodal results or element single value results are written to the results file. This command works in conjunction with the [[outres|OUTRES]] command. [[outres|OUTRES]] specifies when each element quantity will be output, while **RSTCONTROL** specifies the type of result (element nodal versus single value). Not all elements support single value results. For more information, see [Element Single Value Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#)

The element output quantities affected by this command are:

- stress (STRS)
- elastic strain (EPEL)
- plastic strain (EPPL)
- creep strain (EPCR)
- thermal/swelling strains (EPTH)

You can issue up to 50 **RSTCONTROL** commands in an analysis. **RSTCONTROL**,ERASE erases the existing output specifications and resets the counted number of **RSTCONTROL** commands to zero.

**RSTCONTROL** is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSTCONTROL.html

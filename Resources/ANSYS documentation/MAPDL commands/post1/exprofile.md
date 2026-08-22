---
apdl: "EXPROFILE"
method: exprofile
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.exprofile
generated: 2026-08-22
tags: [mapdl-command]
---

# EXPROFILE

PyMAPDL: `mapdl.exprofile(ldtype='', load='', value='', pname='', fname='', fext='', fdir='', **kwargs)`

Exports Mechanical APDL interface data on selected nodes to an Ansys CFX Profile file.

## Parameters

**ldtype**

Load type:

- `SURF` - Surface load.
- `VOLU` - Volumetric load.

**load**

Surface loads:

- `DISP` - Displacement (in a static analysis) or mode shape and global parameters (in a modal analysis).
- `MODE` - Normalized mode shape and global parameters (in a modal analysis only).
- `TEMP` - Temperature.
- `HFLU` - Heat flux.

Volumetric loads:

- `DISP` - Displacement.
- `FORC` - Force.
- `HGEN` - Heat generation.

**value**: If a positive integer, specifies the number of the surface or volume interface. If zero (default), the selected nodes or Named Selection are used.

**pname**: Field name in CFX Profile file (32-character maximum). Defaults to `jobname_bcploadnumber` for a surface load and `jobname_subdloadnumber` for volumetric load.

**fname**: The CFX Profile filename (248-character maximum). Defaults to `jobname_bcploadnumber` for a surface load and `jobname_subdloadnumber` for a volumetric load.

**fext**: The Profile file extension (8-character maximum). Defaults to `csv`.

**fdir**: The Profile file directory (248-character maximum). Defaults to current directory.

## Notes

By default, the **EXPROFILE** command assumes the data it writes to the Profile file are in SI units. For models not described in SI units, issue the [[exunit|EXUNIT]] command as needed to write the correct unit labels on the Profile file.

For a modal analysis, if `Load` = DISP or MODE, global parameters including mass, frequency, and maximum displacement are also written to the Ansys CFX Profile file. You should therefore issue the [[exunit|EXUNIT]] command for DISP, TIME, and MASS.

Verify that the coordinate system is set to the global Cartesian ( [[rsys|RSYS]],0) before using this command.

To transfer multiple loads across an interface, specify a unique file name and extension for each load.

Force (FORC) and heat generation (HGEN) are per-unit volume.

For modal analysis, this command will write global parameters including mass, frequency, and maximum displacement to the profile file. If using cyclic symmetry analysis, this command will also write harmonic indices to the profile file.

For modal analysis, this command does not support the following mode-extraction methods ( [[modopt|MODOPT]] ): unsymmetric matrix (UNSYM), the damped system (DAMP), or the QR-damped system (QRDAMP).

To write the normalized (instead of non-normalized) mode shapes from a modal analysis to the file:

- Use `Load` = MODE.
- Verify that the mode shapes are normalized to the mass matrix ( [[modopt|MODOPT]],,,,,,OFF), the default behavior.
- Verify that the scale factor is set to 1.0 ( [[set|SET]],,,1.0), the default value.

The nodes and underlying elements must be selected in order to be exported. See for details.

For loads not specified directly via commands (such as [[sf|SF]] and [[bf|BF]] ), loads must first be read into the database ( [[set|SET]] or [[lcase|LCASE]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPROFILE.html

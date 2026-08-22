---
apdl: "VFOPT"
method: vfopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.vfopt
generated: 2026-08-22
tags: [mapdl-command]
---

# VFOPT

PyMAPDL: `mapdl.vfopt(opt='', filename='', ext='', dir_='', filetype='', fileformat='', wrio='', addional_command_arg='', **kwargs)`

Specifies options for the view factor file and calculates view factors.

## Parameters

**opt**

View factor option:

- `NEW` - Calculate view factors, store them in the database, and write them to a file. This is an action option that is executed immediately when the command is issued.

- `OFF` - Do not recalculate or read view factors if they already exist in the database; otherwise calculate them at the next [[solve|SOLVE]] command. Remaining arguments are ignored. This option is the default.

- `READ` - If the command is issued in the solution processor ( [[slashsolu|/SOLU]] ), this option reads view factors from the specified binary file when the next [[solve|SOLVE]] command is issued. `FileType` must be set to BINA (binary). For subsequent [[solve|SOLVE]] commands, the program switches back to the default option (OFF).

  If the command is issued in the radiation processor ( [[aux12|/AUX12]] ), this option immediately reads view factors from the specified binary file. `FileType` must be set to BINA (binary). The program switches back to the default option (OFF) after reading the view factors.

- `NONE` - Do not write view factors to a file when the next [[solve|SOLVE]] command is issued. Remaining arguments are ignored.

**filename**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFOPT.html) for further information.

**ext**: Filename extension for view factor matrix. Default = `vf`.

**dir_**: Directory path for view factor matrix. If you do not specify a directory path, it will default to your working directory.

**filetype**

View factor file type:

- `BINA` - Binary (default).
- `ASCI` - ASCII.

**fileformat**

Format for the specified `Filetype` :

Binary files ( `Filetype` = BINA):

- `0` - No compression. (View factor file size may be very large.)
- `1` - Zeroes are compressed out. (Useful for large models to reduce the view factor file size.)

ASCII files ( `Filetype` = ASCI):

- `0` - 10F7.4 (low precision, lower accuracy).
- `1` - 7F11.8 (high precision, higher accuracy).

**wrio**

Write only the view factors of independent facets for symmetric models. This option is valid when view factor condensation is enabled ( [[vfco|VFCO]],,,1 or [[vfco|VFCO]],,,2) and further increases efficiency by reducing read/write time; for more information, see *Considerations for Symmetric Models Using View Factor Condensation* below.

- `ON` - Writes only the independent view factors when view factor condensation has been enabled, providing additional efficiency gains. After view factors are computed and written to a file, `WRIO` is automatically reset to OFF.
- `OFF` - Turns off option to write only the independent view factors (default).

**addional_command_arg**: Additional arguments can be passed to the initial command. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFOPT.html) for further information.

## Notes

The **VFOPT** command allows you to deactivate the view factor computation ( `Opt` = OFF) if the view factors already exist in the database. The default behavior is OFF upon encountering the second and subsequent [[solve|SOLVE]] commands in the solution processor.

When `Opt` = READ, only a previously calculated view factor binary file is valid. View factors are read only and are not written after they are read in. Do not issue **VFOPT**,OFF or **VFOPT**,NONE until after the next [[solve|SOLVE]] command is executed.

If you want to read in view factors after restarting a radiation analysis, issue **VFOPT**,READ after [[antype|ANTYPE]],,REST.

For 3D analyses, two options are available for calculating view factors when running a distributed- memory parallel solution :

- Issue a [[solve|SOLVE]] command - View factors are calculated in parallel mode if no view factors were previously calculated.
- Issue a **VFOPT**,NEW command - View factors are calculated in serial mode.

For 2D analyses, view factors are calculated in serial mode.

### Considerations for Symmetric Models Using View Factor Condensation

For symmetric models using view factor condensation ( [[vfco|VFCO]],,,1 or [[vfco|VFCO]],,,2), read/write time can be reduced by writing only the independent view factors since they are the only non-zero values in the view factor matrix as described in.

When view factor condensation is turned off ( [[vfco|VFCO]],,,0), the full matrix is written to the view factor file when **VFOPT**,NEW is issued:

(equation omitted) where the view factor matrix is decomposed, and the subscripts, (equation omitted) and (equation omitted), denote independent and dependent. (See for details.)

When view factor condensation is turned on ( [[vfco|VFCO]],,,1 or [[vfco|VFCO]],,,2), use `WRIO` to control what is written to the view factor file:

- When **VFOPT**,NEW,,,,,,OFF is issued, the lumped matrix and zeros are written: (equation omitted) (For the definition of **F** <sup>L</sup>, see.)
- When **VFOPT**,NEW,,,,,,ON is issued, only the lumped matrix is written: (equation omitted).

**Example Usage**

2D Radiation Analysis Using the Radiosity Method with Decimation and Symmetry

[3D Open Enclosure with Symmetry: Radiation Analysis with Condensed View Factor Calculation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/the_example_rad_condensedVF.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFOPT.html

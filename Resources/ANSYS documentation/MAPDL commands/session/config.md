---
apdl: "/CONFIG"
method: config
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.config
generated: 2026-08-22
tags: [mapdl-command]
---

# /CONFIG

PyMAPDL: `mapdl.config(lab='', val='', **kwargs)`

Assigns values to Mechanical APDL configuration parameters.

## Parameters

**lab**

Configuration parameter to be changed:

- `NORSTGM` - Option to write or not write geometry data to the results file:

  - When `VAL` = 0, write geometry data (default).
  - When `VAL` = 1, does not write geometry data.

  Useful when complex analyses are likely to create abnormally large files.

- `NBUF` - The number of buffers ( `VAL` = 1 to 32) per file in the solver. Default: `VAL` = 4.

- `LOCFL` - File open and close actions:

  - When `VAL` = 0, global (default).
  - When `VAL` = 1, local.

  Applies to `File.EROT`, `File.ESAV`, and `FileEMAT`.

  Typically used for large problems where locally closed files may be deleted earlier in the run via [[slashfdele|/FDELE]].

- `SZBIO` - Record size ( `VAL` = 1024 to 4194304) of binary files (in integer words).

  Default: `VAL` = 16384 (system-dependent).

- `FSPLIT` - Defines split points for binary files. `VAL` is the file split point in megawords.

  Default: `VAL` = Maximum file size for the system.

- `MXND` - Maximum number of nodes.

  Default: `VAL` = 100 at first encounter.

  Dynamically expanded by doubling, even at first encounter, when the maximum is exceeded.

- `MXEL` - Maximum number of elements. Default and expansion as for MXND.

- `MXKP` - Maximum number of keypoints. Default and expansion as for MXND.

- `MXLS` - Maximum number of lines. Default and expansion as for MXND.

- `MXAR` - Maximum number of areas. Default and expansion as for MXND.

- `MXVL` - Maximum number of volumes. Default and expansion as for MXND.

- `MXRL` - Maximum number of sets of real constants (element attributes). Default and expansion as for MXND.

- `MXCP` - Maximum number of sets of coupled degrees of freedom. Default and expansion as for MXND.

- `MXCE` - Maximum number of constraint equations. Default and expansion as for MXND.

- `NOELDB` - Option to write or not write results into the database after a solution.

  - When `VAL` = 0 (default), writes results into the database.
  - When `VAL` = 1, does not write results into the database.

- `NUMLV` - Maximum number of load vectors written on `Jobname.MODE` file when `MSUPkey` = YES on the [[mxpand|MXPAND]] command.

  Default: `VAL` = 1000 at first encounter.

  When the maximum is exceeded, the value is not expanded.

  The NUMLV option is not supported for fast load vector generation ( `FastLV` = ON on the [[modcont|MODCONT]] command).

- `NUMSUBLV` - Maximum number of load vectors written on `Jobname.SUB` file in substructure/CMS generation pass.

  Default: `VAL` = 31 at first encounter.

  When the maximum is exceeded, the value is not expanded.

- `GRW_NBUF` - Option to automatically grow the number of file buffers for most binary files ( `.ESAV`, `.EMAT`, `.FULL`, and so on), with the exception of the results file and files written by the sparse and PCG equation solvers (for example, `.DSPxxxx` and `.PCn` ).

  - When `VAL` = -1, the number of file buffers does not grow automatically for any file.
  - When `VAL` = 0 (default), the number of file buffers may or may not grow automatically. The logic is program-controlled.
  - When `VAL` = 1, the number of file buffers automatically grows for most binary files to reduce the amount of I/O. This option may require a significantly greater amount of memory than the default behavior ( `VAL` = 0).

- `MEBA_LIC` - Option to control automatic checkout of a Mechanical batch license during solution when the capability is not enabled, useful for PrepPost sessions:

  - When `VAL` = 0 (default), check out a license automatically when needed.
  - When `VAL` = 1, bypass automatic license checkout.

- `STAT` - Displays current values set by the **/CONFIG** command.

**val**: Value (an integer number) assigned to the specified configuration parameter.

## Notes

All configuration parameters have initial defaults, which in most cases do not need to be changed. Where a specially configured version of the Mechanical APDL program is desired, the parameters can be changed with this command.

Issue **/CONFIG**,STAT to display current values.

Define changes before the parameter is required.

These changes (and others) may also be incorporated into the `config.ans` file, read in upon execution of the program. (See [The Configuration File](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19_4.html#a6c2Kn1b3ctg) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html).) If the same configuration parameter appears in both the configuration file and this command, this command overrides.

Distributed-memory parallel DMP solutions use the default FSPLIT value and force NOELDB = 1 for all results files. You cannot change the FSPLIT and NOELDB options for a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CONFIG.html

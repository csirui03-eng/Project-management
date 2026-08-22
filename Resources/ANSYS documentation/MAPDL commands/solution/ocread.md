---
apdl: "OCREAD"
method: ocread
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.ocread
generated: 2026-08-22
tags: [mapdl-command]
---

# OCREAD

PyMAPDL: `mapdl.ocread(fname='', ext='', option='', **kwargs)`

Reads externally defined ocean data.

## Parameters

**fname**: External ocean data file name (excluding the filename extension) and directory path containing the file. For more information, see the [[ocread#Notes|Notes section.]]

**ext**: Filename extension (limited to eight characters).

**option**: Integer value passed to the userOceanRead subroutine (as `iOption` ) for user-defined waves. This value does not apply to the diffracted wave type.

## Notes

The **OCREAD** command imports ocean data that has been defined externally (for example, via the [Hydrodynamic Diffraction System (AQWA)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/wb_aqwa/aqwa_appendix.html) ).

The command operates on the ocean load ID specified via the most recently issued [[octype|OCTYPE]] command. Issue a separate **OCREAD** command for each ocean load that you want to read into the program.

`Fname` is limited to 248 characters, including the directory path. If `Fname` does not include a directory path, the program searches for the specified file in the current working directory. An unspecified `Fname` defaults to `Jobname`.

For the diffracted wave type ( `KWAVE` = 8 on the [[ocdata|OCDATA]] command), you must issue an **OCREAD** command for the ocean wave ID in order to [import the hydrodynamic data from the hydrodynamic analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advOLexample.html).

For more information, see [Applying Ocean Loading from a Hydrodynamic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advOLexample.html)

To learn more about creating user-defined waves, see [Subroutine userPanelHydFor (Calculating Panel Loads Caused by Ocean Loading)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/Hlp_P_UPFCUSTLOAD.html#upf_userOceanRead)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCREAD.html

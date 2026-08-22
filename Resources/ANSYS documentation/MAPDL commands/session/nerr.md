---
apdl: "/NERR"
method: nerr
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.nerr
generated: 2026-08-22
tags: [mapdl-command]
---

# /NERR

PyMAPDL: `mapdl.nerr(nmerr='', nmabt='', ifkey='', num='', **kwargs)`

Limits the number of warning and error messages displayed.

## Parameters

**nmerr**: Maximum number of warning and error messages displayed per command. Defaults to 5 for interactive runs with the GUI turned on, 20 for interactive runs with the GUI turned off, 200 for batch runs. If `NMERR` is negative, the absolute value of `NMERR` is used as the maximum number of warning and error messages written to the error file ( `Jobname.ERR` ) per command, as well as the maximum number of messages displayed per command.

**nmabt**: Maximum number of warning and error messages allowed per command before run aborts (must be greater than zero). Maximum value is 99,999,999. Defaults to 10,000.

**ifkey**

Specifies whether or not to abort if an error occurs during a [[input|/INPUT]] operation:

- `0, or OFF` - Do not abort. This option is the default.
- `1, or ON` - Abort.

**num**

The number of invalid command warnings before a stop warning will be issued:

- `0` - Disables the stop warning/error function.

- `n` - An integer value representing the number of warnings that will be encountered before prompting the user to stop (default = 5). The first error encountered will ALWAYS result in a prompt.

  Invalid command warnings and error tracking are mutually exclusive.

## Notes

Limits the number of warning and error messages displayed for any one command in an interactive run.

Warning and error messages continue to be written to `Jobname.ERR` regardless of these limits, unless `NMERR` is negative. There is no way to totally suppress writing of warning and error messages to the error file.

Issue this command with `NUM` = `n` to specify the number of invalid command warnings to be encountered before the user is prompted to stop. You can then continue or abort the run. If you choose to abort the run, the log file can be saved so that any of the processing up to that point can be appended to an input that rectifies the condition. A batch run always aborts on the first error. Issue **/NERR**,STAT to list current settings.

Issue **/NERR**,DEFA to reset values to initial defaults.

An `IFKEY` value of 1 or ON causes Mechanical APDL to terminate immediately upon encountering an error during a file [[input|/INPUT]] operation. However, use of this option may cause the following conditions to occur:

- The [[input|/INPUT]] command may abort if issued for a log file ( `jobname.log` ).
- Some macros may terminate.
- A CAD connection may fail after reading only a small portion of a CAD model.

The command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NERR.html

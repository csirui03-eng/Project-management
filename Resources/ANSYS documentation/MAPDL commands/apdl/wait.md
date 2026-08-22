---
apdl: "/WAIT"
method: wait
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.process_controls.ProcessControls.wait
generated: 2026-08-22
tags: [mapdl-command]
---

# /WAIT

PyMAPDL: `mapdl.wait(dtime='', **kwargs)`

Causes a delay before the reading of the next command.

## Parameters

**dtime**: Time delay (in seconds). Maximum time delay is 59 seconds.

## Notes

### Argument descriptions

- `dtime : str` - Time delay (in seconds). Maximum time delay is 59 seconds.

The command following the **/WAIT** will not be processed until the specified wait time increment has elapsed. Useful when reading from a prepared input file to cause a pause, for example, after a display command so that the display can be reviewed for a period of time. Another "wait" feature is available via the `*ASK` command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WAIT.html

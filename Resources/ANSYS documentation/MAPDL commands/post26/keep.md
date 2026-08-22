---
apdl: "KEEP"
method: keep
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.display.Display.keep
generated: 2026-08-22
tags: [mapdl-command]
---

# KEEP

PyMAPDL: `mapdl.keep(key='', **kwargs)`

Stores POST26 definitions and data during active session.

## Parameters

**key**

State or value

- `On or 1` - Allows you to exit and reenter [[post26|/POST26]] without losing your current time history variable information. Keeps a cache of the [[post26|/POST26]] variable information including the active file name ( [[file|FILE]] ), variable definitions ( [[nsol|NSOL]], [[esol|ESOL]], [[rforce|RFORCE]], and [[solu|SOLU]] ) and stored variable data in memory for the current Mechanical APDL session.
- `Off or 0` - [[post26|/POST26]] variable information is deleted when you exit [[post26|/POST26]].

## Notes

Your variable information is saved in memory only for the current active Mechanical APDL session. It is deleted when you exit Mechanical APDL. This information is also deleted when you issue [[clear|/CLEAR]], [[resume|RESUME]], [[solve|SOLVE]], or [[reset|RESET]].

When you reenter [[post26|/POST26]] all time history variable data is available for use. When you issue [[store|STORE]], NEW, variable definitions created by math operations such as [[add|ADD]] or [[prod|PROD]] will not be restored. However, variables defined with [[nsol|NSOL]], [[esol|ESOL]], [[rforce|RFORCE]], and [[solu|SOLU]] will be restored. Only the last active results file name is kept in memory ( [[file|FILE]] ).

Commands such as [[layerp26|LAYERP26]], [[shell|SHELL]], and [[force|FORCE]] that specify the location or a component of data to be stored will retain the setting at the time of exiting [[post26|/POST26]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KEEP.html

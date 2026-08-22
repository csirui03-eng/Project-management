---
apdl: "ERINQR"
method: erinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.erinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# ERINQR

PyMAPDL: `mapdl.erinqr(key, pname='__tmpvar__', **kwargs)`

Obtain information from common errors.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**key**

Item to be returned.

- 1 = keyerr (`ER_ERRORFLAG`)

  Master error flag.

- 2 = errfil (`ER_ERRORFILE`)

  Errors file unit number.

- 3 = numnot (`ER_NUMNOTE`)

  Total number of notes displayed.

- 4 = numwrn (`ER_NUMWARNING`)

  Total number of warnings displayed.

- 5 = numerr (`ER_NUMERROR`)

  Total number of errors displayed.

- 6 = numfat (`ER_NUMFATAL`)

  Total number of fatals displayed.

- 7 = maxmsg (`ER_MAXMESSAGE`)

  Max allowed number of displayed messages before abort.

- 8 = lvlerr (`ER_ERRORLEVEL`)

  Used basically in solution (from `cnvr` command.)

  - -1 = do not set keyerr for notes/errors/warnings.
  - -2 = same as -1 but do not display message either.

- 9 = mxpcmd (`ER_MAXCOMMAND`)

  Maximum number of messages allowed per command.

- 10 = nercmd (`ER_NUMCOMMAND`)

  Number of messages displayed for any one command.

- 11 = nertim (`ER_UICLEAR`)

  Key as to how message cleared from u/i pop-up (only for "info" calls)

  - -1 = message is timed before removal
  - 0 = message needs pick or keyboard before removal
  - 1 = message stays up until replaced by another message

- 12 = nomore (`ER_NOMOREMSG`)

  Display no more messages

  - 0 = display messages
  - 1 = display discontinue message and stop displaying

- 13 = eropen (`ER_FILEOPEN`)

  - 0 = errors file is closed
  - 1 = errors file is opened

- 14 = ikserr (`ER_INTERERROR`)

  - 0 = if interactive do not set keyerr.
  - -1 = if interactive set keyerr (used by mesher and tessalation)

- 15 = kystat (`ER_KEYOPTTEST`)

  Flag to bypass keyopt tests in the elcxx routines associated with status/panel info inquiries.

  - 0 = do not bypass keyopt tests
  - 1 = perform all keyopt tests also flag to bypass setting of `_STATUS` upon resume

- 16 = mxr4r5 (`ER_MIXEDREV`)

  Mixed rev4-rev5 input logic (`*do`, `*if` , `*go` , `*if-go`)

  - 1 = rev5 found (`*do`, `*fi-then-*endif`)
  - 2 = rev4 found (`*go`, `:xxx` , `*if`, ...., `:xxx`)
  - 3 = warning printed. do not issue any more.

- 17 = mshkey (`ER_MESHING`)

  CPU intensive meshing etc. This will cause `nertim (11)` to be set to `-1` for "notes", `1` for "warnings",and `0` for "errors". Checking of this key is done in `anserr`.

  - 0 = not meshing or cpu intensive
  - 1 = yes, meshing or cpu intensive

- 18 = syerro (18)

  Systop error code. read by anserr if set.

- 19 = opterr (`ER_OPTLOOPING`)

  - 0 = no error in main ansys during opt looping
  - 1 = an error has happened in main ansys during opt looping

- 20 = flowrn (20)

  Flag used by "floqa" as to list `floqa.ans`.

  - 0 = list `floqa.ans`
  - 1 = `floqa.ans` has been listed. do not list again.

- 22 = noreport (22)

  Used in GUI for turning off errors due to strsub calls.

  - 0 = process errors as usual
  - 1 = do **NOT** report errors

- 23 = pdserr (`ER_PDSLOOPING`)

  - 0 = no error in main ansys during pds looping
  - 1 = an error has happened in main ansys during pds looping

- 24 = mxpcmdw (24)

  Number of messages written to file.err for any command

  - 0 = write all errors to file.err
  - 1 = only write displayed errors to file.err

- 25 = kystop

  No information is provided.

- 26 = icloads (26)

  Key to forbid the `iclist` command from listing solution data instead of the input data.

  - 0 = `iclist` is OK
  - 1 = do not permit `iclist`

- 27 = ifkey error (27)

  key on whether or not to abort during `/input <ansys.mapdl.core.Mapdl.input>` on error.

  - 0 = do not abort
  - 1 = abort

- 28 = intrupt (`ER_INTERRUPT`)

  Interrupt button, so executable returns no error.

- spare - spare integer variables

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: Value corresponding to key.

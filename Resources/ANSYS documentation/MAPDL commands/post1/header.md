---
apdl: "/HEADER"
method: header
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.listing.Listing.header
generated: 2026-08-22
tags: [mapdl-command]
---

# /HEADER

PyMAPDL: `mapdl.header(header='', stitle='', idstmp='', notes='', colhed='', minmax='', **kwargs)`

Sets page and table heading print controls.

## Parameters

**header**

Mechanical APDL page header (system, date, time, version, copyright, title, etc.):

- `ON` - Turns this item on (default for batch mode; not available for interactive mode).
- `OFF` - Turns this item off.
- `(blank)` - Retains the previous setting.

**stitle**: Subtitles (see [[stitle|/STITLE]] command): ON, OFF, or (blank) (see above).

**idstmp**: Load step information (step number, substep number, time value): ON, OFF, or (blank) (see above).

**notes**: Information relative to particular table listings: ON, OFF, or (blank) (see above).

**colhed**: Column header labels of table listings (currently only for single column tables): ON, OFF, or (blank) (see above).

**minmax**: Minimum/maximum information or totals after table listings: ON, OFF, or (blank) (see above).

## Notes

Sets specifications on or off for page and table heading print controls associated with the POST1 [[prnsol|PRNSOL]], [[presol|PRESOL]], [[pretab|PRETAB]], [[prrsol|PRRSOL]], and [[prpath|PRPATH]] commands. If the printout caused a top-of-form (page eject to top of next page), the top-of-form is also suppressed with the printout. Issue **/HEADER**,STAT to display the current settings. Issue **/HEADER**,DEFA to reset the default specifications.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HEADER.html

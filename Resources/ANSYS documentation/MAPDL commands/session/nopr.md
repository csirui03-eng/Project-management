---
apdl: "/NOPR"
method: nopr
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.list_controls.ListControls.nopr
generated: 2026-08-22
tags: [mapdl-command]
---

# /NOPR

PyMAPDL: `mapdl.nopr(**kwargs)`

Suppresses the expanded interpreted input data listing.

> [!WARNING]
> PyMAPDL uses the console output to parse and retrieve information from the MAPDL instance. Hence, it is strongly advised to **NOT** use this command unless you really know what you are doing. In case of an accidental `NOPR` activation, you can run mapdl.gopr() to reactivate console output.

## Notes

Suppresses printout of interpreted input data, including information labeled as "Notes." When this printout is not suppressed, the data input to the analysis is echoed to the output file in an expanded format. Printout is suppressed until a [[gopr|/GOPR]] or [[slashgo|/GO]] command is read.

Use of **/NOPR** is not recommended when the graphical user interface (GUI) is active. The GUI sometimes issues "hidden" **/NOPR** and [[gopr|/GOPR]] command sequences, which will countermand user-issued **/NOPR** commands, thus making the use of **/NOPR** in the GUI environment unpredictable.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NOPR.html

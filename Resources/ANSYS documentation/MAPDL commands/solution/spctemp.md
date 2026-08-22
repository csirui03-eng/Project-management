---
apdl: "SPCTEMP"
method: spctemp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.spctemp
generated: 2026-08-22
tags: [mapdl-command]
---

# SPCTEMP

PyMAPDL: `mapdl.spctemp(encl='', temp='', **kwargs)`

Defines a free-space ambient temperature for radiation using the Radiosity method.

## Parameters

**encl**: Radiating surface enclosure number. Defaults to 1. If `ENCL` = STAT, the command lists all enclosure space temperatures. If `ENCL` = DELE, the command deletes all enclosure space temperatures.

**temp**: Temperature of free-space in the reference temperature system. The temperature will be offset by the value specified in the [[toffst|TOFFST]] command for internal calculations.

## Notes

For open systems, an enclosure may radiate to the free-space ambient temperature ( `TEMP` ).

Open systems may be characterized by one or more enclosures ( `ENCL` ). Each enclosure may radiate to a different free-space ambient temperature ( `TEMP` ).

For the first load step, the space temperature ramps from the uniform temperature specified by the [[tunif|TUNIF]] command to the temperature specified by the **SPCTEMP** command. For subsequent load steps, it ramps from the previous value of the space temperature. For intermediate load steps, use the **SPCTEMP**,DELETE command and specify the space temperature again to ramp from the uniform temperature.

Reissuing **SPCTEMP** does not overwrite the previous value. To change the free-space ambient temperature ( `TEMP` ) between loadsteps, you must issue **SPCTEMP**,DELETE and then reissue **SPCTEMP**, `ENCL`, `TEMP`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPCTEMP.html

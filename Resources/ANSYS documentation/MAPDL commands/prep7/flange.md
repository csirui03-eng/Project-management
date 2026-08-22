---
apdl: "FLANGE"
method: flange
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.flange
generated: 2026-08-22
tags: [mapdl-command]
---

# FLANGE

PyMAPDL: `mapdl.flange(nloc='', leng='', mass='', sif='', flex='', arins='', elem='', **kwargs)`

Defines a flange in a piping run.

## Parameters

**nloc**: Node where flange is to be placed (as described below). Defaults to current piping run starting point.

**leng**: Length of flange (defaults to larger pipe OD).

**mass**: Dry mass (weight/gravity) of flange without insulation (defaults to equivalent straight pipe mass). Note that acceleration ( [[acel|ACEL]] ) must be nonzero for weight to be calculated.

**sif**: Stress intensification factor (defaults to 1.0).

**flex**: Bending flexibility factor (defaults to 1.0).

**arins**: Insulation surface area (defaults to equivalent straight pipe insulation area). Units (length <sup>2</sup> ) must be consistent with the smallest unit of the system used (not mixed) regardless of the PUNIT option.

**elem**: Element number to be assigned to flange (defaults to the previous maximum element number (MAXEL) + 1).

## Notes

Defines a flange (straight-pipe element PIPE16 with adjusted specifications and loadings) at a given location in a piping run. (See the RUN command, and other commands described here, in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

The FLANGE command is similar to the VALVE command except for a different flexibility factor default. The location may be 1) between two adjacent colinear straight pipes, 2) between an adjacent straight pipe and a different piping component, or 3) at the end of a straight pipe.

For Case 1, two new nodes are generated at the ends of the flange. The two straight pipes are automatically "shortened" to meet the ends of the flange. The flange specifications and loadings are taken from the corresponding two straight pipes.

For Case 2, one new node is generated at one end of the flange. The straight pipe is automatically "shortened" to meet this end of the flange. The other end of the flange meets the other piping component. The flange specifications and loadings are taken from the straight pipe.

For Case 3, one new node is generated at the free end of the flange. The other end of the flange meets the straight pipe. The flange specifications and loadings are taken from the straight pipe.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FLANGE.html

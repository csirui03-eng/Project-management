---
apdl: "PUNIT"
method: punit
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.punit
generated: 2026-08-22
tags: [mapdl-command]
---

# PUNIT

PyMAPDL: `mapdl.punit(kopt='', **kwargs)`

Selects the system of length units to be used in a piping run.

**Command default:**

Input units are consistent (no conversions are done).

## Parameters

**kopt**

Units key:

- `0` - Input units are consistent (no conversions are done) (default).

- `FTIN or 1` - English units (feet A, inch B, fraction of inch C/D). Use A+B+C/D format for PDRAG, BRANCH, RUN, BEND, MITER, REDUCE, VALVE, BELLOW, FLANGE, PSPRNG, and PGAP commands. Precede by "-'' sign for negative coordinates. (Example: 5+6+7/16 for 5 ft. 6-7/16 in., +3 for 3 in., -0+3 for -3 in., +0+9/16 for 9/16 in.).

  The two signs should not be consecutive. A, B, C, and D must be integers. Use B+C/D format for PSPEC, PINSUL, and PCORRO commands. (Example: 2 for 2 in., 3+1/2 for 3-1/2 in., +3/8 for 3/8 in.)

- `METRIC or 2` - Metric units (meter A, centimeter B, fraction of cm C/D). Use as explained for English units. (Example: 5+6+7/10 for 5 m 6-7/10 cm with PDRAG command.)

## Notes

Selects the system of length units to be used for the piping commands. Mixed length units require a + sign to delimit (or position) the units in the system and are converted to the smallest unit of the system (inches or centimeters) upon input.

This conversion is local only to pure length units of the piping commands listed. Other units and units for other commands must be input to be consistent with the smallest length unit of the system used.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PUNIT.html

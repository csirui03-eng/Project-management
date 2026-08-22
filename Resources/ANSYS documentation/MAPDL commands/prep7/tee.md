---
apdl: "TEE"
method: tee
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.tee
generated: 2026-08-22
tags: [mapdl-command]
---

# TEE

PyMAPDL: `mapdl.tee(ncent='', type_='', elem='', einc='', l1='', l2='', l3='', **kwargs)`

Defines a tee in a piping run.

## Parameters

**ncent**: Node where three straight pipes intersect forming a tee (or "Y"). Defaults to last starting branch node (BRANCH).

**type_**

Type of tee:

- `WT` - Welding tee (default).

  r = (D<sub>0</sub> - t<sub>w</sub> ) / 2

  h = 4.4 t<sub>w</sub> / r

  SIF = 0.9 / (h <sup>2/3</sup> )

  If (SIF \< 1) SIF = 1

- `UFT` - Unreinforced fabricated tee.

  r = (D<sub>0</sub> - t<sub>w</sub> ) / 2

  h = t<sub>w</sub> / r

  SIF = 0.9 / (h <sup>2/3</sup> )

  If (SIF \< 1) SIF = 1

**elem**: Element number to be assigned to first tee leg (defaults to the previous maximum element number (MAXEL) + 1).

**einc**: Element number increment (defaults to 1).

**l1**, **l2**, **l3**: Tee leg lengths (corresponding in order of increasing straight pipe element numbers). Must be less than the straight pipe length. Defaults to 2 x OD of straight pipe (for each leg).

## Notes

Defines a tee in place of the tee intersection of three previously defined straight pipe elements. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

The new tee is also composed of three PIPE16 straight pipe elements, but of the leg lengths specified and with the appropriate tee factors calculated.

Three new nodes are generated at the ends of the tee.

The original three straight pipes are automatically "shortened" to meet the ends of the tee. The tee specifications and loadings are taken from the corresponding three straight pipes.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/None

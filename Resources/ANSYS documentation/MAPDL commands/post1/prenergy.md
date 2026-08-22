---
apdl: "PRENERGY"
method: prenergy
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prenergy
generated: 2026-08-22
tags: [mapdl-command]
---

# PRENERGY

PyMAPDL: `mapdl.prenergy(energytype='', cname1='', cname2='', cname3='', cname4='', cname5='', cname6='', **kwargs)`

Prints the total energies of a model or the energies of the specified components.

## Parameters

**energytype**

Type of energies to be printed:

- `ALL` - All energies are printed: potential, kinetic, artificial hourglass/drill stiffness, contact stabilization energy, and artificial stabilization energy when applicable. This is the default.
- `SENE` - Potential energy (stiffness energy).
- `KENE` - Kinetic energy.
- `DENE` - Damping energy.
- `WEXT` - Work done by external loads.

**cname1**, **cname2**, **cname3**, **cname4**, **cname5**, **cname6**

Component names for energies of the components printout.

If `Cname1` is blank, the total energies are listed.

If `Cname1` = ALL, the energies are listed for all selected components.

If `Cname1` is neither blank nor ALL, it is the name of an existing component. The energies are listed for up to 6 selected components named in `Cname1` to `Cname6`.

## Notes

The **PRENERGY** command prints out either the total energies of the entire model or the energies of the components depending on the `Cname1` specification.

Only existing components based on elements (defined with the [[cm|CM]] command) are supported when component energies are listed.

Damping energy (DENE) and work done by external loads (WEXT) are available only if the following were set prior to the analysis solution: `EngCalc` = YES on the [[trnopt|TRNOPT]], [[hrout|HROUT]] or [[mxpand|MXPAND]] command; and `Item` = VENG, ESOL, or ALL on the [[outres|OUTRES]] command.

If `EngCalc` = YES on the [[hrout|HROUT]] or [[mxpand|MXPAND]] command, average, amplitude, and peak values are returned for potential (SENE) and kinetic (KENE) energies.

The energy values can be retrieved using the [[get|*GET]] command with `Entity` = PRENERGY.

This command applies to structural elements only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRENERGY.html

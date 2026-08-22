---
apdl: "SYNCHRO"
method: synchro
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.synchro
generated: 2026-08-22
tags: [mapdl-command]
---

# SYNCHRO

PyMAPDL: `mapdl.synchro(ratio='', cname='', **kwargs)`

Specifies whether the excitation frequency is synchronous or asynchronous with the rotational velocity of a structure.

## Parameters

**ratio**

In a stationary reference frame ( [[coriolis|CORIOLIS]] with `RefFrame` = ON), `RATIO` is the ratio between the frequency of excitation and the frequency of the rotational velocity of the structure. This value must be greater than 0. The default is an unbalance excitation.

In a rotating reference frame ( [[coriolis|CORIOLIS]] with `RefFrame` = OFF), `RATIO` is the ratio between the frequency of excitation and the frequency of the rotational velocity of the structure minus 1. This value must be greater than 0. There is no default.

**cname**: The name of the rotating component on which to apply the harmonic excitation.

## Notes

The **SYNCHRO** command specifies whether the excitation frequency is synchronous or asynchronous with the rotational velocity of a structure in a harmonic analysis. Use the command to take into account rotating harmonic forces on rotating structures.

Mechanical APDL calculates the rotational velocity Ω of the structure from the excitation frequency f, defined (via the [[harfrq|HARFRQ]] command) as Ω = 2π f / `RATIO`. The rotational velocity is applied along the direction cosines of the rotation axis (specified via an [[omega|OMEGA]] or [[cmomega|CMOMEGA]] command).

In a stationary reference frame, specifying any value for `RATIO` causes a general rotational force excitation and not an unbalance force. To define an unbalance excitation force (F = Ω <sup>2</sup> \* Unb), `RATIO` should be left blank (the nodal unbalance Unb is specified via the [[f|F]] command).

In a rotating reference frame ( [[coriolis|CORIOLIS]] with `RefFrame` = OFF), an unbalance excitation is a static load; therefore, a value must be supplied for `RATIO`.

The **SYNCHRO** command is valid only for the full harmonic analysis method ( [[hropt|HROPT]],FULL) and the frequency-sweep harmonic analysis method ( [[hropt|HROPT]],VT) involving a rotating structure ( [[omega|OMEGA]] or [[cmomega|CMOMEGA]] ) with Coriolis enabled ( [[coriolis|CORIOLIS]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SYNCHRO.html

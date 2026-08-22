---
apdl: "ENERSOL"
method: enersol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.enersol
generated: 2026-08-22
tags: [mapdl-command]
---

# ENERSOL

PyMAPDL: `mapdl.enersol(nvar='', item='', name='', **kwargs)`

Specifies the total energies to be stored.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to NV).

**item**

- `SENE` - Potential energy (stiffness energy)
- `KENE` - Kinetic energy
- `DENE` - Damping energy
- `WEXT` - Work done by external load
- `AENE` - Artificial energy due to hourglass control/drill stiffness or due to contact stabilization damping
- `STEN` - Artificial energy due to nonlinear stabilization

**name**: A 32-character name identifying the item on printouts and displays. Defaults to a 4-character label formed by the four characters of the `Item` value.

## Notes

Damping energy (DENE) and work done by external loads (WEXT) are available only if the following were set prior to the analysis solution: `EngCalc` = YES on the [[trnopt|TRNOPT]], [[hrout|HROUT]] or [[mxpand|MXPAND]] command; and `Item` = VENG, ESOL, or ALL on the [[outres|OUTRES]] command.

If `EngCalc` = YES on the [[hrout|HROUT]] or [[mxpand|MXPAND]] command, `Item` = SENE and KENE are the average potential and kinetic energies, respectively.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ENERSOL.html

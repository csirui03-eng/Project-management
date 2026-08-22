---
apdl: "FCTYP"
method: fctyp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.failure_criteria.FailureCriteria.fctyp
generated: 2026-08-22
tags: [mapdl-command]
---

# FCTYP

PyMAPDL: `mapdl.fctyp(oper='', lab='', **kwargs)`

Activates or removes failure-criteria types for postprocessing.

## Parameters

**oper**

Operation key:

- `ADD` - Activate failure-criteria types. This option is the default behavior.
- `DELE` - Remove failure-criteria types.

**lab**

Valid failure-criteria labels. If ALL, select all available (including user-defined) failure criteria.

- `EMAX` - Maximum strain criterion (default)
- `SMAX` - Maximum stress criterion (default)
- `TWSI` - Tsai-Wu strength index (default)
- `TWSR` - Inverse of Tsai-Wu strength ratio index (default)
- `HFIB` - Hashin fiber failure criterion
- `HMAT` - Hashin matrix failure criterion
- `PFIB` - Puck fiber failure criterion
- `PMAT` - Puck inter-fiber (matrix) failure criterion
- `L3FB` - LaRc03 fiber failure criterion
- `L3MT` - LaRc03 matrix failure criterion
- `L4FB` - LaRc04 fiber failure criterion
- `L4MT` - LaRc04 matrix failure criterion
- `USR1 through USR9` - User-defined failure criteria

## Notes

The **FCTYP** command modifies the list of active failure criteria.

By default, active failure criteria include EMAX, SMAX, TWSI, and TWSR.

The command affects any subsequent postprocessing listing and plotting commands (such as [[presol|PRESOL]], [[prnsol|PRNSOL]], [[plesol|PLESOL]], [[plnsol|PLNSOL]], and [[etable|ETABLE]] ).

A single **FCTYP** command allows up to six failure-criteria labels. If needed, reissue the command to activate or remove additional failure-criteria types.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FCTYP.html

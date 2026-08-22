---
apdl: "RUN"
method: run
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.run
generated: 2026-08-22
tags: [mapdl-command]
---

# RUN

PyMAPDL: `mapdl.run(dx='', dy='', dz='', ndiv='', nend='', estrt='', einc='', **kwargs)`

PyMAPDL overrides `mapdl.run` with its own wrapper, so the signature above is not what `mapdl.run` runs. Reach the APDL command as text: `mapdl.run("RUN,...")`.

Defines a pipe run.

## Parameters

**dx**, **dy**, **dz**: Increment (in terms of the active coordinate system components) to determine run end point. Increment is applied to branch starting point (BRANCH) or end point of previous run (whichever was later).

**ndiv**: Number of divisions (elements) along branch (defaults to 1). A node is generated at the end of each division.

**nend**: Number to be assigned to end node of branch (defaults to MAXNP + `NDIV` ).

**estrt**: Number to be assigned to first element of branch (defaults to the previous maximum element number (MAXEL) + 1).

**einc**: Element number increment (defaults to 1).

## Notes

Defines a pipe run from a previous point to an incremental point. Nodes (and elements) are generated straight (in the active coordinate system). Elements are of type PIPE16 straight pipes. Material properties, real constants, and loads are derived from the previously defined piping specifications. Piping loads and specifications are defined via PCORRO, PDRAG, PFLUID, PINSUL, POPT, PPRES, PSPEC, PTEMP, and PUNIT commands.

Generated items may be listed (or displayed) with the standard commands ( [[nlist|NLIST]], [[elist|ELIST]], [[nplot|NPLOT]], [[eplot|EPLOT]], [[etlist|ETLIST]], [[rlist|RLIST]], etc.).

Items may also be modified ( [[nmodif|NMODIF]], [[emodif|EMODIF]], [[rmodif|RMODIF]], etc.) or redefined as desired.

See [Piping Models](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/aDcQxq3aemcm.html) for more information.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RUN.html

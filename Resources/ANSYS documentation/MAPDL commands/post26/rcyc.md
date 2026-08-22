---
apdl: "RCYC"
method: rcyc
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.rcyc
generated: 2026-08-22
tags: [mapdl-command]
---

# RCYC

PyMAPDL: `mapdl.rcyc(ir='', ia='', sector='', name='', **kwargs)`

Calculates cyclic results for a mode-superposition harmonic solution.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previous variable, the previous variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**sector**: Sector number to calculate the results for.

**name**: Thirty-two character name identifying the variable on listings and displays. Embedded blanks are compressed for output.

## Notes

This command calculates the harmonic response in the sector specified by `SECTOR` for the variable referenced by the reference number `IA`. Only component values for `IA` are valid (no principles or sums). The variable specified by `IR` will contain the harmonic solution. `Jobname.RFRQ` from the cyclic mode-superposition harmonic solve and `Jobname.RST` or `Jobname.RSTP` from the cyclic modal solve must be available for the calculations to occur. The Jobname must be the same for the cyclic modal solve and the cyclic mode-superposition harmonic solve.

For `SECTOR` \> 1, the result is in the nodal coordinate system of the base sector, and it is rotated to the expanded sector's location. Refer to [Using the /CYCEXPAND Command](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#)

See also [Mode-Superposition Harmonic Cyclic Symmetry Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycsolvharmcycsym.html#cycsym_exampleForcedRespMistuning)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RCYC.html

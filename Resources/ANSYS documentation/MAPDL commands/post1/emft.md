---
apdl: "EMFT"
method: emft
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.emft
generated: 2026-08-22
tags: [mapdl-command]
---

# EMFT

PyMAPDL: `mapdl.emft(**kwargs)`

Summarizes electromagnetic forces and torques.

## Notes

Use this command to summarize electromagnetic force and torque in both static electric and magnetic problems. To use this command, select the nodes in the region of interest and make sure that all elements are selected. If [[rsys|RSYS]] = 0, the force is reported in the global Cartesian coordinate system. If [[rsys|RSYS]] ≠ 0, force is reported in the specified coordinate system. However, for torque, if [[rsys|RSYS]] ≠ 0, this command will account for the shift and rotation as specified by [[rsys|RSYS]], but will report only the Cartesian components.

Forces are stored as items FXSUM, FYSUM, FZSUM, and FSSUM. Torque is stored as items TXSUM, TYSUM, TZSUM, and TSSUM.

This command is valid only with `PLANE121`, `SOLID122`, `SOLID123`, `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, `SOLID227`, `PLANE233`, `SOLID236` and `SOLID237` elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMFT.html

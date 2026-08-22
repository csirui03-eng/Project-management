---
apdl: "ECPCHG"
method: ecpchg
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.ecpchg
generated: 2026-08-22
tags: [mapdl-command]
---

# ECPCHG

PyMAPDL: `mapdl.ecpchg(**kwargs)`

Optimizes degree-of-freedom usage in a coupled acoustic model.

## Notes

The **ECPCHG** command converts uncoupled acoustic element types to coupled acoustic element types that are attached to the fluid-structure interaction interface. Or it converts coupled acoustic element types to uncoupled acoustic element types that are not attached to the fluid- structure interaction interface. Issuing **ECPCHG** can dramatically reduce the size of the `Jobname.EMAT` file, compared to the model fully meshed with the coupled acoustic elements.

Performing the **ECPCHG** conversion on meshed volumes can create circumstances in which more than one element type is defined for a single volume.

If the acoustic elements are coupled with shell elements ( `SHELL181` or `SHELL281` ), you must set the fluid-structure interaction (FSI) flag by issuing the [[sf|SF]],,FSI command before the **ECPCHG** command.

**ECPCHG** may add new element types to your model, or it may change the element type for existing acoustic elements. You should verify the defined element types with [[etlist|ETLIST]] and the element attributes with [[elist|ELIST]] after using this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ECPCHG.html

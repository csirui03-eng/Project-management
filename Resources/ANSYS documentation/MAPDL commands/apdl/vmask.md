---
apdl: "*VMASK"
method: vmask
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vmask
generated: 2026-08-22
tags: [mapdl-command]
---

# *VMASK

PyMAPDL: `mapdl.vmask(par='', **kwargs)`

Specifies an array parameter as a masking vector.

## Parameters

**par**: Name of the mask parameter. The starting subscript must also be specified.

## Notes

Specifies the name of the parameter whose values are to be checked for each resulting row operation. The mask vector usually contains only 0 (for false) and 1 (for true) values. For each row operation the corresponding mask vector value is checked. A true value allows the operation to be done. A false value skips the operation (and retains the previous results). A mask vector can be created from direct input, such as M(1) = 1,0,0,1,1,0,1; or from the DATA function of the [[vfill|*VFILL]] command. The NOT function of the [[vfun|*VFUN]] command can be used to reverse the logical sense of the mask vector. The logical compare operations (LT, LE, EQ, NE, GE, and GT) of the [[voper|*VOPER]] command also produce a mask vector by operating on two other vectors. Any numeric vector can be used as a mask vector since the actual interpretation assumes values less than 0.0 are 0.0 (false) and values greater than 0.0 are 1.0 (true). If the mask vector is not specified (or has fewer values than the result vector), true (1.0) values are assumed for the unspecified values. Another skip control may be input with `NINC` on the [[vlen|*VLEN]] command. If both are present, operations occur only when both are true. The mask setting is reset to the default (no mask) after each **\*V** `XX` or **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VMASK.html

---
apdl: "EDDC"
method: eddc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.eddc
generated: 2026-08-22
tags: [mapdl-command]
---

# EDDC

PyMAPDL: `mapdl.eddc(option='', ctype='', cont='', targ='', **kwargs)`

Deletes or deactivates/reactivates contact surface specifications in an

explicit dynamic analysis.

## Parameters

**option**

Option to be performed for contact definition specified by Ctype, Cont, and Targ.

DELE - Delete the specified contact definition (default); valid only in a new  
analysis.

DACT - Deactivate the specified contact definition; valid only in a small restart.

RACT - Reactivate the specified contact definition (which was previously deactivated);  
valid only in a small restart.

**ctype**: Contact behavior label (see EDCGEN command for valid labels).

**cont**: Component name or part number \[EDPART\] identifying the contact surface.

**targ**: Component name or part number \[EDPART\] identifying the target surface.

## Notes

This command allows you to delete or deactivate/reactivate a particular contact specification that was defined by EDCGEN. The contact definition is identified by Ctype, Cont, and Targ (Note that Cont and Targ may not be required for Ctype = AG, SE, ASSC, ESS, and SS). The delete option (Option = DELE) permanently deletes the contact from the database. Any additional contact parameters defined with the EDCMORE command for the contact definition identified on this command will also be deleted or deactivated/reactivated.

You cannot delete contact specifications in an explicit dynamic small restart (EDSTART,2). However, you can use Option = DACT to deactivate a contact definition that is not needed in the small restart. That contact definition may then be reactivated in a subsequent small restart by using Option = RACT.

To delete or deactivate/reactivate all contact specifications for the entire model, use EDDC,Option,ALL.

The EDDC command is not supported in an explicit dynamic full restart analysis (EDSTART,3). Thus, you cannot delete, deactivate, or reactivate contact specifications in a full restart that were defined in the previous analysis.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.

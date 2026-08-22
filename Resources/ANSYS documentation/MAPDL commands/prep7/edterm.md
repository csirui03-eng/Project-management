---
apdl: "EDTERM"
method: edterm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edterm
generated: 2026-08-22
tags: [mapdl-command]
---

# EDTERM

PyMAPDL: `mapdl.edterm(option='', lab='', num='', stop='', maxc='', minc='', **kwargs)`

Specifies termination criteria for an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define termination criteria (default).

DELE - Delete termination criteria.

LIST - List termination criteria.

**lab**

Label identifying the type of termination (no default).

NODE - Terminate solution based on nodal point coordinates. The analysis terminates  
when the current position of the specified node reaches either the maximum or minimum coordinate value (STOP = 1, 2, or 3), or when the node picks up force from any contact surface (STOP = 4).

PART - Terminate solution based on rigid body (part) displacements. The analysis  
terminates when the displacement of the center of mass of the specified rigid body reaches either the maximum or minimum value (STOP = 1, 2, or 3), or when the displacement magnitude of the center of mass is exceeded (STOP = 4).

**num**: Node number (if Lab = NODE) or rigid body Part ID (if Lab = PART). (No default.)

**stop**

Criterion for stopping the solution (no default).

1 - Global X-direction.

2 - Global Y-direction.

3 - Global Z-direction.

4 - For Lab = NODE, stop the solution if contact occurs. For Lab = PART, stop the  
solution if the displacement magnitude is exceeded for the specified rigid body (use MAXC to define the displacement magnitude).

**maxc**: Maximum (most positive) coordinate value (Lab = NODE) or displacement (Lab = PART). MAXC defaults to 1.0e21

**minc**: Minimum (most negative) coordinate value (Lab = NODE) or displacement (Lab = PART). MINC defaults to -1.0e21.

## Notes

You may specify multiple termination criteria using EDTERM; the solution will terminate when any one of the criteria is satisfied, or when the solution end time (specified on the TIME command) is reached.

In an explicit dynamic small restart analysis (EDSTART,2) or full restart analysis (EDSTART,3), the termination criteria set in the previous analysis (the original analysis or the previous restart) are carried over to the restart. If the previous analysis terminated due to one of these criteria, that specific criterion must be modified so that it will not cause the restart to terminate prematurely. In particular, if a termination condition based on nodal contact (Lab = NODE, STOP = 4) is satisfied, this condition must be deleted and replaced with a condition based on nodal coordinates for that same node. (If a condition based on nodal coordinates already exists for that node, the replacement is not necessary.) In the restart, the number of termination criteria specified using EDTERM cannot exceed a maximum of 10 or the number specified in the original analysis.

Note that the termination criteria set by EDTERM are not active during dynamic relaxation (EDDRELAX).

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.

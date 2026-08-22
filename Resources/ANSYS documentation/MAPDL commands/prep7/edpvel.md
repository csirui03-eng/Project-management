---
apdl: "EDPVEL"
method: edpvel
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edpvel
generated: 2026-08-22
tags: [mapdl-command]
---

# EDPVEL

PyMAPDL: `mapdl.edpvel(option='', pid='', vx='', vy='', vz='', omegax='', omegay='', omegaz='', xc='', yc='', zc='', angx='', angy='', angz='', **kwargs)`

Applies initial velocities to parts or part assemblies in an explicit

dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

VGEN - Define initial velocities for the part or part assembly based on translational  
velocities (relative to global Cartesian) and the rotational velocity about an arbitrary axis. For this option, use the fields VX, VY, VZ to specify the translational velocities, and use OMEGAX, XC, YC, ZC, ANGX, ANGY, ANGZ to specify the rotational velocity and the axis of rotation.

VELO - Define initial velocity for the part or part assembly based on translational  
velocities and nodal rotational velocities input relative to the global Cartesian axes. For this option, use the following fields to define the initial velocity: VX, VY, VZ, OMEGAX, OMEGAY, OMEGAZ.

LIST - List initial velocity for the part or part assembly specified by PID. If PID is  
blank, all initial velocities defined on parts and part assemblies are listed. Remaining fields are ignored for this option.

DELE - Delete initial velocity defined for the part or part assembly specified by PID.  
If PID is blank, all initial velocities defined on parts and part assemblies are deleted. Remaining fields are ignored for this option.

**pid**: Part ID or part assembly ID to which the initial velocity is to be applied. The part or assembly ID must be defined (EDPART or EDASMP) before issuing this command.

**vx**: Initial velocity in X direction. Defaults to 0.

**vy**: Initial velocity in Y direction. Defaults to 0.

**vz**: Initial velocity in Z direction. Defaults to 0.

**omegax**: For Option = VGEN, OMEGAX is the initial rotational velocity of the part or part assembly about the specified rotational axis. For Option = VELO, OMEGAX is the initial nodal rotational velocity about the X-axis. OMEGAX defaults to 0.

**omegay**: Initial nodal rotational velocity about the Y-axis (used only if Option = VELO). Defaults to 0.

**omegaz**: Initial nodal rotational velocity about the Z-axis (used only if Option = VELO). Defaults to 0.

## Notes

You cannot mix the two methods of initial velocity input (Option = VELO and Option = VGEN) in the same analysis. You must use only one method for all initial velocity definitions.

The VGEN and VELO methods differ in how the rotational velocity is defined. Use Option = VGEN to input the initial velocities of a rotating part or part assembly. Use Option = VELO to apply the rotations directly to the nodes' rotation degrees of freedom. Since only shell and beam elements have rotation degrees of freedom, the rotations input with Option = VELO are only applicable to SHELL163 and BEAM161 elements. The rotational velocities input with Option = VELO are ignored for nodes not having rotational degrees of freedom (such as nodes attached to a SOLID164 or SOLID168 element).

It is normally acceptable to mix nodes belonging to deformable bodies and rigid bodies in the part assembly used in an initial velocity definition. However, when defining initial velocities in an implicit- to-explicit sequential solution, this is not an acceptable practice. In order for the initial velocities to be defined correctly in this type of analysis, you must define the initial velocities on the deformable body nodes separately from the initial velocities on the rigid body nodes.

Issuing the EDPVEL command again for the same part or part assembly (PID) will overwrite previous initial velocities defined for that part or part assembly.

To set the initial velocities to zero, issue the EDPVEL command with only the Option (use VELO or VGEN) and PID fields specified.

In a small restart analysis (EDSTART,2), you can only use the Option = VELO method to change initial velocities. When used in a small restart, the command EDPVEL,VELO changes the velocity of the specified part or part assembly. If you don't change the velocity of the parts and assemblies, their velocity at the beginning of the restart will be the same as the velocity at the end of the previous analysis.

Except for the LIST option, the EDPVEL command is not supported in a full restart analysis (EDSTART,3). You can list initial velocities defined in the previous analysis with the command EDPVEL,LIST. However, you cannot change initial velocities for parts that existed in the previous analysis; their velocity at the beginning of the analysis will be the same as the velocity at the end of the previous analysis. In addition, you cannot define initial velocities for any parts that are added in the full restart; the velocity of new parts will be zero.

To apply initial velocities to node components or nodes, use the EDVEL command.

You can use EDPVEL and EDVEL in the same analysis. If a node or node component input on the EDVEL command shares common nodes with a part or part assembly input on the EDPVEL command, the initial velocities defined on the common nodes will be determined by the last command input.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.

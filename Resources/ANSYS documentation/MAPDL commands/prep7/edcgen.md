---
apdl: "EDCGEN"
method: edcgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcgen
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCGEN

PyMAPDL: `mapdl.edcgen(option='', cont='', targ='', fs='', fd='', dc='', vc='', vdc='', v1='', v2='', v3='', v4='', btime='', dtime='', boxid1='', boxid2='', **kwargs)`

Specifies contact parameters for an explicit dynamics analysis.

## Parameters

**option**

Label identifying the contact behavior (dictates the meaning of V1 through V4).

AG - Automatic general contact.

ANTS - Automatic nodes-to-surface contact.

ASSC - Automatic single surface contact.

ASS2D - Automatic 2-D single surface contact.

ASTS - Automatic surface-to-surface contact.

DRAWBEAD - Drawbead contact

ENTS - Eroding nodes-to-surface contact.

ESS - Eroding single surface contact.

ESTS - Eroding surface-to-surface contact.

FNTS - Forming nodes-to-surface contact.

FOSS - Forming one way surface-to-surface contact.

FSTS - Forming surface-to-surface contact.

NTS - Nodes-to-surface contact.

OSTS - One way surface-to-surface contact.

RNTR - Rigid nodes to rigid body contact.

ROTR - Rigid body to rigid body (one way) contact.

SE - Single edge contact.

SS - Single surface contact.

STS - Surface-to-surface contact.

TDNS - Tied nodes-to-surface contact.

TSES - Tied shell edge-to-surface contact.

TDSS - Tied surface-to-surface contact.

TNTS - Tiebreak nodes-to-surface contact

TSTS - Tiebreak surface-to-surface contact.

**cont**: Contact surface identified by a component name \[CM\] , a part ID number \[EDPART\], or an assembly ID number \[EDASMP\]. If a component name is input, the component must contain nodes that represent the contact surface (assemblies are not valid for a component name). Alternatively, a part number may be input that identifies a group of elements as the contact surface, or an assembly number may be input containing a maximum of 16 parts. The assembly ID number must be greater than the highest number used for the part ID. Cont is not required for automatic general contact, single edge contact, and single surface contact options (Option = AG, SE, ASSC, ESS, and SS). For automatic 2-D single surface contact (ASS2D), Cont must be defined as a part assembly. For eroding node-to-surface contact (ENTS), Cont must be defined as a nodal component. For eroding single surface contact (ESS) and eroding surface-to-surface contact (ESTS), Cont must be defined as a part ID or part assembly.

**targ**: Target surface identified by a component name \[CM\] , a part ID number \[EDPART\], or an assembly ID number \[EDASMP\]. If a component name is input, the component must contain nodes that represent the target surface (assemblies are not valid for a component name). Alternatively, a part number may be input that identifies a group of elements as the target surface, or an assembly number may be input containing a maximum of 16 parts. The assembly ID number must be greater than the highest number used for the part ID. Targ is not defined for automatic general contact, single edge contact, automatic single surface contact, eroding single surface contact, single surface contact, and automatic 2-D single surface contact options (Option = AG, SE, ASSC, ESS, SS, and ASS2D). For eroding node-to-surface contact (ENTS) and eroding surface-to-surface contact (ESTS), Targ must be defined as a part ID or part assembly.

**fs**: Static friction coefficient (defaults to 0).

**fd**: Dynamic friction coefficient (defaults to 0).

**dc**: Exponential decay coefficient (defaults to 0).

**vc**: Coefficient for viscous friction (defaults to 0).

**vdc**: Viscous damping coefficient in percent of critical damping (defaults to 0).

**v1, v2, v3, v4**

Additional input for drawbead, eroding, rigid, and tiebreak contact. The meanings of V1-V4 will vary, depending on Option. See the table below for V1-V4 definitions.

V1 - Load curve ID giving the bending component of the restraining force per unit  
draw bead length as a function of draw bead displacement. V1 must be specified.

V2 - Load curve ID giving the normal force per unit draw bead length as a function  
of draw bead displacement. V2 is optional.

V3 - Draw bead depth.

V4 - Number of equally spaced integration points along the draw bead (default = 0,  
in which case ANSYS LS-DYNA calculates this value based on the size of the elements that interact with the draw bead).

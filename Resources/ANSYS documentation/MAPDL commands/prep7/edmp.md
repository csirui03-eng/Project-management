---
apdl: "EDMP"
method: edmp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edmp
generated: 2026-08-22
tags: [mapdl-command]
---

# EDMP

PyMAPDL: `mapdl.edmp(lab='', mat='', val1='', val2='', val3='', val4='', val5='', val6='', **kwargs)`

Defines material properties for an explicit dynamics analysis.

## Parameters

**lab**

Valid material property label. Applicable labels are listed under "Material Properties" in the input table for each explicit dynamics element type in the Element Reference.

HGLS - Hourglass and bulk viscosity properties (valid for PLANE162, SHELL163, SOLID164  
using reduced integration, and SOLID168). VAL1 through VAL6 are also used. For those elements using full integration, HGLS is not applicable and the input has no effect.

RIGID - Rigid body constraint (valid for LINK160, BEAM161, PLANE162, SHELL163,  
SOLID164, and SOLID168). VAL1 and VAL2 are also used.

CABLE - Cable properties (valid for LINK167). VAL1 is optional input (see Notes).

ORTHO - Defines a material coordinate system for the orthotropic material model (valid  
for PLANE162, SHELL163, SOLID164, and SOLID168) or the anisotropic material model (valid for SOLID164 and SOLID168). VAL1 is also used.

FLUID - Fluid properties (valid for PLANE162, SOLID164, and SOLID168). VAL1 is optional  
input (see Notes).

**mat**: Material reference number (defaults to the current MAT setting on MAT command).

**val1, val2, val3, . . . , val6**

Additional input for specified Lab material property. The meaning of VAL1 through VAL6 will vary, depending on Lab. See the table below for VAL1 through VAL6 definitions.

VAL1 - Hourglass control type. For solid elements (PLANE162, SOLID164, and SOLID168),  
5 options are available. For quadrilateral shell and membrane elements (SHELL163) with reduced integration, the hourglass control is based on the formulation of Belytschko and Tsay; i.e., options 1-3 are identical and options 4-5 are identical.

0, 1 - Standard LS-DYNA viscous form (default).

2 - Flanagan-Belytschko viscous form.

3 - Flanagan-Belytschko viscous form with exact volume integration for solid  
elements.

4 - Flanagan-Belytschko stiffness form.

5 - Flanagan-Belytschko stiffness form with exact volume integration for solid  
elements.

VAL2 - Hourglass coefficient. (Defaults to 0.1.) Values greater than 0.15 may cause  
instabilities. The recommended default applies to all options. The stiffness forms can stiffen the response (especially if deformations are large) and, therefore, should be used with care. For the shell and membrane elements, the value input for VAL1 is the membrane hourglass coefficient. VAL5 and VAL6 can also be input, but generally VAL2 = VAL5 = VAL6 is adequate.

VAL3 - Quadratic bulk viscosity coefficient. (Defaults to 1.5.)

VAL4 - Linear bulk viscosity coefficient. (Defaults to 0.06.)

VAL5 - Hourglass coefficient for shell bending. (Defaults to VAL2.)

VAL6 - Hourglass coefficient for shell warping. (Defaults to VAL2.)

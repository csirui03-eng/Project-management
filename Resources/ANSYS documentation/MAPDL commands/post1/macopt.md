---
apdl: "MACOPT"
method: macopt
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.macopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MACOPT

PyMAPDL: `mapdl.macopt(option='', value1='', value2='', value3='', **kwargs)`

Specifies modal assurance criterion (MAC) or frequency response function (FRF) correlation criteria calculation options for [[rstmac|RSTMAC]].

**Command default:** If **MACOPT** is not issued prior to [[rstmac|RSTMAC]], node matching based on location is used by default in MAC calculations performed by [[rstmac|RSTMAC]]. Unless otherwise specified, an absolute tolerance (ABSTOLN) value of 0.01 is used for the node matching.

## Parameters

**option**, **value1**, **value2**, **value3**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MACOPT.html) for further information.

## Notes

The [[rstmac|RSTMAC]] command calculates the MAC or FRF criteria values based on the options specified via **MACOPT**. The **MACOPT** command must be issued before the [[rstmac|RSTMAC]] command. These commands enable you to compare nodal solutions from two results files ( `.rst` or `.rstp` ) or from one results file and one Universal Format file ( `.unv` ). Multiple **MACOPT** commands can be issued to specify which results are compared and how.

As listed in the table above, model solutions can be compared using three different mehtods: matching nodes based on location, matching nodes based on node number, or by node mapping and solution interpolation.

When node mapping and solution interpolation is performed ( `Option` = NODMAP), the following applies:

- `File1` on [[rstmac|RSTMAC]] must correspond to a model meshed in solid and/or shell elements. Other types of elements can be present, but the node mapping is not performed for these elements.
- You should only compare solutions of models having the same dimension (both models are 2D or both models are 3D). Comparing models with different dimensions may lead to incorrect results if the solution at mapped/matched nodes is not representative of the global solution.
- Interpolation is performed on UX, UY, and UZ degrees of freedom.

Node pair MAC computation ( `Option` = NMAC) is only supported when a matching procedure is used and a specific substep number is requested for each solution ( `Sbstep1`, `Sbstep2` on [[rstmac|RSTMAC]] command).

Non-structural degrees of freedom in coupled-field analyses are supported for the matching methods ( `Option` = ABSTOLN or NUMMATCH). Multiple **MACOPT**, DOF commands can be issued consecutively to combine different degrees of freedom.

The FRF option is not compatible with any MAC calculation options (DOF, NMAC and KEYMASS) and can only be used with node matching procedures.

**Example Usage**

For a detailed discussion on using **MACOPT** with examples, see [Comparing Nodal Solutions From Two Models or From One Model and Experimental Data (RSTMAC)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MACOPT.html

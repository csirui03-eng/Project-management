---
apdl: "SE"
method: se
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.superelements.Superelements.se
generated: 2026-08-22
tags: [mapdl-command]
---

# SE

PyMAPDL: `mapdl.se(file='', toler='', nstartvn='', **kwargs)`

Defines a superelement.

## Parameters

**file**: The name (case sensitive) of the file containing the original superelement matrix created by the generation pass ( `Sename.SUB` ). The default is the current Jobname.

**toler**: Tolerance used to determine if use pass nodes are noncoincident with master nodes having the same node numbers. Defaults to 0.0001. Use pass nodes will always be replaced by master nodes of the same node number. However, if a use pass node is more than `TOLER` away from the corresponding master node, a warning is generated.

**nstartvn**: Node number to be assigned to the first virtual node created to store the generalized coordinates in a component mode synthesis analysis. See [[se#Notes|SE]] for more information.

## Notes

Defines a superelement by reading in the superelement matrices and master nodes from the superelement matrix file. The matrix file ( `File.SUB` ) must be available from the substructure generation pass. The proper element type ( `MATRIX50` ) must be active ( [[type|TYPE]] ) for this command. A scratch file called `File.SORD` showing the superelement names and their corresponding element numbers is also written.

`nStartVN` should be chosen so as to offset the virtual node numbers from the other node numbers used in the model. Otherwise, `nStartVN` is internally set by the program to fulfill that condition. The node number defined through `nStartVN` is considered only if applied on the first issued **SE** command. `nStartVN` can also be defined during the generation pass using the [[cmsopt|CMSOPT]] command. If `nStartVN` is defined on both [[cmsopt|CMSOPT]] and **SE** commands, the larger number prevails.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SE.html

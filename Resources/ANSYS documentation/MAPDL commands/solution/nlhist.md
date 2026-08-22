---
apdl: "NLHIST"
method: nlhist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nlhist
generated: 2026-08-22
tags: [mapdl-command]
---

# NLHIST

PyMAPDL: `mapdl.nlhist(key='', name='', item='', comp='', node='', elem='', shell='', layer='', stop_value='', stop_cond='', **kwargs)`

Specify results items to track during solution.

## Parameters

**key**

Specifies the command operation:

- `NSOL` - Nodal solution data.
- `ESOL` - Element nodal data.
- `PAIR` - Contact data (for pair-based contact).
- `GCN` - Contact data (for general contact).
- `RSEC` - [Result section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_resultsec.html#) data.
- `STAT` - Displays a list of items to track.
- `OFF or 0` - Deactivates tracking of all variables. This value is the default.
- `ON or 1` - Activates tracking of all variables. Tracking also activates whenever any specification changes.
- `DEL` - Removes the specified variable from the set of result items to track. If `Name` = ALL (default), all specifications are removed.

**name**: The 32-character user-specified name.

**item**, **comp**: Predetermined output item and component label for valid elements. See the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) for more information.

**node**

Number identifying one of the following:

- Valid node number (if `Key` = NSOL or ESOL).
- Valid real constant set number identifying a contact pair (if `Key` = PAIR).
- Valid section ID number identifying a surface of a general contact definition (if `Key` = GCN).

\* Valid real constant set number identifying a result section (if `Key` = RSEC).  
`NODE` is required input when `Key` = NSOL, ESOL, PAIR, GCN, or RSEC.

**elem**: Valid element number for element results. Used for ESOL items. If `ELEM` is specified, then a node number that belongs to the element must also be specified in the `NODE` field.

**shell**: Valid labels are TOP, MID or BOT. This field can specify the location on shell elements for which to retrieve data. Used only for element nodal data (ESOL).

**layer**: Layer number (for layered elements only). Used only for element nodal data (ESOL).

**stop_value**: Critical value of the tracked variable. This value is used to determine if the analysis should be terminated.

**stop_cond**

Specifies the conditional relationship between the variable being tracked and the `STOP_VALUE` upon which the analysis will be terminated:

- `-1` - Terminate the analysis when the tracked variable is less than or equal to `STOP_VALUE`.
- `0` - Terminate the analysis when the tracked variable equals `STOP_VALUE`.
- `1` - Terminate the analysis when the tracked variable is greater than or equal to `STOP_VALUE`.

## Notes

The **NLHIST** command is a nonlinear diagnostics tool that enables you to monitor diagnostics results of interest in real time during a solution.

You can track a maximum of 50 variables during solution. The specified result quantities are written to the file `Jobname.nlh`. Nodal results and contact results are written for every converged substep (irrespective of the [[outres|OUTRES]] command setting), while element results are written only at time points specified via the [[outres|OUTRES]] command. Result section data is written only at time points specified via the [[outpr|OUTPR]],RSO, `Freq` command.

For time points where element results data is not available, a very small number is written instead. If the conditions for contact to be established are not satisfied, 0.0 will be written for contact results.

Results tracking is available for:

- nonlinear structural analyses (static or transient)
- nonlinear steady-state thermal analyses
- transient thermal analyses (linear or nonlinear)
- nonlinear coupled structural-thermal analyses (static or transient)

All results are tracked in the Solution Coordinate System (that is, nodal results are in the nodal coordinate system and element results are in the element coordinate system).

Contact results can be tracked for elements `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ; they cannot be tracked for `CONTA178`.

[Result section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_resultsec.html#) data can be tracked for elements `CONTA172` and `CONTA174`.

When contact results ( `Key` = PAIR or GCN) or result section data ( `Key` = RSEC) are tracked, the user-specified name ( `Name` argument) is used to create a user-defined parameter. This enables you to monitor the parameter during solution. As an example, you can use a named parameter to easily convert the contact stiffness units from FORCE/LENGTH <sup>3</sup> to FORCE/LENGTH based on the initial contact area CAREA. Be sure to specify `Name` using the [APDL parameter naming convention](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/Hlp_P_APDL3_2.html#apdlhidparmtlm8599).

The `STOP_VALUE` and `STOP_COND` arguments enable you to automatically terminate the analysis when a desired value for a tracked contact result or section result has been reached. This capability is only available for contact variables ( `Key` = PAIR or GCN) and result section variables ( `Key` = RSEC ).

The `Jobname.nlh` file is an ASCII file that lists each time point at which a converged solution occurs along with the values of the relevant result quantities.

The GUI option Solution\> Results tracking provides an interface to define the result items to be tracked. The GUI also allows you to graph one or more variables against time or against other variables during solution. You can use the interface to graph or list variables from any `.nlh` file generated by Mechanical APDL.

You can also track results during batch runs. Either access the [launcher](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/install_misc/launcherhelp.html#laumenuopts) and select `Run Results Tracker Utility` from the Tools menu, or type `nlhist232` at the command line. Use the supplied file browser to navigate to your `Jobname.nlh` file, and click on it to invoke the tracking utility. You can use this utility to read the file at any time, even after the solution is complete (the data in the file must be formatted correctly).

### NLHIST - Valid NSOL Item and Component Labels

| Item | Comp     | Description                                  |
|------|----------|----------------------------------------------|
| U    | X, Y, Z  | X, Y, or Z structural displacement.          |
| ROT  | X, Y, Z  | X, Y, or Z structural rotation.              |
| F    | X, Y, Z  | X, Y, or Z structural reaction force.        |
| M    | X, Y, Z  | X, Y, or Z structural reaction moment.       |
| TEMP | -        | Temperature.                                 |
| TEMP | MAX, MIN | Maximum or minimum temperature in the model. |
| HEAT | -        | Reaction heat flow.                          |

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3,. .., TTOP instead of TEMP.

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels HBOT, HE2, HE3,. .., HTOP instead of HEAT.

### NLHIST - Valid ESOL Item and Component Labels

| Item | Comp                | Description                                   |
|------|---------------------|-----------------------------------------------|
| S    | X, Y, Z, XY, YZ, XZ | Component stress.                             |
| "    | 1, 2, 3             | Principal stress.                             |
| "    | INT                 | Stress intensity.                             |
| "    | EQV                 | Equivalent stress.                            |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain.                     |
| "    | 1, 2, 3             | Principal elastic strain.                     |
| "    | INT                 | Elastic strain intensity.                     |
| "    | EQV                 | Elastic equivalent strain.                    |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain.                     |
| "    | 1, 2, 3             | Principal plastic strain.                     |
| "    | INT                 | Plastic strain intensity.                     |
| "    | EQV                 | Plastic equivalent strain.                    |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain.                       |
| "    | 1, 2, 3             | Principal creep strain.                       |
| "    | INT                 | Creep strain intensity.                       |
| "    | EQV                 | Creep equivalent strain.                      |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain.                     |
| "    | 1, 2, 3             | Principal thermal strain.                     |
| "    | INT                 | Thermal strain intensity.                     |
| "    | EQV                 | Thermal equivalent strain.                    |
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain.                   |
| "    | 1, 2, 3             | Principal diffusion strain.                   |
| "    | INT                 | Diffusion strain intensity.                   |
| "    | EQV                 | Diffusion equivalent strain.                  |
| NL   | SEPL                | Equivalent stress (from stress-strain curve). |
| "    | SRAT                | Stress state ratio.                           |
| "    | HPRES               | Hydrostatic pressure.                         |
| "    | EPEQ                | Accumulated equivalent plastic strain.        |
| "    | CREQ                | Accumulated equivalent creep strain.          |
| "    | PSV                 | Plastic state variable.                       |
| "    | PLWK                | Plastic work/volume.                          |
| TG   | X, Y, Z, SUM        | Component thermal gradient or vector sum.     |
| TF   | X, Y, Z, SUM        | Component thermal flux or vector sum.         |

ETABLE items are not supported for [[esol|ESOL]] items.

PAIR solution quantities are output on a per contact pair basis. GCN solution quantities are output on a “per general contact section” basis. (See [Comparison of Pair-Based Contact and General Contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_comppairgen.html#gcfeatnotsup) `Jobname.nlh` file represent a minimum or a maximum over the associated contact pair or general contact surface, as detailed in the table below.

### NLHIST - Valid Contact (PAIR or GCN) Item and Component Labels

| Item | Comp | Description |
|----|----|----|
| CONT | ELCN | If \>0, number of contact elements in contact. Other values are interpreted as follows: \* 0 indicates the contact pair (or GCN surface) is in near-field contact status. \* -1 indicates the contact pair (or GCN surface) is in far-field contact status. \* -2 indicates that the contact pair (or GCN surface) is inactive ( symmetric to asymmetric contact ). |
| " | ELST | Number of contact elements in sticking contact status |
| " | CNOS | Maximum chattering level |
| " | PENE | Maximum penetration (or minimum gap) |
| " | CLGP | Maximum geometric gap |
| " | SLID | Maximum total sliding distance (algebraic sum) |
| " | SLMX | Maximum total sliding distance for closed contact in the current substep |
| " | ESLI | Maximum elastic slip distance |
| " | KNMX | Maximum normal contact stiffness |
| " | KTMX | Maximum tangential contact stiffness |
| " | KNMN | Minimum normal contact stiffness |
| " | KTMN | Minimum tangential contact stiffness |
| " | PINB | Maximum pinball radius |
| " | PRES | Maximum contact pressure |
| " | SFRI | Maximum frictional stress |
| " | CNDP | Average contact depth |
| " | CLPE | Maximum geometric penetration |
| " | LGPE | Number of contact points having too much penetration |
| " | CAREA | Contacting area |
| " | NDMP | Maximum contact damping pressure |
| " | TDMP | Maximum tangential contact damping stress |
| " | GSMX | Maximum total sliding distance ( GSLID ), including near-field |
| " | GSMN | Minimum total sliding distance ( GSLID ), including near-field |
| " | FPSC | Maximum normal fluid penetration pressure on contact surface |
| " | FPST | Maximum normal fluid penetration pressure on target surface |
| " | WEAR | Total volume lost due to wear for the contact pair (not available for general contact, `Key` = GCN ) |
| " | CTEN | Total strain energy due to contact constraint |
| " | CFEN | Total frictional dissipation energy |
| " | CDEN | Total contact stabilization energy |
| " | CFNX | Total force due to contact pressure - X component |
| " | CFNY | Total force due to contact pressure - Y component |
| " | CFNZ | Total force due to contact pressure - Z component |
| " | CFSX | Total force due to tangential stress - X component |
| " | CFSY | Total force due to tangential stress - Y component |
| " | CFSZ | Total force due to tangential stress - Z component |
| " | CTRQ | Maximum torque in an axisymmetric analysis with MU = 1.0 |
| " | LGSL | Number of contact points having too much sliding for small sliding contact |
| " | NORM | Pair-based force convergence norm |
| " | CRIT | Pair-based force convergence criterion |
| " | FPTC | Maximum tangential fluid penetration pressure on contact surface |
| " | FPTT | Maximum tangential fluid penetration pressure on target surface |

For PENE, a positive value indicates a penetration, and a negative value indicates a gap. If the contact pair (or GCN surface) has a far-field contact status, penetration and gap are not available, and the value stored for PENE is the current pinball radius.

The pair-based dissipation energy (CFEN) and stabilization energy (CDEN) do not include contributions from contact elements that are in far-field. The pair-based strain energy (CTEN) does not include the frictional dissipation energy and stabilization energy; it only contains an elastic recovery energy when the contact status changes from closed to open.

The program uses a default tolerance value of 0.1 to calculate the pair-based force convergence norm and pair-based force convergence criterion. This is not a check for local convergence. It is for monitoring purposes only and is useful for nonlinear contact diagnostics.

If the specified contact pair is a [rigid surface or force-distributed constraint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_surfcon.html#strbeamso1703) that includes stress stiffening effects, this quantity represents a total constraint force or moment at the pilot node as shown below:

(table not available in the PyMAPDL source, see the Ansys help page)

For the case of 2D axisymmetric with torsion ( `CONTA172` with a ROTY DOF), CFNZ and CFSZ represent moments along the Y direction.

### NLHIST - Valid Result Section (RSEC) Item and Component Labels

| Item | Comp | Description                 |
|------|------|-----------------------------|
| REST | SECF | Total section force         |
| "    | SECM | Total section moment        |
| "    | AXST | Section axial stress        |
| "    | BDST | Section bending stress      |
| "    | SPTX | Section center X coordinate |
| "    | SPTY | Section center Y coordinate |
| "    | SPTZ | Section center Z coordinate |
| "    | THXY | Rotation about local z      |
| "    | THYZ | Rotation about local x      |
| "    | THZX | Rotation about local y      |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLHIST.html

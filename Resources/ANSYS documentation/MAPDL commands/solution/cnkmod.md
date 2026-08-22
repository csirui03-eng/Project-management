---
apdl: "CNKMOD"
method: cnkmod
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cnkmod
generated: 2026-08-22
tags: [mapdl-command]
---

# CNKMOD

PyMAPDL: `mapdl.cnkmod(itype='', knum='', value='', **kwargs)`

Modifies contact element key options.

## Parameters

**itype**: Contact element type number as defined on the [[et|ET]] command.

**knum**: Number of the KEYOPT to be modified (KEYOPT( `KNUM` )).

**value**: Value to be assigned to the KEYOPT.

## Notes

The **CNKMOD** command has the same syntax as the [[keyopt|KEYOPT]] command. However, it is valid only in the SOLUTION processor. The command can be used to modify certain contact element KEYOPT values between load steps in any analysis, including restarts and [linear perturbation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html) analyses, as shown in the table below.

(table not available in the PyMAPDL source, see the Ansys help page)

In a [multiframe restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#BASmultprocmap52199), **CNKMOD** must be issued again during each subsequent restart run.

**Modifying KEYOPT(12)**

A common use for the **CNKMOD** command is to modify contact interface behavior between load steps in a restart analysis, a linear perturbation analysis, or other types of analyses. This enables you to control the contact status locally per contact pair. The key options that control contact interface behavior are: KEYOPT(12) of `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ; and KEYOPT(10) of `CONTA178`.

You can change KEYOPT(12) to any value. For example, you can change from standard contact to bonded contact or vice-versa. If an open gap exists at the end of the previous load step and the contact status is adjusted to sliding or sticking due to a bonded or no-separation contact behavior definition, the program considers it as near-field contact when executing **CNKMOD** in the subsequent load steps.

In a [linear perturbation analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html), the **CNKMOD** command adjusts the contact status from the linear perturbation base analysis (at the point of restart) as described in the table below. It enables you to take points in the base analysis that are near contact (within the pinball region) and modify them to be treated as in- contact in the perturbation analysis (see the "1 - near-field" row with KEYOPT(12) values set to 4 or 5). You can also take points that are sliding in the base analysis and treat them as sticking in the perturbation analysis, irrespective of the MU value (see the "2 - sliding" row with KEYOPT(12) values set to 1,3, 5, or 6).

### Contact Status Adjusted in Linear Perturbation Analysis via CNKMOD

|  |  |  |
|----|----|----|
| **Contact Status from the Base Analysis Solution at the Restart Point** | *\*CNKMOD,*\* `ITYPE` ,12, `Value` |  |
|  | KEYOPT(12) Value | Adjusted Contact Status |
| 0 - far-field | any | 0 - far-field |
| 1 - near-field | 0, 1, 2, 3, 6 | 1 - near-field |
|  | 4 | 1 - near-field (if outside of the adjusted pinball region) |
|  |  | 2 - sliding (if inside of the adjusted pinball region) |
|  | 5 | 1 - near-field (if outside of the adjusted pinball region) |
|  |  | 3 - sticking (if inside of the adjusted pinball region) |
| 2 - sliding | 0, 2, 4 | 2 - sliding |
|  | 1, 3, 5, 6 | 3 - sticking |
| 3 - sticking | any | 3 - sticking |

If an open gap exists at the end of the previous load step and the contact status is adjusted as sliding or sticking due to a bonded or no-separation contact behavior definition, the program considers it a near-field contact when executing **CNKMOD** in the subsequent load steps.

In the linear perturbation analysis procedure, contact status can also be controlled or modified via the [[perturb|PERTURB]] command. The contact status always follows local controls defined by the **CNKMOD** command first, and is then adjusted by the global sticking or bonded setting ( `ContKey` = STICKING or BONDED) on the [[perturb|PERTURB]] command.

**Modifying KEYOPT(3)**

Another use for the **CNKMOD** command is to change the units of normal contact stiffness (contact element real constant FKN) in a [linear perturbation modal analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html) that is used to model [brake squeal](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRmodanexamp.html#strlinearnonpresmodan). For contact elements `CONTA172` and `CONTA174`, KEYOPT(3) controls the units of normal contact stiffness. You can issue the command **CNKMOD**, `ITYPE`,3,1 during the first phase of the linear perturbation analysis in order to change the units of normal contact stiffness from FORCE/LENGTH <sup>3</sup> (in the base analysis) to FORCE/LENGTH. Note that KEYOPT(3) = 1 is valid only when a penalty-based algorithm is used (KEYOPT(2) = 0 or 1) and the absolute normal contact stiffness value is explicitly specified (that is, a negative value input for real constant FKN).

**Modifying KEYOPT(15)**

KEYOPT(15) controls the effect of contact stabilization damping for contact elements `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177`. You can use **CNKMOD** to activate or deactivate the contact stabilization damping between load steps. For example, the command **CNKMOD**, `ITYPE`,15,1 deactivates the contact stabilization damping.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CNKMOD.html

---
apdl: "NROPT"
method: nropt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nropt
generated: 2026-08-22
tags: [mapdl-command]
---

# NROPT

PyMAPDL: `mapdl.nropt(option1='', option2='', optval='', **kwargs)`

Specifies the Newton-Raphson options in a static or full transient analysis.

## Parameters

**option1**

Option key:

- `AUTO` - Let the program choose the option (default).
- `FULL` - Use full Newton-Raphson.
- `MODI` - Use modified Newton-Raphson.
- `INIT` - Use the previously computed matrix (initial-stiffness).
- `UNSYM` - Use full Newton-Raphson with unsymmetric matrices of elements where the unsymmetric option exists.

**option2**

Option key:

- `CRPL` - When applicable in a static creep analysis, activates modified Newton-Raphson with a creep-ratio limit. Valid only when `Option1` = AUTO.

**optval**

If `Option2` is blank, `Optval` is the Adaptive Descent Key ( `Adptky` ):

- `ON` - Use adaptive descent (default if frictional contact exists). Explicit ON is valid only if `Option` = FULL.
- `OFF` - Do not use adaptive descent (default in all other cases).

If `Option2` = CRPL, `Optval` is the creep ratio limit:

- `CRLIMIT` - The creep ratio limit for use with the modified Newton-Raphson procedure. Valid only when `Option1` = AUTO (default) and `Option2` = CRPL. Typically, this value should not exceed 0.15 in order to make the modified Newton-Raphson solution converge efficiently. For more information about the creep ratio limit, see the [[cutcontrol|CUTCONTROL]] command.

## Notes

The **NROPT** command specifies the Newton-Raphson option used to solve the nonlinear equations in a static or full transient analysis.

The automatic modified Newton-Raphson procedure with creep-ratio limit control ( **NROPT**,AUTO,CRPL, `CRLIMIT` ) applies to static creep analysis only. When the creep ratio is smaller than the value of the creep ratio limit specified, the modified Newton-Raphson procedure is used. If convergence difficulty occurs during solution, use the full Newton-Raphson procedure.

The command **NROPT**,UNSYM is also valid in a linear non-prestressed modal analysis that is used to perform a brake squeal analysis. In this special case, the command is used only to generate the unsymmetric stiffness matrix; no Newton-Raphson iterations are performed.

**NROPT**,MODI and **NROPT**,INIT are only applicable with the sparse solver ( [[eqslv|EQSLV]],SPARSE). Thermal analyses will always use full Newton-Raphson irrespective of the `Option1` value selected.

See Newton-Raphson Option in the [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html) for more information.

This command is also valid in PREP7.

**Switching Between the Symmetric and Unsymmetric Option**

Normally, switching from the symmetric Newton-Raphson option ( **NROPT**,FULL) to the unsymmetric option ( **NROPT**,UNSYM) or from the unsymmetric option to the symmetric option is allowed between load steps within the same analysis type. This is applicable to linear and nonlinear, static and full transient analyses.

Under the following circumstances, the solution could be slightly different or inaccurate if you switch from symmetric to unsymmetric or vice versa:

- The underlying elements or materials are unsymmetric by their mathematical definition, and you switch from unsymmetric to symmetric.
- You change analysis types and also switch from symmetric to unsymmetric (or vise versa) at the same time. This situation could result in failures such as data corruption or a core dump and should therefore be avoided.
- In some rare cases, switching between the symmetric and unsymmetric options can cause a system core dump when reading/writing the `.ESAV` or `.OSAV` file, and the analysis terminates. Typically, this happens when the record length of the element nonlinear saved variables cannot be altered between load steps by their mathematical definition.

If all the elements and the material are symmetric by their mathematical definition and you use the unsymmetric option, the solution accuracy is the same as the symmetric option. However, the analysis will run twice as slow as the symmetric case.

In a static or full transient linear perturbation base analysis, be aware that if the unsymmetric Newton-Raphson procedure is used, you must specify the UNSYM or DAMP eigensolver option in the downstream modal analysis, which may be more expensive than symmetric modal analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NROPT.html

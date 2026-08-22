---
apdl: "CMSOPT"
method: cmsopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cmsopt
generated: 2026-08-22
tags: [mapdl-command]
---

# CMSOPT

PyMAPDL: `mapdl.cmsopt(cmsmeth='', nmode='', freqb='', freqe='', fbddef='', fbdval='', iokey='', elcalc='', eigmeth='', nstartvn='', **kwargs)`

Specifies component mode synthesis (CMS) analysis options.

**Command default:**

Issuing the **CMSOPT** command with no arguments is invalid. You must specify at least the CMS method ( `Cmsmeth` ) and the number of modes ( `NMODE` ). In a free-interface ( `Cmsmeth` = FREE) or residual-flexible free-interface ( `Cmsmeth` = RFFB) CMS analysis, the default method for determining rigid body modes is FAUTO (automatic).

## Parameters

**cmsmeth**

The component mode synthesis [method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcms.html#pseudo_constraints_FI_CMS) to use. This value is required.

- `FIX` - Fixed-interface method.
- `FREE` - Free-interface method.
- `RFFB` - Residual-flexible free-interface method.

**nmode**: The number of normal modes extracted and used in the superelement generation. This value is required; the minimum is 1.

**freqb**

Beginning, or lower end, of frequency range of interest. This value is optional.

The program always sets this value to zero if the residual-flexible free-interface method ( `Cmsmeth` = RFFB) or the free-interface method ( `Cmsmeth` = FREE) is specified via [[resvec|RESVEC]].

**freqe**: Ending, or upper end, of frequency range of interest. This value is optional.

**fbddef**

In a free-interface ( `Cmsmeth` = FREE) or residual-flexible free-interface ( `Cmsmeth` = RFFB) CMS analysis, the method to use for defining free body modes:

- `FNUM` - The number ( `FDBVAL` ) of rigid body modes in the calculation.
- `FTOL` - Employ a specified tolerance ( `FDBVAL` ) to determine rigid body modes in the calculation.
- `FAUTO` - Automatically determine rigid body modes in the calculation. This method is the default.
- `RIGID` - If no rigid body modes exist, define your own via the [[rigid|RIGID]] command.

**fbdval**: In a free-interface CMS analysis ( `Cmsmeth` = FREE), the number of rigid body modes if `Fbddef` = FNUM (where the value is an integer from 0 through 6), or the tolerance to employ if `Fbddef` = FTOL (where the value is a positive real number representing rad/sec). This value is required only when `Fbddef` = FNUM or `Fbddef` = FTOL; otherwise, any specified value is ignored.

**iokey**

Output key to control writing of the complete transformation matrix on the `.cms` file to the `.tcms` file (FIX or FREE methods) or body properties to the `.EXB` file (FIX method).

- `CMS` - Write the complete transformation matrix of the nodal component on the `.cms` file. For more information, see.
- `TCMS` - Write the transformation matrix of the nodal component defined via [[outpr|OUTPR]] to a `.tcms` file. For more information, see.
- `EXB` - Write a body property input file ( `.EXB` file) containing the condensed substructure matrices and other body properties for use with AVL EXCITE. For more information, see [Ansys Interface to AVL EXCITE](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/substrexbcms.html)

**elcalc**

Element calculation key:

- `NO` - Do not calculate element results (default).
- `YES` - Calculate element results and write them to the `.cms` file for the expansion pass.

**eigmeth**

Mode extraction method to be used for the symmetric eigenvalue problem during the [generation pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcmssuperelem.html#usingcms_elemcalc) :

- `LANB` - Block Lanczos algorithm (default).
- `SUBS` - Subspace algorithm.
- `SNODE` - Supernode algorithm.

**nstartvn**: Node number to be assigned to the first virtual node created to store the generalized coordinates. See [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CMSOPT.html#CMSOPT.prodres) for more information.

## Notes

CMS supports damping matrix reduction when a damping matrix exists. Set the matrix generation key to 3 ( [[seopt|SEOPT]], `Sename`, `SEMATR` ) to generate and then reduce stiffness, mass, and damping matrices.

CMS does not support the [[seopt|SEOPT]],,,,,RESOLVE command. Instead, the program sets the expansion method for the expansion pass ( `EXPMTH` ) to BACKSUB.

By default, the static constraint modes are not written to the `.cms` file for the fixed- interface and free-interface methods. Issue `IOkey` = CMS to write them.

If `IOkey` = TCMS, the transformation matrix is printed out and written to the `.tcms` file when the [[outpr|OUTPR]] command is issued with `ITEM` = NSOL and `FREQ` not equal to NONE. In addition, the transformation matrix is printed out when `SEPR` is equal to 1 or 2 on [[seopt|SEOPT]]. In interactive sessions, the transformation matrix is not output if the model has more than 10 elements.

For information about the component modes stored in the `.cms` or `.tcms` file, refer to [Component Modes Storage](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcmssuperelem.html#)

If `Elcalc` = YES, the element results of the component modes included in the transformation matrix of the CMS method are calculated and written to the `.cms` file. This can significantly reduce the computation time of the. For limitations and available element results, see.

Select a `nStartVN` value to offset the virtual node numbers from the other node numbers used in the model; otherwise, the program selects `nStartVN` to fulfill that condition. In the case of multiple superelements, if `nStartVN` is defined during each generation pass, then in the use pass, the virtual nodes of all imported superelements are gathered and renumbered from the `nStartVN` value specified for the first encountered superelement (first [[se|SE]] command). `nStartVN` can also be defined in the use pass via [[se|SE]]. (If `nStartVN` is defined by both the **CMSOPT** and [[se|SE]] commands, the larger number prevails.)

For more information, see [Component Mode Synthesis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcms.html#advcmsunderstand)

This command is also valid in [[prep7|/PREP7]].

Ansys Mechanical Enterprise PrepPost Only **CMSOPT**,FIX,,,,,,EXB is supported.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMSOPT.html

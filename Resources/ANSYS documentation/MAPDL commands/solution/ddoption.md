---
apdl: "DDOPTION"
method: ddoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.ddoption
generated: 2026-08-22
tags: [mapdl-command]
---

# DDOPTION

PyMAPDL: `mapdl.ddoption(decomp='', nprocpersol='', numsolforlp='', **kwargs)`

Sets domain decomposer option for a distributed-memory parallel (DMP) solution.

**Command default:**

The optimal algorithm for domain decomposition is automatically chosen.

## Parameters

**decomp**

Controls which domain decomposition algorithm to use.

- `AUTO` - Automatically selects the optimal domain decomposition method (default).
- `MESH` - Decompose the FEA mesh.
- `FREQ` - Decompose the frequency domain for harmonic analyses.
- `CYCHI` - Decompose the harmonic indices for cyclic symmetry modal analyses.

**nprocpersol**: Number of processes to be used for mesh-based decomposition in conjunction with each frequency solution ( `Decomp` = FREQ) or harmonic index solution ( `Decomp` = CYCHI). Defaults to 1. This field is ignored when `Decomp` = MESH.

**numsolforlp**: Number of frequency or harmonic index solutions in a subsequent linear perturbation harmonic or linear perturbation cyclic modal analysis. This field is ignored when `Decomp` = MESH.

## Notes

This command controls options related to the domain decomposition algorithm used in a distributed- memory parallel (DMP) solution to split the analysis calculations into domains, with each domain being solved on a different process.

By default, the optimal domain decomposition algorithm (MESH, FREQ, or CYCHI) is automatically chosen. When FREQ (for a harmonic analysis) or CYCHI (for a cyclic symmetry modal analysis) is automatically chosen, the `NPROCPERSOL` argument is also automatically set to a value ≥ 1.

The "mesh" algorithm ( `Decomp` = MESH) divides the finite element mesh into domains. In this case, domains are effectively groups of elements, with one domain being solved on each process. This algorithm seeks to create evenly sized domains (that is, domains with equal numbers of elements) as well as to minimize the size of interfaces between the newly created domains. This algorithm can be used for all analysis types.

The "frequency" algorithm ( `Decomp` = FREQ) divides the specified frequency range for a harmonic analysis into domains. In this case, domains are effectively groups of frequency solutions, with one domain being solved on `NPROCPERSOL` processes. If there are more processes than frequency points, some processes will remain idle during the harmonic analysis solution. This algorithm seeks to create evenly sized domains. However, if the number of processes does not divide evenly into the number of frequency solutions, the efficiency of the parallel solution will be reduced. This algorithm can only be used for harmonic analyses using the auto ( [[hropt|HROPT]],AUTO), full ( [[hropt|HROPT]],FULL), or frequency-sweep ( [[hropt|HROPT]],VT) method.

The "cyclic" algorithm ( `Decomp` = CYCHI) divides the specified list of harmonic indices for a cyclic symmetry modal analysis into domains. In this case, domains are effectively groups of cyclic harmonic indices, with one domain being solved on `NPROCPERSOL` processes. If there are more processes than harmonic indices, some processes will remain idle during the cyclic model solution. This algorithm seeks to create evenly sized domains. However, if the number of processes does not divide evenly into the number of harmonic indices, the efficiency of the parallel solution will be reduced.

For the mesh algorithm (MESH), all available processes are used. This is not necessarily the case for the frequency and cyclic algorithms (FREQ and CYCHI).

`NPROCPERSOL` is only used when `Decomp` = FREQ or CYCHI. It defaults to 1, which essentially means that no mesh-based domain decomposition occurs. When `NPROCPERSOL` is defined to be greater than 1, a combination of FREQ or CYCHI decomposition and MESH decomposition is employed. As an example, consider a harmonic analysis with 50 requested frequency points ( [[nsubst|NSUBST]],50) that uses distributed processing with 100 CPU cores ( -dis -np 100). Specifying **DDOPTION**,FREQ,2 would lead to 50 parallel sets of calculations, each working on a different frequency point and using 2 cores for mesh-based domain decomposition (that is, 2 groups of elements per frequency).

**DDOPTION** must be issued prior to solving the first load step. Once the first load step is completed, this command cannot be used to change the domain decomposition method. The only exception is for analyses which use the linear perturbation procedure.

In a linear perturbation analysis, **DDOPTION** must be entered prior to the [[solve|SOLVE]],ELFORM command. In addition, the number of frequency solutions (in a subsequent harmonic analysis) or harmonic index solutions (in a subsequent cyclic modal analysis) must be input via the `NUMSOLFORLP` argument to enable proper domain decomposition to occur at the [[solve|SOLVE]],ELFORM stage of the linear perturbation analysis. For more information, see [Linear Perturbation Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html)

For more information and recommendations on how to choose the domain decomposition method, see.

For the frequency and the cyclic algorithms, solution information for the harmonic frequencies ( `Decomp` = FREQ) or cyclic harmonic indices ( `Decomp` = CYCHI) solved by the worker processes is only written to the output files for those processes ( `Jobnamen.OUT` ). See for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DDOPTION.html

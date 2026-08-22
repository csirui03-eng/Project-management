---
apdl: "STORE"
method: store
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.store
generated: 2026-08-22
tags: [mapdl-command]
---

# STORE

PyMAPDL: `mapdl.store(lab='', npts='', freq='', toler='', cluster='', **kwargs)`

Stores data in the database for the defined variables.

## Parameters

**lab**

Valid labels:

- `MERGE` - Merge data from results file for the time points in memory with the existing data using current specifications (default).

- `NEW` - Store a new set of data, replacing any previously stored data with current result file specifications and deleting any previously-calculated variables (see ).

  Variables defined using the [[ansol|ANSOL]] command are also deleted if they represent element-based results. Variables created using [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are not deleted.

- `APPEN` - Append data from results file to the existing data.

- `ALLOC` - Allocate (and zero) space for `NPTS` data points.

- `PSD` - Create a new set of frequency points for PSD calculations (replacing any previously stored data and erasing any previously calculated data).

**npts**: The number of time points (or frequency points) for storage (used only with `Lab` = ALLOC or PSD). The value may be input when using POST26 with data supplied from other than a results file. This value is automatically determined from the results file data with the NEW, APPEN, and MERGE options. For the PSD option, `NPTS` determines the resolution of the frequency vector (valid numbers are between 1 and 10, defaults to 5).

**freq**: A frequency value, or an array containing frequency values (Hz). Use [[dim|*DIM]] to define the array and enclose the array name in percent signs (for example, **STORE**,,,,`arrayname`). A default value of 1% of damping is considered for clustering around the user-input frequency values. Supported for `Lab` = PSD only.

**toler**: Tolerance to determine if a user-input frequency value ( `FREQ` ) is a duplicate and can be ignored. Two frequency values are considered duplicates if their difference is smaller than the frequency range multiplied by the tolerance. The default value is 10 <sup>-5</sup>. Supported for `Lab` = PSD and `Cluster` = YES only.

**cluster**

Key to control whether or not to consider the clustering frequencies around each of the user-input array values. Available only when a user-defined frequency array is used ( `FREQ` ).

- `YES` - Merge the clustering frequencies around both the natural frequencies and the frequency values entered in the user-defined array ( `FREQ` ) (default).
- `NO` - Do not include clustering frequencies, and use only natural frequencies and the frequencies in the user-defined array ( `FREQ` ).

## Notes

This command stores data from the results file in the database for the defined variables ( [[ansol|ANSOL]], [[nsol|NSOL]], [[esol|ESOL]], [[solu|SOLU]], [[jsol|JSOL]] ) per specification ( [[avprin|AVPRIN]], [[force|FORCE]], [[layerp26|LAYERP26]], [[shell|SHELL]] ). See [Storing the Variable](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BASP26define.html#)

The **STORE**,PSD command creates a new frequency vector (variable 1) for response PSD calculations ( [[rpsd|RPSD]] ). This command should first be issued before defining variables ( [[nsol|NSOL]], [[esol|ESOL]], [[rforce|RFORCE]] ) for which response PSD's are to be calculated.

If the frequencies in the user-defined array are relevant, turning off clustering ( `Cluster` = NO) reduces calculation costs without significant loss of accuracy. You can check the frequencies by initially issuing a default [[rpsd|RPSD]] (with clustering) to obtain a reference plot of the response.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_STORE.html

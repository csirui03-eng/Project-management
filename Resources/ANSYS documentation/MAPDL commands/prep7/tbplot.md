---
apdl: "TBPLOT"
method: tbplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbplot
generated: 2026-08-22
tags: [mapdl-command]
---

# TBPLOT

PyMAPDL: `mapdl.tbplot(lab='', mat='', tbopt='', temp='', segn='', **kwargs)`

Displays the material data table.

## Parameters

**lab**: Data table label. Valid labels are: MELAS, BKIN, BISO, BH, GASKET, and JOIN. Defaults to the active table label. For B-H data, also valid are: NB to display NU-B <sup>2</sup>, MH to display MU vs. H, and SBH, SNB, SMH to display the slopes of the corresponding data.

**mat**: Material number to be displayed (defaults to the active material).

**tbopt**

Gasket material or joint element material option to be plotted.

The following gasket material options are valid only when `Lab` = GASKET:

- `ALL` - Plots all gasket data.
- `COMP` - Plots gasket compression data only.
- `LUNL` - Plots gasket linear unloading data with compression curve.
- `NUNL` - Plots gasket nonlinear unloading data only.

The following joint element material options are valid only when Lab = JOIN:

- `JNSA` - Plots nonlinear stiffness data that is applicable to all relevant directions.
- `JNS, n` - Plots only the specified nonlinear stiffness data. The n can be 1, 4, or 6. For example, JNS4 plots only the nonlinear stiffness data specified in the local direction 4 (ROTX).
- `JNDA` - Plots nonlinear damping data that is applicable to all relevant directions.
- `JND, n` - Plots only the specified nonlinear damping data. The n can be 1, 4, or 6. For example, JND4 plots only the nonlinear damping data specified in the local direction 4 (ROTX).
- `JNFA` - Plots nonlinear hysteretic friction data that is applicable to all relevant directions.
- `JNF, n` - Plots only the specified nonlinear hysteretic friction data. The n can be 1, 4, or
  6\. For example, JNF4 plots only the nonlinear hysteretic friction data specified in local direction 4 (ROTX).

**temp**: Specific temperature at which gasket data or joint element material data will be plotted (used only when `Lab` = GASKET or JOIN). Use `TEMP` = ALL to plot gasket data or joint element material data at all temperatures.

**segn**

Segment number of plotted curve (valid only when `Lab` = GASKET):

- `NO` - Segment number is not added to plotted curve (default).
- `YES` - Segment number is added to plotted curve. This option is ignored if the number of data points in a curve exceeds 20.

## Notes

Only data for stress-strain, B-H, gasket curves, or joint element nonlinear material model curves can be displayed.

The `TBOPT` and `TEMP` values are valid only when Lab = GASKET or JOIN.

The `SEGN` value is valid only when Lab = GASKET.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBPLOT.html

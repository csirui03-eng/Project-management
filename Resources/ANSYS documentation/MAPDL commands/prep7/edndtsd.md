---
apdl: "EDNDTSD"
method: edndtsd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edndtsd
generated: 2026-08-22
tags: [mapdl-command]
---

# EDNDTSD

PyMAPDL: `mapdl.edndtsd(vect1='', vect2='', datap='', fitpt='', vect3='', vect4='', disp='', **kwargs)`

Allows smoothing of noisy data for explicit dynamics analyses and

provides a graphical representation of the data.

## Parameters

**vect1**: Name of the first vector that contains the noisy data set (i.e., independent variable). You must create and fill this vector before issuing EDNDTSD.

**vect2**: Name of the second vector that contains the dependent set of data. Must be the same length as the first vector. You must create and fill this vector before issuing EDNDTSD.

**datap**: Number of data points to be fitted, starting from the beginning of the vector. If left blank, the entire vector will be fitted. The maximum number of data points is 100,000 (or greater, depending on the memory of the computer).

**fitpt**

Curve fitting order to be used as a smooth representation of the data. This number should be less than or equal to the number of data points. However, because high order polynomial curve fitting can cause numerical difficulties, a polynomial order less than 7 is suggested. The default (blank) is one-half the number of data points or 7, which ever is less. The following values are available:

1 - Curve is the absolute average of all of the data points.

2 - Curve is the least square average of all of the data points.

3 or more - Curve is a polynomial of the order (n-1), where n is the number of data fitting  
order points.

**vect3**: Name of the vector that contains the smoothed data of the independent variable. This vector should have a length equal to or greater than the number of smoothed data points. In batch (command) mode, you must create this vector before issuing the EDNDTSD command. In interactive mode, the GUI automatically creates this vector (if it does not exist). If you do not specify a vector name, the GUI will name the vector smth_ind.

**vect4**: Name of the vector that contains the smoothed data of the dependent variable. This vector must be the same length as Vect3. In batch (command) mode, you must create this vector before issuing the EDNDTSD command. In interactive mode, the GUI automatically creates this vector (if it does not exist). If you do not specify a vector name, the GUI will name the vector smth_dep.

**disp**

Specifies how you want to display data. No default; you must specify an option.

1 - Unsmoothed data only

2 - Smoothed data only

3 - Both smoothed and unsmoothed data

## Notes

You can control the attributes of the graph using standard ANSYS controls (/GRID, /GTHK, /COLOR, etc.). If working interactively, these controls appear in this dialog box for convenience, as well as in their standard dialog boxes. You must always create Vect1 and Vect2 (using `*DIM`) and fill these vectors before smoothing the data. If you're working interactively, ANSYS automatically creates Vect3 and Vect4, but if you're working in batch (command) mode, you must create Vect3 and Vect4 (using `*DIM`) before issuing EDNDTSD. Vect3 and Vect4 are then filled automatically by ANSYS. In addition, ANSYS creates an additional TABLE type array that contains the smoothed array and the unsmoothed data to allow for plotting later with `*VPLOT`. Column 1 in this table corresponds to Vect1, column 2 to Vect2, and column 3 to Vect4. This array is named Vect3_SMOOTH, up to a limit of 32 characters. For example, if the array name is X1, the table name is X1_SMOOTH.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.

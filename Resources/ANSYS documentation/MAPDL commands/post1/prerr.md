---
apdl: "PRERR"
method: prerr
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.listing.Listing.prerr
generated: 2026-08-22
tags: [mapdl-command]
---

# PRERR

PyMAPDL: `mapdl.prerr(**kwargs)`

Prints SEPC and TEPC.

## Notes

Prints the percent error in structural energy norm (SEPC) and the thermal energy norm percent error (TEPC). Approximations of mesh discretization error associated with a solution are calculated for analyses having structural or thermal degrees of freedom.

The structural approximation is based on the energy error (which is similar in concept to the strain energy) and represents the error associated with the discrepancy between the calculated stress field and the globally continuous stress field (see [POST1 - Error Approximation Technique](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post7.html#errormagbased) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)). This discrepancy is due to the assumption in the elements that only the displacements are continuous at the nodes. The stress field is calculated from the displacements and should also be continuous, but generally is not.

Thermal analyses may use any solid and shell thermal element having only temperature degrees of freedom. The thermal approximation is based on the total heat flow dissipation and represents the error associated with the discrepancy between the calculated nodal thermal flux within an element and a continuous global thermal flux. This continuous thermal flux is calculated with the normal nodal averaging procedure.

The volume (result label VOLU) is used to calculate the energy error per element (result label SERR for the structural energy error and TERR for the thermal energy error). These energy errors, along with the appropriate energy, are then used to calculate the percent error in energy norm (SEPC for structural and TEPC for thermal). These percentages can be listed by the **PRERR** command, retrieved by the [[get|*GET]] command (with labels SEPC and TEPC) for further calculations, and shown on the displacement display ( [[pldisp|PLDISP]] ), as applicable.

For structural analyses, the maximum absolute value of nodal stress variation of any stress component for any node of an element (result item SDSG) is also calculated. Similarly, for thermal gradient components, TDSG is calculated. Minimum and maximum result bounds considering the possible effect of discretization error will be shown on contour displays ( [[plnsol|PLNSOL]] ). For shell elements, the top surface location is used to produce a meaningful percentage value. SERR, TERR, SEPC, TEPC, SDSG, and TDSG will be updated whenever the nodal stresses or fluxes are recalculated.

If the energy error is a significant portion of the total energy, then the analysis should be repeated using a finer mesh to obtain a more accurate solution. The energy error is relative from problem to problem but will converge to a zero energy error as the mesh is refined.

**The following element- and material-type limitations apply:**

- Valid with most 2D solid, 3D solid, axisymmetric solid, or 3D shell elements.
- The model should have only structural or thermal degrees of freedom.
- The analysis must be linear (for both material and geometry).
- Multi-material (for example, composite) elements are not valid.
- Transition regions from one material to another are not valid (that is, the entire model should consist of one material).
- Anisotropic materials ( [[tb|TB]],ANEL) are not considered.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRERR.html

# Boundary conditions and flags

Started 2026-08-23. Step 7 of the pipeline, the last two blocks of `double_wall.py`. Both are the same shape as everything before: select, set, done. Each has one decision in it.

## Anechoic ends

For each tube end (`y0`, `y5`): select the nodes on that line, select the uncoupled air elements, `SF,ALL,IMPD,1`, `ALLSEL`. The flag lands on the faces whose nodes are all on the end line, which is the end face of each air element there.

The decision is the division of labour. The IMPD flag says where (which faces). The MU on the air material says how much (1 is full absorption). The flag value is only 1, on. Without the flag MU does nothing anywhere. Without MU the flag absorbs nothing. Why the ends absorb at all: a real impedance tube is long, the model is 100 mm each side, so the ends have to behave like a tube that keeps going, and that is the sound not coming back.

## Rim clamps

For each wall's Y band: select the nodes at `x = r_tube`, narrow to the band, `D,ALL,UX,0` and `D,ALL,UY,0`. The silicone edge is bonded to the tube wall, so its outer rim does not move. 28 constraint entries last time: 7 nodes per rim including midsides, 2 DOFs, 2 rims.

The decision is what is not done. The air nodes on the tube wall at `x = r_tube` get nothing. For an acoustic element, no condition on a boundary means a rigid wall, zero normal velocity. Do nothing equals rigid, which is why the tube wall never appears in the script.

`finish()` leaves PREP7. The model is built.

## What is not here

The FLOW source is in `tl_sweep.py`, not in the model script, because it is a load and not the model: `F,ALL,FLOW` on the `SOURCE_L` nodes, amplitude arbitrary since TL is a ratio of two pressures from the same source. That belongs to [[8 - Solve and extract|step 8]].

## Table of methods

Methods used in the two blocks, in call order. The APDL column links to the converted command page in `Resources\ANSYS documentation`.

| Method | APDL | Does |
|---|---|---|
| `mapdl.nsel("S", "LOC", "Y", y)` | [[nsel\|NSEL]] | select nodes by location, same modes as ASEL |
| `mapdl.esel("S", "TYPE", "", 3)` | [[esel\|ESEL]] | select elements by attribute, here the uncoupled air |
| `mapdl.sf("ALL", "IMPD", 1)` | [[sf\|SF]] | impedance flag on faces whose nodes are all selected, MU on the material sets the amount |
| `mapdl.d("ALL", "UX", 0)` | [[d\|D]] | displacement constraint on the selected nodes, one DOF per call |
| `mapdl.allsel()` | [[allsel\|ALLSEL]] | select every entity again |
| `mapdl.finish()` | [[finish\|FINISH]] | leave the current processor, back to Begin level |

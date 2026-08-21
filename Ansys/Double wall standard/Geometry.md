# Geometry

Axisymmetric cross-section: X = radial, Y = tube axis, axis at X = 0.

A 50 mm radius tube, stacked bottom to top:

- 100 mm upstream air
- wall 1: 5 mm thick — MDF disc to 45 mm, silicone edge 45–50 mm
- 40 mm air gap
- wall 2: same as wall 1
- 100 mm downstream air

Seven rectangles, glued so neighbours share nodes. Each region selected by
its known location and named (`AIR_UP_A`, `W1_SOLID_A`, `W1_EDGE_A`, …);
after naming, no coordinates appear again — everything downstream uses the
names.

Still to change: split the upstream air so a source line exists ~30–50 mm
above the inlet.

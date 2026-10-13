# HW2 result provenance

All images were captured from the supplied `BezierCurve` and `MeshEdit`
renderers, using the implementation in the private HW2 code repository.
The optional capture executable reads the actual OpenGL back buffer and saves
1920 x 1280 PNGs. Camera detail views use the same mesh with a closer camera.
No images from the assignment website are used as results.

- Curve stages: custom `bzc/curve6.bzc`, t = 0.5, C enabled, E advanced from 0 to 5.
- Modified curve: point 1 changed to (0.30, 0.65), point 3 to (0.78, 0.30), t = 0.7.
- Bezier teapot: `bez/teapot.bez`, original patch tessellator and incremental
  vertex merging, vertex normals enabled, wireframe visible.
- Mesh teapot: `dae/teapot.dae`, camera azimuth 0.65, elevation 0.32, distance
  1.5 times the original bounds diagonal multiplied by 1.01.
- Flat/smooth comparison: supplied output-0 diffuse shader; Q toggles normals.
- Local teapot edits: 12 valid front-body flips; separate reset followed by
  12 splits and then 8 valid new-spoke flips. Candidate midpoints have y > 0.25,
  |x| < 0.35, and -0.35 < z < 0. Initial V/E/F = 1232/3696/2464; after splits,
  V/E/F = 1244/3732/2488. The split/flip combination preserves those final counts.
- Detail camera: focus (0, 0.4, -0.1), distance 1.15, same azimuth/elevation.
- Cube: `dae/cube.dae`, camera azimuth 0.72, elevation 0.40; distance remains
  1.9 times the original bounds diagonal multiplied by 1.01 for all comparisons.
- Symmetric cube: split all six face diagonals before Loop subdivision.
- Pre-split cube: one linear 4-to-1 refinement, without updating old positions,
  followed by three Loop iterations.
- Boundary fixture: square corners (+/-1, +/-1, 0), initial diagonal, one boundary
  split, then one Loop iteration. Camera azimuth 0.25, elevation 1.1, distance 6.

`assets/measurements.csv` records counts, maximum absolute coordinate, and
maximum coordinate-plane reflection residual for all cube states. Reflections
use the original coordinate origin. The supplied cube has approximately 1e-6
coordinate noise.

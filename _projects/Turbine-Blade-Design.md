---
layout: project
title: MAE 4272 Turbine Blade Design
description: Designed a full turbine blade in Autodesk Fusion by lofting airfoil cross sections defined at stations along the span, with variable chord and pitch angle. The blade is designed for 3D printing and wind tunnel testing.
technologies: [Autodesk Fusion, 3D Printing]
image: /assets/images/turbine-blade-isometric.jpg
imagealt: Isometric view of the full turbine blade
---

This project was the design of a full turbine blade, modeled in Autodesk Fusion. The blade is designed to be 3D printed and tested in a wind tunnel.

![Isometric view of the full blade]({{ "/assets/images/turbine-blade-isometric.jpg" | relative_url }})

*Isometric view of the full blade. The chord varies along the span rather than staying constant.*

A rotating blade sees a different local flow speed at each point along its length, with the fastest flow near the tip. Because of this, the best airfoil size and orientation is different at every spanwise location, so the blade cannot simply be a constant-width extrusion. Varying the chord lets each section be sized for the conditions it actually sees, as well as for the structural demands of carrying load inward toward the root.

![View of the blade looking from tip to root]({{ "/assets/images/turbine-blade-tip-to-root.jpg" | relative_url }})

*View looking from the tip toward the root. The pitch angle changes from section to section.*

For the same reason, the pitch angle varies along the span. The direction of the flow relative to the blade changes with distance from the axis of rotation, so each section is rotated to a different angle to keep it working at a suitable angle of attack.

## CAD process

![Airfoil cross section sketches positioned along the span]({{ "/assets/images/turbine-blade-airfoil-sections.jpg" | relative_url }})

*The airfoil cross sections before lofting, each placed at its own station along the blade.*

The blade was built in Fusion by creating a separate airfoil cross section sketch at each station along the span:

1. I imported the airfoil spline data from a CSV file to generate the airfoil profile.
2. For each station, I applied the blade parameters for that location: chord, quarter chord, z-axis offset, scale, and rotation.
3. With all of the cross section sketches in place, I used the loft feature to blend them into a single continuous blade surface.

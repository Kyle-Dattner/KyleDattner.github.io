---
layout: project
title: Torque Wrench Design and Ansys FEM
description: Designed a torque wrench and selected a suitable material using analytical calculations. Built a CAD model of the wrench and used Ansys to run a finite element analysis (FEA) of it under torque.
technologies: [Autodesk Fusion, Ansys, MATLAB]
image: /assets/images/wrench-cover.jpg
imagealt: Ansys deformation contours of the torque wrench
---

For a class, I designed a torque wrench to meet a set of specifications at a given maximum torque. I iterated on analytical calculations to find the material and wrench dimensions that satisfied those specifications, then built a CAD model of the chosen design. In Ansys, I ran a finite element analysis (FEA) of the design under the specified load, applying boundary conditions and recording the results using several stress, strain, and deformation metrics. Comparing the FEA results to my hand calculations showed me the limits of hand calculations and where FEA is most useful. Finally, I ran several mesh refinement studies to measure how mesh size affects the results.

Below is the CAD model I designed. It is deliberately simple and lacks the complex geometry and contours of a real wrench, which allowed me to verify the design with hand calculations.

![CAD Model]({{ "/assets/images/Wrench-CAD-Model.png" | relative_url }})

The wrench is made of aluminum alloy 7010-T7451. I selected the material iteratively, comparing several alloy families and narrowing the options using material properties. This alloy is a good fit for several reasons. Its yield strength is high relative to other aluminum alloys, which achieves the desired safety factor against yielding. Its Young's modulus of 10.5e3 ksi is low enough to allow the deformation the strain gauge needs to reach its minimum required output. Finally, its fracture toughness and fatigue strength are high enough to meet the desired safety factors for fracture and fatigue.

The load was applied as a distributed load over the end surface of the wrench, with its magnitude calculated from F = M/L to produce the desired moment. A boundary condition at the wrench drive prevents rotation.

![Load and Boundary Conditions]({{ "/assets/images/Wrench-Boundary-Condition-Analysis.png" | relative_url }})

Normal strain contours:

![Normal Strain Contours]({{ "/assets/images/Wrench-FEM-Normal-Strain.png" | relative_url }})

Maximum principal stress contours:

![Max Principal Stress Contours]({{ "/assets/images/Wrench-FEM-Maximum-Principal-Stress-Contours.png" | relative_url }})

Normal stress contours. The maximum normal stress occurs at stress concentrations on and at the base of the wrench drive:

![Max Normal Stress Contours]({{ "/assets/images/Wrench-FEM-Normal-Stress.png" | relative_url }})

Deflection of the wrench. As expected, the greatest deflection occurs at the end where the load is applied:

![Load Point Deflection]({{ "/assets/images/Wrench-FEM-Deformation.png" | relative_url }})

I chose the SGD-1.5/120-LY11 linear strain gauge from Omega Engineering. At 4.7 mm, it fits within the area of the wrench where it will be placed. The strain at the gauge is very close to my hand calculations at 0.001, which corresponds to an output of 1.039 mV/V.

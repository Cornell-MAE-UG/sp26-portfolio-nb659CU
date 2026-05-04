---
layout: project
title: Nutcracker Bending
description: Design a nutcracker with handles that bend elastically while maintaining mechanical advantage to crack macadamia nuts
image: /assets/images/nutcracker.jpeg
imagealt: Nutcracker design diagram
technologies:
  - Mechanical Engineering
  - Force Analysis
  - CAD Design
  - Beam Bending Analysis
date: 2026-05-03
---

## Project Overview

This engineering project addresses a practical design challenge: creating a nutcracker capable of generating sufficient force to crack a macadamia nut using average human grip strength. The design demonstrates the application of mechanical advantage principles, force equilibrium analysis, and elastic beam bending.

## Problem Statement

**Objective**: Find the dimensions of a nutcracker that will produce enough cracking force for macadamia nuts based on 50th percentile female grip strength.

**Objective 2**: Find the point of maximum elastic deflection in the handles, then choose a beam cross section and material that keep vertical elastic deflection below 2% of handle length while minimizing mass.

## Given Data

| Parameter | Value |
|-----------|-------|
| Load required to crack macadamia nut | 222 kgf |
| 50th percentile female grip strength (ages 20-24) | 28.6 kgf |
| Average macadamia nut diameter | ~25 mm |
| Reference | PMID 39647778 |

## Design Analysis

### Mechanical Advantage Principle

The nutcracker operates as a lever with the joint at the pivot, the nut reaction near the jaw, and the user force at the handle grip.

**Key assumption**: The transverse bending of the handles is the dominant elastic deformation mode. Axial loads and torsion are neglected for this analysis.

### Force Equilibrium Calculation

Using torque equilibrium about the pivot, the required distance between the grip point and the nut compression point is:

$$x = \frac{F_{nut} \times d_{nut}}{F_{grip}} = \frac{222 \text{ kgf} \times 14 \text{ mm}}{28.6 \text{ kgf}} = 109 \text{ mm}$$

Where:
- $x$ = required handle length from grip to pivot
- $F_{nut}$ = cracking force needed (222 kgf)
- $d_{nut}$ = effective nut moment arm (≈14 mm)
- $F_{grip}$ = average grip force (28.6 kgf)

This gives an effective handle length of about 109 mm, which sets the beam span for deflection calculations.

### a) Maximum Elastic Deflection Location

**Beam model**: Each handle is modeled as a cantilever beam fixed at the pivot and loaded by the transverse grip force at the free end.

**Assumptions**:
- The handle is rigidly supported at the pivot.
- The applied actuator/grip force is transverse to the beam axis.
- The nut reaction is transferred through the beam and produces bending moment about the pivot.
- The handle length from pivot to grip is $L \approx 109$ mm.

For a cantilever beam with an end transverse load, the maximum elastic deflection occurs at the free end. Therefore, the location of maximum elastic deflection in the handle is:

- **At the grip end of the handle, farthest from the pivot.**

This is the point where the accumulated bending produces the largest vertical displacement.

### b) Beam Design for <2% Deflection

**Target**: vertical elastic deflection $\delta < 0.02L \approx 2.2$ mm.

Using the cantilever deflection formula for an end load:

$$\delta = \frac{F L^3}{3 E I}$$

With:
- $F = 28.6$ kgf $\approx 280$ N
- $L = 0.109$ m
- $E$ = elastic modulus of the beam material
- $I$ = second moment of area of the handle cross section

#### Material choice

For maximum mass efficiency, the best available material class is carbon-fiber-reinforced polymer (CFRP) because its specific modulus ($E/\rho$) is higher than steel or aluminum.

Selected material:
- **Unidirectional carbon-fiber composite**, $E \approx 70$ GPa, density $\rho \approx 1.60$ g/cm$^3$.

#### Cross section

Selected beam cross section:
- Outer size: **24 mm × 20 mm**
- Wall thickness: **2 mm**
- Section type: **rectangular hollow tube**

Second moment of area for the hollow rectangle:

$$I \approx \frac{24\cdot20^3 - 20\cdot16^3}{12} \approx 9.2 \times 10^{3}\ \text{mm}^4$$

#### Deflection estimate

Using the selected section and material,

$$\delta \approx \frac{280 \times 0.109^3}{3 \times 70\times10^9 \times 9.2\times10^{-9}} \approx 0.19\ \text{mm}$$

This is approximately **0.18% of the handle length**, well below the 2% requirement.

#### Mass efficiency

- Handle wall area: $\approx 160$ mm$^2$
- Handle mass: $\approx 28$ g for 109 mm length
- Pair of handles: $\approx 56$ g total

By comparison, a solid aluminum handle with similar stiffness would weigh roughly **70–80 g per handle**, so the CFRP hollow beam is the more mass-efficient choice.

## Final Design

### c) Final design drawing

![Nutcracker beam design](assets/images/nutcracker-beam-design.svg)

![Design image](assets/images/IMG_1097.jpeg)

### Design summary

- Handle length: **109 mm** from grip to pivot
- Beam type: **rectangular hollow beam**
- Cross section: **24 × 20 mm outer, 2 mm wall thickness**
- Material: **unidirectional carbon-fiber composite**
- Predicted maximum elastic deflection: **0.19 mm** (≈0.18% of handle length)
- Mass-efficient result: **~28 g per handle**

## Feasibility Assessment

✓ **The device remains functionally feasible** with elastic handle design.

### User Compliance

- **Most adult men**: Simple and comfortable to use.
- **Women (ages 20-50)**: Usable with full or near-full grip strength.
- **Elderly or individuals with reduced grip strength**: May still find it challenging due to required force.

The compact geometry and high-specific-stiffness material produce a stiff, lightweight handle while preserving the required mechanical advantage for cracking macadamia nuts.
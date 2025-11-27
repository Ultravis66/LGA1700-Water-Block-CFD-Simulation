# LGA1700 Water Block CFD Simulation

Conjugate heat transfer CFD analysis of LGA1700 CPU water block with jet impingement cooling and porous media fin array modeling.

**Geometry Source:** [EK-CPU Lignum on GrabCAD](https://grabcad.com/library/ek-cpu-lignum-1)

---

## Overview

Advanced CFD analysis demonstrating conjugate heat transfer modeling of a high-performance CPU liquid cooling block for LGA1700 socket. Features jet impingement cooling, porous media representation of microchannel fin arrays, and orthotropic thermal conductivity for directional heat transfer.

**Key Capabilities Demonstrated:**
- Conjugate heat transfer (CHT) between solid copper and liquid coolant
- Porous media modeling with directional thermal and flow resistance
- Realistic thermal interface resistance (TIM contact modeling)
- Energy balance validation and convergence monitoring

---

## Geometry Development

### Starting Point
The analysis began with a detailed CAD model of the EK-CPU Lignum water block from GrabCAD. The original geometry included full mechanical detail with mounting hardware, aesthetic features, and complex internal fin structures.

![Original Geometry - View 1](images/Geometry_1.png)
*Original imported geometry showing full mechanical assembly*

![Original Geometry - View 2](images/Geometry_2.png)
*Internal fin array structure from CAD model*

### CFD Simplification
The geometry was simplified for CFD analysis while preserving critical thermal-hydraulic features:

**Simplifications Made:**
- Removed mounting hardware and cosmetic features
- Extracted fluid domain from internal channels
- Simplified complex fin array geometry to porous media representation
- Created uniform CPU block representing IHS (Integrated Heat Spreader)
- Defined inlet/outlet boundaries for flow simulation

**Retained Critical Features:**
- Jet impingement plate geometry
- Overall flow path and channel dimensions
- CPU contact surface area and geometry
- Thermal mass distribution of copper cold plate

![CFD-Ready Geometry](images/CFD_Ready_Geo.png)
*Final CFD-ready geometry with fluid domain and simplified features*

### Key Dimensions
- **CPU Block (IHS representation):** 45mm × 38mm × 4mm (LGA1700 standard)
- **Fin Spacing:** 0.314 mm
- **Fin Thickness:** 0.371 mm
- **Calculated Porosity:** 0.458 (45.8% open volume)
- **Contact Area:** ~1900 mm²

**Geometry available:** [`CFD_Geo_STP.stp`](geometry/CFD_Geo_STP.stp)

---

## [Next Section: Meshing Strategy]

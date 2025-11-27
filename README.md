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

![Original Geometry - View 1](Geometry_1.png)
*Original imported geometry showing full mechanical assembly*

![Original Geometry - View 2](Geometry_2.png)
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

![CFD-Ready Geometry](CFD_Ready_Geo.png)
*Final CFD-ready geometry with fluid domain and simplified features*

### Key Dimensions
- **CPU Block (IHS representation):** 45mm × 38mm × 4mm (LGA1700 standard)
- **Fin Spacing:** 0.314 mm
- **Fin Thickness:** 0.371 mm
- **Calculated Porosity:** 0.458 (45.8% open volume)
- **Contact Area:** ~1900 mm²

**Geometry available:** [`CFD_Geo_STP.stp`](geometry/CFD_Geo_STP.stp)

### Mesh Overview
![Mesh Overview - Cut Plane](Mesh.png)
*Overall mesh structure with cut plane showing internal regions (outer shell transparent)*

### Mesh
- **CPU (IHS):** 54,368 cells
- **Cold Plate:** 1,698,419 cells
- **Fluid Inlet:** 1,003,017 cells
- **Porous Medium:** 4,335,825 cells
- **Fluid Outlet:** 642,756 cells
- **Total cell count:** 7,734,385 cells
- **Prism layers:** 5 layers on all solid walls
- **y+ target:** < 5 for accurate wall heat transfer

### Region-Specific Meshing

#### CPU Block (IHS)
![CPU Mesh](Mesh_CPU.png)
*Refined mesh on CPU block to capture thermal gradients*

**Details:**
- Uniform refinement throughout solid volume
- Fine resolution at IHS/cold plate interface for CHT coupling
- Cell size: [your value] mm

#### Cold Plate Base
![Cold Plate Mesh](Mesh_Plate.png)
*Cold plate copper base mesh showing prism layers*

#### Porous Medium (Fin Array)
![Porous Medium Mesh](Porous_Medium.png)
*Porous zone mesh representing microchannel fin array*

**Details:**
- Coarser mesh appropriate for volume-averaged porous model
- 3-5 cells across porous region thickness
- No boundary layer mesh within porous zone (not needed for volume-averaged approach)

#### Fluid Domain
![Fluid Volume Mesh](Fluid_Volume.png)
*Complete fluid domain mesh showing inlet/outlet regions*


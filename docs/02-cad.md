# CAD Workflow Fusion 360
 
This document describes the modeling process for the flying wing in Fusion 360. It covers the overall approach, the key decisions made along the way, and what didn't work and what we learned from it.
 
**Software:** Autodesk Fusion 360  
**Current model purpose:** CFD geometry only (ANSYS Fluent input)  
**File:** `cad/flying-wing.step`
 
> **Note:** This version of the model is prepared specifically for CFD simulation. It is a solid, closed body, not hollowed, no internal structure, no servo cutouts. The print-ready version will be a separate file developed in a later phase.
 
---
 
## Modeling Approach
 
The wing was built using a loft-based workflow, which gives precise control over the cross-sectional shape across the span. A guide rail (leading edge path) controls the transition geometry between root and tip profiles.
 
**Workflow overview:**
1. Import MH 45 airfoil profile (root)
2. Create offset plane -> sketch scaled tip profile with washout
3. Loft with leading-edge guide rail -> main wing body
4. Add pod geometry as well as guide rails to achieve the wanted pod form
5. Mirror wing to full span
6. Add holm channel (sweep cut) (Not present in the CFD version)
7. Add winglets (To be redone)
8. Close elevon gaps for CFD (Not present in the CFD version)
---
 
## Key Decisions
 
**Airfoil import:** The MH 45 profile was imported from a `.dat` coordinate file. The raw file leaves a small gap at the trailing edge, this had to be closed manually before the loft would execute.
 
**Washout:** The tip profile was rotated ~2° (trailing edge up) to add geometric washout. In practice this resulted in the tip chord sitting 4mm above the root chordline, verified via Inspect → Measure.
 
**No shell for CFD:** The model is intentionally left as a solid body. CFD only sees the external surface, internal geometry is irrelevant for external aerodynamics. Hollowing is reserved for the print-ready version.

**Pod creation**: The pod body was created via the pod profile sketch to be lofted to the root of the wing. Several rails were created to achieve the pod form. In earlier versions the pod was attempted to be build as a seperate body and be assembled ontop of the wing. Not it is fully integrated into the main body.
 
---
 
## Challenges & What We Learned

### 
 
### Winglet geometry errors for CFD
 
The winglets initially showed 20 face intersection errors in ANSYS Discovery. The root cause was an imprecise transition between the winglet extrude and the swept wing surface, the faces were touching but not cleanly joined. Fusion's own geometry check showed no issues, which was misleading.
 
**Lesson:** Fusion's internal geometry validation is less strict than what CFD preprocessors require. Always validate the exported STEP in Discovery before starting mesh setup.
 
 
---
 
## Current Model State (CFD-ready)

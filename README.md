# Flying Wing UAV: Custom Design & CFD Analysis

> A 1.1 m flying wing drone designed from scratch in Fusion 360, validated with ANSYS Fluent CFD, and built with 3D printing. Inspired by the Skywalker X8.


## Overview

This project documents the end-to-end engineering of a custom flying wing UAV: from aerodynamic concept selection, through CAD modeling and CFD validation, to manufacturing and flight testing. The goal was to design an efficient, payload-capable airframe while learning the full UAV development pipeline.

**Why a flying wing?** Compared to conventional configurations, flying wings offer a higher lift-to-drag ratio for a given wingspan because the entire airframe contributes to lift, there is no tail or fuselage that only adds drag. This makes them ideal for endurance and payload missions.

## Specifications

| Parameter           | Value                  |
| ------------------- | ---------------------- |
| Wingspan            | 1100 mm                |
| Root chord          | 280 mm                 |
| Tip chord           | 120 mm                 |
| Wing area           | 0.22 m²                |
| Aspect ratio        | 5.5                    |
| Sweep angle         | 33°                    |
| Dihedral            | 5°                     |
| Washout             | 2°                     |
| Airfoil             | MH 45 (reflexed)       |
| Target MTOW         | ~900 g                 |
| Target payload      | ~190 g                 |
| Target cruise speed |                        |
| Target L/D          | > 10                   |


## Design Highlights

- **MH 45 reflexed airfoil** selected for its positive pitching moment (Cm0 > 0), which provides natural pitch stability without a horizontal tail
- **33° leading-edge sweep** gives passive pitch stability
- **2° washout (geometric twist)** prevents tip stall, critical for safe flight at high angles of attack
- **Removable wings** wings attach to a central pod via 8 mm carbon spar plus M4 wing bolts for transport and easy maintenance
- **Beluga-style nose hatch** front of the pod opens for access to the electronics tray (still in concept)
- **Trapezoidal winglets with sweep** reduce induced drag and improve yaw stability



## Tools Used

- **CAD** Fusion 360
- **CFD** ANSYS Fluent
- **Flight Controller** 
- **Slicing** 
- **Manufacturing**


## Documentation

The full engineering process is documented in the `docs/` folder:

1. [Design Rationale](docs/01-design.md) aerodynamic decisions, sizing
2. [CAD Workflow](docs/02-cad.md) step-by-step Fusion 360 modeling
3. [CFD Analysis](docs/03-cfd.md) ANSYS Fluent setup and results
4. [Build & Manufacturing](docs/04-build.md) print settings, assembly
5. [Electronics & Avionics](docs/05-electronics.md) components, wiring, FC tuning
6. [Flight Testing](docs/06-flight.md) maiden flight, telemetry


## Project Status

- [x] Concept & sizing
- [x] CAD model (Fusion 360)
- [x] Pod design
- [ ] Servo bays & control surfaces refinement
- [ ] CFD analysis (ANSYS Fluent)
- [ ] 3D printing & assembly
- [ ] Electronics integration
- [ ] Maiden flight


## Results


| Metric           | Predicted (CFD) | Measured (Flight) |
| ---------------- | --------------- | ----------------- |
| L/D at cruise    | TBD             | TBD               |
| Stall speed      | TBD             | TBD               |
| Endurance        | TBD             | TBD               |


## Authors

**Markus T. & Tobias W.** 
Project kick-off: April 2026

## Acknowledgments

- Skywalker X8 design inspiration
- Martin Hepperle MH 45 airfoil

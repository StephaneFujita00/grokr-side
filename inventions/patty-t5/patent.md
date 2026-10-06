# Dual-Track Burger Assembly Conveyor with Charge-Linked Priority Routing

## Abstract
A dual-track conveyor system for high-volume burger preparation at electric vehicle charging locations. The system uses parallel assembly tracks, one for standard orders and one prioritized for charging vehicles, with sensors detecting Supercharger occupancy to route orders and adjust speeds. Materials include stainless steel frames and food-grade belts. Dimensions: main track 4.5 m long, 0.6 m wide, tolerance ±2 mm on belt alignment. Failure modes addressed by redundant drives and jam detection.

## Problem
Tesla Diner averages over 700 burgers daily yet reduced its menu two weeks after opening due to kitchen and ordering throughput limits. Standard kitchen lines cannot sustain volume during peak charging hours without restricting service.

## Prior art
- US9955711B2, Method and apparatus for increased product throughput capacity, improved…: uses single conveyor with speed control; this invention adds dual tracks and vehicle charge sensors for priority routing at charging sites.
- US11685641B2, Modular automated food preparation system: describes modular robotic units; this invention integrates mechanical dual-track belts with simple optical sensors rather than full robotics.

## Summary of the invention
The invention comprises a dual-track stainless steel conveyor (10) with independent belt drives (12, 14). Track A (16) handles standard orders. Track B (18) activates for detected charging vehicles via Supercharger occupancy sensors (20). Orders enter via input chute (22). Diverter arm (24) routes based on sensor input. Assembly stations (26) spaced at 0.8 m intervals. Output to packaging at end (28). Redundant motor (30) engages on primary failure.

## Claims
1. A dual-track food assembly conveyor system comprising a frame supporting two parallel endless belts driven by separate variable-speed motors, an input diverter actuated by signals from vehicle charging occupancy sensors, and spaced assembly positions along each belt.
2. The system of claim 1 wherein the sensors comprise optical detectors mounted at Supercharger stalls that output a binary occupied signal to a controller.
3. The system of claim 1 wherein belt speed on the priority track increases by 25% upon receipt of an occupied signal.
4. The system of claim 1 further comprising a jam detection switch that halts the affected belt and engages a backup motor.
5. The system of claim 1 wherein the frame is constructed of 304 stainless steel with belt width of 600 mm ±2 mm.
6. The system of claim 1 wherein the diverter arm is a pivoting stainless steel plate actuated by a 24 VDC solenoid.

## Brief description of the drawings
FIG. 1 shows a top view of the dual-track conveyor with sensor inputs and diverter.
FIG. 2 shows a side elevation of one track illustrating drive motors, assembly stations, and output.

## Detailed description
The main frame (10) is 4500 mm long, fabricated from 304 stainless steel tubing 50 mm square. Two food-grade polyurethane belts (16, 18) run on rollers spaced 800 mm apart. Primary drive motors (12, 14) are 0.75 kW variable frequency units. Occupancy sensors (20) are infrared beam-break units mounted on each Supercharger stall, wired to a PLC controller that signals the diverter solenoid when any stall is occupied between midnight and 6 a.m. Assembly stations (26) consist of fixed stainless trays holding condiments and patties, positioned at 800 mm centers with 50 mm clearance to belt edge. On jam detection via current spike exceeding 8 A, the controller stops the motor and switches to redundant motor (30) within 2 seconds. Tolerances on roller alignment are held to ±1 mm to prevent belt tracking drift. All surfaces are sloped 2 degrees for drainage. The system handles 1200 patties per hour on dual tracks versus 650 on single track.
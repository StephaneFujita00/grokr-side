# Dual-Track Burger Assembly Conveyor with Integrated Ordering Sensors and Charge-Linked Routing

## Abstract
A dual-track conveyor system for high-volume burger preparation at electric vehicle charging locations integrates ordering terminals with kitchen assembly. Parallel stainless steel tracks run continuously at base speed, with variable motors boosting priority track 25 percent on any high-volume signal. Optical sensors detect Supercharger occupancy for routing and Supercharger app order volume for always-on dual operation. Frame is 4500 mm long 304 stainless, belts 600 mm wide. Redundant motors engage on jam current spike over 8 A within 2 seconds. Handles 1200 patties per hour.

## Problem
Tesla Diner averages over 700 burgers daily yet reduced its menu two weeks after opening due to kitchen and ordering throughput limits. Standard single-track lines cannot sustain volume during peak hours whether charging or non-charging. Ordering delays compound assembly bottlenecks outside midnight-6 a.m. windows.

## Prior art
- US9955711B2, Method and apparatus for increased product throughput capacity, improved…: uses single conveyor with speed control; this invention adds dual parallel tracks, vehicle charge sensors, and ordering volume input for continuous dual-track operation.
- US11685641B2, Modular automated food preparation system: describes modular robotic units; this invention integrates mechanical dual-track belts with simple optical sensors and PLC logic rather than full robotics, plus explicit jam redundancy.

## Summary of the invention
The invention comprises a dual-track stainless steel conveyor frame (10) with independent belt drives motors (12, 14). Track A (16) and Track B (18) run parallel endless belts. Input chute (22) receives orders from linked ordering terminals (32). Diverter arm (24) routes based on Supercharger occupancy sensors (20) or volume signal. Assembly stations (26) spaced at 0.8 m. Output (28). Redundant motor (30) on jam. PLC controller (34) processes signals.

## Claims
1. A dual-track food assembly conveyor system comprising a frame supporting two parallel endless belts driven by separate variable-speed motors, an input diverter actuated by signals from vehicle charging occupancy sensors and ordering volume sensors, and spaced assembly positions along each belt.
2. The system of claim 1 wherein the sensors comprise optical detectors mounted at Supercharger stalls that output a binary occupied signal to a controller and digital ordering terminals that output volume count exceeding 50 orders per hour.
3. The system of claim 1 wherein belt speed on either track increases by 25 percent upon receipt of an occupied or high-volume signal.
4. The system of claim 1 further comprising a jam detection switch that halts the affected belt and engages a backup motor within 2 seconds.
5. The system of claim 1 wherein the frame is constructed of 304 stainless steel with belt width of 600 mm ±2 mm.
6. The system of claim 1 wherein the diverter arm is a pivoting stainless steel plate actuated by a 24 VDC solenoid.

## Brief description of the drawings
FIG. 1 shows a top view of the dual-track conveyor with sensor inputs, diverter, ordering terminals, and full reference numerals.
FIG. 2 shows a side elevation of both parallel tracks illustrating drive motors, assembly stations, redundant drive, and output.

## Detailed description
The main frame (10) is 4500 mm long, fabricated from 304 stainless steel tubing 50 mm square section. Two food-grade polyurethane belts (16, 18) run on rollers spaced 800 mm apart with ±1 mm alignment tolerance. Primary drive motors (12, 14) are 0.75 kW variable frequency units. Occupancy sensors (20) are infrared beam-break units mounted on each Supercharger stall, wired to PLC controller (34) that signals the diverter solenoid when any stall is occupied. Ordering terminals (32) feed volume count to the same PLC; when count exceeds 50 orders per hour the dual tracks activate at base speed regardless of time of day. Assembly stations (26) consist of fixed stainless trays holding condiments and patties, positioned at 800 mm centers with 50 mm clearance to belt edge. On jam detection via current spike exceeding 8 A, the controller stops the motor and switches to redundant motor (30) within 2 seconds. Belt speed on the active track increases by 25 percent upon occupied or high-volume signal. All surfaces are sloped 2 degrees for drainage. The system handles 1200 patties per hour on dual tracks versus 650 on single track. Priority routing operates on charge signal between midnight and 6 a.m. while dual-track throughput remains available at all peaks via ordering input. Tolerances on roller alignment are held to ±1 mm to prevent belt tracking drift. Materials resist 80 °C washdown cycles.
# Firmware-Based Tendon Tension Compensation for Humanoid Robot Hands

## Abstract
A firmware module in the hand controller continuously monitors tendon tension via strain sensors and applies real-time compensation offsets to motor commands. The system detects slack or overload conditions from scale-up wear and corrects drive signals within 5 ms without hardware changes.

## Problem
Optimus hands experience inconsistent grasp force during high-volume production due to tendon stretch and friction variation. Existing motor position loops produce slippage or crushing when cumulative play exceeds 2 mm.

## Prior art
- US12440964B2 Kinetic and dimensional optimization for a tendon-driven gripper: describes passive tendon routing; this invention adds active firmware tension feedback absent in the prior mechanical design.

## Summary of the invention
The firmware runs on the hand MCU and uses a tension estimator updated at 200 Hz. It computes a correction delta added to the position setpoint. Thresholds trigger limp mode on detected failure.

## Claims
1. A method in a robot hand controller comprising: reading tension values from sensors on each tendon; calculating a compensation value as tension error multiplied by gain 0.8; adding the compensation value to the motor position command; repeating every 5 ms.
2. The method of claim 1 further comprising entering a limp state when any tension exceeds 120 N for more than 50 ms.
3. The method of claim 1 wherein the gain is reduced to 0.3 when temperature exceeds 55 C.
4. The method of claim 1 further comprising logging cumulative stretch and alerting when total exceeds 3 mm.
5. The method of claim 1 wherein compensation is disabled during initial calibration cycle lasting 10 s.
6. The method of claim 2 wherein limp state reduces motor current to 20 percent of nominal.

## Brief description of the drawings
FIG. 1 shows tendon path and sensor placement with controller block.

## Detailed description
Tendon (12) runs from motor pulley (14) through guide (16) to finger link (18). Strain gauge (20) mounted on tendon anchor (22) outputs voltage proportional to tension. MCU (24) samples gauge at 200 Hz. Estimator block (26) computes error as target tension 45 N minus measured value. Compensation delta equals error times gain 0.8 and is added to position command sent to motor driver (28). If tension exceeds 120 N for 50 ms the controller asserts limp flag reducing current limit to 20 percent. Temperature sensor (30) on motor housing reduces gain to 0.3 above 55 C. Stretch accumulator (32) integrates position error over time and triggers alert at 3 mm total. Calibration routine holds motors at zero load for 10 s to zero the estimator. All operations execute in firmware on the existing hand PCB with no added parts. Failure mode of sensor drift is handled by periodic zeroing during idle periods longer than 30 s.
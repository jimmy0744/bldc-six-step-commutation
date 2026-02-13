# BLDC Motor Drive Using Six-Step Commutation

## Overview
This project presents the design and implementation of a **Brushless DC (BLDC) motor drive system** using a six-step commutation strategy. The system utilizes Hall sensor feedback to determine rotor position and execute precise switching sequences for continuous motor operation.

The implementation focuses on reliable bidirectional control, torque optimization through phase alignment, and hardware protection to prevent unsafe switching conditions.

---

## Key Features
- Six-step commutation for BLDC motor control  
- Hall sensor-based rotor position detection  
- Bidirectional rotation control  
- Optimized torque via sensor phase alignment  
- Shoot-through prevention for inverter safety  
- Structured commutation lookup table  
- Stable system power-up sequencing  

---

## System Architecture
The motor drive system consists of:

- Texas Instruments (TI) development board  
- Three-phase inverter / drive board  
- Hall sensors for position feedback  
- External power supply  
- GPIO-based control interface  

The controller reads Hall sensor states and references a commutation table to activate the appropriate switching devices, generating a rotating magnetic field that drives the motor.

---

## Control Strategy
A lookup-table-based commutation method was implemented to ensure deterministic switching behavior.

To protect the hardware, a directional safety mechanism was introduced:

- The motor must reach a complete stop before reversing direction  
- Direction-switch commands are ignored during active rotation  

This prevents excessive current spikes and potential hardware damage.

---

## Experimental Validation
The system successfully demonstrated:

- Smooth motor startup  
- Stable forward and reverse operation  
- Continuous acceleration driven by electromagnetic torque  
- Reliable stopping when all switches were disabled  

Additionally, increased supply current was observed when external load was applied to the rotor, confirming the expected relationship between torque demand and current consumption.

---

## Future Improvements
Potential directions for further development include:

- Implementing **ePWM-based speed control**  
- Transitioning to **closed-loop control** for improved speed stability  
- Refactoring the control software using state-based logic to enhance scalability and maintainability  

---

## Technologies Used
- Embedded motor control  
- Six-step commutation  
- Hall sensor feedback  
- Power electronics switching

---

## Six-Step Commutation Table
The commutation table defines the switching sequence based on Hall sensor states, ensuring proper phase excitation and stable motor operation.

---

## Project Documentation

A detailed project report is available for further reference, covering the system design, control strategy, hardware implementation, and experimental validation.

- Code Composer Studio (CCS)  


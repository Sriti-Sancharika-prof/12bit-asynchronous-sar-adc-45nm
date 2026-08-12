# 12-bit Asynchronous SAR ADC — 45 nm CMOS

Design and circuit-level analysis of a 12-bit asynchronous Successive Approximation Register (SAR) Analog-to-Digital Converter (ADC) in 45 nm CMOS technology.

## Overview

This project explores the design of a low-power, medium-speed data converter using an asynchronous SAR architecture. The work focuses on reducing dependence on a high-frequency global clock through internally generated timing signals, while studying the trade-offs between resolution, power, speed, timing, and reliability.

The ADC was designed and simulated at the transistor level using 45 nm CMOS technology models.

## Architecture

The proposed SAR ADC consists of:

- Bootstrapped Sample-and-Hold
- Capacitive DAC (CDAC)
- Dynamic StrongARM Comparator
- TSPC-based SAR Control Logic
- Internal Clock Generator
- Output Register
- Ideal DAC for verification

The conversion follows a binary-search process from MSB to LSB. In the asynchronous architecture, internally generated control signals coordinate successive conversion steps rather than relying on a high-frequency global clock.

## Design Highlights

### Bootstrapped Sample-and-Hold

A bootstrapped sampling circuit was designed to maintain a more constant gate-to-source voltage across the sampling transistor, improving input tracking and reducing signal-dependent distortion.

### Dynamic StrongARM Comparator

A dynamic comparator based on the StrongARM topology was implemented for high-speed, low-static-power comparison. An RS latch and XOR-based ready signal were incorporated to support self-timed operation.

### Capacitive DAC

A capacitive DAC was designed for charge-redistribution-based successive approximation. Its operation was studied with respect to capacitor matching, parasitic loading, switching behavior, and settling.

### TSPC-based SAR Logic

TSPC-based dynamic logic was explored for the SAR control circuitry, providing a high-speed and low-power implementation suitable for the asynchronous conversion architecture.

### Internal Clock Generator

An internal clock-generation circuit was developed to generate the timing signals required for sampling, successive approximation, and end-of-conversion control.

### Output Register

An output register was designed to store the final digital conversion output and interface the SAR conversion process with the output stage.

## Simulation Setup

| Parameter | Value |
|---|---|
| Technology | 45 nm CMOS |
| Supply Voltage | 1 V |
| Resolution | 12-bit |
| Clock Frequency | 10 MHz |
| Clock Period | 100 ns |
| Input Signal | Sine wave |
| Input Frequency | 1 MHz |
| Input Range | 0–1 V |
| Simulation Time | 1 µs |
| Time Step | 0.1 ns |
| Load Capacitance | 1 pF |
| Bootstrap Capacitor | 5 pF |

The individual building blocks were evaluated through transient simulations under these operating conditions.

## Results

The individual building blocks were simulated and analyzed for functional and timing behavior, including:

- Sample-and-hold tracking and hold operation
- Dynamic comparator regeneration and decision behavior
- CDAC operation
- SAR timing and control signals
- Internal clock generation
- TSPC D flip-flop operation
- Output register operation

The simulations demonstrated successful block-level functionality and provided insight into the timing and circuit-level behavior of the individual components.

The project also included a discrete-IC-based SAR ADC implementation for practical validation of SAR conversion behavior. The discrete implementation demonstrated the expected quantized output and conversion behavior, with a reported conversion window of approximately 270–320 ns under the tested conditions.

## System-Level Challenges

Although the individual building blocks were functional, the complete 12-bit asynchronous ADC initially exhibited integration issues and did not produce the expected output.

The main challenges observed during system-level integration included:

- Internal clock timing mismatch
- Pulse-width and skew variations
- DAC settling
- TSPC charge sharing and leakage
- Parasitic capacitances
- Noise sensitivity
- Synchronization between the clock generator, SAR logic, DAC, and comparator

The integrated design was iteratively debugged, modified, and tested to investigate these issues and improve system-level operation.

These observations highlighted the importance of precise timing control and analog–digital co-design in asynchronous mixed-signal systems.

## Key Learning

The project provided practical experience in transistor-level mixed-signal design and demonstrated that successful block-level operation does not necessarily guarantee reliable system-level integration.

Key areas explored included:

- Dynamic CMOS behavior
- Charge redistribution
- Comparator regeneration
- Asynchronous timing
- Parasitic effects
- Noise and leakage
- Analog–digital interface challenges
- System-level verification and debugging

## Future Improvements

Potential improvements identified during the project include:

- More robust SAR logic using static or hybrid flip-flop architectures
- Calibrated delay elements for improved timing control
- Clock pulse-width and skew optimization
- Reduction of parasitic and leakage effects
- Layout-aware and post-layout verification
- Improved noise immunity
- Error correction or redundancy techniques

## Tools & Technologies

- LTspice
- 45 nm CMOS technology models
- Transistor-level circuit simulation
- Mixed-signal circuit analysis

## Project Team

- **Sriti Sancharika** — [GitHub](https://github.com/Sriti-Sancharika-prof) | [LinkedIn](https://www.linkedin.com/in/sriti-sancharika/)
- **Debanshi Jena** — [GitHub](https://github.com/DebanshiJena/) | [LinkedIn](https://www.linkedin.com/in/debanshi-jena-43ba67270/)
- **Sagarika Rout**

## Project Contributions

This project was carried out collaboratively by the project team, covering transistor-level circuit design, block-level simulation, system integration, and integrated ADC testing and analysis.

### Sriti Sancharika

- Designed and analyzed the dynamic StrongARM comparator
- Designed the TSPC D flip-flop used in the SAR logic
- Designed and analyzed the internal clock-generation circuitry
- Designed and implemented the output register
- Performed block-level simulations and analysis of the circuits developed as part of my contribution
- Refined and debugged the integrated SAR ADC through iterative simulation, making circuit and timing adjustments to resolve integration issues and achieve the expected operation
- Performed system-level testing and analysis of the integrated design
- Investigated timing, synchronization, leakage, parasitic, and dynamic logic effects during integration

### Debanshi Jena

- Designed and analyzed the bootstrapped Sample-and-Hold circuit
- Designed and analyzed the Capacitive DAC (CDAC)
- Designed and analyzed the SAR control logic and its supporting internal blocks
- Designed and analyzed the Master-Slave D flip-flop used in the output register
- Performed block-level simulations and analysis of the circuits developed as part of her contribution
- Integrated the individual ADC blocks into the complete 12-bit asynchronous SAR ADC
- Performed testing and analysis of the integrated design

### Sagarika Rout

- Member of the project team

## Project Context

**Bachelor's Major Project**  
School of Electronic Sciences  
Odisha University of Technology and Research, Bhubaneswar  
Academic Session: 2025–26

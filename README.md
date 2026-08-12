# 12-bit Asynchronous SAR ADC — 45 nm CMOS

Design and circuit-level analysis of a 12-bit asynchronous Successive Approximation Register (SAR) ADC in 45 nm CMOS technology.

## Overview

This project explores the design of a low-power, medium-speed data converter using an asynchronous SAR architecture. The work focuses on reducing dependence on a high-frequency global clock through internally generated timing signals, while studying the circuit-level trade-offs between resolution, power, speed, timing, and reliability.

The ADC was designed and simulated at the transistor level using CMOS technology models.

## Architecture

The proposed SAR ADC consists of:

- Bootstrapped Sample-and-Hold
- Capacitive DAC (CDAC)
- Dynamic StrongARM Comparator
- SAR Control Logic
- Internal Clock Generator
- Output Register
- Ideal DAC for verification

The conversion follows a binary-search process from MSB to LSB. In the asynchronous architecture, internal control signals coordinate successive conversion steps rather than relying on a high-frequency global clock.

## Design Highlights

### Bootstrapped Sample-and-Hold

A bootstrapped sampling circuit was designed to maintain a more constant gate-to-source voltage across the sampling transistor, improving input tracking and reducing signal-dependent distortion.

### Dynamic StrongARM Comparator

A dynamic comparator based on the StrongARM topology was implemented for high-speed, low-static-power comparison. An RS latch and XOR-based ready signal were incorporated to support self-timed operation.

### Capacitive DAC

A capacitive DAC was designed for charge-redistribution-based successive approximation. Its operation was studied with respect to capacitor matching, parasitic loading, switching behavior, and settling.

### SAR Logic

TSPC-based dynamic logic was explored for the SAR control circuitry, providing a high-speed and low-power implementation suitable for the asynchronous conversion architecture.

### Internal Clock Generator

An internal clock-generation circuit was developed to generate the timing signals required for sampling, successive approximation, and end-of-conversion control.

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

The individual blocks were evaluated through transient simulations under the above operating conditions. :contentReference[oaicite:2]{index=2}

## Results

The individual building blocks were successfully simulated and verified, including:

- Sample-and-hold tracking and hold operation
- Dynamic comparator regeneration and decision behavior
- CDAC operation
- SAR timing and control signals
- Internal clock generation
- TSPC D flip-flop operation

The simulations demonstrated correct block-level functionality and timing behavior. :contentReference[oaicite:3]{index=3}

The project also included a discrete-IC-based SAR ADC implementation for practical validation of SAR conversion behavior. The discrete implementation demonstrated the expected quantized output and conversion behavior, with a reported conversion window of approximately 270–320 ns under the tested conditions. :contentReference[oaicite:4]{index=4}

## System-Level Challenges

Although the individual blocks were functional, the complete 12-bit asynchronous ADC did not produce the expected output after integration.

The main issues observed were associated with:

- Internal clock timing mismatch
- Pulse-width and skew variations
- DAC settling
- TSPC charge sharing and leakage
- Parasitic capacitances
- Noise sensitivity
- Synchronization between the clock generator, SAR logic, DAC, and comparator

These observations highlighted the importance of **analog–digital co-design and precise timing control** in asynchronous mixed-signal systems. :contentReference[oaicite:5]{index=5}

## Key Learning

The project provided practical experience in transistor-level mixed-signal design and showed that successful block-level operation does not necessarily guarantee reliable system-level integration.

Particular focus was placed on understanding:

- Dynamic CMOS behavior
- Charge redistribution
- Comparator regeneration
- Asynchronous timing
- Parasitic effects
- Noise and leakage
- Analog–digital interface challenges
- System-level verification

## Future Improvements

Potential improvements identified during the project include:

- More robust SAR logic using static or hybrid flip-flop architectures
- Calibrated delay elements for improved timing control
- Clock pulse-width and skew optimization
- Reduction of parasitic and leakage effects
- Layout-aware and post-layout verification
- Improved noise immunity
- Error correction or redundancy techniques

These directions follow directly from the integration challenges observed during the project. :contentReference[oaicite:6]{index=6}

## Tools

- LTspice
- 45 nm CMOS technology models
- Transistor-level circuit simulation
- Mixed-signal circuit analysis

## Project Context

**Bachelor's Major Project**  
School of Electronic Sciences  
Odisha University of Technology and Research  
2025–26

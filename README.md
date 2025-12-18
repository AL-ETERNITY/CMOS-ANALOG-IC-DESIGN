# CMOS Analog IC Design

A comprehensive collection of laboratory experiments and projects focusing on CMOS analog integrated circuit design using **SCL 180nm CMOS technology**. This repository contains detailed characterization, analysis, and design of fundamental analog building blocks simulated using **Cadence**.

## 📋 Table of Contents

- [Overview](#overview)
- [Technology](#technology)
- [Lab Experiments](#lab-experiments)
  - [LAB 1: MOSFET Parameter Extraction](#lab-1-mosfet-parameter-extraction)
  - [LAB 2: Common Source Amplifier Analysis](#lab-2-common-source-amplifier-analysis)
  - [LAB 3: CMOS Current Mirror Circuits](#lab-3-cmos-current-mirror-circuits)
  - [LAB 4: MOS Differential Amplifier](#lab-4-mos-differential-amplifier)
  - [LAB 5: Differential Amplifier Topologies](#lab-5-differential-amplifier-topologies)
- [Project: Telescopic Operational Amplifier](#project-telescopic-operational-amplifier)
- [Authors](#authors)
- [References](#references)

---

## Overview

This repository documents the complete workflow of analog IC design from device characterization to complex amplifier design. Each lab builds upon previous concepts, progressively covering:

1. **Device Physics & Parameter Extraction** - Understanding MOSFET behavior
2. **Single-Stage Amplifiers** - Common source configurations
3. **Current References** - Various current mirror topologies
4. **Differential Amplifiers** - High-performance amplifier stages
5. **Operational Amplifier Design** - Complete op-amp implementation

---

## Technology

| Parameter | Value |
|-----------|-------|
| Process | SCL 180nm CMOS |
| Supply Voltage | 1.8V |
| Simulation Tool | Cadence Virtuoso |

---

## Lab Experiments

### LAB 1: MOSFET Parameter Extraction

**Title:** Analysis of Parameters of NMOS and PMOS Transistors

**Objective:** Comprehensive characterization and parameter extraction of MOSFET devices through DC analysis.

**Key Parameters Extracted:**

| Parameter | NMOS | PMOS |
|-----------|------|------|
| Threshold Voltage (V<sub>t0</sub>) | 0.210 V | -0.356 V |
| Transconductance Parameter (K) | 73.192 µA/V² | 42.841 µA/V² |
| Channel-Length Modulation (λ) | 0.11 V⁻¹ | 0.18 V⁻¹ |
| Subthreshold Swing | 73.5 mV/decade | -106.1 mV/decade |

**Topics Covered:**
- DC characterization of NMOS and PMOS
- Extraction of threshold voltage, transconductance, and λ
- Operating region identification (cutoff, linear, saturation, subthreshold, breakdown)
- Body effect analysis
- NMOS common-source amplifier design (Gain: 28.8, g<sub>m</sub>: 0.167 mA/V)

---

### LAB 2: Common Source Amplifier Analysis

**Title:** Analysis of Common Source Amplifier Circuits: DC, Transient, and AC Characterization Across Process Corners

**Objective:** Comprehensive characterization of five CS amplifier circuits through DC, transient, and AC analyses.

**Analysis Types:**
- DC Analysis - Bias point optimization
- Transient Analysis - Time-domain behavior
- AC Analysis - Frequency response

**Process Corner Analysis (Circuit 1):**

| Corner | AC Gain (dB) | Transient Gain (dB) |
|--------|--------------|---------------------|
| TT | Nominal | Nominal |
| FF | Up to 11.95 | Up to 11.1 |
| SS | Down to 6.90 | Down to 9.47 |
| SF | Varied | Varied |
| FS | Varied | Varied |

**Circuit Variants AC Gains:**
- Circuit 1: 6.90 - 11.95 dB (corner dependent)
- Circuit 2: 4.95 dB
- Circuit 3: 25.9 dB
- Circuit 4: 23.76 dB
- Circuit 5: 12.67 dB

**Key Observations:**
- 180° phase inversion across all topologies
- Optimized DC bias voltage: 700 mV

---

### LAB 3: CMOS Current Mirror Circuits

**Title:** Design and Analysis of CMOS Current Mirror Circuits

**Objective:** Analysis of various current mirror topologies and their performance characteristics.

**Reference Current:** 10 µA

**Topologies Analyzed:**

| Topology | Output Resistance |
|----------|-------------------|
| Simple Current Mirror | 2.273 MΩ |
| Basic Cascode | 674.79 MΩ |
| Cascode | 586.27 MΩ |
| Regulated Cascode | 674.79 MΩ |
| Low-Voltage Cascoded (LV-CCM) | 659.15 GΩ |
| Wilson | 581.31 MΩ |

**Key Insights:**
- Progression from basic to advanced mirrors demonstrates systematic improvements
- LV-CCM achieves highest output impedance (GΩ range)
- Trade-offs between output impedance, voltage headroom, and complexity

---

### LAB 4: MOS Differential Amplifier

**Title:** Design and Analysis of MOS Differential Amplifier

**Objective:** Design and measurement of a differential amplifier with external bias circuit.

**Target vs Measured Performance:**

| Parameter | Target | Measured |
|-----------|--------|----------|
| Differential Gain | 30 dB | 27.18 dB |
| Unity-Gain Bandwidth | 100 MHz | 167.47 MHz |
| Phase Margin | 90° | 87.89° |
| Power Dissipation | 250-350 µW | 331.4 µW |

**Circuit Features:**
- NMOS input differential pair
- Active PMOS loads (current mirror configuration)
- External bias generator
- Single-ended output

---

### LAB 5: Differential Amplifier Topologies

**Title:** Design and Analysis of Two MOS Differential Amplifier Topologies: A Comparative Study

**Objective:** Comparative analysis of NMOS-tail vs PMOS-tail differential amplifiers.

**Performance Comparison:**

| Parameter | NMOS-Tail | PMOS-Tail |
|-----------|-----------|-----------|
| Differential Gain | 28.57 dB | 32.23 dB |
| Unity-Gain Bandwidth | 3.081 MHz | 2.134 GHz |
| Phase Margin | 87.83° | 76.54° |
| Average Power | 3.635 µW | 3.032 µW |

**Design Trade-offs:**
- NMOS-tail: Higher input common-mode range near ground
- PMOS-tail: Better flicker noise, preferred for inputs near supply rail
- Device sizing critically impacts bandwidth characteristics

---

## Project: Telescopic Operational Amplifier

**Title:** Analysis and Design of a Telescopic Operational Amplifier in 180 nm CMOS Technology

**Objective:** Systematic design of a high-performance telescopic op-amp.

**Design Targets vs Achieved Performance:**

| Parameter | Target | Achieved |
|-----------|--------|----------|
| DC Gain | ≥ 50 dB | 63 dB |
| Unity-Gain Bandwidth | 100 MHz | 100.78 MHz |
| Phase Margin | ≥ 60° | 68° |
| PSRR | - | 11.18 dB |
| CMRR | High | 58 dB |
| Input-Referred Noise | - | ~15 nV/√Hz |
| Load Capacitance | 1 pF | 1 pF |

**Architecture Features:**
- Cascoded differential pairs
- Active loads for high gain
- Vertical stacking for output impedance enhancement
- Compact circuit structure with shared bias current path

---

## Authors

Siddhant Shah - siddhantshah469@gmail.com
---

## References

Key references used throughout this work:

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*
2. P. R. Gray et al., *Analysis and Design of Analog Integrated Circuits*
3. D. A. Johns and K. Martin, *Analog Integrated Circuit Design*
4. P. E. Allen and D. R. Holberg, *CMOS Analog Circuit Design*
5. R. J. Baker, *CMOS Circuit Design, Layout, and Simulation*
6. T. C. Carusone et al., *Analog Integrated Circuit Design*

---

## Repository Structure

```
CMOS-ANALOG-IC-DESIGN/
├── LAB_1/
│   ├── main.tex          # MOSFET Parameter Extraction Report
│   └── images/           # Circuit diagrams and plots
├── LAB_2/
│   ├── main.tex          # CS Amplifier Analysis Report
│   └── images/
├── LAB_3/
│   ├── main.tex          # Current Mirror Report
│   └── images/
├── LAB_4/
│   ├── main.tex          # Differential Amplifier Report
│   └── images/
├── LAB_5/
│   ├── main.tex          # Comparative Study Report
│   └── images/
├── Project/
│   ├── main.tex          # Telescopic Op-Amp Report
│   └── images/
└── README.md
```

---

## License

This project is for educational purposes as part of the CMOS Analog IC Design course at IIT Mandi.

---

*Indian Institute of Technology Mandi*

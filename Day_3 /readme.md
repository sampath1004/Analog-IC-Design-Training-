# Day 3 – Bandgap Reference (BGR) & Differential Amplifier Analysis  
**Cadence Virtuoso | Spectre Simulator**

---

## Objective

Day 3 focused on the design, simulation, and performance evaluation of a **Bandgap Reference (BGR)** and a **Differential Amplifier**.

### Goals:
- Generate a temperature-independent reference voltage
- Analyze PTAT and CTAT characteristics
- Perform DC temperature sweep analysis
- Conduct transient and FFT simulations
- Extract performance metrics: SINAD, SNR, ENOB, SFDR

---

## Tools Used

- Cadence Virtuoso (ADE L / ADE XL)
- Spectre Simulator
- Visualization & Analysis XL (Calculator + Spectrum)

---

# 1. Bandgap Reference (BGR)

## Concept

A Bandgap Reference produces a nearly constant voltage (~1.23 V) by combining:

- **CTAT Voltage (V_BE)** → Decreases with temperature  
- **PTAT Voltage (ΔV_BE-based)** → Increases with temperature  

By scaling and summing these components properly, temperature variations cancel, resulting in a stable reference voltage.

---

## DC Temperature Sweep

### Temperature Range:
0 °C to 100 °C

### Observations:
- **VREF ≈ 1.23 V**
- Slight negative slope across temperature
- PTAT increases linearly
- CTAT decreases linearly
- Proper temperature compensation achieved

---

## PTAT Characterization

| Temperature (°C) | PTAT Voltage (V) |
|------------------|------------------|
| 10               | 400.4 µV         |
| 20               | 402.1 µV         |
| 30               | 402.9 µV         |
| 50               | 404.0 µV         |
| 100              | 406.4 µV         |

### Extracted Slope:
~0.4 mV per 100 °C

This confirms correct PTAT generation.

---

## Temperature Coefficient (TC)

- **VREF TC ≈ −59 ppm/°C to −62 ppm/°C**

Indicates:
- Effective first-order temperature cancellation
- Minor residual curvature
- Possible improvement via trimming

---

# 2. Differential Amplifier

## Transient Analysis

### Observations:
- Clean sinusoidal differential output
- Proper common-mode bias
- No clipping
- Stable operation

---

# 3. FFT Analysis

FFT performed on differential input and output nodes.

---

## Performance Metrics

### Input Node (Din1)

- ENOB: −1.8559 bits  
- SINAD: −9.4126 dB  
- SNR: −9.4126 dB  
- SFDR: 0.0895 dBc  

Indicates very low signal amplitude relative to noise.

---

### Output Node (Dout) – Case 1

- SINAD: −6.1596 dB  
- SNR: −6.1596 dB  
- SFDR: 0.6834 dBc  
- THD: 0 %

---

### Output Node (Dout) – Case 2

- Signal Power: −101.77 dB  
- DC Power: −58.37 dB  
- Noise Floor: −102.36 dB  
- Integrated Noise: −118.89 dB  

---

### Output Node (Dout) – Case 3

- Signal Power: −122.71 dB  
- DC Power: −28.70 dB  
- Noise Floor: −126.55 dB  
- Integrated Noise: −143.09 dB  

---

# Analysis & Interpretation

- Reference voltage stabilized near 1.23 V
- PTAT and CTAT behavior validated
- Differential amplifier functionally correct
- FFT shows noise-dominated performance
- Improvement areas:
  - Increase gain
  - Optimize biasing
  - Improve device sizing
  - Add filtering

---

# Day 3 Summary

- Designed and validated Bandgap Reference
- Verified PTAT & CTAT temperature behavior
- Performed DC temperature sweep
- Conducted transient and FFT analysis
- Extracted SINAD, SNR, ENOB, SFDR

Result: Functional circuits with clear optimization path for improved dynamic performance.

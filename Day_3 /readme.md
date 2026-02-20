# Day 3 – Bandgap Reference (BGR) & Differential Amplifier Analysis  
**Cadence Virtuoso | Spectre Simulator**

---

## Objective

Day 3 focused on the design, simulation, and performance evaluation of a **Bandgap Reference (BGR)** and a **Differential Amplifier**.

### Goals
- Generate a temperature-independent reference voltage
- Analyze PTAT and CTAT behavior
- Perform DC temperature sweep analysis
- Conduct transient and FFT simulations
- Extract performance metrics: SINAD, SNR, ENOB, SFDR

---

## Tools Used
- Cadence Virtuoso (ADE L / ADE XL)
- Spectre Simulator
- Visualization & Analysis XL (Calculator + Spectrum)

---

# 1️⃣ Bandgap Reference (BGR)

## BGR Schematic

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


---

## Concept

A Bandgap Reference produces a nearly constant voltage (~1.23 V) by combining:

- **CTAT Voltage (V_BE)** → Decreases with temperature  
- **PTAT Voltage (ΔV_BE)** → Increases with temperature  

Proper scaling ensures temperature cancellation, resulting in a stable reference voltage.

---

## DC Temperature Sweep Analysis

### DC Output vs Temperature

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


### Observed Node Voltages

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


### Final Output Voltage

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


### Observations
- Temperature Range: 0 °C to 100 °C  
- VREF ≈ 1.23 V  
- Slight negative slope  
- PTAT increases linearly  
- CTAT decreases linearly  

---

# 2️⃣ PTAT Characteristic

## PTAT Voltage vs Temperature

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


### Extracted Values

| Temperature (°C) | PTAT Voltage (V) |
|------------------|------------------|
| 10               | 400.4 µV |
| 20               | 402.1 µV |
| 30               | 402.9 µV |
| 50               | 404.0 µV |
| 100              | 406.4 µV |

**PTAT Slope ≈ 0.4 mV / 100 °C**

---

# 3️⃣ Temperature Coefficient (VREF ppm)

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

### Observed Temperature Coefficient
≈ −59 ppm/°C to −62 ppm/°C  

Indicates effective first-order temperature compensation with minor residual curvature.

---

# 4️⃣ Differential Amplifier

## Transient Analysis

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


### Observations
- Clean sinusoidal differential output
- Proper common-mode biasing
- No clipping observed
- Stable and symmetric operation

---

# 5️⃣ Frequency Domain (FFT) Analysis

## FFT – Differential Input

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

## FFT – Differential Output

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


## Noise Spectrum

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


---

# 6️⃣ Extracted Performance Metrics

## Input Node (Din1)

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

- ENOB: −1.8559 bits  
- SINAD: −9.4126 dB  
- SNR: −9.4126 dB  
- SFDR: 0.0895 dBc  

---

## Output Node – Case 1

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />


- SINAD: −6.1596 dB  
- SNR: −6.1596 dB  
- SFDR: 0.6834 dBc  
- THD: 0 %

---

## Output Node – Case 2

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

- Signal Power: −101.77 dB  
- DC Power: −58.37 dB  
- Noise Floor: −102.36 dB  
- Integrated Noise: −118.89 dB  

---

## Output Node – Case 3

<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

- Signal Power: −122.71 dB  
- DC Power: −28.70 dB  
- Noise Floor: −126.55 dB  
- Integrated Noise: −143.09 dB  

---

# 7️⃣ Technical Summary

## Bandgap Reference
- Achieved ~1.23 V stable reference
- Verified PTAT & CTAT compensation
- Temperature coefficient within −60 ppm/°C
- Validated performance across 0–100 °C

## Differential Amplifier
- Stable transient behavior
- Proper differential operation
- Noise-dominated FFT response
- Scope for gain optimization and bias refinement

---

# 📌 Day 3 Conclusion

Successfully:
- Designed and validated a Bandgap Reference circuit
- Verified PTAT and CTAT temperature behavior
- Performed DC temperature sweep analysis
- Conducted transient and FFT simulations
- Extracted SINAD, SNR, ENOB, SFDR, and noise metrics

The circuits are functionally correct with clear scope for dynamic performance improvement and optimization in future iterations.

---

# Day 3 – Bandgap Reference & Differential Amplifier Study  
Cadence Virtuoso | Spectre Simulator

------------------------------------------------------------
Objective
------------------------------------------------------------
The objective of this session was to design and analyze a
Bandgap Reference (BGR) circuit and a Differential Amplifier.
The main focus was on temperature compensation, PTAT and CTAT
behavior, and evaluating the amplifier in both time and
frequency domains.

------------------------------------------------------------
Software Tools
------------------------------------------------------------
- Cadence Virtuoso (ADE L / ADE XL)
- Spectre Simulator
- ViVA Waveform Viewer and Spectrum Analyzer

------------------------------------------------------------
1. Bandgap Reference (BGR)
------------------------------------------------------------

BGR Circuit Schematic:
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/Screenshot%20from%202026-01-29%2015-18-23.png" />

The Bandgap Reference circuit is designed to generate a stable
reference voltage that remains nearly constant with changes
in temperature. This is achieved by combining a CTAT voltage,
which decreases as temperature rises, and a PTAT voltage,
which increases with temperature. When properly scaled, these
two voltages cancel each other’s temperature dependency.

------------------------------------------------------------
2. DC Temperature Sweep Analysis
------------------------------------------------------------

DC Sweep Output:
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/Screenshot%20from%202026-01-29%2011-10-21.png" />

Final Reference Voltage:
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/Screenshot%20from%202026-01-29%2011-10-21.png" />

Observations:
- Temperature range: 0 °C to 100 °C
- Output voltage stays close to 1.23 V
- Slight negative slope observed
- CTAT voltage decreases with temperature
- PTAT voltage increases with temperature

------------------------------------------------------------
3. PTAT Voltage Analysis
------------------------------------------------------------

PTAT Voltage vs Temperature:
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/Screenshot%20from%202026-01-29%2011-15-11.png" />

Extracted Values:

Temperature (°C) | PTAT Voltage (V)
-----------------------------------
10               | 400.4 µV
20               | 402.1 µV
30               | 402.9 µV
40               | 403.5 µV
50               | 404.0 µV
100              | 406.4 µV

Inference:
- PTAT voltage increases almost linearly
- Approximate slope is 0.4 mV per 100 °C

------------------------------------------------------------
4. Temperature Coefficient of Vref
------------------------------------------------------------



------------------------------------------------------------
5. Differential Amplifier – Transient Analysis
------------------------------------------------------------

------------------------------------------------------------
6. Frequency Domain (FFT) Analysis
------------------------------------------------------------

FFT of Differential Input:


------------------------------------------------------------
7. FFT Performance Parameters
------------------------------------------------------------

Input Node :
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/Screenshot%20from%202026-01-29%2010-19-21.png" />





------------------------------------------------------------
Key Takeaways
------------------------------------------------------------
- Bandgap Reference provides a stable output near 1.23 V
- PTAT and CTAT voltages compensate temperature variations
- DC sweep confirms good thermal stability
- Differential amplifier shows stable transient behavior
- FFT analysis indicates noise-limited performance
- Further optimization of gain and biasing is possible

---------------------

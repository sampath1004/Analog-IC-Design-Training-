# Day 3 – Bandgap Reference & Differential Amplifier Study  
Cadence Virtuoso | Spectre Simulator

------------------------------------------------------------
Objective
------------------------------------------------------------
The aim of this session was to design and study a Bandgap
Reference (BGR) circuit along with a Differential Amplifier.
The focus was on understanding temperature compensation,
verifying PTAT and CTAT behavior, and evaluating the amplifier
performance in both time and frequency domains.

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
![BGR](./images/BGR.png)

The Bandgap Reference circuit is used to generate a stable
reference voltage that remains nearly constant over
temperature. This is achieved by combining a CTAT voltage,
which decreases with temperature, and a PTAT voltage, which
increases with temperature. Proper scaling of these voltages
allows their temperature effects to cancel each other.

------------------------------------------------------------
2. DC Temperature Sweep Analysis
------------------------------------------------------------

DC Sweep Output:
![DC Sweep](./images/BGR_op1.png)

Internal Node Voltages:
![Node Voltages](./images/BGR_op2.png)

Final Reference Voltage:
![Vref](./images/BGR_op3.png)

Observations from DC Sweep:
- Temperature range considered: 0 °C to 100 °C
- Output voltage stays close to 1.23 V
- Small negative slope observed across temperature
- CTAT voltage decreases with temperature
- PTAT voltage increases with temperature

------------------------------------------------------------
3. PTAT Voltage Analysis
------------------------------------------------------------

PTAT Voltage vs Temperature:
![PTAT](./images/cdata.png)

Extracted Values:

Temperature (°C) | PTAT Voltage (V)
-----------------------------------
10               | 400.4 µV
20               | 402.1 µV
30               | 402.9 µV
50               | 404.0 µV
100              | 406.4 µV

Inference:
- PTAT voltage shows an almost linear increase
- Approximate slope is 0.4 mV per 100 °C

------------------------------------------------------------
4. Temperature Coefficient of Vref
------------------------------------------------------------

Vref ppm Plot:
![Vref ppm](./images/calc.png)

Key Results:
- Temperature coefficient ≈ −60 ppm/°C
- Indicates good temperature stability
- Further trimming can reduce variation

------------------------------------------------------------
5. Differential Amplifier – Transient Analysis
------------------------------------------------------------

Transient Response:
![Transient](./images/differential_transient.png)

Observations:
- Differential outputs are balanced and sinusoidal
- Proper common-mode voltage is maintained
- No clipping or waveform distortion observed

------------------------------------------------------------
6. Frequency Domain (FFT) Analysis
------------------------------------------------------------

FFT of Differential Input:
![FFT Input](./images/diff_spect1.png)

FFT of Differential Output:
![FFT Output](./images/diff_spect2.png)

Noise Spectrum:
![FFT Noise](./images/diff_spect3.png)

Inference:
- Output spectrum is dominated by noise
- Signal amplitude is relatively low
- Performance limited by noise floor

------------------------------------------------------------
7. FFT Performance Parameters
------------------------------------------------------------

Input Node (Din1):
![Metrics Din1](./images/m1.png)

- ENOB  = −1.86 bits
- SINAD = −9.41 dB
- SNR   = −9.41 dB
- SFDR  = 0.09 dBc

Output Node (Dout) – Case 1:
![Metrics Dout1](./images/m2.png)

- SINAD = −6.16 dB
- SNR   = −6.16 dB
- SFDR  = 0.68 dBc
- THD   = 0 %

Output Node (Dout) – Case 2:
![Metrics Dout2](./images/m3.png)

- Signal Power     = −101.77 dB
- DC Power         = −58.37 dB
- Noise Floor      = −102.36 dB
- Integrated Noise = −118.89 dB

Output Node (Dout) – Case 3:
![Metrics Dout3](./images/m4.png)

- Signal Power     = −122.71 dB
- DC Power         = −28.70 dB
- Noise Floor      = −126.55 dB
- Integrated Noise = −143.09 dB

------------------------------------------------------------
Key Takeaways
------------------------------------------------------------
- Bandgap Reference provides a stable voltage near 1.23 V
- PTAT and CTAT voltages compensate temperature variations
- DC sweep confirms thermal stability
- Differential amplifier shows stable time-domain behavior
- FFT analysis reveals noise-limited performance
- Gain and bias optimization can improve results

------------------------------------------------------------
End of Day 3
------------------------------------------------------------

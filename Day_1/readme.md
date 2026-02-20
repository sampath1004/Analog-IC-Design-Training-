# Day 1 – Common Source Amplifier Simulation in Cadence Virtuoso

## Objective
The goal of Day 1 was to build and simulate a basic Common Source (CS) amplifier in Cadence Virtuoso to understand practical analog design concepts. Emphasis was placed on proper biasing, verifying saturation operation, and evaluating small-signal and large-signal performance using multiple simulation analyses.

---

## Tools Used
- Cadence Virtuoso (ADE L)
- Spectre Simulator

---

## Circuit Overview
A single-stage NMOS Common Source amplifier was designed and biased using a suitable DC voltage to ensure saturation region operation. The circuit performance was evaluated using DC, AC, transient, and parametric simulations to observe its electrical behavior under different conditions.

---

## 1. DC Analysis

DC simulation was performed to determine the operating point of the amplifier by sweeping the input bias voltage and monitoring the output response.

### Key Observations
- The MOSFET remained in saturation for the selected bias range.
- Drain current and output voltage were consistent with theoretical expectations.
- Important parameters such as VGS, VDS, ID, and transconductance (gm) were extracted and verified.

### DC Response
![DC Analysis](./images/DC_analysis.png)

### Operating Point Parameters
![DC Operating Point](./images/DC_analysis_OP.png)

---

## 2. AC Analysis

AC analysis was conducted to examine the frequency response and determine the small-signal gain characteristics of the amplifier.

### Key Observations
- The amplifier shows measurable gain at low frequencies.
- Gain gradually decreases at higher frequencies due to device parasitics.
- Phase response confirms stable amplifier behavior without oscillations.

### AC Gain and Phase Plot
![AC Analysis](./images/AC_ANALYSIS.png)

---

## 3. Transient Analysis

A sinusoidal input signal was applied to observe the time-domain response of the amplifier.

### Key Observations
- Output signal is amplified and inverted, as expected for a CS stage.
- No distortion observed within the chosen input amplitude.
- Confirms proper biasing and linear region operation.

### Transient Waveform
![Transient Analysis](./images/transient_analysis.png)

---

## 4. Parametric Analysis

Parametric sweeps were performed by varying bias voltage and load resistance to study circuit sensitivity.

### Key Observations
- Output voltage changes noticeably with bias variation.
- Load resistance impacts voltage gain and operating point.
- Parametric analysis helps optimize design parameters.

### Parametric Setup
![Parametric Analysis Setup](./images/parametric_analysis.png)

### Parametric Results
![Parametric Output](./images/parametric_output.png)

---

## Day 1 Conclusion

- Verified proper DC biasing and saturation operation of NMOS.
- Gained experience performing DC, AC, transient, and parametric analyses.
- Observed gain behavior in both frequency and time domains.
- Developed a practical understanding of CS amplifier design fundamentals for analog IC applications.

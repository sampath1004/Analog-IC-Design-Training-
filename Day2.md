# Day 2 – Differential Amplifier and OTA Design

## Objective
The goal for Day 2 was to design a MOS differential amplifier and develop it into an Operational Transconductance Amplifier (OTA). We focused on analyzing the circuit's biasing, gain, frequency response, and transient behavior, ending with symbol-level verification.

---

## Tools Used
* Cadence Virtuoso Schematic Editor
* Cadence Virtuoso ADE L
* Spectre Simulator

---

## 1. Differential Amplifier – Transistor Level

### Circuit Description
We implemented a differential amplifier using NMOS transistors for the input pair and a PMOS current mirror as the load. A tail current source was included to provide stable biasing for the differential operation.

### Differential Amplifier Schematic
![Differential Amplifier](./images/Diff_Amplifier.png)

---

## 2. Port Configuration
Input and output ports were added to the schematic. This step is essential for creating a symbol and allowing the design to be used in hierarchical simulations.

### Adding Ports
![Adding Ports](./images/adding_ports.png)

---

## 3. DC Operating Point Analysis
We ran a DC analysis to ensure the circuit was biased correctly. The main goal was to confirm that every transistor remained in the proper operating region.

**Observations:**
* The input NMOS transistors were confirmed to be in saturation.
* The tail current was measured to verify the bias level.
* Input and output DC voltages were checked for stability.
* The PMOS mirror successfully balanced the current between the two branches.

### DC Analysis Plot
![DC Analysis](./images/ckt2_DCanalysis.png)

---

## 4. AC Small-Signal Analysis
AC analysis was used to determine the frequency response and gain of the differential amplifier.



**Observations:**
* We measured the low-frequency differential gain.
* We identified the frequency where the gain begins to drop (roll-off).
* The single dominant pole behavior suggests the amplifier is stable.

---

## 5. Transient Response
A transient simulation was performed by applying out-of-phase sine waves to the differential inputs.

**Observations:**
* The circuit showed effective current steering between the branches.
* The output waveform confirmed that the differential signal was being amplified.
* The peak-to-peak output voltage was consistent with our design goals.

### Differential Transient Response
![Differential Transient](./images/differential_transient.png)

---

## 6. Design Variations
We explored different circuit configurations to see how transistor sizing impacts performance.

* **Variation 2:** This design maintained a stable DC point and balanced gain with bandwidth.
* **Variation 3:** By increasing the width of the transistors, we improved the transconductance and gain, though the extra capacitance slightly reduced the bandwidth.

### Variation Plots
![Circuit 2 AC Analysis](./images/ckt2_ACanalysis.png)
![Circuit 3 Transient Analysis](./images/ckt3_Transientanalysis.png)

---

## 7. Symbol Generation
A symbol was generated for the OTA. This makes the design more modular, allowing us to use the amplifier as a single block in larger systems.

### OTA Symbol
![OTA Symbol](./images/symbol.png)

---

## 8. Testbench Verification
The final step involved placing the OTA symbol into a testbench to confirm it performs the same way as the original schematic.

**Observations:**
* The symbol correctly accepted the differential input signals.
* Power supplies were connected and verified.
* The results from the symbol-level test matched our transistor-level simulations.

### Symbol Testbench
![Symbol Testbench](./images/symbol_test.png)

---

## Day 2 Summary
* Completed the design and analysis of a MOS differential amplifier.
* Verified that all transistors were biased in the saturation region.
* Analyzed gain and bandwidth through AC and Transient simulations.
* Created a functional OTA symbol for future hierarchical design work.


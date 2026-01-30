# Day 2 – Analog IC Design (Hands-on & Circuits)

The Day 2: learning and hands-on circuits designed during the
Analog and Mixed-Signal IC Design training program using Cadence Virtuoso.

---

## Circuit 2 – Common Source Amplifier with Active Load

- Implemented a common-source (CS) amplifier using NMOS as input device.
- PMOS transistor used as active load.
- Bias voltages were applied to set proper operating point by warying W2.
- Output taken at the drain node.
- Small-signal gain expression:
  
  Av = − gm × ro
# Circuit
<img width="521" height="646" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_circuit.png" />

# DC Analysis 
<img width="521" height="646" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

# Transient Analysis
<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac_trans.png" />

# AC Analysis 
 <img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/mos_ac.png" />

- Observed inversion of output signal with respect to input.
- Circuit helped understand:
  - Biasing
  - Gain
  - Saturation region operation
- The gain is still less so we move on to the another ciruit with load as pmos not diode connected.

---

## Circuit 3 – Common Source Amplifier with Current Mirror Load

- NMOS transistor used as amplifying device.
- PMOS current mirror used as active load.
- Improved gain compared to resistive load.
- Bias voltage applied to mirror transistor.
- Small-signal gain expression:

  Av = − gm × (ro3 || ro4)
# Circuit
<img width="1277" height="716" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/small_circuit_3.png" />

# Transient Analysis
<img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/small_tran.png" />

# AC Analysis 
 <img width="1366" height="768" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/small_ac.png" />
 
- Helped in understanding:
  - Current mirror operation
  - Output resistance enhancement
  - Gain improvement techniques

---

## Circuit 4 – Differential Amplifier

- Designed a MOSFET differential amplifier.
- Two NMOS transistors used as differential pair.
- PMOS transistors used as active loads.
- Tail current source implemented using NMOS.
- Differential input applied to both gates.
- Output taken from one side of the differential pair.
# Circuit
<img width="832" height="418" alt="image" src="https://github.com/user-attachments/assets/d7cae71f-7853-49b8-97a8-b0e8621ea200" />

# DC Analysis 
<img width="832" height="418" alt="image" src="https://github.com/user-attachments/assets/60a48306-d331-4188-9926-7c84ba2b17d8" />

# Transient Analysis
<img width="1432" height="574" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/diff_trans.png" />
- Key observations:
  - Differential operation
  - Common-mode rejection
  - Bias current control
- Forms the core block of operational amplifiers.

---

## Symbol Creation of Operational Amplifier

- Created Op-Amp symbol using the previously designed differential amplifier circuit.
- Pins defined:
  - Differential inputs (+, −)
  - Output
  - Power supply (VDD)
  - Ground (VSS)
- Differential amplifier as a functional Op-Amp block.
<img width="1197" height="604" alt="image" src="https://github.com/user-attachments/assets/31ac0ee4-0598-468a-a5fb-19292ddec4ba" />

<img width="1060" height="555" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/opam.png" />


---

## Bandgap Reference (BGR) Circuit

- Bandgap Reference circuit was discussed and implemented at circuit level.
- Focus was on understanding:
  - Circuit structure
  - Use of BJTs/MOS devices
- Aim of BGR:
  - Generate temperature-independent reference voltage
- Only circuit implementation was performed (no detailed analysis).

---

---

---

## Day 2 Summary
* Completed the design and analysis of a MOS differential amplifier.
* Verified that all transistors were biased in the saturation region.
* Analyzed gain and bandwidth through AC and Transient simulations.
* Created a functional OTA symbol for future hierarchical design work.


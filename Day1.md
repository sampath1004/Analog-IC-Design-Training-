# Analog-IC-Design-Training-
# Day 1: MOSFET Fundamentals & Mixed-Signal Basics

## 1. MOSFET Operating Regions
We started the session by looking at how a MOSFET behaves as we change the voltages. The first state is **Cutoff**, where the gate-to-source voltage ($V_{GS}$) is less than the threshold ($V_{TH}$). In this state, the device is essentially an open circuit and no current flows.

Once $V_{GS}$ is high enough to turn the device on, it enters the **Triode (Linear) Region** if the drain voltage is low. Here, the MOSFET acts like a resistor. The current is calculated as:
$I_D = \mu_n C_{ox} \frac{W}{L} [ (V_{GS} - V_{TH}) V_{DS} - \frac{V_{DS}^2}{2} ]$

As we increase the drain voltage further, the device enters **Saturation** when $V_{DS} \ge V_{GS} - V_{TH}$. This is where the channel "pinches off" near the drain, and the MOSFET begins to act as a stable current source. To account for real-world effects like Channel Length Modulation, we use the formula:
$I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{TH})^2 (1 + \lambda V_{DS})$
The $\lambda$ term is important because it shows that even in saturation, the current rises slightly as $V_{DS}$ increases.



## 2. Mixed-Signal Design Challenges
We discussed why "Mixed-Signal" chips—which combine analog and digital parts—are so difficult to design. The main issue is that digital switching creates noise that can interfere with sensitive analog signals. To keep the chip working reliably, we need "anchor" blocks like the **LDO** for clean power, the **PLL** for steady timing, and the **BGR** to provide a constant reference voltage that doesn't drift when the battery voltage or temperature changes.

## 3. The Bandgap Reference (BGR)
The highlight of the day was learning how to create a voltage reference that stays stable even as the chip heats up. We do this by combining two different voltage types that react to temperature in opposite ways.

First, we use a **CTAT (Complementary to Absolute Temperature)** voltage. This is usually the $V_{BE}$ of a bipolar transistor, which naturally drops by about $-1.5mV$ for every degree the temperature rises. To cancel this out, we add a **PTAT (Proportional to Absolute Temperature)** voltage, which is the difference between two BJTs ($\Delta V_{BE} = V_T \ln n$). This voltage increases as it gets hotter.



By carefully summing these two together, the downward slope of the CTAT cancels the upward slope of the PTAT. This creates a rock-solid output of about **1.2V**, which is the bandgap of silicon. We use BJTs for this even in CMOS designs because they are much more predictable than MOSFETs when it comes to temperature changes.

## Hands-on Session

- A **Common-Source (CS) amplifier** was designed and simulated using **Cadence Virtuoso**.
- The design helped in understanding:
  - Biasing techniques
  - Gain behavior
  - MOSFET operation in saturation region

- Hands-on experience was gained in:
  - Schematic entry using Virtuoso
  - Simulation setup
  - Running analyses
  - Observing voltage and gain characteristics

 # Circuit 1 : CS amplifier 
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0000.jpg" />


# DC Analysis 
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0005.jpg" />

# DC Sweep wrt Rd
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0003.jpg" />

# DC Sweep wrt Vin
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0002.jpg" />

# Transient Analysis 
<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0006.jpg" />

# AC Analysis 

<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0004.jpg" />

# Parametric analysis

<img width="1600" height="900" alt="image" src="https://github.com/sampath1004/Analog-IC-Design-Training-/blob/main/IMG-20260128-WA0001.jpg" />

---
# conclusion
Day 1 was all about moving from textbook theory to actual design work. We started by learning how to keep a MOSFET in the "saturation" region to get the best amplification, and why blocks like BGRs and LDOs are necessary to keep a chip stable. The highlight was the hands-on session where we used Cadence Virtuoso to build a Common-Source amplifier. By running different tests—like DC, transient, and parametric sweeps—we saw exactly how changing a single resistor or bias voltage can completely change the amplifier's gain and performance.

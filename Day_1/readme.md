# Analog IC Design Workshop – Day 1  
## Common Source (CS) Amplifier Biasing Techniques using Cadence Virtuoso  

This report summarizes the work completed on **Day 1** of the *Analog IC Design and Layout Considerations* workshop.  

The main objective was to design, simulate, and compare different **Common Source (CS) amplifier** configurations using multiple load and biasing techniques in Cadence Virtuoso.

---

## Objective

The goals of this session were:

- To understand the operation of a Common Source amplifier  
- To study various load and biasing approaches  
- To evaluate:
  - DC operating point  
  - Small-signal gain  
  - Output voltage swing  
  - Bias stability  
- To identify suitable CS amplifier topologies for analog IC applications such as LDOs and Bandgap References  

---

## Circuits Implemented

1. CS Amplifier with Resistor Load (RD)  
2. CS Amplifier with PMOS Diode-Connected Load  
3. CS Amplifier with PMOS Biased (Active) Load  

---

# 1. CS Amplifier with Resistor Load (RD)

## Circuit Description
- NMOS transistor configured in common-source mode  
- Drain connected to resistor RD  
- Source connected to ground  
- Gate driven by input signal  

## Theory
- Drain current depends on VGS and RD  
- Small-signal gain:  

  Av = -gm × RD  

- Output swing is limited due to voltage drop across RD  

## Design Parameters

| Parameter | Value |
|-----------|--------|
| VDD | 1 V |
| RD | Sweep (Best ≈ 5 kΩ) |
| NMOS W/L | 120 nm / 45 nm |
| NMOS Bias Voltage | 0.6 V |
| Input Amplitude | 50 mV |
| Input Frequency | 1 kHz |

## Simulation Observations
- DC Operating Point (Vout): To be added  
- Drain Current (ID): To be added  
- Small-Signal Gain (Av): 3.25 V/V  
- Output Swing: 520 mV to 840 mV  

## Inference
- Bias strongly depends on resistor value and process variations  
- Limited gain and output range  
- Not suitable for modern integrated analog design  

All related images are available in:  
`Day_1/CS_with_Rd`

---

# 2. CS Amplifier with PMOS Diode-Connected Load

## Circuit Description
- Resistor replaced with PMOS diode-connected load  
- PMOS gate and drain shorted  
- Provides self-biasing mechanism  

## Theory
- PMOS acts as a nonlinear resistive load  
- Small-signal gain:  

  Av = -gmn / gmp  

- Offers improved bias stability compared to RD load  

## Design Parameters

| Parameter | Value |
|-----------|--------|
| VDD | 1 V |
| PMOS W/L | 925 nm / 45 nm |
| NMOS W/L | 120 nm / 45 nm |
| NMOS Bias Voltage | 600 mV |
| Input Amplitude | 50 mV |
| Input Frequency | 1 kHz |

## Simulation Observations
- DC Operating Point (Vout): 403 mV  
- Drain Current (ID): 2.323 µA  
- Small-Signal Gain (Av): 0.65 V/V  
- Output Swing: 470 mV to 530 mV  

## Inference
- Better bias stability than resistor load  
- Moderate voltage gain  
- Commonly used in current mirrors and bias circuits  

All related images are available in:  
`Day_1/CS_with_Diode_Connected_PMOS`

---

# 3. CS Amplifier with PMOS Biased Load (Active Load)

## Circuit Description
- PMOS gate biased using fixed voltage  
- PMOS behaves as a current source  
- High output resistance at the drain node  

## Theory
- Small-signal gain:  

  Av = -gm × (ron || rop)  

- Provides highest theoretical gain among the three configurations  

## Design Parameters

| Parameter | Value |
|-----------|--------|
| VDD | 1 V |
| PMOS Bias Voltage | 400 mV |
| PMOS W/L | 1 µm / 45 nm |
| NMOS W/L | 120 nm / 45 nm |
| NMOS Bias Voltage | 600 mV |
| Input Amplitude | 25 mV |
| Input Frequency | 1 kHz |

## Simulation Observations
- DC Operating Point (Vout): To be added  
- Drain Current (ID): To be added  
- Small-Signal Gain (Av): 0.4 V/V  
- Output Swing: 964 mV to 984 mV  

## Inference
- Higher gain potential compared to other loads  
- Improved bias stability  
- Preferred configuration for LDOs, Op-Amps, and Bandgap Reference circuits  

All related images are available in:  
`Day_1/CS_with_Active_Load_PMOS`

---

# Comparison Summary

| Parameter | RD Load | PMOS Diode Load | PMOS Biased Load |
|------------|------------|------------------|------------------|
| Gain | 3.25 V/V | 0.65 V/V | To be added |
| Bias Stability | Low | Medium | High |
| Power Efficiency | Low | Medium | High |
| IC Suitability | No | Partial | Yes |

---

# Conclusion – Day 1

- The CS amplifier with RD load is useful for fundamental understanding  
- The diode-connected PMOS load improves bias stability and IC compatibility  
- The PMOS biased active load provides better performance for analog IC design  
- This topology serves as the foundation for LDO and Bandgap Reference circuit design  

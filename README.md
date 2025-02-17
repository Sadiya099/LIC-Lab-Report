# Linear Integrated Circuits Lab Report
# Experiment 1: ANALYSIS OF CS AMPLIFIER
# Introduction
A Common Source (CS) amplifier, optimized for low-power applications, is designed and analysed using a 180nm TSMC MOSFET in LTSpice. To evaluate the amplifier's DC operating point, voltage gain, bandwidth, and power consumption, it employs data from DC, AC and transient analyses while operating at VDD = 1.8V and with a 90W power budget. Low-power VLSI systems are made more efficient with a combination of high gain and wide bandwidth, which minimizes power consumption.
# Aim
 To analyse the common source amplifier using 180nm tsmc  cmos n-mosfet for a given V_DD = 1.8V & determine bandwidth , gain, DC operating point, power and draw its frequency response.
# Component required 
* 180nm tsmc nmos
* Capacitors
* Resistors
* Voltage Supply
# Theory
The MOSFET structure has become the most important device structure in the Electronics industry. It dominates the integrated circuit technology in Very Large Scale Integrated (VLSI) digital circuits based on n-channel MOSFETs and Complementary n- Channel and p-channel MOSFETs (CMOS). The technical importance of the MOSFET results from Its low power consumption, simple geometry, and small size, resulting in very high packing Densities and compatibility with VLSI manufacturing technology. Two of the most popular Configurations of small-signal MOSFET amplifiers are the common source and common drain Configurations. The common source circuit is shown below. The common sources, like all MOSFET amplifiers, have the characteristic of high input impedance. High input impedance is Desirable to keep the amplifier from loading the signal source. This high input impedance is Controlled by the bias resistors R1 and R2). Normally the value of the bias resistors is chosen as High as possible. However, too big a value can cause a significant voltage drop due to the gate Leakage current. A large voltage drop is undesirable because it can disturb the bias point. For Amplifier operation the MOSFET should be biased in the active region of the characteristics. 
# Circuit Design:
![circuit design](https://github.com/user-attachments/assets/48551f4f-737d-4d12-85d9-1abed4b2f0ad)


# Sample values
Given that V_DD = 1.8 V, Power budget = 90µW and 180nm tsmc nmos.

Let's assume the values of RD, RS, R1, R2, RL such that the FET should be in **SATURATION REGION**

i.e, V_GS > V_TH  and V_DS > V_OV.

**Assumed Values**

**Resister Values**

RD = 2k ohm, RS = 680 ohm, RL = 1k ohm, R1 = 100k ohm, R2 = 60k ohm

**Capacitors Values**

C1, C2 (coupling capacitors) = 1uF
Cs (bypass capacitors) = 10uF

**To Find Current ID**

P = V_DD × ID

ID = 90µW / 1.8V

ID = 50 µA

# Transient Analysis

**Input Characteristics:**
![input trs](https://github.com/user-attachments/assets/c5afcd92-a08b-4b30-96d3-2234ae4ab50e)

**Output Chracteristics:**
![output trs](https://github.com/user-attachments/assets/3cc59ee7-79ea-446c-9c71-cfad7ef6b27e)

**Input and Output Chracteristics:**
![input vs output](https://github.com/user-attachments/assets/4f8e9aa4-7dcc-4f67-8d13-89b97659d588)

# DC Analysis

![DC analya](https://github.com/user-attachments/assets/8d32eed2-33fa-486b-8d70-6c398711df5d)

# AC Analysis

**Vout/Vin**

![AC analysis_1](https://github.com/user-attachments/assets/9c8e39e9-c186-4ba6-9b73-b2d5d2c8e2d3)

**Vout/Vin in dB**

![ACCC](https://github.com/user-attachments/assets/45e5483f-a4a3-4517-b7a4-c9a19f10acc3)

# Result

# Extracting Parameters Using LTspice

**DC OPERATING POINTS**

![op](https://github.com/user-attachments/assets/6c4d54bf-c8f6-4d41-aed0-811a1a752e14)

**POWER DISSIPIATION**

Vin = 0 W

VDD = 90.2 µW

RD = 3.02 µW

RS = 1.02 µW

R1 = 12.65 µW

R2 = 7.59 µW

**GAIN in dB**

Av = Vout / Vin

Av ~ 29dB

**BAND WIDTH**

BW = FH – FL

BW = 350M Hz - 1k Hz

BW = 3.49M Hz

**DC ANALYSIS**

Conditions for nmos to be in Saturation Region  V_GS > V_TH , V_DS > V_OV

VTH = 0.36 v (given in nmos model), VDD = 1.8 v, VG= 0.675 v, VS = 0.026 v, VD = 1.72 v.

V_GS = VG – VS

V_GS = 0.675 – 0.026

V_GS = 0.649 v

Hence VGS > VTH 

V_OV = VGS – VTH

V_OV = 0.649 – 0.36

V_OV = 0.289 v

V_DS = VD – VS 

V_DS = 1.72 – 0.026

V_DS = 1.694 v

Hence V_DS > V_OV 

Therefore fet is in Saturation Region.

# Inference

DC Operating Point Analysis:
The transistor operates within the saturation region if , it ensuring right amplification.

**DC Sweep Analysis:**
By simulation I saw the transfer characteristics of  V_GS in DC Analysis. 

**AC Analysis (Gain in dB):**
By Simulation I saw the frequency response of Cs amplifier and learnt how to find Gain 

**Transient Analysis:**
By Simulation I saw the output waveform and input waveform and output waveform have minimum distortion. 

Overall I learnt Transient Analysis, DC Analysis,  AC Analysis using LTSpice.

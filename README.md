# Linear Integrated Circuits Lab Report
# Experiment 1: CS AMPLIFIER
# Introduction
A Common Source (CS) amplifier, optimized for low-power applications, is designed and analysed using a 180nm TSMC MOSFET in LTSpice. To evaluate the amplifier's DC operating point, voltage gain, bandwidth, and power consumption, it employs data from DC, AC and transient analyses while operating at VDD = 1.8V and with a 50W power budget. Low-power VLSI systems are made more efficient with a combination of high gain and wide bandwidth, which minimizes power consumption.
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
Given that V_DD = 1.8 V, Power budget = 50µW and 180nm tsmc nmos.

Let's assume the values of RD, RS, R1, R2, RL such that the FET should be in SATURATION REGION

i.e, V_GS > V_TH  and V_DS > V_OV.

Assumed Values

RD = 2k ohm, RS = 680 ohm, RL = 1k ohm, R1 = 100k ohm, R2 = 60k ohm

Capacitors Values 

C1, C2 (coupling capacitors) = 1uF
Cs (bypass capacitors) = 10uF

To Find Current ID

P = V_DD × ID

ID = 50µW / 1.8V

ID = 27.74 µA

# Transient Analysis

Input Characteristics:
![input trs](https://github.com/user-attachments/assets/c5afcd92-a08b-4b30-96d3-2234ae4ab50e)

Output Chracteristics:
![output trs](https://github.com/user-attachments/assets/3cc59ee7-79ea-446c-9c71-cfad7ef6b27e)




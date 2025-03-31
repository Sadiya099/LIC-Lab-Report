![partB DC op](https://github.com/user-attachments/assets/67156843-479c-4832-9a72-7c3f24874d77)# EXPERIMENT 6: CURRENT MIRROR CIRCUITS

### AIM: Design , analyze, and simulate a current mirror circuit used as active load in an amplifier circuit and Using LTspice to simulate circuit behavior and evaluating the impact of channel length variation (Lmin = 180nm, L = 500nm) on performance. Varying the current mirror ratio and analyzing its effect on circuit performance.

## THEORY

![image](https://github.com/user-attachments/assets/67bea55c-71ea-44cb-abac-dc2432f5bfe5)

A current mirror is a circuit that replicates a reference current through one transistor to another, ensuring a constant current in different branches. It is commonly used in analog circuits for biasing and as an active load in amplifiers. In MOSFET-based current mirrors, two transistors operate in saturation, maintaining equal gate-source voltages, which results in the mirrored current being proportional to the reference current. If the transistors have the same aspect ratio, the mirrored current equals the reference current. Current mirrors are widely used in voltage references, differential amplifiers, and other analog applications to maintain stable and accurate currents.

## Design Question

![image](https://github.com/user-attachments/assets/28a17dea-9350-4950-9288-b9b19d7cfbc3)

![image](https://github.com/user-attachments/assets/9fb443a2-f051-4fc1-8f34-4e6e49a9fdfc)

## Circuit Analysis

GIVEN:

VDD = 1.8V

P <= 1mW

AV > -10v/v

PART A

I_TOTAL = P/VDD

I_TOTAL  <= 1mW/1.8V

I_TOTAL  <= 0.555mA

For 1:1 Current mirror ratio:

 Iref = Ix = I_TOTAL/2

Iref = 0.2775mA & Ix = 0.2775mA

W/L = 16.66

THE ASPECT RATIO'S OF MOSFET FOR 1:1 CURRENT MIRROR:

M1 = 3um/180nm VGS = 0.858V

M2 = 3um/180nm

M3 = 3um/180nm 

For 1:2 Current mirror ratio:

 Iref  = I_TOTAL/3

Ix = 2 * Iref

Iref = 0.185mA & Ix = 0.370mA

W/L for M1 and M2 = 33.33

W/L for M3 = 16.66

THE ASPECT RATIO'S OF MOSFET FOR 1:2 CURRENT MIRROR:

M1 = 6um/180nm VGS = 0.783V

M2 = 6um/180nm

M3 = 3um/180nm 

## SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:1 MIRROR RATIO.

### CIRCUIT DIAGRAM 

![image](https://github.com/user-attachments/assets/fdd1b528-051a-45ea-b527-b401c320c81d)

### DC ANALYSIS

**DC OPERATING POINTS**

![image](https://github.com/user-attachments/assets/12a5674f-6bff-4193-b260-73ef99fb705c)

**ID M1 = 277.5uA , ID M2 = 277.5uA , ID M3 = 277.5uA**

### TRANSIENT ANALYSIS

**Max Output Swing** 

![image](https://github.com/user-attachments/assets/e7ea1fe7-9153-4760-b2ce-1e698345e6eb)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 45mV.

**The Gian from The Transient Analysis is -10.06 V/V.**

### AC ANALYSIS

![image](https://github.com/user-attachments/assets/4b827664-340d-4e40-8ebc-e7c168d1061d)

**Gain in dB is 21.4dB & Bandwidth is 2.48GHz**

## SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:2 MIRROR RATIO.

### CIRCUIT DIAGRAM 

![image](https://github.com/user-attachments/assets/22552ea9-e7eb-4d12-b748-f4759f67b524)

### DC ANALYSIS

**DC OPERATING POINTS**

![image](https://github.com/user-attachments/assets/37a0a9be-1e4d-4180-822c-d5b693aa55ca)

**ID M1 = 370.4uA , ID M2 = 370.4uA , ID M3 = 185uA**

### TRANSIENT ANALYSIS

**Max Output Swing** 

![image](https://github.com/user-attachments/assets/0df73717-af0f-43b6-86f0-0755a2c81a3e)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 45mV.

**The Gian from The Transient Analysis is -10.133 V/V.**

### AC ANALYSIS

![image](https://github.com/user-attachments/assets/13c83a38-c2f5-4b5d-891b-8fc1f7798fc0)

**Gain in dB is 20.7dB & Bandwidth is 1.713GHz** .

## PART B:DESIGN OF DIFFERENTIAL AMPLIFIER USING CURRENT MIRROR

The circuit have six MOSFETs (M1 to M6) with distinct (W/L) ratios, designed to operate in the saturation region to maintain accurate current mirroring and signal amplification. 

### CIRCUIT DESIGN 

![part B circuot diagrzm](https://github.com/user-attachments/assets/b0a5af31-e25c-453e-8c11-545eac749b73)

### DC ANALYSIS

**DC OPERATING POINTS**

![partB DC op](https://github.com/user-attachments/assets/327d383a-fd52-4655-969c-3f28ee716ef5)


### TRANSIENT ANALYSIS

**INPUT AND OUTPUT**

![trs part b](https://github.com/user-attachments/assets/99a55790-5503-45d4-8151-fca441689503)

Gain = Vopp/Vinpp 

Gain  =(2.06-1.30)V/(1.67-1.63)V

Gain  = 19V/V

Gain in dB = 25.67

### AC ANALYSIS

![AC analysis part b](https://github.com/user-attachments/assets/91ee3ad9-13ed-4c67-908c-5ccec9a4dfd6)

**Gain is 26.00dB**

## RESULT

### PERFORMANCE COMPARISION TABLE WRT CURRENT MIRROR RATIO:

![liccc](https://github.com/user-attachments/assets/8553e25a-5d61-4a63-b55d-d2d5b4fe83ca)

## INFERENCE

From the experiment and simulations, the following technical inferences can be drawn regarding the Current Mirror Load Common Source Amplifier and the impact of varying the current mirror ratio:

1. Impact of Current Mirror Ratio on Gain and Bandwidth

As the current mirror ratio increases, the gain increases, as seen from the values in the comparison table:

1:1 ratio → Gain = -10.06 V/V

1:2 ratio → Gain = -10.133 V/V

And , as gain increases, bandwidth decreases significantly due to the trade-off between gain and frequency response:

1:1 ratio → Bandwidth = 2.48 GHz

1:2 ratio → Bandwidth = 1.713 GHz

The higher gain reduces the bandwidth because increasing the W/L ratio of the MOSFETs increases capacitance, which limits high-frequency response.

2. Voltage Variations and Threshold Effects

The gate-source voltage (VGS) decreases as the current mirror ratio increases:

1:1 ratio → VGS = 0.858V

1:2 ratio → VGS = 0.783V

This happens because, in a current mirror, the MOSFET aspect ratio (W/L) is adjusted to achieve the required current ratio.

A lower VGS suggests that the MOSFETs are operating deeper in the saturation region, which improves current replication accuracy.

3. Effect of MOSFET Aspect Ratio (W/L)

As the current mirror ratio increases, the W/L ratio of the current mirror transistors (M1, M2) increases significantly:

1:1 ratio → (M1, M2) = 3µm/180nm

1:2 ratio → (M1, M2) = 6µm/180nm

Increasing W/L improves current mirroring accuracy but increases parasitic capacitance, affecting speed and stability.

4. Current Accuracy

From the DC Analysis, it is observed that ID (drain current) values closely match the expected current mirror ratios:

For 1:1 ratio:

IREF = 277.5 µA, IX (mirrored current) = 277.5 µA, which is  1:1 ratio.

For 1:2 ratio:

IREF = 185 µA, IX (mirrored current) = 370 µA, which is  1:2 ratio.

This confirms that the current mirror circuit effectively replicates the reference current, proving its reliability in biasing applications.

5. Trade-offs Between Gain, Bandwidth

Higher current mirror ratios provide more gain but reduce bandwidth.

Large W/L ratios enhance current mirroring accuracy but introduce higher parasitic capacitance, affecting high-frequency performance.

The circuit shows 180° phase shift, as expected for a common-source amplifier with active load.

For applications requiring higher bandwidth (e.g., RF amplifiers), a lower current mirror ratio (1:1 or 1:2) is preferable.

## Conclusion

A current mirror circuit replicates a reference current (IREF) through one or more transistors, ensuring a constant output current despite variations in load. It uses MOSFETs in saturation to 
maintain a stable current ratio, which depends on the aspect ratios (W/L) of the transistors. Current mirrors are widely used in analog circuits, such as operational amplifiers and differential 
amplifiers, to provide biasing and active loads. They offer high accuracy, low power consumption, and improved stability in integrated circuits.

















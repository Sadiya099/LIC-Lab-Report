# Experiment 3: DIFFERENTIAL MOS AMPLIFIER

## AIM : Design the MOS differential amplifier circuit and perform DC analysis, Transient analysis, AC analysis using LTSpice.

## THEORY
MOS differential amplifier is a circuit,primarily used to amplify the difference between two input signals while rejecting common-mode noise. It consists of two NMOS transistors with their sources connected together and biased by a current source. The gate terminals receive the differential input signals, while the drain terminals provide the output. The load can be a current source or a resistor or NMOS FET

The circuit operates in the active region, where a small difference in gate voltages results in a significant change in drain currents, generating a differential output voltage. The common-mode rejection ratio (CMRR) is a key advantage, interference affecting both inputs equally is minimized. The gain of the amplifier depends on the transconductance (gm) of the transistors and the load resistance (RD).

To ensure proper operation, the tail current source provides a stable bias current, ensuring that both transistors share current based on the input difference. The NMOS differential amplifier is widely used in operational amplifiers,due to its high gain, stability, and noise rejection.


![image](https://github.com/user-attachments/assets/9eeeb225-6300-4ddd-879a-791b8018dc86)


## COMPONENTS USED 
1. Q1 & Q2 (NMOS Transistors):These form the differential pair and are responsible for amplifying the difference between the two input voltages.

2. I_bias (Current Source): This provides a constant tail current to the differential pair, ensuring proper operation. It sets the total current available for both transistors and controls the amplifier’s gain and biasing.

3. R1 & R2 (Load Resistors): These resistors convert the drain currents of Q1 and Q2 into voltage signals.

4. +V (Supply Voltage): Provides the necessary power for the circuit.

5. Vin1 & Vin2 (Differential Inputs): These are the input signals applied to the gates of Q1 and Q2.

6. Vout1 & Vout2 (Differential Outputs): The output is taken from the drains of Q1 and Q2. The differential output is Vout = Vout1 - Vout2.

### Design Specification : V_DD = 3.3V ,P <= 3mW, Vicm = 1.72V, Vocm = 1.81V, Vp = 0.7V 
### Circuit Analysis
WKT P = V_DD * I_SS

I_SS = P / V_DD = 3mW / 3.3V = 0.91mA

I_D1 = I_D2 = I_SS / 2 = 0.91mA / 2 = 0.455mA

R_SS = Vp / I_SS = 0.7V / 0.91mA = 769.230 ohm

R_D = (V_DD - Vocm) / I_D1 = (3.3V - 1.81V) / 0.455mA  = 3.274k ohm

**Q point (V_DS, I_D)**

V_G = Vicm = 1.72V

V_S = Vp = 0.7V

V_D = Vocm = 1.81V

V_DS = Vocm - Vp = 1.81V - 0.7V = 1.11V

V_GS = Vicm - Vp = 1.72V - 0.7V = 1.02V

**Q point ( 1.11V , 0.455mA)**

## CIRCUIT 1 : With R_SS

### Circuit Diagram 

![circuit1_DCanalysis_diagram](https://github.com/user-attachments/assets/2e445241-465c-4b95-a050-342fc0434e97)

Length(L) and Width(W) values for both NMOS M1 and M2 are 182nm and 2.525um respectively.

**W and L Values**

![circuit1_WandL](https://github.com/user-attachments/assets/46ea3d3b-7b13-49c9-8d51-c67fbf63862e)

## DC Analysis

![DC_operating circuit1](https://github.com/user-attachments/assets/1cd79eb5-610c-4015-91da-fc911f3bc4cb)

![circuitVgsvth](https://github.com/user-attachments/assets/7b5da7b7-74af-479b-93bd-e10686163206)

By Considering Circuit Analysis which made earlier we can say that

I_SS = 0.91mA

R_D = 3.274k ohm

R_SS = 769.230 ohm

V_DS = 1.11V

V_GS = 1.02V

V_th = 0.48V

V_OV = V_GS - V_th = 1.02V - 0.48V = 0.54V 

For Saturation region V_DS > V_OV 

i.e., 1.11V > 0.54V 

gm = ID/2*Vov = 0.455mA/2 * 0.54 = 0.8425 mA/V

Small Signal gain Av = gm * R_d = 0.8425mA *3.274kohm = 2.758

Therefore FET is in saturation region.

**If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then**

![circuit1_opincres](https://github.com/user-attachments/assets/989ab963-ad82-46ca-bb50-4f44e5cb2fe4)

Vocm decreases slightly to 1.686 

Vp slightly increases to 0.758 due to adjust the current balance

Q point also has slight changes and becomes (0.92V , 0.492mA)

## Transient Analysis

**INPUT and OUTPUT Waveform**

![circuit1_trs](https://github.com/user-attachments/assets/5241215d-8e73-4750-88f1-979f0201619e)


Vicm p-p = 1.7682188V - 1.67182V = 0.0963988V

Vocm p-p = 1.8705374 - 1.7505557 = 0.1199817V

Av = Vocm p-p / Vicm p-p = 0.1199817V / 0.0963988V = 1.2446

Av = 1.2446

Gain in dB = 20*log(1.2446) 

Gain in dB = 1.900dB

## AC Analysis

![acanalyasi CIRcuit](https://github.com/user-attachments/assets/73f34049-0932-4525-998c-00afee7d7c75)

Gain in dB is 1.900dB

by this we can say that gain obtained is exactly equal to theoretical value.

### Maximum Input and Output Swing 

Vicm_max = V_DD - (I_SS*R_D)/2 + Vth = 3.3V - (0.91mA * 3.274kohm)/2 + 0.48V = 2.293V

Vocm_max = V_DD - (I_D*R_D) = 3.3V - (0.455mA * 3.274kohm) = 1.811V

## Differential Input and Differential Output

![diff in out cir1](https://github.com/user-attachments/assets/df344bb6-cd32-49d0-aa7f-bf47b9eb6349)

Vin(diff) = 0.1999V

Vout(diff) = 0.637241V

Av(diff) = Vout/Vin = 3.1878

![Difff circuit 1](https://github.com/user-attachments/assets/b583733d-6c20-40af-88bb-15e05e2cbd93)

## Differential gain

Gain(diff) in dB = 20 * log(Av(diff)) = 20 * log(3.1878) 

Gain(diff) in dB = 10.069

![diff gain cir1](https://github.com/user-attachments/assets/8f3b15e2-a70e-4dfe-a18d-50763b47514e)

by this we can say that gain is equal to the theoretical value.

## CIRCUIT 2 : With I_SS

### Circuit Diagram 

![circuit_2 diagram](https://github.com/user-attachments/assets/d9593b35-26a5-449b-9387-6df8cf9d64d2)

Length(L) and Width(W) values for both NMOS M1 and M2 are 182nm and 2.525um respectively.

**W and L Values**

![circuit1_WandL](https://github.com/user-attachments/assets/56b0a27e-8817-46f6-bb66-2f1fa6f5d18d)

## DC Analysis

![circuit2 dcop](https://github.com/user-attachments/assets/f0634014-9355-4bc7-8523-efa90391db33)

![circuit2 dcvgsvds](https://github.com/user-attachments/assets/d59d581b-8038-48b6-8933-b5853e88e9d5)

By Considering Circuit Analysis which made earlier we can say that

I_SS = 0.91mA

R_D = 3.27444k ohm

R_SS = 769.230 ohm

V_DS = 1.11V

V_GS = 1.02V

V_th = 0.48V

V_OV = V_GS - V_th = 1.02V - 0.48V = 0.54V 

For Saturation region V_DS > V_OV 

i.e., 1.11V > 0.54V 

Therefore FET is in saturation region.

gm = ID/2*Vov = 0.455mA/2 * 0.54 = 0.8425 mA/V

Small Signal gain Av = gm * R_d = 0.8425mA *3.274kohm = 2.758

**If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then**

![Circuit@2](https://github.com/user-attachments/assets/49b2ecdb-a5dd-493b-814a-064a42b6b4af)

Vocm remains as it is that is 1.810V

Vp increases to 0.795 due to adjust the current balance

Q point also has slight changes and becomes (1.01V , 0.455mA)

## Transient Analysis

**INPUT and OUTPUT Waveform**

![Cir_2 trs](https://github.com/user-attachments/assets/e0209c43-c953-4c8f-bba3-cea54980a4e1)

from the graph we can see 180 degree phase shift in the Vocm.

Vicm p-p = 1.77V - 1.67V = 0.1V

Vocm p-p = 1.97 - 1.65 = 0.32V

Av = Vocm p-p / Vicm p-p = 0.32V / 0.1V = 3.2

Av = 3.2

Gain in dB = 20*log(3.2) 

Gain in dB = 10.10 dB

## AC Analysis

![ACAC circuit 2](https://github.com/user-attachments/assets/0ac594c5-cdad-4293-b43b-5dc5a38ca327)

Gain in dB is 10.10 dB

To find 3dB gain 

10.10 dB - 3 dB = 7.1dB

by this we can say that gain obtained is almost equal to theoretical value.

### Maximum Input and Output Swing 

Vicm_max = V_DD - (I_SS*R_D)/2 + Vth = 3.3V - (0.91mA * 3.274kohm)/2 + 0.48V = 2.293V

Vocm_max = V_DD - (I_D*R_D) = 3.3V - (0.455mA * 3.274kohm) = 1.811V

## Differential Input and Differential Output

![Circuit2 diff input output](https://github.com/user-attachments/assets/b6f7d4fe-3133-4528-accc-8174f1b08360)


Vin(diff) = 0.1999V

Vout(diff) = 0.637308V

Av(diff) = Vout/Vin = 3.18814

![circuit2_diffgaincal](https://github.com/user-attachments/assets/a67ee3df-6211-4730-a4e2-5176636d41f2)

## Differential gain

Gain(diff) in dB = 20 * log(Av(diff)) = 20 * log(3.18814) 

Gain(diff) in dB = 10.070

![AC diff gain circuit2](https://github.com/user-attachments/assets/a8ac4dab-27eb-4c76-82e9-05cfc846347d)

by this we can say that gain is almost equal to the theoretical value.

## CIRCUIT 3 : With NMOSFET

### Circuit Diagram 

![circuit3 diagram](https://github.com/user-attachments/assets/61620532-c169-4f9f-b793-e972a0adc117)

Length(L) and Width(W) values for both NMOS M1 and M2 are 182nm and 2.525um respectively.

**W and L Values**

![circuit1_WandL](https://github.com/user-attachments/assets/56b0a27e-8817-46f6-bb66-2f1fa6f5d18d)

**W and L Value for M3**

![W and L for circuit3](https://github.com/user-attachments/assets/35742aa2-0593-4ea9-b8ba-7f23bc38d27e)

## DC Analysis

![circuit3 dcop](https://github.com/user-attachments/assets/d8962942-e9b8-4edf-8d07-5e0df7b06d41)

![Circuit3 vgsvth](https://github.com/user-attachments/assets/2b842c14-47da-4003-8029-25f15c4bd2ba)

By Considering Circuit Analysis which made earlier we can say that

I_SS = 0.91mA

R_D = 3.27444k ohm

R_SS = 769.230 ohm

V_DS = 1.11V

V_GS = 1.02V

V_th = 0.48V

V_OV = V_GS - V_th = 1.02V - 0.48V = 0.54V 

For Saturation region V_DS > V_OV 

i.e., 1.11V > 0.54V 

Therefore FET is in saturation region.

gm = ID/2*Vov = 0.455mA/2 * 0.54 = 0.8425 mA/V

Small Signal gain Av = gm * R_d = 0.8425mA *3.274kohm = 2.758

**V3 = Vp + Vth = 0.7 + 0.366 = 1.066**

**If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then**

![circiutjvb3](https://github.com/user-attachments/assets/13e5d200-ad46-4f6c-896e-7a31c4bddf09)

Vocm slightly decreases that is 1.789V

Vp increases to 0.789 due to adjust the current balance

Q point also has changes and becomes (1V , 0.461mA)

## Transient Analysis

**INPUT and OUTPUT Waveform**

![trs circuit3](https://github.com/user-attachments/assets/b8c7d8bf-f7f1-49cb-8ed4-fc20b50b7eb7)

from the graph we can see 180 degree phase shift in the Vocm.

Vicm p-p = 1.77V - 1.67V = 0.1V

Vocm p-p = 1.96 - 1.65 = 0.31V

Av = Vocm p-p / Vicm p-p = 0.31V / 0.1V = 3.

Av = 3.1

Gain in dB = 20*log(3.1) 

Gain in dB = 9.82 dB

## AC Analysis

![AC circit3](https://github.com/user-attachments/assets/859154ba-f084-4592-94e1-ca0bc47838f1)


Gain in dB is apporx 9.82 dB

To find 3dB gain 

9.82 dB - 3 dB = 6.82dB

by this we can say that gain obtained is almost equal to theoretical value.

### Maximum Input and Output Swing 

Vicm_max = V_DD - (I_SS*R_D)/2 + Vth = 3.3V - (0.91mA * 3.274kohm)/2 + 0.48V = 2.293V

Vocm_max = V_DD - (I_D*R_D) = 3.3V - (0.455mA * 3.274kohm) = 1.811V

## Differential Input and Differential Output

![Circuit input Diff output](https://github.com/user-attachments/assets/4f965f70-316e-4aaa-8fb7-a7732c855e50)


Vin(diff) = 0.199992V

Vout(diff) = 0.637542V

Av(diff) = Vout/Vin = 3.18784

![circuit3333333](https://github.com/user-attachments/assets/73780a09-71f6-412b-a3a3-73f22f635830)


## Differential gain

Gain(diff) in dB = 20 * log(Av(diff)) = 20 * log(3.18784) 

Gain(diff) in dB = 10.06 dB

![cirrrr33333](https://github.com/user-attachments/assets/1cb62a65-c385-4681-88a2-ac0d239622c5)

by this we can say that gain is almost equal to the theoretical value.

## Result 

**Circuit 1 :** 

We will use here Resistor(RSS)

If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then

Vocm decreases slightly 

Vp slightly increases 

Q point also has slight changes and becomes (0.92V , 0.492mA) here V_DS decreases

**Circuit 2:**

We will use here Current(I_SS)

If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then

Vocm remains as it is .

Vp increases  .

Q point also has slight changes and becomes (1.01V , 0.455mA) here V_DS decreases

**Circuit 3:**

We will use here FET(NMOS)

If the value of Vicm increases from 1.72 to 1.82 i.e, increased by 0.1V then

Vocm slightly decreases 

Vp increases 

Q point also has changes and becomes (1V , 0.461mA) here V_DS decreases

## INFERENCE

Performed Transient Analysis,dc analysis,ac anlysis.

Resistor as Current Source:

DC: Bias point varies with supply/resistor tolerances.

AC: Lower gain and poorer common-mode rejection.

Conclusion: Simple but not suitable for high-precision or high-gain applications.


Ideal Current Source:

DC: Perfectly stable biasing.

AC: Maximum differential gain and excellent CMRR.

Conclusion: Sets the performance benchmark but is impractical to implement directly.


NMOS as Current Source:

DC: Provides stable biasing close to the ideal case.

AC: High differential gain and improved CMRR, nearly matching the ideal source.

Conclusion: Offers a practical and balanced approach, making it the preferred choice in most real-world differential amplifier designs.



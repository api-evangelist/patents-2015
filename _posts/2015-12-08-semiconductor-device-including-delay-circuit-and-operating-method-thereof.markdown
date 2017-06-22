---

title: Semiconductor device including delay circuit and operating method thereof
abstract: A semiconductor device includes a calibration code generation circuit suitable for generating a calibration code by adjusting a period of a short-term oscillation signal oscillating at a period less than a reference period, based on a reference oscillation signal oscillating at the reference period; and a delay circuit suitable for setting a delay value based on the calibration code.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09531362&OS=09531362&RS=09531362
owner: SK Hynix Inc.
number: 09531362
owner_city: Gyeonggi-do
owner_country: KR
publication_date: 20151208
---
The present application claims priority of Korean Patent Application No. 10 2015 0087250 filed on Jun. 19 2015 which is incorporated herein by reference in its entirety.

Exemplary embodiments of the present invention relate to a semiconductor design technology and more particularly to a semiconductor device including a delay circuit.

Delay circuits are included in a semiconductor device using an inverter chain in which inverters coupled in series or using a resistor capacitor RC delay circuit. The inverter chain delays a signal by using gate delays i.e. transmission delays of transistors forming the inverters. The characteristics of the transistors in the semiconductor device are changed by Process Voltage Temperature PVT variation. Furthermore the transistors arranged in the semiconductor device may show undesired characteristics due to a difference between gate patterning processes of the respective transistors or a difference in dose between implantation processes for determining a threshold voltage. In this case the performance of semiconductor products may be degraded.

Since the RC delay circuit exhibits a smaller skew variation for the PVT variation than the inverter chain implemented with gate delays the RC delay circuit is used in various circuits. A long RC delay circuit having a large delay amount exhibits a small skew variation. On the other hand a short RC delay circuit having a small delay amount exhibits a skew variation greater than that of the long RC delay circuit. Thus the use of the short RC delay circuit is limited.

The long RC delay circuit is also used to determine a refresh operation period in DRAMs. For example a refresh cycle time tRFC used during a refresh operation may be set through the long RC delay circuit having a considerably large delay amount. However considering the efficiency of the circuit area of DRAMs the short RC delay circuit and a circuit using a counter may be used to set the refresh cycle time tRFC. Since an active operation period by the refresh operation is changed due to the PVT variation the retention time of DRAM cells may be changed which makes it difficult to manage the refresh characteristic.

Thus there is a demand for a short RC delay circuit which has a less skew while exhibiting the efficiency of the circuit area of DRAMs.

Various embodiments are directed to a semiconductor device which is capable of Implementing a short RC delay circuit having a relatively less skew and a reduced circuit area.

In an embodiment a semiconductor device may include a calibration code generation circuit suitable for generating a calibration code by adjusting a period of a short term oscillation signal oscillating at a period less than a reference period based on a reference oscillation signal oscillating at the reference period and a delay circuit suitable for setting a delay value based on the calibration code.

In an embodiment an operating method of a semiconductor device including a delay circuit may include generating a reference oscillation signal having a reference period generating a short term oscillation signal having a period less than the reference period outputting a period control code and a calibration code based on the reference oscillation signal and the short term oscillation signal adjusting a period of the short term oscillation signal based on the period control code and setting a delay value of the delay circuit based on the calibration code.

Various embodiments will be described below in more detail with reference to the accompanying drawings. The present invention may however be embodied in different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the present invention to those skilled in the art. Throughout the disclosure like reference numerals refer to like parts throughout the various figures and embodiments of the present invention.

The drawings are not necessarily to scale and in some instances proportions may have been exaggerated to clearly illustrate features of the embodiments. It is also noted that in this specification connected coupled refers to one component not only directly coupling another component but also indirectly coupling another component through an Intermediate component. In addition a singular form may include a plural form as long as it is not specifically mentioned.

Referring to the semiconductor device in accordance with the embodiment of the present invention may include a calibration code generation circuit and a plurality of delay circuits .

The calibration code generation circuit may generate a calibration code CAL CODE by adjusting a period of a short term oscillation signal based on a reference oscillation signal in response to a calibration start signal CAL START. The reference oscillation signal may oscillate at a reference period and the short term oscillation signal may oscillate at a period less than the reference period. The delay circuits may set internal delay values in response to the calibration code CAL CODE. Each of the delay circuits may include an RC delay.

Referring to the calibration code generation circuit may include a calibration operation adjust unit a reference oscillation signal generation unit and a short term oscillation signal generation unit .

The reference oscillation signal generation unit may generate a reference oscillation signal B ROD. The short term oscillation signal generation unit may generate a short term oscillation signal S ROD and adjust a period of the short term oscillation signal S ROD in response to a period control code PRE CAL CODE. Each of the reference oscillation signal generation unit and the short term oscillation signal generation unit may include a ring oscillator delay ROD .

The calibration operation adjust unit may output the period control code PRE CAL CODE or the calibration code CAL CODE in response to the reference oscillation signal B ROD and the short term oscillation signal S ROD. The calibration operation adjust unit may output the period control code PRE CAL CODE to the short term oscillation signal generation unit when the reference period is greater than N times the period of the short term oscillation signal S ROD and output the calibration code CAL CODE to the delay circuits shown in when the reference period is less than or equal to N times the period of the short term oscillation signal S ROD where N is a positive integer.

The calibration operation adjust unit may include a calibration control unit a judgment signal generation unit a detection unit and a counter latch unit .

The judgment signal generation unit may generate a first judgment signal JUDGE PRE which is activated at each reference period of the reference oscillation signal B ROD and generate a second judgment signal JUDGE by delaying the first judgment signal JUDGE PRE.

The counter latch unit may generate a count signal S FLAG by counting the period of the short term oscillation signal S ROD.

The detection unit may compare the first judgment signal JUDGE PRE with the count signal S FLAG and output a detection signal STOP CAL.

The calibration control unit may output the period control code PRE CAL CODE and the calibration code CAL CODE in response to the second judgment signal JUDGE and the detection signal STOP CAL. The calibration control unit may output a count reset signal RESTART for resetting the counter latch unit . Furthermore the calibration control unit may generate an operation start signal RUN ROD for starting operations of the reference oscillation signal generation unit and the short term oscillation signal generation unit . The operation start signal RUN ROD may be used for controlling operations of the judgment signal generation unit and the counter latch unit .

Hereinafter referring to the components of the calibration code generation circuit will be described. In the descriptions for the drawings the description of a reset signal RSTB related to the operation of the entire semiconductor device is omitted.

Referring to the calibration control unit may include an operation start signal generation unit a count reset signal generation unit an update signal generation unit a first code output unit and a second code output unit .

The operation start signal generation unit may generate the operation start signal RUN ROD for starting the operations of the reference oscillation signal generation unit and the short term oscillation signal generation unit shown in . The operation start signal generation unit may activate the operation start signal RUN ROD in response to the calibration start signal CAL START and the count reset signal RESTART and deactivate the operation start signal RUN ROD in response to the second judgment signal JUDGE. In an embodiment the operation start signal generation unit may include an RS latch which receives the calibration start signal CAL START and the count reset signal RESTART as set signals and receives the second judgment signal JUDGE as a reset signal. The RS latch may include a cross coupled NAND latch.

The count reset signal generation unit may generate the count reset signal RESTART for resetting the counter latch unit shown in at a predetermined time after the second judgment signal JUDGE is activated in a state where the detection signal STOP CAL is deactivated. In an embodiment the count reset signal generation unit may include a first inverter INV a first NAND gate NAND and a delay unit . The first inverter INV may invert the detection signal STOP CAL the first NAND gate NAND may perform a NAND operation on an output of the first inverter INV and the second judgment signal JUDGE and the delay unit may delay an output of the first NAND gate NAND and output the count reset signal RESTART.

The update signal generation unit may output the first update signal UPDATE CODE when the second judgment signal JUDGE is activated in a state where the detection signal STOP CAL is deactivated and output the second update signal UPDATE CODE when the second judgment signal JUDGE is activated in a state where the detection signal STOP CAL is activated. In an embodiment the update signal generation unit may include the first inverter INV the first NAND gate NAND a second NAND gate NAND and a second inverter INV. The first inverter INV may invert the detection signal STOP CAL the first NAND gate NAND may perform the NAND operation on the output of the first inverter INV and the second judgment signal JUDGE and output a first update signal UPDATE CODE and the second NAND gate NAND and the second inverter INV may perform an AND operation on the detection signal STOP CAL and the second judgment signal JUDGE and output a second update signal UPDATE CODE.

The first code output unit may output the period control code PRE CAL CODE in response to the first update signal UPDATE CODE. In an embodiment the first code output unit may include counters CNT for up counting the period control code PRE CAL CODE by one bit whenever the first update signal UPDATE CODE is activated.

The second code output unit may output the calibration code CAL CODE in response to the second update signal UPDATE CODE. In an embodiment the second code output unit may output the period control code PRE CAL CODE which is finally generated as the calibration code CAL CODE when the second update signal UPDATE CODE is activated. The second code output unit may include a plurality of flip flops.

Referring to the judgment signal generation unit may include a first judgment signal generation unit and a second judgment signal generation unit .

The first judgment signal generation unit may generate a first judgment signal JUDGE PRE which is activated at each reference period of the reference oscillation signal B ROD. The second judgment signal generation unit may generate a second judgment signal JUDGE by delaying the first judgment signal JUDGE PRE.

In an embodiment the first judgment signal generation unit may include a logic circuit for generating the first judgment signal JUDGE PRE as a pulse signal when the reference oscillation signal B ROD transitions from a logic high level to a logic low level during an active period of the operation start signal RUN ROD and the second judgment signal generation unit may include an inverter chain for delaying the first judgment signal JUDGE PRE by a predetermined time.

The detection unit may synchronize the count signal S FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In an embodiment the detection unit may include a flip flop and an inverter configured to invert an output of the flip flop and output the inverted signal as the detection signal STOP CAL.

Referring to the judgment signal generation unit may include a first judgment signal generation unit and a second judgment signal generation unit .

The first judgment signal generation unit may have substantially the same configuration as the first judgment signal generation unit illustrated in . The second judgment signal generation unit may sequentially delay a first judgment signal JUDGE PRE outputted from the first judgment signal generation unit and generate two or more intermediate signals JUDGE INT and JUDGE INT. Then the second judgment signal generation unit may generate a second judgment signal JUDGE by delaying the final signal JUDGE INT among the intermediate signals.

The detection unit may include a plurality of flip flops coupled in series to each other and an inverter. For example the detection unit may include a first flip flop and two or more second flip flops and . The first flip flop may output the count signal S FLAG in synchronization with the first judgment signal JUDGE PRE and the two or more second flip flops and may sequentially transmit the output of the first flip flop in synchronization with the two or more intermediate signals JUDGE INT and JUDGE INT and output the detection signal STOP CAL.

The detection unit illustrated in may register a plurality of spots at which the count signal S FLAG and the first judgment signal JUDGE PRE meet each other and prepare for metastability based on a timing difference between the count signal S FLAG and the first judgment signal JUDG PRE.

The counter may count the period of the short term oscillation signal S ROD. In an embodiment the counter may include a plurality of shift registers SR coupled in series. The shift registers may sequentially transmit a high level signal VDD in response to low edges of the short term oscillation signal S ROD. The shift registers may be reset in response to the operation start signal RUN ROD.

The transmission unit may output the short term oscillation signal S ROD as an output signal P FLAG when the counting value reaches a predetermined value. In an embodiment the transmission unit may include a NAND gate NAND which performs a NAND operation on an output signal of the counter and the short term oscillation signal S ROD.

The latch unit may output the count signal S FLAG which is set by the output signal P FLAG and reset in response to the count reset signal RESTART. In an embodiment the latch unit may include an RS latch which receives the output signal P FLAG as a set signal and receives the count reset signal RESTART as a reset signal. The RS latch may include a cross coupled NAND latch.

Referring to the reference oscillation signal generation unit may include the reference RC unit and a first output unit .

The reference RC unit may have a relatively lesser skew variation for PVT variation and output an input signal as an output signal having a relatively constant period. The first output unit may selectively output the output signal of the reference RC unit as the reference oscillation signal B ROD in response to the operation start signal RUN ROD. In an embodiment the first output unit may include a NAND gate NAND which performs a NAND operation on the operation start signal RUN ROD and the output signal of the reference RC unit .

Referring to the reference RC unit may delay an input signal IN by a time corresponding to a fixed RC delay value and output the delayed signal as an output signal OUT. Since the reference RC unit has a relatively lesser skew variation for the PVT variation the input signal IN may be outputted as the output signal OUT having a relatively lesser skew variation.

Thus the reference oscillation signal generation unit may output the reference oscillation signal B ROD which has a relatively lesser skew variation for the PVT variation and oscillates at the reference period.

Referring to the short term oscillation signal generation unit may include the calibration RC unit and a second output unit .

The calibration RC unit may calibrate the period of the input signal in response to the period control code PRE CAL CODE and output an output signal having the calibrated period.

The second output unit may selectively output the output signal of the calibration RC unit as the short term oscillation signal B ROD in response to the operation start signal RUN ROD. In an embodiment the second output unit may include a NAND gate NAND and an inverter INV which perform an AND operation on the operation start signal RUN ROD and the output signal of the reference RC unit .

Referring to the calibration RC unit may include a first calibration unit and a second calibration unit . The first calibration unit may calibrate the resistance value of a transmission node of the input signal IN in response to the period control code PRE CAL CODE and the second calibration unit may calibrate the capacitance of the transmission node of the input signal IN in response to the period control code PRE CAL CODE. In an embodiment as calibration is started to sequentially generate the period control code PRE CAL CODE as 00 01 10 11 the RC delay value of the calibration RC unit may gradually increase. That is as the RC delay value of the calibration RC unit is gradually increased to generate an optimal calibration code the calibration time may be reduced.

Referring to when the calibration start signal CAL START is activated the operation start signal generation unit of the calibration control unit may activate the operation start signal RUN ROD for starting the operations of the reference oscillation signal generation unit and the short term oscillation signal generation unit . In response to the operation start signal RUN ROD the reference oscillation signal generation unit may output the reference oscillation signal B ROD which oscillates at the reference period and the short term oscillation signal generation unit may output the short term oscillation signal S ROD which oscillates at a period less than the reference period.

The judgment signal generation unit may generate a pre Judgment signal JUDGE PRE which is activated at each reference period of the reference oscillation signal B ROD and generate a judgment signal JUDGE by delaying the pre judgment signal JUDGE PRE. Furthermore the counter latch unit may generate the count signal S FLAG by counting the period of the short term oscillation signal S ROD. For example when the value obtained by counting the period of the short term oscillation signal R ROD reaches four the counter latch unit may output the count signal S FLAG in synchronization with the short term oscillation signal S ROD which becomes a logic high level.

The detection unit may synchronize the count signal S FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In when the first judgment signal JUDGE PRE toggles to a logic high level the count signal S FLAG may transition to a logic high level. Thus the detection unit may finally output the detection signal STOP CAL at a logic low level.

Then when the second judgment signal JUDGE is activated to a logic high level in a state where the detection signal STOP CAL is deactivated to a logic low level the update signal generation unit of the calibration control unit may activate the first update signal UPDATE CODE. The operation start signal RUN ROD may be deactivated in response to the second judgment signal JUDGE. Thus the counter latch unit may stop the counting operation. In response to the first update signal UPDATE CODE the first code output unit of the calibration control unit may output the period control code PRE CAL CODE. Thus the short term oscillation signal generation unit may adjust the period of the short term oscillation signal S ROD.

When a predetermined time elapses after the first update signal UPDATE CODE is activated the count reset signal generation unit of the calibration control unit may activate the count reset signal RESTART to a logic low level. Thus the operation start signal RUN ROD may be reactivated. The above described process may be repeated until the reference period of the reference oscillation signal B ROD becomes less than or equal to the quadruple of the period of the short term oscillation signal S ROD.

Referring to in response to the operation start signal RUN ROD the reference oscillation signal generation unit may output the reference oscillation signal B ROD which oscillates at the reference period and the short term oscillation signal generation unit may output the short term oscillation signal S ROD which oscillates at a period less than the reference period.

The judgment signal generation unit may generate the pre judgment signal JUDGE PRE which is activated at each reference period of the reference oscillation signal B ROD and generate the Judgment signal JUDGE by delaying the pre Judgment signal JUDGE PRE. The counter latch unit may generate the count signal S FLAG by counting the period of the short term oscillation signal S ROD. For example when the value obtained by counting the period of the short term oscillation signal R ROD reaches four the counter latch unit may output the count signal S FLAG in synchronization with the short term oscillation signal S ROD which becomes a logic high level.

The detection unit may synchronize the count signal S FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In when the first judgment signal JUDGE PRE toggles to a logic high level the detection unit may finally output the detection signal STOP CAL to a logic high level because the count signal S FLAG already transitions to a logic low level.

Then when the second judgment signal JUDGE is activated to a logic high level in a state where the detection signal STOP CAL is activated to a logic high level the update signal generation unit of the calibration control unit may activate the second update signal UPDATE CODE. The operation start signal RUN ROD may be deactivated in response to the second judgment signal JUDGE. Thus the counter latch unit may stop the counting operation. The second code output unit of the calibration control unit may output the period control code PRE CAL CODE which is finally generated as the calibration code CAL CODE in response to the second update signal UPDATE CODE.

Using the calibration code CAL CODE outputted through the above described process the delay circuits may set the internal delay values.

Referring to the calibration code generation circuit may include a calibration operation adjust unit a reference oscillation signal generation unit and a short term oscillation signal generation unit .

The reference oscillation signal generation unit may generate a reference oscillation signal B ROD. The short term oscillation signal generation unit may generate a short term oscillation signal S ROD and adjust a period of the short term oscillation signal S ROD in response to a period control code PRE CAL CODE.

The calibration operation adjust unit may output the period control code PRE CAL CODE and the calibration code CAL CODE in response to the reference oscillation signal B ROD and the short term oscillation signal S ROD. The calibration operation adjust unit may generate the period control code PRE CAL CODE and output the period control code PRE CAL CODE to the short term oscillation signal generation unit when the reference period is greater than N times the period of the short term oscillation signal S ROD and generate the calibration code CAL CODE and output the calibration code CAL CODE to the delay circuits shown in when the reference period is less than or equal to N times the period of the short term oscillation signal S ROD.

The calibration operation adjust unit may include a calibration control unit a signal latch unit and a counter detection unit .

The signal latch unit may generate a flag signal B FLAG which is activated at each reference period of the reference oscillation signal B ROD.

The counter detection unit may count the period of the short term oscillation signal S ROD and activate the first judgment signal JUDGE PRE when the counting value reaches a predetermined value. Furthermore the counter detection unit may activate a second judgment signal JUDGE by delaying the first judgment signal JUDGE PRE by a predetermined time and output a detection signal STOP CAL in response to the second judgment signal JUDGE and the flag signal B FLAG.

The calibration control unit may output the period control code PRE CAL CODE and the calibration code CAL CODE in response to the second judgment signal JUDGE and the detection signal STOP CAL. The calibration control unit may output a signal reset signal RESTART for resetting the signal latch unit . Furthermore the calibration control unit may generate an operation start signal RUN ROD for starting the operations of the reference oscillation signal generation unit and the short term oscillation signal generation unit . The operation start signal RUN ROD may also be used for controlling the operations of the signal latch unit and the counter detection unit .

Since the calibration control unit the reference oscillation signal generation unit and the short term oscillation signal generation unit have substantially the same configuration as the calibration control unit the reference oscillation signal generation unit and the short term oscillation signal generation unit the detailed descriptions thereof are omitted herein.

Referring to the signal latch unit may include a first flag signal generation unit and a second flag signal generation unit .

The first flag signal generation unit may generate a pre flag signal P FLAG which is activated at each reference period of the reference oscillation signal B ROD.

The second flag signal generation unit may output a flag signal B FLAG which is set by the pre flag signal P FLAG and reset in response to the signal reset signal RESTART. In an embodiment the second flag signal generation unit may include an RS latch which receives the pre flag signal P FLAG as a set signal and receives the signal reset signal RESTART as a reset signal. The RS latch may include a cross coupled NAND latch.

Referring to the counter detection unit may include a counter a first judgment signal generation unit a second judgment signal generation unit and a detection signal generation unit .

The counter may count the period of the short term oscillation signal S ROD. In an embodiment the counter may include a plurality of shift registers SR coupled in series. The shift registers may sequentially transmit a high level signal VDD in response to low edges of the short term oscillation signal S ROD. The shift registers may be reset in response to the operation start signal RUN ROD.

The first judgment signal generation unit may output the short term oscillation signal S ROD as the first judgment signal JUDGE PRE when the counting value reaches a predetermined value. In an embodiment the first judgment signal generation unit may include a NAND gate and an Inverter which perform an AND operation on the output signal of the counter and the short term oscillation signal S ROD.

The second judgment signal generation unit may generate the second judgment signal JUDGE by delaying the first judgment signal JUDGE PRE. In an embodiment the second judgment signal generation unit may include an inverter chain which delays the first judgment signal JUDGE PRE by a predetermined time.

The detection signal generation unit may synchronize the flag signal B FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In an embodiment the detection signal generation unit may include a flip flop.

Hereinafter referring to the operation of the calibration code generation circuit will be described as follows.

Referring to when the calibration start signal CAL START is activated the operation start signal RUN ROD may be activated. In response to the operation start signal RUN ROD the reference oscillation signal B ROD oscillating at the reference period may be outputted and the short term oscillation signal S ROD oscillating at a period less than the reference period may be outputted.

The counter detection unit may count the period of the short term oscillation signal S ROD. When the counting value reaches a predetermined value for example four the counter detection unit may activate the first judgment signal JUDGE PRE in synchronization with the short term oscillation signal S ROD which becomes a logic high level. Furthermore the counter detection unit may delay the first judgment signal JUDGE PRE by a predetermined time and activate the second judgment signal JUDGE.

The operation start signal RUN ROD may be deactivated in response to the second judgment signal JUDGE. Thus since the operation start signal RUN ROD is already deactivated in response to the second judgment signal JUDGE the signal latch unit may maintain the pre flag signal P FLAG at a logic high level regardless of the reference period of the reference oscillation signal B ROD. Thus the flag signal B FLAG may be maintained at a logic low level.

The counter detection unit may synchronize the flag signal B FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In when the first judgment signal JUDGE PRE toggles to a logic high level the detection signal STOP CAL may be outputted at a logic low level because the flag signal B FLAG maintains a logic low level.

Then when the second judgment signal JUDGE is activated to a logic high level in a state where the detection signal STOP CAL is deactivated to a logic low level the first update signal UPDATE CODE may be activated. The operation start signal RUN ROD may be deactivated in response to the second judgment signal JUDGE. Thus the counter of the counter detection unit may stop the counting operation. In response to the first update signal UPDATE CODE the period control code PRE CAL CODE may be outputted. Thus the period of the short term oscillation signal S ROD may be adjusted.

When a predetermined time elapses after the first update signal UPDATE CODE is activated the count reset signal RESTART may be activated to a logic low level. Thus the operation start signal RUN ROD may be reactivated. The above described process may be repeated until the reference period of the reference oscillation signal B ROD becomes less than or equal to the quadruple of the period of the short term oscillation signal S ROD.

Referring to in response to the operation start signal RUN ROD the reference oscillation signal B ROD oscillating at the reference period and the short term oscillation signal S ROD oscillating at a period less than the reference period may be outputted.

The signal latch unit may generate the pre flag signal P FLAG which is activated at each reference period of the reference oscillation signal B ROD and thus generate the flag signal B FLAG.

The counter detection unit may count the period of the short term oscillation signal S ROD. When the counting value reaches a predetermined value for example four the counter detection unit may activate the first judgment signal JUDGE PRE in synchronization with the short term oscillation signal S ROD which becomes a logic high level. Furthermore the counter detection unit may activate a second judgment signal JUDGE by delaying the first judgment signal JUDGE PRE by a predetermined time. Then the counter detection unit may synchronize the flag signal B FLAG with the first judgment signal JUDGE PRE and output the synchronized signal as the detection signal STOP CAL. In when the first judgment signal JUDGE PRE toggles to a logic high level the detection signal STOP CAL may be outputted at a logic high level because the flag signal B FLAG already transitions to a logic high level.

Then when the second judgment signal JUDGE is activated to a logic high level in a state where the detection signal STOP CAL is activated to a logic high level the second update signal UPDATE CODE may be activated. The operation start signal RUN ROD may be deactivated in response to the second judgment signal JUDGE. Thus the counter of the counter detection unit may stop the counting operation. In response to the second update signal UPDATE CODE the period control code PRE CAL CODE which is finally generated may be outputted as the calibration code CAL CODE.

Using the calibration code CAL CODE outputted through the above described process the delay circuits may set the internal delay values.

In accordance with the embodiments of the present invention as the short RC delay circuit is calibrated on the basis of the long RC delay circuit the short RC delay circuit may be configured to have a skew corresponding to that of the long RC delay circuit. Furthermore the short RC delay circuit occupying a relatively small area may be used to improve the efficiency of the circuit area of DRAM.

Although various embodiments have been described for illustrative purposes it will be apparent to those skilled in the art that various changes and modifications may be made without departing from the spirit and scope of the invention as defined in the following claims.


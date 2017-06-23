---

title: Method for recording the number of sterilizations of a piece for a medical device
abstract: A method for recording the number of sterilizations of a piece for a medical device. The piece can be a motor and/or a handpiece. The piece includes a temperature sensor and/or a pressure sensor and/or a humidity sensor and/or an angular position. The method includes the following steps: inserting the piece into the sterilization camber; detecting the sterilization based on the temperature and/or the pressure and/or the humidity and/or the angular position in which the handpiece is received in the sterilization chamber by the temperature sensor and/or the pressure sensor () and/or the humidity sensor and/or the angular position sensor. This solution allows recording of the number of sterilizations of a handpiece and/or a motor for a medical device, in particular for a dental device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652710&OS=09652710&RS=09652710
owner: DASSYM SA
number: 09652710
owner_city: Hauterive
owner_country: CH
publication_date: 20150303
---
The present application claims the priority of Swiss patent application CH2014 00312 filed on Mar. 4 2014 the content of which is hereby incorporated by reference.

The present invention concerns a method for recording the number of sterilizations of a piece for a medical device in particular a dental device for example a motor for a medical device in particular a dental device. It concerns also a piece for a medical device in particular a dental device.

Surgical systems in particular dental systems comprise an instrument having a handpiece for example a contra angle which may be provided with a tool for example a milling cutter and a rotating motor that drives the tool. The handpiece and the motor may be two separate pieces and interconnected by appropriate interfaces or may constitute a single piece. The controller device of the instrument is often connected to the patient s chair and connected to the manual instrument by a flexible connection containing electric wires and tubes for passing air and water.

This type of instrument needs to be sterilized regularly. The sterilization is usually performed by autoclaving or in general in a sterilization chamber.

The state of the art however has no solution for the traceability of sterilization activities such as counting the number of sterilizations. This traceability allows the after sales service to have additional information on the surgical instrument and also allows a secure use of instruments in hospitals.

An aim of the present invention is to provide a method for recording the number of sterilizations of a motor and or a handpiece for a medical device.

Another aim of the invention is to provide a motor and or a handpiece for a medical device allowing this recording.

According to the invention these aims are achieved in particular by means of a method for recording the number of sterilizations of a piece for a medical device in particular for a dental device said piece being a motor and or a handpiece said piece comprising a temperature sensor and or a pressure sensor and or a humidity sensor and or an angular position sensor that said piece has when placed in a sterilization chamber said method comprising the following steps 

detecting of the sterilization based on said temperature and or said pressure and or said humidity and or said angular position sensed in said sterilization chamber by said temperature sensor and or said pressure sensor and or said humidity sensor and or said angular position sensor

The invention also relates to a piece motor and or handpiece for a medical device in particular for a dental device for the implementation of the method according to the invention.

This solution has the particular advantage over the prior art to allow to record the number of sterilizations of a motor and or of a handpiece for a medical device.

In the following description that is provided as example we will refer for simplicity to a motor for a device or surgical instrument in particular for a dental instrument. However it should be understood that the invention is not limited to a motor but also refers to a handpiece which can be separated from the motor or forms a single piece with the motor.

Sterilization of a motor for a surgical device is generally performed in a sterilization chamber for example an autoclave.

To detect and memorize a phenomenon it is necessary to have at disposal a minimum of energy. During the sterilization the motor is completely disconnected and deprived of any energy. It is therefore imperative that an energy source is present during sterilization. So there are two possible solutions 

sensorless motors i.e. devoid of sensors that are devoid of microprocessor and electronics for the rotor position measurement.

The symbol in indicates that during sterilization a communication between the motor respectively and the electronic control unit is no longer possible

The sensor may be a temperature sensor and or a pressure sensor the temperature and pressure are physical quantities that can be used for detecting a sterilization. Indeed when the motor is in operation these two physical quantities show much lower values for example an order of magnitude lower than those of the same motor during a sterilization which avoids false sterilization detections.

In another variant the sensor is a humidity sensor hygrometer . However the information provided by such a sensor may in some cases be unreliable especially if ambient moisture out of the sterilizing chamber is high close to 100 e.g. 90 or more.

In the motor is inserted into a sterilization chamber for example an autoclave. The sensor therefore senses the temperature and or pressure in the sterilization chamber and transmits this information to the storage element as indicated by the arrow.

In a variant that information includes an indication that sterilization has taken place as will be seen later.

In the motor is removed from the sterilization chamber and the FLAG maintains the information received during the step illustrated in .

In the motor is turned on as indicated schematically by the arrow . The FLAG being lifted the microprocessor will increment the sterilization recorder from n to n 1 in the register of the memory of the microprocessor .

In the motor is inserted into a sterilization chamber for example an autoclave. The sensor therefore senses the temperature and or pressure in the sterilization chamber and transmits this information to the storage element as indicated by the arrow.

In the motor is removed from the sterilization chamber and the FLAG maintains the information received during the step illustrated in .

In the motor is turned on as schematically indicated by the arrow . The FLAG being lifted the electronic oscillator generates a signal at a first frequency f during a time span t allowing the electronic to record a sterilization

In a preferred variant the first frequency f is within the range 600 kHz 1000 kHz for example 800 kHz and the timespan t is between 1 ms and 200 ms for example 10 ms or 100 ms. In general the timespan t must be long enough for the electronic control unit can determine that a sterilization has occurred and recorded it. The timespan t must take into account also the time to recharge a battery or a super capacitor which can be used as storage elements as will be seen later.

As discussed the sensor of the motor or the motor may be a pressure sensor. illustrates an example of a pressure sensor . This pressure sensor comprises a metal piece comprising a button shaped portion. In a preferred variant this piece is made of copper or in general any other conductive material. Button shown in has a width and a height h. In the illustrated embodiment it has a circular cross section but any other shape square rectangular etc. can be used.

In a preferred variant the width is less than 7 mm for example 5 mm or 3 mm. In another variant the height h is less than 2 mm for example equal to 1.5 mm or 1 mm.

In a variant the button shaped metal piece constitutes a protection from one or more electronic components during sterilization in other words one or more electronic components can be placed in this button shaped metal piece and thus be protected from humidity vapor etc. generated during sterilization.

The metal piece is arranged to be soldered to a printed circuit or any type of non conductive support arranged to include conductive parts including a pad or in general a conductive part shown in . In a preferred variant the conductive portion is placed in correspondence of the depression .

Advantageously the metal piece includes a sealed volume of gas at atmospheric pressure that is to say at ambient pressure about 100 kPa for example a volume of air. When a sterilization takes place the pressure acts on the part of the pressure sensor so that this part including its depression comes into contact with the conductive portion of the printed circuit .

The thickness of the piece determines the value of the obtained contact pressure which can vary between 0.1 bar to a thickness of 0.1 mm of the piece and 1.8 bar a thickness of 0.25 mm of the piece .

In a preferred variant the piece and the pad of the printed circuit undergo browning or any other suitable method for providing durability of electrical contacts.

In general the pressure sensor is a device arranged to allow an electrical contact when the sensed pressure is above a certain threshold indicating that sterilization takes place.

In this context the word super capacitor means a capacitor having a power density of between 1000 W kg and 5000 W kg and an energy density between 4 Wh kg and 6 Wh kg. In a preferred variant the super capacitor used is the PAS3225P3R3113 marketed by Taiyo Yuden.

The super capacitor Cap of is an embodiment of the storage element of . The super capacitor Cap is systematically reloaded at every turn on of the motor by the power supply for example providing a DC voltage of 3.3 V activating the signal A microprocessor . When sterilizing which is indicated by the arrow in correspondence with the pressure sensor the super capacitor Cap is discharged by the entry into contact of the pressure sensor . When the motor is turned on the B signal of the microprocessor activates the measurement of the state of charge of the super capacitor Cap read from the C signal. If the super capacitor Cap is discharged a sterilization occurred. The recharging of the super capacitor is then performed Cap.

In this variant the microprocessor must have a power supply voltage in at least one mode of operation for example in the low power mode of operation compatible with the used battery Batt. For example the microprocessor may be an ultra low power ARM Cortex M3 for example STM32L151C6 which consumes only 9 uA in Low Power Run allowing the use of a 12 pAh battery.

The battery Batt of supplies the microprocessor only during the contact time of the pressure sensor 50 ms is more than enough signal A microprocessor is 0 respectively 1 that increments the register of the microprocessor containing the number of sterilizations.

When the motor is running thus under external pressure given by the power module providing for example a DC voltage of 3.3 V the A signal is 1 respectively 0 the microprocessor so recharge the battery Batt activating the B signal but does not increment the register of the microprocessor sterilizations.

As discussed the sensor of the motor may alternatively be a temperature sensor. In another variant a pressure sensor and a temperature sensor are both used.

Such thermo generator operates the Seebeck effect wherein the presence of a temperature difference a potential difference appears at the junction of two materials for example as illustrated in the graph of .

During sterilization the outside temperature Text rises rapidly to at least 120 C. On the other hand the internal temperature Tint at the motor progresses more slowly. In other words there is a time during which the temperature difference external internal Text Tint is of the order of magnitude of tens of C.

The Embedded microprocessor is programmed to detect if its power supply voltage come from an external source motor is running or from the thermo generator motor in sterilization .

In a variant the minimum operating voltage of the microprocessor is about 2V for example 1.8 V so with reference to a temperature difference of 20 C. during 50 ms is sufficient to generate such a voltage.

In another variant not illustrated the microprocessor of the motor is continuously supplied even during its sterilization. However this solution is cumbersome because the size of the battery necessary for a sufficient monitoring time cannot fit inside of a motor for a medical device in particular dental device and is expensive.

When the motor is switched on by the power supply module providing for example a DC voltage of 3.3 V a timer is enabled. During a first timespan t for example 100 ms if the voltage of the super capacitor Cap is below a threshold V for example 200 mV the oscillation frequency of the electronics measuring the position emits a signal having a first frequency f for example 800 kHz indicating to the electronic control unit not shown that a sterilization has occurred.

After the timespan t the transmission frequency passes to a second frequency f for example 400 kHz and the super capacitor Cap is put under load.

When the motor is disconnected waiting for sterilization it has a charged battery Batt and all the non conductive MOS transistors including the transistor A by the resistor R. The battery Batt is therefore subject to any charge.

At the time of sterilization the pressure sensor puts the gate of the transistor A to the battery voltage Batt. The drain voltage of the transistor A named voltage A R in the following falls to zero which opens B which in the illustrated variant is a PMOS and maintains the transistor in conduction state even after disappearance of the contact provided by the pressure sensor thyristor effect . This stable state leads to a slow discharge of the battery Batt. However this effect does not affect the sterilization FLAG indication that is given by a voltage A R lower than a threshold voltage V for example V 1 V.

When the motor is turned on again during the timespan t for example 100 ms the transistor C is conductive and if the voltage of the trigger T is less than V the frequency of the position signals is f for example 800 kHz.

After t the frequency drops to f for example 400 kHz and the transistor C is no more conductive. On the other hand the transistor D becomes conductive and engages the recharging of the battery Batt. The transistor E also becomes conductive which cancels the thyristor effect of the transistor A which is no more conductive and the cycle can start again.

The arrangement of the transistors A to E and of the resistors R and R of is informative and should not be considered as limiting the present invention. Any other arrangement of transistors resistors and other electronic components for the charging and discharging of the battery Batt as explained above is also possible.

According to an independent aspect of the invention it is possible to detect whether a sterilization took place on the basis of the angular position of the motor in the sterilization chamber by exploiting the fact that the motor has a generally cylindrical body and that the probability that it is placed in the sterilization chamber two or more times consecutively in the same angular position is very low or zero.

In other words each time the motor is placed in the sterilization chamber it assumes an angular position which most likely will be different from the angular position that the motor will assume when it is will placed anew in the sterilization chamber.

Indeed the motor is generally placed in a specific packet for this purpose and then placed on a tray which is introduced into the interior of the sterilizing chamber similar as a baking tray in an oven.

Once in the sterilization chamber the motor axis is approximately horizontal in the vast majority of cases 99.9 of cases .

The motor is substantially balanced on its axis. In a variant it could be specifically improved if required to be balanced on its axis.

As discussed the outer body of the motor is generally cylindrical thus the motor in the sterilization chamber will almost never have the same angular position.

If the motor is not in the bag it will probably roll and randomly rest against an edge of the tray the horizontality of the latter is obviously not perfect so the goal is to detect this angular change from case to case.

There are different possibilities to achieve an angular sensor that can detect the angular change of the motor from case to case in order to record the number of sterilizations the same motor.

In a first variant we exploit a printed circuit which is generally present in a motor with microprocessor or devoid of microprocessor. This printed circuit is generally perpendicular to the axis of the motor. In the context of this invention the expression axis of the motor indicates the axis of the cylinder of the body of the motor.

If this circuit is not present in the engine which is not generally the case it is possible to add another printed circuit in the motor.

A side of this printed circuit may advantageously comprise a cover preferably made of resilient synthetic material resistant to the sterilization for example Rython . In another variant the cover is metallic and coated with an insulating.

In a preferred variant the cover is cylindrical but it can also have other forms provided that its shape is arranged so that it does not determine a unique position of the motor when placed in the sterilization chamber.

Before to fix the cover in this volume is placed a quantity for example a drop of insulating material which has the feature of being solid at room temperature for example 25 C. and of passing to the liquid or gas state at the sterilization temperatures 120 C. 134 C. . A non limiting example of such a material is paraffin.

Inside this volume before the fixing of the cover on the printed circuit is also placed a quantity for example a drop of conductive material for example water.

The printed circuit area circumscribed within the cover comprises at least two crossing conductive contacts for example golden contacts. In a variant these contacts are evenly distributed in the printed circuit area circumscribed within the cover. The number of such contacts determines the accuracy of the desired angular detection. These contacts are connected with ohmic measure elements located on the other face of the integrated circuit opposite to the face that comprises the cover and which generally comprises electronic components.

When the motor is placed in the sterilization chamber the insulating material for example the paraffin melt and by gravity moves in the upper region of the volume defined by the cover the water coming to position themselves in the lower region.

When the motor is removed from the sterilization chamber the probability that the positioning of the paraffin once returned to the solid state is the same as the one it had before sterilization is very low or even zero.

It is thus a question of comparing a previous resistance value with the new one and if there has been a change it is possible for example to increment the corresponding memory of an embedded processor by one.

In another variant the motor may comprise a thermo generator as that illustrated in and a gyroscope. The thermo generator is arranged as shown in . This thermo generator is configured to generate after the temperature difference Tint Text a voltage required to turn on the gyroscope that can therefore sense the angular position of the motor in the chamber sterilization

In another variant the motor includes a box containing a movable magnet or a movable magnet piece. This box also includes paraffin or other insulating material that has the feature of being solid at room temperature for example 25 C. while to pass to the state of liquid or gas at the sterilization temperatures 120 C. 134 C. .

When the motor is not in the sterilization chamber and it is at ambient temperature the insulating material for example paraffin is solid and keeps the movable part in a fixed position by imprisoning it.

When the motor is placed in the sterilization chamber the paraffin becomes liquid thereby releasing the movable part thus changes its position.

Once the motor outs from the sterilization chamber a Hall sensor a magneto resistive sensor or any other suitable sensor can determine the new position of the movable part which is changed after the sterilization and therefore may record a sterilization.

In another variant the position sensor is a box comprising an unbalanced mass and arranged to be rotatable about the axis of the motor and an insulating material which has the feature of being solid at room temperature for example 25 C. while to pass to the liquid or gas state at the sterilization temperatures 120 C. 134 C. for example paraffin. In a variant the mass has the same shape as an oscillating mass of an automatic watch.

When the motor is not in the sterilization chamber and is at ambient temperature the insulating material for example paraffin is solid and keeps the movable part in a fixed position by imprisoning it.

When the motor is placed in the sterilization chamber the paraffin becomes liquid thereby releasing the movable part that changes its position.

Once the motor outs from the sterilization chamber the new position of the movable part which is changed after the sterilization can be determined by a proximity sensor. In a variant the movable part is made of metal and the proximity sensor comprises a high frequency coil for example at a frequency exceeding 500 kHz for example 1 MHz or more.

Although examples of the position sensors to determine the angular position of the motor have been described it should however be understood that the invention is not limited to these examples but includes other equivalent position sensors.

According to another independent aspect of the invention the recording of the number of sterilization is performed by a passive RFID TAG of the motor that communicates with an RFID TAG connected to the sterilization chamber.

All variants described herein can also be used to record the number of sterilizations of a sensorless motor using a temperature sensor and or pressure and or moisture and or angular position described above. In this case the motor must contain the storage element FLAG for storing the information sensed by one of these sensors. This information will be read and processed by the electronic control unit once the sensorless motor is connected to the electronic control unit .

As discussed a surgical instrument in particular dental includes a handpiece for example an against angle which may be provided with a tool for example a milling cutter and a rotating motor that drives the tool. The handpiece and the motor may be two separate pieces and connected by appropriate interfaces or constitute a single piece.

In the case the handpiece and the motor constitute a single piece all the considerations made below with respect to the motor also applies to the piece comprising both the handpiece and the motor.

In the case the handpiece and the motor are two separate pieces the invention is not limited to the recording of the number of sterilizations of the motor of the medical device in particular dental device but it also allows to record the number of sterilizations of such a handpiece separated from the motor as long as the handpiece comprises a temperature sensor and or a pressure sensor and or a humidity sensor and or an angular position sensor.

The invention therefore also relates to a method for recording the number of sterilizations of a handpiece for a medical device said hand piece comprising a temperature sensor and or a pressure sensor and or a humidity sensor and or an angular position sensor that the handpiece has when it is placed in a sterilization chamber said method comprising the following steps 

If the handpiece separated from the motor comprises a storage element the method may also comprise the following step 

If the handpiece is separated from the motor the invention also relates to a handpiece for a medical device comprising a temperature sensor and or a pressure sensor and or a humidity sensor and or angular position sensor that the hand piece has when it is placed in a sterilization chamber each of said sensors being arranged to record the number of sterilization of the hand piece

In a variant the handpiece further comprises a storage element for storing information that sterilization has occurred.


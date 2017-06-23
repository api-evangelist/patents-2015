---

title: System and method for automatic reloading of software into embarked equipment
abstract: A system and method for automating detection of a change of configuration of an embedded unit and the reloading of the appropriate software configuration into the unit. An automatic reloading system comprises a transmitter associated with the unit to transmit a configuration frame comprising a set of identifiers of the current hardware and/or software configuration of the unit, a detector to capture the configuration frame and to detect a change of hardware and/or software configuration of the unit, and a software loader to automatically reload a set of appropriate software elements into the unit according to the detected change of configuration.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09612819&OS=09612819&RS=09612819
owner: Airbus Operations (S.A.S.)
number: 09612819
owner_city: Toulouse
owner_country: FR
publication_date: 20150924
---
This application claims priority to French Patent Application 14 59125 filed Sep. 26 2014 the entire disclosure of which is incorporated by reference herein.

The present disclosure relates to the field of downloading and more particularly relates to automatic reloading of software on an embedded and replaceable unit of an aircraft.

An aircraft comprises a plurality of downloadable embedded units that perform functions specific to the aircraft. These embedded units are replaceable and are generally called computers or line replaceable units LRU.

Currently when an embedded unit is defective it is dismantled from the aircraft sent to the maintenance center to be tested and possibly repaired. The defective unit is then replaced by the repaired unit or by a new unit.

At the maintenance center dedicated test software for testing the defective unit is installed in place of the operational software already in the unit. After the unit has been repaired the test software is deleted and the unit is often kept blank or reloaded with minimal configuration software. Only very rarely is the operational software reinstalled in the unit because it is difficult to anticipate the software configuration that the unit will need to have when it is reinstalled in an aircraft.

In the case where the unit has not been reloaded or has been partially reloaded the maintenance operator must perform the downloading of the missing software into the unit on board the aircraft. After having returned the unit to its receptacle the maintenance operator must make a plurality of selections on an interface of a handheld or embedded downloading management device to select the target to be downloaded and install the appropriate software in the targeted unit. Then he or she must check the new configuration of the unit validate his or her actions and close his or her jobcard. All these actions take a not inconsiderable amount of time and are performed while the aircraft is immobilized thus potentially generating delays and additional costs. Even in the very rare case where the operational software has been reinstalled in the unit the maintenance operator must still check the configuration of the unit.

Similarly in the case where the defective unit has to be replaced by another unit comprising none or just some of the operational software the same actions as previously have to be performed by the maintenance operator.

Furthermore in the case where the defective unit is replaced by an alternative non standard unit requiring different software the maintenance operator must make sure that the software packages are authorized recover the corresponding software and load them in the unit which will therefore take even a longer time.

An object of the present disclosure is consequently to remedy the above mentioned drawbacks by providing a method and a system for automatically reloading appropriate software on an embedded unit thus making it possible to reduce the aircraft downtime and the costs.

The present disclosure aims to automate the detection of a change of configuration of an embedded unit and the reloading of the appropriate software configuration in the unit. The disclosure herein relates to a method and a system for automatically reloading software in an embedded and replaceable unit of an aircraft the unit being reinstalled on the aircraft after having been removed and repaired or being a new unit installed on the aircraft to replace a previously removed defective unit the system comprising 

Thus this system for automatically reloading software on an embedded unit makes it possible to reduce the time and costs involved in replacing a defective unit.

A principle of the disclosure herein comprises automating the reloading of software on an embedded and replaceable unit of an aircraft.

The embedded unit is a replaceable and downloadable unit LRU of computer type for example a flight control computer a hydraulic regulation computer etc. . Each unit is identified by a serial number SNR and by hardware functional identifiers or hardware functional item numbers HW FIN comprising hardware part numbers HW PNR and by software functional identifiers or software functional item numbers SW FIN comprising software part numbers SW PNR. Each of these identifiers is unique and unchanging. For example each software functional identifier SW FIN is a constant uniquely and unambiguously identifying the position of a piece of embedded software on the aircraft . Thus each unit can be identified by a set of identifiers defining its hardware and or software configuration.

When a unit is reinstalled on the aircraft after having been removed and repaired or when a new unit is installed on the aircraft to replace a previously removed defective unit the reloading system according to the disclosure herein is adapted to automatically reload the appropriate software elements missing from the unit.

In effect in accordance with the disclosure herein the reloading system comprises hardware and or software comprising a transmitter a detector and a software loader .

The transmitter is associated with the unit and can form an integral part of the unit or of its environment. It is adapted to transmit a configuration frame comprising a set of identifiers of the current hardware and or software configuration of the unit. Current configuration should be understood to mean that which defines the unit on the date of transmission.

The detector is embedded and adapted to capture the configuration frame transmitted by the transmitter . The detector is configured to detect any change of hardware and or software configuration of the unit thus making it possible to identify the fact that the latter has been removed then reinstalled or that the unit is new and replaces that which was installed previously.

The receiver is adapted to capture each hardware and or software configuration frame for the unit transmitted by the transmitter .

The recorder is adapted to store the identifiers of the current configuration. For example the identifiers are recorded in an internal table describing the history of the identifiers with the date of reception of these identifiers.

The comparator is adapted to compare the identifiers of the current configuration of the unit with those of the preceding configuration in order to detect any change of hardware and or software configuration of the unit.

Thus the comparator compares each current configuration frame with that received previously. If the current frame comprises the same identifiers as the preceding frame then the comparator concludes that the unit has not been removed and simply updates the date of the identifiers in the internal log of the recorder .

On the other hand if the current frame does not comprise identifiers and or does not comprise some of the identifiers then the comparator concludes that the unit is new if the serial number SNR and or hardware part numbers HW PNR have changed or that it has been reinstalled after having been removed if only software part numbers SW PNR have changed . In this case the current identifiers are recorded and the trigger triggers the loading of the appropriate software. In effect the trigger is adapted to transmit to the software loader a trigger signal indicating for example the preceding and current configurations of the unit thus triggering the downloading of the set of appropriate software elements into the unit according to the detected change of configuration.

Advantageously the software loader is adapted to reload the set of appropriate software elements into the unit in an appropriate order.

As a variant the software loader is adapted to reload the set of appropriate software elements into the unit in any order. In this case it is the unit which is configured to reorganize the set of software elements in an appropriate loading order.

Advantageously the system comprises an embedded software storage device repository . The software loader is then adapted to recover the set of software elements from this embedded software storage device . It will be noted that in the case where certain software elements are not included in the embedded storage device the software loader is adapted to recover via communication devices the missing elements from a software storage device or service arranged on the ground.

Furthermore in the case where the system does not include any embedded software storage device the software loader is also adapted to recover via the communication devices the set of software elements from the software storage device arranged on the ground.

Advantageously the software loader is adapted to transmit after the reloading of the set of appropriate software elements in the unit a notification to a maintenance operator confirming the completion of the reloading.

Moreover after the loading of the appropriate software elements the unit is adapted to restart automatically. After the unit has been restarted the transmitter is adapted to transmit a new configuration frame comprising the current hardware and or software configuration identifiers.

Furthermore the detector is adapted to check that the unit comprises the appropriate hardware and or software configuration. The detector is also adapted to perform a validation and a logging of the new configuration. The logging consists for example in storing all the new identifiers in the first line of the internal log table by shifting all the other lines.

According to this first embodiment the transmitter is incorporated in the embedded unit . The transmitter is for example a computer application which is implemented by the processor or the processing device of the unit . When the unit is installed in its receptacle and therefore powered the transmitter is adapted to transmit on successive dates for example periodically each minute a series of configuration frames each frame comprising on the date of transmission the current hardware and or software configuration identifiers of the unit .

Thus each current frame transmitted by the transmitter is picked up by the detector and compared to the frame previously received in order to detect any change of hardware and or software configuration of the unit. It will be noted that if the transmission is periodic and the detector no longer receives any frames for a time longer than the transmission period it concludes that the unit has been removed. The detector awaits the reception of new frames before concluding that the unit has been reconnected or that a new unit has been connected according to the identifiers included in the frame.

In the step E a maintenance operator removes a defective embedded unit after the aircraft has landed. By way of example the unit has been previously detected as defective during the flight by an embedded monitoring system not represented and a message has been sent to the ground for the replacement of the unit with a new unit.

In the step E the maintenance operator installs the new unit procured before the landing of the aircraft in its corresponding receptacle in place of the defective unit which has been removed in the step E.

In the step E the new unit begins to periodically transmit a configuration frame LRU CONF FRAME comprising a set of identifiers in the form of triplets for the hardware identifiers and pairs for the software identifiers. For example the configuration frame comprises a hardware identifier FIN HW associated with a new part number PNR HW NEW and a new serial number SNR HW NEW and each of the N software identifiers FIN SW . . . FIN SWN is associated with a new software part number PNR SW NEW . . . PNRSWN NEW. The configuration frame can then take the following form 

In the step E the detector acquires the configuration frame LRU CONF FRAME extracts each identifier pair triplet and updates the values of the hardware and software identifiers PNR SNR in an internal log table which comprises a line or position for each part number. Then the detector compares each of the hardware identifiers PNR HW NEW SNR HW NEW and software identifiers PNR SW NEW . . . PNR SWN NEW of the current frame to each of the corresponding hardware identifiers PNR HW OLD SNR HW OLD and software identifiers PNR SW OLD . . . PNR SWN OLD already stored on the last line of the internal table and associated with the preceding unit. In particular it is assumed that according to this example the defective unit has been replaced by a standard or equivalent new unit . Then the hardware serial number SNR of the new unit is different from that of the preceding unit but the hardware part number PNR does not change. Moreover it is assumed that at least one element of the software identifiers FIN SW hosted by the new unit is different from that hosted by the removed unit. Thus the detector detects a change of hardware SNR and software FIN SW configuration of the unit and determines the software elements which have to be reloaded in the new unit.

In the step E the detector transmits to the software loader a trigger signal indicating for example the preceding and current configurations of the unit thus signalling to them the software elements which have to be reloaded in the unit . In particular it signals to the software loader that the software identifiers FIN SW . . . FIN SWN of the equipment referred to by the hardware identifier FIN HW PNR HW NEW SNR HW NEW have to be loaded with software elements PNR SW OLD . . . PNR SWN OLD associated with the preceding unit equipped with a same hardware part number PNR HW NEW PNR HW OLD.

In the case where the unit does not need to be downloaded in any particular order then the next step will be the step E. On the other hand in the case where the unit needs to be downloaded in a well determined order then the next step will be the step E

In the step E the software loader knows that the unit FIN HW affected by the loading is capable of downloading the software element or elements SW in any order and that no software element other than those indicated by the detector needs to be reloaded in the unit the latter being itself adapted to reorganize the set of downloaded software elements in an appropriate loading order. Thus the software loader can reload in the step E the set of software elements into the unit without any concern for the order of loading.

In the step E the software loader is adapted to store the order in which the set of software elements must be reloaded in the unit . In effect the software loader determines which software identifiers FIN SW are affected and uses models templates LRU RESTORE PATTERN previously recorded in a dedicated memory. This kind of model is described in the patent application FR1352194 co owned herewith.

In the case where the software loader notices that there is a certain software reference SWX PNR missing then it asks the detector to supply it with the missing information. The latter then returns the corresponding value PNRSWX OLD to the software loader which in turn acknowledges receipt. Thus the software loader can reload in the step E the set of software elements in the unit .

In the step Eor E the software loader recovers the software elements that have to be reloaded in the unit .

It will be noted that in the case where the aircraft comprises an embedded storage device or space repository in which all the software of the embedded units is stored then the software loader recovers for each of the software constants the software elements or software parts that have to be reloaded in the unit step E .

On the other hand in the case where the aircraft does not comprise an embedded storage space then the software loader uses the communication devices of the aircraft to send requests to a service on the ground FLSGR field loadable software repository in order to recover copies of all the missing software elements that have to be loaded in the unit and acknowledges reception after reception of these copies step E .

In the step Eor E the software loader reloads the set of software elements in the targeted unit being guided if necessary by the LRU RESTORE PATTERN templates.

More particularly in the step E the software loader constructs a list of elements to be loaded from the elements established in the step Eand recovered in the step Eor E

In the step E the software loader recovers the LRU RESTORE PATTERN templates associated with the FIN HW and updates them with the elements established in the step Eand recovered in the step Eor E. Then the software loader executes the LRU RESTORE PATTERN template step by step according to an electronic Service Bulletin eSB. The step by step execution is notably described in the patent application FR1352194 from the applicant.

In the step E the software loader transmits a notification to the maintenance operator indicating to him or her that the automatic reloading operation is finished.

In the step E the unit restarts automatically and recommences periodically transmitting a new configuration frame LRU CONF FRAME comprising the new hardware and or software configuration identifiers for example in the following form 

In step E the detector captures the new configuration frame LRU CONF FRAME and compares each PNR SNR value of the current frame i.e. received last with the corresponding values of the preceding frame stored previously in order to check that the targeted unit comprises the desired configuration.

In step E the detector checks that the targeted unit has been restored or reconfigured according to the appropriate hardware and or software configuration of the removed unit. The detector then validates this new configuration and all the new elements are stored in the first line of the internal log table by shifting all the other lines i.e. the line N is shifted to N 1 the line N 1 to N 2 and the line N 2 is lost .

In step E the detector transmits to the maintenance operator the new configuration of the unit in order for the latter to be able to close his or her jobcard. As a variant the new configuration is sent to an application for automatically filling out the jobcards.

In step E the jobcard is closed by the maintenance operator or by the automatic filling out application.

According to this example it is assumed that the defective unit has been replaced by a non standard new unit. In this case the hardware serial number SNR and the hardware part number PNR of the new unit are different from those of the preceding unit.

Steps E to E and Eto E are identical to those of . As previously it is also assumed that at least one element of the software identifiers FIN SW hosted by the new unit is different from that hosted by the removed unit. Thus the detector detects a change of hardware SNR and software FIN SW configuration of the unit.

In step E the detector transmits to the software loader a trigger signal indicating that it has to reload all the software elements FIN SW . . . FIN SWN in a unit having a new hardware identifier and that the list of these software elements has to be procured.

In step E the software loader sends a request to a service on the ground to procure the list of the software part numbers that have to be installed on the new unit equipped with a new hardware part number SNR HW NEW. Once it has the list of the new software part numbers it acknowledges reception and recovers as previously the set of software elements either from the embedded storage device step E or from the FLSGR service step E .

This second embodiment applies in the case where the unit is not adapted to itself transmit configuration frames. In this case the unit is coupled to a transmitter comprising a connection detector a first RFID tag tagging the unit a second RFID tag tagging the receptacle associated with the unit and a management device or an RFID controller . An RFID management procedure is described in the French patent application FR1353448 from the applicant.

The connection detector is adapted to detect a reconnection of the unit in a corresponding receptacle of the aircraft and to transmit a reconnection signal when the unit has been connected in its receptacle. This mechanism comprises an electrical circuit provided with a switch which is tripped when the unit is installed in its receptacle changing the open or closed state of the circuit.

The first RFID tag is a radio tag fixed for example by bonding onto the unit with which it is associated. The first RFID tag comprises first identifiers of the hardware configuration PNR HW SNR HW and possibly software configurations of the unit .

The second RFID tag is fixed for example by bonding onto the receptacle with which it is associated and is coupled to the first RFID tag . The second RFID tag comprises second hardware identifiers FIN HW of the unit which has to be installed in this receptacle . The information contained in the first and second tags are at least sufficient to allow an appropriate reloading of the unit .

The RFID controller is installed on board the aircraft . After the reconnection of the unit the RFID controller is adapted to interrogate the first RFID tag tagging this unit . In response to the request from the RFID controller the first RFID tag is adapted to transmit thereto the data from the second RFID tag to which it is coupled and the data from the first RFID tag itself. Thus the RFID controller is adapted to recover the first and second configuration identifiers recorded in the first and second RFID tags. Furthermore the RFID controller is adapted to transmit a configuration frame comprising these first and second configuration identifiers of the unit to the detector .

This method is identical to that of or of apart from the step E which is replaced by the steps E to E.

Steps E to E relate to the replacement of a defective unit with a new unit or the installation of the same unit after repair.

In step E after the installation of a new unit or of the same unit repaired in its receptacle a reconnection signal is transmitted by the connection detector .

In step E the detector receives the reconnection signal from the connection mechanism indicating that the unit has been connected in its receptacle . The detector consequently asks the RFID controller to transmit to it the configuration identifiers of the unit.

In step E the RFID controller excites the first tag which returns thereto step E the data from the second RFID tag to which it is coupled as well as the data from the first RFID tag itself. Thus the RFID controller recovers the hardware identifiers FIN HW from the second tag and the hardware identifiers PNR HW SNR HW and possibly software identifiers from the first tag .

In step E the RFID controller transmits a configuration frame comprising the hardware and possibly software configuration identifiers of the unit to the detector . Then the steps are identical to the steps E to E of or .

Thus the present disclosure makes it possible to automatically detect a change of configuration of an embedded unit signifying that the latter has been removed then reinstalled on the aircraft and to automatically reload the appropriate software configuration in the unit.

The subject matter disclosed herein can be implemented at least partially in software in combination with hardware and or firmware. For example the subject matter described herein can be implemented in software executed by a processor or processing unit. In one exemplary implementation the subject matter described herein can be implemented using a computer readable medium having stored thereon computer executable instructions that when executed by a processor of a computer control the computer to perform steps. Exemplary computer readable mediums suitable for implementing the subject matter described herein include non transitory devices such as disk memory devices chip memory devices programmable logic devices and application specific integrated circuits. In addition a computer readable medium that implements the subject matter described herein can be located on a single device or computing platform or can be distributed across multiple devices or computing platforms.

While at least one exemplary embodiment of the present invention s is disclosed herein it should be understood that modifications substitutions and alternatives may be apparent to one of ordinary skill in the art and can be made without departing from the scope of this disclosure. This disclosure is intended to cover any adaptations or variations of the exemplary embodiment s . In addition in this disclosure the terms comprise or comprising do not exclude other elements or steps the terms a or one do not exclude a plural number and the term or means either or both. Furthermore characteristics or steps which have been described may also be used in combination with other characteristics or steps and in any order unless the disclosure or context suggests otherwise. This disclosure hereby incorporates by reference the complete disclosure of any patent or application from which it claims benefit or priority.


---

title: Managing data exchange between an avionic core and an open world device
abstract: A flight management system includes: an avionics core implementing generic aircraft management functionalities and providing services associated with the generic functionalities; at least one remote functionality in an open world part performing a function of interfacing between the avionics core and the open world applications run on the open world part which need to communicate with the avionics core, wherein the remote functionality ensures homogeneity and consistency of data exchanged and guaranteeing integrity and security of data exchanges, and an exchange interface of between the avionics core and the open world functionality supporting data exchanges.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09583008&OS=09583008&RS=09583008
owner: Airbus Operations (S.A.S.)
number: 09583008
owner_city: Toulouse
owner_country: FR
publication_date: 20151204
---
This application claims priority to French Patent Application 1461946 filed Dec. 5 2014 the entirety of which is incorporated by reference.

The present invention relates to a management system for an aircraft in particular for a Flight Management System FMS for a transport aircraft. The invention may be embodied as other types of avionics systems such as an airport navigation system.

Current avionics architectures generally comprise an avionics part that includes a flight management system that offers the flight crew e.g. pilots the option to define a flight path before a flight and to maintain or change the flight path during the flight.

An avionics part or avionics world relates to on board elements computer systems etc. which are secured so as to obey given constraints of integrity and availability.

An open world part relates to on board equipment laptop tablet etc. in the cockpit of the aircraft and hosting applications which are not sufficiently secure to be integrated as the avionics part or avionics world in the aircraft.

A strict segregation exists between the avionic part avionics world and the open world. Because of the segregation integration of functions performed in the cockpit by the open world parts with the avionics part is very limited which greatly reduces their utility. The limited integration causes the crew to juggle between the avionics part and the open world part while in the cockpit. The juggling includes manually transferring information between the avionics part and the open world part which creates extra work for the crew and a risk of a data error occurring during the transfer.

Mainly for reasons of cost and simplicity of development many initiatives are emerging for implementing open world side functionalities aimed at simplifying the task of the crew regarding the management of the aircraft s mission.

A data exchange management system has been invented for an aircraft in particular for a flight management system that reduces the risk of data transfer error and the manual efforts needed to transfer data between the avionics part and the open world part.

The novel management system comprises an avionics core configured to implement generic aircraft management functionalities and provide services associated with at least the following generic functionalities 

 i at least one remote functionality in an open world part performing a function of interfacing between the avionics core and open world applications that need to communicate with the avionics core. The remote functionality provides homogeneity and consistency of data exchanged between the open world part and the avionics core and

 ii an exchange interface between the avionics core and the at least one remote functionality supporting the data exchanges.

Using the at least one remote functionality and the exchange interface it is possible to interface open world applications with the avionics core of the flight management system which contains the main functionalities generic functionalities for flight management while ensuring homogeneity and consistency of data exchanged and guaranteeing integrity and security of data exchanges. Thus the novel management system addresses the problem of integrating open world applications in the management system which overcomes the aforementioned shortcoming.

 i a set of software partitions grouped on at least one hardware partition and implementing the generic management functionalities and

 ii a set of functional services in connection with the set of generic functionalities implemented by the avionics core and open to requests from applications external to the avionics core.

 i functionalities configured for ensuring consistency of data merging and or consolidation of data from open world applications to the avionics core performing at least one part of securing the data extracting data from models used by open world applications for supplying the simplified models of the avionics core and exporting data from the avionics core to the open world applications 

 ii functional services offering access for the avionics core to one or more of specific data hosted on an open world platform and services carried by open world applications via the at least one remote functionality 

 iii functional services offering access for the open world applications to one or more of avionics core data and functional services in connection with the set of functionalities supported by the avionics core.

The exchange interface between the avionics core and the at least one remote functionality is based on at least some of the following elements bidirectional data requests bidirectional function execution requests bidirectional event warnings bidirectional message transfers and bidirectional file transfers.

In addition the exchange interface may comprise a data securing module configured to automatically monitor data to be transmitted and to automatically manage an authorization to transmit data between the avionics core and the at least one remote functionality according to the monitoring.

The data securing module includes at least one of the following security applications an incorrect data flow detection application a data consistency and format checking application and a data decryption application.

The data securing module may comprise a switching element the switching element being of one of the following types hardware type or a software type.

Further the management system may correspond to different avionics systems such as for example an airport navigation system or an aircraft flight management system FMS .

The generic functionalities implemented by the avionics core may include at least some of the following functionalities 

 vi calculation of deviations between the position of the aircraft and a flight trajectory determined by the FMS 

 vii calculation of guidance set points for guiding the aircraft along the fight trajectory determined by the FMS and

Moreover in a second variant of the embodiment the generic functionalities implemented by the simplified avionics core may only include the following functionalities 

The present invention also relates to an aircraft in particular a transport aircraft which is provided with a management system such as the one specified above.

The system schematically represented in and illustrating the invention is intended for the management notably of a mission of an aircraft not represented in particular of a passenger or cargo transport aircraft.

This system of managing a mission e.g. of the flight of the aircraft may be a Flight Management System FMS that includes one or more computer systems dedicated to flight avionics and software systems providing avionics functions and run on the computer system. Alternatively the system may be another avionics system such as an airport navigation system. In the following description the system described is the example of a flight management system.

The FMS also includes a set comprising at least one remote functionality in an open world part or equipment performing a single interfacing function between the avionics core and a set of open world applications which need to communicate with the avionics core ensuring the homogeneity and consistency of the data exchanged and guaranteeing the integrity and security of data exchanges as well as compliance with the formats used by the avionics core .

The FMS further includes an exchange interface between the avionics core and the set of remote functionality functionalities supporting data exchanges and guaranteeing a segregation between these elements.

The transmission of information between the avionics core and the open world part may notably be implemented by Ethernet link by an A429 bus or by Wifi link as illustrated by a double link L. In addition the transmission of information between the open world part and set may notably be implemented by Wifi or 3G 4G link as illustrated by a double link L.

In one particular embodiment the open world part includes an EFB Electronic Flight Bag electronic flight device or any other laptop or touch tablet used in particular to prepare a flight of the aircraft.

This architecture of the system facilitates integration into the system of open world applications outside of avionics such as mission management applications installed on an EFB device a tablet or a laptop in the cockpit. This effectively assists the crew of the aircraft in its task of carrying out the mission in several ways including 

 i by removing into the open world part a function of merging concentrating and converting data exchanged between these open world applications and the avionics core 

 ii by manipulating these data for generating elements such as a flight plan a trajectory performance data predictions etc. which will supply the avionics core and

 iii by securing the link between the avionics core and the open world part of the system for preventing a malicious corruption of these elements.

At the hardware level the system may include various integrated software on one or more computer hardware platforms. For example the computer hardware platforms may be an integrated modular avionics IMA computer module hosting the avionics core software with a personal computer PC platform connected to the avionics core of the system including specific software for the open world part . The computer hardware platforms may include a processor s with non transitory memory that stores software programs executed by the processor to perform avionics and data exchange functions.

 i a set of software partitions grouped on the same hardware partition or on a set of hardware partitions and implementing the generic flight management functionalities and

 ii a set of functional services in connection with the set of generic functionalities implemented by the avionics core and open to requests from applications external to the avionics core .

It should be noted that a software partition represents executable software and executes in a defined period of time and a hardware partition designates on board computer equipment including a processor unit a non transitory memory physical interfaces with the other hardware partitions and the aircraft s environment and mechanisms to assist the processor to run the set of software partitions.

Set comprises a plurality of remote functionalities F to Fn. These remote functionalities include for example functionalities configured for 

 i ensuring consistency merging and or consolidation of data from the open world applications of set to the avionics core 

 iii extracting data from models weather forecast etc. used by open world applications of set for supplying simplified models of the avionics core 

 ii services carried by open world applications of set via the remote functionalities specific human machine interface and specific performance calculation 

Functional services offering access for the open world applications of set to avionics core data and functional services in connection with the set of functionalities supported by the avionics core .

These remote functionalities are integrated into the overall flight management system without requiring modification of the software elements of the avionics core but drawing on the functional services provided by the latter. These remote functionalities may be developed independently of the avionics core including by a manufacturer other than that responsible for the development of the avionics core .

Furthermore the exchange interface between the avionics core and set of remote functionalities is based on the use of encoded messages namely bidirectional data requests bidirectional function execution requests bidirectional event warnings bidirectional message transfers and bidirectional file transfers.

The exchange interface comprises at least one data securing module which is configured for automatically monitoring data to be transmitted and for automatically managing an authorization to transmit data between the avionics core and the remote functionalities of set according to the monitoring.

The data securing module implements the physical link between the avionics core and the open world part in a secure way. The main function of the data securing module is a function of activating deactivating the connection of the avionics core to the open world part .

 i a switching element capable of being controlled. The switching element is configured for being able to be brought alternately into one or the other of two different positions a first position in which it prevents the transmission of data between the open world part and the avionics core via the link L and a second position in which it authorizes the transmission of data via the link L and

 ii a monitoring unit or module including at least one security application A. This security application A is configured for monitoring the data so as to be able to detect an incorrect data flow.

The switching element is either a hardware switching element or a software switching element. The switching element may for example be a switch transistor notably controlled by the monitoring unit and one or more security applications which are used to isolate the two items of equipment and which cut the link either automatically upon the detection of a particular condition or upon an action of the crew. The switching element may be a software switching element such as a program that automatically cuts the link when a particular condition is detected e.g. an incorrect data flow wrong format etc. The switching element may be located in equipment outside the avionics core and the open world part or if necessary in a specific part.

The monitoring unit may include the following security applications A to A as represented in i the incorrect data flow detection application A ii a data consistency and format checking application A and iii a data decryption application A. The applications A to A may be software programs operating within the monitoring unit .

The application A compares an expected format to a measured format according to the category of data considered. Even flight plan data and wind and temperature data which have a variable content and size have a known and detectable format and dimension range . The expected format of the data is encoded in the application software for preventing a malicious person from being able to circumvent the protection. The application A acts as a filter by rejecting data which are not in the correct format or in the correct dimension before they are inserted in the avionics core and ensures that some exchanges may take place only for certain well defined phases of flight wind and temperature data may be transmitted from the world part to the avionics core only on the ground 

The security application A may be a data decryption application that implements a common method of calculating a value CRC depending on the data considered. The transmitter and the receiver apply the same algorithm for calculating this value and if the data is sent with its CRC code the receiver is capable of decoding the data recalculating the CRC code and comparing the calculated value with the one received from the transmitter. The decryption ensures that the data have not been corrupted during the transfer of information but it does not allow checking that the data were originally valid.

The avionics part P comprises in addition to the data format checking and formatting carried out in the remote functionalities exchange securing functionalities either at a system module level or in an upstream avionics firewall. In one particular embodiment such an avionics firewall is provided in the system .

In particular the system includes in the exchange interface between the switching element and the avionics core flow control checks and functional checks for ensuring the integrity of the data exchanges.

In addition the system also includes an exchange interface between the remote functionalities of set of the open world part and set of open world applications including for example an API interface Application Programming Interface .

Furthermore the generic flight management functionalities as implemented by the avionics core may include one or more of the following functionalities 

In one particular embodiment the functional content of the avionics core is limited to the elements strictly necessary for guiding the aircraft on a predefined reference flight plan and all the functions of defining revising and updating this reference flight plan and mission management are placed remotely in the open world. The generic functionalities implemented by the avionics core are limited in this particular embodiment to the following functionalities 

 i flight plan management management of the segment buffer determination of the active segment sequencing 

In this particular embodiment the system therefore includes an avionics core reduced to the minimum functionalities for ensuring a robust and integrated guidance of the aircraft on a flight plan predefined by an external system and remote functionalities distributed over multiple software partitions hosted on multiple hardware partitions of the open world platform ensuring the residual functions of a normal flight management system as well as the function of interfacing with the mission management assistance and crew decision making support applications developed in the open world.

In one particular embodiment only the elements strictly necessary for guidance are retained in the avionics core capable of meeting a classification of Hazardous for RNP AR 0.1 NM operations on a flight plan defined in the open world but validated by the pilot before the transfer and passing through the exchange interface and the advanced graphical interface capabilities of the open world laptop tablet etc. are used for handling the definition and revision of the flight plan and mission management.

 ii ensure the consistency of the information provided to the crew by the open world on the one hand and the avionics core on the other 

 iii ensure the security of the data exchanged between the open world applications of set and the avionics core via an exclusive link guaranteeing for example the integrity of the trajectory on which the aircraft is guided 

 iv ensure that the exchanges with the open world applications of set remain in the field of use that guarantees the robustness and performance of the avionics core and

 v increase the stability and maturity of the avionics core notably by limiting the number of upgrades and the risk of associated regression.

Thus an open flight management system is obtained including a stable avionics core acting as a server for data and functional services about the management of flight plans and the calculation of trajectories and predictions with which other functions or systems developed independently in the open world can effectively interface.

A description is given below of the operation of the system from a particular example of implementation or application concerning a low speed performance calculation with reference to .

 i a TOPOC Take Off and landing Performance Optimization Computer application hereafter referred to as application A which is configured for computing and performing low speed performance calculations 

 iii a human machine interface linked to this application A which is connected via links and to application A and via links and to set .

In addition the avionics core is provided with a flight plan module . The exchange interface is connected to set via links and and the avionics core via links and .

Application A hosted in the open world in connection with the remote functionalities in the open world of this application is intended to enable the crew to compute the take off and landing performance characteristic speeds etc. of the aircraft taking into account the latest parameters wind conditions temperature mass of the aircraft characteristics of a selected runway etc. and insert them into the avionics core of the system .

 i the human machine interface and setting the parameters of requests made by the crew to the avionics core 

 iii sending calculation results and data used for calculation to the avionics core on validation by the crew of the results via the remote functionalities.

 ii checks on the format dimension and functional consistency of the data transmitted from application A to the avionics core 

 i transmitting the data entered by the crew in the FMS pages which are used in the low speed performance calculations to application A via the remote functionalities of set for their display on the human machine interface 

 ii acquiring the calculation results implemented by application A as well as the data that have been used in the calculations via the remote functionalities 

The example considered in one particular embodiment on the basis of the system represented in may present the following successive steps 

 i the crew of the aircraft accesses the human machine interface for managing low speed performance calculations on an open world screen e.g. of the human machine interface 

 ii application A requests the avionics core via the remote functionalities set to transmit thereto the parameters used in low speed performance calculation which have already been entered by the crew in the FMS pages and displays them on the human machine interface 

 iii the crew selects the parameters of the low speed performance calculations in the open world e.g. the runway contamination state and starts a calculation 

 iv a performance calculation module of application A acquires the data and the calculation parameters performs the calculation and returns the results to the human machine interface for their presentation to the crew 

 v the crew checks and validates the results on the human machine interface of application A which transfers the results and the data that have been used in the calculation to the avionics core via the remote functionalities set 

 vi the avionics core acquires the data and the results updates the FMS pages with the data and the results received 

 viii the avionics core inserts the data into the flight plan of module and restarts a calculation of trajectory and predictions on the basis of the new data inserted.

 i a possibility of interfacing additional functionalities with the increasingly complex flight management system without strictly piling these upgrades onto bloated and hard to maintain software and benefiting from flexibility of development on the open world platform 

 ii preparing for the avionics architectures vision of the future in which the flight management system is confined to the management of the trajectory for guidance and other systems support mission management and decision making support 

 iii a level of industrial independence between the avionics core and the open world applications the remote functionalities ensuring flexible and robust interfacing between the two worlds 

 iv an increased maturity of the avionics core by virtue of its wider deployment and its greater stability. Thus the frequency of upgrading the avionics core is reduced which helps to reduce anomalies regressions introduction of new functionalities that are faulty etc. 

 v an ability to install applications interfaced with the avionics core without any impact on the certification of the avionics core operational approval of the applications 

 vii a strict segregation between the functionalities of the avionics core which must be integrated and reliable and the functionalities relating to the mission that have a low criticality and

 viii the possibility of taking advantage of the computing capabilities of open world equipment for using more complex and more accurate models than those embedded in the flight management system. FMS calculations and predictions are improved by adapting in the most consistent way possible the outputs of these complex models on the simple models of the avionics core. Thus by improving integration between open world applications and the avionics core the quality of FMS calculations is also improved.

In one particular embodiment the flight management system comprises in its avionics part two modules namely a special module and a standard module the special module hosting for example a part of the securing checks. In this case the open world part may draw on functionalities by exchanging with the standard module via a securing module of the special module.

While at least one exemplary embodiment of the present invention s is disclosed herein it should be understood that modifications substitutions and alternatives may be apparent to one of ordinary skill in the art and can be made without departing from the scope of this disclosure. This disclosure is intended to cover any adaptations or variations of the exemplary embodiment s . In addition in this disclosure the terms comprise or comprising do not exclude other elements or steps the terms a or one do not exclude a plural number and the term or means either or both. Furthermore characteristics or steps which have been described may also be used in combination with other characteristics or steps and in any order unless the disclosure or context suggests otherwise. This disclosure hereby incorporates by reference the complete disclosure of any patent or application from which it claims benefit or priority.


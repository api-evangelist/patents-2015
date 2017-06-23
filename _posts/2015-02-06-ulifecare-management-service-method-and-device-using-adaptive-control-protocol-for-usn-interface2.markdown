---

title: Ulifecare management service method and device using adaptive control protocol for USN interface
abstract: A control method of a gateway communicating with at least one sensor and a service server is provided. The control method may include receiving, from the at least one sensor, first information comprising at least one of bioinformation, disaster prevention information, and public information, transmitting the first information to the service server when the first information meets a first standard, or processing the first information in a data format of the first standard and transmitting the processed first information to the service server when the first information does not meet the first standard, receiving, from the service server, a control command to control the at least one sensor, and transmitting the control command to a sensor corresponding to the control command.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09542837&OS=09542837&RS=09542837
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09542837
owner_city: Daejeon
owner_country: KR
publication_date: 20150206
---
This application claims the benefit of Korean Patent Application No. 10 2014 0016384 filed on Feb. 13 2014 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

Embodiments of the present invention relate to a gateway sensor and a service server based on a ubiquitous sensor network USN sensor access protocol.

In information connection processing methods expressed as ubiquitous sensor networks USNs a variety of organized methods for classifying information used for various purposes exist. To this end in domestic and foreign standardization organizations standardization of bioinformation collection sensors employing information communication technologies has been promoted to minimize effort or interference of information users using information.

The International Organization for Standardization ISO Institute of Electrical and Electronics Engineers IEEE 11073 series define standards of sensors and peripheral devices to collect bioinformation.

A bioinformation collection sensor may include for example a pulse oximeter ISO IEEE 11073 10404 a heart rate monitor ISO IEEE 11073 10406 a sphygmomanometer ISO IEEE 11073 10407 a thermometer ISO IEEE 11073 10408 a weighting scale ISO IEEE 11073 10415 a glucose meter ISO IEEE 11073 10417 and other sensors in a fitness field and a medical field ISO IEEE 11073 10441 10442 10471 and 10472 . A basic framework protocol for the bioinformation collection sensor is defined in the ISO IEEE 11073 20601 and standards for new equipment have been continuously defined. As a new bioinformation sensor an urineanalyzing apparatus and the like has been proposed.

Bioinformation collection apparatuses collect and transmit information through nonstandard information relay apparatuses that is gateways. The gateways may include for example personal computers PCs health information collection terminals mobile phones wired or wireless set top boxes and the like. Recently smartphones tablets or gateways for exclusive use in Android Apple s iOS and Windows that meet an international standard have emerged.

An aspect of the present invention provides a gateway to automatically transmit data collected by various sensors to a service server to receive a control command from the service server and to transfer the control command to a sensor and provides a server operating based on the control command received from the service server.

According to an aspect of the present invention there is provided a control method of a gateway communicating with at least one sensor and a service server the control method including receiving from the at least one sensor first information including at least one of bioinformation disaster prevention information and public information transmitting the first information to the service server when the first information meets a first standard or processing the first information in a data format of the first standard and transmitting the processed first information to the service server when the first information does not meet the first standard receiving from the service server a control command to control the at least one sensor and transmitting the control command to a sensor corresponding to the control command.

The registering may include registering the at least one sensor based on registration information including at least one of a version of an adaptive control protocol ACP a name and a type of each of the at least one sensor a gateway interface type identification information initial setup information authentication information and right information.

The transmitting may include determining based on the registration information whether a sensor transmitting the first information meets the first standard.

The control method may further include receiving identification information from the at least one sensor when the at least one sensor enters a network of the gateway and transmitting the received identification information to the service server.

The control method may further include receiving at least one of initial setup information corresponding to the identification information and operating software version information and updating the at least one of initial setup information and the operating software version information.

The control method may further include receiving an ACP information search request and transmitting to each of the at least one sensor a request for a report on whether ACP information is included in each of the at least one sensor in response to the ACP information search request.

The control method may further include receiving from each of the at least one sensor a report on whether each of the at least one sensor has an ACP of each of the at least one sensor in response to the request for the report on whether the ACP information is included in each of the at least one sensor and transmitting a report on an ACP information list to the service server.

The control method may further include receiving a request for a report on all ACP information found by the service server and transmitting to the at least one sensor the request for the report of all the ACP information.

The control method may further include receiving an ACP information record report of each of the at least one sensor from each of the at least one sensor and collecting the ACP information record report and transmitting the collected ACP information record report to the service server.

The control method may further include receiving an ACP service start request from the service server and transmitting an ACP service mode entry request to the at least one sensor.

The control method may further include receiving an ACP service start notification from the at least one sensor transmitting the ACP service start notification to the service server and starting an ACP service.

According to another aspect of the present invention there is provided a control method of a sensor communicating with a gateway communicating with a service server the control method including sensing first information including at least one of bioinformation disaster prevention information and public information transmitting the first information to the gateway receiving a control command relayed from the gateway the control command being used to control the sensor and controlling the sensor based on the control command.

The control method may further include registering the sensor in the gateway based on registration information including at least one of a version of an ACP a name and a type of the sensor a gateway interface type identification information initial setup information authentication information and right information.

The control method may further include receiving from the gateway a request for a report on whether ACP information is included in the sensor and transmitting to the gateway a report on whether the sensor has an ACP of the sensor in response to the request for the report on whether the ACP information is included in the sensor.

The control method may further include receiving from the gateway a request for a report on ACP information found by the service server and transmitting to the gateway an ACP information record report of the sensor in response to the request for the report on the ACP information.

The control method may further include receiving an ACP service mode entry request from the gateway transmitting an ACP service start notification to the gateway transmitting the ACP service start notification to the service server and starting an ACP service.

According to another aspect of the present invention there is provided a gateway communicating with at least one sensor and a service server the gateway including a communication unit to receive from the at least one sensor first information including at least one of bioinformation disaster prevention information and public information and a controller to control the communication unit to transmit the first information to the service server when the first information meets a first standard or to process the first information in a data format of the first standard and to transmit the processed first information to the service server when the first information does not meet the first standard wherein the communication unit receives from the service server a control command to control the at least one sensor and transmits the control command to a sensor corresponding to the control command.

According to another aspect of the present invention there is provided a sensor communicating with a gateway communicating with a service server the sensor including a sensing unit to sense first information including at least one of bioinformation disaster prevention information and public information a communication unit to transmit the first information to the gateway and to receive a control command relayed by the gateway from the service server the control command being used to control the sensor and a controller to control the sensor based on the control command.

In the present disclosure data received from various ubiquitous sensor network USN information collection sensors may be automatically transmitted to a server may be stored and utilized and each of sensors may be remotely controlled. Additionally embodiments of the present invention may be applied to a sensor a hub or a gateway a server and a user personal computer PC or a whole system for example an end information processing system a data hub and the like and an operation may be performed based on a set procedure and accordingly an ACP for a USN sensor interface Korean Patent Registration No. 10 1095793 enabling coping with a system change even in a dynamic and complex USN environment may be used. A user bioinformation sensor may design a life cycle health management service using a pulse oximeter ISO IEEE 11073 10404 a heart rate monitor ISO IEEE 11073 10406 a sphygmomanometer ISO IEEE 11073 10407 a thermometer ISO IEEE 11073 10408 a weighting scale ISO IEEE 11073 10415 a glucose meter ISO IEEE 11073 10417 other sensors ISO IEEE 11073 10441 10442 10471 and 10472 a newly proposed in vitro bioinformation collection apparatus for example a urineanalyzing apparatus and arbitrary complex bioinformation collection sensors having functions of a series of equipment. To this end an aspect of the present invention is to develop and implement an apparatus for applying an apparatus based on a standard framework ISO IEEE 11073 20601 of bioinformation measurement sensors to various existing operating systems OSs and an arbitrary OS that is to appear.

When the same type of technology is applied to a personal disaster prevention sensor an automatic detection function by a sensor may be used as disaster prevention information while a resident goes out in a general home. As a personal disaster prevention sensor a portable sensor that an individual may carry for example an outing sensor an intrusion detection sensor a gas sensor a fire sensor and the like may be applied.

Additionally living environment variables as well as a general residential environment may be monitored and accordingly a sensor used to measure liquid or materials to be monitored a temperature humidity sensor a wind direction wind speed sensor an altitude sensor a location information sensor and the like may be defined as a public information sensor and may be applicable using a protocol according to embodiments of the present invention. An open access scheme may be used to access public information of big data type provided by the government and the public information may be used as extensible sensor information.

The present disclosure may be implemented to perform connection and management to enable various information collection sensors to be used without users special interferences using the ACP for USN sensor interface Korean Patent Registration No. 10 1095793 . Target sensors may be classified into equipment with an international standard protocol and equipment for which an international standard protocol has not yet been defined and accordingly activation of industry conforming to a global standard may be induced and standardization of nonstandard equipment may be induced. Thus an effect of securing consumers convenience in use may be obtained along with activation of industry of a corresponding field.

The above sensors may be classified based on a region of a user into bioinformation sensors disaster prevention information sensors and public information sensors and may be developed which may have an effect of preparing a foundation to actively deal with personal service industries through personal information collection sensors that is automatically adaptable based on service desires of users in the era of cloud services and big data processing era that is arriving.

Along with the advent of the era of cloud services data may be processed using a platform called big data. However the data may provide source data instead of following an existing standardized processing scheme and accordingly a new method enabling data processing to meet consumer requirements has been provided. Accordingly collection information of various sensors proposed in the present disclosure may be classified into bioinformation sensor data disaster prevention information sensor data public information sensor data and expansion sensor information data and may be processed. The method may have an effect of providing raw data of a format suitable for processing of big data.

By regulating a processing procedure to automatically synchronize at a required point in time an ACP acceptance service server characteristic file an ACP acceptance gateway characteristic file and an ACP acceptance apparatus characteristic file to process sensor equipment affecting a service performance by a user when the user is involved between an apparatus and a service may be fundamentally prevented. Accordingly prior knowledge or technical ability of a user may be prevented from having an influence on providing of services if possible.

An individual bioinformation measurement sensor that is most standardized now may be first applied to a life cycle health management service. A kidney disease measurement sensor that has not been yet standardized but that is to be standardized may be practically implemented in the same method and accordingly a base platform applicable by standardizing nonstandard sensors that are to be developed or to emerge may be developed.

Reference will now be made in detail to exemplary embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. Exemplary embodiments are described below to explain the present invention by referring to the figures.

As shown in the USN system may include a service server a gateway and at least one sensor for example a bioinformation sensor a disaster prevention information sensor for individual use and a public information sensor . The service server may be connected to the gateway via a transmission network . Additionally the service server may be connected to a system administrator or a service provider via the transmission network . The gateway may be connected via the transmission network to at least one of the service server the system administrator and the service provider .

The bioinformation sensor may sense bioinformation. For example the bioinformation sensor may sense bioinformation including at least one of a blood pressure a blood sugar a temperature a heartbeat a body fat an oxygen saturation and an electrocardiogram of a user wearing the bioinformation sensor . The bioinformation sensor may be a sensor conforming to the International Organization for Standardization ISO Institute of Electrical and Electronics Engineers IEEE 11073 standard or an independent sensor that does not conform to a specific standard.

The bioinformation sensor may transmit the sensed bioinformation to the gateway via the access network . The access network may transmit and receive data to and from the gateway and the at least one sensor. The access network may be implemented by at least one of ZigBee communication Bluetooth communication a universal serial bus USB communication medical implant communication service MICS medical data service MEDS communication Ethernet communication and wireless fidelity Wi Fi communication.

For example the gateway may include a communication unit and a controller. The communication unit may transmit and receive a signal based on a communication scheme of the access network and the controller may generate and process a signal to be transmitted and received or may perform an operation. Additionally each of the at least one sensor may include a communication unit and a controller. In each of the at least one sensor the communication unit may transmit and receive a signal based on the communication scheme of the access network and the controller may generate and process a signal to be transmitted and received or may perform an operation. Each of the at least one sensor may further include a sensing unit to sense predetermined information. In the following description one of ordinary skill in the art may easily understand that signals may be transmitted and received by a communication unit of each of the gateway and the at least one sensor and that an operation may be performed or signals may be generated and processed by a controller of each of the gateway and the at least one sensor.

The disaster prevention information sensor may sense a personal hazard factor. For example the disaster prevention information sensor may sense information collected from surroundings of a residence or a body or environment information different from bioinformation. The disaster prevention information sensor may sense disaster prevention information associated with intrusion detection going out gas fire hurt from a fall an accidental collision and the like. The disaster prevention information sensor may transmit the sensed disaster prevention information to the gateway via the access network .

The public information sensor may sense public information different from personal body information or hazard factor. For example the public information sensor may sense public information for example measuring an altitude global positioning system GPS information a rainfall a snowfall a temperature a humidity an atmospheric pressure a wind direction a wind speed a luminous intensity and the like. In addition the public information sensor may sense public information provided through an open application programming interface API of a spread of population a volume of traffic an amount of precipitation a temperature a weather situation a public transportation timetable location information of a public institution and the like. The public information sensor may transmit the sensed public information to the gateway via the access network .

In an example the gateway may transmit at least one of the received bioinformation the received disaster prevention information and the received public information to the service server via the transmission network . The gateway may transmit at least one of the received bioinformation the received disaster prevention information and the received public information to the service server without processing.

In another example the gateway may process at least one of the received bioinformation the received disaster prevention information and the received public information in a predetermined data format and may transmit the at least one processed information to the service server . For example when bioinformation that does not meet the ISO IEEE 11073 standard is received from the bioinformation sensor the gateway may process the received bioinformation in a data format of the ISO IEEE 11073 standard and may transmit the processed bioinformation to the service server . The gateway may determine whether received information meets the ISO IEEE 11073 standard and may perform processing. Additionally the gateway may determine whether a sensor meets the ISO IEEE 11073 standard during registration of the sensor that will be described. The gateway may process data received from a sensor that does not meet the ISO IEEE 11073 standard in the data format of the ISO IEEE 11073 standard.

The processing of bioinformation in the data format of the ISO IEEE 11073 standard by the gateway is merely an example. The gateway may include a data format of the gateway that is different from the data format of the ISO IEEE 11073 standard and accordingly may process collected data in the data format of the gateway and may transmit the processed data to the service server .

In an example every time data is received from the at least one sensor the gateway may transmit the received data to the service server . In another example the gateway may temporarily store the received data in a storage for example a buffer and the like and may transmit the temporarily stored data to the service server for every predetermined period. One of ordinary skill in the art may easily understand that the gateway may temporarily store the received data in the storage until a user s delete command is input.

The service server may be connected via the transmission network to at least one of the gateway the system administrator and the service provider . The service server may store at least one of the bioinformation the disaster prevention information and the public information that are received from the gateway . The service server may include an interface to provide the system administrator or the service provider with at least one of the bioinformation the disaster prevention information and the public information that are stored. The service server may receive a data modification command or a data analysis command through the interface. The service server may modify or analyze data based on a received user command. The service server may also receive a sensor control command through the interface. The service server may transfer the received sensor control command to the gateway and the sensor control command may be transferred through the gateway to the at least one sensor. When a control command does not meet a specific standard the gateway may process the control command in a data format of the specific standard and may transmit the processed control command.

In operation S the service server may register in a management list the at least one sensor that exists in the USN system. The service server may perform registration based on registration information of each of the at least one sensor. The registration information may include at least one of a version of an ACP a name and a type of each of the at least one sensor a gateway interface type identification information initial setup information authentication information and right information. The gateway interface type may include for example a serial interface a USB interface a ZigBee communication interface and a Bluetooth communication interface.

Operation S may be initiated when the at least one sensor and a user enter a USN. When the gateway and the at least one sensor are physically connected to each other the at least one sensor may transmit identification information of each of the at least one sensor to the gateway . The gateway may transmit the received identification information to the service server . The service server may transmit to the gateway operating software version information and initial setup information of each of the at least one sensor in response to the identification information. At least one of the gateway and the at least one sensor may perform an operating software updating procedure or an initial setup procedure corresponding to the initial setup information. Additionally the service server may provide a login interface for a user. The user may perform a login procedure using the login interface provided in operation S.

In operation S the at least one sensor may be connected to the gateway . Additionally the gateway may be connected to the service server . The user may log into the service server and accordingly the user and the service server may be connected.

For example when data from the at least one sensor is streaming information peer to peer P2P connection between the user and the at least one sensor or P2P connection between the gateway and the user may be formed. In an embodiment a user may input a sensor list that the user desires to receive in advance to the service server . When a sensor connection request is received from the gateway the service server may notify a corresponding user of the sensor connection request and may enable connection to be completed.

When a connection procedure is completed and connection is set the service server may set a data storage space based on a characteristic of data from a sensor or may mediate P2P connection.

Operation S may be performed when data measured by the at least one sensor corresponds to a plurality of users not a single region or an individual. When a sensor is used for an individual authentication of each individual may be performed in operation S. For example for authentication in operation S a radio frequency identification RFID tag may be used or an input of sensor personal information may be received directly in the gateway .

In operation S the gateway may receive data from the at least one sensor and may transmit the data to the service server . The service server may transfer the received data to a user. For example the service server may provide the user with the data using a push scheme.

In operation S the user may enter a control command to the service server . The service server may transmit the received control command to the gateway and the gateway may relay the received control command to each of the at least one sensor. The control command may include sensor identifier information and accordingly the gateway may verify the control command and transmit the control command to only a corresponding sensor. The control command may include for example a command to start or stop data transceiving of a sensor and the like or may include sensing period setup information data transceiving scheme change information and the like.

In operation S the gateway or the at least one sensor may provide a script or a web page to control the gateway or the at least one sensor. The service server may control the gateway or the at least one sensor based on the script or the web page.

In operation S the gateway may transmit a disconnection request to the service server . In response to the disconnection request the service server may be disconnected from the gateway and may provide a user with a disconnection result. The service server may release a resource of a temporary storage space for data transceiving set in a server.

Operation S may be performed when the user logs out or when the at least one sensor escapes from the USN due to powering off or malfunctions.

As shown in a sensor may sense at least one of bioinformation disaster prevention information and public information by an application executed in an application layer . The sensor may be for example the bioinformation sensor . Collected information may be processed through an ACP driver a device driver an OSI RM and an operating system OS . The processed information may be transmitted to hardware of the access network through hardware .

The information received in the hardware may be transferred to an OSI RM and may be transferred to hardware of the gateway by passing through the hardware again.

The information received in the hardware may be transferred to an ACP client through an OSI RM . The ACP client may transfer the information to an application executed in the application layer .

The information may be transferred from the application back to the hardware through the ACP client and the OSI RM . The hardware may transfer the information to hardware of the service server .

The service server may receive the information through the hardware . The received information may be transferred to an ACP server through an OS an OSI RM and a database DB web application server WAS . The ACP server may transfer the received information to an application executed in the application layer .

The application may transfer the information to the ACP server and the ACP server may transfer the received information to an ACP player . The ACP player may transfer the received information to the application and the information may be transferred to the hardware through the DB WAS the OSI RM and the OS .

The hardware may transfer the information to hardware of a user terminal . The information received in the hardware may be transferred to a web browser executed in the application layer through an OS . A user may verify information sensed by the sensor based on the information provided in the web browser .

Additionally the user may enter a sensor control command to the user terminal . The sensor control command may be transferred to the sensor through a process inverse to an information transfer process.

As shown in the ACP client may include an ACPsr unit a user profile DB a protocol profile setting unit a service information processing unit a restoration unit an analysis unit an output unit a notification unit a profile DB an ACP feedback unit and an ACPss unit . The ACP server may include a profile DB a main processing unit that is an ACP manager a configuration management unit a sensor setting unit a communication setting unit a hardware search unit a setting management unit a performance management unit a driver setting unit a protocol matching unit a security processing unit a quality matching unit a sensor matching unit a sensor value setting unit a threshold setting unit an ACPcs unit a sensor data processing unit a bioinformation sensor a disaster prevention information sensor a public information sensor a sensor expansion unit an ACP restoration unit and an ACPcr unit .

The ACP client may operate in the gateway that processes an ACP function enabling an arbitrary terminal device to access an information service processing device while performing the ACP function.

The ACPsr unit may receive an ACP parameter from the ACP server may determine whether corresponding information is stored in the profile DB and the protocol profile setting unit may set a protocol profile based on a result of the determining to enable an ACP to be accepted. The profile DB may maintain synchronization of information with the profile DB .

The service information processing unit may process data to which an ACP profile is applied. The restoration unit may restore received data and the analysis unit may analyze the restored data based on an instruction translation table. The output unit may output the analyzed data and the notification unit may transfer the data to a unit from which the data is received. An analyzed profile may be stored in the profile DB .

The ACP feedback unit may transfer data to the ACPss unit and may enable the data to be transferred to the ACPcr unit . The ACPss unit may transfer an ACP profile processed by the service information processing unit to the ACP server .

To process sensor information transmitted in a sensor device in all applications applying an ACP the ACP server may automatically process an appropriate ACP profile of a sensor device in which an ACP transmitted from the ACP client is accepted or may register an ACP profile enabling active communication between an application and a sensor device in which an ACP is not accepted and may enable the ACP profile to be suited for the application.

The profile DB may store all known profile information of ACP Profile device of ACP Profile client of and ACP Profile server of to match all sensor devices that are connectable to an application. For example when a sensor device does not accept an ACP the sensor device may be registered in the profile DB based on a defined procedure and may be synchronized with the ACP client .

The configuration management unit may include the sensor setting unit configured to set a characteristic of a sensor device based on a profile of ACP Profile device and the communication setting unit of the sensor device.

The sensor setting unit may include the hardware search unit configured to search for a sensor device and the driver setting unit configured to match a sensor device.

The communication setting unit may include the setting management unit configured to set communication and the performance management unit configured to manage performance.

The protocol matching unit may include the security processing unit of an actually connected ACP sensor device and the quality matching unit configured to guarantee a service level agreement SLA and may pass through the ACPcs unit to perform protocol matching with the ACP client .

The sensor matching unit may process sensor data based on a setting value of each of the sensor value setting unit and the threshold setting unit . The sensor data processing unit may include the bioinformation sensor the disaster prevention information sensor and the public information sensor based on classification of sensor devices and the sensor expansion unit used to accommodate various sensors expected to emerge.

The ACP restoration unit may restore an ACP while communicating with the ACPss unit of the ACP client .

Referring to in operation service information processed by the service information processing unit may be provided. In operation configuration may be performed based on a profile provided from the profile DB . In operation equipment information user information printer information language information environment variable information and data information may be set and data may be analyzed.

In operation a gateway profile may be set. In operation whether a device is a case device may be determined.

When a device profile is set in operation a user profile may be generated and stored in the user profile DB .

In operation whether a device is a standard device may be determined. When the device is determined as the standard device a processing procedure corresponding to a personal health device PHD standard may be performed in operation . When the device is determined as a nonstandard device the device may be individually managed as a nonstandard device in operation .

The ACP client may perform mechanical analysis in operation and may store data in operation . Accordingly a data DB may be generated.

The ACP server may include the ACP manager the ACPcs unit and the ACPcr unit . The ACP manager may control an operation of each of the ACPcs unit and the ACPcr unit and may generate the profile DB .

The ACP client may include the ACPsr unit and the ACPss unit and may generate and manage the user profile DB and the data DB .

The ACP driver may include an ACPdev unit and may generate and manage a device profile of the ACP driver .

Synchronization of the profile DB may be performed among the ACP driver the ACP client and the ACP server using two schemes that is a polling mode for example an ACP request mode and an event inducing mode for example an ACP report mode . The two schemes may be interchangeably performed.

An operating procedure of an ACP may include the ACP request mode based on a periodic polling mode and the ACP report mode operated based on an event. In the ACP request mode data may be acquired by periodically polling data from an ACP gateway . Additionally in the ACP report mode the ACP gateway may report data. The ACP gateway may store collected data in a buffer and may periodically report the data or may perform real time streaming.

In operation the ACP master may propagate an ACP information search request to the ACP gateway . The ACP gateway may receive the ACP information search request and may transmit to the ACP slave a request for a report on whether ACP information is included in the ACP slave in operation .

In response to the request for the report on whether the ACP information is included in the ACP slave the ACP slave may report whether the ACP slave has an ACP in operation . The ACP gateway may report a gateway ACP information list in operation .

In operation the ACP master may transmit to the ACP gateway a request for a report on all found ACP information. In operation the ACP gateway may transmit a request for a report on ACP information to the ACP slave .

In operation the ACP slave may transmit to the ACP gateway an ACP information record report of the ACP slave . In operation the ACP gateway may report ACP information to the ACP master .

In operation the ACP master may transmit an ACP service start request to the ACP gateway . In operation in response to the ACP service start request the ACP gateway may transfer an ACP service mode entry request to the ACP slave .

In operation the ACP slave may start an ACP service and may transmit an ACP service start notification to the ACP gateway . In operation the ACP gateway may transmit the received ACP service start notification to the ACP master .

The ACP master the ACP gateway and the ACP slave may perform personal information protection encryption and security related process in operation may transmit and receive sensor data and may process the sensor data in operation . When operations to are completed the ACP master the ACP gateway and the ACP slave may be disconnected from each other based on an ACP in operation .

The ACP master and the ACP gateway may be implemented as the service server and the gateway respectively. The ACP slave may be implemented as the bioinformation sensor the disaster prevention information sensor or the public information sensor .

The above described embodiments of the present invention may be recorded in non transitory computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. The program instructions recorded on the media may be those specially designed and constructed for the purposes of the embodiments or they may be of the kind well known and available to those having skill in the computer software arts.

Although a few exemplary embodiments of the present invention have been shown and described the present invention is not limited to the described exemplary embodiments. Instead it would be appreciated by those skilled in the art that changes may be made to these exemplary embodiments without departing from the principles and spirit of the invention the scope of which is defined by the claims and their equivalents.


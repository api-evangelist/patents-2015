---

title: Apparatus and method for canceling feedback in hearing aid
abstract: A method of operating an electronic device is provided. The method includes transmitting, by the electronic device, a control signal for controlling a microphone sensitivity of a hearing aid, to the hearing aid, and transmitting a reception signal from a counterpart electronic device to the hearing aid.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09565500&OS=09565500&RS=09565500
owner: Samsung Electronics Co., Ltd.
number: 09565500
owner_city: Suwon-si
owner_country: KR
publication_date: 20150306
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed on Mar. 7 2014 in the Korean Intellectual Property Office and assigned Ser. No. 10 2014 0027390 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates to an apparatus and method for preventing a feedback phenomenon in a hearing aid.

As people age there is an increased suffering from geriatric diseases. Specifically due to the misuse of portable electronic devices as the population ages there has been an increased loss of hearing. Hearing aids can fix problems resulting from poor hearing of hard of hearing patients. For example the hearing aid is installed in an ear of the hard of hearing patient and amplifies a sound introduced through a microphone adaptively to a characteristic of a hearing sense of the hard of hearing patient and outputs the amplified sound through a speaker or a receiver thereby being able to correct the poor hearing of the hard of hearing patient.

As the hearing aid is miniaturized for easy installation in the ear of the hard of hearing patient a distance between the microphone and the speaker becomes short and thus a feedback phenomenon can take place in which a sound signal outputted from the speaker or a sound signal reflected from an external auditory canal is fed back to the microphone and is again amplified in the microphone. In accordance to this the hearing aid requires a way for decreasing a feedback phenomenon.

The above information is presented as background information only to assist with an understanding of the present disclosure. No determination has been made and no assertion is made as to whether any of the above might be applicable as prior art with regard to the present disclosure.

Aspects of the present disclosure are to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present disclosure is to provide an apparatus and method for preventing a feedback phenomenon of a hearing aid.

In accordance with an aspect of the present disclosure a method of operating an electronic device is provided. The method includes transmitting by the electronic device a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid and transmitting a reception signal provided from a counterpart electronic device to the hearing aid.

In accordance with an aspect of the present disclosure a method of operating an electronic device is provided. The method includes transmitting by the electronic device a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid and transmitting a sound signal collected through a microphone of the electronic device to the hearing aid.

In accordance with another aspect of the present disclosure a method of operating a hearing aid is provided. The method includes controlling by the hearing aid a microphone sensitivity of the hearing aid based on a control signal provided from an electronic device amplifying a sound signal provided from the electronic device and outputting the amplified signal to a speaker of the hearing aid.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a microphone a speaker a communication module and a processor configured to transmit a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid through the communication module and to transmit a reception signal provided from a counterpart electronic device to the hearing aid through the communication module.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a microphone a speaker a communication module and a processor configured to transmit a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid through the communication module and to transmit a sound signal collected through a microphone of the electronic device to the hearing aid.

In accordance with another aspect of the present disclosure a hearing aid apparatus is provided. The hearing aid apparatus includes at least one microphone a speaker a communication module and a processor configured to control a microphone sensitivity of the hearing aid based on a control signal provided from an electronic device to amplify a sound signal provided from the electronic device through the communication module and to output the amplified sound signal to a speaker of the hearing aid.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses various embodiments of the present disclosure.

Throughout the drawings it should be noted that like reference numbers are used to depict the same or similar elements features and structures.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of various embodiments of the present disclosure as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the various embodiments described herein can be made without departing from the scope and spirit of the present disclosure. In addition descriptions of well known functions and constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the present disclosure. Accordingly it should be apparent to those skilled in the art that the following description of various embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the present disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

The expressions comprise may comprise and the like usable in the various embodiments of the present disclosure indicate the existence of disclosed corresponding functions operations constituent elements or the like and do not limit additional one or more functions operations constituent elements or the like. Also it should be understood that the terms comprise have and the like in the various embodiments of the present disclosure are to designate the existence of features stated in the specification numerals operations constituent elements components and or a combination thereof and are not to previously exclude the possibility of existence or an addition of one or more other features numerals operations constituent elements components and or combinations thereof.

The expressions such as or and the like in the various embodiments of the present disclosure include any and all combinations of words enumerated together. For example A or B may include A may include B or may include all A and B.

The expressions such as 1st 2nd first second and the like used in the various embodiments of the present disclosure may modify various constituent elements of various embodiments but do not intend to limit the corresponding constituent elements. For example the expressions do not limit the order and or importance and the like of the corresponding constituent elements. The expressions may be used to distinguish one constituent element from another constituent element. For example all of a 1st user device and a 2nd user device are user devices and represent different user devices. For example a 1st constituent element may be named as a 2nd constituent element without departing from the scope of right of the various embodiments of the present disclosure. Likely even a 2nd constituent element may be named as a 1st constituent element.

When it is mentioned that any constituent element is coupled and or connected to another constituent element the any constituent element may be directly coupled or connected to the another constituent element but it should be understood that new other constituent element may also exist between the any constituent element and the another constituent element. In contrast when it is mentioned that any constituent element is directly coupled and or directly connected to another constituent element it should be understood that no new other constituent element exists between the any constituent element and the another constituent element.

The terms used in the various exemplary embodiments of the present disclosure are used for just describing specific exemplary embodiments and do not intend to limit the various exemplary embodiments of the present disclosure. The expression of singular number includes the expression of plural number unless the context clearly dictates otherwise.

Unless defined otherwise all the terms used herein including the technological or scientific terms have the same meaning as those commonly understood by a person having ordinary knowledge in the art which various embodiments of the present disclosure belong to. The terms as defined in a general dictionary should be interpreted as having the same meanings as the contextual meanings of a related technology and are not interpreted as having ideal or excessively formal meanings unless defined clearly in various embodiments of the present disclosure.

An electronic device according to various embodiments of the present disclosure may be a device including a telecommunication function. For example the electronic device may include at least one of a smart phone a tablet Personal Computer PC a mobile phone a video phone an electronic book e book reader a desktop PC a laptop PC a netbook computer a Personal Digital Assistant PDA a Portable Multimedia Player PMP an MPEG Audio Layer 3 MP3 player a mobile medical instrument a camera or a wearable device e.g. a Head Mounted Display HMD such as electronic glasses electronic clothes an electronic bracelet an electronic necklace an appcessory an electronic tattoo and or a smart watch .

According to various embodiments the electronic device may be smart home appliances having a telecommunication function. The smart home appliances may include for example at least one of a television a Digital Versatile Disc DVD player an audio system a refrigerator an air conditioner a cleaner an oven a microwave a washing machine an air cleaner a set top box a TV box for example Samsung HomeSync Apple TV and or Google TV a game console an electronic dictionary an electronic locking system a camcorder and an electronic frame.

According to various embodiments the electronic device may include at least one of various medical instruments including telecommunication functions e.g. Magnetic Resonance Angiography MRA Magnetic Resonance Imaging MRI Computerized Tomography CT a moving camera an ultrasonic machine and the like a navigation device a Global Positioning System GPS receiver an Event Data Recorder EDR a Flight Data Recorder FDR a car infotainment device electronic equipment for a ship e.g. a navigation device for a ship a gyrocompass and the like avionics a security instrument and or an industrial or home robot.

According to various embodiments the electronic device may include at least one of a part of furniture or building structure including a telecommunication function an electronic board an electronic signature receiving device a projector and or various measuring metering instruments e.g. a tap water measuring instrument an electricity measuring instrument a gas measuring instrument a radio wave measuring instrument and or the like . The electronic device according to the present disclosure may be one of the aforementioned various devices or a combination of two or more. Also it is obvious to those skilled in the art that the electronic device according to the present disclosure is not limited to the aforementioned instruments.

An electronic device according to various embodiments of the present disclosure will be described with reference to the accompanying drawings. The term user used in the various embodiments may denote a person who uses the electronic device and or a device e.g. an artificial intelligent electronic device which uses the electronic device.

An embodiment of the present disclosure describes a technology for preventing a feedback phenomenon of a hearing aid.

Various embodiments of the present disclosure describe a digital hearing aid of a Receiver In the Canal RIC type for example but are identically applicable to a digital and or analog hearing aid of other type that is wearable on a user e.g. a hearing aid of a Completely in the Canal CIC type .

Referring to an electronic device and a hearing aid are illustrated where the electronic device and the hearing aid connect communicate and transmit receive data with each other. For example the electronic device and the hearing aid may communicate using a short range communication method. Here the short range communication method may include one or more of Wireless Fidelity WiFi Bluetooth Zigbee or Near Field Communication NFC . For example the electronic device and the hearing aid may transmit receive data using a Bluetooth Low Energy BLE protocol communication method thereby decreasing the power consumption of the hearing aid . The electronic device and the hearing aid may deform a data transmission interval or a data transmission duration defined in the BLE protocol such that transmission of a sound signal is possible and may transmit receive the sound signal with each other.

To prevent a feedback phenomenon of the hearing aid the electronic device can control a microphone sensitivity of the hearing aid . For example the electronic device may transmit to the hearing aid a microphone sensitivity control signal for decreasing the microphone sensitivity of the hearing aid based on a communication state with the hearing aid . For instance if communication is performed with the hearing aid the electronic device may transmit to the hearing aid the microphone sensitivity control signal for decreasing the microphone sensitivity of the hearing aid . Furthermore for example if sensing the occurrence of an event e.g. a telephony event with a counterpart electronic device the electronic device can transmit to the hearing aid the microphone sensitivity control signal for decreasing the microphone sensitivity of the hearing aid .

The hearing aid may control a sensitivity of a microphone or of the hearing aid based on a microphone sensitivity control signal provided from the electronic device . For example the hearing aid may control the microphone sensitivity such that the microphone or is inactivated based on the microphone sensitivity control signal provided from the electronic device . The hearing aid may amplify a sound signal provided from the electronic device and output the amplified sound signal through a speaker or receiver .

Referring to an electronic device e.g. the electronic device of is illustrated where the electronic device may include a bus a processor a memory a speaker a microphone a communication module i.e. a communication interface a display module and or an input module i.e. an input interface . Here one or more of the processor and or the memory may exist in plural.

The bus may connect constituent elements included in the electronic device with one another and control communication between the constituent elements included in the electronic device .

The processor may control the electronic device to control various services. For example the processor may decipher an instruction received from one or more other constituent elements e.g. the memory the speaker the microphone the communication module the display module and the input module included in the electronic device through the bus and execute operation or data processing according to the deciphered instruction.

The processor may control a microphone sensitivity of the hearing aid . For example if sensing the occurrence of an event for microphone sensitivity control the processor may transmit a microphone sensitivity control signal for decreasing the microphone sensitivity of a hearing aid to the hearing aid through the communication module . For instance if communication is performed with the hearing aid through the communication module the processor may transmit the microphone sensitivity control signal for decreasing the microphone sensitivity of the hearing aid to the hearing aid through the communication module . The processor may transmit a sound signal collected through the microphone or a sound signal collected through a peripheral device to the hearing aid through the communication module .

Furthermore for example if sensing the occurrence of an event e.g. a telephony event with a counterpart electronic device the processor can transmit a microphone sensitivity control signal for decreasing a microphone sensitivity of the hearing aid to the hearing aid through the communication module . The processor may transmit a reception signal e.g. a call reception signal provided from the counterpart electronic device through the communication module to the hearing aid through the communication module . Here the event with the counterpart electronic device may further include a sound information sharing event.

The processor may transmit a microphone sensitivity restoration signal for restoring a microphone sensitivity of the hearing aid to the hearing aid through the communication module . For example if sensing the occurrence of an event for microphone sensitivity restoration the processor may transmit the microphone sensitivity restoration signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module . For instance if an event service e.g. a telephony service with a counterpart electronic device is provided using a peripheral device e.g. a wearable device the processor may transmit the microphone sensitivity restoration signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module . Furthermore if the event service e.g. the telephony service with the counterpart electronic device has ended the processor may transmit the microphone sensitivity restoration signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module .

When the electronic device transmits a signal e.g. a call reception signal for an event service with a counterpart electronic device to the hearing aid the processor may transmit a sound signal collected through the microphone of the electronic device to the hearing aid together with the call reception signal. For example if sensing a user s danger signal through the sound signal collected through the microphone of the electronic device the processor may transmit a danger sensing signal to the hearing aid together with the call reception signal.

Furthermore for example the processor may separate the sound signal collected through the microphone of the electronic device into a surrounding sound and a user voice. The processor may transmit the user voice to the counterpart electronic device through the communication module and transmit the surrounding sound to the hearing aid together with the call reception signal.

The memory may store an instruction or data received from one or more constituent elements i.e. the processor the speaker the microphone the communication module the display module and the input module included in the electronic device and or generated by the one or more constituent elements.

The speaker may output an audio signal provided from the processor to a user. For example when the processor transmits to the hearing aid a sound signal collected through the microphone or a call reception signal provided from the counterpart electronic device through the communication module the speaker may be inactivated and or activated in accordance to a control of the processor .

The microphone may collect an external sound and convert the external sound into an electrical audio signal and provide the audio signal to the processor .

The communication module i.e. the communication interface may communicate via a network between at least one hearing aid and or at least one other electronic device and or a server and or at least one peripheral device and the electronic device . For example the communication module may communicate with at least one hearing aid based on tag information provided through an electronic tag of the hearing aid . For instance the communication module may collect tag information of a hearing aid from an electronic tag inserted into the hearing aid or existing in a place separate from the hearing aid such as a product box of the hearing aid or a retailer thereof. Here the tag information of the hearing aid may include one or more of identification information of the hearing aid or communication link setting information of the hearing aid.

The communication module may support a short range communication protocol e.g. WiFi Bluetooth ZigBee or NFC a network communication protocol e.g. the Internet a Local Area Network LAN a Wireless Area Network WAN a telecommunication network a cellular network a satellite network and or a Plain Old Telephone Service POTS and or a wired communication protocol e.g. a Universal Serial Bus USB a High Definition Multimedia Interface HDMI . Here the communication protocol e.g. the short range communication protocol the network communication protocol and or the wired communication protocol may be supported in a middleware of the memory and or an Application Programming Interface API . Here the other electronic device being a peripheral device of the electronic device may be the same type device as the electronic device or may include a different type device.

The input module i.e. an input interface may transmit an instruction and or data generated by user s selection to the processor and or the memory through the bus . For example the input module may include one or more of a keypad including at least one hardware button and a touch panel sensing touch information.

In the aforementioned embodiment the electronic device may transmit a sound signal or call reception signal collected through the microphone to the hearing aid . Accordingly the electronic device may perform digital signal processing such as noise removal for the sound signal and or call reception signal and transmit the processed sound signal and or call reception signal to the hearing aid .

According to various embodiments of the present disclosure the electronic device may be comprised of the microphone the speaker and the communication module . The electronic device may include the processor for transmitting a control signal for controlling a microphone sensitivity of the hearing aid to the hearing aid through the communication module and transmitting a reception signal provided from a counterpart electronic device e.g. the electronic device to the hearing aid through the communication module .

In an embodiment of the present disclosure the communication module may communicate with the hearing aid using a short range communication method.

In an embodiment of the present disclosure the short range communication method may include one or more of WiFi Bluetooth and or NFC.

In an embodiment of the present disclosure the communication module may communicate with the hearing aid in a BLE protocol communication method of deforming one or more of a data transmission interval and or a data transmission duration.

In an embodiment of the present disclosure the processor may transmit at least a portion of a sound signal collected through the microphone of the electronic device to the hearing aid through the communication module .

In an embodiment of the present disclosure the processor may separate the sound signal collected through the microphone of the electronic device into a surrounding sound and a user voice and transmit the surrounding sound to the hearing aid through the communication module .

In an embodiment of the present disclosure the processor may check a user s danger occurrence and or non occurrence using the sound signal collected through the microphone of the electronic device and if sensing the user s danger occurrence may transmit a danger signal to the hearing aid through the communication module .

In an embodiment of the present disclosure if an event for microphone sensitivity restoration takes place the processor may transmit a control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module .

In an embodiment of the present disclosure if an event with the counterpart electronic device e.g. electronic device has ended the processor may transmit the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module .

In an embodiment of the present disclosure if providing an event service with the counterpart electronic device e.g. electronic device using a peripheral device the processor may transmit the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid through the communication module .

In an embodiment of the present disclosure if transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid the processor may inactivate the speaker of the electronic device .

In an embodiment of the present disclosure if a telephony event with the counterpart electronic device e.g. electronic device takes place the processor may transmit the control signal for controlling the microphone sensitivity of the hearing aid to the hearing aid through the communication module .

According to various embodiments of the present disclosure the electronic device may be comprised of the microphone the speaker and the communication module . The electronic device may include the processor for transmitting a control signal for controlling a microphone sensitivity of the hearing aid to the hearing aid through the communication module and for transmitting a sound signal collected through the microphone of the electronic device to the hearing aid .

In an embodiment of the present disclosure the communication module may collect electronic tag information of the hearing aid and may communicate with the hearing aid based on the electronic tag information.

Referring to a hearing aid is illustrated where the hearing aid may include a bus a processor a memory a microphone a speaker and or a communication module i.e. communication interface . Here the speaker may include a receiver.

The bus may connect the constituent elements included in the hearing aid with one another and control communication between the constituent elements included in the hearing aid .

The processor may control to amplify a sound signal collected through the microphone and an audio signal provided from an electronic device through the communication module and output the amplified signals through the speaker . For example when operating in a general mode the processor may convert an audio signal provided from the microphone into a digital sound signal. The processor may perform digital signal processing such as noise removal amplification gain and non linear amplification for the digital sound signal.

For instance the processor may control the speaker to amplify the digital sound signal based on a preset amplification gain and output the amplified sound signal. If the hearing aid includes a hardware amplifier not shown the hardware amplifier may amplify the digital sound signal based on the control of the processor . The processor may convert the processed digital sound signal into an analog signal and output the analog signal through the speaker .

Furthermore for example if a microphone sensitivity control signal is received from the electronic device through the communication module the processor may decrease a sensitivity of the microphone based on the microphone sensitivity control signal. For instance the processor may control the sensitivity of the microphone and inactivate the microphone . If inactivating the microphone the processor may control to amplify an audio signal provided from the electronic device through the communication module and output the amplified audio signal to the speaker .

If decreasing the sensitivity of the microphone the processor may restore the decreased sensitivity of the microphone to the original sensitivity based on the occurrence of an event for microphone sensitivity restoration. For example if receiving a microphone sensitivity restoration signal from the electronic device through the communication module the processor may restore the decreased sensitivity of the microphone to the original sensitivity.

Furthermore for example if an event e.g. communication with the electronic device has ended or has been paused the processor may restore the decreased sensitivity of the microphone to the original sensitivity.

If restoring the sensitivity of the microphone the processor may control to amplify a sound signal collected through the microphone and output the amplified sound signal through the speaker .

The memory may store control data for controlling one or more constituent elements i.e. the processor the microphone the speaker and the communication module included in the hearing aid . For example the memory may store amplification gain information for amplification of a sound signal.

The microphone may collect an external sound and convert the collected sound into an electrical audio signal and output the audio signal. For example the microphone may include a plurality of microphones and may collect a sound of an audible frequency band or preset specific frequency band and convert the collected sound into an electrical audio signal and output the audio signal. Additionally the microphone may include a filter for filtering an audio signal and or extracting a signal of an audible band based on a characteristic of a hearing sense of a user who wears the hearing aid .

The speaker may output a sound signal provided from the processor . For example the speaker may amplify an analog sound signal based on an amplification gain that is set in the processor and output the amplified sound signal.

Referring to a processor is illustrated where the processor may include an Analog Digital A D conversion module a hearing aid control module and a Digital Analog D A conversion module .

The A D conversion module may convert an audio signal provided from the microphone as illustrated in into a digital sound signal.

The hearing aid control module may control to amplify a digital sound signal provided from the A D conversion module and or an audio signal provided from the electronic device through the communication module as illustrated in and may output the amplified signals through the speaker as illustrated in . If operating in a general mode the hearing aid control module may perform digital signal processing such as noise removal amplification gain and non linear amplification for the digital sound signal provided from the A D conversion module .

Furthermore for example if receiving a microphone sensitivity control signal from the electronic device through the communication module the processor may decrease a sensitivity of the microphone based on the microphone sensitivity control signal. For instance the processor may control the sensitivity of the microphone and inactivate the microphone . If inactivating the microphone the processor may control to amplify an audio signal provided from the electronic device through the communication module and output the amplified audio signal to the speaker .

If decreasing the sensitivity of the microphone the processor may restore the decreased sensitivity of the microphone to the original sensitivity based on the occurrence of an event for microphone sensitivity restoration. For example if receiving a microphone sensitivity restoration signal from the electronic device through the communication module the processor may restore the decreased sensitivity of the microphone to the original sensitivity. Furthermore for example if an event e.g. communication with the electronic device has ended or has been paused the processor may restore the decreased sensitivity of the microphone to the original sensitivity.

The D A conversion module may convert the digital sound signal digital signal processed in the hearing aid control module into an analog signal and output the analog signal through the speaker .

According to various embodiments of the present disclosure the hearing aid as illustrated in may include at least one microphone the speaker the communication module and the processor for controlling a microphone sensitivity of the hearing aid based on a control signal provided from the electronic device as illustrated in amplifying a sound signal provided from the electronic device through the communication module and outputting the amplified sound signal to the speaker of the hearing aid .

In an embodiment of the present disclosure the processor may control the microphone sensitivity such that the microphone of the hearing aid is inactivated based on the control signal provided from the electronic device .

In an embodiment of the present disclosure if an event with the electronic device has ended or has been paused the processor may restore the microphone sensitivity of the hearing aid amplify a sound signal collected through the microphone of the hearing aid and output the amplified sound signal through the speaker of the hearing aid .

In an embodiment of the present disclosure if a control signal for restoring the microphone sensitivity of the hearing aid is received from the electronic device through the communication module the processor may restore the microphone sensitivity of the hearing aid amplify a sound signal collected through the microphone of the hearing aid and output the amplified sound signal through the speaker of the hearing aid .

Referring to a procedure is illustrated such that in operation an electronic device may transmit a microphone sensitivity control signal to a hearing aid. For example the electronic device may transmit the microphone sensitivity control signal to the hearing aid using a BLE protocol communication method. The electronic device may deform a data transmission interval and a data transmission duration being defined in the BLE protocol such that transmission of a sound signal is possible.

In operation the electronic device may transmit a sound signal collected through a microphone of the electronic device to the hearing aid. For example the electronic device as illustrated in may perform digital signal processing such as noise removal for a sound signal collected through the microphone as illustrated in and transmit the processed sound signal to the hearing aid as illustrated in .

Referring to a procedure is illustrated such that in operation a hearing aid may receive a microphone sensitivity control signal from an electronic device.

In operation the hearing aid may decrease a sensitivity of a microphone of the hearing aid based on the microphone sensitivity control signal received from the electronic device. For example the hearing aid as illustrated in may control a microphone sensitivity such that the microphone as illustrated in is inactivated based on the microphone sensitivity control signal.

In operation the hearing aid may amplify a sound signal provided from the electronic device and output the amplified sound signal through a speaker of the hearing aid.

Referring to a procedure is illustrated such that if amplifying a sound signal provided from an electronic device and if outputting the amplified sound signal through the speaker of the hearing aid is performed as in operation of in operation the hearing aid may sense if an event for microphone sensitivity restoration occurs. For example if an event e.g. communication with the electronic device has ended or has been paused the hearing aid may recognize that the event for microphone sensitivity restoration takes place. Furthermore for example if a control signal for microphone sensitivity restoration is received from the electronic device the hearing aid may recognize that the event for microphone sensitivity restoration takes place.

If the event for microphone sensitivity restoration does not take place in operation the hearing aid may proceed to operation of to amplify a sound signal provided from the electronic device and to output the amplified sound signal through the speaker of the hearing aid.

If the event for microphone sensitivity restoration takes place in operation then in operation the hearing aid may restore a sensitivity of a microphone of the hearing aid. For example the hearing aid may control the microphone sensitivity such that the microphone is activated.

In operation the hearing aid may amplify a sound signal collected through the microphone of the hearing aid based on the restored sensitivity of the microphone of the hearing aid and may output the amplified sound signal through the speaker of the hearing aid.

Referring to a procedure is illustrated such that in operation an electronic device may check if an event service e.g. a telephony service with a counterpart electronic device is provided. For example the electronic device as illustrated in may receive a call from the counterpart electronic device as illustrated in and check if a call with the counterpart electronic device is connected. Furthermore for example the electronic device may perform a call connection with the counterpart electronic device based on input information detected through the input module as illustrated in .

If the event service e.g. telephony service with the counterpart electronic device is not connected in operation the electronic device may return to operation and again check if the event service e.g. telephony service with the counterpart electronic device is connected.

If the event service e.g. telephony service with the counterpart electronic device is connected in operation the electronic device may proceed to operation and check if communication with the hearing aid is connected. For instance the electronic device may check a communication state with the hearing aid.

If the communication with the hearing aid is not connected in operation the electronic device may terminate the present algorithm. For example the electronic device may provide a telephony service with the counterpart electronic device using the speaker and the microphone as illustrated in .

If the communication with the hearing aid is connected in operation then in operation the electronic device may transmit a microphone sensitivity control signal to the hearing aid.

In operation the electronic device may transmit a call reception signal provided from the counterpart electronic device to the hearing aid. For example the electronic device may perform digital signal processing such as noise removal for the call reception signal provided from the counterpart electronic device through the communication module as illustrated in and transmit the processed call reception signal to the hearing aid as illustrated in .

Referring to a procedure is illustrated such that in operation a hearing aid may check if a microphone sensitivity control signal is received from an electronic device.

If the microphone sensitivity control signal is not received from the electronic device in operation the hearing aid may return to operation and again check if the microphone sensitivity control signal is received from the electronic device. The hearing aid may amplify a sound signal collected through a microphone of the hearing aid based on a preset microphone sensitivity and output the amplified sound signal through a speaker of the hearing aid.

If the microphone sensitivity control signal is received from the electronic device in operation the hearing aid may proceed to operation and decrease a sensitivity of the microphone of the hearing aid based on the microphone sensitivity control signal provided from the electronic device. For example the hearing aid as illustrated in may control the microphone sensitivity such that the microphone as illustrated in is inactivated based on the microphone sensitivity control signal.

In operation the hearing aid may check if a call reception signal is received from the electronic device.

If the call reception signal is not received from the electronic device in operation the hearing aid may return to operation and again check if the call reception signal is received from the electronic device. If the call reception signal is not received during a valid time after controlling the sensitivity of the microphone the hearing aid may restore the microphone sensitivity to the original sensitivity amplify a sound signal collected through the microphone of the hearing aid and output the amplified sound signal through the speaker of the hearing aid.

If the call reception signal is received from the electronic device in operation the hearing aid may proceed to operation to amplify the received call reception signal and to output the amplified call reception signal through the speaker of the hearing aid.

Referring to a procedure is illustrated such that in operation the electronic device may check if a telephony event takes place. For example the electronic device as illustrated in may check if a call is received from the counterpart electronic device as illustrated in .

If the telephony event does not take place in operation the electronic device may return to operation and again check if the telephony event takes place.

If the telephony event occurs in operation the electronic device may go to operation and check if communication with the hearing aid is connected.

If the communication with the hearing aid is not connected in operation the electronic device may terminate the present algorithm. For example the electronic device may provide a telephony service with the counterpart electronic device using the speaker and the microphone as illustrated in .

If the communication with the hearing aid is connected in operation the electronic device may proceed to operation and transmit a microphone sensitivity control signal to the hearing aid.

In operation the electronic device may transmit telephony event occurrence information to the hearing aid.

In operation the electronic device may check if a call connection signal is received from the hearing aid.

If the call connection signal is not received from the hearing aid in operation the electronic device may return to operation and again check if the call connection signal is received from the hearing aid. If the call connection signal is not received during a valid time after transmitting the telephony event occurrence information the electronic device may recognize that the call connection fails and terminate the present algorithm.

If the call connection signal is received from the hearing aid in operation the electronic device may proceed to operation and connect a call with the counterpart electronic device and transmit to the hearing aid a call reception signal provided from the counterpart electronic device. For example the electronic device may perform digital signal processing such as noise removal for the call reception signal provided from the counterpart electronic device through the communication module as illustrated in and transmit the processed call reception signal to the hearing aid as illustrated in .

In the aforementioned embodiment the electronic device may connect a call with the counterpart electronic device based on the call connection signal provided from the hearing aid.

In another embodiment the electronic device may connect a call with the counterpart electronic device based on input information detected through the input module of the electronic device.

Referring to a procedure is illustrated such that in operation a hearing aid may check if a microphone sensitivity control signal is received from an electronic device.

If the microphone sensitivity control signal is not received from the electronic device in operation the hearing aid may return to operation and again check if the microphone sensitivity control signal is received from the electronic device. The hearing aid may amplify a sound signal collected through a microphone of the hearing aid based on a preset microphone sensitivity and output the amplified sound signal through a speaker of the hearing aid.

If the microphone sensitivity control signal is received from the electronic device in operation the hearing aid may proceed to operation and control e.g. decrease a sensitivity of the microphone based on the microphone sensitivity control signal provided from the electronic device. For example the hearing aid as illustrated in may control the microphone sensitivity such that the microphone as illustrated in is inactivated based on the microphone sensitivity control signal.

In operation the hearing aid may check if telephony event occurrence information is received from the electronic device.

If the telephony event occurrence information is not received from the electronic device in operation the hearing aid may return to operation and again check if the telephony event occurrence information is received from the electronic device. If the telephony event occurrence information is not received during a valid time after controlling the sensitivity of the microphone the hearing aid may restore the microphone sensitivity amplify a sound signal collected through the microphone of the hearing aid and output the amplified sound signal through the speaker of the hearing aid.

If the telephony event occurrence information is received from the electronic device in operation the hearing aid may proceed to operation and generate output a telephony event occurrence sound through the speaker of the hearing aid.

In operation the hearing aid may check if a call connection input is detected. For example the hearing aid as illustrated in may check if a user s input for call connection is detected through an input unit not shown .

If the call connection input is not detected in operation the hearing aid may return to operation and again check if the call connection input is detected.

If the call connection input is detected in operation the hearing aid may proceed to operation and transmit call connection information including the call connection input to the electronic device.

In operation the hearing aid may check if a call reception signal is received from the electronic device.

If the call reception signal is not received from the electronic device in operation the hearing aid may return to operation and again check if the call reception signal is received from the electronic device. If the call reception signal is not received during a valid time after transmitting the call connection information the hearing aid may restore the microphone sensitivity amplify a sound signal collected through the microphone of the hearing aid and output the amplified sound signal through the speaker of the hearing aid.

If the call reception signal is received from the electronic device in operation then in operation the hearing aid may amplify the call reception signal and output the amplified call reception signal through the speaker of the hearing aid.

Referring to a procedure is illustrated such that when transmitting the call reception signal to the hearing aid in operation of or operation of in operation the electronic device may collect a sound signal through a microphone of the electronic device.

After operation the electronic device may separate the sound signal collected through the microphone of the electronic device into a surrounding sound and a user voice.

After separating the sound signal into the surrounding sound and the user voice in operation the electronic device may also proceed to operation and transmit the surrounding sound to the hearing aid. For example when a call reception signal to be transmitted to the hearing aid exists the electronic device may transmit the surrounding sound to the hearing aid together with the call reception signal.

If separating the sound signal into the surrounding sound and the user voice in operation the electronic device may proceed to operation and transmit the user voice to a counterpart electronic device providing a telephony service.

In the aforementioned embodiment the electronic device may separate the surrounding sound among the sound signal collected through the microphone of the electronic device and transmit the surrounding sound to the hearing aid.

In another embodiment the electronic device may transmit the sound signal collected through the microphone of the electronic device to the hearing aid. For example when a call reception signal to be transmitted to the hearing aid exists the electronic device may transmit the sound signal collected through the microphone of the electronic device to the hearing aid together with the call reception signal.

Referring to a procedure is illustrated such that when transmitting the call reception signal to the hearing aid in operation of or operation of in operation the electronic device may check if a user s danger situation is sensed. For example the electronic device as illustrated in may check if the user s danger situation is sensed based on a sound signal collected through the microphone as illustrated in .

If the user s danger situation is not sensed in operation the electronic device may return to operation and again check if the user s danger situation is sensed.

If the danger situation is sensed in operation then in operation the electronic device may transmit a danger signal to the hearing aid. For example when the call reception signal to be transmitted to the hearing aid exists the electronic device may transmit the danger signal to the hearing aid together with the call reception signal.

Referring to a procedure is illustrated such that when transmitting the call reception signal to the hearing aid in operation of or operation of in operation the electronic device may check if a call connection with a counterpart electronic device has ended.

If the call connection with the counterpart electronic device has not ended in operation the electronic device may return to operation and again check if the call connection with the counterpart electronic device has ended.

If the call connection with the counterpart electronic device has ended in operation then in operation the electronic device may transmit a microphone sensitivity restoration signal for restoring a microphone sensitivity of the hearing aid to the hearing aid.

Referring to a procedure is illustrated such that when transmitting the call reception signal to the hearing aid in operation of or operation of in operation the electronic device may check if it performs a call e.g. telephony with a counterpart electronic device using a peripheral device. For example the electronic device may check if it performs telephony with the counterpart electronic device using a wearable device.

If the call is not performed with the counterpart electronic device using the peripheral device in operation the electronic device may transmit the call reception signal to the hearing aid in operation of or operation of FIG. .

If the call is performed with the counterpart electronic device using the peripheral device in operation then in operation the electronic device may transmit a microphone sensitivity restoration signal for restoring a microphone sensitivity of the hearing aid to the hearing aid.

In the aforementioned embodiment the electronic device may control the microphone sensitivity of the hearing aid and check if it performs the call with the counterpart electronic device using the peripheral device during transmission of a call reception signal.

In another embodiment the electronic device may check whether to perform the telephony with the counterpart electronic device using the peripheral device before controlling the microphone sensitivity of the hearing aid. For example if the telephony event occurs in operation of the electronic device may check whether to perform the telephony with the counterpart electronic device using the peripheral device. If not using the peripheral device in operation the electronic device may check if the communication with the hearing aid has been connected.

Referring to a procedure is illustrated such that when amplifying the call reception signal provided from the electronic device and outputting the amplified call reception signal through the speaker in operation of or operation of in operation the hearing aid may check if a microphone sensitivity restoration signal is received from the electronic device.

If the microphone sensitivity restoration signal is not received from the electronic device in operation the hearing aid may return to operation and again check if the microphone sensitivity restoration signal is received from the electronic device. Accordingly the hearing aid may amplify the call reception signal provided from the electronic device and output the amplified call reception signal through a speaker of the hearing aid.

If the microphone sensitivity restoration signal is received from the electronic device in operation then in operation the hearing aid may restore a microphone sensitivity based on the microphone sensitivity restoration signal. For example the hearing aid as illustrated in may control the microphone sensitivity such that the microphone is activated as illustrated in .

In operation the hearing aid may amplify a sound signal collected through a microphone of the hearing aid based on the restored microphone sensitivity and output the amplified sound signal through a speaker of the hearing aid.

In the aforementioned embodiment the electronic device may transmit the sound signal collected through the microphone of the electronic device to the hearing aid. Accordingly the electronic device may perform beamforming for the sound signal and process the sound signal such that the sound signal is focused in a specific direction and transmit the processed sound signal to the hearing aid.

Referring to a 1electronic device a 2electronic device and a hearing aid are illustrated where the 1electronic device may decide a microphone array such that a sound signal collected through a microphone of the 1electronic device a microphone of the 2electronic device and at least one microphone and or of the hearing aid is focused in a specific direction. Corresponding to the microphone array the 1electronic device may control activation inactivation of at least one microphone among the microphone of the 1electronic device the microphone of the 2electronic device and or the at least one microphone and or of the hearing aid . Here the 2electronic device may include a wearable device.

In the aforementioned embodiment the electronic device as illustrated in may control a microphone sensitivity of the hearing aid as illustrated in whose communication is performed. In this regard as in the electronic device may communicate with the hearing aid for controlling microphone sensitivity using an electronic tag of the hearing aid .

Referring to a procedure is illustrated such that in operation the electronic device may collect tag information of a hearing aid for controlling a microphone sensitivity from an electronic tag such as an NFC tag. For example the electronic device may collect tag information of a hearing aid from an electronic tag inserted to the corresponding hearing aid. Furthermore for example the electronic device may collect tag information of the hearing aid from an electronic tag existing in a place separate from the hearing aid such as a product box of the hearing aid or a retailer thereof. Here the tag information of the hearing aid may include one or more of identification information of the hearing aid and communication link setting information of the hearing aid.

In operation the electronic device may communicate with the corresponding hearing aid based on the tag information of the hearing aid. For example the electronic device may search if a hearing aid connectable for microphone sensitivity control exists based on tag information of the hearing aid. If the hearing aid is located the electronic device may communicate with the corresponding hearing aid e.g. operation of . Furthermore for example the electronic device may search if a hearing aid connectable for microphone sensitivity control exists based on tag information of the hearing aid. If the hearing aid is located the electronic device may transmit a microphone sensitivity control signal to the corresponding hearing aid e.g. operation of .

According to various embodiments of the present disclosure an operation method of an electronic device may include the operations of transmitting a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid and transmitting a reception signal provided from a counterpart electronic device to the hearing aid.

In an embodiment of the present disclosure the operation of transmitting the reception signal to the hearing aid may include the operation of transmitting the reception signal provided from the counterpart electronic device to the hearing aid using a short range communication method.

In an embodiment of the present disclosure the short range communication method may include one or more of WiFi Bluetooth and or NFC.

In an embodiment of the present disclosure the operation of transmitting the reception signal to the hearing aid may include the operation of transmitting the reception signal provided from the counterpart electronic device to the hearing aid using a Bluetooth Low Energy BLE protocol communication method deforming one or more of a data transmission interval or a data transmission duration.

In an embodiment of the present disclosure the method may further include the operations of collecting a sound signal through a microphone of the electronic device and transmitting at least a portion of the sound signal collected through the microphone of the electronic device to the hearing aid.

In an embodiment of the present disclosure the operation of transmitting the at least portion of the sound signal to the hearing aid may include the operations of separating the sound signal collected through the microphone of the electronic device into a surrounding sound and a user voice and transmitting the surrounding sound to the hearing aid.

In an embodiment of the present disclosure the processor may check user s danger occurrence or non occurrence using the sound signal collected through the microphone of the electronic device and if sensing the user s danger occurrence transmit a danger signal to the hearing aid through the communication module.

In an embodiment of the present disclosure the method may further include the operation of if an event for microphone sensitivity restoration takes place transmitting a control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid.

In an embodiment of the present disclosure the operation of transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid may include the operation of if an event with the counterpart electronic device has ended transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid.

In an embodiment of the present disclosure the operation of transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid may include the operations of checking if it provides an event service with the counterpart electronic device using a peripheral device and if providing the event service with the counterpart electronic device using the peripheral device transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid.

In an embodiment of the present disclosure the method may further include the operation of if transmitting the control signal for restoring the microphone sensitivity of the hearing aid to the hearing aid inactivating a speaker of the electronic device.

In an embodiment of the present disclosure the operation of transmitting the control signal for controlling the microphone sensitivity of the hearing aid to the hearing aid may include the operation of if a telephony event with the counterpart electronic device takes place transmitting the control signal for controlling the microphone sensitivity of the hearing aid to the hearing aid.

According to various embodiments of the present disclosure an operation method of an electronic device may include the operations of transmitting a control signal for controlling a microphone sensitivity of a hearing aid to the hearing aid and transmitting a sound signal collected through a microphone of the electronic device to the hearing aid.

In an embodiment of the present disclosure before the operation of transmitting the control signal to the hearing aid the method may further include the operations of collecting electronic tag information of the hearing aid and connecting communication with the hearing aid based on the electronic tag information.

According to various embodiments of the present disclosure an operation method of a hearing aid may include the operations of controlling a microphone sensitivity of the hearing aid based on a control signal provided from an electronic device amplifying a sound signal provided from the electronic device and outputting the amplified sound signal to a speaker of the hearing aid.

In an embodiment of the present disclosure the operation of controlling the microphone sensitivity may include the operation of controlling the microphone sensitivity such that a microphone of the hearing aid is inactivated based on the control signal provided from the electronic device.

In an embodiment of the present disclosure the method may further include the operations of checking an event state with the electronic device and if an event with the electronic device has ended or has been paused restoring the microphone sensitivity of the hearing aid amplifying a sound signal collected through the microphone of the hearing aid and outputting the amplified sound signal through the speaker of the hearing aid.

In an embodiment of the present disclosure the method may further include the operations of if receiving a control signal for restoring the microphone sensitivity of the hearing aid from the electronic device restoring the microphone sensitivity of the hearing aid amplifying a sound signal collected through the microphone of the hearing aid and outputting the amplified sound signal through the speaker of the hearing aid.

In accordance to various embodiments of the present disclosure if a hearing aid is connected with an electronic device the hearing aid may collect a sound signal using a microphone of the electronic device thereby preventing a feedback phenomenon of the hearing aid.

In accordance to various embodiments of the present disclosure upon telephony service provision a hearing aid may inactivate a microphone of the hearing aid and amplify and output a call reception signal provided from the electronic device thereby preventing a feedback phenomenon of the hearing aid.

In accordance to various embodiments of the present disclosure an electronic device may perform digital signal processing such as noise removal for a sound signal collected using a microphone of the electronic device and transmit the digital signal processed sound signal to a hearing aid thereby improving a sound quality of the hearing aid.

While the present disclosure has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present disclosure as defined by the appended claims and their equivalents.


---

title: System and method for providing cloud printing service
abstract: Provided is an image forming system operable to provide a cloud printing service, the image forming system comprising: a transmitting device operable to transmit content by designating a target phone number; a cloud printing server operable to receive the target phone number and the content from the transmitting device; a receiving device assigned with the target phone number and operable to receive an upload notification of the content with respect to the target phone number from the cloud printing server; and an image forming device operable to print the content by receiving the content from the cloud printing server, wherein the cloud printing server transmits the content to the image forming device registered in the target phone number when the cloud printing service is requested for the content to the target phone number.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09661160&OS=09661160&RS=09661160
owner: S-PRINTING SOLUTION CO., LTD.
number: 09661160
owner_city: Suwon-si
owner_country: KR
publication_date: 20151229
---
This is a continuation application based on U.S. patent application Ser. No. 14 503 238 filed on Sep. 30 2014 and which claims the priority benefit of Korean Patent Application No. 10 2013 0116716 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116717 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116718 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116917 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116918 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116919 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116920 filed on Sep. 30 2013 Korean Patent Application No. 10 2013 0116921 filed on Sep. 30 2013 Korean Patent Application No. 10 2014 0011733 filed on Jan. 29 2014 Korean Patent Application No. 10 2014 0015172 filed on Feb. 10 2014 Korean Patent Application No. 10 2014 0027433 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027434 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027435 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027436 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027437 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027438 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027439 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027440 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027441 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027465 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0027466 filed on Mar. 7 2014 Korean Patent Application No. 10 2014 0105434 filed on Aug. 13 2014 in the Korean Intellectual Property Office and U.S. Provisional Application No. 61 937 835 filed on Feb. 10 2014 in the USPTO the disclosures of which are incorporated herein in their entirety by reference.

Examples of an image forming apparatus include individual apparatuses such as a printer a scanner a photocopier and a facsimile and a multi function product MFP in which various functions of the individual apparatuses are combined. Recently such an image forming apparatus includes a wired communication module such as Ethernet or a wireless communication module such as Wi Fi Wi Fi direct near field communication NFC Bluetooth zigbee or infrared data association IrDA to be connected to a mobile device or a user device such as a laptop through a network. Also the image forming apparatus may upload or download a document to or from a cloud server by connecting to the cloud server by using the wired or wireless communication module.

One or more embodiments may include a cloud printing system and a method for providing a phone number based cloud printing service. Also one or more embodiments include a computer readable recording medium having recorded thereon a program for executing the method.

Additional aspects will be set forth in part in the description which follows and in part will be apparent from the description or may be learned by practice of the presented embodiments.

According to one or more embodiments there is provided an image forming system operable to provide a cloud printing service the image forming system comprising a transmitting device operable to transmit content by designating a target phone number a cloud printing server operable to receive the target phone number and the content from the transmitting device a receiving device assigned with the target phone number and operable to receive an upload notification of the content with respect to the target phone number from the cloud printing server and an image forming device operable to print the content by receiving the content from the cloud printing server wherein the cloud printing server transmits the content to the image forming device registered in the target phone number when the cloud printing service is requested for the content to the target phone number.

The transmitting device may include a user interface unit operable to receive input information about the content and the target phone number a controller operable to generate print job information including the content and the target phone number and a network interface unit operable to transmit the generated print job information to the cloud printing server.

The transmitting device may include a user interface unit operable to display a list of contacts and a list of contents which are stored in the transmitting device and a network interface unit operable to transmit the content and the target phone number to the cloud printing server when the content and the target phone number are set from among the lists displayed through the user interface unit.

The user interface unit may display the list of contents which is stored in the transmitting device when the list of contacts is displayed and the target phone number is selected from the displayed list of contacts.

The user interface unit may display the list of contacts which is stored in the transmitting device when the list of contents is displayed and the content is selected from the displayed list of contents.

The cloud printing server may include a network interface unit operable to receive print job information including the content and the target phone number from the transmitting device a controller operable to register the print job information by mapping the content and the target phone number and a storage unit operable to store the registered print job information.

The cloud printing server may receive from at least one of the receiving device and the image forming device registration request information including the target phone number and identification information of the image forming device to be mapped to the target phone number and manages registration information about the image forming device mapped to the target phone number based on the received registration request information.

The identification information may include a media access control MAC address of the image forming device the cloud printing server may receive from the image forming device meta information comprising at least one of the MAC address an internet protocol IP address a serial number and a product name of the image forming device maps the target phone number and the image forming device by using the identification information and the meta information when the registration request information is received and transmits the meta information of the image forming device to the receiving device and the receiving device may identify the image forming device registered in the target phone number by using the meta information received from the cloud printing server.

The receiving device may include a network interface unit operable to receive from the cloud printing server the upload notification indicating that the content corresponding to the target phone number is registered in the cloud printing server a user interface unit operable to display information about the content based on the received upload notification and a controller operable to generate a print request about the content wherein the network interface unit may transmit the generated print request to the cloud printing server.

When the print request is received from the receiving device the cloud printing server may identify the image forming device for processing the received print request and transmits print data of the content to the identified image forming device.

According to one or more embodiments there is provided a method of providing by an image forming system a cloud printing service the method comprising transmitting by a transmitting device content by designating a target phone number receiving by a cloud printing server the target phone number and the content from the transmitting device receiving by a receiving device assigned with the target phone number an upload notification of the content with respect to the target phone number from the cloud printing server and printing by an image forming device the content by receiving the content from the cloud printing server wherein the cloud printing server transmits the content to the image forming device registered in the target phone number when the cloud printing service is requested for the content to the target phone number.

The method may further include displaying by the transmitting device a list of contacts and a list of contents which are stored in the transmitting device wherein the transmitting of the content may include when the content and the target phone number are set from among the displayed lists transmitting the set content and the set target phone number to the cloud printing server.

The method may further include receiving by the cloud printing server print job information including the content and the target phone number from the transmitting device registering by the cloud printing server the print job information by mapping the content and the target phone number and storing by the cloud printing server the registered print job information.

The method may further include receiving by the cloud printing server registration request information including the target phone number and identification information of the image forming device to be mapped to the target phone number from at least one of the receiving device and the image forming device updating by the cloud printing server registration information about the image forming device mapped to the target phone number based on the received registration request information and storing by the cloud printing server the updated registration information.

The identification information may include a media access control MAC address of the image forming device and the method may further include receiving by the cloud printing server meta information comprising at least one of the MAC address an internet protocol IP address a serial number and a product name of the image forming device from the image forming device mapping by the cloud printing server the target phone number and the image forming device by using the identification information and the meta information when the registration request information is received transmitting by the cloud printing server the meta information of the image forming device to the receiving device and identifying by the receiving device the image forming device registered in the target phone number by using the meta information received from the cloud printing server.

The method may further include receiving by the receiving device the upload notification indicating that the content corresponding to the target phone number is registered in the cloud printing server from the cloud printing server displaying by the receiving device information about the content based on the received upload notification generating by the receiving device a print request about the content and transmitting by the receiving device the generated print request to the cloud printing server.

According to one or more embodiments there is provided an image forming system operable to provide a cloud printing service the image forming system may include a cloud printing server operable to receive from a transmitting device content and a target phone number of a receiving device to which the cloud printing service for the content is to be provided and an image forming device operable to print the content by receiving the content from the cloud printing server wherein the cloud printing server maps and registers the target phone number and the image forming device so as to perform the cloud printing service on the target phone number requested by the transmitting device.

The cloud printing server may receive from at least one of the receiving device and the image forming device the target phone number and identification information of the image forming device to be mapped to the target phone number and manages registration information about the image forming device mapped to the target phone number based on the received registration request information.

According to one or more embodiments there is provided a method of providing by an image forming system a cloud printing service the method may include receiving by a cloud printing server content and a target phone number of a receiving device to which the cloud printing service for the content is to be provided from a transmitting device receiving by an image forming device the content from the cloud printing server and printing by the image forming device the received content wherein the cloud printing server maps and registers the target phone number and the image forming device so as to process a request of the cloud printing service on the target phone number.

In an aspect of one or more embodiments there is provided at least one non transitory computer readable medium storing computer readable instructions which when executed implement methods of one or more embodiments.

Reference will now be made in detail to embodiments examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to like elements throughout. Embodiments may have different forms and should not be construed as being limited to the disclosure set forth herein. Accordingly embodiments are merely described below by referring to the figures to explain aspects of the present disclosure.

In the present disclosure it is to be understood that the terms such as including or having etc. are intended to indicate the existence of the features numbers steps actions components parts or combinations thereof disclosed in the specification and are not intended to preclude the possibility that one or more other features numbers steps actions components parts or combinations thereof may exist or may be added.

While such terms as first second etc. may be used to describe various components such components must not be limited to the above terms. The above terms are used only to distinguish one component from another.

Expressions such as at least one of when preceding a list of elements modify the entire list of elements and do not modify the individual elements of the list.

One or more embodiments relate to a method and system for providing a cloud printing service and a cloud server for supporting the cloud printing service and detailed explanations of related art well known to one of ordinary skill in the art may be omitted.

Referring to a first individual for example John Lee may transmit a content such as an image or a document stored in a mobile device of the first individual to a mobile device of a second individual for example Jane Kim so that the second individual prints the content through an image forming apparatus .

The content stored in the mobile device of the first individual is transmitted to the mobile device of the second individual based on a phone number of the mobile device .

The mobile devices and herein may each be a portable mobile device or user device having a mobile communication function such as a smart phone a tablet device portable media player PMP digital camera personal computer PC laptop computer notebook computer portable game player wearable device or a personal digital assistant PDA but are not limited thereto. Further it is understood that embodiments are also applicable to any device with which an apparatus method or medium of an embodiment can be used.

Such a portable mobile device having a mobile communication function is capable of a telephone call by using a well known mobile communication technology such as a second generation 2G mobile communication a third generation 3G mobile communication or a fourth generation 4G mobile communication.

In detail one intrinsic phone number is assigned to each portable mobile device by a telecommunication company and the portable mobile devices are distinguished from each other via the intrinsic phone numbers.

Accordingly one phone number is assigned to each of the mobile device of the first individual and the mobile device of the second individual . In other words the phone number may be an intrinsic identification ID number of the mobile device or .

Referring to the first individual may transmit a content to the second individual that is a subject to print the content by inputting the phone number of the second individual . Then the second individual may print the received content by using the image forming apparatus .

An image forming system for providing a phone number based cloud printing service according to an embodiment will now be described in detail.

In an embodiment types of the mobile devices and of the first and second individuals and are not limited to the above and the mobile devices and may be any devices as long as they are user devices to which a phone number is assigned.

Referring to the image forming system includes the mobile device used by the first individual for example John Lee the mobile device used by the second individual for example Jane Kim a mobile device used by a third individual for example Brad Jones a mobile device used by a fourth individual for example Tom Smith a plurality of image forming apparatuses and and a cloud server .

The number of the first through fourth individuals through and the number of image forming apparatuses through included in the image forming system are arbitrarily set for convenience of description and thus are not limited thereto.

Also the names of the first through fourth individuals through are arbitrarily determined for convenience of description and thus are not limited thereto.

The first individual may transmit print data of a content by inputting a phone number of at least one subject for example the second individual from among subjects to print the content to the mobile device . Also the first individual may transmit the print data of the content to another individual for example the third or fourth individual or by inputting a phone number of the other individual to the mobile device .

For example let s assume that the first individual is to transmit the print data of the content to the second individual through the mobile device .

The first individual may select a content stored in or being used by the mobile device and input the phone number of the second individual that is a subject to print the data to the mobile device .

Information about the selected content and the input phone number are transmitted to the cloud server .

The cloud server is a server for managing the phone numbers of the mobile devices through . In detail the cloud server may be a server for managing information about a mapping relationship between the phone numbers of the mobile devices through and the image forming apparatuses through and information about a mapping relationship between the phone numbers of the mobile devices through and contents transmitted from the mobile devices through .

Also the cloud server may perform cloud rendering for rendering or converting a content that is not in a print data format to a print data format.

When the phone number of the second individual and the information about the selected content are transmitted from the mobile device of the first individual the cloud server renders or converts the received content to a print data format and transmits print data of the content to the mobile device of the second individual based on the phone number of the second individual mapped to the content.

When the mobile device of the second individual receives the information about the selected content from the cloud server the print data of the content may be printed by at least one of the image forming apparatuses through assigned mapped by the mobile device .

In detail when the second individual pre set a direct printing mode or a direct printing function regarding printing of the content in the mobile device the print data of the content may be automatically printed by at least one of the image forming apparatuses through . Such a direct printing mode will be described in detail later.

Alternatively when the second individual pre set a pull printing mode or a pull printing function regarding printing of the content in the mobile device the print data of the content is not automatically printed by at least one of the image forming apparatuses through but may be held may stand by until a process request is input to the mobile device by the second individual . In other words unlike the direct printing mode in the pull printing mode the mobile device displays the information about the selected content to the second individual and processes the content when the second individual inputs the process request.

The second individual may input a print request to the at least one of the image forming apparatuses through assigned mapped by the mobile device . Alternatively the second individual may input a forwarding request for forwarding the content to the other individual for example the third or fourth individual or . Alternatively when the second individual does not want to print the content the second individual may input a delete request for deleting the information about the selected content stored in the cloud server . Such a pull printing mode will be described in detail later.

Pull printing and direct printing will be described in detail later with reference to corresponding descriptions.

The cloud server may pre manage information about the image forming apparatus mapped to the mobile device of the second individual . Accordingly the cloud server transmits the print data of the content transmitted to the mobile device of the second individual to the image forming apparatus mapped to the mobile device . Then the image forming apparatus prints the content based on the print data of the content and thus a request of the mobile device of the first individual to print the content is completed.

The same processes are performed when the print data of the content is to be transmitted from the mobile device of the first individual to the third or fourth individual or .

The cloud server may manage that only the image forming apparatus is mapped to the mobile device of the second individual but the other image forming apparatus or may be additionally mapped thereto.

Alternatively even when none of the image forming apparatuses through are currently mapped to the mobile device of the second individual registration information about a mapping relationship may be updated in the cloud server by performing a registration process of the mobile devices through with respect to one of the image forming apparatuses through as described later.

The mobile devices through the image forming apparatuses through and the cloud server in the image forming system may be connected to each other through any one of currently well known types of wired wireless communication networks and mobile communication networks.

Referring back to the image forming system may transmit and receive a content to be printed by only using the phone numbers of the mobile devices through and may print a content by using the various image forming apparatuses through .

A printing platform of the image forming system may be provided to an open application programmer interface API for an application developer or a webpage manufacturer. Accordingly the application developer or the webpage manufacturer may freely develop a print application executed in the mobile device or or the image forming apparatus or by using the open API of the image forming system based on the printing platform.

Operations and functions of components included in the image forming system for providing a phone number based cloud printing service will now be described in detail.

Referring to the user device may correspond to at least any one of the mobile devices through of the image forming system of . In other words the user device may be the mobile device that is a transmitter terminal for transmitting a content to be printed or the mobile device or that is a receiver terminal for receiving a content to be printed. Alternatively the user device may be a computing device of connectable to an embedded webpage provided by the image forming apparatus or .

The user device includes a user interface UI unit user interface a controller and a network interface unit network interface . In order to prevent features of an embodiment from being blurred only hardware components related to an embodiment are described in . However general purpose hardware components other that those shown in may be included in the user device .

The UI unit is a hardware component including an input device or a display device and displays information to a user of the user device or receives information from the user. The user interface may include for example one or more of a keyboard a keypad a mouse a joystick a button a switch an electronic pen or stylus a gesture recognition sensor e.g. to recognize gestures of a user including movements of a body part an input sound device or voice recognition sensor e.g. a microphone to receive a voice command an output sound device e.g. a speaker a track ball a pedal or footswitch a virtual reality device and the like. The user interface may further include a haptic device to provide haptic feedback to a user. The user interface may also include a touchscreen display for example. The touchscreen display may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display and the like for example. However the disclosure is not so limited thereto and may include other types of touchscreen displays. The disclosure may also include other types of user interfaces.

The user may select a content to be printed which is received from for example outside the user device or may set print options of the content. Also the user may input a phone number that is an external destination through the UI unit .

The controller is a hardware component for controlling overall operations and functions of the user device . In detail the controller may execute a printing application for providing a phone number based cloud printing service.

The controller may be realized in at least one processor such as a central processing unit CPU an application processor AP an arithmetic logic unit a graphics processing unit GPU a digital signal processor DSP a microcomputer a field programmable gate array a programmable logic unit an application specific integrated circuit ASIC a microprocessor or any other device capable of responding to and executing computer readable instructions.

The network interface unit is a hardware component for supporting a wired or wireless communication function and may support a wireless communication such as Wi Fi Wi Fi Direct a near field communication NFC Zigbee infrared data association IrDA or Bluetooth a wired communication such as Ethernet or a 2G mobile communication a 3G mobile communication or a 4G mobile communication.

Referring to the cloud server may correspond to the cloud server of the image forming system of . It is assumed that the cloud server described hereinafter includes components of the cloud server of .

The cloud server includes a controller a storage unit storage and a network interface unit network interface . In order to prevent features of an embodiment from being blurred only hardware components related to an embodiment are described in . However general purpose hardware components other that those shown in may be included in the cloud server .

The controller is a hardware component for controlling overall operations and functions of the cloud server . The controller may manage and update mapping information of the phone numbers of the first through fourth individuals through or may operate as a renderer for rendering or converting a content.

The storage unit stores phone number registration information with respect to a list of the phone numbers of the first through fourth individuals through a list of contents mapped to the phone numbers and a list of the image forming apparatuses through mapped to the phone numbers.

The network interface unit network interface is a hardware component for supporting a wired or wireless communication function and may support a wireless communication such as Wi Fi Wi Fi Direct an NFC Zigbee infrared data association IrDA or Bluetooth a wired communication such as Ethernet or a 2G mobile communication a 3G mobile communication or a 4G mobile communication.

Referring to the image forming apparatus may correspond to at least one of the image forming apparatuses through of the image forming system of . It is assumed that the image forming apparatuses through include components of the image forming apparatus of .

The image forming apparatus includes a UI unit user interface a controller a network interface unit network interface and an image forming unit image forming apparatus . In order to prevent features of an embodiment from being blurred only hardware components related to an embodiment are described in . However general purpose hardware components other that those shown in may be included in the image forming apparatus .

A printing application providing a phone number based cloud printing service which has similar functions as the printing application of the mobile device of the first individual described above may be pre installed on an operating system OS of the image forming apparatus . Alternatively even if such a printing application is not pre installed in the image forming apparatus a printing application may be newly installed on the OS of the image forming apparatus by one of the first through fourth individuals through who wants to use the image forming apparatus .

The user interface UI unit is a hardware component including an input device or a display device and displays information to a user of the image forming apparatus or receives information from the user. The user interface may include for example one or more of a keyboard a keypad a mouse a joystick a button a switch an electronic pen or stylus a gesture recognition sensor e.g. to recognize gestures of a user including movements of a body part an input sound device or voice recognition sensor e.g. a microphone to receive a voice command an output sound device e.g. a speaker a track ball a pedal or footswitch a virtual reality device and the like. The user interface may further include a haptic device to provide haptic feedback to a user. The user interface may also include a touchscreen display for example. The touchscreen display may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display and the like for example. However the disclosure is not so limited thereto and may include other types of touchscreen displays. The disclosure may also include other types of user interfaces.

The user may select a content to be scanned by the image forming apparatus or may set print options of the content through the UI unit . Also the user may input a phone number that is an external destination through the UI unit .

The controller is a hardware component for controlling overall operations and functions of the image forming apparatus . In detail the controller may execute a printing application for providing a phone number based cloud printing service. Also the controller may control a print function a copy function or a scan function of the image forming unit image forming apparatus .

The network interface unit is a hardware component for supporting a wired or wireless communication function and may support a wireless communication such as Wi Fi Wi Fi Direct an NFC Zigbee infrared data association IrDA or Bluetooth a wired communication such as Ethernet or a 2G mobile communication a 3G mobile communication or a 4G mobile communication.

The image forming unit is a hardware component for performing print and copy functions of a content or a scan function of a document.

In operation the controller of the mobile device obtains the phone number of the mobile device through the executed printing application.

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the image forming apparatus to receive identification ID information of the image forming apparatus .

The ID information of the image forming apparatus may include information about a network address of the image forming apparatus for example a media access control MAC address or an internet protocol IP address and information about a serial number and product specification of the image forming apparatus .

The network interface unit of the mobile device and the network interface unit of the image forming apparatus may be connected to each other through a wireless network such as Wi Fi Wi Fi Direct an NFC or Zigbee infrared data association IrDA Bluetooth .

For example operation may be performed by NFC tagging the mobile device to the image forming apparatus by activating an NFC function.

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the cloud server and transmits information about the phone number of the mobile device and the ID information of the image forming apparatus to the cloud server as registration information of the mobile device .

In operation the controller of the cloud server maps the phone number of the mobile device and the ID information of the image forming apparatus to each other and stores such mapping information in the storage unit as the registration information of the mobile device .

In operation the UI unit of the mobile device notifies that the registering of the phone number of the mobile device with respect to the image forming apparatus is completed.

In operation the controller of the mobile device obtains the phone number of the mobile device through the executed printing application.

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the image forming apparatus to transmit information about the obtained phone number to the image forming apparatus .

For example operation may be performed by NFC tagging the mobile device to the image forming apparatus by activating an NFC function.

In operation the network interface unit of the image forming apparatus is wirelessly connected to the network interface unit of the cloud server to transmit the information about the obtained phone number and the ID information of the image forming apparatus to the cloud server as the registration information of the mobile device .

The image forming apparatus may be connected to the cloud server by using an extensible messaging and presence protocol XMPP or alternatively any other protocol.

In operation the controller of the cloud server maps the phone number of the mobile device and the ID information of the image forming apparatus to each other and stores such mapping information in the storage unit as the registration information of the mobile device .

In operation the UI unit of the mobile device notifies that registering of the phone number of the mobile device with respect to the image forming apparatus is completed.

In operation the controller of the mobile device obtains the phone number of the mobile device through the executed printing application.

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the image forming apparatus to receive ID information of the image forming apparatus .

For example operation may be performed by NFC tagging the mobile device to the image forming apparatus by activating an NFC function.

In operation the network interface unit of the image forming apparatus connects to the cloud server . Operation may be performed by a connection command of the mobile device . The image forming apparatus may be connected to the cloud server by using an XMPP or alternatively any other protocol.

In operation the controller of the cloud server obtains the ID information of the image forming apparatus .

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the cloud server to transmit the information about the phone number of the mobile device and the ID information of the image forming apparatus to the cloud server as the registration information of the mobile device .

In operation the controller of the cloud server maps the phone number of the mobile device and the ID information of the image forming apparatus and stores such mapping information in the storage unit as the registration information of the mobile device .

In operation the UI unit of the mobile device notifies that the registering of the phone number of the mobile device with respect to the image forming apparatus is completed.

When the second individual wants to register the phone number of the mobile device and the image forming apparatus in the cloud server the second individual executes the printing application in the mobile device .

When the second individual clicks a registration icon to register a new printer while the printing application is being executed a first screen is displayed.

The first screen may display an entry for requesting registration of the image forming apparatus an entry for setting a direct printing mode and a list of image forming apparatuses registered to the phone number of the mobile device .

When the second individual clicks a dialog in the entry for requesting registration a second screen is displayed.

The second screen is a screen for guiding the registration of the image forming apparatus . When the second screen is displayed the second individual may complete the registration of the image forming apparatus by establishing a communication between the mobile device and the image forming apparatus . The communication between the mobile device and the image forming apparatus may be established by NFC tagging the mobile device to the image forming apparatus . Alternatively the communication between the mobile device and the image forming apparatus may be established by connecting them via any wireless communication method such as Wi Fi or Wi Fi direct.

In other words the mobile device may register the information about the phone number of the mobile device in the cloud server through the first and second screens and of the pre installed printing application. The first and second screens and may be differently configured and an embodiment is not limited by the screen configurations of the printing application.

The mobile device may activate or deactivate a direct printing function through an icon in the entry for setting the direct printing mode of the printing application.

If the direct printing function is activated the second individual may select the image forming apparatus for example CLP 680 from the list of image forming apparatuses and click a set button to assign the image forming apparatus to perform the direct printing mode.

Information about the registration and direct printing mode performed by the printing application of the mobile device may be transmitted to and stored in the cloud server .

Referring to the second individual i.e. Jane Kim inputs the phone number of the mobile device through the UI unit of the image forming apparatus in operation .

In operation the network interface unit of the image forming apparatus is wirelessly connected to the network interface unit of the cloud server to transmit information about the input phone number to the cloud server .

In operation the network interface unit of the cloud server transmits an arbitrary personal ID number PIN code to the mobile device of the second individual having the input phone number by using a short message service SMS or a multimedia message service MMS . The cloud server may transmit another type of an arbitrary code instead of the PIN code.

In operation the UI unit of the mobile device displays the PIN code received by using the SMS or MMS.

In operation the second individual inputs the PIN code received from the mobile device through the UI unit of the image forming apparatus .

In operation the network interface unit of the image forming apparatus transmits information about the input PIN code and the ID information of the image forming apparatus to the cloud server .

In operation the controller of the cloud server compares the PIN code transmitted from the image forming apparatus and the PIN code transmitted from the mobile device to determine whether the two PIN codes are the same.

If the two PIN codes are the same the controller of the cloud server maps and registers the phone number of the mobile device and the image forming apparatus in operation .

If the two PIN codes are not the same the controller of the cloud server denies the registration of the phone number of the mobile device .

In operation the UI unit of the mobile device or the UI unit of the image forming apparatus notifies that the registering of the phone number of the mobile device with respect to the image forming apparatus is completed.

Referring to the registering may be completed with only intermediation of the cloud server while the mobile device and the image forming apparatus do not communicate with each other unlike . Accordingly the processes of may be used when any one of the mobile device and the image forming apparatus does not support an NFC Wi Fi Wi Fi Direct Zigbee infrared data association IrDA or Bluetooth for a wireless communication between the mobile device and the image forming apparatus . However the processes of may be used even when the mobile device and the image forming apparatus both support a wireless communication function described above with reference to .

Referring to the second individual i.e. Jane Kim connects to an embedded webpage provided by the image forming apparatus by using the computing device in operation . The computing device corresponds to a PC or a laptop and may be the user device of . Accordingly the computing device includes the UI unit the controller and the network interface unit .

In operation the second individual inputs the phone number of the mobile device through the embedded webpage .

In operation the network interface unit of the computing device is wirelessly connected to the network interface unit of the cloud server to transmit information about the input phone number to the cloud server .

In operation the network interface unit of the cloud server transmits an arbitrary PIN code to the mobile device of the second individual having the input phone number by using an SMS or MMS. The cloud server may transmit another type of an arbitrary code instead of the PIN code.

In operation the UI unit of the mobile device displays the PIN code received by using the SMS or MMS.

In operation the second individual inputs the PIN code received from the mobile device through the embedded webpage .

In operation the network interface unit of the computing device transmits information about the input PIN code and the ID information of the image forming apparatus to the cloud server .

The computing device may obtain the ID information of the image forming apparatus by connecting to the embedded webpage of the image forming apparatus .

In operation the controller of the cloud server compares the PIN code transmitted from the computing device and the PIN code transmitted to the mobile device to determine whether the two PIN codes are the same.

If the two PIN codes are the same the controller of the cloud server maps and registers the phone number of the mobile device and the image forming apparatus in operation .

If the two PIN codes are not the same the controller of the cloud server denies the registration of the phone number of the mobile device .

In operation the UI unit of the mobile device or the UI unit of the computing device notifies that the registering of the phone number of the mobile device with respect to the image forming apparatus is completed.

In operation the controller of the mobile device obtains the phone number of the mobile device through the executed printing application.

In operation the second individual i.e. Jane Kim inputs an email address through the executed printing application.

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the cloud server to transmit information about the obtained phone number and input email address to the cloud server .

In operation the controller of the cloud server maps the phone number and the email address and stores such mapping information in the storage unit as registration information of the mobile device .

In operation the UI unit of the mobile device notifies that registering of the phone number of the mobile device with respect to the email address is completed.

Referring to the phone number and the mobile device and the image forming apparatus are not mapped but the phone number of the mobile device and the email address of the second individual are mapped unlike .

When the phone number of the mobile device and the email address of the second individual are mapped via the processes of a content may be transmitted and printed according to processes described below with reference to .

Referring to the second individual i.e. Jane Kim connects to an embedded webpage provided by the image forming apparatus by using the computing device in operation . The computing device corresponds to a PC or a laptop and may be the user device of . Thus the computing device includes the UI unit the controller and the network interface unit .

In operation the second individual inputs the email address and the phone number of the mobile device through the embedded webpage .

In operation the network interface unit of the computing device is wirelessly connected to the network interface unit of the cloud server to transmit information about the input phone number and email address to the cloud server .

In operation the network interface unit of the cloud server transmits an arbitrary personal identification number PIN code to the mobile device of the second individual having the input phone number by using an SMS or MMS. The cloud server may transmit another type of an arbitrary code instead of the PIN code.

In operation the UI unit of the mobile device displays the PIN code received by using the SMS or MMS.

In operation the second individual inputs the PIN code received from the mobile device through the embedded webpage .

In operation the network interface unit of the computing device transmits information about the input PIN code to the cloud server .

In operation the controller of the cloud server compares the PIN code transmitted from the computing device and the PIN code transmitted to the mobile device to determine whether the two PIN codes are the same.

If the two PIN codes are the same the controller of the cloud server maps and registers the phone number of the mobile device and the email address in operation .

If the two PIN codes are not the same the controller of the cloud server denies the registration of the phone number of the mobile device .

In operation the UI unit of the mobile device or the UI unit of the computing device notifies that the registering of the phone number of the mobile device with respect to the email address is completed.

Various methods of registering the image forming apparatus to print a received content the methods performed by the mobile device of the second individual i.e. Jane Kim corresponding to a receiver terminal of the image forming system have been described with reference to . In addition various methods for registering an email address to receive a content have been described as additional methods. The processes of may be used to assign the image forming apparatus to print a content when the content is transmitted from the mobile device of the first individual i.e. John Lee. Accordingly the processes of may be performed before the content is transmitted from the mobile device of the first individual or alternatively may be performed after the content is transmitted.

Various methods of transmitting delivering a content to be printed from the image forming system to the cloud server the methods performed by the first individual i.e. John Lee who is a sender will now be described with reference to . In other words descriptions of may correspond to partial processes before a content transmitted from a sender first individual John Lee reaches a recipient the second individual i.e. Jane Kim .

Referring to the first individual i.e. John Lee inputs information about a content to be printed and information about the phone number of the mobile device of the second individual i.e. Jane Kim which is a destination for receiving the content to be printed through the UI unit of the mobile device in operation .

The information about the content to be printed includes selection information about on a content to be transmitted to the second individual and to be printed from among contents being used by the mobile device . Also the information about the content to be printed may include information about print options of the content which are pre set by the first individual in the mobile device for example general settings such as a paper size and a color white and black option.

In operation the network interface unit of the mobile device transmits the information about the content and the information about the phone number to the cloud server . In other words the mobile device transmits print job information including the information about the content and the information about the phone number to the cloud server .

In operation the controller of the cloud server maps and stores the information about the content and the information about the phone number in the storage unit .

First referring to a contact list of names and phone numbers may be displayed on a contacts screen of the mobile device .

When the first individual i.e. John Lee wants to transmit a content to be printed to the second individual i.e. Jane Kim the first individual selects the second individual from the contact list. At this time if contact information of the second individual is not in the contact list the first individual may directly input and select the phone number of the second individual .

When the second individual is selected a content type screen for selecting a type of the content to be printed is displayed as a pop up screen.

As such when information about the phone number of the second individual and about the content to be printed is input through the contacts screen and the content type screen the mobile device transmits the information about the phone number and about the content to the cloud server as described above.

Then referring to a list of images stored in the mobile device may be displayed on a camera image screen of the mobile device .

When at least one image for example a flower image corresponds the content to be printed from the list of images the first individual selects the flower image .

When the flower image is to be transmitted to the second individual the first individual selects the second individual from the contacts screen .

As such when the information about the phone number of the second individual and about the content to be printed the flower image is input through the camera image screen and the contacts screen the mobile device transmits the information about the phone number and the content to the cloud server as described above.

Referring to icons and indicating whether the image forming apparatus is registered to each of the phone numbers of the second and third individuals and i.e. Jane Kim and Brad Jones may be displayed on the contacts screens and .

Information indicated by the icons and is based on mapping information transmitted from the cloud server . In other words before the displaying of the contacts screens and is activated in the mobile device the mobile device pre receives the mapping information of each of the phone numbers of the second and third individuals and from the cloud server . Accordingly when the contacts screens and are displayed in the mobile device the existence of the image forming apparatus pre registered to the second and third individuals and may also be displayed by using the icons and .

According to the contacts screen is displayed first and then the content type screen is displayed. In other words according to the phone number is selected first and then the content is selected. However according to the camera image screen is displayed first and then the contacts screen is displayed. In other words according to the content is selected first and then the phone number is selected.

A difference between is an order of selecting the phone number and the content. Thus according to an embodiment it does not matter which one of the phone number and the content is selected first as shown in .

Configurations of the UI screens of are arbitrarily illustrated for convenience of description and thus an embodiment is not limited to the configurations of the UI screens.

Referring to the image forming unit image forming apparatus of the image forming apparatus generates scan data by scanning a document in operation . The image forming apparatus may be the image forming apparatus of . Thus the image forming apparatus includes the UI unit the controller the network interface unit and the image forming unit .

In operation the first individual i.e. John Lee inputs information about the phone number of the mobile device of the second individual i.e. Jane Kim which is a destination for receiving the scan data to be printed through the UI unit of the image forming apparatus .

A printing application having the similar functions as that of the mobile device of the first individual described above may be pre installed in the image forming apparatus . Alternatively even when a printing application is not pre installed in the image forming apparatus the first individual may newly install a printing application on the OS of the image forming apparatus .

Accordingly the first individual may input the information about the phone number of the mobile device of the second individual which is the destination for receiving the scan data to be printed on the printing application displayed through the UI unit of the image forming apparatus .

In other words operation may be performed as the information about the phone number of the mobile device of the second individual is input through the UI unit of the image forming apparatus by the first individual while the printing application is being executed by the controller of the image forming apparatus .

In operation the network interface unit of the image forming apparatus transmits the information about the phone number and the scan data to the cloud server .

In operation the controller of the cloud server maps the information about the phone number and the scan data and stores such mapping information in the storage unit .

Referring to the first individual may transmit deliver the content scan data to be printed to the second individual without having to use the mobile device unlike .

Referring to the first and second UI screens and may be screens provided by the printing application executed in the image forming apparatus .

The first individual i.e. John Lee may identify a list of image forming functions executable in the printing application through the first UI screen of the printing application displayed on the UI unit of the image forming apparatus .

As described above with reference to when the first individual wants to transmit the scan data of the document to a phone number of the mobile device of the second individual the first individual performs a Scan to Phone function by clicking a Scan to Phone icon .

The second UI screen is a UI screen when the Scan to Phone function is performed. A preview of the scan data may be displayed on the second UI screen and an address book stored in the image forming apparatus may be displayed on the second UI screen .

The first individual may click the phone number of the mobile device that is a destination for receiving the scan data from a list displayed in the address book to determine the destination the phone number through the Scan to Phone function.

However when the phone number of the mobile device is not in the address book of the second UI screen the first individual may newly input the phone number of the mobile device through the UI unit of the image forming apparatus .

Configurations of the first and second UI screens and of are illustrated for convenience of description and an embodiment is not limited by the configurations of the first and second UI screens and of . Also a name of the Scan to Phone function may be changed as long as the Scan to Phone function is a function for providing a phone number based cloud printing service.

Referring to in operation the first individual i.e. John Lee selects a content to be printed through the UI unit of the computing device . The computing device corresponds to a PC or a laptop and may be the user device of . Thus the computing device includes the UI unit the controller and the network interface unit .

In operation the controller of the computing device executes a printer driver for providing a phone number based cloud printing service. The printer driver executed by the computing device may be a virtual driver but is not limited thereto.

The printer driver does not select a printer as a destination for printing a content like a general printer driver. The printer driver displays s list of phone numbers as destinations so as to provide a phone number based cloud printing service.

For example when a content to be printed is selected and the printer driver is executed the printer driver displays ME 82 10 XXXX 9900 the first individual JANE KIM 82 10 XXXX 8800 the second individual and BRAD JONES 82 10 XXXX 7700 the third individual in the list of phone numbers.

Only the list of phone numbers is displayed in the printer driver of but alternatively the printer driver may also include functions for setting general print options on the content to be printed.

In operation the first individual selects the phone number 82 10 XXXX 8800 of the mobile device of the second individual to which the content is to be transmitted through the UI unit of the computing device . If the phone number of the mobile device is not in the list of phone numbers in the printer driver the first individual may directly input the phone number of the mobile device .

In operation the network interface unit of the computing device transmits information about the input phone number and about the selected content to the cloud server .

In operation the controller of the cloud server maps the information about the input phone number and the information about the selected content and stores such mapping information in the storage unit .

Referring to the first individual may transmit deliver the content scan data to be printed to the second individual without having to use the first device unlike .

The processes of may be performed by the user device or the image forming apparatus . The user device may correspond to the mobile device or of or the computing device described above and the image forming apparatus may correspond to the image forming apparatus or of .

In operation the first individual i.e. John Lee selects a content to be printed through the UI unit of the user device or the UI unit of the image forming apparatus and inputs an email address of the second individual i.e. Jane Kim. An order of selecting the content and inputting the email address may be switched.

In operation the controller of the user device or the controller of the image forming apparatus generates an email enclosed with the content.

In operation the network interface unit of the user device or the network interface unit of the image forming apparatus transmits the generated email to the cloud server under the email address of the second individual .

The cloud server may pre store mapping information of the email address of the second individual and the phone number of the mobile device of the second individual via the processes described above with reference to .

In operation the controller of the cloud server maps information about a phone number pre mapped to an email address and information about the content enclosed in the email again and stores such mapping information in the storage unit .

Various methods of transmitting delivering a content to be printed to the cloud server the methods performed by the first individual i.e. John Lee who is a sender in the image forming system have been described above with reference to .

Various methods of receiving a content to be printed from the cloud and printing the content the methods performed by the second individual i.e. Jane Kim who is a recipient in the image forming system will now be described with reference to . In other words descriptions of may correspond to partial processes before a content transmitted from a sender first individual i.e. John Lee reaches a recipient the second individual i.e. Jane Kim . In other words processes of may be performed after the processes of .

Referring to the network interface unit of the mobile device receives upload information of a content to be printed from the cloud server in operation . The content to be printed corresponds to a content uploaded by the first individual i.e. John Lee based on the phone number of the mobile device of the second individual i.e. Jane Kim.

The cloud server may transmit the upload information by using an SMS or MMS or via a wireless network such as Internet.

In operation the UI unit of the mobile device notifies an arrival of the content to the phone number of the mobile device of the second individual .

When the upload information of the content for example Image001.JPG is transmitted through a message the UI unit of the mobile device may display an arrival message but is not limited thereto. In other words the UI unit of the mobile device may notify the arrival to the second individual via any one of various methods.

In operation when the second individual requests to check the content Image001.JPG the cloud server returns information about the content Image001.JPG to the mobile device of the second individual .

In operation the controller of the mobile device executes a printing application and the UI unit of the mobile device displays a list of contents transmitted to the second individual on the printing application. The list of contents includes the content Image001.JPG transmitted from the first individual .

When the second individual selects the content Image001.JPG in operation the UI unit of the mobile device displays a preview of the content Image001.JPG on the printing application. The second individual may additionally set print options of the content Image001.JPG through the printing application.

In operation the second individual inputs a print command for printing the content Image001.JPG in the image forming apparatus that is pre mapped through the UI unit of the mobile device .

In operation the network interface unit of the mobile device transmits the input print command to the cloud server .

In operation the network interface unit of the cloud server transmits print data of the content Image001.JPG to the image forming apparatus .

Operations through may be performed when the second individual requests to print the content Image001.JPG in operation . However the second individual may deny to print the content Image001.JPG in operation .

When the second individual requests to delete the content Image001.JPG from the list of contents the network interface unit of the mobile device may transmit a delete request of the content Image001.JPG to the cloud server in operation .

In operation the controller of the cloud server deletes information about the content Image001.JPG stored in the storage unit .

On the other hand the second individual may input a forwarding request for transmitting the content Image001.JPG to the third or fourth individual or .

When the second individual input the forwarding request the network interface unit of the mobile device transmits the forwarding request to the cloud server in operation . The second individual may command the forwarding request by inputting the phone number of the mobile device or of the third or fourth individual or through the UI unit of the mobile device .

In operation the cloud server forwards the content Image001.JPG to the third or fourth individual or requested by the second individual .

Referring to the second individual i.e. Jane Kim inputs the phone number of the mobile device through the UI unit of the image forming apparatus in operation .

In operation the network interface unit of the image forming apparatus is wirelessly connected to the network interface unit of the cloud server to transmit information about the input phone number to the cloud server .

In operation the network interface unit of the cloud server transmits an arbitrary PIN code to the mobile device of the second individual having the input phone number by using an SMS or MMS. The cloud server may transmit another type of an arbitrary code instead of the PIN code.

In operation the UI unit of the mobile device displays the PIN code received by using the SMS or MMS.

In operation the second individual inputs the PIN code received from the mobile device through the UI unit of the image forming apparatus .

In operation the network interface unit of the image forming apparatus transmits information about the input PIN code to the cloud server .

In operation the controller of the cloud server compares the PIN code transmitted from the image forming apparatus and the PIN code transmitted to the mobile device to determine whether the two PIN codes are the same.

In operation if the two PIN codes are the same the cloud server returns information about a content mapped to the phone number of the mobile device of the second individual to the image forming apparatus .

If the two PIN codes are not the same the controller of the cloud server denies return of the information about the content.

In operation the UI unit of the image forming apparatus displays a list of contents currently transmitted to the second individual .

In operation when the second individual selects a content to be printed from the list of contents the network interface unit of the cloud server transmits print data of the selected content to the image forming apparatus .

The second individual printing the content through the image forming apparatus has been described with reference to but operations similar to at least one of operations through of may be additionally performed between operations and performed by the image forming apparatus and the cloud server . For example the UI unit of the image forming apparatus may display the preview of the content to be printed or the second individual may receive the print options. Also the second individual may deny printing the content or perform pull printing. In other words the processes of may be combined with each other.

Referring to the cloud server transmits upload information of a content to be printed to the mobile device of the second individual i.e. Jane Kim in operation .

In operation the UI unit of the mobile device notifies an arrival of the content to be printed to the phone number of the mobile device of the second individual .

In operation the network interface unit of the mobile device is wirelessly connected to the network interface unit of the image forming apparatus to transmit information about the phone number of the mobile device to the image forming apparatus .

The network interface unit of the mobile device may be connected to the network interface unit of the image forming apparatus through a wireless network such as Wi Fi Wi Fi Direct an NFC Zigbee infrared data association IrDA or Bluetooth .

For example operation may be performed by NFC tagging the mobile device to the image forming apparatus by activating an NFC function.

In operation the network interface unit of the image forming apparatus is wirelessly connected to the network interface unit of the cloud server to transmit the information about the phone number obtained from the mobile device to the cloud server .

In operation the network interface unit of the cloud server returns information about a content mapped to the phone number to the image forming apparatus .

In operation the UI unit of the image forming apparatus displays a list of contents currently transmitted to the second individual .

In operation when the second individual selects a content to be printed from the list of contents the network interface unit of the cloud server transmits print data of the selected content to the image forming apparatus .

Operations similar to at least one of operations through of may be additionally performed between operations through of . For example the UI unit of the image forming apparatus may display the preview of the content to be printed or the second individual may receive the print options. Also the second individual may deny printing the content or perform pull printing. In other words the processes of may be combined with each other.

Referring to the second individual i.e. Jane Kim connects to an embedded webpage provided by the image forming apparatus by using the computing device in operation . The computing device corresponds to a PC or a laptop and may be the user device of . Thus the computing device includes the UI unit the controller and the network interface unit .

In operation the UI unit of the computing device displays a list of contents currently transmitted to the second individual through the embedded webpage .

In operation when the second individual selects a content to be printed from the list of contents the network interface unit of the cloud server transmits print data of the selected content to the image forming apparatus .

Operations similar to at least one of operations through of may be additionally performed between operations through of . For example the UI unit of the computing device may display the preview of the content to be printed or the second individual may receive the print options. Also the second individual may deny printing the content or perform pull printing. In other words the processes of may be combined with each other.

The controller of the mobile device of the second individual i.e. Jane Kim executes a printing application.

The second individual clicks a received content list icon on a first screen of the printing application to display a second screen .

A list of contents transmitted from the first individual i.e. John Lee and other individuals is displayed on the second screen .

The second individual may selects a content Image001.JPG transmitted from the first individual from the list and click a print icon to print the content Image001.JPG .

Configurations of the UI screens of are arbitrarily illustrated for convenience of description and an embodiment is not limited by the configurations of the UI screens.

When a content to be printed is transmitted from the first individual i.e. John Lee who is a sender the cloud server of generates print data of the content by rendering or converting the content to a print data format by using the controller . Then the cloud server transmits the print data of the content to the second individual who is a recipient in detail the image forming apparatus assigned by the second individual .

Various methods of printing a content transmitted from the first individual i.e. John Lee who is a sender by using the image forming apparatus the methods performed by the second individual i.e. Jane Lee who is a recipient have been described with reference to .

Referring to the second individual i.e. Jane Kim who is a recipient receives information about a content to be printed from the first individual i.e. John Lee who is a sender by using the processes described above.

First in the direct printing a content to be printed is directly printed by the image forming apparatus that is a representative printer set as a default when the content reaches the second individual . In other words print data of the content is directly transmitted from the cloud server to the image forming apparatus to be automatically printed even when the second individual does not manipulate the mobile device .

As described above with reference to the second individual may turn on or off a direct printing function through the icon for setting a direct printing mode of the print application.

When the direct printing function is turned on the second individual may assign the image forming apparatus as a representative printer or a default printer by selecting the image forming apparatus for example CLP 680 from a list of image forming apparatuses and then clicking the set button .

Accordingly when the direct printing function is turned on the content that reached the second individual may be directly printed by the image forming apparatus without being checked by the second individual .

In the pull printing when a content to be printed reaches the second individual the content is not directly printed but exists in a held or standby state. In other words the pull printing is performed when the direct printing function is turned off.

According to the pull printing when the content to be printed reaches the second individual the second individual may input a print request delete the content newly assign one of the image forming apparatuses through to print the content or forward the content to the third or fourth individual or . In other words the content is printed deleted or forwarded only when the second individual inputs at least one process request to the mobile device .

In other words the image forming apparatus according to an embodiment supports both of the direct printing and the pull printing.

Referring to the first individual i.e. John Lee transmits a content to be printed to the phone number of the mobile device of the second individual i.e. Jane Kim.

As described above the cloud server may transmit information about the content in a message such as an SMS or MMS based on the phone number of the mobile device of the second individual .

When the mobile device of the second individual receives the message a message application installed in the mobile device displays a notification about the arrival of the content.

Then when the message application is executed in the mobile device a content information message received from the cloud server is displayed. The content information message includes information about the content Image001.JPG transmitted from the first individual .

Referring to the cloud server pre maps and manages a phone number of a mobile device of the administrator and the ID information of the image forming apparatus according to the processes described above with reference to . The administrator and the mobile device exist in the image forming system of .

When an error such as paper jam no paper or low toner occurs in the image forming apparatus the cloud server collects error information about errors occurred in the image forming apparatus .

The cloud server transmits the error information of the image forming apparatus to the mobile device of the administrator mapped to the image forming apparatus . The cloud server transmits the error information by transmitting a message in an SMS or MMS by using the phone number of the mobile device of the administrator .

Referring to the storage unit of the cloud server may manage the phone numbers in the white list and the black list .

The white list and the black list may be stored in the cloud server according to a request of the mobile device or that is a receiver.

The white list is a management list for receiving contents only from allowed phone numbers. Thus according to the white list a content transmitted from an unallowed impermissible phone number is not transmitted to the mobile device or .

The black list is a management list for rejecting contents only from unallowed phone numbers. Thus according to the black list a content transmitted from a phone number not in the black list may be transmitted to the mobile device or .

As described above the second individual i.e. Jane Kim who is a recipient may pre store the white list or the black list in the cloud server by using the mobile device the computing device or the image forming apparatus or .

Referring to the first individual i.e. John Lee selects a content to be faxed from the mobile device and inputs the facsimile number for example 82 31 580 XXXX of the image forming apparatus .

The cloud server receives information about the content and about the facsimile number from the mobile device of the first individual . The cloud server may have a function of a facsimile server.

The cloud server faxes the information about the content to the image forming apparatus having the received facsimile number. Then the image forming apparatus prints the faxed content.

In other words is different from above described drawings only in that a receiver terminal is changed to the image forming apparatus and a content is faxed and thus operations and functions described above when a receiver terminal is the mobile device or may be similarly applied to .

Referring to the environment of the phone number based cloud printing service is generally illustrated based on the cloud server . In order to support the phone number based cloud printing service the cloud server may match and store phone numbers and various information. For example the cloud server may store information in which a phone number and information are matched such as a phone number and information about a corresponding image forming apparatus or a phone number and a print job and ID information of the print job. In sender devices and recipient devices are placed respectively on left and right of the cloud server .

Looking at the left of the cloud server in a sender who wants to transmit a print job registers the print job in the cloud server by using various types of the sender devices . For example the sender may generate the print job by selecting a content displayed on a screen after executing an application of a mobile device to assign a file scanning a document to generate scan data or assigning a content to be printed by using a print program in a user computer such as a laptop or a desktop. The generated print job may be transmitted to the cloud server supporting the phone number based cloud printing service as the sender inputs a phone number of a recipient by using an UI of each of the sender devices .

Looking at the right of the cloud server in the recipient who wants to perform the print job receives the print job from the cloud server by using various types of the recipient devices . The recipient devices may receive the print job from the cloud server in a direct print method or a pull print method. One of the direct print method and the pull print method may be determined by a user.

In the direct print method a print job is performed as the print job is directly transmitted from the cloud server to an image forming apparatus corresponding to a phone number of a recipient even when the recipient does not separately request the print job to be performed since the cloud server is pre set to transmit the print job to the image forming apparatus corresponding to the phone number of the recipient. In the pull print method a print job is performed as the print job is transmitted from the cloud server to the recipient device only when the print job transmitted from the sender device to the cloud server is registered in the cloud server information about the registered print job is transmitted to a mobile device corresponding to a phone number of a recipient so as to notify the recipient that the print job is registered in the cloud server and then the recipient requests the print job to be performed.

In detail in the pull print method the recipient may request the print job to be performed by selecting the print job to be performed from a list of print jobs displayed on a screen after executing an application of the mobile device. Information about an image forming apparatus that is to perform the print job may be additionally selected. When the recipient requests the print job to be performed the cloud server may transmit the requested print job to an image forming apparatus that is pre set correspondingly to the phone number or selected by the recipient so that the print job is performed. Hereinafter one or more embodiments are described based on the pull print method but are not limited thereto.

Since a general cloud printing service using a management server such as a company server is based on a user account the general cloud printing service is different from the phone number based cloud printing service described above with reference to in terms of a base. In other words since an apparatus supporting the general cloud printing service based on a user account performs a print job via a user login using the user account the apparatus does not use a phone number of a user while transmitting or managing the print job. Also when information about the user is to be registered the apparatus does not necessarily store the phone number of the user and generally does not provide a field for storing the phone number. Accordingly in order to provide the phone number based cloud printing service described above while continuously using the apparatus supporting the general cloud printing service based on a user account such as a user device usable via a user login using a user account and a management server such as a general company server the general cloud printing service based on a user account and the phone number based cloud printing service need to be linked to each other. This will now be described with reference to accompanying drawings.

In following embodiments it is assumed that the user device and the management server are apparatuses supporting the user account based cloud printing service and since the user account based cloud printing service is supported the user device and the management server do not include information about a phone number of a user and thus do not provide the phone number based cloud printing service.

The user device may be any one of various types such as an image forming apparatus a user computer such as a desktop or a laptop and a mobile device and is not limited as long as the user is able to use the user device via user authentication using the user account. Hereinafter for convenience of description it is assumed that the user device is an image forming apparatus according to an embodiment.

When the user logs in the user device by using the user account the management server may perform user authentication by using a user account database and manage a usage set authorization of the user and manage a history of the user.

The cloud server may intermediate an apparatus for supporting the user account based cloud printing service and an apparatus for supporting the phone number based cloud printing service. In other words the cloud server may communicate with the user device and the management server which are the apparatuses for supporting the user account based cloud printing service and communicate with the mobile device that is the apparatus for supporting the phone number based cloud printing service.

The mobile device is the apparatus for supporting the phone number based cloud printing service which is capable of communicating with the cloud server and may support the phone number based cloud printing service unlike the user device . The user device may be a mobile type but whereas the user device is capable of transmitting a user account based print job to the management server or the cloud server the mobile device is capable of transmitting a phone number based print job to the cloud server .

By linking the management server supporting the user account based cloud printing service and the cloud server supporting the phone number based cloud printing service the cloud printing service providing system in which the user account based cloud printing service and the phone number based printing cloud service are linked may be formed. The cloud server may perform a server client communication for maintaining security with the management server .

The cloud server may be a public cloud server or a private cloud server. Accordingly a location where a print job is registered may differ in the cloud printing service providing system including the management server and the cloud server . This is because a security level differs according to a type of the cloud server as will be described in detail below with reference to .

Referring to the cloud server of commonly includes a server unit server and a user information database DB and the cloud server of further includes a print job DB . The cloud server of may further include other general purpose components.

There may be two types of the cloud server i.e. a public cloud server and a private cloud server. When the cloud server is public the cloud server is satisfactory in terms of costs but has weak security and when the cloud server is private the cloud server is unsatisfactory in terms of costs but has strong security and may provide a data storage space. Accordingly when the cloud server is public the print job may be registered in the management server of the cloud printing service providing system including the management server and the cloud server in order to maintain security. On the other hand when the cloud server is private the print job may be registered in the cloud server of the cloud printing service providing system . In detail a private cloud server is used mostly when there is no space in the management server to store the print job and thus the print job may be registered in the cloud server when the cloud server is private.

The cloud server of is private and may include the print job DB for registering a print job. In this case the cloud server may manage registration of a print job without registering the print job in the management server . For example the cloud server of including the print job DB may be used when the management server does not include the print job DB for registering a print job or when it is difficult to newly build the print job DB in the management server .

Accordingly hereinafter it is assumed that the cloud server of is used when public and the cloud server of is used when private. Structures and operations of the cloud printing service providing system will now be described when the cloud server is public and private respectively by using .

Referring to the cloud printing service providing system may include the management server and the cloud server . The management server supporting the user account based cloud printing service may communicate with the user device and the cloud server supporting the phone number based cloud printing service may communicate with not only the user device but also the mobile device .

The management server may include a client unit client a user account data base DB a print job allowing unit printer job allower and a print job DB . As described above with reference to the print job DB is included in the management server . The cloud server may include the server unit server and the user information DB .

The management server may receive the print job from the user device . For example when the user device is an image forming apparatus the management server may receive scan data generated by scanning a document in the image forming apparatus. The user device is usable via a user authentication using a user account and may transmit a user account based print job while transmitting a user account of a recipient.

The user account DB may store the user account as well as various types of information related to the user account. For example the user account DB may store each user account and usage information or authorization information of a user corresponding to each user account.

The print job allowing unit may determine allowing of the user account based print job included in the user account based print job received by the management server . For example the print job allowing unit may determine the allowing of the print job by checking whether the user account received with the print job in the management server exists in the user account DB . Also the print job allowing unit print job allower may determine the allowing of the print job by further considering usage or authorization of the user corresponding to the user account.

The print job DB may register the print job allowed by the print job allowing unit . For example the print job received in the management server may be matched to the user account of the recipient and stored.

The client unit client of the management server is a communication module of the management server capable of performing a server client communication with the cloud server . In other words the client unit is a communication module of the management server for performing a communication maintaining security between the management server supporting the user account based cloud printing service and the cloud server supporting the phone number based cloud printing service.

The client unit client of the management server may transmit information to be transmitted to the mobile device through the cloud server or information required to control the cloud server to the cloud server or receive information to be transmitted to the user device or information required to control the management server from the cloud server . For example the client unit may transmit a result of determining the allowing of the print job by the print job allowing unit or a result of registering the allowed print job in the print job DB to the cloud server or receive the print job from the cloud server or information for requesting to perform the print job transmitted to the cloud server from the mobile device .

The cloud server may receive the print job from the mobile device . The mobile device may transmit the phone number based print job wherein the phone number of the recipient is also transmitted while transmitting the print job to the cloud server . Also the cloud server may receive the information for requesting to perform the print job from the mobile device wherein the information is based on a phone number which is transmitted with the phone number.

The user information DB may store user information in which the phone number of the user and the user account are matched to each other. In other words the phone number and the user account may be matched and stored in the user information DB so that the user account and the phone number are mutually switched. For example the phone number may be used to be switched to the user account corresponding to the phone number or the user account may be used to be switched to the phone number corresponding to the user account. The user information DB may store user information in which device information such as an image forming apparatus is further matched to the phone number and the user account.

The server unit server of the cloud server is a communication module of the cloud server which is capable of performing a server client communication with the management server . In other words the server unit is a communication module of the cloud server for performing a communication maintaining security between the management server supporting the user account based cloud printing service and the cloud server supporting the phone number based cloud printing service.

The server unit of the cloud server may receive information to be transmitted to the mobile device through the cloud server or information required to control the cloud server from the management server or transmit information to be transmitted to the user device or information required to control the management server to the management server . For example the server unit may receive a result of determining the allowing of the print job by the print job allowing unit or a result of registering the allowed print job in the print job DB from the management server or transmit the print job from the cloud server or information for requesting to perform the print job transmitted to the cloud server from the mobile device .

Information received from or transmitted to the management server are information based on a user account and usable by the management server because the management server is an apparatus supporting the user account based cloud printing service. While the server unit of the cloud server performs the server client communication with the client unit of the management server the user account and the phone number may be mutually switched by using the user information DB so that the management server and the cloud server are linked thereby intermediating the apparatus supporting the phone number based cloud printing service and the apparatus supporting the user account based cloud printing service.

Referring to the cloud printing service providing system may include the management server and the cloud server . The management server supporting the user account based printing service may communicate with the user device and the cloud server supporting the phone number based cloud printing service may communicate not only with the user device but also with the mobile device .

The management server may include the client unit the user account DB and the print job allowing unit . Unlike the management server does not include the print job DB . The cloud server may include the server unit the user information DB and the print job DB . As described above with reference to the print job DB is included in the cloud server . Details overlapping those of are not repeated herein and only differences generated as the print job DB is included in the cloud server will now be described.

The print job DB of the cloud server may register the print job allowed by the print job allowing unit of the management server . For example the print job received in the cloud server may be matched to the user account or the phone number of the recipient and then stored. The cloud server may receive the user account based print job from the user device or receive the phone number based print job from the mobile device . By matching and storing the phone number and the user account in the user information DB the user account and the phone number may be mutually switched and thus the print job received in the cloud server may also be matched to the user account or the phone number and then stored.

Unlike since the print job DB is included in the cloud server the result of registering the allowed print job may not be received from the management server and since the print job received in the cloud server is registered the print job may not be transmitted to the management server .

Embodiments of the printing service provided by the cloud printing service providing system in which the user account based cloud printing service and the phone number based cloud printing service are linked will now be described with reference to .

The user may log in the user device by using a user account in operation S. The user device is an apparatus usable via a user authentication using the user account. For example since the user may use an image forming apparatus in a company by logging in using the user s user account the image forming apparatus is an example of the user device .

The user device transmits a login request to the management server by using the user account received from the user and the management server may allow the login via user authentication for checking the user account in operation S. When the login is allowed the user may start processes for receiving a cloud printing service by using the user device .

The user device may execute an application supporting the cloud printing service according to an input of the user in operation S. In other words the user may execute the application supporting the cloud printing service in the user device . The application supporting the cloud printing service may operate as an interface connecting the cloud printing service providing system and the user device . If the application executed by the user device guarantees a connection only to the management server supporting the user account based cloud printing service instead of the entire cloud printing service providing system the management server may set a trigger so that a print job is retransmitted to the cloud server .

In order to transmit the print job to another user the user as a sender may select a recipient from an address book of the user device in operation S. The address book may store a plurality user accounts of users to display the user accounts so that the user who is a sender may select the user account of the recipient.

The user may generate a print job by using the user device and may request the print job to be performed in operation S. For example the user may scan a document by using the image forming apparatus that is an example of the user device to generate a scan data and request the print job to be performed by transmitting the generated scan data to the other user.

The user device may transmit the print job requested from the user to the management server in operation S. In other words the management server may receive the print job. The print job received by the management server from the user device may be a user account based print job that includes a user account and a print job.

The management server may determine allowing of the print job based on the user account in operation S. The management server may determine the allowing of the print job based on the user account included in the user account based print job transmitted from the user device . For example the management server may check whether the user account of the recipient included in the user account based print job is capable of receiving a cloud printing service thereby determining the allowing of the print job.

The management server may register the allowed print job in operation S according to the result of allowing. Since the cloud server included in the cloud printing service providing system is a public cloud server the print job is registered in the management server as described above with reference to . The management server may match the print job to ID information of the print job and then store the print job. Thus when a plurality of print jobs exist in the same user account the management server may manage the print jobs by using ID information of the print jobs. If the print job is not allowed the print job transmitted to the management server may be deleted.

The management server may transmit the result of registering the print job to the cloud server in operation S. In other words the cloud server may receive the result of registering from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of registering may include the user account of the recipient and the ID information of the print job for identifying the print job.

By transmitting the result of registering to the cloud server the cloud server may convert the user account of the recipient included in the result of registering to a phone number corresponding to the user account in operation S. In order to be connected to the mobile device supporting the phone number based cloud printing service the user account included in the result of registering is converted to the corresponding phone number thereby performing a process of linking the user account based cloud printing service and the phone number based cloud printing service. Accordingly the cloud server may include the user information DB for storing the user information in which phone numbers of users and user accounts are matched to each other as described above.

The cloud server may notify the mobile device about the registering of the print job in operation S. The cloud server may transmit the ID information of the print job to the phone number converted from the user account so as to notify the registering of the print job.

As described above the user account based print job requested to be performed through the user device by using the user account is transmitted to the phone number corresponding to the user account of the recipient through the cloud printing service providing system including the management server and the cloud server . Accordingly the user account based cloud printing service is linked to the phone number based cloud printing service and at this time the cloud server may convert the user account to the corresponding phone number.

Then the recipient may check the registered print job through the mobile device of the recipient and may select the print job to be performed according to a pull print method.

Since is different from only in the type of the cloud server overlapping descriptions are briefly described and descriptions of may be applied to even if omitted.

The user device transmits a login request to the management server by using the user account received from the user and the management server may allow the login via user authentication for checking the user account in operation S.

The user device may execute an application supporting the cloud printing service according to an input of the user in operation S.

In order to transmit the print job to another user the user as a sender may select a recipient from an address book of the user device in operation S.

The user may generate a print job by using the user device and may request the print job to be performed in operation S.

The user device may transmit a request to allow the print job requested by the user to the management server in operation S. The request transmitted from the user device to the management server may include a user account. In other words by transmitting the user account of the recipient to the management server the management server may determine whether the print job is allowable.

The user device may transmit the print job requested by the user to the cloud server in operation S. The print job transmitted from the user device to the cloud server is a user account based print job that includes a user account and a print job. Operation S may be simultaneously performed with operation S or may be performed after operation S.

The management server may determine allowing of the print job based on the user account in operation S. The management server may determine the allowing of the print job based on the user account received from the user device according to the request received in operation S. For example the management server may check whether the user account of the recipient is capable of receiving the cloud printing service to determine the allowing of the print job.

The management server may transmit the result of allowing to the cloud server in operation S. In other words the cloud server may receive the result of allowing from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of allowing may include the user account of the recipient and a value indicating the result of allowing.

The cloud server may register the allowed print job in operation S according to the result of allowing. In other words the cloud server may register the allowed print job by checking the result of allowing transmitted from the management server . Since the cloud server included in the cloud printing service providing system is a private cloud server the print job may be registered in the cloud server as described above with reference to . The cloud server may match the print job to ID information of the print job and then store the print job. If a plurality of print jobs exist in the same user account the management server may manage the print job by using the ID information of the print job. If the print job is not allowed the print job transmitted to the cloud server may be deleted.

The cloud server may convert the user account of the recipient regarding the registered print job to a phone number corresponding to the user account in operation S. In order to be connected to the mobile device supporting the phone number based cloud printing service the user account of the recipient regarding the registered print job is converted to the corresponding phone number thereby performing a process of linking the user account based cloud printing service and the phone number based cloud printing service. Accordingly the cloud server may include the user information DB for storing the user information in which phone numbers of users and user accounts are matched to each other as described above.

The cloud server may notify the mobile device about the registering of the print job in operation S. The cloud server may transmit the ID information of the print job to the phone number converted from the user account so as to notify the registering of the print job.

As described above the user account based print job requested to be performed through the user device by using the user account is transmitted to the phone number corresponding to the user account of the recipient through the cloud printing service providing system including the management server and the cloud server . Accordingly the user account based cloud printing service is linked to the phone number based cloud printing service and at this time the cloud server may convert the user account to the corresponding phone number.

Then the recipient may check the registered print job through the mobile device of the recipient and may select the print job to be performed according to a pull print method.

The mobile device may execute an application supporting a cloud printing service according to an input of the user in operation S. In other words the user may execute the application supporting the cloud printing service in the mobile device . The application may operate as an interface connecting the mobile device and the cloud printing service providing system in which the user account based cloud printing service and the phone number based cloud printing service are linked.

The user may select a content to be transmitted for a print job from the mobile device in operation S. The mobile device may obtain a file corresponding to the selected content so that the user may externally transmit the selected content.

The user as a sender may select a recipient from contacts of the mobile device in operation S in order to transmit the print job to another user. The contacts may be phone numbers of users and may display a plurality of phone numbers for the user to select a phone number of the recipient.

The user may request the print job to be performed by using the mobile device in operation S. In other words the mobile device may request the print job to be performed such that the selected recipient prints the file of the selected content.

The mobile device may transmit the print job requested by the user to the cloud server in operation S. In other words the cloud server may receive the print job. The print job received from the mobile device to the cloud server may be a phone number based print job including a phone number and a print job.

The cloud server may convert the phone number of the recipient included in the phone number based print job transmitted from the mobile device to a user account corresponding to the phone number in operation S. In order to be connected to the management server supporting the user account based cloud printing service the cloud server converts the phone number included in the received print job to the user account corresponding to the phone number thereby linking the phone number based cloud printing service to the user account based cloud printing service. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched to each other as described above.

The cloud server may transmit a user account based print job including the user account converted from the phone number to the management server in operation S. In other words the management server may receive the user account based print job from the cloud server . The cloud server and the management server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The print job transmitted from the cloud server to the management server may be the user account based print job including the user account and the print job.

The management server may determine allowing of the print job based on the user account in operation S. The management server may determine the allowing of the print job based on the user account included in the user account based print job. For example the management server may determine the allowing of the print job by checking the user account of the recipient obtained by converting the phone number of the recipient is a user account capable of receiving the cloud printing service.

The management server may register the allowed print job according to a result of the allowing in operation S. Since the cloud server included in the cloud printing service providing system is a public cloud server the print job is registered in the management server as described above with reference to . The management server may match a print job to ID information of the print job and register the print job. When a plurality of print jobs exist in the same user account the management server may manage the print job by using the ID information. If the print job is not allowed the user account based print job transmitted to the management server may be deleted.

The management server may transmit a result of registering the print job to the cloud server in operation S. In other words the cloud server may receive the result of registering from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of registering may include the user account of the recipient and the ID information for identifying the print job.

By transmitting the result of registering from the management server to the cloud server the cloud server may again convert the user account of the recipient included in the result of registering to the phone number corresponding to the user account in operation S. By converting the user account included in the result of registering back to the phone number in order to be connected to the mobile device supporting the phone number based cloud printing service the user account based cloud printing service and the phone number based cloud printing service may be linked. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched as described above.

The cloud server may notify the mobile device about the registering of the print job in operation S. The cloud server may notify the registering of the print job by transmitting the ID information of the print job to the phone number converted back from the user account obtained in operation S.

As described above the phone number based print job requested to be performed through the mobile device using the phone number by the sender is transmitted to the phone number of the recipient through the cloud printing service providing system including the management server and the cloud server via processes of converting the phone number to the user account and converting the user account back to the phone number. At this time the phone number based cloud printing service is linked to the user account based cloud printing service and accordingly the cloud server may perform the processes of converting the phone number to the user account and converting the user account back to the phone number.

Then the recipient may check the registered print job through the mobile device and select the print job according to a pull print method to be performed.

Since is different from only in the type of the cloud server overlapping descriptions are briefly described and descriptions of may be applied to even if omitted.

The mobile device may execute an application supporting a cloud printing service according to an input of the user in operation S.

The user may select a content to be transmitted for a print job from the mobile device in operation S.

The user as a sender may select a recipient from contacts of the mobile device in operation S in order to transmit the print job to another user.

The mobile device may transmit the print job requested by the user to the cloud server in operation S. The print job received from the mobile device to the cloud server may be a phone number based print job including a phone number and a print job.

The cloud server may convert the phone number of the recipient included in the phone number based print job transmitted from the mobile device to a user account corresponding to the phone number in operation S.

The cloud server may transmit a request to allow the print job requested by the user to the management server in operation S. In other words the management server may receive the request to allow the print job from the cloud server . The cloud server and the management server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The request transmitted from the cloud server to the management server may include the converted user account. In other words the user account of the recipient is transmitted to the management server so that the management server determines whether the print job is allowed.

The management server may determine allowing of the print job based on the user account in operation S. The management server may determine the allowing of the print job based on the converted user account. For example the management server may determine the allowing of the print job by checking whether the user account of the recipient converted from the phone number of the recipient is capable of receiving the cloud printing service.

The management server may transmit a result of allowing to the cloud server in operation S. In other words the cloud server may receive the result of allowing from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of allowing may include the user account of the recipient and a value indicating the result of allowing.

The cloud server may register the allowed print job in operation S according to the result of allowing. Since the cloud server included in the cloud printing service providing system is a private cloud server the print job may be registered in the cloud server as described above with reference to . The cloud server may match a print job to ID information of the print job and store the print job. When a plurality of print jobs exist in the same user account the cloud server may manage the print job by using ID information of the print jobs. If the print job is not allowed the print job transmitted to the cloud server may be deleted.

The cloud server may convert the user account of the recipient regarding the registered print job back to the phone number corresponding to the user account in operation S. By converting the user account of the recipient regarding the print job registered in the cloud server back to the phone number in order to be connected to the mobile device supporting the phone number based cloud printing service the user account based cloud printing service and the phone number based cloud printing service may be linked. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched as described above.

The cloud server may notify the mobile device about the registering of the print job in operation S. The cloud server may notify the registering of the print job by transmitting the ID information of the print job to the phone number converted back from the user account obtained in operation S.

As described above the phone number based print job requested to be performed through the mobile device using the phone number by the sender is transmitted to the phone number of the recipient through the cloud printing service providing system including the management server and the cloud server via processes of converting the phone number to the user account and converting the user account back to the phone number. At this time the phone number based cloud printing service is linked to the user account based cloud printing service and accordingly the cloud server may perform the processes of converting the phone number to the user account and converting the user account back to the phone number.

Then the recipient may check the registered print job through the mobile device and select the print job according to a pull print method to be performed.

The mobile device may execute an application supporting the cloud printing service according to an input of the user in operation S. In other words the user may execute the application supporting the cloud printing service in the mobile device . The application supporting the cloud printing service may operate as an interface connecting the mobile device and the cloud printing service providing system in which the user account based cloud printing service and the phone number based cloud printing service are linked.

In operation S the user may select a print job in the mobile device . The mobile device may display a list of print jobs related to the registered print job for the user and the user may select a print job.

In operation S the user may further select an image forming apparatus to be used for the print job in the mobile device .

The user may request the print job to be performed by using the mobile device in operation S. In other words the print job may be requested to be performed so that the image forming apparatus selected in the mobile device performs the selected print job.

The mobile device may transmit request information about the request to perform the print job from the user to the cloud server in operation S. In other words the cloud server may receive the request information. The request information received from the mobile device to the cloud server may include a phone number and ID information of the print job for identifying the print job selected by the user. If the image forming apparatus is selected by the user the request information may further include ID information of the image forming apparatus for identifying the selected image forming apparatus.

The cloud server may convert the phone number of the recipient included in the request information received from the mobile device to a user account corresponding to the phone number in operation S. The cloud server converts the phone number to the user account corresponding to the phone number in order to be connected to the management server supporting the user account based cloud printing service thereby linking the phone number based cloud printing service and the user account based cloud printing service. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched as described above.

The cloud server may transmit the request information including the user account converted from the phone number to the management server in operation S. In other words the management server may receive the request information including the converted user account from the cloud server . The cloud server and the management server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key.

The management server may determine allowing of the print job based on the user account included in the request information in operation S. For example the management server may determine the allowing of the print job by checking whether the user account of the recipient converted from the phone number of the recipient is capable of receiving the cloud printing service.

The management server may instruct the print job to be performed in operation S according to a result of allowing. Since the cloud server included in the cloud printing service providing system is a public cloud server the print job may be registered in the management server . If the print job is allowed the print job corresponding to the ID information of the print job may be transmitted to the image forming apparatus connected to the management server and then instructed to be performed. The image forming apparatus is usable via user authentication using the user account and may be an example of the user device connected to the management server .

The image forming apparatus that is an example of the user device may perform the print job in operation S upon receiving the instruction from the management server .

The management server may transmit a result of performing the print job to the cloud server in operation S. In other words the cloud server may receive the result of performing from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of performing may include the user account of the recipient and a value indicating the result of performing.

By transmitting the result of performing from the management server to the cloud server the cloud server may convert the user account of the recipient included in the result of performing back to the phone number corresponding to the user account in operation S. In order to be connected to the mobile device supporting the phone number based cloud printing service the user account included in the result of performing is converted back to the phone number so that the user account based cloud printing service and the phone number based cloud printing service are linked to each other. Accordingly the cloud server includes the user information DB storing user information in which phone numbers of users and user accounts are matched as described above.

The cloud server may notify the result of performing the print job to the mobile device in operation S. The cloud server may transmit the value indicating the result of performing to the phone number converted back from the user account in operation S to notify the user about the result of performing through the mobile device .

Since is different from only in the type of the cloud server overlapping descriptions are briefly described and descriptions of may be applied to even if omitted.

The mobile device may execute an application supporting the cloud printing service according to an input of the user in operation S.

In operation S the user may further select an image forming apparatus to be used for the print job in the mobile device .

The mobile device may transmit request information about the request to perform the print job from the user to the cloud server in operation S.

The cloud server may convert the phone number of the recipient included in the request information received from the mobile device to a user account corresponding to the phone number in operation S.

The cloud server may transmit a request to allow the print job from the user to the management server in operation S. The request to allow the print job received from the cloud server to the management server may include a user account. In other words by transmitting the user account converted from the phone number to the management server the management server may determine whether the print job is allowed. The cloud server and the management server may perform a server client communication and data transferred therebetween may be encoded by using a key.

The cloud server may transmit the print job requested by the user to the image forming apparatus that is an example of the user device in operation S. Since the cloud server included in the cloud printing service providing system is a private cloud server the print job may be registered in the cloud server . Operation may be performed simultaneously with operation S or after operation S.

The management server may determine allowing of the print job based on the user account included in the request information in operation S. For example the management server may check whether the user account of the recipient converted from the phone number of the recipient is capable of receiving the cloud printing service to determine the allowing of the print job.

The management server may instruct the print job to be performed in operation S according to a result of allowing.

The image forming apparatus that is an example of the user device may perform the print job in operation S upon receiving the instruction from the management server .

The management server may transmit a result of performing the print job to the cloud server in operation S. In other words the cloud server may receive the result of performing from the management server . The management server and the cloud server may perform a server client communication and data transferred therebetween may be in a format encoded by using a key. The result of performing may include the user account of the recipient and a value indicating the result of performing.

By transmitting the result of performing from the management server to the cloud server the cloud server may convert the user account of the recipient included in the result of performing back to the phone number corresponding to the user account in operation S. In order to be connected to the mobile device supporting the phone number based cloud printing service the user account included in the result of performing is converted back to the phone number so that the user account based cloud printing service and the phone number based cloud printing service are linked to each other. Accordingly the cloud server includes the user information DB storing user information in which phone numbers of users and user accounts are matched as described above.

The cloud server may notify the result of performing the print job to the mobile device in operation S. The cloud server may transmit the value indicating the result of performing to the phone number converted back from the user account in operation S to notify the user about the result of performing through the mobile device .

The mobile device may execute an application supporting the cloud printing service according to an input of the user in operation S. In other words the user may execute the application supporting the cloud printing service in the mobile device . In order to be provided with the cloud printing service of the cloud printing service providing system the user device first needs to be logged in and thus the user may try to log in the user device by using the mobile device where the application is being executed.

The mobile device may transmit the phone number to the user device via an NFC tagging with the user device in operation S. A data communication between the mobile device and the user device may not only be performed via the NFC tagging but also via any one of various wireless communications such as a near infrared ray communication Zigbee Bluetooth infrared data association IrDA and Wi Fi Direct . By transmitting user information such as a phone number to the user device the user device may obtain information for user authentication. Since the management server allows a login and user authentication based on a user account the user authentication is not obtained from the management server by using a phone number. Accordingly the phone number is converted to the user account so that the user device is logged in.

The user device may transmit the phone number received from the mobile device again to the cloud server to request the login of the user device in operation S. Here ID information of the user device to be logged in may also be transmitted.

The cloud server may transmit the phone number transmitted from the user device to the user account corresponding to the phone number in operation S. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched.

The cloud server may transmit the user account converted from the phone number to the management server instead of the user device so as to request the login of the user device in operation S. The ID information of the user device to be logged in may also be transmitted.

The management server may perform user account authentication on the user account received from the cloud server in operation S. Accordingly the management server may include the user account DB for storing and managing user accounts capable of receiving a cloud printing service. The management server checks whether the user account received from the cloud server exists in the user account DB to perform the user account authentication.

When the user account received from the cloud server exists in the user account DB the management server may allow the login of the user device corresponding to the user account in operation S. Then there are a plurality of the user devices corresponding to the user account the user device that requested the login may be determined based on the ID information of the user device transmitted with the user account.

By performing the login of the user device as such the cloud printing service may be provided by using the user device .

First in operation S the cloud printing service providing system may receive the print job. For example the management server included in the cloud printing service providing system may receive a user account based print job from the user device . Alternatively the cloud server included in the cloud printing service providing system may receive a user account based print job from the user device or a phone number based print job from the mobile device . When the phone number based print job is received an operation of converting a phone number to a user account corresponding to the phone number may be further performed for following operations.

In operation S the cloud printing service providing system may determine allowing of the print job based on the user account. Since the allowing of the print job is determined by the management server supporting the user account based cloud printing service the allowing of the print job may be determined by using the user account included in the received print job or the user account converted from the phone number.

In operation S the cloud printing service providing system may register the allowed print job according to a result of the determining. A location of registering the allowed print job may differ based on a type of the cloud server included in the cloud printing service providing system . For example when the cloud server is a public cloud server the allowed print job may be stored in the management server . On the other hand when the cloud server is a private cloud server the allowed print job may be stored in the cloud server . In detail when the cloud server is a private cloud server the management server may transmit the result of determining to the cloud server so that the allowed print job is registered in the cloud server .

In operation S the cloud printing service providing system may convert the user account to the phone number corresponding to the user account so as to notify the registering of the print job in the mobile device supporting the phone number based cloud printing service. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched. However when the cloud server is a public cloud server the result of registering is transmitted from the management server to the cloud server so that the cloud server converts the user account to the corresponding phone number.

In operation S the cloud printing service providing system may notify the registering of the allowed print job to the phone number converted from the user account.

The user account based cloud printing service is linked to the phone number based cloud printing service through operations S through S and at this time the cloud server may convert the user account to the phone number corresponding to the user account.

First in operation S the cloud printing service providing system may receive request information for performing a phone number based print job. In detail the cloud server supporting a phone number based cloud printing service and included in the cloud printing service providing system may receive the request information including a phone number and ID information of a print job for identifying a print job selected by the user from the mobile device . If the user selected an image forming apparatus through the mobile device the request information may further include ID information of the image forming apparatus.

In operation S the cloud printing service providing system may convert the phone number to a user account corresponding to the phone number. In detail the cloud server supporting the phone number based cloud printing service and included in the cloud printing service providing system may convert the phone number included in the request information received from the mobile device to the user account corresponding to the phone number. Accordingly the cloud server may include the user information DB storing user information in which phone numbers of users and user accounts are matched. As such the phone number based cloud printing service and the user account based cloud printing service may be linked.

In operation S the cloud printing service providing system may determine allowing of the print job corresponding to the request information based on the converted user account. In detail the management server supporting the user account based cloud printing service and included in the cloud printing service providing system may determine the allowing of the print job by receiving the request information from the cloud server or receiving a request to allow the print job using the converted user account. For example when the cloud server included in the cloud printing service providing system is a public cloud server since the print job is registered in the management server the request information including the converted user account and the ID information of the print job is transmitted to the management server and thus the management server may determine the allowing of the print job. Alternatively when the cloud server included in the cloud printing service providing system is a private cloud server since the print job is registered in the cloud server the print job is allowed by using the converted user account and thus the management server may determine the allowing of the print job.

In operation S the cloud printing service providing system may instruct the allowed print job to be performed according to a result of allowing the print job. In detail the management server supporting the user account based cloud printing service and included in the cloud printing service providing system may instruct the image forming apparatus to perform the allowed print job. When the cloud server included in the cloud printing service providing system is a public cloud server since the print job is registered in the management server the management server may transmit the allowed print job to the image forming apparatus to instruct the image forming apparatus to perform the allowed print job. On the other hand when the cloud server included in the cloud printing service providing system is a private cloud server since the print job is registered in the cloud server the cloud server may transmit the allowed print job to the image forming apparatus and the management server may instruct the image forming apparatus to perform the allowed print job.

Then in order to transmit a result of performing the print job to the mobile device the management server may transmit the result of performing to the mobile device through the cloud server . The cloud server converts the user account back to the phone number to transmit the result of performing to the mobile device corresponding to the phone number.

The phone number based cloud printing service is linked to the user account based cloud printing service through operations S through S and at this time the cloud server may convert the phone number to the user account corresponding to the phone number.

According to an embodiment a recipient may set print job conditions in a cloud server and the cloud server may transmit a print job to at least one of electronic devices connected according to the set print job conditions such that the print job is performed.

Generally when it is not suitable for a recipient to receive a print job or for an image forming apparatus to perform a print job in a cloud printing service provided by a cloud server and a sender transmits a content to be printed the recipient is unable to check the print job or the image forming apparatus is unable to perform the print job.

Accordingly one or more embodiments provide a method enabling a recipient to set print job conditions and a cloud server to transmit a print job to at least one of electronic devices connected according to the set print job conditions such that the print job is performed. An embodiment will now be described in detail with reference to .

The cloud printing system may include a mobile terminal a cloud server an image forming apparatus and a mobile terminal . Any one of various electronic devices such as a laptop a tablet a personal computer PC portable media player PMP digital camera laptop computer notebook computer portable game player wearable device and a personal digital assistant PDA may replace a mobile terminal to perform the same functions as the mobile terminal.

In the cloud printing system a user uploads data in the mobile terminal to the cloud server . Then the user may request the cloud server to print the data any time at any place. For example the user may request the cloud server for the data by using the mobile terminal or the image forming apparatus and the data may be printed by the image forming apparatus .

A storage space may be provided in the cloud server according to users and each storage space may be mapped to correspond to a phone number of a mobile device of each user.

Then the user transmits a print job destined for a phone number of the mobile terminal to the cloud server by using the mobile terminal . The cloud server stores a print job in the storage space mapped to correspond to the phone number of the mobile terminal .

The user checks the print job in the storage space by using the mobile terminal . The cloud server transmits the print job to the mobile terminal according to a request of the user. The mobile terminal receives the print job and the user checks details of the print job through a preview by using the mobile terminal . The user may enable the image forming apparatus to perform the print job by transmitting the print job to the image forming apparatus connected to the mobile terminal . The cloud server may map a phone number to each image forming apparatus included in the cloud printing system and use the mapped phone number as a destination address for data transmission. The cloud server may include a storage space according to image forming apparatuses and each storage space may be mapped to correspond to each of phone numbers of the image forming apparatuses. For example a phone number 031 xxx yyyy may be mapped to correspond to the image forming apparatus and the mapped phone number 031 xxx yyyy may be used as a destination address. Accordingly when the user requests the cloud server for the print job destined for the mapped phone number by using the mobile terminal the cloud server stores the print job in the storage space for the image forming apparatus . Then the cloud server may transmit the stored print job to the image forming apparatus . The image forming apparatus receives the print job and performs the received print job.

The user may check the storage space for the image forming apparatus in the cloud server by using the image forming apparatus . The cloud server transmits the print job stored in the storage space according to a request of the user. The image forming apparatus may receive and perform the print job.

Also the cloud server may map the image forming apparatus to correspond to a phone number of the mobile terminal of the user and may use the mapped phone number as a destination address for data transmission. As described above since the cloud server may include the storage space according to users the storage space may be mapped to correspond to the phone number of the mobile terminal .

When the user transmits the print job destined for the phone number of the mobile terminal to the cloud server by using the mobile terminal the cloud server stores the print job in the storage space of the user. The cloud server transmits the print job stored in the storage space to the image forming apparatus . The image forming apparatus receives and performs the print job.

In the environment of the cloud printing system based on a phone number it is difficult to perform the print job if the user is unable to check the print job. In other words it is difficult to perform the print job when the user of the mobile terminal is absent and thus unable to check the print job.

Also when the print job is transmitted to the image forming apparatus mapped to a certain phone number but the image forming apparatus is not suitable for performing the print job the print job may be difficult to be performed. In other words when the image forming apparatus is malfunctioning or only supports black and white whereas the print job is in color the print job may be difficult to be performed.

Referring to the cloud printing system includes the mobile terminal the cloud server and the image forming apparatus .

The mobile terminal included in the cloud printing system transmits the print job to the cloud server . The cloud server receives the print job and selects the image forming apparatus from among image forming apparatuses connected according to print job conditions. The cloud server transmits the print job to the image forming apparatus . The image forming apparatus receives and performs the print job.

The transmitter transmits data. In detail the transmitter transmits data including the print job and the receiver receives the data.

The controller may control the transmitter to transmit the print job destined for at least one phone number.

The mobile terminal may further include an interface unit not shown for receiving an input from the user.

The controller controls the transmitter to receive information indicating print job conditions from the interface unit and to transmit the information indicating the print job conditions to the cloud server .

The receiver receives the data. In detail the receiver may receive the print job. Also the receiver may receive the information indicating the print job conditions. Also the receiver may include an ARS connector and receive the information indicating the print job conditions from an ARS server.

The controller may control the receiver to receive the print job destined for at least one phone number. In detail the controller may control the receiver to receive the print job destined for a group of a plurality of phone numbers. Also the controller may control the transmitter to transmit the print job to a selected image forming apparatus. The controller may control the receiver to receive the information indicating the print job conditions from the mobile terminal . The controller may control the receiver to receive the information indicating the print job conditions from the ARS server. Also the controller may control the condition setter to set the print job conditions based on the received information indicating the print job conditions.

The condition setter sets the print job conditions and the selector selects at least one of image forming apparatuses corresponding to the plurality of phone numbers included in the group. Also the selector checks the print job conditions set by the condition setter to determine whether the print job conditions are suitable for receiving the print job by the image forming apparatus corresponding to the phone number. If it is determined that the print job conditions are not suitable the selector may select another image forming apparatus different from the image forming apparatus corresponding to the phone number. The other image forming apparatus may be pre assigned by the condition setter . The selector may determine whether the print job conditions are suitable by controlling the transmitter to transmit a request for checking print job conditions set in the image forming apparatus corresponding to the phone number and controlling the receiver to receive a response to the request. The selector determines whether the print operation conditions are suitable for the image forming apparatuses corresponding to the plurality of phone numbers to perform the print job by checking capability information of the image forming apparatuses and selects at least one of the image forming apparatuses based on a result of the determining. Capability information may include at least one of a current state of an image forming apparatus and information about whether the image forming apparatus supports color or black and white printing.

The selector controls the receiver to receive the capability information of the image forming apparatuses corresponding to the plurality of phone numbers. Also the selector determines whether the print job conditions of the image forming apparatuses corresponding to the plurality of phone numbers are suitable for performing the print job by checking the set print job conditions based on the capability information received by the receiver . If it is determined that the print job conditions of the image forming apparatuses corresponding to the plurality of phone numbers are not suitable the selector may select another image forming apparatus different from the image forming apparatuses corresponding to the plurality of phone numbers. The other image forming apparatus may be pre assigned by the condition setter .

The image forming apparatus includes a receiver a transmitter a controller and a print operation performer .

The receiver receives the data. In detail the receiver receives the print job. Also the receiver may receive a request on the capability information of the image forming apparatus . The receiver may receive a request for checking the set print job conditions.

The transmitter transmits the data. The transmitter may transmit the capability information of the image forming apparatus . Also the transmitter may transmit a response to the request for checking the set print job conditions.

The controller controls the receiver and the transmitter . The controller may control the print job performer . The controller controls the receiver to receive the print job from a server. The controller may control the receiver to receive the request on the capability information of the image forming apparatus or the request for checking the set print job conditions. The controller may control the transmitter to transmit the capability information of the image forming apparatus to the cloud server . The controller may control the transmitter to transmit a response to the request for checking the print job conditions.

The cloud printing system is not limited to directly receiving and performing the print job in the image forming apparatus but the print job may be first transmitted to an electronic device such as the mobile terminal and the image forming apparatus may receive and perform the print job from the electronic device.

According to an embodiment a user pre sets print job conditions in a server and a suitable printer performs a print job according to the set print job conditions.

In operation S a user B sets automatic forwarding conditions. The automatic forwarding conditions are basic conditions for selecting an electronic device to transmit a print job from among electronic devices connected to a cloud server. For example the automatic forwarding conditions may include conditions that are not suitable for a mobile terminal to receive a print job or for a printer to perform a print job. A user B may assign an electronic device to receive a print job when automatic forwarding conditions are satisfied while setting the automatic forwarding conditions.

A user B may set automatic forwarding conditions through a mobile application executed in a mobile terminal through a UI of an image forming apparatus or through an ARS.

In an embodiment the user B set the automatic forwarding conditions such that a print job received by the cloud server during 9 00 of 10th to 18 00 of 11th is transmitted to a kiosk C. At the same time the user B set the automatic forwarding conditions such that a print job received by the cloud server while the user B is out of office is transmitted to the kiosk C. The user B sets a print job received by the cloud server to be limited to that destined for a phone number 010 AAAA BBBB of the user B.

In operation S the cloud server may transmit an approval request to the kiosk C such that a print job is transmitted to the kiosk C according to the set automatic forwarding conditions.

In operation S the kiosk C transmits an approval response to the approval request to the cloud server . Upon receiving the approval response the automatic forwarding conditions on the print job destined for the phone number of the user B is set in the cloud server .

However the cloud server may complete the setting of the automatic forwarding conditions without having to perform operations S and S.

Referring to a user A transmits a print job to the cloud server the cloud server transmits the print job to a suitable printer and the suitable printer performs the print job in operations S through S.

In operation S the user A transmits the print job destined for the phone number 010 AAAA BBBB of the user B.

In operation S the cloud server checks the automatic forwarding conditions set in operations S through S. In an embodiment the print job is transmitted by the user A at 10 00 of 10th. Thus the cloud server determines that the automatic forwarding conditions are satisfied. The cloud server may transmit a message to the user A for checking whether to transmit the print job to the kiosk C.

In operation S the user A transmits a message to the cloud server approving the print job to be transmitted to the kiosk C by using a mobile terminal.

In operation S the cloud server transmits the print job to the kiosk C. The kiosk C may receive and perform the print job.

In operation S after the kiosk C performs the print job the cloud server transmits a notification that the print job is completed in the kiosk C.

Alternatively the cloud server may directly transmit the print job to the kiosk C without separately transmitting an approval request to the user A.

Referring to a user executes a mobile application in a mobile terminal and selects the user s phone number and a phone number to which a print job is automatically distributed according to conditions. Also the user sets print job conditions. The print job conditions may be variously set according to times from one day to another day or according to states absence of the user using the mobile terminal. Also the print job conditions may be variously set based on whether an image forming apparatus is capable of performing a print job for example based on whether the image forming apparatus malfunctions or whether the image forming apparatus supports color printing.

After the setting is completed the print job conditions are transmitted to and stored in a cloud server. The user may set a phone number assigned to an image forming apparatus a phone number to which a print job is to be distributed and print job conditions through a UI of the image forming apparatus and may similarly transmit the print job conditions to the cloud server to be stored.

Referring to when print job conditions are to be set via an ARS the user dials a main ARS number by using a general phone. The user is guided by a voice in an ARS server and sets the print job conditions by pressing buttons on the general phone. The setting is performed similarly to a mobile application. After the setting is completed the print job conditions are transmitted to and stored in the cloud server from the ARS server through an ARS connector of the cloud server.

The sender A pre sets the print job conditions before transmitting the print job. In other words the sender A sets a group of phone numbers to transmit the print job. A group of phone numbers of image forming apparatuses in offices B C and D is set through a mobile application or an ARS. Then the sender A sets the print job conditions in detail direct performance of a print job and a print job in a color document in the cloud server .

In operation S the sender A transmits a print job destined for the group of phone numbers of the image forming apparatuses of the offices B C and D to the cloud server .

The cloud server examines states of the image forming apparatuses in the group to check an image forming apparatus matching the print job conditions set by the sender A. In an embodiment it is assumed that the image forming apparatus of the office B is unprintable the image forming apparatus of the office C does not support a color print option and the image forming apparatus of the office D matches the print job conditions.

The cloud server may check whether the print job conditions are suitable by receiving capability information from each image forming apparatus. In detail the cloud server may transmit a message to each image forming apparatus for checking a state of each image forming apparatus in operations S S and S and may receive capability information in operations S S and S in response so as to check the state of each image forming apparatus.

Then in operation S the cloud server selects the image forming apparatus of the office D to transmit the print job. The image forming apparatus of the office D receives and performs the print job.

In an embodiment a user B pre sets print job conditions by executing a mobile application in the user B s mobile terminal. In detail the user B set a phone number to which a print job destined for the user B s phone number is to be forwarded to a phone number 010 CCCC DDDD of a user C. Also the user B sets the print job to be forwarded when the user B is not home.

In operation S the user A transmits a print job destined for a phone number 010 AAAA BBBB of the user B to a cloud server by using an electronic device.

In operation S the cloud server transmits a message notifying the print job to the mobile terminal of the user B.

In operation S the mobile terminal of the user B transmits a message to the cloud server about absence at home in response to the message notifying the print operation.

In operation S the cloud server receives the message from the mobile terminal of the user B to check that the user B is not at home and transmits an approval request on the print job to the mobile terminal of the user C.

In operation S the user C transmits a message approving the print job to the cloud server by using the user C s mobile terminal.

In operation S the cloud server transmits the print job to an image forming apparatus mapped to the phone number of the user C s mobile terminal. The image forming apparatus receives and performs the print job.

In operation S the cloud server may transmit a message to the user A that the print job destined for the phone number of the user C s mobile terminal has been performed.

In an embodiment a user A sets print job conditions through a UI of an image forming apparatus and stores the print job conditions in a cloud server by transmitting the print job conditions to the cloud server. It is assumed that the user A set the print job conditions such that a print job is destined for a phone number of an office C if an image forming apparatus of an office B is broken.

In operation S the user A transmits the print job destined for a phone number 031 AAA BBBB of the image forming apparatus of the office B to the cloud server by using the user A s mobile terminal.

In operation S the cloud server transmits a request to check the print job conditions to the image forming apparatus of the office B.

In operation S the image forming apparatus of the office B transmits a message about a malfunction to the cloud server in response to the request to check the print job conditions.

In operation S the cloud server receives the message from the image forming apparatus of the office B. The cloud server checks that the image forming apparatus of the office B is malfunctioning through the received message. Accordingly the cloud server transmits the print job to a phone number 031 CCC DDDD of the image forming apparatus in the office C. In other words the cloud server transmits the print job to the image forming apparatus of the office C. The image forming apparatus of the office C may receive and perform the print operation.

In operation S the cloud server transmits a notification that the print job is performed in the image forming apparatus of the office C because of the malfunction of the image forming apparatus in office B.

In operation S the cloud server selects at least one electronic device from among connected electronic devices according conditions set by a user. The cloud server checks capability information of an electronic device corresponding to a phone number to determine whether the electronic device is suitable for performing a print job and if it is determined that the electronic device is not suitable may select another electronic device different from the electronic device corresponding to the phone number. The other electronic device may be pre set by the user.

In operation S the cloud server transmits the print job request to the selected at least one electronic device.

In operation S a cloud server receives a print job request destined for a plurality of phone numbers assigned to a group.

In operation S the cloud server selects at least one of electronic devices corresponding to the plurality of phone numbers included in the group.

In operation S the cloud server transmits the print job request to the selected at least one electronic device.

In operation S a cloud server receives a print job request destined for a plurality of phone numbers assigned to a group.

In operation S the cloud server determines whether an electronic device corresponding to a phone number is in a suitable condition for receiving the print job request.

In operation S when it is determined that the electronic device is not in the suitable condition the cloud server selects another electronic device. The other electronic device different from the electronic device corresponding to the phone number may be an electronic device pre set by a user.

In operation S a cloud server sets print job conditions in the cloud server. In detail the print job conditions may be set as a mobile terminal or a host executes an application or calls an ARS server connected to the cloud server via an ARS.

In operation S the cloud server selects at least one of electronic devices connected according to the set print job conditions.

In operation S the cloud server transmits the print job to the selected at least one electronic device.

In operation S a cloud server receives a print job request destined for a plurality of phone numbers assigned to a group.

In operation S the cloud server checks capability information of electronic devices corresponding to the plurality of phone numbers to determine whether the electronic devices are suitable for performing the print job. The cloud server may receive the capability information and check conditions set based on the received capability information to determine whether the electronic devices corresponding to the plurality of phone numbers are suitable for performing the print job.

In operation S the cloud server selects at least one of the electronic devices corresponding to the plurality of phone numbers included in the group based on a result of the determining.

In operation S the cloud server transmits the print job request to the selected at least one electronic device.

According to an embodiment a sender may transmit the same print jobs having different destinations only once to a cloud server together with life information of the print jobs to store the print jobs in the cloud server and transmit the print jobs to electronic devices according to the life information of the print jobs to perform the print jobs.

In a general cloud printing service provided by a cloud server a sender transmits the same print jobs having different destinations several times. Accordingly unnecessary transmission traffics are generated and since the same print jobs are individually stored in several storage spaces the storage spaces are unnecessarily wasted.

Accordingly one or more embodiments provide a method enabling when a sender transmits the same print jobs having different destinations only once together with life information of the print jobs a cloud server to determine whether a content is transmittable based on the life information of the print jobs and transmit the print jobs to electronic devices such that the print job is performed. An embodiment will now be described in detail with reference to .

Referring to the cloud printing system includes a mobile terminal a cloud server and image forming apparatuses through . The mobile terminal may be replaced by any one of various electronic devices such as a laptop a tablet a personal computer PC portable media player PMP digital camera laptop computer notebook computer portable game player wearable device or a personal digital assistant PDA to perform the same functions as the mobile terminal . Further it is understood that embodiments are also applicable to any device with which an apparatus method or medium of an embodiment can be used

In the cloud printing system a user uploads data stored in the mobile terminal to the cloud server . Then the user may request the cloud server to print the data any time at any place.

The cloud server may map a phone number to each image forming apparatus and use the mapped phone number as a destination address for data transmission. The cloud server may include a storage space according to image forming apparatuses and each storage space may be mapped to correspond to each of phone numbers of the image forming apparatuses. For example a phone number 031 xxx yyyy may be mapped to correspond to the image forming apparatus and the mapped phone number may be used as a destination address. Accordingly when the user requests the cloud server for a print job destined for the mapped phone number by using the mobile terminal the cloud server stores the print job in the storage spaces for the image forming apparatuses through . Then the cloud server may transmit the stored print job to the image forming apparatuses through . The image forming apparatuses through receive the print job and perform the received print job.

Alternatively the cloud server may include storage spaces according to phone numbers and may map printers to respectively correspond to the storage spaces according to phone numbers. For example A printer may be mapped to correspond to a storage space of a phone number of a mobile terminal of a user A. Such a storage space may be accessed by a person corresponding to the phone number. For example the storage space of the phone number of the mobile terminal of the user A may be accessed by the user A using the mobile terminal of the user A.

In an embodiment the user transmits a print job destined for phone numbers of users A through C. It is assumed that printers are respectively mapped to storage spaces of phone numbers of mobile terminals of the users A through C.

In operation S the user transmits the print job destined for the phone number of the user A by using the mobile terminal to the cloud server .

Upon receiving the print job the cloud server stores the print job in the storage spaces provided according to phone numbers. Print files included in the print jobs may be stored. The print jobs have the same print file despite of different destinations. However since the print jobs are separately requested the same print file is stored separately in the storage spaces according to phone numbers.

In an embodiment since the user requested to print a print file a.doc the print file a.doc is stored in the storage spaces according to phone numbers.

Accordingly the user has to transmit the print jobs having different destinations several times thereby causing unnecessary transmission traffics. Also since the same print file is separately stored in the storage spaces according to phone numbers the storage spaces are unnecessarily wasted.

In operation S a user transmits print operations destined for phone numbers of users A through C to the cloud server by using the mobile terminal .

The cloud server may store only one of print files included in the print jobs set a printing number of times by mapping the printing number of times to the print file and store the set printing number of times. The print file and the printing number of times may be stored in a table form in which the print file and the printing number of times are mapped. For example a table in which a printing number of times 3 is mapped to a print file a.doc may be stored.

Unlike the cloud server may map print file reference which references one print file to a phone number. A table in which a print file reference is mapped to a phone number may be stored. For example a table in which a print file reference indicating the print file a.doc and a phone number are mapped may be stored. Phone numbers of users are mapped to correspond to storage spaces according to phone numbers.

Thus according to an embodiment when a mobile terminal transmits print jobs on the same print file destined for a plurality of phone numbers only one print job may be transmitted so as to prevent unnecessary transmission traffic. In addition since the same print file is stored once a cloud server may not waste storage spaces according to phone numbers and efficiently use resources.

Referring to the cloud server according to an embodiment includes a receiver a storage unit a determiner a transmitter and a controller .

The cloud server receives a print job from outside the cloud server and transmits the print job based on determining whether the print job is transmittable according to a life of the print job.

The receiver receives data and the transmitter transmits the data. In detail the receiver receives the print job and the transmitter transmits the print job.

The storage unit stores data. In detail the storage unit stores a content and the life of the print job.

The determiner determines whether the content is transmittable according to the life of the print job.

The controller controls the receiver to receive the print job destined for a plurality of phone numbers. The controller controls the storage unit to store the content included in the print job as one file. Also the controller controls the storage unit to map the life of the print job according to the stored content and to store the life of the print job. The controller controls the transmitter to transmit the content to at least one of a plurality of electronic devices corresponding to the plurality of phone numbers based on a result of determining by the determiner .

The controller may control the storage unit to map a printable number of times to correspond to the stored content and to store the printable number of times of the print job. The determiner may determine that the content is transmittable when the printable number of times is not 0. Also when the content is transmitted the controller may control the storage unit to adjust the printable number of times. The controller may delete the stored content when the printable number of times is 0.

The controller may control the storage unit to map a printable duration to correspond to the stored content and to store the printable duration of the print operation. The determiner may determine whether the printable duration is passed and determine that the content is transmittable when the printable duration is not passed.

The controller controls the receiver to receive a request on the content from at least one of the plurality of electronic devices. Upon receiving the request the determiner determines whether the content is transmittable based on the life of the print job. The controller may control the transmitter to transmit the content to the at least one of the plurality of electronic devices based on a result of the determining.

The controller may control the storage unit to map the plurality of phone numbers to the content and store the plurality of phone numbers according to the content. Also when the print job is transmitted destined for at least one phone number the controller controls the storage unit to delete a phone number to which the print job is transmitted from stored phone numbers. Then the controller may control the transmitter to transmit the content to electronic devices corresponding to the stored phone numbers. In other words the content is not repeatedly transmitted to one electronic device.

However an embodiment is not limited to mapping a phone number to a content and the controller may store contents of print jobs having a plurality of destinations only once in any one of various methods and print the contents once at each destination.

The controller may control the storage unit to set and store the printable number of times according to the number of phone numbers that are destinations of the print job. For example when a print job destined for three phone numbers is received the controller may control the storage unit to set and store a printable number of times to three.

The cloud printing system according to an embodiment includes the mobile terminal the cloud server and the image forming apparatus .

The mobile terminal included in the cloud printing system of an embodiment transmits a print job to the cloud server . Upon receiving the print job the cloud server sets a life of the print job and transmits the print job to the image forming apparatus according to the life of the print job. The image forming apparatus receives and performs the print job.

The mobile terminal includes a receiver a transmitter a controller a storage unit and a user input receiver .

The receiver receives data and the transmitter transmits the data. In detail a print job may be transmitted.

The user input receiver receives an input for controlling various operations of the mobile terminal from a user. In detail the user input receiver receives an input for selecting a plurality of phone numbers from the user. Also the user input receiver may receive an input for selecting a content to be included in a print job from contents stored in the storage unit from the user.

The controller controls the user input receiver to receive the input for selecting the plurality of phone numbers and the input for selecting the content to be included in the print job from the user and controls the transmitter to transmit the print job including the selected contents to the plurality of phone numbers.

Since the cloud server performs the same operations as the cloud server of details thereof are not repeated here.

The image forming apparatus includes a receiver a transmitter a print operation performer and a controller .

The receiver receives data and the transmitter transmits the data. In detail the receiver receives a print job and the transmitter may transmit a request for a content.

The controller controls the receiver to receive the content from the cloud server . The controller may control the transmitter to transmit the request for the content to the cloud server and control the receiver to receive the content from the cloud server in response to the request.

The cloud printing system is not limited to performing the print job as the image forming apparatus directly receives the content but alternatively the content may be first transmitted to an electronic device such as the mobile terminal and the image forming apparatus may receive and perform the print job including the content from the electronic device.

Referring to a user may set a group including a plurality of phone numbers by using a mobile terminal and generate a print job destined for the plurality of phone numbers. In detail the mobile terminal may receive an input from the user to set the group and generate the print job.

In order to set the group including the plurality of phone numbers the user selects Group Setting from a print request screen displayed on the mobile terminal. The user selects Add from a group management screen displayed on the mobile terminal. The user inputs a name of the group to be generated and phone numbers to be included in the group respectively to a group name input box and a phone number input box in a group addition screen displayed on the mobile terminal. For example in an embodiment the user generates a home study material A group including phone numbers 010 1111 1111 and 010 2222 2222 . Then the user selects Add to generate the group. Accordingly the home study material A group is added to the group management screen . The user inputs a destination phone number or group to a destination input box in the print request screen . For example the user inputs the phone number 010 1111 1111 a group company and a group Samsung Apartment . Then when the user selects Print a print job destined for the destination phone number or group input in the destination input box is generated and transmitted to a cloud server.

A user may select a destination by checking a box in a destination select screen displayed on a mobile terminal. In an embodiment the user selects a My Company group as a destination of a print job.

Then the user may select a content type through a content type select screen . In an embodiment the user selects Documents to print a document.

Then the user selects a file to be printed through a print file select screen . The print file select screen may display various files stored in the mobile terminal and the user may select one file by checking a box. In order to transmit such a print job the user may pre check data to be printed through a preview screen .

The HTTP packet for transmitting a print job in a mobile terminal may include contents related to a request uniform resource locator URL a phone number and a print file .

In an embodiment it is assumed that a user transmits a print job regarding a print file document.doc and destined for phone numbers 010 0000 0000 010 1111 1111 and 010 2222 2222 to http xx.xx.xx.xx transmit that is an address of a cloud server.

The mobile terminal generates the HTTP packet by setting the request URL to be http xx.xx.xx.xx transmit that is the address of the cloud server. Also the mobile terminal generates the HTTP packet by setting the phone number to be the phone numbers 010 0000 0000 010 1111 1111 and 010 2222 2222 . Also the mobile terminal generates the HTTP packet by setting the print file to be the print file document.doc . As such the mobile terminal may generate the HTTP packet including the contents relates to the request URL the phone number and the print file and transmit the print job destined for the plurality of phone numbers to the cloud server.

Referring to a cloud server stores the document and count table and the phone number and document reference table and may manage an job request received by using the document and count table and the phone number and document reference table .

The document and count table maps and stores a file name and a printable number of times . For example when a request to print a image.jpg file destined for three phone numbers is received from outside the cloud server the document and count table stores the image.jpg file as the file name and 3 as the printable number of times in one row.

The phone number and document reference table maps and stores a phone number and a document reference . Phone numbers may be mapped to correspond to storage spaces according to phone numbers.

For example when the request to print the image.jpg file destined for the three phone numbers is received from outside the cloud server the phone number and document reference table stores the image.jpg file as the document reference . In the phone number and document reference table the three phone numbers are stored as the phone number in three rows.

Only one image.jpg file to be printed is stored in the cloud server. In other words the cloud server does not store the image.jpg file according to phone numbers. The image.jpg stored as the document reference and the file name indicates one image.jpg file. In other words the document reference and the file name may be mapped to correspond to a stored document file.

Referring to in operation S a printer requests for a print job regarding an image.jpg file. In operation S the cloud server transmits the image.jpg file to the printer. A phone number set according to the printer that requested for the print is 010 4444 4444 . The cloud server deletes a row where a phone number is 010 4444 4444 and a document reference is image.jpg from a phone number and document reference table . Then the cloud server reduces a printable number of times in a row where a file name is image.jpg by 1 from a document and count table . In an embodiment the printable number of times is reduced from 3 to 2.

Referring to a printer requests for a print job regarding a document.doc file in operation S. In operation S the cloud server transmits the document.doc file to the printer. A phone number set according to the printer that requested for the print is 010 4444 4444 . The cloud server deletes a row where a phone number is 010 4444 4444 and a document reference is document.doc from a phone number and document reference table . In such a row is already deleted from the phone number and document reference table .

Then the cloud server reduces a printable number of times in a row where a file name is document.doc by 1 from a file name and count table . In an embodiment since the reduced printable number of times is 0 a row where a file name is document.doc is deleted from the file name and count table .

Referring to a cloud server stores the document and printable duration table and the phone number and document reference table and may manage job requests by using the document and printable duration table and the phone number and document reference table .

The document and printable duration table maps and stores a file name a printable duration and a registered date . The printable duration may be pre set in the cloud server. In an embodiment it is assumed that printable durations are 2 days throughout files. For example when a request to print an image.jpg file destined for three phone numbers is received from outside the cloud server the image.jpg file is stored as the file name and 2 days are stored as the printable duration in one row of the document and printable duration table . When the print job is registered stored in the cloud server information about the date and time may be obtained and a registered date may be registered together with the print job. In an embodiment the registered date is 02 December 2013 .

Referring to in operation S a printer requests for a print job regarding an image.jpg file. A phone number corresponding to the printer that requested for the print job is 010 4444 4444 . The cloud server checks a printable duration in a row where a file name is image.jpg from a document and printable duration table . When a point of time the print job is requested is 03 December 2013 two days are not passed from the registered date of 02 December 2013 . Thus in operation S the cloud server transmits the print job to the printer.

However when the point of time the print operation is requested is 05 December 2013 the cloud server determines that the printable duration is already passed. Accordingly operation S is not performed and the row where the file name is image.jpg is deleted from the document and printable duration table . At this time a row where a file reference is image.jpg may also be deleted from a phone number and file reference table .

In operation S the server maps and sets a life of the print job to correspond to the stored content and stores the life of the print job.

In operation S the server determines whether the content is transmittable according to the life of the print job. The server receives a request on the content from at least one of a plurality of electronic devices and upon receiving the request may determine whether the content is transmittable to the at least one electronic device based on the life of the print job.

In operation S the server transmits the content to the at least one electronic device corresponding to the plurality of phone numbers based on a result of the determining. The server may transmit the content to an electronic device that requested for the content based on the result of determining.

In operation S the server maps and sets a printable number of times to correspond to the stored content and stores the printable number of times. The printable number of times may be set to correspond to the number of plurality of phone numbers that are destinations of the print job.

In operation S the server determines whether the content is transmittable based on whether the printable number of times is 0. In other words the server may determine that the content is transmittable when the printable number of times is not 0.

In operation S the server transmits the content to at least one of a plurality of electronic devices corresponding to the plurality of phone numbers based on a result of the determining.

When the content is transmitted the printable number of times may be additionally adjusted. Also when the printable number of times is 0 the content may be deleted.

In operation S the server maps and sets a printable duration to correspond to the stored content and stores the printable duration.

In operation S the server determines whether the content is transmittable based on whether the printable duration is passed. In other words the server may determine that the content is transmittable when the printable duration is not passed.

In operation S the server transmits the content to at least one of a plurality of electronic devices corresponding to the plurality of phone numbers based on a result of the determining.

In operation S the server maps and sets a printable number of times to correspond to the stored content and stores the printable number of times.

In operation S the server maps and stores the plurality of phone numbers to correspond to the content.

In operation S the server determines whether the content is transmittable based on whether the printable number of times is 0.

In operation S the server transmits the content to an electronic device corresponding to the stored phone number.

In operation S after the content is transmitted the server deletes the phone number to which the content is transmitted.

According to an embodiment a sender may transmit a content to a person who does not subscribe to a cloud printing service and at this time an invitation message may be transmitted to a non subscriber to induce the non subscriber to subscribe the cloud printing service and receive the content.

A cloud printing service provided by a cloud server is generally provided only to users subscribed to the cloud printing service. Accordingly a sender is unable to transmit a content to be printed if a recipient is not a user subscribed to the cloud printing service and the user has to subscribe to the cloud printing service to be provided with the cloud printing service. Accordingly one or more embodiments provide a method enabling a sender to transmit a content to be printed even to a person who does not subscribe to a cloud printing service and at this time an invitation message is transmitted to a non subscriber to induce the non subscriber to subscribe to the cloud printing service and receive the content. An embodiment will be described in detail with reference to .

According to the cloud printing system the user device transmits a content and a phone number to which the content is to be transmitted to the cloud server . The cloud server determines whether the received phone number is registered in the cloud server and if the received phone number is not registered transmits a server registration induction message to the received phone number and stores the content correspondingly to the received phone number. The device transmits a server registration request corresponding to the server registration induction message to the cloud server and the cloud server transmits the stored content to the device .

Thus according to an embodiment a user of the user device may transmit the content and the phone number regardless of whether the phone number is registered in the cloud server .

A user of the device mapped to a phone number that is not registered in the cloud server receives a server registration induction message from the cloud server and transmits a server registration request to the cloud server in response. Based on the transmitted server registration request the phone number is registered in the cloud server . As such a non subscriber is induced to easily subscribe a phone number based printing service.

After the registration the user of the device may receive contents stored before the registration from the cloud server . In other words the user may receive the contents stored before the phone number of the device is registered and thus the user may experience a seamless service.

The user of the user device may transmit the content regardless of whether the phone number is registered in the cloud server . Accordingly the user of the user device may have confidence that content shall be transmitted to a desired phone number.

The network interface unit network interface transmits the content and the phone number to which the content is to be transmitted. Also the network interface unit may receive a message indicating whether to transmit the server registration induction message and transmit a response to the message.

The controller controls the network interface unit to transmit the content and the phone number. The controller may control the network interface unit to receive the message indicating whether to transmit the server registration induction message from the cloud server and to transmit the response to the message to the cloud server .

The user device may include a UI unit not shown . The UI unit may receive inputs indicating the content and the phone number from a user. The UI unit may receive the response to the message indicating whether to transmit the server registration induction message from the user.

The cloud server includes a network interface unit network interface a controller a determiner and a storage unit storage .

The network interface unit receives the content and the phone number to which the content is to be transmitted. The network interface unit transmits the server registration induction message to the received phone number and transmits the content stored in the storage unit to the device mapped correspondingly to the received phone number.

The storage unit storage stores the content and the phone number. Also the storage unit may store a user identifier.

The determiner determines whether the phone number received by the network interface unit is registered in the cloud server . Also the determiner may determine whether a predetermined period is passed from a point of time when the content is stored.

If the determiner determines that the phone number is not registered in the cloud server the controller transmits the server registration induction message to the phone number receives the server registration request corresponding to the server registration induction message and controls the network interface unit to transmit the stored content to the device mapped correspondingly to the phone number.

Also the controller controls the storage unit to store the content correspondingly to the received phone number. When the determiner determines that the predetermined period is passed the controller may control the storage unit to delete the stored content.

The cloud server may further include an authenticator not shown . The authenticator may perform authentication on the phone number upon receiving the server registration request.

The controller may control the storage unit to map and register a plurality of phone numbers correspondingly to the user identifier.

The controller may control the network interface unit to transmit the message indicating whether to transmit the server registration induction message to the device receive a response to the message from the cloud server and transmit the server registration induction message based on the response.

The network interface unit receives the server registration induction message. Also the network interface unit transmits the server registration request in response to the server registration induction message.

The controller controls the network interface unit to receive the server registration induction message transmit the server registration request correspondingly to the server registration induction message and receive the content.

The device may further include a UI unit not shown . The UI unit may receive the server registration request correspondingly to the server registration induction message from the user and display the received content to the user.

The device may further include a print operation performer not shown . The print operation performer performs a printing operation of the received content. For example the device may be a mobile terminal. The mobile terminal stores an intrinsic phone number in a universal subscriber identity module USIM chip and thus is communicable by using a mobile network based on the intrinsic phone number. Accordingly even when a phone number is not registered in the cloud server the cloud server may transmit a server registration induction message to the phone number via an MMS. The user may receive the content from the cloud server by using the mobile terminal pre check the content via a display or the like and print the content by directly transmitting the content to an image forming apparatus connected to the mobile terminal. Alternatively the user may map and register an image forming apparatus correspondingly to a phone number registered in the cloud server and the mobile terminal may request the cloud server to transmit the content to the mapped image forming apparatus.

However alternatively the device may be an apparatus including a print operation performer such as an image forming apparatus. For example when the device is a kiosk that is a public image forming apparatus the device is communicable through a phone network based on an intrinsic phone number. Accordingly the cloud server is able to transmit a message to the image forming apparatus and the user is able to transmit a server registration request through a UI unit of the image forming apparatus to register the image forming apparatus and receive a content.

Since the cloud server of performs the same operations as the cloud server of details thereof are not repeated here.

In operation S the user device transmits the content and the phone number to which the content is to be transmitted to the cloud server . The cloud server receives the content and the phone number.

In operation S the cloud server determines whether the received phone number is registered in the cloud server .

In operation S when it is determined that the received phone number is not registered the cloud server transmits the server registration induction message to the received phone number. The device receives the server registration induction message from the cloud server .

In operation S the device may transmit the server registration request to the cloud server in response to the server registration induction message.

In operation S the cloud server may transmit the stored content to the device mapped correspondingly to the phone number.

In operation S the cloud server receives the content and the phone number to which the content is to be transmitted.

In operation S the cloud server determines whether the received phone number is registered in the cloud server .

In operation S when it is determined that the received phone number is not registered the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the server registration induction message to the device based on the received phone number.

In operation S the cloud server receives the server registration request corresponding to the server registration induction message from the device . Upon receiving the server registration request the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S when it is determined that the received phone number is registered the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S the cloud server receives the content and the phone number to which the content is to be transmitted.

In operation S the cloud server determines whether the received phone number is registered in the cloud server .

In operation S when it is determined that the received phone number is not registered the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the server registration induction message to the received phone number.

In operation S the cloud server receives the server registration request corresponding to the server registration induction message.

In operation S the cloud server determines whether authentication performed on the received phone number succeeded.

In operation S when the authentication succeeded the cloud server registers the device after mapping the device correspondingly to the received phone number.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S when it is determined that the received phone number is registered in the cloud server the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S the cloud server receives the content and the phone number to which the content is to be transmitted.

In operation S the cloud server determines whether the received phone number is registered in the cloud server .

In operation S when the received phone number is not registered in the cloud server the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the server registration induction message to the received phone number. For example the cloud server transmits the server registration induction message to the device mapped correspondingly to the received phone number.

In operation S the cloud server receives the server registration request corresponding to the server registration induction message.

In operation S the cloud server determines whether authentication performed on the received phone number succeeded. Also the cloud server may determine whether authentication performed on the user identifier succeeded.

In operation S the cloud server maps and registers the device correspondingly to the received phone number. Also the cloud server maps and registers the phone number correspondingly to the user identifier. The cloud server may map and register a plurality of phone numbers correspondingly to the user identifier.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S when the received phone number is registered in the cloud server the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

If a plurality of phone numbers are mapped and registered correspondingly to a user identifier a user is able to check all contents destined for the plurality of phone numbers mapped correspondingly to the user identifier when the user logs in via authentication on the user identifier. For example when the cloud server provides a webpage providing a printing service to a user and the user logs in the webpage by performing authentication on a user identifier the user is able to check all contents destined for a plurality of phone numbers mapped correspondingly to the user identifier.

However if a user checks a content transmitted to his her phone number by using a mobile terminal the user is able to check only a content mapped correspondingly to his her phone number. In other words even when a plurality of phone numbers are mapped correspondingly to a user identifier only the content mapped correspondingly to his her phone number is received if the mobile terminal is used. However alternatively the user may pre set the mobile terminal to receive a content destined for a plurality of phone numbers mapped correspondingly to the user identifier.

In operation S the cloud server receives the content and the phone number to which the content is to be transmitted.

In operation S the cloud server determines whether the received phone number is registered in the cloud server .

In operation S when it is determined that the received phone number is not registered the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the server registration induction message to the received phone number. For example the cloud server transmits the server registration induction message to the device mapped correspondingly to the received phone number.

In operation S the cloud server determines whether a predetermined period is passed from a point of time when the content is stored.

In operation S when it is determined that the predetermined period is not passed and the cloud server receives the server registration request corresponding to the server registration induction message from the device the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S when it is determined that the received phone number is registered the cloud server stores the content after mapping the content to the received phone number.

In operation S the cloud server transmits the stored content to the device mapped correspondingly to the received phone number.

In operation S when it is determined that the predetermined period is passed the cloud server deletes the stored content.

Referring to a user transmits the content by inputting the phone number to which the content is to be transmitted by using the user device . When the cloud server determines that the phone number is not registered the cloud server transmits a message to the user device . The message is about whether to transmit the service subscription invitation message to a person using the phone number. When the user selects OK from the message the cloud server transmits the service subscription invitation message to the phone number. For example the cloud server transmits the service subscription invitation message to the device . The device may be a device using an intrinsic phone number such as a mobile terminal. However instead of transmitting the service subscription invitation message from the cloud server the user device may directly transmit the service subscription invitation message in an SMS form to the device if the user device is a mobile terminal.

The device may download and install an application from an address shown in the service subscription invitation message and transmit a service subscription request to the cloud server through the application. However alternatively a user of the device may transmit the service subscription request to the cloud server without having to install the application.

Referring to the device is a mobile terminal. Since a mobile terminal uses an intrinsic phone number the mobile terminal may receive an SMS and perform authentication on the intrinsic phone number.

The device selects Request on an application providing a service for authenticating a phone number to request the cloud server to transmit an authentication number. Accordingly the cloud server generates a PIN code. When the cloud server transmits the generated PIN code to the device the user of the device checks and inputs the PIN code and selects Authenticate . Then the device transmits the inputted PIN code the cloud server and the cloud server compares the inputted PIN code and the generated PIN code. When the inputted PIN code and the generated PIN code match the authentication is completed.

Referring to authentication is performed on a user account used in a service according to an embodiment.

In when a user inputs a user account into an input box inputs a password into an input box and selects Login information including the user account and the password is transmitted to the cloud server for authentication.

For example in an embodiment the user inputs Samsung as the user account into the input box inputs four digit password into the input box and selects Login to authenticate the user account.

The cloud server completes authentication when a stored user account and a stored password match the user account and the password input by the user.

In operation S the API server determines whether a user account is also transmitted while authenticating a phone number. In other words the user of the device may request the API server to authenticate the phone number while authenticating the user account and the API server may determine whether the user account is also transmitted while authenticating the phone number to determine whether the user account is to be authenticated.

In operation S when it is determined that the user account is not transmitted while authenticating the phone number the API server determines whether the phone number is registered in a database. In other words when it is determined that the user account is not requested to be authenticated while authenticating the phone number the API server determines whether the phone number is registered in the database.

In operation S when it is determined that the phone number is registered in the database the API server determines whether the phone number is interlocked with the user account.

In operation S when it is determined that the phone number is interlocked with the user account the API server requests the device to determine whether to authenticate the user account determined to be interlocked with the phone number of the device . When a request to authenticate the user account is received the API server requests an authentication server to transmit an access token for the user account by transmitting the user account with the request. On the other hand when a request not to authenticate the user account is received the API server does not transmit the user account so as to authenticate the phone number without the user account and requests the authentication server to transmit a new access token.

In operation S when it is determined that the phone number is not interlocked with the user account the API server requests the authentication server to transmit a new access token. In other words the API server requests the authentication server to transmit an access token so as to obtain authority to use a service by registering the phone number. In operation S the API server receives a result of the request from the authentication server. For example when the request is successfully authenticated the API server receives the access token and when the request is failed the API server receives a value indicating an authentication failure instead of the access token.

In operation S the authentication server receives a request to authenticate a PIN code from the API server.

In operation S the authentication server determines whether a user account is also transmitted while authenticating a phone number.

In operation S when it is determined that the user account is also transmitted the authentication server determines whether the phone number is interlocked with another user account.

In operation S when it is determined that the phone number is interlocked with the other user account the authentication server authenticates the transmitted user account. At the same time the authentication server may authenticate the PIN code. When the authenticating succeeds the authentication server deactivates an access token of the other user account.

In operation S the authentication server determines whether the authenticating of the PIN code succeeded.

In operation S when it is determined that the PIN code is successfully authenticated the authentication server determines whether an access token is assigned to the phone number.

In operation S when it is determined that the access token is assigned to the phone number all access tokens of the phone number are deactivated.

In operation S when it is determined that the access token is not assigned to the phone number the authentication server assigns a new access token to the phone number. Also when it is determined that the access token is assigned to the phone number the authentication server assigns a new access token to the phone number. When the access token of the other user account is deactivated the authentication server may assign a new access token to the phone number. Also when it is determined that the phone number is not interlocked with the other user account the authentication server requests the device to authenticate the other user account. Also the authentication server may also authenticate the PIN code. When the authenticating of the PIN code succeeds the authentication server assigns a new access token to the phone number.

In operation S when the authenticating of the PIN code fails the authentication server transmits a value indicating an authentication failure to the API server.

In operation S the authentication server assigns a new access token to the phone number the authentication server transmits the new access token to the API server. are diagrams for describing processes of performing authentication on a phone number in response to a service subscription inducement message which are performed by a service non subscriber.

A user A uses a mobile terminal M as a usage device uses 010 as a phone number a service application is installed in the usage device based on a service subscription message received from a server regarding an application installation state the phone number is not interlocked with any ID regarding a user account interlocking state and the usage device did not obtain an access token regarding an access token obtain state .

In operation S the user A requests an API server to transmit a PIN code by using the mobile terminal M as the usage device .

In operation S the authentication server generates the PIN code and stores the PIN code in a database .

In operation S the authentication server transmits the generated PIN code to the mobile terminal M via an SMS.

Accordingly the user A may receive the PIN code via the SMS from the authentication server by requesting the PIN code by using the mobile terminal M as the usage device .

In operation S the user A requests the API server to authenticate the PIN code by using the mobile terminal M.

In operation S the API server checks a user table stored in the database . In the user table user identifiers phone numbers and devices are correspondingly mapped to each other.

In operation S when there is no user registered in a requested phone number the API server requests the authentication server to authenticate the PIN code.

In operation S the authentication server generates an access token with respect to the request to authenticate the PIN code and stores the access token in the database .

Accordingly the user A may access a content stored in a cloud server by using the access token as the phone number is registered in the cloud server such that the mobile terminal M is able to use a service of the cloud server.

In an embodiment it is assumed that a user A is able to use a service by using a mobile terminal M as a usage device as the mobile terminal M obtains an access token as shown in .

The user A uses a tablet T as a usage device uses 010 as a phone number a service application is installed in the usage device regarding an application installation state the phone number is not interlocked with any ID regarding a user account interlocking state and the usage device did not obtain an access token regarding an access token obtain state .

In operation S the authentication server generates the PIN code in response to the request and stores the generated PIN code in a database .

In operation S the authentication server transmits the generated PIN code to the mobile terminal M via an SMS. However if the tablet T has an intrinsic phone number different from the mobile terminal M the PIN code may be transmitted to the tablet T.

In operation S the user A may request the API server to authenticate the PIN code by checking the PIN code received by the mobile terminal M and inputting the PIN code by using the tablet T.

In operation S the API server checks a user table stored in the database . The API server determines that the phone number i.e. 010 is already registered correspondingly to the mobile terminal M.

In operation S the API server transmits a request to authenticate the PIN code to the authentication server .

In operation S the authentication server generates an access token and stores the generated access token in the database .

The tablet T is able to use the service by receiving the access token. However since an access token pre transmitted to the mobile terminal M is deactivated the user A is unable to use the service by using the mobile terminal M.

In this case in order for the user A to use the service again by using the mobile terminal M the user A may request for a PIN code by using the mobile terminal M request to authenticate the received PIN code and obtain an access token again for the mobile terminal M. At this time the authentication server deactivates the access token transmitted to the tablet T and thus the user A is unable to use the service by using the tablet T.

The user A uses a mobile terminal M as a usage device uses 010 as a phone number a service application is installed in the usage device regarding an application installation state the phone number is not interlocked with any ID regarding a user account interlocking state and the usage device obtained an access token regarding an access token obtain state .

In operation S the user A transmits an account interlock request to an API server by using the mobile terminal M. In the account interlock request a user account is transmitted together with a phone number as one parameter.

In operation S when there is no user account registered in the phone number based on the stored user table the API server requests an authentication server to transmit an access token for the user account.

In operation S all access tokens for phone numbers registered in the authentication server are deactivated and an access token for a new user account is generated. The generated access token is stored in the database .

Accordingly a user account A and the phone number are interlocked with each other in the mobile terminal M.

In operation S the authentication server generates the PIN code and stores the generated PIN code in the database .

In operation S the authentication server transmits the generated PIN code to the mobile terminal M via an SMS.

In operation S the user A inputs the PIN code received by the mobile terminal M to request the API server to authenticate the PIN code.

In operation S the API server checks a user table stored in the database . The API server determines that a phone number 010 and a user account A are interlocked with each other by using the mobile terminal M by checking the user table.

In operation S the API server may request the tablet T to determine whether to authenticate the user account A . Since the user A owns the user account A the user A transmits a request to authenticate the PIN code again to the API server together with the user account A by using the tablet T.

In operation S the API server checks the user table stored in the database . The API server determines whether a requested phone number and user account match those that are pre registered.

In operation S when it is determined that the requested phone number and user account match those that are pre registered the API server requests the authentication server to authenticate the PIN code together with the user account A .

In operation S the authentication server authenticates the PIN code and the user account A and additionally generates an access token for the tablet T without deactivating an existing access token when the user account A and the phone number 010 are interlocked with each other. The additionally generated access token is stored in the database .

In operation S the authentication server transmits the additionally generated access token to the API server .

In an embodiment since the existing access token is not deactivated the user A is able to use the service not only by using the tablet T and also by using the mobile terminal M.

A user A uses a service by using the mobile terminal M. In other words the user A uses the mobile terminal M as a usage device uses 011 as a phone number a service application is not installed in the usage device regarding an application installation state the phone number is not interlocked with any ID regarding a user account interlocking state and the usage device did not obtain an access token regarding an access token obtain state .

In operation S the user A requests an API server to transmit a PIN code by using the mobile terminal M.

In operation S the authentication server generates the PIN code upon the request and stores the generated PIN code in a database .

In operation S the authentication server transmits the generated PIN code to the mobile terminal M via an SMS.

In operation S the user A inputs the received PIN code by using the mobile terminal M to request the API server to authenticate the PIN code.

In operation S it is determined that there is no user registered in a requested phone number 011 and the API server requests the authentication server to authenticate the PIN code.

In operation S the authentication server receives the request to authenticate the PIN code and when authenticating the PIN code succeeds generates and stores an access token in the database .

Accordingly the user A receives the access token by using the mobile terminal M and is able to use the service by using the mobile terminal M. The user A is able to use the service also by using the mobile terminal M and the tablet T which are registered in different phone numbers 010 since access tokens of the mobile terminal M and the tablet T are not deactivated.

In operation S the user A transmits an authentication request to the API server together with a user account A by using the mobile terminal M.

In operation S the API server checks a user table stored in the database . When it is determined that a requested phone number 011 is not interlocked with a user account the API server transmits the authentication request to the authentication server together with the user account A in operation S.

In operation S the authentication server authenticates a user account and a phone number based on the authentication request and when the authenticating succeeds generates an access token. At this time an existing access token is deactivated and the access token is newly generated. The generated access token is stored in the database .

Referring to a user A applied to cancel the mobile terminal M. Accordingly the user A is no longer able to use the mobile terminal M. Thus the phone number 010 is able to be used by another person and thus the other user B opened the mobile terminal M with the phone number 010 .

The other user B uses the mobile terminal M as a usage device uses 010 as a phone number a service application is installed in the usage device regarding an application installation state the phone number is not interlocked with any ID regarding a user account interlocking state and the usage device did not obtain an access token regarding an access token obtain state .

In operation S the other user B requests an API server to transmit a PIN code by using the mobile terminal M.

In operation S the authentication server receives the request generates the PIN code upon the request and stores the generated PIN code in a database .

In operation S the authentication server transmits the generated PIN code to the mobile terminal M via an SMS.

In operation S the other user B checks and inputs the received PIN code to request the API server to authenticate the PIN code.

In operation S since the phone number 010 is interlocked with a user account A based on the user table the API server requests the mobile terminal M whether to authenticate the user account A .

In operation S since the other user B does not have a user account the other user B requests the API server to authenticate a PIN code without a user account by using the mobile terminal M.

In operation S the authentication server authenticates the PIN code and when the authenticating succeeds generates an access token. Here since all access tokens for devices mapped correspondingly to the phone number 010 are deactivated the access token for the tablet T used by the user A is deactivated and thus the user A is no longer able to use a service by using the tablet T.

Accordingly the mobile terminal M obtains the access token and thus the other user B is able to use the service by using the mobile terminal M.

The other user B uses the mobile terminal M as the usage device uses 010 as the phone number a service application is installed in the usage device regarding the application installation state the phone number is not interlocked with any ID regarding the user account interlocking state and the usage device obtained the access token regarding the access token obtain state .

In operation S the other user B transmits an authentication request together with the user account B to the API server by using the mobile terminal M.

In operation S since the phone number 010 is not interlocked with any user account the API server transmits the authentication request together with the user account B to the authentication server .

In operation S when the authentication server successfully authenticates the user account B and the phone number 010 the authentication server deactivates an existing access token and generates a new access token. The generated new access token is transmitted to the database .

In operation S upon receiving the new access token the API server transmits the new access token to the mobile terminal M.

The mobile terminal M obtains the new access token and thus the other user B is able to use the service by using the mobile terminal M.

According to an embodiment since not only an invitation message but also a content are transmitted to a non subscriber the content may not be transmitted several times regardless of a subscription to a service. Also since a service may be used regardless of a recipient s subscription state anyone may send a document and thus the service may be easily spread. Also a recipient after subscribing to the service is able to view a document received before he she subscribed to the service and thus does not need to request a sender to re transmit the document.

In it has been described that the image forming apparatus of the image forming system supports a function of providing the phone number based cloud printing service. However the image forming apparatus may not support a network connection function to communicate with the cloud server or may only include a USB port to communicate one on one with a PC via a USB connection based on specifications of the image forming apparatus . In this case the image forming apparatus is unable to independently connect to the cloud server the image forming apparatus is unable to participate in the phone number based cloud printing service. Hereinafter a method of providing a phone number based cloud printing service under an environment when the image forming apparatus is unable to directly connect to the cloud server since the image forming apparatus does not support a network connection function will be described.

Unlike the image forming system described above with reference to the image forming system further includes the computing device in which the agent application is installed. It is assumed that the image forming apparatus of the image forming system does not support a network connection function and thus is able to independently connect to the cloud server . Accordingly different reference numerals are used to classify the image forming apparatus of and the image forming apparatus of .

Referring to the first individual for example John Lee selects a content used by or stored in the mobile device and inputs the phone number of the second individual for example Jane Kim who is to receive the content to the mobile device . Information about the content and the phone number of the second individual are transmitted from the mobile device to the cloud server .

The cloud server maps and stores the information about the content and the phone number of the second individual received from the mobile device .

As described above the cloud server manages phone numbers subscribed to a cloud printing service and registration information of image forming apparatuses respectively assigned to the phone numbers. The cloud server determines that a subject to print the content requested by the phone number of the second individual is the image forming apparatus based on the registration information.

In addition the cloud server manages path information about paths for transmitting print data of contents to the image forming apparatuses assigned to the phone numbers. The path information is information about whether to transmit print data from the cloud server directly to an image forming apparatus for example the image forming apparatus of or to an image forming apparatus for example the image forming apparatus of through a computing device for example the computing device of connected to the image forming apparatus . In other words the path information managed by the cloud server may be information for determining whether an image forming apparatus is capable of a direct network connection with the cloud server .

In it is assumed that the image forming apparatus is not capable of a direct network connection with the cloud server and thus the cloud server determines that a content to be printed by the image forming apparatus assigned to the phone number of the second individual is processed through the computing device in which the agent application is installed based on the path information.

The cloud server transmits the information about the content received from the mobile device to the computing device where the agent application is being executed.

The agent application manages lists of phone numbers and image forming apparatuses which are subscribed to the cloud printing service. For example the agent application may map and manage the phone number of the second individual and the image forming apparatus .

The computing device transmits print data of the content transmitted by the phone number of the second individual to the image forming apparatus based on the lists managed by the agent application .

The image forming apparatus prints the received print data. When the image forming apparatus completes the printing of the print data of the content the cloud printing service requested by the mobile device of the first individual to the phone number of the second individual is completed.

Hereinafter functions of the agent application and operations of the computing device for intermediating between the phone number based cloud printing service requested from the cloud server and the image forming apparatus that does not have a network connection function will be described in detail.

Even the image forming apparatus of that has a network connection function may provide the phone number based cloud printing service by using the agent application as described above. In detail when the image forming apparatus uses the agent application installed in the computing device data related to the phone number based cloud printing service which is to be performed by the image forming apparatus may be distributed to the agent application and thus throughput of the image forming apparatus may be reduced.

Referring to the computing device is connected between the cloud server and the image forming apparatus so as to support the phone number based cloud printing service of the image forming apparatus in the image forming system of .

The computing device is a general computer such as a PC or a laptop and includes a controller a network interface unit network interface a UI unit and a storage unit storage . In order to prevent features of an embodiment from being blurred only hardware components related to an embodiment are described in . However general purpose hardware components other that those shown in may be included in the computing device .

The controller is a hardware component controlling overall operations and functions of the computing device . In detail the controller may execute the agent application supporting the phone number based cloud printing service.

The agent application is software for controlling the image forming apparatus assigned to a target phone number for example the phone number of the second individual subscribed to the cloud printing service to print the content when the content requested to the target phone number is uploaded to the cloud server .

As described above the agent application manages the lists of phone numbers and image forming apparatuses subscribed to the cloud printing service. Accordingly the target phone number may be included in the list of phone numbers managed by the agent application . Also the image forming apparatus may be included in the list of image forming apparatuses managed by the agent application . In addition a mapping relationship is assigned between the lists of phone numbers and the lists of image forming apparatuses which are managed by the agent application .

The agent application may perform the functions of the printer driver described above with reference to .

The network interface unit network interface is a hardware component supporting a wired or wireless communication function and may support a wireless communication such as Wi Fi Wi Fi Direct an NFC Zigbee infrared data association IrDA or Bluetooth a wired communication such as Ethernet or a 2G mobile communication a 3G mobile communication or a 4G mobile communication.

The network interface unit receives the print data of the content transmitted to the target phone number from the cloud server . Then the network interface unit transmits the print data to the image forming apparatus assigned to the target phone number by the agent application .

The UI unit is a hardware component including an input device or a display device and displays information to or receives information from a user of the computing device . The user interface may include for example one or more of a keyboard a keypad a mouse a joystick a button a switch an electronic pen or stylus a gesture recognition sensor e.g. to recognize gestures of a user including movements of a body part an input sound device or voice recognition sensor e.g. a microphone to receive a voice command an output sound device e.g. a speaker a track ball a pedal or footswitch a virtual reality device and the like. The user interface may further include a haptic device to provide haptic feedback to a user. The user interface may also include a touchscreen display for example. The touchscreen display may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display and the like for example. However the disclosure is not so limited thereto and may include other types of touchscreen displays. The disclosure may also include other types of user interfaces.

The UI unit displays a UI screen of the agent application to the user. Also the user may input information on the UI screen of the agent application being executed in the computing device through the UI unit .

The storage unit is a hardware component capable of storing data such as a memory a hard disk drive HDD or a solid state drive SSD . In detail the agent application may be installed in the storage unit . Also the storage unit stores information about the lists of phone numbers and image forming apparatuses managed by the agent application .

In operation the controller of the computing device executes the agent application . It is assumed that the agent application is already registered in the cloud server for use.

In operation the first individual i.e. John Lee inputs information about a content to be printed and information about the phone number of the second individual i.e. Jane Kim which is a destination for receiving the content to be printed through the mobile device . The phone number of the second individual may be a phone number assigned to the mobile device of the second individual described above with reference to .

In operation the mobile device transmits the content input to the phone number of the second individual . In other words the mobile device uploads the information about the content and the information about the phone number of the second individual to the cloud server .

In operation the cloud server maps and stores the information about the content and the information about the phone number of the second individual .

In operation the cloud server determines that a subject to print the content requested to the phone number of the second individual is the image forming apparatus based on the registration information between phone numbers and image forming apparatuses. Also the cloud server determines that the content to be printed by the image forming apparatus is processed through the computing device where the agent application is installed based on the path information about paths for transmitting print data of contents to image forming apparatuses.

In other words the cloud server identifies that the phone number of the second individual is registered by the agent application installed in the computing device .

In operation the cloud server transmits upload information about the content requested from the mobile device to the computing device where the agent application is installed. Then the cloud server transmits print data of the content to the computing device .

According to an embodiment a print approval process of the computing device may exist between a point of time when the upload information is transmitted and a point of time when the print data is transmitted. For example the cloud server may transmit the print data of the content only when the computing device replied to the cloud server about a request to print the content after the upload information is transmitted. However according to an embodiment the print data may be transmitted immediately after the upload information is transmitted without a print approval process of the computing device . In other words operation S may be performed unlimitedly to any embodiment.

The cloud server provides a URL address for downloading the upload information and the print data to the computing device . Accordingly the network interface unit of the computing device connects to the URL address to receive the upload information and the print data from the cloud server .

The storage unit of the computing device stores the upload information and the print data received from the cloud server .

In operation the controller of the computing device determines the image forming apparatus assigned to the phone number of the second individual as the subject to print the content transmitted to the phone number of the second individual based on the lists of phone numbers and image forming apparatuses managed by the agent application .

In operation the network interface unit of the computing device transmits the print data of the content received from the cloud server to the image forming apparatus .

The controller of the computing device may transmit the print data via an FIFO method. When the transmitting of the print data is completed the controller of the computing device may control the storage unit to immediately delete the stored print data. However alternatively the controller of the computing device may control the storage unit to delete the stored image data after a predetermined period of time such that the image forming apparatus may re print the print data.

In operation the image forming apparatus prints the content by using the received print data thereby completing the phone number based cloud printing service requested to the phone number of the second individual .

As such when the computing device in which the agent application is installed is used the phone number based cloud printing service may be supported even by the image forming apparatus that is not capable of a direct network connection with the cloud server .

After the agent application is installed in the computing device the process of needs to be performed for the agent application to support a cloud printing service of the cloud server .

In operation the controller of the computing device executes the agent application . In operation the agent application may be executed for the first time after being installed in the computing device or after the registering of the use is initialized.

In operation the agent application obtains ID information of the computing device . The ID information of the computing device may be intrinsic information existing only in the computing device for example a medium access control MAC address or an internet protocol IP address. In other words the agent application obtains an MAC address by accessing system information of the computing device . The MAC address may be used as information for identifying the agent application on the cloud server . If a plurality of MAC addresses are assigned to the computing device the agent application may obtain all MAC addresses.

In operation the network interface unit of the computing device transmits the ID information for example the MAC address obtained by the agent application to the cloud server .

In operation the computing device and the cloud server perform authentication of the agent application .

According to an embodiment of the authentication of the agent application when a user already subscribed to the cloud printing service provided by the cloud server the user may input login information including a user account and a password to the agent application thereby performing the authentication.

According to another embodiment of the authentication of the agent application the user may input an authentication key issued from the cloud server to the agent application thereby performing the authentication.

Alternatively any one of various general methods for authenticating a use of commercial software may be applied to the authentication of the agent application .

In operation the cloud server completes the registering of the use of the agent application installed in the computing device . When the registering of the use is completed information about a list of phone numbers or image forming apparatuses to subscribe to a cloud printing service may be added to the agent application .

If an existing MAC address of the computing device is changed the process of may be performed again to register the use of the agent application .

Referring to the UI screens through of the agent application are screens displayed through the UI unit of the computing device . Since no phone number and no image forming apparatus are registered in the UI screen it may be assumed that the UI screen is a screen displayed immediately after the use of the agent application is registered as described above with reference to but embodiments are not limited thereto.

In it is assumed that the user of the computing device is the second individual i.e. Jane Kim but embodiments are not limited thereto.

The second individual activates a dialog for displaying a list of image forming apparatuses connectable to the computing device from the UI screen . Then the UI screen displays a list of image forming apparatuses addible to the agent application as the image forming apparatuses connectable to the computing device .

The second individual selects the image forming apparatus for example SCX 6401 n from the list of image forming apparatuses.

When the image forming apparatus is selected the second individual inputs the phone number for example 82 10 ABCD ABCD of the second individual on the UI screen and clicks a Register button.

After the image forming apparatus and the phone number of the second individual are input the UI screen displays registration information indicating that the phone number of the second individual is assigned to the image forming apparatus .

After the image forming apparatus and the phone number of the second individual are registered in the agent application the computing device transmits such registration information to the cloud server . The agent application may manage a list of image forming apparatuses by using a name of the image forming apparatus i.e. SCX 6401n .

Since the phone number 82 10 ABCD ABCD of the second individual and the image forming apparatus SCX 6401n are mapped by the agent application the cloud server may request the computing device where the agent application for controlling the image forming apparatus is installed for the cloud printing service when the cloud printing service is requested to the phone number of the second individual .

Referring to the agent application is registered as the system service on the OS installed in the computing device . Accordingly after the computing device is booted the agent application may be always executed regardless of login off of a user account. In other words when the computing device is booted and the OS starts to run the agent application may automatically start. Accordingly the user of the computing device may not have to inconveniently execute the agent application every time after logging in to the OS.

Information about lists of phone numbers and image forming apparatuses that are newly registered while using the agent application may be information processed after the login of the user account to the OS. However as described above the agent application may be executed regardless of the login off of the user account since the agent application corresponds to the system service. Accordingly information processed by the agent application executed before the login of the user account may be transmitted to the agent application executed after the login of the user account by using a PIPE communication method that does not have a limitation to user authority. Also the processes processed by the agent application may be stored in a partial region of the storage unit capable of being accessed by a system account of the OS installed in the computing device .

Ann agent management application for monitoring an operation state of the agent application may be executed as a system service together with the agent application . The agent management application is software pre installed in the storage unit like the agent application . The agent management application controls the agent application to be restored or re executed if the agent application does not normally operate.

In it is described that the agent application is executed as the system service but alternatively the agent application may be executed as a general commercial application executed after the login of the user account instead of as the system service. In other words a method of executing the agent application according to an embodiment is not limited.

In operation the user of the computing device inputs information about a phone number or an image forming apparatus to be registered in the agent application through the UI unit . For example the second individual Jane Kim may input 82 10 ABCD ABCD as the information about the phone number to be registered in the agent application and may input the image forming apparatus SCX 6410n as the information about the image forming apparatus to be registered in the agent application .

In operation the network interface unit of the computing device transmits the information about the phone number or the image forming apparatus which is registered in the agent application to the cloud server .

In operation the cloud server registers the information about the phone number or the image forming apparatus. Also the cloud server registers path information indicating that the information about the phone number or the image forming apparatus is managed by the agent application .

As such the cloud server manages the information about the phone number for example of the second individual Jane Kim the information about the image forming apparatus for example the image forming apparatus SCX 6401n and information about the agent application by linking them with each other.

Referring to the UI screen of the agent application phone numbers 82 10 AAAA BBBB and 82 10 CCCC DDDD of other individuals are already assigned to the image forming apparatus SCX 6401n .

When the second individual Jane Kim wants to add his her phone number 82 10 ABCD ABCD to the agent application the second individual inputs his her phone number to the UI screen and clicks an Add button.

As a result based on the UI screen the phone number 82 10 ABCD ABCD of the second individual is added and at the same time assigned to the image forming apparatus and registered in the agent application .

Information about the added phone number of the second individual is transmitted to the cloud server and also registered in the cloud server . In other words the cloud server updates pre registered information such that the phone numbers 82 10 AAAA BBBB 82 10 CCCC DDDD and 82 10 ABCD ABCD are assigned to the image forming apparatus by the agent application .

Referring to the UI screen of the agent application phone numbers 82 10 AAAA BBBB 82 10 CCCC DDDD and 82 10 ABCD ABCD of individuals are already assigned to the image forming apparatus SCX 6501n .

When the second individual Jane Kim wants to delete his her phone number 82 10 ABCD ABCD and the phone number 82 10 AAAA BBBB of the other individual from the agent application the second individual selects phone numbers to be deleted and clicks a Delete button on the UI screen .

As a result a pop up window inquiring whether to delete the selected phone numbers is displayed on the UI screen .

When the second individual clicks a Yes button in the pop up window the phone numbers 82 10 ABCD ABCD and 82 10 AAAA BBBB are deleted from the agent application .

Thus on the UI screen only the phone number 82 10 CCCC DDDD is assigned to the image forming apparatus .

Information about the deleted phone numbers is transmitted to the cloud server . In other words the cloud server updates pre registered information such that only the phone number 82 10 CCCC DDDD is assigned to the image forming apparatus by the agent application .

Referring to the UI screen of the agent application a phone number 82 10 CCCC DDDD is already assigned to the image forming apparatus SCX 6401n .

When the second individual Jane Kim wants to change information about the image forming apparatus from the agent application the second individual clicks a Set button on the UI screen .

When the second individual wants to change the name of the image forming apparatus i.e. SCX 6401n the second individual may input a new name Printer A and then click a Change button of the pop up window to change the name.

The second individual may click an Initialize button of the pop up window to delete and initialize the registration of the image forming apparatus from the agent application . For example the initializing of the image forming apparatus may be used to register image forming apparatuses other than the image forming apparatus in the agent application . Then a pop up window inquiring whether to initialize the registration of the image forming apparatus is displayed on the UI screen .

When the second individual clicks a Yes button on the pop up window the registration information of the image forming apparatus is deleted from the agent application as shown in the UI screen .

Information about the deleted image forming apparatus is transmitted to the cloud server . In other words the cloud server updates pre registered information such that there is no image forming apparatus managed by the agent application .

Referring to the UI screen of the agent application phone numbers 82 10 AAAA BBBB 82 10 CCCC DDDD and 82 10 ABCD ABCD of individuals are already assigned to the image forming apparatus SCX 6401n .

When the second individual Jane Kim wants to update information registered in the agent application the second individual clicks a Refresh button on the UI screen .

While an updating process is performed as shown in the UI screen the cloud server transmits information about lists of phone numbers and image forming apparatuses currently managed by the cloud server with respect to the agent application to the agent application .

As a result as shown in the UI screen a phone number 82 10 XXXX YYYY that is not registered in the agent application but registered only in the cloud server is newly added in the agent application . The phone number 82 10 XXXX YYYY may be registered in the cloud server by being assigned to the image forming apparatus SCX 6401n by another external device for example the mobile device of instead of the agent application installed in the computing device .

In the phone number 82 10 XXXX YYYY is added to the agent application by the cloud server but alternatively other various types of information such as a name of an image forming apparatus may be updated in the agent application by the cloud server .

Referring to image forming apparatuses that are connectable to the computing device from among image forming apparatuses through around the computing device are the image forming apparatus SCX 6401n and the image forming apparatus ML 2525m .

When the second individual Jane Kim wants to input information about the image forming apparatus to subscribe to the cloud printing service the agent application displays a UI screen for providing a list of image forming apparatuses connectable to the computing device . As described above since it is assumed that the image forming apparatuses and are connectable to the computing device in the UI screen may display a list of SCX 6401n and ML 2525m .

When the second individual wants to input the information about the image forming apparatus to subscribe to the cloud printing service the agent application may need to discover the image forming apparatuses connectable to the computing device .

Referring to the computing device executes a dialog box of a print management of an OS to check a printer queue thereby discovering the image forming apparatuses and SCX 6401n and ML 2525m connectable to the computing device based on printer drivers installed in the OS.

Referring to the computing device may execute a dialog box of print server properties of the OS to check a port list. As a result the computing device may discover that the image forming apparatuses and SCX 6401n and ML 2525m are connectable to the computing device .

Referring to the computing device may execute a dialog box of an automatic search for searching for peripheral apparatuses of the computing device thereby discovering the image forming apparatuses and SCX 6401 n and ML 2525m .

A list of the image forming apparatuses and SCX 6401n and ML 2525m discovered via discovering methods described above with reference to may be provided to the agent application and displayed to the second individual as shown in the UI screen of .

In operation the network interface unit of the computing device receives print data of a content from the cloud server if the content requested to a target phone number for example the phone number of the second individual i.e. Jane Kim subscribed to the cloud printing service is uploaded on the cloud server .

In operation the controller transmits the print data to the image forming apparatus assigned to the target phone number and controls the image forming apparatus to print the content.

According to an embodiment a cloud printing service may be interlocked linked coupled interworked interacted with a web storage service so that a user of the cloud printing service may store print data in a server of the web storage service that is personally used.

Generally a cloud printing server providing a cloud printing service temporarily stores print data only for a predetermined period of time required for a service provision. For example print data uploaded to the cloud printing server by a sender is automatically deleted if a recipient does not check or print the print data for a predetermined period of time for example 24 hours. Data is temporarily stored only for a predetermined period of time so as to increase flexibility of using resources which is a property of a cloud service while preventing expenses generated by obtaining a storage space.

However a user of the cloud printing service may want to store print data without a time limit. However a provider of the cloud printing service may feel burdened by expenses generated while providing storage spaces desired by users. Moreover even if the provider provides individual storage spaces to the users while enduring an increase of the expenses reliability of the storage spaces provided by the cloud printing service may be lower than that of a personal web storage service in terms of the users.

Accordingly one or more embodiments provide a method of interlocking a web storage service with a cloud printing service and storing the print data used in the cloud printing service in a web storage server as will now be described in detail with reference to .

First and second users and are users subscribed to the cloud printing service and a mobile application for using the cloud printing service in a mobile terminal is installed in the first and second mobile terminals and . The first and second users and subscribed to the cloud printing service respectively through phone numbers of the first and second mobile terminals and and each have a user account for the cloud printing service. Accordingly the user accounts of the first and second users and are mapped respectively to the phone numbers of the first and second mobile terminals and and are registered in the cloud printing server .

The second user is also a user subscribed to a web storage service and has a user account for the web storage service. The web storage service is a service providing a personal data storage space in a cloud server. In other words the second user may upload or download data by accessing the web storage server from any one of various devices such as a PC a laptop and a mobile terminal through the user account of the second user .

In an embodiment the second user may interlock the cloud printing service with the web storage service. In detail the cloud printing server may be interlocked with the web storage server with respect to the phone number of the second mobile terminal of the second user .

In order to interlock the cloud printing server with the web storage server with respect to the phone number of the second mobile terminal the second mobile terminal receives an access token from the web storage server and transmits the access token to the cloud printing server . The access token is an access token corresponding to the user account of the second user for the web storage service and is required to access the web storage server by using the user account of the second user .

The cloud printing server stores the access token after mapping the access token to the phone number of the second mobile terminal . The user account of the second user for the cloud printing service may also be mapped and stored together with the phone number. When the cloud printing server receives print data the cloud printing server may store the print data in the web storage server by using the access token.

When the first user uploads the print data destined for the phone number of the second mobile terminal in the cloud printing server the cloud printing server provides a cloud printing service with respect to the print data and stores the print data in the web storage server by using the access token.

The provided cloud printing service may be direct printing of the print data or may be a service that stores the print data for a predetermined period of time and notifies the second mobile terminal about the upload of the print data. In other words an assigned image forming apparatus may directly print the print data or the second user may check or print the uploaded print data through the mobile application of the cloud printing service in the second mobile terminal within the predetermined period of time from a point of time when the print data is uploaded.

A process of transmitting the print data to the second user will now be described in detail. The first user may transmit the print data to the second user by using the mobile application of the cloud printing service installed in the first mobile terminal . In detail when the print data destined for the phone number of the second mobile terminal is transmitted the print data is mapped to the phone number of the second mobile terminal and uploaded to the cloud printing server . Also the cloud printing server transmits a message notifying that the print data is uploaded to the second mobile terminal . The second user checks the message and may check or print the print data destined for the phone number of the second mobile terminal through the mobile application of the cloud printing service installed in the second mobile terminal .

According to one or more embodiments described above the print data uploaded to the cloud printing server is stored only for a predetermined period of time and is deleted after the predetermined period of time. However according to an embodiment the print data is stored in the web storage server without a time limit while being temporarily stored in the cloud printing server to provide the cloud printing service.

Upon receiving the print data the cloud printing server checks that the web storage server is interlocked with the cloud printing server for the phone number of the second mobile terminal that is a destination of the print data and stores the print data in the web storage server . At this time the access token mapped to the phone number of the second mobile terminal and stored in the cloud printing server is used. The cloud printing server requests the web storage server to store the print data by transmitting the access token to the web storage server .

Here since the access token corresponding to the user account of the second user is transmitted the print data is stored in a space of the web storage server which corresponds to the user account of the second user . Accordingly the second user may access the print data stored in the web storage server not only directly through the user account for the web storage service but also through the cloud printing service.

A process of accessing the print data stored in the web storage server through the cloud printing service will now be described in detail.

When the second user requests the cloud printing server to access print data and the print data is stored in the web storage server the cloud printing server may request the cloud printing server for the print data and receive the print data by using an access token that is pre stored. The cloud printing server may store metadata of the print data including a storage path of the print data for storing the print data in the web storage server in the cloud printing server . Accordingly it may be determined whether the print data is stored in the web storage server by checking the stored metadata.

When the second user requests the cloud printing server to print the print data stored in the web storage server the cloud printing server may render the print data by using the access token as described above and transmit the rendered print data to an image forming apparatus assigned by the second user . Alternatively when the second user requests for a preview the cloud printing server may transmit a preview of the print data to the second mobile terminal .

As described above the second user may directly access the print data stored in the web storage server without passing through the cloud printing server . In other words the second user may upload the print data directly to the web storage server and change the print data stored in the web storage server .

However when the second user uploads or changes the print data by directly accessing the web storage server the cloud printing server needs to be notified about such changes. Accordingly a synchronization folder that is synchronized with the cloud printing server may be managed in the web storage server . Print data stored in the web storage server through the cloud printing server is stored in the synchronization folder and if the second user directly accesses the web storage server to change data stored in the synchronization folder the cloud printing server may also recognize such a change.

Accordingly when the second user requests for a list of print data transmitted to the second user through the mobile application installed in the second mobile terminal the cloud printing server requests the web storage server for changes in the synchronization folder and transmits a list of updated print data to the second mobile terminal by reflecting the changes.

Such a synchronization folder may be newly created in the web storage server while interlocking the cloud printing service and the web storage service with each other or may be selected from folders pre stored in the web storage server .

Even when a web storage service is interlocked with respect to a phone number of a recipient print data may be stored in the web storage server or may be stored only in the cloud printing server like a general cloud printing service without being stored in the web storage server based on a selection of a sender. This is because the sender may not want some data to be stored in a personal storage space of a recipient.

In detail the first user transmits the print data destined for the phone number of the second mobile terminal through the mobile application installed in the first mobile terminal . The cloud printing server checks that the web storage service is interlocked with respect to the phone number of the second mobile terminal and requests the first mobile terminal to determine whether to store the print data in the web storage server . If the first user determines to store the print data in the web storage server from a selection request screen the print data is stored in the web storage server and if not the print data is temporarily stored in the cloud printing server only for a predetermined period of time.

Hereinabove an overall process of the method of interlocking a cloud printing service with a web storage service according to one or more embodiments has been described. Hereinafter processes of interlocking services transmitting print data reading and printing stored print data will be described in detail with reference to accompanying drawings.

When the web storage service to be interlocked is selected the second mobile terminal transmits a user account for the selected web storage service to the web storage server in operation . The user account transmitted to the web storage server may include a user ID and a password for the selected web storage service.

The user account may be pre stored in the second mobile terminal or may be directly input by a user when interlocking is requested. When the user account is pre stored in the second mobile terminal the mobile application may obtain the user account from an account administrator of the second mobile terminal . If there are a plurality of user accounts for the selected web storage service the mobile application may display the plurality of user accounts obtained from the account administrator on a screen for the user to select one of the user accounts. Then when the user selects one of the user accounts the selected user account is transmitted to the web storage server .

Upon receiving the user account for the web storage service the web storage server transmits an access token corresponding to the received user account to the second mobile terminal in operation . In operation the second mobile terminal transmits the received access token to the cloud printing server . In operation the cloud printing server stores the access token after mapping the access token to the phone number of the second mobile terminal . The stored access token is used when the cloud printing server stores print data in the web storage server or obtains print data stored in the web storage server .

Ann access token is generally valid only for a predetermined period of time after it is generated and cannot be used after its validity is expired. An access token having an expired validity needs to be renewed and at this time the access token may be automatically renewed or a valid access token may be newly issued. If the access token stored in the cloud printing server is capable of being automatically renewed the cloud printing server may renew the access token when the validity of the access token expires. However if a new valid access token needs to be issued the cloud printing server requests the second mobile terminal for the new valid access token when the validity of the access token expires. The second mobile terminal transmits the user account to the web storage server receives the new valid access token from the web storage server and transmits the new valid access token to the cloud printing server .

In a second UI screen when the user selects Google Drive the mobile application obtains a user account for the Google Drive which is stored in a mobile terminal. The mobile application may obtain the user account through an account administrator installed in the mobile terminal.

When only one user account is stored in the mobile terminal for the Google Drive the user account is immediately transmitted to the web storage server. However when a plurality of user accounts are stored in the mobile terminal for the Google Drive a screen for selecting a user account is displayed as shown in a third UI screen . The plurality of user accounts for Google Drive are displayed on a user account selecting window . A user touches a user account aceruky gmail.com to be used from the user account selecting window and touches an OK button.

As such when the web storage service and the user account are selected an icon indicating the interlocking is displayed in a region besides an item of Google Drive.

When the user inputs a name of the synchronization folder to an input box of a synchronization folder creating window the synchronization folder having the input name is created in a web storage server. Data stored in the web storage server through a cloud printing server is stored in the synchronization folder and changes of the data in the synchronization folder made by a direct access to the web storage server are transmitted to and updated in the cloud printing server.

A new synchronization folder may be created while interlocking the cloud printing service with the web storage service or one of folders pre stored in the web storage server may be selected as a synchronization folder.

Referring to in operation a mobile terminal transmits information about a user account for a web storage service to a web storage server. Then in operation the mobile terminal transfers an access token from the web storage server to a cloud printing server. Next in operation the cloud printing server stores the received access token after mapping the access token to a phone number of the mobile terminal.

Referring to in operation a mobile application of the cloud printing service installed in the mobile terminal activates a web storage interlocking function. In operation one of a plurality of user accounts for the web storage service which are stored in the mobile terminal is selected. When a synchronization folder to be interlocked with the web storage service is created in operation the mobile terminal transmits information about the created synchronization folder and information about the selected user account to the web storage server in operation . In other words when a name of the synchronization folder to be creased is input through the mobile application in operation the name of the synchronization folder is transmitted to the web storage server in operation . Then the web storage server creates the synchronization folder under the received name.

In operation the mobile terminal transfers an access token from the web storage server to the cloud printing server and in operation the cloud printing server stores the received access token after mapping the received access token to the phone number of the mobile terminal.

The cloud printing server checks a web storage setting of a recipient in operation . In other words the cloud printing server determines whether there is a web storage service interlocked with the phone number assigned to be a destination of the print data. The cloud printing server maps and stores an access token corresponding to the web storage service interlocked with the phone number. Accordingly the cloud printing server is able to determine whether the web storage service is interlocked with the phone number.

In operation when it is determined that the web storage service is interlocked with the phone number i.e. the recipient the first mobile terminal is requested to select whether to use the web storage service in operation . In other words a sender may select whether to store the transmitted print data in the web storage server . Based on the sender s selection the print data may be stored in the web storage server or may be temporarily stored only in the cloud printing server .

When the sender selects to use the web storage service in operation the first mobile terminal transmits a result of the selecting to the cloud printing server in operation . Upon receiving the result the cloud printing server transmits an access token pre stored correspondingly to the phone number and requests the web storage server to store the print data.

When the print data is stored in the web storage server the cloud printing server stores metadata of the print data in operation . In detail the cloud printing server may store a job ID of the print data the web storage service where the print data is stored and an URL of a storage path of the print data as the metadata of the print data.

Referring to a user may select a recipient to which print data is to be transmitted from a list of other users subscribed to a cloud printing service in a first UI screen . In a USER B is selected as the recipient.

When there is a web storage service interlocked with the USER B that is selected as the recipient a storage space selecting window is displayed as shown in a second UI screen . A message indicating that there is the web storage service interlocked with the USER B is displayed on the storage space selecting window and a menu for selecting whether to store print data in a personal web storage server of the USER B or only in a cloud printing server is displayed.

When the user selects to store the print data in the personal web storage server of the USER B from the storage space selecting window and touches a Transmit button the print data is stored in the personal web storage server through the cloud printing server according to processes described above.

When it is determined that the web storage service is interlocked with the predetermined phone number in operation a sender is requested to determine whether to use the web storage service in operation . It is determined whether the web storage service is selected to be used in operation and operation is performed if the web storage service is selected to be used. In operation the cloud printing server transmits an access token to a web storage server and requests the web storage server to store print data.

When it is determined that the web storage service is not interlocked with the predetermined phone number in operation or the web storage service is not selected to be used in operation operation is performed to temporarily store the print data in the cloud printing server.

Referring to when a user requests to read a list of print data by using the second mobile terminal in operation the second mobile terminal transmits a request for the list of print data to the cloud printing server in operation . Upon receiving the request the cloud printing server requests the web storage server to check changes in a synchronization folder in operation . When the web storage server transmits the changes to the cloud printing server in operation the cloud printing server updates the changes in operation .

When the cloud printing server transmits the list of print data with the updated changes to the second mobile terminal in operation the second mobile terminal displays the list of print data with the updated changes in operation .

Referring to upon receiving a request for a list of print data from a mobile terminal in operation a cloud printing server requests a web storage server to transmit changes of the print data stored in a synchronization folder and checks the changes in operation . The cloud printing server updates the changes of the list of print data in operation and transmits the list of print data with the updated changes to the mobile terminal in operation .

Referring to when a user requests to print print data stored in the web storage server by using the second mobile terminal in operation the second mobile terminal transmits a print request to the cloud printing server in operation .

In operation the cloud printing server checks a storage path of the print data by using pre stored metadata of the print data. When it is determined that the print data is stored in the web storage server the cloud printing server transmits a pre stored access token to the web storage server and requests the web storage server for the print data in operation . Then the web storage server transmits the print data to the cloud printing server in operation .

Upon receiving the print data from the web storage server the cloud printing server renders the print data in operation and transmits the rendered print data to an image forming apparatus in operation .

Referring to when a cloud printing server receives a request to print print data in operation the cloud printing server checks a storage path of the print data by using pre stored metadata in operation . In operation it is determined whether the print data is stored in a web storage server based on the checked storage path.

When it is determined that the print data is stored in the web storage server operation is performed to request for and receive the print data by transmitting an access token to the web storage server. When it is determined that the print data is not stored in the web storage server but is temporarily stored in the cloud printing server operation is performed to extract the print data stored in the cloud printing server.

Then the cloud printing server renders the print data in operation and transmits the rendered print data to an image forming apparatus in operation .

The communication interface unit communication interface is used to communicate with an external mobile terminal or a web storage server and may be a network module capable of wired and wireless communication.

The storage unit storage may be realized in any one of various types of storage medium. In detail the interlocking information storage unit may store interlocking information required for interlocking with a web storage service. In detail the interlocking information storage unit may store an access token for accessing an interlocked web storage service and an interlocked web storage server after mapping the access token to a phone number subscribed to a cloud printing service.

The metadata storage unit may store metadata about print data stored in the web storage server. In detail the metadata storage unit may store a job ID the web storage service and a URL of a storage path after mapping them to print data stored in the web storage server.

The temporary storage unit temporarily stores print data for providing the cloud printing service only for a predetermined period of time.

The controller controls operations of other components. In detail when print data destined for a phone number interlocked with the web storage service is received the controller provides the cloud printing service for the print data and stores the print data in the web storage server by using the interlocking information stored in the storage unit .

The synchronization manager manages synchronization of the print data stored in the web storage server.

According to an embodiment even when a sender transmits a content to be printed together with a direct printing command a recipient may print the content by using an image forming apparatus at a point of time the recipient wants to print the content.

Generally when a sender transmits a content to be printed together with a direct printing command from a cloud printing service provided by a cloud server the content is directly transmitted to an image forming apparatus to print the content. Thus a recipient is unable to choose a point of time the recipient wants to print the content.

Accordingly one or more embodiments provide a method of printing a content to be printed at a point of time a recipient wants to print the content even when a sender transmits the content together with a direct printing command. Such a method will now be described in detail with reference to .

Referring to a sender wants to immediately print a content to be printed in an image forming apparatus by transmitting the content.

The sender transmits a direct printing command and the content which are destined for the image forming apparatus to a cloud server by using a user device . A direct printing command is a command for transmitting a content to be printed to a destination through a cloud server to be immediately printed without storing the content in the cloud server.

Upon receiving the direct printing command and the content the cloud server analyzes the direct printing command and transmits the content to the image forming apparatus . When the content is received the image forming apparatus prints the content. Since the content is immediately printed by the image forming apparatus a point of time when the content is to be printed is unable to be determined.

In detail in a phone number based cloud printing system a sender transmits a content to be printed and a print command which are destined for a phone number to the cloud server and the cloud server checks the phone number and transmits the content to the image forming apparatus corresponding to the phone number. When a direct printing command is not transmitted with the content the cloud server may store the content correspondingly to the phone number a recipient may check and print the content after requesting for a preview of the content at a point of time the recipient wants to print the content by using a device that was mapped to correspond to the phone number in a mobile terminal having the phone number or in the cloud server and the cloud server may transmit the content to the image forming apparatus corresponding to the phone number such that the image forming apparatus prints the content.

On the other hand when a direct printing command is transmitted together with the content the cloud server immediately transmits the content to the image forming apparatus corresponding to the cloud server and thus a recipient is unable to print the content at a point of time the recipient wants to print the content.

Referring to the cloud server according to an embodiment receives print data and a direct printing command which are destined for a predetermined phone number determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number and when the direct printing is performable enables an image forming apparatus corresponding to the predetermined phone number to print the print data. On the other hand when the direct printing is not performable the print data is stored in the cloud server correspondingly to the predetermined phone number. Then upon receiving a preview request of the stored print data the cloud server transmits preview data of the stored print data to a user device and upon receiving a print request of the preview data the cloud server transmits the print data to the image forming apparatus corresponding to the predetermined phone number so that the image forming apparatus prints the print data.

Referring to the cloud server includes a network interface unit network interface an option setter a determiner a storage unit and a controller .

The network interface unit receives the print data and the direct printing command which are destined for the predetermined phone number. Also the network interface unit transmits the print data to the image forming apparatus corresponding to the predetermined phone number.

The option setter sets options for performing direct printing. In detail the option setter may pre set a time slot for direct printing with respect to the predetermined phone number or a sender allowing direct printing as options.

The determiner determines whether the direct printing is performable by checking the options pre set with respect to the predetermined phone number. The determiner may determine whether the direct printing is performable based on a time when the direct printing command is received. Alternatively the determiner may determine whether the direct printing is performable based on a user who transmitted the direct printing.

The storage unit stores the predetermined phone number the print data and the options. The storage unit may store the print data and the options to correspond to the predetermined phone number.

When it is determined that the direct printing is performable the controller controls the image forming apparatus corresponding to the predetermined phone number to print the print data and when it is determined that the direct printing is not performable the controller controls the storage unit to store the print data in the cloud server correspondingly to the predetermined phone number. The controller controls the storage unit to store the options set by the option setter . The set options may be stored correspondingly to the predetermined phone number.

The controller may control the network interface unit to receive the preview request of the print data from the user device and upon receiving the preview request to transmit the preview data of the print data to the user device. The controller may control the network interface unit to receive the print request of the preview data. The controller may control the image forming apparatus corresponding to the predetermined phone number to print the print data according to the print request of the preview data.

The cloud printing system according to an embodiment receives options for performing direct printing from the user device and transmits the option to the cloud server such that the cloud server sets the options. Upon receiving the options for performing direct printing the cloud server sets and stores the options.

Referring to the user device includes a user input receiver a network interface unit and a controller .

The user input receiver receives a user input. For example the user device may be a mobile terminal and may receive various touch inputs through a touch panel of the mobile terminal. In detail the user input receiver may receive the options for performing direct printing.

The network interface unit may transmit the options to the cloud server so that the cloud server sets the options. Also the network interface unit may receive the options set by the cloud server from the cloud server . A user may check the options set in the cloud server through a display unit not shown and change the set options. The display unit may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display a plasma display panel PDP a cathode ray tube CRT display and the like for example. However the disclosure is not so limited thereto and may include other types of displays.

The controller may control the user input receiver to receive the options for performing direct printing and control the network interface unit network interface to transmit the options to the cloud server . The controller may control the network interface unit to receive the options from the cloud server . When the cloud server is requested to transmit the set options the controller may receive the set options in response.

Referring to the cloud server includes the network interface unit the option setter the storage unit storage and the controller .

The network interface unit receives the options. The network interface unit network interface may transmit the options set by the option setter to the user device .

The storage unit stores the options. The options may be stored to correspond to the predetermined phone number. The predetermined phone number may be a phone number of the user device that is the mobile terminal.

The controller may control the network interface unit to receive the options from the user device . The controller may control the option setter to set the options and control the storage unit storage to store the received options. The controller may control the network interface unit to transmit the options set by the option setter to the user device . The controller may control the network interface unit to receive a request for the options from the user device and transmit the options to the user device in response.

Referring to the cloud server receives print data and a direct printing command which are destined for a predetermined phone number determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number and when it is determined that the direct printing is performable transmits the print data to the image forming apparatus corresponding to the predetermined phone number. The image forming apparatus may receive the print data and print the received print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in a server correspondingly to the predetermined phone number. Then when a print request of the print data is received the cloud server transmits the print data to the image forming apparatus corresponding to the predetermined phone number. The image forming apparatus may receive and print the print data.

Since the cloud server of performs functions of the cloud server of details thereof are not repeated here.

The image forming apparatus includes a network interface unit network interface a print operation performer and a controller .

The network interface unit receives the print data. The print operation performer performs a print operation on the print data. The controller may control the network interface unit to receive the print data from the cloud server and control the print operation performer to print the received print data.

Referring to since the cloud server and the image forming apparatus of performs functions of the cloud server and the image forming apparatus of details thereof are not repeated here.

Referring to the cloud printing system includes the user device . The user device includes the user input receiver the network interface unit network interface and the controller .

The network interface unit transmits a preview request of print data stored in the cloud server . Also the network interface unit receives preview data regarding the preview request. The preview data is data for a user to preview a content included in the print data. The preview data only include a part of the print data.

The user device may include a display unit not shown and the display unit may display the content included in the preview data. The user may check the content included in the preview data through the display unit. The display unit display may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display a plasma display panel PDP a cathode ray tube CRT display and the like for example. However the disclosure is not so limited thereto and may include other types of displays.

The user input receiver receives various user inputs from the user. The user input receiver may receive a print request of the preview data. In other words the user may check the content included in the preview data through the display unit and request the image forming apparatus to print the content included in the print data.

The controller may control the user input receiver to receive the preview request and control the network interface unit to transmit the preview request to the cloud server .

Upon receiving the preview request from the user device the controller of the cloud server controls the network interface unit network interface of the cloud server to transmit the preview data of the print data to the user device .

Upon receiving the print request of the preview data from the user input receiver the controller of the user device may control the network interface unit of the user device to transmit the print request to the cloud server .

Upon receiving the print request from the user device the controller of the cloud server may control the network interface unit to transmit the print data to the image forming apparatus .

Referring to in operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number.

When it is determined that the direct printing is performable the cloud server may enable the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server may transmit the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server to correspond to the predetermined phone number in operation S.

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable based on a time when the direct printing command is received. In detail the cloud server may pre set a time slot when the direct printing is performable as an option and determine whether the direct printing is performable by checking whether the time when the direct printing command is received is included in the time slot.

When it is determined that the direct printing is performable the cloud server enables the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server transmits the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server correspondingly to the predetermined phone number.

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable based on a user who transmitted the direct printing command. In detail the cloud server may pre set a sender who is allowed to perform direct printing as an option and determine whether the direct printing is performable by checking the sender and the user who transmits the direct printing command.

When it is determined that the direct printing is performable the cloud server enables the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server may transmit the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server correspondingly to the predetermined phone number in operation S.

In operation S the cloud server pre sets and stores a time slot when direct printing is performable or a sender who is allowed to perform direct printing as options.

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether the direct printing is performable by checking options pre set with respect to the predetermined phone number.

When it is determined that the direct printing is performable the cloud server enables the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server may transmit the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server correspondingly to the predetermined phone number in operation S.

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number.

When it is determined that the direct printing is performable the cloud server enables the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server may transmit the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server may store the print data in the cloud server correspondingly to the predetermined phone number.

In operation S the cloud server receives a preview request of the stored print data from the user device .

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number.

When it is determined that the direct printing is performable the cloud server enables the image forming apparatus corresponding to the predetermined phone number to print the print data in operation S. In detail the cloud server transmits the print data to the image forming apparatus so that the image forming apparatus prints the print data.

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server correspondingly to the predetermined phone number.

In operation S the cloud server receives a preview request of the stored print data from the user device .

In operation S the cloud server transmits the print data to the image forming apparatus corresponding to the predetermined phone number.

In operation S the cloud server receives print data and a direct printing command which are destined for a predetermined phone number.

In operation S the cloud server determines whether direct printing is performable by checking options pre set with respect to the predetermined phone number. A user may pre set options for performing direct printing by using the user device . The cloud server may receive the pre set options from the user device and set options in the cloud server .

When it is determined that the direct printing is not performable the cloud server stores the print data in the cloud server correspondingly to the predetermined phone number in operation S.

When it is determined that the direct printing is performable the cloud server transmits the print data to the image forming apparatus corresponding to the predetermined phone number in operation S.

Referring to a user receives the HTTP packet about the set options from http xx.xx.xx.xx pp settings that is an address of the cloud server by using the user device . The HTTP packet is a packet received by the user device in response to a request transmitted to the cloud server by the user to check the options currently set in the cloud server .

The HTTP packet includes details about the options currently set in the cloud server . In detail the HTTP packet includes options about whether direct printing is performable. An option portion includes details about phoneNumber and time . In detail phoneNumber denotes a phone number of a sender who is allowed to perform direct printing. time denotes a time slot when direct printing is allowed. For example a phoneNumber portion of the option portion includes 01012345678 01023456789 and 01034567890 which denotes that direct printing is performable only on print data transmitted from senders using phone numbers of 01012345678 01023456789 and 01034567890 . Also a time portion of the option portion includes 0000 0000 1000 1200 1000 1200 1000 1200 1000 1200 1000 1200 and 0000 0000 which denotes that direct printing is performable only on print data received from 00 00 to 00 00 on Monday from 10 00 to 12 00 on Tuesday from 10 00 to 12 00 on Wednesday from 10 00 to 12 00 on Thursday from 10 00 to 12 00 on Friday from 10 00 to 12 00 on Saturday and from 00 00 to 12 00 on Sunday.

Referring to a user transmits the HTTP packet that is a request packet for setting options to http xx.xx.xx.xx transmit pp that is an address of the cloud server by using the user device .

The HTTP packet includes details about options currently set in the cloud server . In detail the HTTP packet includes options about whether direct printing is performable.

An allowed time portion is a portion for setting an option regarding a time slot when direct printing is performable. For example in an embodiment an option is set such that direct printing is performable from 00 00 to 00 00 on Monday from 10 00 to 12 00 on Tuesday from 10 00 to 12 00 on Wednesday from 10 00 to 12 00 on Thursday from 10 00 to 12 00 on Friday from 10 00 to 12 00 on Saturday and from 00 00 to 00 00 on Sunday.

An allowed sender portion is a portion for setting an option regarding a sender who is allowed to perform direct printing. For example in an embodiment an option is set such that direct printing is performable only on print data transmitted by senders using phone numbers of 010 1234 5678 010 2345 6789 and 010 3456 7890 .

Referring to a user selects Settings and selects Personalized Printing from a screen displayed on the user device . Referring to after selecting the Personalized Printing the user is able to select whether to activate options via a toggle button by turning on or off the toggle button . Referring to when the user selects ON the user may select a time slot and a day for allowing direct printing. The user is able to select a start time and a end time according to days by using a time picker. Then when the user touches NEXT the user is able to set a time slot when direct printing is performable. The options set as such are transmitted to the cloud server and the cloud server sets the received options.

Referring to a user sets a sender who is allowed to perform direct printing from a screen displayed by using the user device . When a list of phone numbers stored in the user device is displayed by calling the list the user may select a sender who is allowed to perform direct printing. The user may use a toggle button to determine whether direct printing is allowed according to each sender. When the user selects DONE after setting the sender who is allowed to perform direct printing direct printing may be performed only on print data transmitted by the set sender. Options set as such are transmitted to the cloud server and the options are set in the cloud server . Referring to when the user selects EVERYONE direct printing may be allowed to all senders in the list of phone numbers stored in the user device .

Referring to when the options are successfully set and stored in the cloud server a message notifying the success may be displayed on the user device .

Referring to the cloud server stores options in a form of a table and may manage the options about whether direct printing is performable through the table.

In an embodiment it is assumed that options are set for a user having a phone number 010 AAAA BBBB . The options may be stored in forms of tables such as an enable table an allowed time table and an allowed sender table correspondingly to the phone number 010 AAAA BBBB .

The enable table is a table for determining whether personalized printing is to be activated and may have a value of TRUE or FALSE .

The allowed time table is a table about a time slot when direct printing is allowed and may be used to set days and time slots. Alternatively the allowed time table may be used to set dates.

The allowed sender table is a table about a sender who is allowed to perform direct printing and may be used to set a phone number of the sender. The allowed sender table may store additional information such as an IP address a serial number and a location together with the phone number of the sender.

Embodiments are not limited thereto and the options about whether direct printing is performable may be stored and managed in various forms of tables.

In operation S the cloud server receives a direct print job. The direct print job may include a direct printing command and print data.

In operation S the cloud server determines whether personalized print options are activated. The personalized print options are options about whether direct printing corresponding to a predetermined phone number is performable.

When it is determined that the personalized print options are activated the cloud server determines whether a time when the direct print operation is received is within a set time in operation S.

When it is determined that the time is not within the set time the cloud server performs pull printing in operation S. The pull printing is an operation for storing a print job in the cloud server and transmitting and printing print data to and in the image forming apparatus when a user requests the cloud server to print the print data. Direct printing is an operation for transmitting and printing print data to and in the image forming apparatus without storing the print data in the cloud server .

In operation S when it is determined that the time is within the set time the cloud server determines whether a user who transmitted the direct print operation is a sender who is allowed to perform direct printing.

When the user is determined to be the sender who is allowed to perform direct printing the cloud server may perform direct printing in operation S. In detail the cloud server transmits the print data to the image forming apparatus so that the image forming apparatus prints the print data.

According to an embodiment even when a sender transmits a direct printing command and print data whether to perform direct printing may be determined based on options pre set by a recipient and thus direct printing may be performed only when the recipient wants and pull printing may be performed otherwise.

For example the recipient may set a time slot when direct printing is performable so as to avoid printing noise during a personal time such as a bedtime. Also the recipient may store print data in the cloud server if required so that the print data is printed only after the recipient checks the print data through the user device .

A phone number based printing service may be requested by a sender not only through a mobile device such as a mobile phone but also through a sender device such as an image forming apparatus. It is easy to input a phone number of a recipient who is to receive a print job to a mobile device such as a mobile phone by using an address book but a sender has to directly input a phone number of a recipient in a sender device such as an image forming apparatus. Hereinafter requesting of a phone number based printing service from an image forming apparatus will be described in detail with reference to .

Referring to sender devices i.e. the image forming apparatus and a mobile device are on the left of a cloud server and recipient devices i.e. an image forming apparatus and a mobile device are on the right of the cloud server . A sender who is to transmit a print job may register the print job in the cloud server by using the sender devices and a recipient who is to receive the print job may receive the print job from the cloud server by using the recipient devices and perform the print job. The sender devices on the left of the cloud server may be the image forming apparatus that requests for a phone number based printing service and the mobile device communicable with the image forming apparatus .

The image forming apparatus requesting for a phone number based printing service may generate a print job and transmit the print job to the cloud server so as to transmit the print job to a recipient by using a phone number of the recipient. In other words when the image forming apparatus requests for a printing service using the phone number of the recipient the phone number of the recipient and the print job may be transmitted to and registered in the cloud server .

In order to request for a phone number based printing service the image forming apparatus needs to receive the phone number of the recipient from a user. If the user knows the phone number of the recipient the user may directly input the phone number of the percipient to the image forming apparatus . However if the user does not know the phone number of the recipient the phone number of the recipient may be obtained from the mobile device of the user or the cloud server . Hereinafter embodiments of easily inputting the phone number of the recipient from the image forming apparatus requesting for a phone number based printing service will be described with reference to .

Referring to the image forming apparatus may include an application executer a user interface UI unit a communication unit communicator a controller and a storage unit storage . The image forming apparatus of may further include other general purpose components. For example the image forming apparatus may further include a scanner that generates scan image data by scanning a document or an image former that forms an image on a printing paper.

The application executer may execute an application for inputting a print job request and a phone number of a recipient. For example the application executer may execute a scan to phone application for registering scan image data obtained by scanning a document in the cloud server together with the phone number of the recipient. In another example the application executer may execute a box to phone application for registering a print job stored in the image forming apparatus in the cloud server together with the phone number of the recipient.

The UI unit may adaptably display a UI of an application executed according to a user input. For example the UI unit may display a list of print jobs or a preview of a print job when a user selects a screen for inputting a print job. In another example the UI unit may display a message requesting the user to input the phone number of the recipient when the user selects a screen for inputting the phone number of the recipient.

Alternatively the UI unit may adaptively display a UI by reflecting received external information. For example the UI unit may reflect and display received external recipient information or an address book of an external device on the screen for inputting the phone number of the recipient. This will be described in detail later with reference to .

The communication unit communicator may receive information from an external device or transmit information to an external device. For example the communication unit may receive recipient information including the phone number of the recipient from the mobile device . In another example the communication unit may request the cloud server supporting a phone number based printing service for a server address book and receive the server address book from the cloud server in response.

The communication unit may support various types of communication method such as Wi Fi Direct Bluetooth Zigbee infrared data association IrDA and near field communication NFC . The user may select a communication method by overall considering a state a data amount etc of a device that is to communicate with the image forming apparatus . Alternatively the communication unit may perform communication according to a pre set communication method.

The controller may control the image forming apparatus in general. The controller is able to control components of the image forming apparatus .

For example the controller may control the image forming apparatus such that the recipient information received from the mobile device is automatically input on the screen for inputting the phone number of the recipient. In detail the controller may control the UI unit such that a name and the phone number of the recipient are matched and automatically input to the screen for inputting the phone number of the recipient based on the recipient information received while displaying the screen for inputting the phone number of the recipient. The recipient information may further include at least one of an email address of the recipient and information about a group to which the recipient belongs as well as the name and the phone number of the recipient and the controller may further display the at least one of them on the screen.

Also the controller may control the phone number of the recipient included in the recipient information and the print job to be transmitted to the cloud server supporting a phone number based printing service based on a print job request of the user.

In another example the controller control the UI unit to display the server address book received from the cloud server on the screen for inputting the phone number of the recipient and to receive a selection on a recipient from the displayed server address book. In detail the controller may control the UI unit to match the name and the phone number of the recipient and display the name and the phone number based on the server address book received while displaying the screen for inputting the phone number of the recipient. The server address book may further include at least one of an email address of the recipient and information about a group to which the recipient belongs as well as the name and the phone number of the recipient and the controller may further display the at least one of them.

Also the controller may control the phone number and a print job to be transmitted to the cloud server supporting a phone number based printing service based on the print job request of the user.

The storage unit may store information and programs required for operations of the image forming apparatus and data generated according to the operations of the image forming apparatus . For example the storage unit may store the recipient information received from the mobile device in the address book of the image forming apparatus to update the address book. Alternatively the storage unit may store the server address book received from the cloud server in the address book of the image forming apparatus to update the address book.

When the image forming apparatus includes a scanner not shown the storage unit may store scan image data generated by the scanner and store the scan image data in a form of a print job list by listing the scan image data print job. The storage unit may store print jobs received from an external device. The storage unit may also store the received print jobs in a form of a print job list by listing the received print jobs.

In order to update the server address book of the cloud server the controller may transmit the address book that is updated by storing the recipient information received from the mobile device to the cloud server . Also in order to update a mobile address book of the mobile device the controller may transmit the address book that is updated by storing the server address book received from the cloud server to the mobile device . The updated address book is transmitted so as to synchronize address books of devices supporting a phone number based printing service such as the image forming apparatus the mobile device and the cloud server .

The image forming apparatus may execute an application for inputting a print job request and a phone number of a recipient in operation S. In other words a user may execute an application capable of performing a print job desired by the user from among menus of applications displayed on the UI unit of the image forming apparatus . It is assumed that a scan to phone application is executed.

The image forming apparatus may adaptively display a UI of the application executed by the user in operation S. For example when the user selects a screen for inputting a print job from the displayed UI the image forming apparatus may display a list of existing scan image data or display a preview of scan image data of a currently scanned document. In another example when the user selects a screen for inputting a phone number of a recipient the image forming apparatus may display a message requesting the user to input the phone number of the recipient.

When the message requesting the user to input the phone number of the recipient is displayed the user may directly input the phone number by using a keypad or other user interface. However if the user does not know the phone number or needs to input several phone numbers the user may easily input the phone number by transmitting recipient information including phone numbers of recipients to the image forming apparatus by using the mobile device . Hereinafter it is assumed that the user transmits the recipient information by using the mobile device .

The mobile device may execute an application for selecting and transmitting user information including a phone number to an external device in operation S. For example the mobile device may execute an application supporting a phone number based printing service or an application for selecting user information by searching an address book of the mobile device .

The mobile device displays a mobile address book and the user may select a recipient from the mobile address book in operation S. In other words the user may check the recipient to which a print job is to be transmitted from the mobile address book and select recipient information including a phone number of the recipient.

The mobile device may transmit the recipient information selected from the mobile address book to the image forming apparatus . In other words the image forming apparatus may receive the recipient information including the phone number of the recipient from the mobile device in operation S.

The image forming apparatus may automatically input the recipient information received from the mobile device to the screen for inputting the phone number of the recipient in operation S. Accordingly the user is able to check the recipient information selected by the mobile device through the UI unit of the image forming apparatus .

Based on the print job request of the user the image forming apparatus may transmit the phone number of the recipient included in the recipient information and a requested print job to the cloud server supporting a phone number based printing service in operation S. In other words the cloud server may receive the phone number of the recipient and the requested print job from the image forming apparatus . The cloud server may match and store the phone number of the recipient and the requested print job.

The image forming apparatus may store the recipient information received from the mobile device in an address book in operation S so as to update the address book of the image forming apparatus . Then when the user wants to transmit a print job to the same recipient the user may use the updated address book of the image forming apparatus .

The image forming apparatus may transmit the updated address book to the cloud server in operation S. In other words the cloud server may receive the updated address book of the image forming apparatus from the image forming apparatus .

The cloud server may update a server address book in operation S by using the updated address book of the image forming apparatus received from the image forming apparatus . As such the address book of the image forming apparatus and the server address book of the cloud server may be synchronized with each other.

The image forming apparatus may store log data of a print job in operation S. The cloud server may store log data under the name of the recipient with respect to the received print job. Accordingly the recipient of the received print job may be easily determined based on the log data.

A user i.e. a sender may select the recipient who is to receive a print job from the mobile address book of the mobile device . If the user is unable to remember a phone number of the recipient or there are several recipients the user may use phone numbers of recipients stored in the mobile device .

Referring to the mobile address book is displayed on the UI of the mobile device . Such a mobile address book may be displayed on the UI by executing an application supporting a phone number based printing service or an application for selecting user information by searching the mobile address book of the mobile device .

The user i.e. the sender may select the recipient who is to receive the print job from the mobile address book displayed on the UI of the mobile device . As shown in the user may scroll the mobile address book to search for desired recipient information and select a check box to select the recipient. The user may select at least one recipient and touch a Complete button to compete the selecting of the recipient.

When the selecting of the recipient is completed the mobile device may transmit the recipient information to the image forming apparatus according to a pre set communication method. If a communication method or an image forming apparatus is not pre set the mobile device may display a pop up for selecting a communication method or an image forming apparatus to which the recipient information is to be transmitted so as to induce the user to select a communication method or an image forming apparatus. For example the mobile device may display a pop up of various types of communication methods such as Wi Fi Direct Bluetooth Zigbee infrared data association IrDA and NFC and a plurality of image forming apparatuses registered in the mobile device for the user to select. When the communication method and the image forming apparatus are selected the mobile device may transmit the recipient information to the image forming apparatus .

The UI of the image forming apparatus at the right top of is displayed when a user selects the screen for inputting the phone number of the recipient. An address book region may be displayed in a partial region of the UI of the image forming apparatus . When user information is registered in an address book of the image forming apparatus the image forming apparatus may display the registered user information in the address book region . When user information is not registered in the address book of the image forming apparatus the image forming apparatus may display a message requesting the user to input a phone number of a recipient. The user may directly input the phone number of the recipient by using a keypad located below the address book region or other user interface. When it is difficult for the user to directly input the phone number of the recipient the user may transmit recipient information including the phone number of the recipient to the image forming apparatus by using the mobile device as described above with reference to .

When the user selected the recipient information from the UI of the mobile device and transmitted the selected recipient information to the image forming apparatus the UI of the image forming apparatus at the right top of may be displayed as the UI of the image forming apparatus at the right bottom of . In other words the recipient information selected from the UI of the mobile device may be automatically input to the screen for inputting the phone number of the recipient in the UI of the image forming apparatus and displayed to the user. As shown in the recipient information transmitted from the mobile device may be temporarily automatically input to the address book of the image forming apparatus . After the recipient is selected the user may touch a Send button on the UI of the image forming apparatus to request for a print job. Accordingly the image forming apparatus may generate scan image data and transmit the scan image data to the cloud server together with the phone number of the recipient.

However when a phone number of a recipient and a print job are transmitted based on a print job request of the user the address book of the image forming apparatus may be pre set to be automatically updated so as to skip the displaying of the pop up window of .

In recipient information received from the mobile device is stored in an address book of the image forming apparatus by selecting Individual as a category.

Referring to a name a phone number and an email address of a recipient are input in the sated order and the phone number replaced a fax number in the address book. However alternatively a phone number field may be separately provided to store the phone number.

In recipient information received from the mobile device is stored in an address book of the image forming apparatus by selecting Group as a category.

Referring to information about a group included in the recipient information is Company and total three people are in the group.

In recipient information received from the mobile device is stored in an address book of the image forming apparatus by selecting Any as a category.

Referring to names and phone numbers of recipients are stored in the address book of the image forming apparatus and in detail there is a phone number field for storing the phone numbers.

The image forming apparatus may execute an application for inputting a request for a print job and a phone number of a recipient in operation S. In other words a user may execute an application for performing a print job desired by the user from among menus of applications displayed on the UI unit of the image forming apparatus . Hereinafter for convenience of description it is assumed that a scan to phone application is executed.

The image forming apparatus may adaptively display a UI of the executed application in operation S. For example when the user selects a screen for inputting a print job from the displayed UI the image forming apparatus may display a list of existing scan image data or display a preview of scan image data of a currently scanned document. In another example when the user selects a screen for inputting a phone number of a recipient the image forming apparatus may display a message requesting for a phone number of a recipient.

When the message requesting for a phone number of a recipient is displayed the user may directly input the phone number by using a keypad or other user interface. However if the user does not remember the phone number or has to input several phone numbers the user may use the cloud server .

The image forming apparatus may request the cloud server for the server address book in operation S. In response the image forming apparatus may receive the server address book from the cloud server in operation S.

The image forming apparatus may display the server address book received from the cloud server on the screen for inputting a phone number of a recipient in operation S.

The user may select a recipient from the server address book displayed on the image forming apparatus thereby easily inputting a phone number of a recipient in operation S.

Based on the request for a print job the image forming apparatus may transmit a phone number of the selected recipient and the requested print job to the cloud server supporting a phone number based printing service in operation S. In other words the cloud server may receive the phone number and the requested print job from the image forming apparatus . The cloud server may match and store the phone number and the requested print job.

The image forming apparatus may store the server address book received from the cloud server in an address book in operation S so as to update the address book of the image forming apparatus . Then when a print job is to be transmitted to the same recipient later the updated address book of the image forming apparatus may be used.

The image forming apparatus may transmit the updated address book to the mobile device in operation S. In other words the mobile device may receive the updated address book of the image forming apparatus from the image forming apparatus .

The mobile device may update a mobile address book by using the updated address book received from the image forming apparatus in operation S thereby synchronizing the address book of the image forming apparatus and the mobile address book of the mobile device .

The image forming apparatus may store log data of the print job in operation S. The log data of the print job transmitted to the cloud server may be stored under a name of the recipient.

As described with reference to operation S of the image forming apparatus may request the cloud server for the server address book. Accordingly the image forming apparatus may perform an operation of pre setting information about the cloud server .

Referring to the image forming apparatus may display a UI for pre setting the information about the cloud server or may amend the information about the cloud server according to a user input.

The UI of the image forming apparatus at the left top of is displayed when the user of the image forming apparatus selects a screen for inputting a phone number of a recipient. The address book region may be displayed on a partial region of the UI of the image forming apparatus . When there is user information registered in the address book of the image forming apparatus the image forming apparatus may display the registered user information on the address book region . However when there is no user information registered in the address book of the image forming apparatus the image forming apparatus may display a message requesting for a phone number of a recipient. At this time the user may directly input the phone number by using a keypad or other user face below the address book region . If it is difficult for the user to directly input the phone number the image forming apparatus may receive the server address book from the cloud server .

The user may request the cloud server that is pre set to be connected to the image forming apparatus for the server address book through the UI of the image forming apparatus . When the user touches a button requesting for a phone number on the UI the image forming apparatus may request the cloud server for the server address book.

When the cloud server transmitted the server address book to the image forming apparatus the UI at the left top of may be displayed as the UI at the left bottom of . In other words the server address book received from the cloud server may be displayed on the screen for inputting a phone number of a recipient. As shown in the server address book received from the cloud server may be displayed on the address book of the image forming apparatus . The user may check a check box from the server address book to select a recipient who is to receive a print job and touch a Send button on the UI of the image forming apparatus thereby requesting for the print job. Accordingly the image forming apparatus may generate scan image data and transmit the scan image data to the cloud server together with a phone number of the selected recipient.

First in operation S the image forming apparatus may execute an application for inputting a request for a print job and a phone number of a recipient.

In operation S the image forming apparatus may adaptively display a UI of the executed application based on a user input. When a user selects a screen for inputting a print job the image forming apparatus displays a list of print jobs or displays a preview of a print job and when the user selects a screen for inputting a phone number of a recipient the image forming apparatus may display a message requesting for the phone number of the recipient.

In operation S the image forming apparatus may receive recipient information including the phone number of the recipient from a mobile device and automatically input the recipient information to the screen for inputting the phone number. The image forming apparatus may match and automatically input a name and the phone number of the recipient based on the recipient information received while displaying the screen for inputting the phone number of the recipient. The recipient information may further include at least one of an email address of the recipient and information about a group to which the recipient belongs.

In operation S the image forming apparatus may transmit the phone number included in the recipient information and the requested print job to a cloud server supporting a phone number based printing service based on the request for the print job.

First in operation S the image forming apparatus may execute an application for inputting a request for a print job and a phone number of a recipient.

In operation S the image forming apparatus may adaptively display a UI of the executed application based on a user input. The image forming apparatus may display a list of print jobs or display a preview of a print job when the user selects a screen for inputting a phone number of a recipient.

In operation S the image forming apparatus may receive a server address book from the cloud server supporting a phone number based printing service according to a request for the server address book and display the server address book on the screen for inputting the phone number of the recipient. The image forming apparatus may match and display a name and the phone number of the recipient based on the server address book received while displaying the screen for inputting the phone number of the recipient. The server address book may further include at least one of an email address of the recipient and information about a group to which the recipient belongs.

In operation S the image forming apparatus may receive a selection on a recipient from the displayed server address book.

In operation S the image forming apparatus may transmit a phone number of the selected recipient and the requested print operation to the cloud server based on the request for the print operation.

In the image forming apparatus provides a cloud printing service with a help of the agent application installed in the computing device that intermediates between the cloud server and the image forming apparatus if the image forming apparatus does not support a network connection function or an application supporting a cloud printing service is unable to be installed in the image forming apparatus .

According to only a user who has an authority to log in the computing device for example the second individual is able to assign a new phone number to the image forming apparatus and register or subscribe the new phone number in or to a cloud printing service through the agent application installed in the computing device . Accordingly another user who has no authority to log in the computing device for example the first individual is unable to perform registration or subscription to a cloud printing service by using the agent application without a help of the second individual .

A method registering even a user who does not have a login authority in a cloud printing service by using an NFC tag will now be described with reference to . Also a user who has a login authority may easily register in a cloud printing service by using an NFC tag that is to be described below. In the same reference numerals are used to denote the same elements even if not illustrated for convenience of description.

Unlike the image forming system of the cloud printing system of further includes the computing device in which the agent application is installed. It is assumed that the image forming apparatus of the cloud printing system is unable to receive a cloud printing service by independently connecting to a cloud server since the image forming apparatus does not support a network connection function or an application for executing a cloud printing service is unable to be installed in the image forming apparatus .

Referring to the cloud server a first mobile device a second mobile device the computing device the image forming apparatus and the agent application which exist on the cloud printing system may provide a phone number based cloud printing service in the same manner described above with reference to .

In it is assumed that a user A is an owner of the computing device and the first mobile device but embodiments are not limited thereto. Also it is assumed that the user A has an authority to log in an OS installed in the computing device . It is assumed that a user B is an owner of the second mobile device and does not have an authority to log in the OS of the computing device . However alternatively the user B may have an authority to log in the computing device .

The agent application that is the same as the agent application described above with reference to is installed in the computing device . Accordingly when a phone number of the first mobile device and the image forming apparatus are registered in the agent application the user A may print a content regarding a cloud printing service requested to the phone number of the first mobile device through the image forming apparatus .

When a phone number of the second mobile device used by the user B is not registered in the agent application the user B is unable to print a content requested to the phone number of the second mobile device through the image forming apparatus . Also since the user B does not have an authority to log in the computing device the user B is unable to directly register the phone number of the second mobile device in the computing device . In this case the user B may register the phone number of the second mobile device in a cloud printing service through the agent application by using an NFC tag .

In detail since the cloud server registers and manages information about the agent application a printing application installed in the first mobile device and supporting a cloud printing service may receive the information about the agent application from the cloud server . Accordingly the user A may NFC tag the first mobile device to the NFC tag so as to write the information about the agent application on the NFC tag .

Then the user B NFC tags the second mobile device to the NFC tag so as to obtain the information about the agent application written on the NFC tag . In other words even if the user B is unable to execute the agent application since the user B does not have an authority to log in the computing device the user B may obtain the information about the agent application via NFC tagging.

Like the first mobile device a printing application supporting a cloud printing service is installed in the second mobile device . The second mobile device transmits the information about the agent application obtained via the NFC tagging to the cloud server by using the printing application. The second mobile device also transmits information about the phone number of the second mobile device which is to be registered in the agent application .

The cloud server that registers and manages the agent application registers the phone number of the second mobile device after mapping the phone number of the second mobile device to the agent application by using the information about the agent application and the phone number of the second mobile device received from the second mobile device .

Accordingly even when the phone number of the second mobile device is not directly registered in the agent application by manipulating the agent application through the computing device the user B is able to register the phone number of the second mobile device in the agent application via the NFC tagging. As a result the user B may print the content about the cloud printing service requested to the phone number of the second mobile device through the image forming apparatus registered in the agent application .

Referring to the NFC tag may be attached to the computing device for convenience of using the NFC tag . Accordingly a user who is to be registered in the agent application installed in the computing device may conveniently subscribe the cloud printing service by NFC tagging the NFC tag without having to execute the agent application by booting the computing device .

In the NFC tag on which the information about the agent application is recorded is attached to the computing device in which the agent application is installed but alternatively the NFC tag may be attached to any place under an office environment or home environment.

Referring to the first mobile device includes a controller a network interface unit network interface an NFC module and a UI unit user interface . Also referring to the second mobile device includes a controller a network interface unit an NFC module and a UI unit .

In order to prevent features of an embodiment from being blurred only hardware components related to an embodiment are described in . However general purpose hardware components other that those shown in may be included in the first and second mobile devices and .

The first and second mobile devices and of may each be a smart phone laptop computer notebook computer portable game player portable media player PMP digital camera a tablet device a personal digital assistant PDA or a wearable device but are not limited thereto. Further it is understood that embodiments are also applicable to any device with which an apparatus method or medium of an embodiment can be used.

The UI unit is a hardware component including an input device or a display device and displays information to the user A of the first mobile device or receives information from the user A . The user interface unit may include for example one or more of a keyboard a keypad a mouse a joystick a button a switch an electronic pen or stylus a gesture recognition sensor e.g. to recognize gestures of a user including movements of a body part an input sound device or voice recognition sensor e.g. a microphone to receive a voice command an output sound device e.g. a speaker a track ball a pedal or footswitch a virtual reality device and the like. The user interface may further include a haptic device to provide haptic feedback to a user. The user interface may also include a touchscreen display for example. The touchscreen display may include a liquid crystal display LCD a light emitting diode LED display an organic light emitting diode OLED display active matrix organic light emitting diode AMOLED flexible display 3D display and the like for example. However the disclosure is not so limited thereto and may include other types of touchscreen displays. The disclosure may also include other types of user interfaces. The UI unit may also be a hardware component having the same functions as the UI unit .

The controller is a hardware component for controlling overall operations and functions of the first mobile device . In detail the controller may execute a printing application providing a phone number based cloud printing service. The controller may also be a hardware component having the same functions as the controller .

The controller or may be realized by at least one processor such as a central processing unit CPU an application processor AP an arithmetic logic unit a graphics processing unit GPU a digital signal processor DSP a microcomputer a field programmable gate array a programmable logic unit an application specific integrated circuit ASIC a microprocessor or any other device capable of responding to and executing computer readable instructions.

The network interface unit is a hardware component supporting a wired or wireless communication function and may support a wireless communication such as Wi Fi Wi Fi Direct Zigbee infrared data association IrDA or Bluetooth a wired communication such as Ethernet a 2G mobile communication a 3G mobile communication or a 4G mobile communication. The network interface unit may also be a hardware component having the same functions as the network interface unit .

The NFC module or is a hardware component that communications with other NFC devices for example the NFC tag and an NFC supporting smart phone according to an NFC protocol. When an NFC tagging function is activated the NFC module or may operate in a P2P mode a read write mode or an emulation mode.

Detailed operations and functions of the components of the first and second mobile devices and related to an embodiment will now be described in detail with reference to .

Referring to the registering of the use of the agent application is related to the registering of the use of the agent application described above with reference to . Accordingly details described above with reference to and details that will be described below with reference to may be applied to each other.

The cloud server registers and manages the agent application installed in the computing device . In other words the cloud server may register and manage not only the agent application but also agent applications existing on the cloud printing system . The agent application may be installed in image forming apparatuses or computing devices.

Referring to a table an Agent Type item has a value of PRT AGENT when agent applications are installed in image forming apparatuses and has a value of PC AGENT when agent applications are installed in computing devices.

The Agent Type item may correspond to the path information described above with reference to . In other words when the Agent Type item has the value of PRT AGENT a content requested to a certain phone number is directly transmitted to and printed by a certain image forming apparatus. In this case an agent application supporting a cloud printing service is installable in the certain image forming apparatus and a provided path of the cloud printing service is the certain image forming apparatus. On the other hand when the Agent Type item has the value of PC AGENT a content requested to a certain phone number is transmitted to a certain computing device and then is printed by a certain image forming apparatus registered in an agent application installed in the certain computing device. In this case an agent application supporting a cloud printing service is unable to be installed in the certain image forming apparatus and a provided path of the cloud printing service is the certain computing device. However as described above the agent application installed in the certain computing device may be used even when an agent application is installable in the certain image forming apparatus.

Referring to the table a Device ID Mac Address item may be an MAC address an IP address or the like that is intrinsically assigned to a device where an agent application is installed.

The cloud server maps and manages types Agent Type of agent applications and network information Device ID Mac Address of devices where agent applications are installed by using the table .

For example referring to the table since the value of PRT AGENT is mapped to an MAC address 00 15 99 00 00 AA an agent application installed in an image forming apparatus having the MAC address 00 15 99 00 00 AA is registered in the cloud server . Also since the value of PC AGENT is mapped to MAC addresses 00 15 99 00 00 BB and 00 15 99 00 00 CC agent applications installed in computing devices having the MAC addresses 00 15 99 00 00 BB and 00 15 99 00 00 CC are registered in the cloud server .

The cloud server stores the table for managing registration information of agent applications as described above.

Referring to the registering of the lists managed by the agent application is related to the details described above with reference to . Accordingly details described above with reference to and details that will be described below with reference to may be applied to each other.

The user A may add a new phone number for example 82 10 0000 0004 through a UI screen of the agent application .

In order to register the new phone number in the cloud server the computing device transmits information about the new phone number to the cloud server . The computing device may also transmit ID information of the agent application so that the cloud server identifies a request from the agent application . The ID information may be an authentication key or a login account intrinsically assigned from the cloud server to the agent application or may be an MAC address of the computing device where the agent application is installed.

The cloud server determines that the agent application installed in the computing device corresponds to an MAC address 00 15 99 00 00 CC by using a table .

Also the cloud server maps and registers the MAC address 00 15 99 00 00 CC and the new phone number 82 10 0000 0004 as shown in a table . Image forming apparatus information SCX 6401 may be additionally mapped.

As described above the cloud server may map and manage phone numbers added by the agent application and information about the agent application .

In operation the controller of the first mobile device executes a printing application installed in the first mobile device .

When the printing application is executed the UI unit of the first mobile device displays the UI screen of the printing application.

As shown on the UI screen it is assumed that a phone number of the first mobile device is 82 10 0000 0004 .

When the user A clicks a start button instructing NFC write through the UI screen the controller of the first mobile device activates an NFC tagging mode of the printing application in operation .

In operation the network interface unit of the first mobile device requests the cloud server for ID information of the agent application according to a control of the printing application. The ID information of the agent application includes network address information of the computing device where the agent application is installed. In detail the network address information of the computing device may be the MAC address of the computing device used while registering the agent application in the cloud server as described above with reference to .

In order to request for the ID information of the agent application the network interface unit of the first mobile device may transmit the phone number of the first mobile device registered in the agent application to the cloud server .

The cloud server determines that MAC addresses mapped to the phone number 82 10 0000 0004 of the first mobile device are 00 15 99 00 00 CC and 00 15 99 00 00 DD by using a table . Also the cloud server determines that an agent application mapped to the MAC address 00 15 99 00 00 CC is an agent application installed in a PC of HOME PC and an agent application mapped to the MAC address 00 15 99 00 00 DD is an agent application installed in a PC of OFFICE PC by using a table .

In operation the cloud server transmits the ID information of the agent application to the first mobile device . The transmitted ID information includes the MAC addresses 00 15 99 00 00 CC and 00 15 99 00 00 DD . Also the transmitted ID information may also include PC names HOME PC and OFFICE PC respectively corresponding to the MAC addresses 00 15 99 00 00 CC and 00 15 99 00 00 DD .

When the user A NFC tags the first mobile device to the NFC tag the NFC module of the first mobile device writes the ID information of the agent application on the NFC tag in operation .

Since the transmitted ID information includes two types of MAC addresses the user A may select at least one of the MAC addresses through the UI screen . As such when the transmitted ID information includes a plurality of MAC addresses the UI screen displays a pop up window for selecting an MAC address to be written.

When the user A selects OFFICE PC 00 15 99 00 00 DD from the pop up window the NFC module writes ID information of OFFICE PC 00 15 99 00 00 DD on the NFC tag . If the user A selects two or more MAC addresses the selected two or more MAC addresses may be written.

In operation the NFC tag stores the ID information of the agent application . In other words the NFC tag stores the ID information of OFFICE PC 00 15 99 00 00 DD .

In operation the controller of the second mobile device executes a printing application installed in the second mobile device .

When the printing application is executed the UI unit of the second mobile device displays the UI screen of the printing application.

As shown in the UI screen it is assumed that a phone number of the second mobile device is 82 10 1234 ABCD .

When the user B clicks a start button instructing NFC read through the UI screen the controller of the second mobile device activates an NFC tagging mode of the printing application in operation .

When the user B NFC tags the second mobile device to the NFC tag the NFC module of the second mobile device reads the ID information of the agent application written on the NFC tag in operation . In other words the NFC module reads the ID information of OFFICE PC 00 15 99 00 00 DD from the NFC tag .

In operation the network interface unit of the second mobile device transmits a registration request including the read ID information of OFFICE PC 00 15 99 00 00 DD and the phone number 82 10 1234 ABCD of the second mobile device to the cloud server .

In operation the cloud server registers the phone number of the second mobile device after mapping the phone number to the agent application corresponding to the ID information.

In detail the cloud server determines the agent application mapped to the ID information by using a table . Then the cloud server registers the phone number of the second mobile device in the agent application corresponding to the ID information as shown in a table .

In operation the cloud server transmits a registration response to the second mobile device in response to the registration request from the second mobile device . In other words the cloud server may transmit the registration response indicating that the phone number of the second mobile device is registered in the agent application corresponding to the ID information.

In operation the UI unit of the second mobile device displays registration information indicating that the phone number of the second mobile device is registered in the agent application based on the registration response. In other words the UI unit may display the registration information indicating that the phone number of the second mobile device is registered in the agent application corresponding to the ID information through the UI screen .

In operation the cloud server may transmit the registration information to the first mobile device or the computing device where the agent application is installed.

In operation the first mobile device or the agent application may update a list of existing phone numbers based on the transmitted registration information.

As such the user B may register the phone number of the second mobile device in the agent application via NFC tagging even when the phone number of the second mobile device is not directly registered in the agent application by manipulating the agent application in the computing device .

In the processes performed by the first mobile device the second mobile device the cloud server and the NFC tag which have been described above with reference to are synthetically described. Accordingly details described with reference to may also be applied to details described with reference to .

In operation the cloud server transmits the ID information of the agent application installed in the computing device to the first mobile device .

In operation the first mobile device writes the ID information of the agent application on the NFC tag .

In operation the second mobile device reads the ID information of the agent application written on the NFC tag .

In operation the second mobile device transmits the read ID information and the phone number of the second mobile device to the cloud server .

In operation the cloud server registers the phone number of the second mobile device after mapping the phone number of the second mobile device to the agent application corresponding to the read ID information.

In operation the first mobile device receives the ID information of the agent application in which the phone number of the first mobile device is registered from the cloud server .

In operation the second mobile device transmits a registration request generated by using the read ID information to the cloud server .

In operation the cloud server registers the second mobile device in the agent application based on the transmitted registration request.

In order to use the cloud printing service described above a process of registering an image forming apparatus such as a printer a scanner or a multi function product MFP in a server after mapping the image forming apparatus to a phone number is necessary. Hereinabove a method of tagging a mobile terminal to an NFC tag of an image forming apparatus has been described as a device registration method.

However in the device registration method through NFC tagging it may be difficult to recognize a location of an image forming apparatus supporting a cloud printing service and moreover it is not possible to register an image forming apparatus that does not support an NFC tag.

Accordingly one or more embodiments for registering an image forming apparatus in a cloud printing server through an augmented reality application a Bluetooth communication or QR code reading are suggested. Such one or more embodiments will now be described in detail with reference to .

Referring to the cloud printing system may include a cloud printing server a mobile terminal and an image forming apparatus . In order to use a cloud printing service the image forming apparatus needs to be registered in the cloud printing server correspondingly to a predetermined phone number as described above. In an embodiment it is assumed that the image forming apparatus is registered in the cloud printing server to correspond to a phone number of the mobile terminal .

In an embodiment the mobile terminal requests the cloud printing server for a device registration of the image forming apparatus . In order to request for the device registration device information about the image forming apparatus is required together with the phone number of the mobile terminal . The device information may include at least one of an MAC address an IP address a serial number a host name a model name or capability of the image forming apparatus .

Accordingly the mobile terminal obtains the device information about the image forming apparatus through at least one of an augmented reality application a Bluetooth communication and QR code reading and requests for the device registration while transmitting the obtained device information and the phone number of the mobile terminal to the cloud server .

Detailed processes of obtaining the device information about the image forming apparatus and performing the device registration through at least one of the augmented reality application the Bluetooth communication and the QR code reading will now be described in detail with reference to accompanying drawings.

Referring to indoor positioning system IPS information and device information of the image forming apparatus are first registered in the cloud printing server .

An IPS is a system for determining a location of a person or an object in a building by using a wireless communication apparatus mostly indoors where a global positioning system GPS does not reach and may use any one of triangulation using Wi Fi or Bluetooth a fingerprint method and various methods using infrared rays an acoustic analysis an electronic tag RFID and various sensors. In other words IPS information corresponds to location information for determining a location indoors. Considering that an image forming apparatus is generally located indoors it is assumed that IPS information is used.

The device information of the image forming apparatus may be an MAC address and may further include a model name and supportability of a cloud printing service.

The mobile terminal executes the augmented reality application and photographs the image forming apparatus . The mobile terminal may request for IPS information and device information stored in the cloud printing server . In response the cloud printing server transmits the IPS information and the device information to the mobile terminal . The cloud printing server may extract and transmit IPS information and device information of an image forming apparatus adjacent to the mobile terminal from among the stored IPS information and the stored device information.

The mobile terminal may recognize the image forming apparatus photographed by the augmented reality application by using the received IPS information. In detail an image forming apparatus may be found from a captured screen of the augmented reality application through the location of the image forming apparatus determined from the received IPS information.

After finding the image forming apparatus from the captured screen the device information of the image forming apparatus received from the cloud printing server may be displayed at a location corresponding to the found image forming apparatus. The displayed device information may include a model name of the image forming apparatus or supportability of a cloud printing service.

In the model name i.e. ML 2020 of the image forming apparatus is displayed in a region of a screen of the augmented reality application. Also when the image forming apparatus is found from the captured screen a button for device registration and a button for performing printing may be additionally displayed.

When the button for device registration is selected the mobile terminal requests the cloud printing server for device registration while transmitting a phone number of the mobile terminal together with the MAC address of the image forming apparatus . When the button for performing printing is selected the image forming apparatus performs printing.

In order for the mobile terminal that executed the augmented reality application to receive the IPS information and the MAC address from the cloud printing server the IPS information and the MAC address need to be pre stored in the cloud printing server .

When the image forming apparatus is able to obtain or generate the IPS information the image forming apparatus may directly transmit the IPS information and the MAC address to the cloud printing server . However when the image forming apparatus is unable to obtain or generate the IPS information the mobile terminal may obtain or generate the IPS information and transmit the obtained or generated IPS information to the cloud printing server .

Referring to the image forming apparatus directly obtains or generates the IPS information and transmits the IPS information to the cloud printing server together with the MAC address of the image forming apparatus . For example the image forming apparatus may generate the IPS information by determining an indoor location based on location information and strength of a connection signal of a wireless AP connected via Wi Fi or by using any one of well known various methods. The cloud printing server stores the MAC address and the IPS information in a table after mapping the IPS information to the MAC address.

Referring to the mobile terminal generates the IPS information of the image forming apparatus since the image forming apparatus is unable to directly obtain or generate the IPS information. Then the mobile terminal receives the MAC address from the image forming apparatus and transmits the received MAC address and the generated IPS information to the cloud printing server . The cloud printing server stores the MAC address and the IPS information in a table after mapping the IPS information to the MAC address.

A method of the mobile terminal generating the IPS information of the image forming apparatus may vary. For example the mobile terminal is connected to the image forming apparatus via Bluetooth and measures a distance between the mobile terminal and the image forming apparatus by measuring strength of a connection signal and determines a location of the mobile terminal based on a location of a connected base station or a wireless AP. Then the mobile terminal may generate the IPS information by using the location of the mobile terminal and the distance between the mobile terminal and the image forming apparatus . Alternatively the mobile terminal may receive the IPS information from an external IPS information providing system.

Referring to the cloud printing server stores the IPS information and the device information of the image forming apparatus in operation . In detail the cloud printing server receives the MAC address together with the IPS information of the image forming apparatus maps the IPS information to the MAC address and stores the IPS information and the MAC address in a table. The IPS information of the image forming apparatus may be received directly from the image forming apparatus or received from the mobile terminal or an external system.

In operation the mobile terminal executes the augmented reality application to photograph the image forming apparatus . The mobile terminal requests the cloud printing server for the IPS information and the device information in operation . The cloud printing server transmits the IPS information and the device information which are pre stored to the mobile terminal in operation . The cloud printing server may extract and transmit only IPS information and device information of an image forming apparatus adjacent to the mobile terminal from among the pre stored IPS information and the pre stored device information. In this case the mobile terminal may transmit the location information of the mobile terminal to the cloud printing server while requesting for the IPS information and the device information in operation and the cloud printing server may extract the IPS information and the device information of the image forming apparatus adjacent to the mobile terminal based on the received location information of the mobile terminal .

In operation the mobile terminal may recognize the image forming apparatus photographed by using the received IPS information. In detail a location corresponding to the received IPS information is searched for in the captured screen of the augmented reality application and it may be recognized that the image forming apparatus exists in the searched location.

In operation the received device information is displayed on the captured screen of the augmented reality application. In other words the device information received in operation is displayed at the location of the image forming apparatus recognized in operation . The displayed device information may be the model name of the image forming apparatus and may also include supportability of a cloud printing service. An example of a screen of an augmented reality application on which device information is displayed is shown in .

In operation the mobile terminal receives a request for device registration. A user may check the image forming apparatus and the device information of the image forming apparatus from the screen of the augmented reality application and request for device registration of the image forming apparatus . For example a button for device registration may also be displayed on the screen of the augmented reality application where a captured image and the device information of the image forming apparatus are displayed and the user may touch the button to request for the device registration.

In operation the mobile terminal may transmit the phone number and the device information to the cloud printing server to request the cloud printing server to register the image forming apparatus . In detail the mobile terminal may transmit the MAC address of the image forming apparatus from among the device information to the cloud printing server together with the phone number of the mobile terminal to request for registration. In response the cloud printing server may store the phone number and the MAC address after mapping the MAC address to the phone number thereby registering the image forming apparatus as a device capable of using a cloud printing service.

Referring to IPS information and device information of the image forming apparatus are stored in a cloud printing server in operation . The cloud printing server stores the IPS information after mapping the IPS information to an MAC address of the image forming apparatus.

In operation a mobile terminal executes the augmented reality application and photographs the image forming apparatus.

In operation the mobile terminal obtains the IPS information and the device information of the image forming apparatus from the cloud printing server.

In operation the mobile terminal displays the device information of the image forming apparatus on a captured image by using the received IPS information. In detail the mobile terminal may search for a location corresponding to the received IPS information from a captured screen of the augmented reality application and recognize that the image forming apparatus exists at the searched location. Also the mobile terminal may display a model name of the image forming apparatus and supportability of a cloud printing service which are included in the received device information on the location of the image forming apparatus in the captured image.

In operation the mobile terminal receives a request for device registration. A button for device registration may be displayed on a screen of the augmented reality application executed in the mobile terminal and when a user touches the button the mobile terminal receives the request for device registration regarding the image forming apparatus displayed on the screen.

In operation the mobile terminal transmits a phone number and the device information to the cloud printing server and requests the cloud printing server for device registration of the image forming apparatus. In response the cloud printing server may register the image forming apparatus after mapping an MAC address included in the received device information to the received phone number.

Referring to the cloud printing system capable of registering the image forming apparatus through QR code reading may include the cloud printing server the mobile terminal the image forming apparatus and a QR code on which the device information of the image forming apparatus is recorded.

The QR code may be manufactured in a sticker to be attached to an outer surface of the image forming apparatus or may be printed on a test page output after setting the image forming apparatus .

When the user executes a mobile application of a cloud printing service in the mobile terminal and selects device registration using a QR code from menus of the mobile application the mobile terminal is switched to a state for reading a QR code. Then when the user photographs the QR code by using the mobile terminal the device information including the MAC address of the image forming apparatus which is stored in the QR code is obtained. Next the mobile terminal transmits the phone number of the mobile terminal to the cloud printing server together with the obtained device information of the image forming apparatus and requests the cloud printing server for device registration. The cloud printing server registers the image forming apparatus after mapping the device information to the received phone number.

In operation the image forming apparatus transmits the device information including the MAC address and the model name to the cloud printing server when power is turned on.

In operation the cloud printing server stores the received device information and maintains a connection with the image forming apparatus . In detail the cloud printing server receives and stores the MAC address and the model name from the image forming apparatus via a wireless connection such as Bluetooth . Then the wireless connection used for transmission is not released but maintained. The MAC address and the model name are mapped to the maintained wireless connection.

In operation the mobile terminal may obtain the MAC address and the model name of the image forming apparatus by photographing a QR code attached to the image forming apparatus . When the user executes the mobile application of the cloud printing service in the mobile terminal and selects a device registration menu using a QR code from the mobile application the mobile terminal is changed to a state for photographing a QR code. Then the mobile terminal photographs a QR code and obtains device information stored in the QR code.

In operation the mobile terminal transmits the MAC address and the model name of the image forming apparatus together with the phone number of the mobile terminal .

In operation the cloud printing server maps the phone number to an existing connection by using the MAC address of the image forming apparatus as a key value. In detail as described above the cloud printing server maintains the connection with the image forming apparatus in operation and the MAC address of the image forming apparatus is mapped to the maintained connection. Accordingly the cloud printing server is able to find a connection corresponding to the MAC address received in operation and map the phone number of the mobile terminal also received in operation to the connection.

Referring to a mobile terminal photographs a QR code attached to the image forming apparatus to obtain an MAC address and a model name of the image forming apparatus in operation .

In operation the mobile terminal transmits the obtained MAC address and the obtained model name to a cloud printing server together with a phone number of the mobile terminal.

In operation the cloud printing server registers the image forming apparatus after mapping the MAC address and the model name to the received phone number.

Referring to the cloud printing system capable of direct registration of the image forming apparatus may include the cloud printing server the mobile terminal and the image forming apparatus .

The image forming apparatus may display a UI screen for device registration on a display unit display . A user may input the phone number of the mobile terminal to the UI screen via an input device of the image forming apparatus . When the phone number of the mobile terminal is input the image forming apparatus may request the cloud printing server for device registration by transmitting the input phone number and the MAC address of the image forming apparatus . In response the cloud printing server stores the phone number and the MAC address after mapping the MAC address to the phone number.

Referring to the image forming apparatus transmits the MAC address and the model name to the cloud printing server when power is turned on in operation .

In operation the cloud printing server stores received information and maintains a connection with the image forming apparatus . In detail the cloud printing server receives and stores the MAC address and the model name from the image forming apparatus through a wireless connection such as Bluetooth . Then the wireless connection used for transmission is not released but maintained. The received MAC address and the model name are mapped to the maintained wireless connection.

In operation the image forming apparatus displays a UI screen for device registration on a display unit.

In operation the image forming apparatus receives a phone number of a mobile terminal from a user through the UI screen.

In operation the image forming apparatus transmits the input phone number and the MAC address to the cloud printing server .

In operation the cloud printing server maps the phone number to an existing connection by using the received MAC address as a key value. In detail the cloud printing server maintains the connection with the image forming apparatus as described above in operation and the MAC address of the image forming apparatus is mapped to the maintained connection. Accordingly the cloud printing server is able to find a connection corresponding to the MAC address received in operation and map the phone number of the mobile terminal received in operation .

Referring to a UI screen for device registration is displayed on a display unit of an image forming apparatus in operation .

In operation the image forming apparatus transmits the received phone number to a cloud printing server together with an MAC address to request the cloud printing server for device registration. In response the cloud printing server stores the received phone number and the MAC address after mapping the MAC address to the received phone number.

Referring to the cloud printing system capable of registering the image forming apparatus by using the Bluetooth may include the cloud printing server the mobile terminal and the image forming apparatus . The mobile terminal and the image forming apparatus may support the Bluetooth .

The mobile terminal may obtain the device information from the image forming apparatus by being connected to the image forming apparatus via the Bluetooth . The received device information may include an MAC address an IP address a serial number a host name a model name and capability of the image forming apparatus .

The mobile terminal may request the cloud printing server for device registration of the image forming apparatus by transmitting the obtained device information and the phone number of the mobile terminal to the cloud printing server . In response the cloud printing server stores the received phone number and the device information after mapping the device information to the received phone number.

Device information of image forming apparatuses may be pre stored in the cloud printing server . Also whether each image forming apparatus is registered may be recorded in the pre stored device information. Accordingly upon receiving device information from the mobile terminal the cloud printing server may compare the received device information and pre stored device information to notify the mobile terminal whether an image forming apparatus corresponding to the received device information is already registered. When the image forming apparatus is a nonregistered device the mobile terminal may request the cloud printing server for device registration of the image forming apparatus .

Referring to the image forming apparatuses and transmit device information to the cloud printing server . The device information may be transmitted through a Bluetooth . The cloud printing server stores the received device information in a table . Although not shown the table may show whether an image forming apparatus corresponding to each piece of device information is a registered device.

Referring to the mobile terminal receives device information from the image forming apparatus and device information from the image forming apparatus . The received device information and may include capability such as color printability and double side printability and current state information.

The mobile terminal may transmit the received device information and to the cloud printing server to inquire registration of the image forming apparatuses and respectively corresponding to the device information and . The cloud printing server compares the received device information and with pre stored device information and transmits a response regarding the registration to the mobile terminal .

The mobile terminal may transmit a registration request for a nonregistered device to the cloud printing server together with the phone number of the mobile terminal . In if the image forming apparatus is a registered device but the image forming apparatus is a nonregistered device the mobile terminal may request the cloud printing server for device registration by transmitting the device information of the image forming apparatus to the cloud printing server together with the phone number of the mobile terminal . In response the cloud printing server stores the received phone number and the device information after mapping the device information to the received phone number.

Referring to the image forming apparatus transmits and stores the device information of the image forming apparatus to and in the cloud printing server when power is turned on.

In operation the mobile terminal obtains the device information from the image forming apparatus through the Bluetooth .

In operation the mobile terminal inquires device registration of the image forming apparatus by transmitting the device information to the cloud printing server .

In operation the cloud printing server compares pre stored device information and the device information received in operation to determine the device registration and transmits a result of the determining to the mobile terminal .

When it is determined that the image forming apparatus is a nonregistered device the mobile terminal transmits the device information and the phone number to the cloud printing server to request for device registration in operation .

Referring to the image forming apparatus transmits and stores the device information to and in the cloud printing server when power is turned on in operation .

In operation the mobile terminal transmits a print request to the cloud printing server after setting print options such as color printability and double side printability.

In operation the cloud printing server compares pre stored device information and the received print options so as to transmit print data to the image forming apparatus capable of printing according to the received print options.

The image forming apparatus prints the received print data in operation and transmits a result of the printing the print data to the mobile terminal in operation . In detail the image forming apparatus may transmit the result about whether the printing was successful or whether the printing failed since the image forming apparatus is not capable of printing to the mobile terminal . If an error message that the printing failed is transmitted to the mobile terminal a user checks the error message through the mobile terminal and request another image forming apparatus to print the print data. In this case the cloud printing server may search for an image forming apparatus capable of printing the print data according to the print option by using the device information and transmit the print data and a print command to the searched image forming apparatus.

Referring to device information of an image forming apparatus is stored in a cloud printing server in operation . In detail the image forming apparatus transmits the device information to the cloud printing server when power is turned on and the cloud printing server may store the received device information in a table. The cloud printing server may record whether the image forming apparatus corresponding to the stored device information is a registered device.

In operation a mobile terminal may obtain device information of an adjacent image forming apparatus via a Bluetooth connection. Device information may include current state information and capability such as color printability and double side printability.

When the mobile terminal transmits the obtained device information to the cloud printing server in operation the cloud printing server compares the stored device information and the received device information to determine whether the adjacent image forming apparatus corresponding to the received device information is a registered device in operation and transmits a result of the determining to the mobile terminal.

When it is determined that the adjacent image forming apparatus is a nonregistered device in operation the mobile terminal transmits the device information obtained in operation to the cloud printing server together with a phone number of the mobile terminal and requests the cloud printing server for device registration in operation .

In operation the cloud printing server registers the image forming apparatus correspondingly to the received phone number.

In operation a mobile terminal obtains device information of the image forming apparatus through at least one of an augmented reality application a Bluetooth communication and QR code reading in operation .

In operation the mobile terminal requests a cloud printing server for device registration by transmitting the obtained device information together with a phone number of the mobile terminal.

In operation the cloud printing server registers the image forming apparatus correspondingly to the received phone number.

Generally when a plurality of files including several contents are to be uploaded but some of the plurality of files are not properly uploaded or are damaged a mobile terminal determines that an entire uploading operation failed even if the other some of the plurality of files are uploaded in a cloud server and re uploads the plurality of files thereby unnecessarily inducing traffics and unnecessarily wasting a storage space. Also when one file including content is to be transmitted to several users the file is uploaded for each user thereby unnecessarily including traffics and unnecessarily wasting a storage space.

One or more embodiments provide a method of uploading print content and a print job to a cloud server by using a content key.

According to one or more embodiments a mobile terminal uploads print content and a print job to a cloud server by using a content key without unnecessarily inducing traffics.

According to one or more embodiments by using a content key a mobile terminal does not upload a plurality of files and thus traffics are not unnecessarily induced. Also the mobile terminal uploads a file which is duplicated between users only once and thus a storage space may be saved.

Referring to the user uploads to the cloud server content to be printed and a print job related to the content to be printed by using the mobile terminal . The cloud server may include a management server and a content server . Here the management server is a server that performs a function of generating and managing the print job related to content which is uploaded by the user by using the mobile terminal . The content server is a server that performs a function of storing content related to a print job. One server does not perform all functions but functions may be divided and a plurality of servers may respectively perform the divided functions so as to reduce a load of each server.

The user may first select content to be uploaded by using the mobile terminal . At the same time the user may select a job to be performed in relation to the content to be uploaded by using the mobile terminal . For example the user uploads a.jpg b.jpg and c.jpg files including drawing contents to a space in the cloud server by using the mobile terminal and later wants to print the a.jpg b.jpg and c.jpg files through an image forming apparatus registered in the cloud server by accessing the cloud server by using the mobile terminal .

In operation the mobile terminal transmits a job upload request regarding content selected by the user to the management server .

In operation the management server transmits content received from the mobile terminal to the content server such that the content is stored in the content server . Here the management server may transmit the content together with the job upload request. The content server receives the content from the management server and stores the received content.

In operation when the content is stored in the content server the management server may generate job data related to the stored content. In other words the management server may generate a job identifier and map and store the generated job identifier and the stored content thereby generating the job data. For example the management server uploads the a.jpg b.jpg and c.jpg files to an individual cloud space assigned to the user at once. Here the mobile terminal calls an API once with respect to the a.jpg b.jpg and c.jpg files from the management server . When the a.jpg b.jpg and c.jpg files are all uploaded to the content server the management server generates jobs with respect to the job upload request.related to the a.jpg b.jpg and c.jpg files. The management server may manage the generated jobs in a form of a table. Here the table may include a job identifier a content identifier and a phone number. While generating the jobs the management server may generate a job for each of the a.jpg b.jpg and c.jpg files. Since the jobs are registered in the management server when there are no jobs the registered job identifiers may be 1 2 and 3 in sequence. Also the management server may store a.jpg b.jpg and c.jpg as content identifiers in sequence in relation to currently generated jobs. In addition the management server may store metadata a file name or a file size of each file together with each job.

After the content file to be printed and the print job related to the content file are uploaded stored in the cloud server the user may download and print the uploaded content file .

The management server may store the print job regarding the content file in a storage space corresponding to mobile terminal ID information. Here the mobile terminal ID information may be a phone number of the mobile terminal .

If the user wants to upload a print job regarding content to an individual cloud space assigned to the user by using the mobile terminal the user may be able to transmit a job upload request regarding the content to the management server without having to separately input the mobile terminal ID information. At this time the mobile terminal may check a subscriber ID number i.e. the phone number of the mobile terminal stored in a USIM chip of the mobile terminal and transmit the subscriber ID number together with the job upload request. Accordingly the management server may determine storage spaces according to subscriber ID numbers and store print jobs in the determined storage spaces. For example the user may store a print job in an individual storage space corresponding to a phone number 010 xxx xxxx of the mobile terminal . Here the storage spaces are not limitedly divided physically but may be logically divided. In other words if storage spaces are logically divided even if the storage spaces are physically divided the storage devices are divided according to phone numbers since the storage spaces are mapped and managed according to the phone numbers. For convenience of description a job table includes a phone number field but a corresponding relation between the phone number field and the job table may be separately managed in a form of a mapping table or may be managed by storing the job table in storage spaces according to phone numbers.

The user may transmit content to be printed and a print job to several other users. In operation in order to transmit the print job to the several other users the user may input phone numbers of the several other users to the mobile terminal and transmit a job upload request regarding the content to the management server together with the phone numbers of the several other users by using the mobile terminal . For example the mobile terminal may transmit a print job upload request regarding a.jpg that is drawing content to phone numbers 010 yyy yyyy and 010 zzz zzzz of the several other users.

In operation the management server may transmit content to the content server such that the content is stored in the content server . Here if the same content is stored according to users the content server stores the same content several times according to the users. For example when the mobile terminal transmits a job upload request regarding the a.jpg to the phone numbers 010 yyy yyyy and 010 zzz zzzz of the several other users the content server stores the a.jpg in storage spaces respectively mapped to the phone numbers 010 yyy yyyy and 010 zzz zzzz . Thus the content server stores a.jpg twice.

In operation the management server may generate job data in a form of a mapping table in which a job identifier and content are mapped. Here a job table may be generated in a storage space mapped to a phone number of a mobile terminal. For example the job table is generated in each storage space mapped to the phone number 010 yyy yyyy . The management server may generate and store a job table having rows in which a job identifier is 1 and a content identifier field is a.jpg in the storage space mapped to the phone number 010 yyy yyyy . Also the management server may generate and store a job table having rows in which a job identifier is 1 and a content identifier field is a.jpg in the storage space mapped to the phone number 010 zzz zzzz .

Referring to the user uploads a job regarding content to the cloud server by using the mobile terminal and several files are uploaded simultaneously for the job. At this time if only some of the several files are stored in the cloud server while the other some of the several files are not stored in the cloud server the cloud server notifies the mobile terminal that all of the several files are not stored and thus the mobile terminal transmits all of the several files again despite that some of the several files are already stored in the cloud server. Accordingly traffics are unnecessarily induced and a storage space is unnecessarily wasted.

Also if the user transmits a job upload request regarding the same content to other several users by using the mobile terminal the same content is uploaded to the cloud server several times according to the other several users and thus traffics are unnecessarily induced and a storage space is unnecessarily wasted by storing the same content several times.

The cloud server according to an embodiment may receive a user input indicating a job request regarding content from the mobile terminal store the content according to the received user input obtain a content key corresponding to the stored content and transmit the obtained content key to the mobile terminal . Then the cloud server may receive the job request together with the content key from the mobile terminal and perform a job on the stored content corresponding to the received content key according to the received job request.

The receiver may receive data from an external device. In detail the receiver may receive a user input indicating a job request regarding content from the mobile terminal . The receiver may receive the job request from the mobile terminal together with a content key received from the transmitter .

The transmitter may transmit data to the external device. Upon successfully storing content received from the mobile terminal the transmitter may transmit a content key corresponding to the stored content to the mobile terminal .

The controller may control components the transmitter the receiver and the storage unit included in the cloud server . In detail the controller may further include an obtainer a job manager a job performer and an authenticator . The obtainer may perform a function of obtaining content and a content key. The job manager may perform a management function such as generating or deleting a job mapped to a content key. The job performer may perform a function of performing a job generated by the job manager . The authenticator may authenticate a mobile terminal ID number and at this time generate a PIN code and an access token.

The controller may control the receiver to receive a user input indicating a job request regarding content from the mobile terminal . Also the controller may control the storage unit to store the content according to the user input received from the receiver . The controller may obtain a content key corresponding to the stored content. In other words the content key may be generated and obtained under a control of the controller .

The controller may control the transmitter to transmit the obtained content key. The controller may control the receiver to receive a job request from the mobile terminal together with the content key from the transmitter . The controller may perform a job on the stored content corresponding to the received content key based on the received job request.

The controller may control the receiver to receive an identifier stored in the storage unit from the mobile terminal . The controller may control the storage unit to obtain a content key mapped to a job identifier and control the storage unit to obtain content stored in the storage unit by using the obtained content key. The controller may perform a job on the content obtained from the storage unit .

A job request regarding content which is received from the mobile terminal may be destined for a predetermined phone number and the controller may control the receiver to receive a confirmation request on a job identifier stored in the storage unit from a mobile terminal corresponding to the predetermined phone number. The controller may control the transmitter to transmit a job list including the job identifier corresponding to the confirmation request received from the receiver to the mobile terminal corresponding to the predetermined phone number.

The controller may control the receiver to receive from the mobile terminal corresponding to the predetermined phone number a print job request including at least one job identifier included in the job list transmitted from the transmitter . The controller may control the storage unit to obtain a content key corresponding to the job identifier included in the received print job request. The controller may control the storage unit to obtain content stored in the storage unit by using the content key corresponding to the job identifier obtained from the storage unit . The controller may control the transmitter to transmit content obtained from the storage unit to an image forming apparatus corresponding to a mobile terminal ID information such that an image forming job of the content is performed by the image forming apparatus.

The controller may control the receiver to receive from a mobile terminal a content preview request including at least one job identifier included in the job list transmitted from the transmitter . The controller may control the storage unit to obtain a content key corresponding to the at least one job identifier included in the content preview request received from the receiver . The controller may control the storage unit to obtain content stored in the storage unit by using the content key corresponding to the at least one job identifier obtained from the storage unit . The controller may generate preview data of the obtained content and control the storage unit to store the generated preview data.

The controller may control the transmitter to transmit location information of the preview data to the mobile terminal that transmitted the content preview request to the cloud server such that the mobile terminal checks the preview data.

The controller may control the receiver to receive an authentication request from the mobile terminal . The controller may generate a PIN code corresponding to mobile terminal ID information based on the authentication request received from the receiver . The controller may control the transmitter to transmit a message including the PIN code to the mobile terminal such that the mobile terminal checks the message. The controller may control the receiver to receive a PIN code confirmation request including a PIN code from the mobile terminal in response to the message transmitted from the transmitter . If it is determined that the PIN code included in the PIN code confirmation request is the same as the PIN code included in the message an access token corresponding to the mobile terminal is generated and obtained under a control of the controller . The controller may control the transmitter to transmit the obtained access token to the mobile terminal . Here the controller may control the receiver to receive a user input indicating a job request regarding content from the mobile terminal together with the access token from the transmitter .

The controller may generate delete or modify a job regarding content. In detail the controller may generate a job identifier corresponding to a job request received from the receiver and map and store the generated job identifier and a content key corresponding to content. Here the controller may generate a mapping table wherein the generated job identifier and the content key corresponding to the content are mapped to each other.

The controller may control the storage unit to store content preview data of the content and a job identifier a mapping table wherein a job identifier and a content key corresponding to content are mapped to each other .

The cloud server may include the management server and the content server . The controller may control the management server to transmit a store request regarding content to the content server . The controller may control the content server to store the content based on the received store request. The controller may control the content server to generate a content key corresponding to the content stored in the content server . The controller may control the management server to receive the generated content key from the content server . Also the controller may control the management server to transmit the store request regarding the content to the content server such that the content is stored. The controller may control the content server to store the content according to the received store request. The controller may control the management server to receive the content key stored in the content server from the content server . The controller may control the management server to receive a stored job identifier from a mobile terminal. The controller may control the management server to obtain a content key corresponding to the received job identifier. The controller may control the management server to transmit a request regarding the stored content including the content key corresponding to the job identifier to the content server . The controller may control the management server to receive the stored content from the content server in response to the transmitted request regarding the stored content. The controller may perform a job on the received content.

When a user wants to store a print job regarding content in an individual cloud server storage space assigned to the user or transmit the print job to another user the content needs to be first uploaded. In the current embodiment it is assumed that a storage space is not divided according to users but is managed by using a content key corresponding to content which is generated when the content is stored. Accordingly a physical cloud space of content does not exist for users but all files may be stored in one cloud space a unique content key may be assigned to content and a mapping table wherein the assigned unique content key and a user are mapped to each other may be managed thereby easily securing a storage space according to a service increase without having to obtain a physical or logical cloud storage space according to users.

First the user may input a job upload request regarding content by using the mobile terminal . For example the user may execute an application in the mobile terminal select content on the application and set a destination for the content. In other words the mobile terminal may receive a user input indicating an upload request regarding content from the user.

In operation the mobile terminal may transmit an upload request regarding content to the management server . The upload request may contain the content.

In operation upon receiving the upload request from the mobile terminal the management server may transmit the content included in the upload request to the content server to be stored.

In operation upon receiving the content from the management server the content server may store the received content and generate a content key corresponding to the stored content. The content server may transmit the generated content key to the management server .

In operation upon receiving the content key from the content server the management server may transmit the content key to the mobile terminal . Here the management server does not store the content key but directly transmits the content key to the mobile terminal thereby relaying the content key.

The mobile terminal may receive the content key from the management server . Upon receiving the content key the mobile terminal may determine that the content has been normally transmitted. Upon determining that the content has been normally transmitted the mobile terminal may request the cloud server to generate a print job regarding the content. Here the content key may be generated according to contents.

Accordingly when the user uploads several files contents by using the mobile terminal by calling API once a content key is generated whenever one file content is successfully uploaded in the content server and upon receiving the content keys the mobile terminal may determine which file content is successfully uploaded and which content is failed to be uploaded. Accordingly the mobile terminal may prevent traffics from being unnecessarily induced by re transmitting only a file content including the content that is failed to be uploaded.

Generally if a user wants to transmit a print job regarding content to other users by using the mobile terminal the content is uploaded according to the other users. In detail if the user requests to upload a job regarding the same content to the other users the mobile terminal transmits an upload request regarding the same content to each of the other users and thus the same content is uploaded several times. However referring to if the user wants to transmit a print job regarding the same content to other users by using the mobile terminal the mobile terminal first transmits an upload request regarding the same content to the cloud server and at this time transmits the same content only once to be stored in the cloud server without having to transmit the same content to each of the other users. In the current embodiment a content key corresponding to content is generated and the generated content key is transmitted to a mobile terminal but an embodiment is not limited thereto and it would be obvious to one of ordinary skill in the art that an identifier corresponding to content may be generated and the generated identifier may be transmitted to a mobile terminal.

If a user wants to upload a job regarding content by using the mobile terminal the content related to the job is first successfully uploaded to the cloud server as shown in regardless of a destination of the job and a type of the job. Once the content is successfully uploaded the mobile terminal may transmit the job upload request as shown in . As described above the mobile terminal may determine that the content is successfully uploaded by receiving a content key.

Referring to upon receiving a content key after content is successfully uploaded to the cloud server the mobile terminal may transmit the received content key and a job upload request regarding the content to the management server in operation . Here the user of the mobile terminal is unable to recognize that the mobile terminal transmits the job upload request again after an upload request regarding the content is transmitted. In other words when the user inputs the job upload request regarding the content to the mobile terminal the mobile terminal transmits the upload request regarding the content and the job upload request regarding the content to the cloud server.

In operation the management server may transmit a content search request to the content server by using the received content key.

In operation the content server may determine the content corresponding to the content key in response to the content search request. At this time a determination result may be transmitted to the management server . The determination result may include metadata a file name or a file size of the content determined in the content server .

In operation when the management server receives the determination result from the content server and determines that the content exist the management server may generate job data regarding the content. In detail the management server may generate and manage a job table.

In the current embodiment it is assumed that a user uploads a job to an individual cloud space assigned to the user. Here unlike when a job is transmitted to another user the user does not have to separately input a mobile terminal ID information for example a phone number . The mobile terminal may determine mobile terminal ID information embedded in a USIM chip and transmit the mobile terminal ID information together with the job upload request regarding the content. The management server may check a space corresponding to the mobile terminal ID information by using the mobile terminal ID information and generate a job in the checked space. In the current embodiment it is assumed that a job table is stored in the space corresponding to the mobile terminal ID information. In other words it would be obvious to one of ordinary skill in the art that the management server separately stores a table wherein mobile terminal ID information and a storage space are mapped to each other and the storage space is managed by using the table.

First the management server generates a job identifier. In the current embodiment since there is no job uploaded to the management server the generated job identifier is 1 . The management server may map a content key to a job identifier. For example the management server may generate the job identifier 1 and store a content key abc corresponding to content stored according to the job identifier 1 in the same row of a job table as the job identifier 1 . Here the management server may map and additionally store the metadata included in the determination result and the content key in the same row as the job identifier 1 .

The user does not want to directly print content but uploads the content to be printed in the cloud server and prints the content whenever the user wants to by accessing the cloud server.

Although not shown in it would be obvious to one of ordinary skill in the art that a name of a file content corresponding to the content key may also be stored in the job table.

In the current embodiment it is assumed that a user directly prints content by using an image forming apparatus registered in the cloud server.

Here the user may request for and receive a list of image forming apparatuses pre registered in the cloud server by using the mobile terminal and select an image forming apparatus from the list. The cloud server may manage the image forming apparatuses pre registered in the cloud server by assigning image forming apparatus identifiers to the image forming apparatuses according to mobile terminal ID information. When the user selects content to be printed and an image forming apparatus for printing the content by using the mobile terminal first as shown in the mobile terminal transmits an upload request regarding the content to the management server and receives a content key corresponding to the content if the content is successfully uploaded to the cloud server.

Referring to in operation the mobile terminal may transmit a print request to the management server together with the received content key and an image forming apparatus identifier.

In operation the management server may transmit a content search request to the content server to search for content by using the content key corresponding to a received job identifier.

In operation the content server may extract the content corresponding to the content key in response to the content search request and transmit the extracted content to the management server . The management server may receive the content from the content server . Here the extracted content may also contain metadata a file name or a file size of a file including the extracted content.

In operation the management server may check the received content to determine that the content requested to be uploaded exists and generate job data. In detail the management server may generate a job identifier and then generate a job table by mapping the job identifier and a content key corresponding to content. In the current embodiment it is assumed that a job is first generated in the cloud server and thus the management server may generate a job table including a job identifier 1 and a content key abc in the same row. Here metadata of a file including content may also be mapped to a content key and stored in the same row.

In operation the management server may transmit a rendering request regarding the received content to a rendering server . While transmitting the rendering request information about an image forming apparatus corresponding to the image forming apparatus identifier received from the mobile terminal may also be transmitted. The rendering server may perform rendering on the content. In detail the rendering server may convert the content to print data such that the content is printed in the image forming apparatus . Here the print data may be data including a command interpretable by the image forming apparatus .

In operation the rendering server may transmit the rendered content to the image forming apparatus corresponding to the image forming apparatus identifier. The image forming apparatus may perform an image forming job on the rendered content by receiving the rendered content from the rendering server .

Referring to the user may additionally input a phone number of the other user by using the mobile terminal in order to transmit a print job regarding content to the other user. First as described above with reference to the mobile terminal transmits an upload request regarding the content to the management server . After the content is successfully uploaded to the cloud server the mobile terminal may receive a content key corresponding to the uploaded content.

In operation the mobile terminal may transmit a print job upload request to the management server together with the phone number of the other user and the content key. For example when the user selects the content and inputs the phone number 010 yyy yyyy of the other user by using the mobile terminal the mobile terminal may transmit the upload request regarding the selected content to the cloud server and receive the content key corresponding to the uploaded content from the cloud server if the content is successfully uploaded to the cloud server. The mobile terminal may transmit the job upload request regarding the uploaded content together with the received content key and the phone number 010 yyy yyyy of the other user.

In operation the management server may transmit a content search request to the content server to search for the content by using the content key. The content server may receive the content search request from the management server .

In operation the content server may check the content stored in the content server corresponding to the content key in response to the content search request. The content server may transmit a content check result to the management server .

In operation the management server may receive the content check result from the content server . Upon receiving the content check result the management server may determine that the content exists and generate job data regarding the content.

Here the management server searches for a storage space corresponding to the phone number of the other user received from the mobile terminal . The management server may use a mapping table generated by mapping storage spaces of the management server and pre registered phone numbers to each other.

The management server may generate a job identifier. For example since the management server generates a job for the first time in the storage space of the phone number 010 yyy yyyy i.e. the storage space of the other user the job identifier may be 1 .

The management server may map the content key to the job identifier. For example the management server may map a content key abc corresponding to the uploaded content to the job identifier 1 . The management server may store the job identifier and the content key in one row of the job table. Referring to the job table includes a phone number field to indicate to which phone number a job identifier is mapped but the job table may not include the phone number field as long as the job table is stored in a storage space of a certain phone number . On the other hand if storage spaces are not divided according to phone numbers the management server may generate a job table including a phone number field to indicate a phone number a job is destined for.

In operation the other user may transmit a job list confirmation request regarding a print job corresponding to the phone number 010 yyy yyyy of the other user to the management server by using a mobile terminal having the phone number 010 yyy yyyy . Here the mobile terminal may check the phone number 010 yyy yyyy of the other user embedded in a USIM chip of the mobile terminal and transmit the checked phone number 010 yyy yyyy while transmitting the job list confirmation request.

Upon receiving the job list confirmation request from the mobile terminal the management server may search for a storage space corresponding to the phone number 010 yyy yyyy and generate in the storage space a job list based on the job included in the job table. Here the job list may not include the content key included in the job table.

In operation the other user may receive the job list from the management server by using the mobile terminal . The other user may select one of jobs included in the received job list by using the mobile terminal . The other user may transmit a preview or print request regarding the selected job to the management server so as to receive preview data regarding content related to the selected job or to print the content related to the selected job by using an image forming apparatus registered in the cloud server. The receiving of the preview data or the printing of the content by transmitting the preview or print request to the cloud server will now be described in detail with reference to .

Referring to the user B may transmit a job list confirmation request to the cloud server by using the mobile terminal and select a job from a job list received from the cloud server. Also the user B may transmit a image forming apparatus list request to the cloud server by using the mobile terminal to receive an image forming apparatus list including image forming apparatuses pre registered in the cloud server. The user B may select the image forming apparatus to perform the image forming job regarding the content from the image forming apparatus list by using the mobile terminal .

In operation the mobile terminal may transmit a print request to the management server together with a job identifier indicating a job and an image forming apparatus identifier indicating the image forming apparatus which are selected by the user B.

In operation the management server may obtain a content key from job data by using the job identifier received from the mobile terminal . In detail the management server may refer to a job table to obtain the content key from a content key field in the same row as the job identifier. For example the management server may obtain a content key abc in a content key field of the same row as a job identifier 1 by referring to the job table.

In operation the management server may transmit a content search request to the content server to search for content by using the content key obtained according to the job identifier. The content server may search for the content corresponding to the content key in response to the content search request.

In operation the content server may search for the content corresponding to the content key and transmit searched content to the management server .

In operation the management server may receive the content from the content server and transmit a rendering request regarding the content to the rendering server . Here the management server may transmit information about the image forming apparatus corresponding to the image forming apparatus identifier received from the mobile terminal to the rendering server together with the rendering request.

In operation the rendering server receives the rendering request from the management server and performs rendering on the content included in the rendering request. In detail the rendering server converts the content to print data including a print command regarding the content so that the image forming apparatus performs the image forming job on the content. The rendering server may transmit the rendered content to the image forming apparatus by using the information about the image forming apparatus corresponding to the received image forming apparatus identifier. The image forming apparatus may receive the rendered content from the rendering server and perform the image forming job on the rendered content based on the rendered content.

Referring to in operation the user B receives a job list stored in a storage space corresponding to the phone number of the mobile terminal from the management server by using the mobile terminal . Here the job list may include a job identifier corresponding to an uploaded job.

In operation the user B may select one of jobs included in the job list by using the mobile terminal . Here the mobile terminal may transmit a preview request to the management server together with a job identifier corresponding to the job selected by the user B.

In operation the management server may obtain a content key from job data by using the job identifier received together with the preview request from the mobile terminal . In detail the management server may obtain the content key from a content key field in the same raw as the job identifier by referring to a job table. For example the management server may obtain a content key abc in a content key field in the same row as a job identifier 1 by referring to the job table.

In operation the management server may transmit a content search request to the content server to search for content by using the content key corresponding to the job identifier. The content server may receive the content search request from the management server and search for the content corresponding to the content key in response to the received content search request.

In operation the content server may transmit searched content corresponding to the content key to the management server .

In operation the management server may receive the searched content from the content server and transmit a preview data generate request to a preview server to generate preview data regarding the received content. Upon receiving the preview data generate request the preview server generates the preview data regarding the content. In detail the preview server may include various types of contents and may convert such content to an image file JPG or PNG files supported by a web browser such that the content is previewed by a user using the web browser regardless of an operating system of the mobile terminal and without having to separately install a plug in in the mobile terminal . Here the image file may be preview data. Alternatively any type of data obtained by converting content to be previewed by a user may be preview data.

In operation after generating the preview data regarding the content the preview server may generate the preview data to the content server to be stored. Upon receiving the preview data from the preview server the content server may store the preview data and provide a URL of the preview data to the preview server such that the user B may access the preview data by using a web browser.

In operation the preview server may transmit the URL of the preview data provided from the content server to the management server .

In operation the management server may transmit the URL of the preview data received from the preview server to the mobile terminal .

In operation the mobile terminal may receive the URL of the preview data from the management server and access the preview data stored in the content server by using the received URL. The user B may view the preview data via a display of the mobile terminal .

According to the current embodiment for example a user does not have to install a separate program to a mobile terminal so as to preview a file edited by a certain program by using the mobile terminal and thus the user may receive and preview content from a cloud server without having to install the separate program to the mobile terminal.

Referring to the user of the mobile terminal transmits a print job upload request regarding content to the cloud server by using the mobile terminal . Here the cloud server first authenticates the mobile terminal so as to determine that the user is using a mobile terminal corresponding to mobile terminal ID information. Here the cloud server includes the management server and the authentication server .

In operation the user may transmit an authentication request to the management server by using the mobile terminal . Here even if the user does not input the phone number of the mobile terminal the mobile terminal may check the phone number embedded in the USIN chip of the mobile terminal and transmit the checked phone number to the management server together with the authentication request.

In operation the management server may transmit the authentication request to the authentication server . Here the management server may transmit the received phone number of the mobile terminal to the authentication server together with the authentication request.

In operation the authentication server may generate a PIN code correspondingly to the received phone number.

In operation the authentication server may request a short message service SMS provider to transmit an SMS message including the generated PIN code to the mobile terminal . The SMS provider may be a communication carrier. In this case the SMS provider may be located outside the cloud server.

In operation the SMS provider may transmit the SMS message including the generated PIN code to the mobile terminal .

In operation after the mobile terminal received the SMS message the user may transmit a PIN code confirmation request to the management server by inputting a PIN code that is the same as the PIN code included in the SMS by using the mobile terminal .

In operation the management server may receive the PIN code confirmation request from the mobile terminal and transmit the received PIN code confirmation request to the authentication server .

In operation the authentication server may receive the PIN code confirmation request from the management server determine whether the PIN code included in the PIN code confirmation request and the PIN code generated and received in operations through are the same and if the PIN codes are the same issues an access token corresponding to the phone number of the mobile terminal .

In operation the authentication server may transmit the issued access token to the management server .

In operation the management server may receive the access token from the authentication server and transmit the received access token to the mobile terminal .

In operation the mobile terminal may receive the access token from the management server and transmit an upload request regarding the content to the management server together with the received access token. Here upon receiving the upload request from the mobile terminal the management server may determine whether the access token is proper. In other words the management server transmits the access token to the authentication server and the authentication server determines whether the transmitted access token is issued by itself. Also the authentication server determines whether the issued access token is generated by authenticating the phone number of the mobile terminal . As such the authentication server determines whether the access token is proper and transmits a determination result to the management server . The management server may receive the determination result from the authentication server to check whether the access token is proper and if the access token is proper the management server processes the upload request transmitted together with the access token. In the current embodiment only the upload request is transmitted together with the access token but alternatively any request transmitted from the mobile terminal to the management server may be transmitted together with the access token and the authentication server may determine whether the access token is proper.

Referring to the cloud printing system according to an embodiment includes the mobile terminal the cloud server an SMS provider the image forming apparatus and a personal computer PC .

The cloud server denotes several servers immediately supporting a client with settable computing resources a network a server a storage space an application system and service through a network whenever the user requires the settable computing resources such that the settable computing resources are easily accessed through the network. In detail according to the current embodiment the cloud server denotes servers providing computing resources so as to provide a cloud printing service to the client.

Referring to the cloud server may include an API server a content server a database an authentication server a rendering server a preview server a fetching server and a web server .

The API server is a server that provides a client service function to the client in a form of RESTful API so as to provide the cloud printing service to the client. Accordingly the API server may receive a cloud printing service function through the RESTful API of the API server . Here the RESTful API is an interface that basically provides jobs of generating reading modifying and deleting data.

The content server is a server that includes a storage space for content. The content server performs the same functions as the content server . In other words the content server may not divide a storage space according to users but store content in one storage space generate a content key corresponding to the content and manage the stored content by using a job table wherein the content key corresponding the content and a job identifier are mapped to each other.

The database provides a storage space for job data. In detail the database may assign the storage space according to users. The database may store a job table in the storage space assigned according to users. The job table may include a job identifier and a content key mapped to the job identifier.

Here a storage space assigned according to users indicates that a storage space is assigned to correspond to mobile terminal ID information. Here the mobile terminal ID information includes a phone number a country code and a mobile hardware ID a unique value for classifying a mobile terminal of a user. Alternatively the storage spaces may not be assigned according to users but the mobile terminal ID information may be mapped to the job identifier and included in the job table such that the database is managed without having to use storage spaces divided according to users or mobile terminals. The job table may be stored in a storage space according to users and include a job assigned to users but alternatively jobs transmitted from a user to other users may be stored in a storage space according to the transmitted users in a form of a job history table.

Also the database may store various types of information generated by the API server the authentication server the fetching server and the web server .

When the user transmits an authentication request regarding a phone number by using the mobile terminal the authentication server may issue a PIN code regarding the authentication request. Also the authentication server may verify validity of the PIN code. Also when the authentication server determines that the PIN code is valid by verifying the validity of the PIN code in response to the authentication request the authentication server may issue an access token. Then the authentication server may verify validity of the access token when the user transmits various requests together with the access token by using the mobile terminal to receive a cloud printing service. The authentication server may link and manage a user account and a phone number of a mobile terminal. Here the linking and managing mean that a user account is managed after being mapped to phone numbers of several mobile terminals. For example a user account samsung may be mapped to phone numbers of a plurality of mobile terminals and at this time if the user transmits an authentication request regarding the user account samsung to the authentication server by using the mobile terminal since the user account samsung is mapped to the phone numbers of the plurality of mobile terminals not only a job of the mobile terminal but also jobs of the plurality of mobile terminals may be provided to the user.

Upon receiving a rendering request regarding content from the API server the rendering server may render the content stored in the content server . Here the rendered content may be obtained by converting the content to print data including a print command regarding the content such that the image forming apparatus may print the content. The rendering server may transmit the rendered content to the image forming apparatus and the image forming apparatus may receive the rendered content from the rendering server and perform an image forming job on the content by using the received rendered content.

Upon receiving a preview request regarding the content stored in the content server from the API server the preview server may generate preview data regarding the content. Here the preview data may be obtained by converting the content to an image file JPG or PNG supported by a web browser so that the content is previewed on the mobile terminal . The preview server may transmit a storage request regarding the preview data to the content server to store the preview data receive a URL of the stored preview data from the rendering server and provide the URL to the mobile terminal . Thus the mobile terminal is able to access the preview data by using the URL received from the preview server and the user is able to preview the content upon receiving the preview data by using the mobile terminal .

The fetching server is a server that tracks state information of the rendering server or the preview server and if the rendering server or the preview server receives a rendering request or a preview request regarding content from the API server the fetching server may receive the state information of the rendering server or the preview server from the rendering server or the preview server to determine a current job state related to the content in the rendering server or the preview server . The determined current job state is transmitted to the mobile terminal through the API server for the user to check the current job state.

The web server is a server that provides a user portal service in a form of a web service and provides a web service on the assumption that a user account of a user portal is linked to a phone number of a mobile terminal. For example when the user may execute a web browser by using the PC access a user portal website to authenticate a user account and if the user account is successfully authenticated view a job and a job history related to the mobile terminal linked to the user account through the web browser. Also the user may check a registration state of the image forming apparatus corresponding to the phone number of the mobile terminal linked to the user account and then may register an additional image forming apparatus or set the image forming apparatus as a basic image forming apparatus.

On the other hand the mobile terminal the image forming apparatus and the PC may communicate with the cloud server by using an HTTP or a hypertext transfer protocol secure HTTPS . The API server may communicate with the database by using a transmission control protocol TCP . The web server may communicate with the database by using a TCP.

The API server may communicate with the content server the authentication server the rendering server and the preview server by using an HTTP HTTPS. The fetching server may communicate with the rendering server and the preview server by using an HTTP HTTPS. The authentication server may communicate with the SMS provider by using a TCP.

In operation the cloud server may receive a user input indicating a job request regarding content from the mobile terminal .

In operation upon receiving the user input from the mobile terminal the cloud server may store the content according to the user input.

In operation when the content is stored the cloud server may generate a key corresponding to the content and obtain the generated key. In operation the cloud server may transmit the key to the mobile terminal .

In operation the cloud server may receive the job request from the mobile terminal together with the key from the mobile terminal .

In operation the cloud server may perform a job on the content corresponding to the key according to the job request received from the mobile terminal .

The cloud server may include the management server and the content server . Accordingly when the cloud server stores the content data may be exchanged between the management server and the content server .

In operation upon receiving the user input indicating the job request regarding the content from the mobile terminal the management server may transmit a store request regarding the content to the content server .

In operation the content server may store the content according to the store request received from the management server .

In operation the content server may generate a key corresponding to the content stored in the content server . The content server may transmit the generated key to the management server .

In operation the management server may receive the key from the content server . The management server may obtain a content key by receiving the key from the content server .

In operation the cloud server may generate a job identifier corresponding to the job request received from the mobile terminal .

In operation the cloud server may store the job identifier after mapping the job identifier to the key.

In operation the cloud server may receive the job identifier from the mobile terminal . Here the cloud server may receive the job identifier input by the user of the mobile terminal from the mobile terminal .

In operation the cloud server may receive the job identifier from the mobile terminal obtain a key mapped according to the received job identifier and obtain content by using the content key.

Referring to in operation the management server may receive the job identifier from the mobile terminal .

In operation the management server may obtain the key corresponding to the job identifier and request the content server to transmit the request regarding the stored content including the obtained key corresponding to the job identifier. Upon receiving the request from the management server the content server may determine whether the content corresponding to the key is stored in the content server .

In operation the management server may receive the content corresponding to the key from the content server .

It is assumed that the mobile terminal transmits a job upload request regarding content to the cloud server wherein the job upload request is destined for mobile terminal ID information of another mobile terminal and when the cloud server generates a job identifier according to the job upload request the job identifier is mapped to the mobile terminal ID information of the other mobile terminal. Here mobile terminal ID information may be a phone number of a mobile terminal. When a job uploaded to the cloud server is to be performed the other mobile terminal that is a destination requests the cloud server to transmit job identifiers mapped to the mobile terminal ID information of the other mobile terminal selects one of the received job identifiers and transmits a request including the selected job identifier to the cloud server such that the cloud server performs the job on the content. Here the job performed on the content may be transmitting the content to an image forming apparatus corresponding to the mobile terminal ID information such that the image forming apparatus performs an image forming job on the content or may be generating preview data of the content storing the generated preview data and transmitting location information for example a URL of the stored preview data to the other mobile terminal such that the other mobile terminal previews the content.

If the destination of the job to be uploaded is mobile terminal ID information of the mobile terminal that requested the job upload request the other mobile terminal may be the mobile terminal .

In operation the cloud server may receive a confirmation request regarding a job identifier stored in the cloud server from a mobile terminal corresponding to mobile terminal ID information. Here the stored job identifier may be mapped to the mobile terminal ID information and the cloud server may check the job identifier corresponding to the mobile terminal ID information.

In operation the cloud server may transmit a job list including job identifiers corresponding to the confirmation request to the mobile terminal corresponding to the mobile terminal ID information.

In operation the cloud server may receive a print job request including at least one of the job identifiers included in the job list from the mobile terminal corresponding to the mobile terminal ID information.

In operation the cloud server may obtain a key corresponding to the job identifier included in the print job request.

In operation the cloud server may obtain content by using the key corresponding to the job identifier.

In operation the cloud server may transmit the obtained content to the image forming apparatus corresponding to the mobile terminal ID information such that the image forming apparatus performs an image forming job on the obtained content.

In operation the cloud server may receive a confirmation request regarding a job identifier stored in the cloud server from a mobile terminal corresponding to the mobile terminal ID information. Here the stored job identifier may be mapped to the mobile terminal ID information and the cloud server may check the job identifier corresponding to the mobile terminal ID information.

In operation the cloud server may transmit a job list including job identifiers corresponding to the confirmation request to the mobile terminal corresponding to the mobile terminal ID information.

In operation the cloud server may receive a content preview request including at least one of the job identifiers included in the job list from the mobile terminal corresponding to the mobile terminal ID information.

In operation the cloud server may obtain a key corresponding to the job identifier included in the content preview request.

In operation the cloud server may obtain content by using the key corresponding to the job identifier.

In operation the cloud server may transmit location information about the preview data to the mobile terminal corresponding to the mobile terminal ID information such that the mobile terminal displays the preview data. Accordingly the mobile terminal that transmitted the content preview request may receive the location information about the preview data and access the preview data based on the location information. Thus the user of the mobile terminal may preview the content.

In the current embodiment it is assumed that the user uses a cloud printing service through the mobile terminal for the first time.

In operation the cloud server may generate a PIN code corresponding to mobile terminal ID information based on the authentication request. Here the PIN code corresponding to the mobile terminal ID information may be a phone number of the mobile terminal .

In operation the cloud server may transmit a message including the PIN code to the mobile terminal . The cloud server may request an SMS provider to transmit the message to the mobile terminal . Then the SMS provider may transmit the message according to the request of the cloud server .

In operation the cloud server may receive a PIN code confirmation request including a PIN code from the mobile terminal in response to the message.

In operation if the PIN code included in the PIN code confirmation request is the same as the PIN code included in the message the cloud server generates an access token corresponding to the mobile terminal ID information and obtains the generated access token.

In operation the cloud server may receive a user input indicating a job request regarding content from the mobile terminal together with the access token.

As such according to the current embodiment a user is able to use a service by authenticating a phone number without having to separately subscribe to the service.

According to another embodiment if data is stored in a storage space of the cloud server for a long period of time a service provider may have to spend additional costs based on a storage period and may have a reduced usable storage space. Also most data stored in the cloud server are useless after about one day. Thus the cloud server may be set to store content and a job only for a predetermined period of time. For example the cloud server may store the content and the job for 24 hours. Here a user who is using a cloud printing service may need to check remaining times of content and a job before deleting the content and the job.

Hereinafter a method of easily checking by a user remaining times of content and job through a mobile terminal by displaying the remaining times on a UI of the mobile terminal in graphics when the user is using a cloud printing service via the mobile terminal according to an embodiment will now be described in detail with reference to .

Referring to the user executes an application regarding a cloud printing service by using the mobile terminal . When the application is executed an initial screen is displayed as shown in the left of . When a My Cloud menu is selected from the initial screen a My Cloud screen is displayed as shown in the right of . Jobs related to the mobile terminal are displayed on the My Cloud screen. The user may check a remaining time graphic and a remaining time together with the jobs related to the mobile terminal .

Referring to the remaining time graphics and the remaining times displayed on the mobile terminal are illustrated.

Referring to the remaining time graphic and the remaining time at the top of current content is just uploaded and the remaining time is 24 hours and thus bar regions of the remaining time graphic may be displayed in a light color. Also the remaining time may be displayed as 24 00 to show that 24 hours are left. Here a time may be expressed in HH mm . Here HH denotes a currently remaining hour and mm denotes a currently remaining minute.

Referring to the remaining time graphic and the remaining time shown first at the bottom of 1 hour has passed after the current content is uploaded and thus the remaining time is 23 hours and the bar regions of the remaining time graphic may still be displayed in the light color. Here the remaining time graphics when the remaining time is 24 hours and when the remaining time is 23 hours are displayed in the same form because one bar region indicate 2 hours and 2 hours are not passed yet. Alternatively a part of the bar region may be changed to a dark color according to time.

Referring to the remaining time graphic and the remaining time shown second at the bottom of 2 hours have passed after the current content is uploaded and thus the remaining time is 22 hours and one of the bar regions of the remaining time graphic may be displayed in a dark color. Also the remaining time may be displayed as 22 00 to show that 22 hours are left. When the remaining times are 18 hours and 12 hours the remaining time graphics and the remaining times may be displayed on the mobile terminal as shown third and fourth at the bottom of .

Referring to a cloud print service system according to an embodiment may include mobile terminals namely first and second mobile terminals and multi function printers MFP namely MFP and MFP and and a cloud server .

Here it is illustrated that the first and second mobile terminals and are smartphones. However the first and second mobile terminals and may also be a tablet PC or a notebook computer and the MFPs may also include various kinds of image forming devices such as a printer a scanner and a fax machine.

An application for using a cloud print service may be installed on the mobile terminals first and second and . At this time the application may be made by a provider of the cloud print service or a third party. Furthermore the first and second mobile terminals and may be registered as devices which may use the cloud print service in the cloud server by installing the application.

The MFP and MFP and as well as the first and second mobile terminals and may be registered as devices which may use the cloud print service in the cloud server . At this time the MFP and MFP and are registered in the cloud server in order to correspond to the phone numbers of the first and second mobile terminals and . Furthermore the registration of the MFP and MFP and may be simply performed through near field communication NFC in the state where the application is executed as described in detail when describing the drawings illustrating UI screens.

A method of providing a cloud print service according to an embodiment will be described below with reference to .

A first user installs an application on the first mobile terminal so that the first mobile terminal may be registered as a device which may use a cloud print service in the cloud server .

Furthermore the first user allows the MFP to be registered in the cloud server by performing NFC tagging on the MFP in the state where the application is executed in the first mobile terminal . In detail in the state where a UI screen for device registration of the application is displayed on a display unit of the first mobile terminal if the first mobile terminal NFC tags the MFP the MFP is registered in the cloud server as the device corresponding to the phone number of the first mobile terminal .

Likewise if the first mobile terminal and MFP are registered in the cloud server the first user may perform printing by NFC tagging the first mobile terminal to the MFP .

Furthermore the second user may also register the second mobile terminal and the MFP as devices which may use the cloud print service in the cloud server in the same manner as that by the first user . At this time the MFP may be registered in the cloud server to correspond to the phone number of the second mobile terminal as described above.

If the registration of devices is completed the first user may print print data stored in the first terminal or transmit the print data to the second user through the cloud server .

In detail the first user may select print data from among print data stored in the first mobile terminal and tag the first mobile terminal to the MFP so that the print data may be promptly printed. At this time in the state where the UI screen for printing of the application is displayed if the NFC tagging to the MFP is performed the printing job is promptly performed in the MFP .

Furthermore the first user may store print data in the cloud server to correspond to the phone number of the first user i.e. the phone number of the first mobile terminal and NFC tag the first mobile terminal to the MFP at a desired point of time so as to print the print data stored in the cloud server .

Furthermore the first user may transmit print data stored in the first mobile terminal to the second user . In detail after the first user selects print data to be transmitted on the executed application in the first mobile terminal if the print data is transmitted using the phone number of the second mobile terminal of the second user as the destination the selected print data is stored in the cloud server to correspond to the phone number of the second mobile terminal .

Then the second user may check print data which is received after executing the application in the second mobile terminal i.e. print data which is stored in the cloud server to correspond to the phone number of the second mobile terminal of the second user . Furthermore the second user may select data to be printed from among received print data and NFC tag the second mobile terminal to the MFP so as to print the print data stored in the cloud server .

In detail the second user checks and selects print data which is received on the UI screen for performing printing of the application displayed on the second mobile terminal and NFC tags the second mobile terminal to the MFP in the state where the UI screen for printing is displayed. Then the selected print data is printed in the MFP .

Hereinafter the method of providing a cloud print service by using a mobile application according to an embodiment will be described below in detail with reference to UI screens of the application which is displayed on a mobile terminal.

Referring to a first UI screen for selecting and registering an image forming device displays a list of registered devices that correspond to the user s mobile terminal and a list of phone numbers of other users which use the cloud print service. A check box displays a basic device and it may be understood that My Cloud Printer has been set as the basic device in the first UI screen

In the state where the first UI screen is displayed on the display unit of the mobile terminal if the mobile terminal NFC tags the image forming device a second UI screen is displayed on the mobile terminal. A pop up window in which whether to register a tagged device is asked is displayed on the second UI screen

If the OK button is selected from the pop up window displayed on the second UI screen an input blank field for inputting the name of the device registered in the pop up window in a third UI screen is displayed. A model name of the registered device is basically displayed on the input blank and if the user desires to register the device with another name the user may directly input the desired name.

If the OK button is selected from the pop up window displayed on the third UI screen a fourth UI screen is displayed. In the fourth UI screen a newly registered image forming device has been added to the list of registered devices. At this time the check box is displayed on the newly registered image forming device and thus it is understood that the device has been set as a basic device. Likewise when a new device is registered the device may be set as a basic device.

Referring to a list of registered devices that correspond to the user s mobile terminal and a list of phone numbers of other users which use the cloud print service are displayed on a first UI screen via which selection and registration of devices is performed. A check box displays a basic device.

If an additional menu display button is touched in a second UI screen additional menu items such as a third UI screen are displayed. If an Add device with NFC item is selected from the menu items a pop up window which guides on the method of registering a device through NFC is displayed on a fourth UI screen

The user may register a device by NFC tagging the mobile terminal to an image forming device according to the guidance of the pop up window . The following process is similar to the process described with reference to .

Referring to a first UI screen is a UI screen via which the selection and registration of devices is performed and that displays a list of registered devices that correspond to the user s mobile terminal and a list of phone numbers of other users which use the cloud print service. If My Cloud Printer is selected from the list a second UI screen is displayed.

The second UI screen is a screen where Start Print is selected from among menu items of Start Print Get Print and Send Print . The second UI screen is a UI screen for transmitting print data to perform a printing job. The user may select the category of print data to be uploaded from the second UI screen . In the present embodiment an album has been selected. As such a list of albums is displayed on a third UI screen . If Album Name is selected from among the displayed albums image files included in the Album Name are displayed on a fourth UI screen . If one of the image files for example an image file is selected from among the image files displayed on the fourth UI screen a fifth UI screen of is displayed.

Referring to a checkbox is displayed on the image file which is selected from among the image files in the fifth UI screen which indicates that the image file has been selected. Here it is illustrated that only one image file has been selected but two or more image files may also be selected. After the selection of an image file is completed if the user touches a print button a pop up window which indicates that data is being uploaded to the cloud server is displayed on a sixth UI screen

If the upload of the print data is completed a pop up window including a message notifying that the upload has been completed is displayed on a seventh UI screen . If Go to Get Print is selected from the pop up window of the seventh UI screen the screen where a Get Print menu item has been selected is displayed on an eighth UI screen and a list of print data uploaded to the cloud server is displayed. Furthermore if an OK button is selected from the pop up window of the seventh UI screen the screen where a Start Print menu item has been selected is displayed on a ninth UI screen

Referring to a first UI screen is a screen where a Send Print menu item has been selected and is a UI screen for transmission of print data. A list of people who have installed the application in a mobile terminal and a list of people who have not installed the application are separately displayed on the first UI screen . An icon which denotes the cloud is displayed on the list of people who have installed the application. Furthermore an invitation message to install an application by selecting one from the list of people who have not installed the application may be transmitted.

Print data may be transmitted to people who have installed the application in the mobile terminal. If a receiver is selected in the first UI screen a checkbox is displayed to the selected receiver as in a second UI screen . Furthermore if the print button is selected in the second UI screen a pop up window which shows categories of print data to be transmitted is displayed on a third UI screen . If a photo is selected from the categories displayed on the pop up window a list of photo albums is displayed on a fourth UI screen

If a receiver icon is selected in the fourth UI screen the first UI screen is displayed again so that the receiver may be selected again. If one album is selected from the list of photo albums displayed on the fourth UI screen a fifth UI screen of is displayed.

Referring to print data to be transmitted is selected in the fifth UI screen and if the print button is selected a pop up window which indicates that the print data is being transmitted is displayed on a sixth UI screen . Furthermore if the transmission of the print data is completed by the passage of a certain time a pop up window which notifies that transmission has been completed is displayed on a seventh UI screen . Here if the OK button is pushed an eighth UI screen is displayed. The eighth UI screen is a UI screen in the state where a Send Print menu item has been selected.

Furthermore here the fact that print data has been transmitted to the receiver actually refers to print data being uploaded to the cloud server to correspond to a phone number of the mobile terminal of the receiver. The receiver may check print data uploaded to the cloud server and perform a printing job by executing the application from the receiver s mobile terminal.

Referring to a first UI screen is a UI screen in the state where a Get Print menu item has been selected. A list of print data to be printed is displayed on the first UI screen . The print data displayed in the list is files which are stored in the cloud server.

If print data to be printed is selected by the user in a second UI screen and the mobile terminal NFC tags the image forming device in the state where the application screen is displayed a pop up window which indicates that the print data is being transmitted from the cloud server to the image forming device is displayed on a third UI screen . Furthermore if the printing of the selected print data is completed with the passage of a certain time a fourth UI screen is displayed. A message that the printing has been completed is displayed on the fourth UI screen . Furthermore a list of print completed data disappears from a list of the print data and print data which is waiting for printing is displayed.

Referring to a first UI screen is a UI screen in the state where a Get Print menu item has been selected. A list of print data to be printed is displayed on the first UI screen . The print data displayed in the list is files which are actually stored in the cloud server.

If the mobile terminal NFC tags the image forming device in the state where the first UI screen is displayed on the mobile terminal all print data in the list is selected. A second UI screen shows that all print data has been selected. Furthermore if the mobile terminal NFC tags the image forming device again in the state the second UI screen has been displayed the printing of the selected print data is performed. A pop up window which indicates that the print data is being transmitted from the cloud server to the image forming device is displayed on a third UI screen and if the printing job is completed with the passage of a certain time a message which notifies that the printing has been completed is displayed on a fourth UI screen

In detail illustrates an animation which is displayed when uploading print data to the cloud server to correspond to the user s mobile terminal. Referring to a pop up window which indicates that print data is being uploaded to the cloud server is displayed on a first UI screen and if the upload is completed with the passage of a certain time a pop up window which shows an animation indicating that the upload of the print data has been completed is displayed on a second UI screen

Referring to in operation S an application for using the cloud print service in a mobile terminal is executed. In operation S an image forming device is registered in a cloud server through NFC tagging in a state where a UI screen for device registration of the application is displayed. In operation S print data stored in the mobile terminal is uploaded to the cloud server in the UI screen for transmission of print data. Lastly in operation S in the state where the UI screen for performing printing is displayed data stored in the cloud server is printed through NFC tagging.

Referring to an upload command of print data is received in operation S. In operation S print data to be uploaded is selected. In operation S the selected print data is stored in the cloud server to correspond to a phone number of the mobile terminal.

Referring to the phone number of the receiver to receive print data is selected in the UI screen for transmission of print data in operation S. In operation S the print data to be transmitted is selected. In operation S the selected print data is stored in the cloud server to correspond to the phone number of the receiver.

Referring to in operation S a list of at least one set of print data stored in the cloud server is displayed on a UI screen for performing printing. In operation S print data to be printed is selected from the list of print data. In operation S if the mobile terminal NFC tags the image forming device the print data selected from the cloud server is transmitted to the image forming device so as to be printed.

Referring to in operation S the list of at least one set of print data stored in the cloud server is displayed on the UI screen for performing printing. In operation S if the mobile terminal firstly NFC tags the image forming device all the print data displayed in the list is selected. In operation S if the mobile terminal secondly NFC tags the image forming device the selected print data is printed in the image forming device.

A mobile application for using a cloud print service may be installed in and executed by the first and second mobile terminals and and the first and second mobile terminals and may be registered in the cloud print service. In detail when the mobile application is installed in the first and second mobile terminals and and goes through a predetermined registering process a user account is generated under a phone number of each of the first and second mobile terminals and and thus the first and second mobile terminals and are registered in the cloud print server .

Examples of the output devices include all devices that support various types of outputs such as the image forming apparatus and the TV . The image forming apparatus supports an output in a printing form and the TV supports an output in a display form. Since examples of content used in the cloud print service generally include texts and images such as documents and photos the output device may be any device supporting an output of such content. For example the output device may be a device capable of outputting an image such as a monitor or a laptop or a device capable of a print output such as a printer or a multi function printer MFP .

The output devices may be registered in the cloud print server to correspond to the phone number of at least one of the first and second mobile terminals and . Also authority for using the output devices registered in the cloud print server is assigned to the user account of the corresponding phone number. For example when the image forming apparatus is registered in the cloud print server to correspond to the phone number of the first mobile terminal a first user having the user account of the phone number of the first mobile terminal has authority for using the image forming apparatus .

When the first and second mobile terminals and are registered in the cloud print service the first and second mobile terminals and may perform cloud printing by transmitting and sharing content to and with another mobile terminal or the output devices registered in the cloud print service. Such an operation may be performed through the mobile application installed in the first and second mobile terminals and and in detail an embodiment suggests a method of transmitting and sharing content through a sharing room.

A user who subscribed to a cloud print service may open a sharing room on a mobile application and invite another user who is subscribed to the cloud print service and an output device that is authorized to be used by the user to the sharing room.

When the second user and the image forming apparatus participate in the sharing room content may be transferred and shared through the sharing room. When the participating is completed participants of the sharing room are displayed on an application screen displayed on a display unit of the first mobile terminal . Here the opening of the sharing room may be simultaneously performed with the inviting or the inviting may be additionally performed while the sharing room is opened. Detailed operations of transmitting and sharing content through a sharing room are described in detail later with reference to drawings regarding user interface UI screens displayed during the corresponding operation.

Referring to the cloud print server according to an embodiment may include a communication interface unit a controller a storage unit a rendering performer and a sharing room manager . Also the cloud print server may selectively include a hypertext mark up language HTML converter .

The communication interface unit is a component for communicating with a mobile terminal and output devices through an Internet or the like.

The controller is a component for controlling operations of other components included in the cloud print server and controls a series of operations for providing a cloud print service.

The storage unit may store account information subscribed to the cloud print service device information registered to correspond to each account and content transferred through the cloud print service.

The rendering performer performs rendering to convert content to a proper format being output by an output device. The rendering performer may be realized as a component included in the cloud print server as shown in or may be realized in a separate server that performs rendering.

The sharing room manager manages a sharing room opened on a mobile application executed in a mobile terminal connected to the cloud print server . For example the sharing room manager transmits a sharing room invitation message to a mobile terminal or manages lists of mobile terminals or output devices participating in a sharing room. Also the sharing room manager stores content transferred or shared through a sharing room in the storage unit or transmits the content to a destination terminal or a device. The sharing room manager may be physically realized in one processor together with the controller .

The HTML converter is a component that is selectively included if required and converts transferred content to an HTML format. Although a layout of a file in an HTML format may sometimes be misaligned but the HTML format is widely used in transferring content since the HTML is conveniently obtained and any device having a web browser is capable of interpreting and displaying an HTML file.

Operations of the components included in the cloud print server in detail the sharing room manager will be described in detail later by referring to UI screens of a mobile application.

Referring to the mobile terminal according to an embodiment may include a communication interface unit a controller a storage unit an application executer and a near field communication NFC module .

The communication interface unit is a component for communicating with a cloud print server through an Internet or the like.

The controller is a component for controlling operations of other components included in the mobile terminal and controls a series of operations for providing a cloud print service using a mobile terminal.

The storage unit may store various contents and may store data required to execute a mobile application. Also the storage unit may store details about option settings on a mobile application.

The application executer is a component for executing a mobile application. The application executer may perform processes for opening a sharing room inviting a user or a device to the sharing room and transferring and sharing content in the sharing room. In detail when a sharing room is opened or a user or a device is invited to the sharing room such information is notified to the cloud print server so that the sharing room is managed. Also when content is transferred or shared through the sharing room content stored in the storage unit may be transmitted to the cloud print server through the communication interface unit the mobile terminal may receive content stored in the cloud print server or content stored in the cloud print server may be transmitted to an output device.

The NFC module is a component that is selectively included if required. The NFC module may be used while registering an output device in the cloud print server. In detail when the mobile terminal tags an NFC tag storing device information of the output device the NFC module obtains the device information stored in the NFC tag. The controller transmits the obtained device information to the cloud print server together with a phone number of the mobile terminal so that the output device is registered as a device corresponding to the phone number of the mobile terminal .

Detailed operations of the components included in the mobile terminal in detail the application executer will be described in detail later by referring to UI screens of a mobile application.

A method of using a cloud print service using a mobile application according to an embodiment will now be described in detail with reference to illustrating UI screens of a mobile application. Here the cloud print server of and the mobile terminal of will also be described.

A first UI screen is a UI screen displayed when a mobile application is initially executed in a mobile terminal after the mobile application is installed. When Phone number is selected from the first UI screen a UI screen for receiving a phone number is displayed as in a second UI screen

When a phone number of the mobile terminal is input to a phone number input box displayed on the second UI screen and Register is selected the mobile terminal is subscribed to a cloud print service by using the phone number as a user account and then a third UI screen is displayed. A list of output devices registrable as device buddies is displayed in the third UI screen . Here a device buddy is a device registered in a server for using a cloud print service.

A registrable output device may be searched for via any one of various methods and for example a device such as a registrable image forming apparatus or TV may be searched for via an access point AP .

When an output device is selected from the list displayed on the third UI screen the selected output device is registered in a cloud print server to correspond to the phone number of the mobile terminal. In an image forming apparatus SCX 621 and a TV Smart TV are selected.

After the mobile terminal subscribes to the cloud print service and the selected output device is registered in the cloud print service a fourth UI screen is displayed. A device buddy list and a buddy list are displayed on the fourth UI screen . As described above a device buddy is a device registered in a server for using a cloud print service and a buddy is another user capable of using the cloud print service. When the mobile terminal initially subscribes to the cloud print service the buddy list may be formed by comparing contacts stored in the mobile terminal with phone numbers registered in the cloud print server and preparing a list of users corresponding to phone numbers matching the contacts. In other words a user who is subscribed to the cloud print service from among people stored in the contacts is registered as a buddy and included in the buddy list .

In the mobile application is executed by the application executer of the mobile terminal . Then when the phone number is input and Register is selected in the second UI screen the application executer transmits the input phone number to the cloud print server through the communication interface unit . The controller of the cloud print server stores the received phone number in a user account table of the storage unit thereby completing account registration.

Also when an output device is selected in the third UI screen the controller maps a media access control MAC address of the selected output device to the phone number of the mobile terminal and stores the MAC address in the storage unit .

After the account registration is completed the cloud print server provides the buddy list to the mobile terminal based on contact information received from the mobile terminal .

A first UI screen of is in a state in which a buddy menu is selected and a device buddy list and a buddy list are displayed. When a buddy add icon is selected in the first UI screen a second UI screen is displayed.

First through fourth menus through of various methods for adding a buddy are displayed on the second UI screen . Also a list of devices registrable as device buddies and a list of users registrable as buddies are displayed below the first through fourth menus through . As shown in when a device SCX 621 is selected from the list the selected device SCX 621 is registered in a cloud print server and a third UI screen is displayed. The device SCX 621 that is already registered is disappeared from a list of registrable devices in the third UI screen

When the buddy menu is selected again after device registration a fourth UI screen is displayed. As shown in the fourth UI screen the newly registered device SCX 621 is added to a device buddy list .

An output device may be registered as a device buddy via any other method. Referring to the second UI screen when the first menu is selected a device buddy is registered according to the method described with reference to . When the second menu is selected a device may be registered by inputting an identification ID or a serial number of the device. When the third menu is selected a device may be registered in a server by reading a quick response QR code storing information about the device. Here if the device is a printer a printer ID and the QR code may be printed on a demo page output after installing the printer.

When the fourth menu is selected a mobile terminal may be NFC tagged to an output device to conveniently register the output device.

In when a device buddy is added the controller of the cloud print server may map an MAC address of the added device buddy to a phone number of the mobile terminal and store the mapped MAC address in the storage unit .

In a first UI screen of a share menu is selected and a list of sharing rooms is displayed. In order to enter one of the sharing rooms a sharing room item is selected from the list . In order to open a new sharing room a sharing room add icon at the right top of the first UI screen is selected. When the sharing room add icon is selected a second UI screen is displayed.

In the second UI screen a screen for selecting a buddy to be invited to the new sharing room is shown. In the second UI screen a device buddy list and a buddy list are displayed. Here a device buddy displayed on the device buddy list may be displayed in a device name such as Smart TV or may be displayed in a device location or model name such as 7th Meeting room SCX 621 . In addition a device buddy may be displayed in any method for identifying the device buddy.

In 7th Meeting room SCX 621 is selected from the device buddy list . As a result a sharing room screen is displayed as in a third UI screen and buddies participating in the new sharing room are shown in a region . In a region menus of operations performable in the new sharing room are displayed. A user may select one of the menus in the region to take a photograph and transmit the photograph directly to the new sharing room to select one of photographs stored in the mobile terminal and transmit the selected photograph to the new sharing room or to select one of documents stored in the mobile terminal and transmit the selected document to the new sharing room. In a document transmit menu is selected from the menus in the region .

When the document transmit menu is selected from the third UI screen and then the user selects a document to be transmitted the document is transmitted to and shared in the new sharing room as in a fourth UI screen . When the document is transmitted a preview of the document is displayed in a form of a thumbnail in the new sharing room. A file name of the document is also displayed in the thumbnail . Also a document output icon is displayed at the bottom of the thumbnail . The user may select the document output icon to output the document corresponding to the thumbnail . Here the document is output by 7th Meeting room SCX 621 that is the device buddy participating in the new sharing room.

In the current embodiment since the device buddy participating in the new sharing room is an image forming apparatus the document is printed according to a document output command but if Smart TV is selected in the second UI screen and participates in the new sharing room the document is displayed on a TV screen corresponding to Smart TV according to attributes of a TV that is an output device.

If a plurality of output devices are participating in the new sharing room a UI screen for receiving a selection on an output device is displayed according to a content output command and the document is output according to attributes of the output device selected by a user.

As such a user may open a sharing room in a mobile application and invite a device buddy to the sharing room thereby conveniently outputting content through the device buddy. Here outputting of the content may be determined according to attributes of an output device participating in the sharing room.

In when a mobile application opens a sharing room the application executer of the mobile terminal notifies the cloud print server about the opened sharing room and the sharing room manager of the cloud print server manages the sharing room. In detail the sharing room manager manages a list of buddies participating in the sharing room and when content is shared in the sharing room receives the content from the mobile terminal and stores the content in the storage unit . Here the content may be converted to an HTML format by the HTML converter and then stored in the storage unit .

Also the sharing room manager provides a thumbnail of a preview of the content to the mobile terminal and if the HTML converter is included in the cloud print server the sharing room manager transmits the content in the HTML format to the mobile terminal and the application executer of the mobile terminal displays the content in the HTML format in the sharing room as the thumbnail .

Also when the document output icon is selected from the fourth UI screen the sharing room manager extracts the content corresponding to the thumbnail from the storage unit and transmits the extracted content to the rendering performer to be rendered.

A share menu is selected from a first UI screen of . Here as described above a list of sharing rooms is displayed. When Carol who is the transmitter selects a sharing room add icon from the first UI screen a second UI screen is displayed.

A screen for selecting a buddy to be invited to a sharing room that is newly opened is shown in the second UI screen . A device buddy list and a buddy list are displayed in the second UI screen

In Carol selects 7th Meeting room SCX 621 from the device buddy list and selects Stella as the receiver from the buddy list . As a result a sharing room screen is displayed as in a third UI screen and buddies participating in the sharing room are displayed in a region . A menu of operations performable in the sharing room is displayed in a region and Carol selects a document transmit menu from among the menus.

When the document transmit menu is selected from the third UI screen and Carol selects a document to be transmitted the document is transmitted to and shared in the sharing room as shown in a fourth UI screen . When the document is transmitted a preview of the document is displayed in the sharing room in a form of a thumbnail . A file name of the document is also displayed in the thumbnail . Also a document output icon is displayed at the bottom of the thumbnail . Here if Carol selects the document output icon from the mobile terminal 7th Meeting room SCX 621 participating in the sharing room prints the document corresponding to the thumbnail as described above with reference to .

A sharing room is displayed on a fifth UI screen of and a thumbnail and a file name of a document shared with buddies participating in the sharing room are displayed. The fifth UI screen is similar to the fourth UI screen of the mobile terminal of Carol described above. However the fifth UI screen further displays a store menu a print menu and a display menu . Stella may select the store menu from the fifth UI screen to store a document file shared in the sharing room in the mobile terminal. Alternatively Stella may select the print menu or the display menu to print or display a shared document.

In when Stella selects the print menu a popup for selecting a device to perform printing is displayed as shown in a sixth UI screen . In only one device is displayed since the number of output devices participating in the sharing room is one but if at least two devices participate in the sharing room the at least two devices may be displayed and one of the at least two devices may be selected to perform printing.

When a device is selected and an OK button is selected in the sixth UI screen a shared document is printed and when the printing is completed a message indicating that the printing is completed is displayed in a region as shown in a seventh UI screen

Operations of the cloud print server and the mobile terminal in are similar to those described above with reference to .

Referring to the sharing room is displayed on the UI screen and a list of buddies participating in the sharing room is displayed in a region . In a region state information of SCX 621 that is a device participating in the sharing room is displayed. The displayed state information includes information about whether a current operation is performable and print option information.

Also a message indicating that the device participating in the sharing room is currently usable such as SCX 621 is Ready is displayed in a region . A user may easily determine option settings and current usability by referring to the state information displayed in the sharing room.

In the sharing room manager of the cloud print server checks option settings and a state of a device participating in a sharing room and transmits the checked option settings and state to the mobile terminal to be displayed in a form of a message.

Referring to in a first UI screen a user selects a display menu so that a document shared in Smart TV that is a device participating in a sharing room is displayed.

When the document is displayed on Smart TV a mobile terminal displays a screen for remotely controlling display of the document as in a second UI screen . In the second UI screen a message indicating that the display is currently controlled is displayed in a region a total number of pages of the document and a currently displayed page number of the document are displayed in a region and a time passed after the document is displayed is displayed in a region . Here the document currently displayed is in a form of a thumbnail .

When the user touches and slides the thumbnail in the second UI screen a screen displaying a next page of the document is shown as in a third UI screen

As such the user may control a displayed screen through a UI screen of a mobile application while a document shared in a sharing room is displayed on a device.

In the application executer of the mobile terminal transmits details of controlling a display on a mobile application to the cloud print server and the sharing room manager transmits a control command to a device according to the received details.

A sharing room is displayed in a first UI screen of a list of buddies participating in the sharing room is displayed in a region and a thumbnail of a shared document is displayed. When a user touches the thumbnail in the first UI screen a function of adding a memo to a document is activated as shown in a second UI screen

The user may add a memo by selecting a memo menu and touching a screen in the second UI screen . Also if the user wants to delete an added memo the user may select a delete menu and touch the added memo.

After the user completes a memo and selects a store menu a popup for selecting a space for storing the document with the memo is displayed as in a third UI screen . In Sharing Window that is an item for sharing in the sharing room is selected. Then a thumbnail of the document with the memo is displayed in the sharing room as in a fourth UI screen . The document with the memo may be output as described above.

In the application executer of the mobile terminal transmits content with a memo to the cloud print server and the sharing room manager extracts the content with the memo in a form of a bitmap and stores the extracted content with the memo in the storage unit .

When a history management menu is selected from a first UI screen thumbnails and that were pre shared and sharing room information and including information about participants and shared times of the sharing room are displayed as in the first UI screen . A user checks the first UI screen to conveniently determine the history of contents shared in the sharing room.

Then when the first UI screen is scrolled down a previous history is displayed as in a second UI screen

If content has been shared before but is currently deleted the thumbnail is displayed dark as shown in a third UI screen . Also if the sharing room is currently deleted the sharing room information is displayed dark as shown in a fourth UI screen

In the sharing room manager of the cloud print server transmits the history of contents shared in the sharing room to the mobile terminal according to a request of the mobile terminal and the application executer receives and displays the history on a screen.

In operation a sharing room is opened by inviting another user subscribed to a cloud print service and an output device registered in a server. Here a device buddy and a buddy to be invited may be selected by using a device buddy list and a buddy list displayed on a UI screen of the mobile application.

Referring to a mobile application is installed in a mobile terminal in operation and a phone number of the mobile terminal is input in a registration screen of the mobile application in operation . When the phone number is input a list of output devices registrable as device buddies are displayed via searching.

When at least one of the output devices is selected in operation the input phone number is registered as a user account and the selected at least one output device is registered in a server to correspond to the phone number in operation .

In operation a sharing room is opened by inviting another user subscribed to a cloud print service and an output device registered in a server. Here a device buddy and a buddy to be invited may be selected by using a device buddy list and a buddy list displayed on a UI screen of the mobile application.

In operation content is transmitted to the other user i.e. a buddy participating in the sharing room.

In operation the transmitted content is output by the output device i.e. a device buddy participating in the sharing room.

In operation a sharing room is opened by inviting another user subscribed to a cloud print service and an output device registered in a server. Here a device buddy and a buddy to be invited may be selected by using a device buddy list and a buddy list displayed on a UI screen of the mobile application.

In operation content is transmitted to the other user i.e. a buddy participating in the sharing room.

As described above according to the one or more of the above embodiments an image forming apparatus supporting a cloud printing service may be easily found and registered in a server by using an augmented reality application. Also device registration of image forming apparatuses adjacent to a mobile terminal may be determined via a Bluetooth communication and a nonregistered image forming apparatus may be registered in the server. Also even when an image forming apparatus does not support an NFC tag the image forming apparatus may be registered in the server via QR code reading.

In operation when the power of the image forming apparatus is turned on the image forming apparatus is connected to the cloud printing server . At this time the image forming apparatus may maintain connection to the cloud printing server according to a long polling connection scheme. On the other hand in the embodiments of the present specification the term cloud printing server may also be used along with the term cloud server for example the term cloud server in or the like .

In operation the image forming apparatus transmits meta information to the cloud printing server so as to identify the image forming apparatus . Here the meta information of the image forming apparatus may contain information including a serial number a MAC address an IP address a product name a manufacturer or the like.

In operation the cloud printing server stores the meta information including the serial number the MAC address the IP address the product name the manufacturer or the like from the image forming apparatus . The cloud printing server may identify the image forming apparatus by using the stored meta information.

In operation the image forming apparatus transmits identification information of the image forming apparatus including the MAC address of the image forming apparatus to the mobile device receiving device for example the mobile device . The image forming apparatus may transmit the MAC address of the image forming apparatus to the mobile device through a P2P connection such as NFC tagging or Bluetooth.

In operation the mobile device maps a phone number of the mobile device to the MAC address of the image forming apparatus so as to register the image forming apparatus as a device designated in the phone number of the mobile device .

In operation the mobile device transmits registration request information including the phone number of the mobile device and the MAC address of the image forming apparatus to the cloud printing server .

In operation the cloud printing server identifies the image forming apparatus by comparing the MAC address included in the meta information stored in operation and the MAC address included in the registration request information received in operation .

In operation when the image forming apparatus is identified by the MAC address of the image forming apparatus the cloud printing server registers the image forming apparatus with regard to the phone number of the mobile device .

In operation the mobile device requests the cloud printing server to transmit the meta information of the image forming apparatus registered to the phone number of the mobile device .

In operation the cloud printing server transmits the meta information of the registered image forming apparatus including the serial number the MAC address the IP address the product name or the manufacturer to the mobile device . Here the transmitted meta information may be the meta information stored in operation .

In operation the mobile device identifies the image forming apparatus registered to the phone number of the mobile device using the serial number the MAC address the IP address the product name or the manufacturer included in the meta information. That is when the mobile device receives an upload notification of content for a cloud printing service from the printing server the mobile device may identify the image forming apparatus as a device for printing the content by using the product name or the like of the image forming apparatus included in the meta information. Here in the embodiments of the present specification the content for the cloud printing service may include a picture photographed by the transmitting device for example the mobile device of an image stored in the transmitting device mobile device of a document stored in the transmitting device mobile device of a webpage displayed on the transmitting device mobile device of and an email displayed on the transmitting device mobile device of .

Referring to in operation the image forming apparatus maintains a session with the print job server by using a long polling connection scheme so as to receive a print job. The print job server is a server that is included in the rendering server and refers to a server that manages rendered content. In particular the rendering server may manage the rendered content by mapping the rendered content to an identifier of the image forming apparatus . Specifically the image forming apparatus maintains the session by transmitting a long polling request to the print job server so as to receive the print job rendered content in a state of being connected to the print job server through a wired wireless network. A time during which the session is maintained may be preset.

In operation when an event corresponding to the long polling request occurs the print job server transmits a response to the long polling request to the image forming apparatus at a point of time when the event occurs. Specifically when a print job mapped to the image forming apparatus is generated by the print job server within the session maintenance time the print job server notifies the reception of the print job to the image forming apparatus through the session connected to the image forming apparatus in a form of a response to the long polling request. The print job may be generated by a fetching server.

In operation when the notification of the print job is received the image forming apparatus may recognize the arrival of the print job and request the print job server for print job information including a file name a file size and a job identifier. At this time in practice the image forming apparatus does not request the print job but requests metadata such as the file name the file size and the job identifier of the print job.

In operation when the request for the metadata of the print job is received from the image forming apparatus the print job server transmits the metadata of the print job which is mapped to the image forming apparatus to the image forming apparatus . The image forming apparatus receives the metadata of the print job that is detailed job information from the print job server .

In operation when the metadata of the print job is received the image forming apparatus may transmit the request for the print job to the print job server .

In operation when the request for the print job is received the print job server may transmit print job data rendered content to the image forming apparatus .

In operation when the print job data is transmitted to the print job server the image forming apparatus requests the print job server to delete the relevant print job from the print job server . Here the image forming apparatus requesting the print job server to delete the print job data so as to prevent the repeated reception of the same print job but the current embodiment is not limited thereto. It is obvious to those of ordinary skill in the art that the request for reducing the printable number of times of the print job may be transmitted to the print job server without directly deleting the print job on the print job server or the print job may not be directly deleted.

In operation when the print job is successfully deleted the print job server may send a message indicating the successful deletion of the print job.

In operation when the print job data is received from the print job server the image forming apparatus may perform an image forming operation for the print job. That is the image forming apparatus may print the print job data.

In operation after the print job is output the image forming apparatus may transmit the print job output result to the print job server . For example the image forming apparatus may transmit to the print job server the print job output result indicating that the print job has been successfully performed after the output of the print job. At this time the print job server may send a message indicating that the print job output result has been successfully confirmed.

On the other hand after reception of the message indicating that the print job output result has been successfully confirmed the session is connected between the image forming apparatus and the print job server in a long polling manner by transmitting a long polling request and the image forming apparatus waits for the print job mapped to the image forming apparatus .

Specifically the image forming apparatus and the print job server may communicate with each other by using an HTTP or an HTTPS.

In operation an image forming apparatus may perform a scan job on a document to be scanned. When the scan job has been completed a scan job file may be generated. The image forming apparatus transmits the scan job file to a cloud server . At this time the image forming apparatus may receive a user input indicating that the scan job is performed.

In operation the cloud server may store the relevant scan job file and send a content key corresponding to the stored scan job file to the image forming apparatus .

In operation the image forming apparatus may send to the cloud server the received content key sender information input from a user through a user panel of the image forming apparatus arbitrary input character string and receiver information country code and phone number of a receiver .

The cloud server generates a job identifier mapped such that the content key and the phone number of the receiver corresponded to each other and sends a message indicating the successful generation of the job identifier to the image forming apparatus . At this time the message may include the job identifier.

The image forming apparatus and the cloud server may communicate with each other by using an HTTP HTTPS.

In operation when the power of the image forming apparatus is turned on the image forming apparatus performs connection to the managing server .

In operation the image forming apparatus transmits a serial number a MAC address and a model name of the image forming apparatus to the managing server .

In operation the managing server may generate an image forming apparatus object. The generated image forming apparatus object is a logical object. The image forming apparatus object may be generated by mapping the serial number the MAC address and the model name of the image forming apparatus to each other. At this time an image forming apparatus identifier printer ID corresponding to the image forming apparatus may be generated. On the other hand when the image forming apparatus object is already generated by the managing server the process of generating the image forming apparatus object may not be performed.

In operation when the managing server generates the image forming apparatus object the managing server may transmit a print job server address and an image forming apparatus identifier to the image forming apparatus . The image forming apparatus may periodically check a license with respect to the managing server . For example the image forming apparatus may check the license every 24 hours.

Since the contents associated with the communication performed between the image forming apparatus and the print job server are substantially the same as the contents described above with reference to a description thereof will be omitted.

A user may set an option by using a mobile device and upload and store a print option set to the cloud server by using the mobile device . At this time the cloud server may store the print option mapped to a user account.

According to an embodiment the print option may be mapped to identification information of the mobile device such as the phone number of the mobile device and be stored in the cloud server . On the other hand the embodiment is not limited to the use of the mobile device to set the print option the user may use a PC to set the print option.

At this time the user may access a webpage provided by the cloud server using a web browser embedded in the PC and set the print option in a user interface including a print option provided on the webpage. On the other hand the print option set on the webpage and the print option set in the mobile device may be synchronized with each other.

The print option refers to an option that is applicable to content so as to allow the image forming operation to be performed in the image forming apparatus . For example the print option may include an option regarding color black and white supportability an option regarding a paper direction an option regarding double side printability and an option regarding to a paper size.

The print option may further include an option regarding direct printing mode pull printing mode supportability. In particular when the print mode is set to support the direct printing mode one of the image forming apparatuses registered in the cloud server may be set by default. The direct printing mode refers to a printing mode in which content uploaded from the mobile device to the cloud server is transmitted to the image forming apparatus set by default and is output in the image forming apparatus without being stored in the cloud server . The pull printing mode refers to a printing mode in which content uploaded from the mobile device to the cloud server is stored information designating one of the plurality of registered image forming apparatuses is received from the mobile device when the cloud server receives a print request for the content from the mobile device and the uploaded content is transmitted to the designated image forming apparatus .

Since the image forming apparatuses are able to support different print options the print option that is able to be set by the user using a mobile device or a computer may be a print option that is supported by all image forming apparatuses. Upon receiving a print request from the mobile device in the cloud server it is checked whether the print option stored in the cloud server is an option that is supported by the image forming apparatus that is to transmit the content. If not supported an error message may be sent to the mobile device . For example when a print request for content is transmitted to the image forming apparatus that supports only A an error occurs when a paper option stored in the cloud server is set A. The mobile device may provide a user with an interface for setting the print option and the user may change the print option.

On the other hand the mobile device transmits the changed print option to the cloud server and the cloud server receives the print option from the mobile device . At this time the received print option may be stored in the cloud server . The previously stored option is changed to the received print option and is stored in the cloud server .

The cloud server may transmit the content to which the print option is applied to the image forming apparatus and the image forming apparatus may receive the content to which the print option is applied and perform the image forming job on the received content.

Referring to the mobile device transmits the print request for the content to the cloud server . It is assumed that upon transmitting the print request for the content the mobile device does not receive a user input of setting a separate print option from a user and does not transmit the separate print option included in the user input together with the print request.

At this time the phone number of the mobile device which is included in a USIM chip of the mobile device may be obtained and the obtained phone number of the mobile device may be transmitted together with the print request for the content. Upon receiving the print request for the content the cloud server obtains the option stored in the cloud server . That is the cloud server may obtain the print option mapped to the phone number of the mobile device that is transmitted together with the print request for the content. The cloud server may apply the obtained print option to the content stored in the cloud server and transmit the content to which the print option is applied to the image forming apparatus . The content may be converted to the print data and be transmitted to the image forming apparatus .

When the content is successfully transmitted to the image forming apparatus the cloud server may send a message indicating the successful transmission of the content to the mobile device .

When the image forming apparatus receives the content from the cloud server the image forming apparatus may perform the image forming job on the content. Specifically the image forming apparatus may print the content.

The embodiment is not limited thereto. The cloud server may transmit the obtained print option to the image forming apparatus together with the content mapped to the phone number of the mobile device and the image forming apparatus may perform the image forming job on the content by applying the print option to the content received from the cloud server .

A user may set a print option by using the mobile device and upload and store a print option set to the cloud server by using the mobile device . At this time the cloud server may store the print option mapped to a user account. According to an embodiment the cloud server may store the print option mapped to identification information of the mobile device such as the phone number of the mobile device .

Referring to the mobile device sends a print request for content to the cloud server . It is assumed that upon sending the print request for the content the mobile device receives a user input of setting a separate print option from a user and sends the separate print option included in the user input together with the print request.

At this time the phone number of the mobile device which is embedded in a USIM chip of the mobile device may be obtained and the obtained phone number of the mobile device may be sent together with the print request for the content. When the cloud server receives the print request for the content together with the print option the cloud server may apply the received print option to the requested content. That is when the cloud server receives the print request for the content together with the print option the option stored in the cloud server is not used. The cloud server may apply the obtained print option to the content stored in the cloud server and transmit the content to which the print option is applied to the image forming apparatus . At this time the content may be converted to print data and be transmitted to the image forming apparatus .

When the content is successfully transmitted to the image forming apparatus the cloud server may send a message indicating the successful transmission of the content to the mobile device .

When the image forming apparatus receives the content from the cloud server the image forming apparatus may perform the image forming job on the content. Specifically the image forming apparatus may print the content.

At this time the cloud server may temporarily apply the print option received from the mobile device to the content and does not change the previously stored print option. However the embodiment is not limited thereto and the previously stored print option may be changed and synchronized.

Referring to a user executes a cloud printing service application by using a mobile device . The mobile device displays icons that allow the user to select a type of content to be uploaded on a screen of the mobile device .

It is assumed that the user selects a web icon and an email icon among the icons regarding the type of the content displayed on the screen of the mobile device .

If the user selects the web icon by using the mobile device a web browser is executed and a webpage is displayed on the screen of the mobile device . That is if the user performs web surfing by using the mobile device the mobile device receives a webpage from a web server through an HTTP and displays the received webpage on the screen of the mobile device . On the other hand when the displayed webpage is uploaded to the cloud server as content the user selects Send Job by using the mobile device in a state in which the relevant webpage is displayed.

When the user selects Send Job by using the mobile device page data may be generated by dividing the webpage currently displayed on the screen by page. The generated page data is converted to image data such as PNG or JPEG and the image data is transmitted to the cloud server . When the cloud server receives the image data generated by the mobile device the cloud server may store the relevant image data. When the cloud server receives a print request for content by using the mobile device the cloud server may transmit the stored content image data to an image forming apparatus and the image forming apparatus may receive the relevant content and print the received content.

If the user selects the email icon by using the mobile device the contents included in the email is displayed on the screen of the mobile device . That is the user inputs a user account password by using the mobile device or connects to an mail server by using the prestored user account password. In order for the user to check the email stored in the mail server the mobile device receives the email from the mail server through POP3 or IMAP and displays the received email. When the displayed email is uploaded to the cloud server as content the user selects Send Job by using the mobile device in a state in which the relevant email is displayed.

When the user selects Send Job by using the mobile device page data may be generated by dividing the webpage currently displayed on the screen by page. The generated page data is converted to image data such as PNG or JPEG and the image data is transmitted to the cloud server . When the cloud server receives the image data generated by the mobile device the cloud server may store the relevant image data. When the cloud server receives a print request for content by using the mobile device the cloud server may transmit the stored content image data to the image forming apparatus and the image forming apparatus may receive the relevant content and print the received content.

On the other hand the mobile device may generate page data based on a paper size. That is when the mobile device receives HTML data or email data from the web server or the mail server the mobile device may extract a raw image of an entire page from the HTML data or the email data and divide raw image data to page images based on a selected page height width.

Referring to when a user intends to print content uploaded to a cloud server or content stored in the mobile device by using the mobile device the mobile device may obtain preview data of content to be printed and display the obtained preview data on a preview screen of the mobile device and the user may check the content in advance through the preview screen . On the other hand the user may set a simple print option displayed on the preview screen of the mobile device. At this time the simple print option may display a print option stored in the cloud server. The user may select the simple print option and changes the user print option. A print request for the previewed content may be transmitted to the cloud server together with the changed print option. The cloud server may receive the print request for the content together with the changed print option generate print data by applying the received print option to the content transmit the generated print data to the image forming apparatus and perform the image forming job on the received print data. On the other hand the print option stored in the cloud server is replaced with the print option transmitted together with the print request for the content and the print option may be stored in the cloud server. The embodiment is not limited to the preview screen . The user may select a print option displayed on a different screen and change the selected print option.

When the user selects a setting icon on the preview screen of the mobile device by using the mobile device the mobile device displays the setting screen . Here various print options may be set. When the user selects the print options the selected print options are transmitted to the cloud serve and replace the print option stored in the cloud server. The print options are stored and synchronized.

A user may access a web server included in a cloud server by using a user device or a PC and set print options. In other words the user may select option values of print option items through a UI screen of displayed on the user device or the PC. If an image forming apparatus for performing a print job is selected the UI screen may display print option items that are selectable according to the selected image forming apparatus.

Meanwhile if the user selects the option values of the print options items and selects a save icon the selected option values are stored in a cloud server. Here the selected option values may be mapped to a user s account and stored in the cloud server.

Processes functions methods and or software in apparatuses described herein may be recorded stored or fixed in one or more non transitory computer readable media computer readable storage recording media that includes program instructions computer readable instructions to be implemented by a computer to cause one or more processors to execute perform or implement the program instructions. The media may also include alone or in combination with the program instructions data files data structures and the like. The media and program instructions may be those specially designed and constructed or they may be of the kind well known and available to those having skill in the computer software arts. Examples of non transitory computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks and DVDs magneto optical media such as optical disks and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The program instructions may be executed by one or more processors. The described hardware devices may be configured to act as one or more software modules that are recorded stored or fixed in one or more non transitory computer readable media in order to perform the operations and methods described above or vice versa. In addition a non transitory computer readable medium may be distributed among computer systems connected through a network and program instructions may be stored and executed in a decentralized manner. In addition the computer readable media may also be embodied in at least one application specific integrated circuit ASIC or Field Programmable Gate Array FPGA .

While embodiments been particularly shown and described above it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the disclosure as defined by the appended claims. Embodiments should be considered in a descriptive sense only and not for purposes of limitation. Therefore the scope of the disclosure is defined not by the detailed description but by the appended claims and all differences within the scope will be construed as being included in the present disclosure.


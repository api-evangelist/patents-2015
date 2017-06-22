---

title: Communication apparatus, external apparatus, and control method therefor
abstract: A communication apparatus which controls an external apparatus, comprises a communication unit configured to control communication with the external apparatus, a control unit configured to control the external apparatus by causing the communication unit to transmit, to the external apparatus, operation information for causing the external apparatus to execute a predetermined function, and a management unit configured to, when a function controllable on the external apparatus is added, manage additional function information that renders the added function usable also by second application software that is different from first application software, the first application software causing the control unit to function so as to control the external apparatus.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09467550&OS=09467550&RS=09467550
owner: Canon Kabushiki Kaisha
number: 09467550
owner_city: Tokyo
owner_country: JP
publication_date: 20150708
---
The present invention relates to a technique to remotely control an external apparatus using a communication apparatus.

In recent years there is an increasing demand to remotely control an external apparatus such as a digital camera from a communication apparatus such as a smartphone. As application software hereinafter application for controlling digital cameras from smartphones and the like there are applications provided by camera manufacturers for their digital cameras however there is a demand by a third party other than these camera manufacturers to develop camera applications different from the provided applications.

To meet this demand in some cases camera manufacturers provide software development kits hereinafter SDKs that enable camera control Japanese Patent Laid Open No. 2008 167269 Japanese Patent Laid Open No. 2007 013880 .

Some of the applications for controlling an external apparatus from the aforementioned communication apparatus validate an additional function upon purchase of add in software for a fee. In this case the additional function is normally usable only by an application that has purchased the additional function. Furthermore when there are applications developed by different developers add in software needs to be purchased separately.

In view of this in a case where add in software for a certain apparatus has been purchased there is a demand to use the additional function also on a different application in another apparatus or the same apparatus.

The present invention has been made in consideration of the aforementioned problems and realizes a technique to allow an additional function that is usable by an application for controlling an external apparatus to be used also by a different application in another apparatus or the same apparatus.

In order to solve the aforementioned problems the present invention provides a communication apparatus which controls an external apparatus comprising a communication unit configured to control communication with the external apparatus a control unit configured to control the external apparatus by causing the communication unit to transmit to the external apparatus operation information for causing the external apparatus to execute a predetermined function and a management unit configured to when a function controllable on the external apparatus is added manage additional function information that renders the added function usable also by second application software that is different from first application software the first application software causing the control unit to function so as to control the external apparatus.

In order to solve the aforementioned problems the present invention provides an external apparatus which is controlled by a communication apparatus comprising a communication unit configured to be capable of communicating with the communication apparatus a control unit configured to execute a function corresponding to operation information received from the communication apparatus and a notification unit configured to when a function controllable on the external apparatus is added and a notice of operation information of the added function is issued from the communication apparatus give notice of a usable state of the added function on the external apparatus to the communication apparatus.

In order to solve the aforementioned problems the present invention provides a control method of a communication apparatus which controls an external apparatus the method comprising a step of controlling communication with the external apparatus a step of controlling the external apparatus by transmitting operation information for causing the external apparatus to execute a predetermined function to the external apparatus and a step of when a function controllable on the external apparatus is added managing additional function information that renders the added function usable also by second application software that is different from first application software for controlling the external apparatus.

In order to solve the aforementioned problems the present invention provides a control method of an external apparatus which is controlled by a communication apparatus the method comprising a step of connecting to the communication apparatus in such a manner that communication can be performed with the communication apparatus a step of executing a function corresponding to operation information received from the communication apparatus and a step of when a function controllable on the external apparatus is added and a notice of operation information of the added function is issued from the communication apparatus giving notice of a usable state of the added function on the external apparatus to the communication apparatus.

In order to solve the aforementioned problems the present invention provides a system in which a communication apparatus and an external apparatus are connected wherein the communication apparatus comprises a communication unit configured to control communication with the external apparatus a control unit configured to control the external apparatus by causing the communication unit to transmit to the external apparatus operation information for causing the external apparatus to execute a predetermined function and a management unit configured to when a function controllable on the external apparatus is added manage additional function information that renders the added function usable also by second application software that is different from first application software the first application software causing the control unit to function so as to control the external apparatus and wherein the external apparatus comprises a communication unit configured to be capable of communicating with the communication apparatus a control unit configured to execute a function corresponding to operation information received from the communication apparatus and a notification unit configured to when the function controllable on the external apparatus is added and a notice of operation information of the added function is issued from the communication apparatus give notice of a usable state of the added function on the external apparatus to the communication apparatus.

According to the present invention an additional function that is usable by an application for controlling an external apparatus can be used also by a different application in another apparatus or the same apparatus.

Further features of the present invention will become apparent from the following description of an exemplary embodiment with reference to the attached drawings .

An embodiment of the present invention will be described in detail below. The following embodiment is merely an example for practicing the present invention. The embodiment should be properly modified or changed depending on various conditions and the structure of an apparatus to which the present invention is applied. The present invention should not be limited to the following embodiment. Also parts of the embodiment to be described later may be properly combined.

The following describes a system in which a smartphone which is one type of a mobile telephone and a digital single lens reflex camera hereinafter digital camera are used as a communication apparatus and an external apparatus of the present invention and the smartphone and the digital camera are connected via a network. Although the external apparatus is assumed to be a digital single lens reflex camera in the present embodiment the present invention is not limited in this way and the external apparatus may be a compact digital camera a mobile electronic apparatus such as a tablet a personal computer equipped with a web camera etc. Furthermore although the communication apparatus is assumed to be a smartphone in the present embodiment the present invention is not limited in this way and the communication apparatus may be a tablet a personal computer a personal digital assistant PDA a mobile AV player a game console an electronic book etc.

An overview of a configuration and functions of a digital camera of the embodiment according to the present invention will now be described with reference to .

In a shooting lens includes a zoom lens and a focus lens and can be built in a camera body or is attachable to and detachable from the camera body as a lens unit. An autofocus AF drive circuit includes for example a DC motor and an ultrasonic motor and achieves focus by changing a focus lens position in accordance with a control instruction from a microcomputer .

A zoom drive circuit includes for example a DC motor and an ultrasonic motor and changes a focal length by changing a zoom lens position in accordance with a control instruction from the microcomputer .

A diaphragm drive circuit drives a diaphragm in accordance with a control instruction from the microcomputer so as to change an optical f number of the diaphragm . The optical f number of the diaphragm is calculated by the microcomputer .

A main mirror switches between an optical path for directing a light beam incident from the shooting lens toward a viewfinder and an optical path for directing the light beam toward an image sensor. A force is always applied so as to place the main mirror in a mirror down position for directing the light beam toward the viewfinder however at the time of shooting and live view a non illustrated mirror drive circuit flips up the mirror that is to say places the mirror in a mirror up position by retracting the mirror from an optical axis so as to direct the light beam toward the image sensor. The main mirror is a half mirror that can transmit a part of the light beam at its central portion and makes the part of the light beam incident on AF sensors for performing focus detection. It should be noted that the AF sensors are disposed inside a focus detection circuit . A sub mirror reflects the light beam transmitted through the main mirror toward the AF sensors.

A pentaprism composes the viewfinder. The viewfinder is comprised of a non illustrated focusing screen eyepiece lens and the like in addition to the pentaprism and the light beam reflected by the main mirror is incident on these components and directed to the viewfinder.

The focus detection circuit performs focus detection using for example a phase difference between two images formed via the lenses and includes a pair of AF sensors in the present example. The light beam that has been transmitted through the central portion of the main mirror and reflected by the sub mirror arrives at the pair of AF sensors that is disposed inside the focus detection circuit for performing photoelectric conversion. A defocus amount indicating the state of focus adjustment of the shooting lens with respect to a subject is obtained by calculating the output from the pair of AF sensors. The microcomputer evaluates the calculation result and issues a control instruction to the AF drive circuit so as to drive the focus lens.

A reference numeral denotes a focal plane shutter. A shutter drive circuit drives the focal plane shutter at a shutter speed corresponding to a control instruction from the microcomputer .

An image sensor is an image sensor using photoelectric conversion elements such as a CCD and a CMOS and generates an analog image signal by applying photoelectric conversion to a subject image formed by the shooting lens .

A clamp circuit and an AGC circuit apply basic analog signal processing to the analog image signal obtained from the image sensor and their clamp level and AGC reference level are changed by the microcomputer .

An AD converter converts the analog image signal which has been obtained from the image sensor and to which the analog signal processing has been applied into a digital signal and outputs the digital signal to a signal processing circuit .

The signal processing circuit is realized by a logic device such as a gate array. The signal processing circuit applies filter processing color conversion processing gamma processing and compression processing according to JPEG and the like to a digital image signal from the AD converter or to image data read from a memory and outputs the resultant image signal or image data to a memory controller . The memory controller performs writing and reading of image data between the memory or a buffer memory and the signal processing circuit . The signal processing circuit also calculates information of exposure AE white balance WB and the like as necessary using the image signal obtained from the image sensor and outputs the calculation result to the microcomputer . The microcomputer adjusts white balance and gain based on the calculation result.

In continuous shooting image signals are first stored into the buffer memory without being processed then the unprocessed image signals are read via the memory controller and the signal processing circuit applies image processing and compression processing thereto. The number of images obtained through continuous shooting depends on the capacity of the buffer memory .

The signal processing circuit also applies compression processing to a digital audio signal input from a microphone and audio line input via an AD converter and outputs the resultant digital audio signal to the memory controller . The signal processing circuit can also output to a speaker via a DA converter digital audio data that is input from the microphone and audio line input . The DA converter converts a digital signal into an analog signal.

An electronic viewfinder EVF drive circuit displays image data output from the signal processing circuit on an EVF monitor in accordance with a control signal from the microcomputer .

The memory controller stores an unprocessed digital image signal and audio signal input from the signal processing circuit into the buffer memory and stores a processed digital image signal and audio signal into the memory . The memory controller also outputs image data and audio data read from the buffer memory and the memory to the signal processing circuit . In some cases the memory is detachable from an apparatus body. The memory controller can output image data and audio data stored in the memory to an external apparatus via a communication interface I F .

The communication I F has a function of transmitting and receiving a control signal an image signal an audio signal and the like to and from the external apparatus . For example a picture transfer protocol PTP or a media transfer protocol MTP is used as a protocol for establishing connection to and performing data communication with the external apparatus . It should be noted that no particular limitation is intended regarding a communication method and communication may be performed using a wireless LAN a wired LAN USB Bluetooth registered trademark etc. Here the external apparatus may be any apparatus e.g. a personal computer a camera a mobile telephone a smartphone a hard disk recorder a game console and a remote control as long as it can communicate with the digital camera . In a case where the communication I F performs communication using a wireless LAN elements such as an antenna an RF unit and a baseband unit are provided and packets compliant with the supported wireless LAN standards can be transmitted and received.

The microcomputer is a calculation processing apparatus that integrally controls the entirety of the apparatus and executes processing sequences described later by executing programs stored in a non volatile memory .

An operation member includes buttons a dial a touch panel touchscreen and the like for receiving a user operation. The microcomputer controls various elements in accordance with a change in the state of the operation member .

The operation member also includes a first switch and a second switch that are turned on and off by an operation on a release button.

The first switch is turned on and generates a first switch signal SW in the middle of an operation on the release button provided to the camera that is to say when the release button is pressed halfway down issuance of a shooting preparation instruction . The microcomputer starts operations for AF processing AE processing WB processing and the like in response to the first switch signal SW.

The second switch is turned on and generates a second switch signal SW when an operation on a shutter button has been completed that is to say when the shutter button is pressed all the way down issuance of a shooting instruction . In response to the second switch signal SW the microcomputer starts an operation for a series of shooting processes from reading of a signal from the image sensor to writing of image data to the memory .

Furthermore while the first switch signal SW and the second switch signal SW are both in an on state a continuous shooting operation is performed.

The operation member also includes a main switch a shooting mode dial an ISO setting button a menu button a set button a flash setting button a button for switching among single shooting continuous shooting and a self timer a switch plus button and a switch minus button for switching to a menu and switching among reproduced images an exposure correction button a button for enlarging a displayed image a button for reducing a displayed image a reproduction switch a diaphragm button an erase button a button for displaying information related to shooting and reproduction etc.

A display drive circuit drives a main display unit on the back surface of the camera body and a sub display unit inside the viewfinder in accordance with a control instruction from the microcomputer . A backlight not illustrated comprised of for example LEDs driven by the display drive circuit is provided in the sub display unit . The microcomputer checks the capacity of the memory via the memory controller based on a predicted value of image data corresponding to the ISO speed image size and image quality that have been set in advance. Based on the capacity of the memory the microcomputer calculates the remaining number of images that can be shot and performs control to display the calculated number on the main display unit and the sub display unit as necessary.

The non volatile memory is an electrically erasable and recordable memory such as an EEPROM. The non volatile memory stores constants programs and the like for the operations of the microcomputer . The programs mentioned here denote programs for executing processing sequences described later.

A power source unit is constituted for example by a primary battery such as an alkaline battery and a lithium battery by a secondary battery such as a NiCd battery a NiMH battery and a lithium ion battery or by an AC adaptor and supplies necessary power to various elements.

An overview of a configuration and functions of a smartphone of the embodiment according to the present invention will now be described with reference to .

A ROM is an electrically erasable and recordable flash memory and is used to store data and various types of control programs such as application programs and an OS executed by the CPU . The ROM also stores various types of contents such as moving images and still images captured by a camera unit .

The RAM is mainly used as a storage area for various types of data e.g. an area into which a program executed by the CPU is stored or deployed and a working area during program execution.

The camera unit includes an image sensor constituted by for example a CMOS for converting a subject image into an electrical signal a lens for forming the subject image onto the image sensor a diaphragm a shutter etc. The camera unit also includes an A D converter for converting an analog image signal output from the image sensor into a digital signal.

A microphone and a speaker are used in a call to from a user of another communication apparatus. The speaker and an earphone terminal output an audio signal stored in the ROM and an audio signal input from for example a telephone line via a communication I F an external I F and the like.

A global positioning system GPS unit has a GPS antenna for acquiring information of the current position of the smartphone by receiving radio waves from a GPS satellite.

An electronic compass acquires information of the direction in which the smartphone is facing by detecting the geomagnetic orientation.

An operation unit is comprised of a physical switch button and the like receives a user operation and transmits a control signal to the CPU . The CPU receives a control signal input from the operation unit and controls various elements of the smartphone . The operation unit also includes a touch panel that can detect contact with a display unit and constitutes a GUI that enables the user to feel as if he she can directly operate a screen displayed on the display unit . The CPU detects the user s contact with the touch panel and executes processing corresponding to the position of contact. The type of the touch panel may be selected from among various types including a resistive type a capacitive type a surface acoustic wave type an infrared type an electromagnetic induction type an image recognition type and an optical sensor type.

The display unit is for example a liquid crystal panel or an organic EL panel and displays images a GUI and the like.

The touch panel is integrally constructed with the display unit and the capable of detecting a touch operation on the display unit . Input coordinates on the touch panel and display coordinates on the display unit are correlated. As a result a GUI can be constructed that makes it possible for the user to directly manipulate the screen displayed on the display unit . The CPU is capable of detecting the following operations performed by contacting the touch panel touching of the panel using a finger or pen referred to as touch down below a state in which the touch panel is in contact with a finger or pen referred to as touch on below movement of a finger or pen while in contact with the touch panel referred to as move below lifting of a finger or pen that has been in contact with the touch panel referred to as touch up below and a state in which the touch panel is not being touched at all referred to as touch off below . These operations and position coordinates at which the touch panel is being touched by the finger or pen are communicated to the CPU and based upon the information thus communicated the CPU determines what kind of operation was performed on the touch panel. As for move the determination can be made also for every vertical component and horizontal component with regard to the direction of movement of the finger or pen which is moved on the touch panel based upon a change in the coordinate position. Further it is assumed that a stroke has been made when touch up is performed following a regular move after a touch down on the touch panel. A very quick stroke action is referred to as a flick . A flick is an operation in which with fingers in contact with the touch panel the fingers are moved rapidly over a certain distance and then lifted. In other words this is a rapid tracing operation in which the fingers are flicked across the surface of the touch panel. The CPU can determine that a flick has been performed when it detects such movement over a predetermined distance or greater and at a predetermined speed or greater and then detects touch up . Further the CPU can determine that drag has been performed if it detects movement over a predetermined distance or greater at a speed less than a predetermined speed.

The communication I F has a function of transmitting and receiving a control signal an image signal an audio signal and the like to and from an external apparatus such as a digital camera a printer and another communication apparatus. For example a picture transfer protocol PTP or a media transfer protocol MTP is used as a protocol for establishing connection and performing data communication with a digital camera. It should be noted that no particular limitation is intended regarding a communication method and communication is performed using a wireless LAN a wireless wide area network WWAN a wired LAN Bluetooth registered trademark etc. Here the external apparatus may be any apparatus e.g. a personal computer a camera a mobile telephone a smartphone a hard disk recorder a game console and a remote control as long as it can communicate with the smartphone . In a case where the communication I F performs communication using a wireless LAN elements such as an antenna an RF unit and a baseband unit are provided and packets compliant with the supported wireless LAN standards can be transmitted and received.

The external I F is in conformity with various types of standards such as USB and HDMI registered trademark and exchanges video data and audio data with the external apparatus. The external I F also exchanges data with a recording medium such as a memory card and a hard disk.

A power source unit is constituted by a secondary battery such as a lithium ion battery or by an AC adaptor and supplies necessary power to various elements.

In the system according to the present embodiment the digital camera and the smartphone are connected via the communication I Fs and the smartphone can remotely control the digital camera .

As shown in the digital camera and the smartphone are connected via an access point hereinafter AP compliant with the wireless LAN standards of IEEE 802.11. It should be noted that communication between the digital camera and the smartphone may be performed through direct connection using an ad hoc network and the like or through infrastructure connection via the AP and the like. Furthermore the digital camera may serve as a simple access point so as to establish communication directly with the smartphone through infrastructure connection.

A description is now given of a software configuration of a camera application according to the present embodiment with reference to .

In order to realize the system according to the present embodiment it is necessary to install in the smartphone communication control application software hereinafter camera application for remotely controlling the digital camera . It should be noted that the camera application may be preinstalled at the time of shipment of the smartphone or may be installed by a user operation after the purchase of the smartphone .

The camera application is application software that is mainly used to remotely control the digital camera . The user can download the camera application from a predetermined server via for example the Internet and install the same in the smartphone .

The camera application includes a camera control software development kit SDK which is a software program playing a role in communication with the digital camera as a library. Direct communication between the digital camera and the smartphone having the camera application installed therein is performed via this camera control SDK hereinafter camera SDK which is a communication application software program. A control application software program other than the camera SDK hereinafter camera control application plays a role in other functions e.g. receiving a user operation displaying a GUI and activating deactivating the camera application .

The camera SDK is expected to be provided from a vendor of the digital camera to an application developer. Therefore the application developer determines whether to incorporate the camera SDK which is provided for a smartphone OS into the application depending on the smartphone that is expected to install the application therein.

A description is now given of a basic processing sequence of the camera application for a case in which connection between the digital camera and the smartphone has been established with reference to .

In the camera control application calls up an application programming interface hereinafter API of the camera SDK corresponding to a substance of desired control and requests the camera SDK for processing step S .

Upon receiving the API call from the camera control application the camera SDK identifies operation information ID of a communication protocol that is suitable for a substance of processing for the called API and transmits the operation ID to the digital camera step S .

Upon receiving the operation ID from the camera SDK the digital camera executes camera control corresponding to the requested operation ID step S .

Examples of the types of control functions corresponding to operation IDs transmitted from the camera SDK to the digital camera include AF start shooting preparation operation release change in a shooting parameter live view LV start acquisition of an LV image and acquisition of an image file.

As indicated above communication between the digital camera and the camera SDK is controlled using operation IDs.

It should be noted that the following operations are prepared in the present embodiment operations that can be controlled by the camera SDK in a normal connection state and additional function operations that validate additional functions upon purchase of add in software for a fee. The additional function operations are not valid in a normal connection state upon receiving from the camera SDK an additional function purchase notice indicating that the additional functions have been purchased the additional function operations are added to the digital camera as newly controllable operations.

Examples of the additional function operations include an interval shooting function and a raw development function see .

A description is now given of a processing sequence of the camera application in the smartphone a server and the digital camera according to the present embodiment with reference to .

The processing sequence according to the present embodiment is started when connection between the smartphone in which the camera application A has been activated and the digital camera is established in accordance with the procedure described with reference to . It should be noted that in the processing sequence according to the present embodiment processing of the digital camera is realized by the microcomputer reading a control program stored in the non volatile memory into a system memory such as a RAM and executing the read control program. On the other hand processing of the smartphone is realized by the CPU reading a control program stored in the ROM into the RAM and executing the read control program.

Below processing executed by reading from the camera application a camera control application A independently of the camera SDK and processing executed by reading the camera SDK will be discussed in distinction from each other. To facilitate the understanding these items of software will be treated as the main executors of processing in some portions of the following description however in reality the main executor of operations is the CPU that has read the camera control application A or the camera SDK .

In once the camera application A has been activated in the smartphone by a user operation the camera control application A issues a connection request to the camera SDK step S .

Upon receiving the connection request the camera SDK transmits a device information acquisition request to the digital camera step S .

Upon receiving the device information acquisition request the digital camera transmits device information to the smartphone step S . The device information includes operations supported by the digital camera valid events and current properties.

Operations are control commands addressed to the digital camera and are mainly classified into operations of causing the digital camera to transmit an image held therein and operations of controlling a shooting function of the digital camera . One example of the operations of causing the digital camera to transmit an image held therein is acquisition of an image file whereby the digital camera transmits image data to the external apparatus in the present example the smartphone . One example of the operations of controlling the shooting function is release for causing the digital camera to shoot a still image. Other examples include live view LV whereby the digital camera transmits a live view image to the external apparatus in the present example the smartphone and start and stop of moving image recording for causing the digital camera to record moving images. Furthermore an additional function purchase notice for validating an additional function on the digital camera is also included among these operations. Examples of operations that become usable upon purchase of additional functions include interval shooting for causing the digital camera to shoot a still image in every certain time period and raw development for causing the digital camera to apply development processing to a raw image.

In step S first notice is given of camera control operations corresponding to acquisition of an image file release LV start and stop of moving image recording and the like as well as an operation corresponding to the additional function purchase notice as usable operations.

Events are information for giving notice of actions that occurred in the digital camera to the external apparatus in the present example the smartphone . Examples of the events include a change in a setting value of the digital camera on the camera side and shooting caused by an operation on the camera side.

The properties are shooting parameters of the digital camera and examples thereof include an f number a shutter speed and an ISO speed.

Returning to upon receiving the device information the camera SDK transmits an operation corresponding to a connection request to the digital camera step S .

Thereafter the camera SDK refers to an SDK management file stored in the ROM and confirms whether there is additional function purchase information indicating that an additional function s has been purchased if there is no additional function purchase information no processing is executed with respect to the digital camera step S .

A description is now given of a processing sequence in which the camera application A controls the digital camera .

A GUI screen shown in includes an image file acquisition button a camera control button and an add in purchase button .

The image file acquisition button is a button for acquiring an image file held in the digital camera by executing processing for transmitting the image file from the digital camera to the smartphone .

The camera control button is a button for switching to a mode for remotely controlling the digital camera . Once the camera control button has been operated by the user a camera control screen shown in is displayed and control of the digital camera from the smartphone is enabled. In a live view display region and still image shooting are displayed as examples of functions of the digital camera that can be controlled by the smartphone .

Once the camera control screen has been displayed the camera control application A issues an LV image acquisition request to the camera SDK step S .

Upon receiving the LV image acquisition request the camera SDK transmits an LV image acquisition request to the digital camera step S .

Upon receiving the LV image acquisition request the digital camera transmits a generated LV image to the camera SDK and the camera SDK passes the received LV image to the camera control application A. Through the foregoing processes the camera control application A can display a live view image received from the digital camera in the live view display region . Furthermore an image in the live view display region is updated by executing the processes of steps S and S periodically.

A description is now given of a case in which the release button on the UI screen shown in is pressed.

When the release button is pressed by a user operation the camera control application A issues a release request to the camera SDK in step S.

Upon receiving the release request the camera SDK transmits a release request to the digital camera step S .

Upon receiving the release request the digital camera shoots and acquires a new image by performing a release operation.

The add in purchase button is a button for switching to a mode for purchasing an additional function for remotely controlling the digital camera . When the add in purchase button is pressed by a user operation an add in purchase screen shown in is displayed on which an additional function that enables control of the digital camera from the smartphone can be purchased.

In a raw development purchase button and an interval shooting purchase button are displayed as examples of functions that can be added through add in purchase.

Once the add in purchase screen has been displayed the camera control application A issues an additional function purchase confirmation request to the camera SDK step S .

Upon receiving the additional function purchase confirmation request the camera SDK transmits an additional function purchase confirmation request to an account server step S .

Upon receiving the additional function purchase confirmation request the account server performs user authentication confirms the status of the user s purchase of an additional function s step S and gives notice of the substance of the purchase of the additional function s to the camera SDK step S .

The camera SDK confirms the notice from the account server indicating the substance of the purchase of the additional function s if no additional function has been purchased no processing is executed with respect to the digital camera .

A description is now given of a case in which the interval shooting purchase button on the UI screen shown in is pressed.

When the interval shooting purchase button is pressed by a user operation the camera control application A issues an additional function interval shooting purchase request to the camera SDK step S .

Upon receiving the additional function interval shooting purchase request the camera SDK transmits an additional function interval shooting purchase request to the account server step S .

Upon receiving the additional function interval shooting purchase request the account server performs user authentication and executes additional function purchase processing by for example charging the user step S when the purchase processing has been completed it gives notice of completion of the purchase of the additional function interval shooting to the camera SDK step S .

Upon receiving the notice of completion of the purchase of the additional function interval shooting from the account server the camera SDK records additional function interval shooting purchase information as an SDK management file into the ROM of the smartphone step S .

Thereafter the camera SDK issues an additional function interval shooting purchase notice to the digital camera step S .

Upon receiving the additional function interval shooting purchase notice from the camera SDK the digital camera adds an operation for controlling the additional function interval shooting step S and transmits a device information reacquisition request to the camera SDK step S .

Upon receiving the device information reacquisition request from the digital camera the camera SDK transmits a device information acquisition request to the digital camera step S . Upon receiving the device information acquisition request from the camera SDK the digital camera transmits current device information step S . It should be noted that the device information transmitted here includes information related to the additional function interval shooting added in step S. It should be noted that in a case where the digital camera transmits device information to the camera SDK it is possible to encrypt additional function information using information that varies with each camera such as camera serial numbers and MAC addresses and then transmit the encrypted additional function information this prevents a situation in which a user who has not purchased an additional function can use the additional function by analyzing a communication protocol between the digital camera and the smartphone .

The camera SDK can acknowledge functions that are usable in control of the digital camera by reacquiring the device information from the digital camera in step S as the reacquired device information includes the interval shooting function an additional function interval shooting validity notice is issued to the camera control application A step S .

Upon receiving the additional function interval shooting validity notice in step S the camera control application A notifies the user of the purchased state by displaying the purchased state on the interval shooting purchase button of the add in purchase screen shown in .

If the camera control button shown in is pressed by the user again after the purchase of the interval shooting function the camera control screen shown in is displayed and control of the digital camera from the smartphone is enabled. On the UI screen shown in an interval shooting button is displayed in addition to the live view display region and the release button which were displayed prior to the purchase of the interval shooting function as the functions of the digital camera that can be controlled by the smartphone .

Once the camera control screen shown in has been displayed the camera control application A issues an LV image request to the camera SDK step S .

A description is now given of a case in which the interval shooting button on the UI screen shown in is pressed.

When the interval shooting button is pressed by a user operation the camera control application A issues an interval shooting request to the camera SDK step S .

Upon receiving the interval shooting request the camera SDK transmits an interval shooting request to the digital camera step S .

Upon receiving the interval shooting request the digital camera newly performs shooting and acquires an image in every certain time period by performing an interval shooting operation based on the following camera settings the interval at which interval shooting is performed and the total number of shot images.

In the present embodiment the interval at which interval shooting is performed and the total number of shot images are set on the camera side however the camera control application A may have an individual function of setting the interval at which interval shooting is performed and the total number of shot images to the digital camera .

When the camera application A is deactivated by a user operation the camera control application A issues a disconnection request to the camera SDK step S .

Upon receiving the disconnection request the camera SDK transmits a disconnection request to the digital camera step S .

Upon receiving the disconnection request the digital camera deletes the operation corresponding to the additional function interval shooting and disconnects communication with the smartphone .

With reference to the following describes a processing sequence in which a camera control application B which is different from the camera control application A controls the digital camera after the additional function interval shooting has been purchased as described with reference to .

It is assumed that the camera control application B is included in a camera application B which uses the camera SDK executed by the camera control application B and which has been developed by a different developer that is to say company B.

In once the camera application B has been activated in the smartphone by a user operation the camera control application B executes processes for connecting to the digital camera steps S to S similarly to steps S to S shown in .

After the connection processes the camera SDK refers to an SDK management file stored in the ROM and confirms whether there is additional function purchase information. Here the SDK management file includes additional function interval shooting purchase information indicating that the additional function interval shooting was purchased during the use of the camera control application A described with reference to and therefore the camera SDK issues an additional function interval shooting purchase notice to the digital camera step S .

In subsequent steps S to S processes that are similar to the processes of steps S to S shown in are executed.

If the camera control button shown in is pressed by the user a camera control screen shown in is displayed and control of the digital camera from the smartphone is enabled. It should be noted that this UI screen may be displayed at the same time as the activation of the camera application B or may be displayed after receiving a notice of completion of processing up until step S from the camera SDK .

A live view display region a still image shooting button an interval shooting button a moving image recording button and an add in purchase button are displayed as examples on the UI screen shown in . On the camera control screen displayed by the camera control application B the interval shooting button is displayed in a valid state as the additional function interval shooting has been purchased. Furthermore characters indicating that the interval shooting function has newly become valid such as NEW are displayed on the camera control screen . It should be noted that in a case where the interval shooting function has not been purchased yet at the time of display of the camera control screen the interval shooting button is placed in an invalid state e.g. grayed out when displayed.

In subsequent steps S to S processes that are similar to the processes of steps S to S shown in are executed.

As described above in the present embodiment the camera SDK manages an additional purchase of a control function of the digital camera that can be controlled by the camera control application in this way a single purchase of an additional function allows all of the camera control applications that use the camera SDK to use the additional function that is to say there is no need to purchase the additional function per camera control application.

Although the present embodiment has discussed an example case in which one smartphone switches between two types of camera applications A and B the present embodiment is applicable to a case in which different camera applications are used by different smartphones.

Furthermore although the camera SDK records the additional function purchase information into the SDK management file in the present embodiment the SDK no longer needs to manage the additional function purchase information if the SDK confirms the additional function purchase information with the account server each time connection is established. In this case the camera SDK can download the additional function purchase information by accessing the account server and undergoing user authentication.

Embodiment s of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions e.g. one or more programs recorded on a storage medium which may also be referred to more fully as a non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s and or that includes one or more circuits e.g. application specific integrated circuit ASIC for performing the functions of one or more of the above described embodiment s and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s and or controlling the one or more circuits to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more processors e.g. central processing unit CPU micro processing unit MPU and may include a network of separate computers or separate processors to read out and execute the computer executable instructions. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2014 142636 filed Jul. 10 2014 which is hereby incorporated by reference herein in its entirety.


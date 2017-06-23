---

title: Display apparatus and method for controlling the display apparatus
abstract: A multifunctional display device includes a processor to control display of information during booting of an operating system. The operating system is booted in response to a predetermined signal and displayed the information includes first information corresponding to visual information, and second information indicating that the operating system is currently booting. The operating system is one which controls display of multimedia content.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09578272&OS=09578272&RS=09578272
owner: LG Electronics Inc.
number: 09578272
owner_city: Seoul
owner_country: KR
publication_date: 20150421
---
This application is a Continuation Application of U.S. application Ser. No. 14 329 126 filed Jul. 11 2014 which is a Continuation Application of U.S. application Ser. No. 13 071 226 filed Mar. 24 2011 now U.S. Pat. No. 8 804 039 which claims the benefit of priority of U.S. Provisional Application No. 61 391 089 filed on Oct. 8 2010 and Korean Application No. 10 2010 0113794 filed on Nov. 16 2010 the contents of which is incorporated herein by reference.

One or more embodiments described herein relate to managing and displaying information on an electronic device.

A variety of display devices are currently in use including televisions monitors smart phones music and video players computers PDAs and many many more. Many of these devices boot of one or more applications and include an operating system in order to manage the same. Often times however this booting process takes a considerable amount of time which is considered undesirable by users.

The content provider manufactures various contents and provides them. Examples of the content provider include a terrestrial broadcaster a cable system operator SO a multiple system operator MSO a satellite broadcaster and an Internet broadcaster as illustrated in .

Also the content provider may provide various applications in addition to broadcast contents which will be described in more detail later.

The service provider can provide contents provided by the content provider by service packaging them. For example the service provider of can package first terrestrial broadcasting second terrestrial broadcasting cable MSO satellite broadcasting various kinds of Internet broadcasting application etc. and provide the packaged one to a user.

In the meantime the service provider may provide a service to the client by using a unicast or multicast mode. The unicast mode is to transmit data between a single transmitter and a single receiver 1 1. In case of the unicast mode for example if the receiver requests a server to transmit data the server can transmit data to the receiver in accordance with the request. The multicast mode is to transmit data to a plurality of receivers of a specific group. For example the server can transmit data to a plurality of receivers which are previously registered therewith at one time. For this multicast registration IGMP Internet Group Management Protocol can be used.

The network provider may provide a network for providing a service to the client . The client may construct a home network end user HNED to receive a service.

In the system of the aforementioned display device conditional access or content protection can be used to protect contents which are transmitted. For conditional access or content protection a cable card or downloadable conditional access system DCAS can be used.

In the meantime the client may provide contents through the network. In this case the client may be a content provider contrary to the above. The content provider may receive contents from the client . In this case it is advantageous in that bidirectional content service or data service is available.

Application information table AIT data a real time broadcast content application data and stream event are received through the broadcast interface . The real time broadcast content may be designated as a linear A V content.

The section filter performs section filtering for four kinds of data received through the broadcast interface . Then the section filter transmits AIT data to the AIT filter the linear A V content to the broadcast data processor and stream event and application data to the application data processor .

In the meantime a non linear A V content and application data are received through the Internet interface . The non linear A V content may be content on demand COD application for example. The non linear A V content is transmitted to the media player and the application data is transmitted to the runtime module .

Moreover the runtime module as illustrated in includes an application manager and a browser for example. The application manager controls a lifecycle for an interactive application by using the AIT data. The browser serves to display and process the interactive application.

The service provider may perform service provider discovery S and the display device may transmit a service provider SP attachment request signal S . If SP attachment is finished the display device receives provisioning information S . Moreover the display device receives a master SI table from the service provider S receives a virtual channel map table S receives a virtual channel description table S and receives a source table S .

Hereinafter the process steps for receiving channel information will be described in more detail. The service provider discovery may mean that service providers which provide IPTV related services discover a service discovery SD server that provides information on the service providers.

For example three methods for discovering an address list that can receive information for example SP discovery information on the SD server will be provided as follows. First of all an address previously set by the display device or an address set by a manual operation of the user can be used. Second a DHCP based SP discovery method can be used. Third a DNS SRV based SP discovery method can be used. Also the display device accesses a server of an address acquired by any one of the above three methods and receives a service provider discovery record that includes information required for service discovery per SP. Then the display device performs a service search step by using the received service provider discovery record. The above steps can be performed in a push mode or pull mode.

The display device performs a registration procedure or service attachment procedure by accessing the SP attachment server designated by an SP attachment locator of the SP discovery record.

Moreover after performing a separate authentication procedure by accessing an SP authentication service server designated by an SP authentication locator the display device may perform a service authentication procedure.

In the meantime after the service attachment procedure is successfully performed data transmitted from the server to the display device may be a form of a provisioning information table.

The display device transmits the data to the service attachment server during the service attachment procedure wherein the data includes ID and location information of the display device. The service attachment server can define a service subscribed by the display device based on the received data. Moreover address information that can acquire service information desired to be received by the display device is provided in the form of the provisioning information table. The address information corresponds to access information of the master SI table. In this case it is easy to provide a customized service per subscriber.

The service information includes a master SI table record that manages access information and version on the virtual channel map a virtual channel map table that provides a package type service list a virtual channel description table that includes detailed information of each channel and a source table that includes access information that enables actual access to services.

Each virtual channel map is uniquely identified by a virtual channel map identifier and virtual channel map version represents version information of the virtual channel map. If any one of all tables connected to one another along an arrow starting from the master SI table in is changed version of all upper tables to reach master SI table is increased together with increase of the corresponding table. Accordingly it is advantageous in that the display device can identify change on all SI tables directly by monitoring the master SI table.

For example if there is any change of the source table version of the source table is increased and version of the virtual channel description table for reference of the source table is also changed. Accordingly change of a lower table causes change of an upper table whereby version of the master SI table is finally changed.

The master SI table may exist per service provider. However if configuration of the service is varied per location or subscriber or subscriber group the service provider is designed to have a plurality of master SI tables thereby providing a customized service per each unit. In this way if the service provider is designed it is possible to efficiently provide a customized service for location of a subscriber and subscription information through the master SI table.

The virtual channel map table may have one or more virtual channels and includes location information that can acquire detailed information of the channel without including the detailed information in the virtual channel map. Virtual channel description location of the virtual channel map table indicates location of the virtual channel description table that includes detailed information of the channel.

The virtual channel description table includes detailed information of the virtual channel and can access the virtual channel description table by using the virtual channel description location of the virtual channel map table.

The source table provides access information for example IP address port AV codec transport protocol etc. per service wherein the access information is required for actual access to the service.

The aforementioned master SI table the virtual channel map table the virtual channel description table and the source table are transferred through four flows which are logically divided from one another in a push mode or pull mode. In the meantime the master SI table can be transmitted in a multicast mode for version management and monitors version change by receiving multicast streaming.

The network interface receives packets from a network and transmits the packets to the network. In other words the network interface receives services contents etc. from the service provider through the network.

The TCP IP manager is involved in packets received in the display device and packets transmitted from the display device i.e. packet transfer from the source to the destination. The TCP IP manager sorts the received packets to correspond to a proper protocol and outputs the sorted packets to the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service delivery manager takes the role of control of received service data. For example if the service delivery manager controls real time streaming data it can use RTP RTCP. If the service delivery manager transmits the real time streaming data by using RTP it parses the received packets in accordance with RTP and transmits the parsed packets to the demultiplexer or stores the parsed packets in the SI Metadata DB under the control of the service manager . The service delivery manager feeds the received information back to a server which provides a service by using RTCP.

The demultiplexer demultiplexes the received packets to audio video and PSI Program Specific Information data and then transmits the demultiplexed data to the audio decoder the video decoder and the PSI PSIP and or SI decoder respectively.

The PSI PSIP and or SI decoder decodes service information such as PSI for example. Namely the PSI PSIP and or SI decoder receives and decodes PSI section PSIP Program and Service Information Protocol section or SI Service Information section which is demultiplexed by the demultiplexer .

Also the PSI PSIP and or SI decoder decodes the received sections to make a database for service information and stores the database for service information in the SI Metadata DB .

The audio video decoders decode the video data and the audio data which are received from the demultiplexer . The audio data decoded by the audio decoder and the video data decoded by the video decoder are provided to the user through the display .

The UI manager and the service manager manage the whole state of the display device provide a user interface and manage other managers. The UI manager provides a graphic user interface for the user by using an on screen display OSD and performs a receiving operation based on a key input from the user. For example if a key input signal for channel selection is input from the user the UI manager transmits the key input signal to the service manager .

The service manager controls managers related to the service such as the service delivery manager the service discovery manager the service control manager and the metadata manager .

Also the service manager makes a channel map and selects a channel by using the channel map in accordance with the key input signal received from the UI manager . The service manager receives service information of the channel from the PSI PSIP and or SI decoder and sets audio video PID Packet Identifier of the selected channel in the demultiplexer .

The service discovery manager provides information required to select the service provider that provides services. If a signal related to channel selection is received from the service manager the service discovery manager discovers a corresponding service by using the received information.

The service control manager takes the role of selection and control of the service. For example if the user selects a live broadcasting service like the existing broadcasting mode the service control manager uses IGMP or RTSP. If the user selects a video on demand VOD service the service control manager selects and controls the service by using RTSP. The RTSP protocol can provide a trick mode for real time streaming. Also the service control manager can initiate and manage a session through IMC gate by using IMS IP Multimedia Subsystem and Session Initiation Protocol SIP . The above protocols are only exemplary and other protocols may be used depending on embodiments.

The metadata manager manages metadata related to the service and stores the metadata in the SI Metadata DB . The SI Metadata DB stores the service information decoded by the PSI PSIP and or SI decoder the metadata managed by the metadata manager and the information required to select the service provider provided by the service discovery manager . Also the SI Metadata DB may store setup data for the system.

The SI Metadata DB may be implemented by using a NonVolatile RAM NVRAM or a flash memory and the IG is a gateway where functions required for access to IMS based IPTV services are gathered.

The tuner selects one of RF radio frequency broadcast signals received through an antenna which corresponds to a channel selected by the user or all previously stored channels. Also the tuner converts the selected RF broadcast signal to an intermediate frequency signal or a baseband video or audio signal.

For example if the selected RF broadcast signal is a digital broadcast signal the tuner coverts the selected RF broadcast signal to a digital IF DIF signal. If the selected RF broadcast signal is an analog broadcast signal the tuner coverts the selected RF broadcast signal to an analog baseband video or audio signal CVBS SIF . In other words the tuner can process both the digital broadcast signal and the analog broadcast signal. The analog baseband video or audio signal CVBS SIF output from the tuner may directly be input to the control module .

Also the tuner can receive RF broadcast signal of a single carrier based on an advanced television system committee ATSC mode and RF broadcast signal of multiple carriers based on a digital video broadcasting mode DVB .

In the meantime the tuner sequentially selects RF broadcast signals of all broadcast channels stored through a channel memory function from RF broadcast signals received through the antenna and converts the selected RF broadcast signals to intermediate frequency signals or baseband video or audio signals.

The demodulation module receives the digital IF DIF signal converted by the tuner and demodulates the received digital IF signal.

For example if the digital IF signal output from the tuner is based on the ATSC mode the demodulation module performs 8 vestigal side band 8 VSB demodulation for example. Also the demodulation module may perform channel decoding. To this end the demodulation module may include a trellis decoder a de interleaver and a Reed Solomon decoder to perform trellis decoding de interleaving and Reed Solomon decoding.

For example if the digital IF signal output from the tuner is based on the DVB mode the demodulation module performs coded orthogonal frequency division modulation COFDMA demodulation for example. Also the demodulation module may perform channel decoding. To this end the demodulation module may include a convolution decoder a de interleaver and a Reed Solomon decoder to perform convolution decoding de interleaving and Reed Solomon decoding.

The demodulation module can output a stream signal TS after performing demodulation and channel decoding. At this time the stream signal may be a signal where a video signal an audio signal and a data signal are multiplexed. For example the stream signal may be MPEG 2 Transport Stream TS where a video signal of an MPEG 2 specification and an audio signal of Dolby AC 3 specification are multiplexed. Specifically the MPEG 2 TS may include a 4 byte header and 184 byte payload.

The aforementioned demodulation module may be provided separately depending on the ATSC mode and the DVB mode. Namely an ATSC demodulation module and a DVB demodulation module may be provided separately.

The stream signal output from the demodulation module may be input to the control module . The control module performs demultiplexing video audio signal processing etc. and then outputs video to the display module and audio to the audio output module .

The external device interface module may connect an external device to the display device . To this end the external device interface module may include an A V input output unit not shown or a wireless communication unit not shown .

The external device interface module is connected to external devices such as Digital Versatile Disks DVD Blu rays game devices cameras camcorders computers e.g. notebook computers etc. through wire wireless cables. The external device interface module transmits a video audio or data signal externally input through an external device connected thereto to the control module of the display device . Also the external device interface module outputs the video audio or data signal processed by the control module to the external device. To this end the external device interface module may include an A V input output unit not shown or a wireless communication unit not shown .

The A V input output unit of the external input circuit may include a USB terminal a composite Video Banking Sync CVBS terminal a component terminal an S video terminal analog a Digital Visual Interface DVI terminal a High Definition Multimedia Interface HDMI terminal an RGB terminal a D SUB terminal etc. to input video and audio signals of the external device to the display device .

The wireless communication unit may perform a short distance wireless communication with other electronic devices. For example communication standards such as Bluetooth Radio Frequency Identification RFID infrared Data Association IrDA Ultra Wideband UWB ZigBee Digital Living Network Affiance DLNA etc. can be used for the short distance wireless communication whereby network connection between the display device and other electronic devices can be performed.

In addition the external device interface module may be connected to various set top boxes through at least one of the above mentioned various terminals to perform input output operation with the set top boxes. The external device interface module receives an application of a neighboring external device or list of applications and transmits the received application or the list of applications to the control module or the memory module .

The network interface module provides interface for connecting the display device with wire wireless networks including Internet network. The network interface module may include an Ethernet terminal for example for wire network connection. Also for example Wireless LAN WLAN Wi Fi Wireless broadband Wibro World Interoperability for Microwave Access Wimax High Speed Downlink Packet Access HSDPA can be used for the wireless network connection.

The network interface module transmits or receives data to and from other users or other electronic devices through a network connected thereto or another network linked on the connected network. In particular the network interface module can transmit some contents data stored in the display device to a user or electronic device selected from other users or electronic devices previously registered with the display device .

Also the network interface module can access a predetermined web page through a network connected thereto or another network linked on the connected network. In other words the network interface module can transmit or receive data to and from a corresponding server by accessing the predetermined web page through the corresponding network.

In addition the network interface module can receive contents or data provided by the content provider or the network operator. In other words the network interface module can receive contents such as movies advertisements games VOD broadcast signals etc. and related information which are provided from the content provider or the network provider through the network.

Also the network interface module can receive update information and update files of firmware provided by the network operator. Moreover the network interface module can transmit data to the Internet or content provider or the network operator. Furthermore the network interface module can selectively receive a desired one of contents open to the public through the network.

Also the network interface module can transmit or receive contents or data of a list of contents to and from a predetermined server through the network.

The memory module may store a program for processing and controlling each signal of the control module or may store the processed video audio or data signal.

Also the memory module may temporarily store the video audio or data signal input from the external device interface module or the network interface module . The memory module may store information on a predetermined broadcast channel through a channel memory function.

Also the memory module may store the application or the list of applications input from the external device interface module or the network interface module .

Also the memory module may store the contents or the list of contents input from the external device interface module or the network interface module . For example the memory module may include a storage medium of at least one type of a flash memory type a hard disk type a multimedia card micro type a card type memory for example SD or XD memory RAM and ROM EEPROM etc. The display device can play contents files moving picture files still image files music files application files etc. stored in the memory module to provide the played contents files to the user.

Although illustrates that the memory module and the control module are provided separately these modules may be combined in other embodiments. For example according to one embodiment memory module may be included in the control module .

The user input interface module transmits the signal input by the user to the control module or transmits the signal from the control module to the user. For example the user input interface module may receive a control signal such as power on off channel selection and screen setup from the remote controller or transmit the control signal from the control module to the remote controller in accordance with various communication modes such as RF communication mode and IR communication mode.

Also for example the user input interface module may transmit a control signal input by a local key not shown such as a power key a channel key a volume key and a setup key to the control module .

Also for example the user input interface module may transmit a control signal input by a sensing unit not shown which senses gesture of the user to the control module or may transmit the signal from the control module to the sensing unit. In this case the sensing unit may include a touch sensor an audio sensor a position sensor an action sensor etc.

Also for synchronization and search of the contents stored in the display device the user input interface module may receive predetermined synchronization target content a selection signal of the display device for synchronization a content keyword and a synchronization command from the user.

The control module demultiplexes an input stream and processes the demultiplexed stream through the tuner the demodulation module or the external device interface module to generate and output a signal for a video and audio output.

The video signal processed by the control module may be input to the display module so that the video signal may be displayed as image corresponding to the video signal. Also the video signal processed by the control module may be input to the external output device through the external device interface module .

The video signal processed by the control module may be output to the audio output module . Also the video signal processed by the control module may be input to the external output device through the external device interface module .

Although not shown in the control module may include a demultiplexer and a video processor which will be described later with reference to .

In addition the control module controls overall operations of the display device . For example the control module may control the tuner to tune RF broadcasting corresponding to the channel selected by the user or the previously stored channel.

Also the control module may control the display device through a user command input through the user input interface module or its internal program. In particular the control module may allow the user to access the network and download a desired application or a list of desired applications into the display device .

For example the control module controls the tuner to input a signal of a channel selected in accordance with a predetermined channel selection command received through the user input interface module and processes a video audio or data signal of the selected channel. The control module may allow the channel information selected by the user to be output through the display module or the audio output module together with the processed video or audio signal.

For another example the control module may allow a video signal or an audio signal from an external device for example camera or camcorder which is input through the external device interface module to be output through the display module or the audio output module in accordance with an external device video play command received through the user input interface module .

Also the control module may control the display device through a user command input through the user input interface module or its internal program. In particular the control module may allow the user to access the network and download a desired content or a list of contents into the display device .

In the meantime the control module may control the display module to display video. For example the control module may control the display module to display broadcasting image input through the tuner external input image input through the external device interface module image input through the network interface module or image stored in the memory module . At this time the image displayed in the display module may be still image or moving image and may be 2D image or 3D image.

In the meantime if the control module enters a contents viewing list it may control the display module to display contents or a list of contents that can be downloaded in the display device or from the external network.

Also the control module may play contents. At this time the contents may be contents stored in display device received broadcasting contents or externally input contents. The contents may be at least one of broadcasting image external input image audio files still image accessed web screen and document files.

According to the embodiment the control module may control the display module to display a home screen in accordance with an input of movement to home screen.

The home screen may include a plurality of card objects sorted per content source. The card object may include at least one of a card object representing a thumbnail list of a broadcast channel a card object representing a broadcast guide list a card object representing a broadcasting reservation list or a broadcasting recording list and a card object representing a media list within the display device or another device connected with the display device. Also the card object may further include at least one of a card object representing a list of accessed external devices and a card object representing a list related with calls.

Also the home screen may further include an application menu provided with at least one executable application list. If there is an input of card object movement the control module may control the display module to display the corresponding card object through movement or move a card object not displayed in the display module to the display module .

If a predetermined one of a plurality of card objects in the home screen is selected the control module may control the display module to display image corresponding to the corresponding card object.

The control module may control the display module to display received broadcasting image and an object representing corresponding broadcasting image information in the card object displaying broadcasting image. The control module may control the broadcasting image such that the size of the broadcasting image may be fixed by lock.

The control module may control the display module to display a setup object for at least one of video setup audio setup reservation setup pointer setup of the remote controller and network setup in the home screen.

The control module may control the display module to display an object of login help message or exit in a part of the home screen. Also the control module may control the display module to display an object representing the number of all card objects or representing the number of card objects displayed in the display module in a part of the home screen.

If a card object name of a predetermined one of card objects displayed in the display module is selected the control module may control the display module to display the corresponding card object as the whole screen.

Also if an incoming call signal is received in the accessed external device or the display device the control module may control the display module to focus and display a call related card object of a plurality of card objects or move the call related card object into the display module .

In the meantime if the control module enters an application viewing list it may display an application or a list of applications that can be downloaded in the display device or from the external network.

The control module may control installation or driving of the application downloaded from the external network together with various user interfaces. Also the control module may control the display module to display image related to the application implemented by selection of the user.

In the meantime although not shown a channel browsing processor that generates thumbnail image corresponding to a channel signal or external input signal may further be provided.

The channel browsing processor extracts image from the stream signal TS output from the demodulation module or the stream signal output from the external device interface module to generate thumbnail image. The thumbnail image may be input to the control module as it is or encoded. Also the generated thumbnail image may be encoded in a stream format and then input to the control module . Therefore the control module may display a thumbnail list that includes a plurality of thumbnail images by using the input thumbnail image. The thumbnail images of the thumbnail list may be updated in due order or at the same time. Then the user can simply recognize contents of a plurality of broadcast channels.

According to one embodiment for synchronization of contents of the display device if contents for synchronization and a selection signal of the display device for synchronization are received from the user through the user input interface module the control module transmits the selection signal to a predetermined server through the network interface module . If a comparison result of the list of contents is received from the server the control module transmits the contents corresponding to the comparison result to the server.

According to another embodiment if contents for synchronization are received from the predetermined server through the network interface module the control module outputs a list of the received contents through the display module . If a synchronization confirmation command for the received contents is input from the user through the user input interface module the control module controls the memory module to update the list of contents of memory module .

Also if contents for synchronization are received from the predetermined server through the network interface module the control module outputs a notification message to a predetermined zone of the display module . If a confirmation command for the received contents is input from the user through the user input interface module the control module controls the display module to output a list of the received contents.

Also the control module may control the display module to output the notification message together with image data corresponding to the received contents or information on the number of the received contents.

The control module may control the memory module such that the list of the received contents may additionally include contents previously stored in the memory module . Also the control module may control the display module to respectively display the received contents and the contents previously stored in the memory module.

According to another embodiment if a content search keyword and a selection signal of the display device for search are received from the user through the user input interface module the control module transmits the received search information to a predetermined server through the network interface module and receives the search result from the server through the network interface module .

The display module converts the video data and OSD signals processed by the control module or the video and data signals received from the external device interface module to R G B signals respectively to generate driving signals. Examples of the display module may include PDP LCD OLED flexible display and 3D display.

A touch screen may be used as the display module whereby the display module may be used as an input module as well as an output module.

According to one embodiment the display module may output a user interface that includes contents or a list of contents for synchronization which are stored in the memory module for synchronization and search of contents a contents synchronization menu a synchronization notification message and a contents search menu.

The audio output module receives the signal audio processed by the control module for example stereo signal 3.1 channel signal or 5.1 channel signal and outputs the received signal as sound. Various types of speakers may be used as the audio output module .

To sense a gesture of the user the display device may further include a sensing unit not shown that includes at least one of a touch sensor an audio sensor a position sensor and an action sensor as described above. The signal sensed by the sensing unit may be transmitted to the control module through the user input interface module .

The display device may further include a camera module not shown that takes a user. Image information taken by the camera module may be input to the control module .

The control module may sense gesture of the user by using the image taken from the camera module not shown and the signal sensed from the sensing unit respectively or in combination.

The power supply module supplies the corresponding power to the whole portion of the display device . In particular the power supply module can supply the power to the control module that can be implemented in the form of a system on chip SOC the display module for image display and the audio output module for audio output.

To this end the power supply module may further include a converter not shown that converts alternating current to direct current. In the meantime if the display module is implemented as a liquid crystal panel that includes a plurality of back light lamps for example for luminance variable or dimming driving the power supply module may further include an inverter not shown that enables PWN operation.

The remote controller transmits a user input to the user input interface module . To this end the remote controller can use Bluetooth Radio Frequency RF communication infrared IR communication Ultra Wideband UWB ZigBee etc. Also the remote controller can receive the video audio or data signal output from the user input interface module to display the received signal or output audio or vibration.

The aforementioned display device may be a fixed type digital broadcast receiver that can receive at least one of digital broadcasting of ATSC mode 8 VSB mode digital broadcasting of DVB T mode COFDM mode and digital broadcasting of ISDB T mode BST OFDM mode .

The block diagram in corresponds to one of many embodiments. The respective elements of the block diagram may be incorporated added or omitted depending on options of the display device which is actually implemented. In other words two or more elements may be incorporated into one element or one element may be divided into two or more elements as occasion demands.

In contrast to the embodiment in display device may receive and play video contents through the network interface module or the external device interface module without the tuner and the demodulation module illustrated in .

The display device is an example of a video processor that performs signal processing of video stored therein or input video. Another examples of the video signal processor include a set top box that excludes the display module and the audio output module illustrated in the aforementioned DVD player a blu ray player a game device and a computer. Hereinafter the set top box will be described with reference to and .

The network interface module provides an interface for connection with wire wireless network including Internet network. Also the network interface module transmits or receives data to and from other users or other electronic devices through a network connected thereto or another network linked on the connected network.

The memory module may store a program for processing and controlling each signal of the signal processor or may temporarily store the video audio or data signal input from the external device interface module or the network interface module . Also the memory module may store a platform illustrated in and which will be described later.

The signal processor performs signal processing of an input signal. For example the signal processor may demultiplex or decode the input video signal or may demultiplex or decode the input audio signal. To this end the signal processor may further include a video decoder or an audio decoder. The video signal or audio signal subjected to signal processing can be transmitted to the displayer through the external device interface module .

The user input interface module transmits the signal input by the user to the signal processor or transmits the signal from the signal processor to the user. For example the user input interface module may receive various control signals such as power on off action input and setup input which are input by a local key not shown or a remote controller to transmit the control signals to the signal processor .

The external device interface module provides an interface for transmitting or receiving data to and from an external device connected thereto through a wire or wireless cable. In particular the external device interface module provides an interface for transmitting or receiving data to and from the displayer . In addition the external device interface module may provide an interface for transmitting or receiving data to and from external devices such as game devices cameras camcorders computers e.g. notebook computers etc.

In the meantime the set top box may further include a media input module not shown for playing separate media. An example of the media input module includes a blu ray input module not shown . In other words the set top box may include a blu ray player. Media of the input blu ray disk are subjected to signal processing such as demultiplexing or decoding by the signal processor and then transmitted to the displayer through the external device interface module whereby the media are displayed in the displayer .

The displayer includes a tuner an external device interface module a demodulation module a memory module a control module a user input interface module a display module and an audio output module .

Since the tuner the demodulation module the memory module the user input interface module the display module and the audio output module correspond to the tuner the demodulation module the memory module the user input interface module the display module and the audio output module which are illustrated in their description will be omitted.

The external device interface module provides an interface for transmitting or receiving data to and from an external device connected thereto through a wire or wireless cable. In particular the external device interface module provides an interface for transmitting or receiving data to and from the set top box .

Accordingly the video signal or audio signal input through the set top box is output to the display module or the audio output module through the control module .

Referring to the set top box and the displayer are similar to those illustrated in but are different from those illustrated in in that the tuner and the demodulation module are located in the set top box not the displayer . Hereinafter the set top box and the displayer of will be described based on the difference from .

The signal processor performs signal processing of a broadcast signal received through tuner and demodulation module . Also the user input interface module receives an input signal of channel selection channel storage etc.

The display device receives a broadcast signal that includes a video signal transmitted from the broadcasting station . The display device processes the video signal included in the broadcast signal and audio or data signal to be appropriately output from the display device . The display device outputs video or audio based on the processed signal.

In the meantime the display device can perform communication with the network server. The network server can transmit and receive a signal to and from the display device through a random network. For example the network server may be a portable terminal that can be connected with the display device through a wire or wireless base station. Also the network server may be a device that can provide contents to the display device through Internet network. The content provider can provide contents to the display device by using the network server.

The display device can perform communication with the external device . The external device can directly transmit and receive a signal to and from the display device through a wire or wireless cable. For example the external device may be a media memory device or a media player which is used by the user. In other words the external device corresponds to a camera a DVD player a blu ray player or a personal computer.

The broadcasting station the network server or the external device can transmit a signal which includes a video signal to the display device . The display device can display video based on the video signal included in the input signal. Also the display device can transmit the signal which is transmitted from the broadcasting station or the network server to the display device to the external device . Also the display device can transmit the signal which is transmitted from the external device to the display device to the broadcasting station or the network server . In other words the display device serves to directly play and transmit the contents included in the signal transmitted form the broadcasting station the network server and the external device .

This display device includes control module having a demultiplexer a video processor an OSD generator a mixer a frame rate converter and a formatter . The control module may further include an audio processor not shown and a data processor not shown .

The demultiplexer demultipelxes input streams. For example if MPEG 2 TS is input the demultiplexer demultiplexes the MPEG 2 TS and splits the demultiplexed MPEG 2 TS into a video signal an audio signal and a data signal. In this case the stream signal input to the demultiplexer may be the stream signal output from the tuner the demodulation module or the external device interface module .

The video processor can process the demultiplexed video signal. To this end the video processor includes a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal the scaler performs scaling to output resolution of the decoded video signal through the display module .

Also the video decoder may include decoders having various specifications. For example if the demultiplexed video signal is an encoded video signal of the MPEG 2 specification it may be decoded by an MPEG 2 decoder.

Also for example if the demultiplexed video signal is an encoded video signal of the H.264 specification based on a Digital Multimedia Broadcasting DMB mode or DVB H mode it may be decoded by an H.264 decoder.

The OSD generator generates an OSD signal in accordance with input of the user or by itself. For example the OSD generator may generate a signal for displaying various kinds of information on the screen of the display module in the form of graphic or text based on the control signal from the user input interface module . The generated OSD signal may include various data such as a user interface screen of the display device a screen of various menus widget and icon.

For example the OSD generator may generate a signal for displaying broadcast information based on EPG or caption of broadcast video.

The mixer mixes the OSD signal generated by the OSD generator with the decoded video signal processed by the video processor . The mixed signal is provided to the formatter . As the decoded broadcast video signal or the external input signal is mixed with the OSD signal the OSD may be overlaid on the broadcast video or the external input video.

The frame rate converter FRC converts a frame rate of the input video. For example the frame rate converter converts a frame rate of 60 Hz to a frame rate of 120 Hz or 240 Hz. If the frame rate converter converts the frame rate of 60 Hz to the frame rate of 120 Hz a first frame may be inserted between another first frame and the second frame or a third frame predicted from the first frame and the second frame may be inserted between the first frame and the second frame.

If the frame rate converter converts the frame rate of 60 Hz to the frame rate of 240 Hz three same frames may be inserted between another first frame and the second frame or the third frame predicted from the first frame and the second frame may be inserted between the first frame and the second frame. The input frame rate may be maintained without separate conversion.

The formatter receives an output signal of the frame rate converter changes a format of the signal to conform to the display module and then outputs the changed format. For example the formatter may output R G B data signals. The R G B data signals may be output by low voltage differential signaling LVDS or mini LVDS.

The audio processor not shown in the control module may perform audio processing of the demultiplexed audio signal. To this end the audio processor may include various decoders.

If the demutliplexed audio signal is an encoded audio signal the audio processor in the control module may decode the encoded audio signal. For example the demultiplexed audio signal may be decoded by an MPEG 2 decoder MPEG 4 decoder AAC decoder or AC 3 decoder. Also the audio processor in the control module can process base treble and sound volume control.

The data processor not shown in the control module can perform data processing of the demultiplexed data signal. If the demutliplexed data signal is an encoded data signal the data processor in the control module may decode the encoded data signal. The encoded data signal may be electronic program guide EPG information that includes broadcast information such as start time and end time of a broadcast program broadcasted from each channel. For example the EPG information may be ATSC Program and System information protocol ATSC PSIP information in case of the ATSC mode and may include DVB Service Information DVB SI in case of the DVB mode.

The ATSC PSIP information or the DVB SI information may be information included in the aforementioned stream i.e. a header 4 byte of the MPEG 2 TS.

The block diagram of control module in is but for one embodiment. Other modules or elements may be used or added to the respective elements of this block diagram in accordance with an intended application or one or more elements or modules may be omitted.

Referring to a split type platform is designed in such a manner that it is split into a legacy system platform and a smart system platform . An OS kernel may be used in common for the legacy system platform and the smart system platform . The legacy system platform includes a driver on the OS kernel a middleware and an application layer .

The OS kernel is a core of the operating system and can perform at least one of driving of a hardware driver security of hardware and processor in the display device efficient management of system resources memory management interface for hardware based on hardware abstraction multi process and schedule management based on multi process when the display device is driven. In the meantime the OS kernel may further perform power management.

The hardware driver in the OS kernel for example may include a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver and a memory driver.

Also the hardware driver in the OS kernel may further include a character device driver a block device driver and a network device driver as drivers for hardware devices therein. The block device driver may need a buffer equivalent to unit size in accordance with data transmission of a specific block unit. The character device driver may not need a buffer due to data transmission in a basic data unit i.e. character unit.

The OS kernel can be implemented as the kernel based on various operating systems such as unix linux based operating system and window based operating system. Also the OS kernel is an opened OS kernel and can be used generally by other electronic devices.

The driver is located between the OS kernel and the middleware and drives the device for operation of the application layer together with the middleware . For example the driver may include drivers such as a micom in the display device a display module a graphic processing unit GPU a frame rate converter FRC a general purpose input output pin GPIO HDMI system decoder or demultiplexer SDEC video decoder VDEC audio decoder ADEC a personal video recorder PVR and an inter integrated circuit I2C . These drivers interact with the hardware driver in the OS kernel .

Also the driver may further include a driver of a remote controller especially a spatial remote controller which will be described later. The driver of the spatial remote controller may be provided in the OS kernel or the middleware in addition to the driver .

The middleware is located between the OS kernel and the application layer and serves as a medium that allows data to be exchanged between hardware and software. In this case a standardized interface can be provided various environments can be supported and mutual interaction between tasks of different systems can be performed.

Examples of the middleware in the legacy system platform include data broadcasting related middleware i.e. multimedia and hypermedia information coding experts group MHEG middleware and advanced common application platform ACAP middleware broadcast information related middleware i.e. PSIP middleware and SI middleware and peripherals communication related middleware i.e. DLNA middleware.

The application layer on the middleware namely the application layer in the legacy system platform may include a user interface application on various menus in the display device. The application layer on the middleware can be edited by selection of the user and can be updated through the network. This application layer enables the user to input a desired menu of various user interfaces in accordance with input of the remote controller during viewing broadcasting image.

Also the application layer in the legacy system platform may further include at least one of TV guide application Bluetooth application reservation application digital video recorder DVR application hot key application.

In the meantime the library in the smart system platform is located between the OS kernel and the framework and can form the base of the framework . For example the library includes security library web engine library and media library wherein the security library includes secure socket layer SSL the web engine library includes WebKit libc c library and video and audio formats and the media library includes media framework. The library can be made based on C or C and can be exposed to a developer through the framework .

The library may include a runtime that includes a core java library and a virtual machine VM . The runtime forms the base of the framework together with the library .

The virtual machine VM may be a virtual machine that enables a plurality of instances i.e. multi tasking. The virtual machine VM may be allocated in accordance with each application in the application layer . At this time for schedule adjustment and interconnection between the plurality of instances the binder driver not shown in the OS kernel may be driven.

In the meantime the binder driver and the runtime can connect java based application with C based library. The binder driver and the runtime can correspond to middleware of the legacy system.

The framework in the smart system platform includes a program based on the application in the application layer . The framework is compatible with any one of the applications and enables reuse movement or exchanges of components. The framework may include a support program and a program that compiles other software elements. For example the framework may include a resource manager an activity manager related to activities of the application a notification manager and a content provider for briefing of information shared between the applications. The framework can be made based on JAVA.

The application layer on the framework includes various programs that can be driven and displayed in the display device . For example the application layer may include core application that includes at least one of email short message service SMS calendar map and browser. This application layer can be made based on JAVA.

Also the application layer can be divided into application that can be stored in the display device and cannot be deleted by the user and application that can be downloaded through the external device or network and can freely be installed or deleted by the user.

Internet phone service video on demand VOD service web album service social networking service SNS location based service LBS map service web search service and application search service may be performed by network access through the application in the application layer . Also various functions such as games and schedule management may be performed through the application in the application layer .

Referring to an integrated type platform includes an OS kernel a driver a middleware a framework and an application layer . The platform of is different from that of in that the library in is omitted and application layer is an integrated layer. The driver and the framework may correspond to those of .

The platform of may be designed such that the library illustrated in is incorporated into the middleware in . In other words the middleware includes legacy system middleware and display system middleware.

The legacy system middleware may include data broadcasting related middleware i.e. multimedia and hypermedia information coding experts group MHEG middleware and advanced common application platform ACAP middleware broadcast information related middleware i.e. PSIP middleware and SI middleware and peripherals communication related middleware i.e. DLNA middleware.

The display system middleware may include security library web engine library and media library wherein the security library includes secure socket layer SSL the web engine library includes WebKit libc and the media library includes media framework. The display system middleware may further include runtime described above.

The application layer in the legacy system may include menu application TV guide application and reservation application while the application layer in the display system may include email short message service SMS calendar map and browser.

Also the application layer may be divided into application that can be stored in the display device and cannot be deleted by the user and application that can be downloaded through the external device or network and can freely be installed or deleted by the user.

Based on the aforementioned platforms of and various API Application Programming Interface and SDK Software Development Kit can be opened for an application development. In the future or present time. Moreover API can be implemented by calling the function that provides a connection to specific subroutine for implementation in a program.

For example Those API and SDK can be opened by a source involved with a hardware driver in OS kernel such as display driver Wi Fi driver Bluetooth driver USB driver or Audio driver.

According to another embodiment those API and SDK can be opened by a related source in a driver such as a micom in the display device a display module a graphic processing unit GPU a frame rate converter FRC system decoder or demultiplexer SDEC video decoder VDEC audio decoder ADEC a spatial remote controller and so on.

According to another embodiment those API and SDK can be opened by a related source such as PSIP involved with broadcasting information SI middleware or DLNA middleware.

Developers skilled in the art can develop at least one of application that is used for display device control or ran in display device based on the aforementioned platforms of and by using those various open API.

The aforementioned platforms of and can be used generally for various electronic devices as well as the display device. In the meantime the platforms of and may be stored or loaded in the memory module or the control module illustrated in or a separate processor not shown . Also the platforms of and may be stored or loaded in the SI Metadata DB the UI manager or the service manager illustrated in . Also a separate application processor not shown for implementing application may further be provided.

The user can move or rotate the remote controller in up and down direction and left and right direction b of and in front and rear direction c of . The pointer displayed in the display module of the display device corresponds to movement of the remote controller . Since the remote controller moves to the corresponding pointer in accordance with movement on 3D space as shown it may be referred to as a spatial remote controller.

Information on movement of the remote controller which is sensed by a sensor of the remote controller is transmitted to the display device. The display device can obtain a coordinate of the pointer from the information on movement of the remote controller . The display device can display the pointer to correspond to the above coordinate.

If the remote controller becomes far away from the display module the selected zone may be subjected to zoom out. If the remote controller becomes close to display module the selected zone may be subjected to zoom in.

In a state that the specific button of the remote controller is pushed up and down movement and left and right movement may not be recognized. In other words if the remote controller moves to be far away from or close to the display module front and rear movement may be recognized only without recognition of up and down movement and left and right movement. In a state that the specific button of the remote controller is not pushed the pointer is only moved in accordance with up and down movement and left and right movement of the remote controller .

Movement speed or movement direction of the pointer may correspond to that of the remote controller . In this specification the pointer means may in one exemplary application refer to an object displayed in the display module to correspond to action of the remote controller .

Accordingly in addition to an arrow shape illustrated by the pointer various shaped objects may be provided. Examples of the pointer may include dot cursor prompt and thick outline. The pointer may be displayed to correspond to any one point of a horizontal axis and a vertical axis on the display module or may be displayed to correspond to a plurality of points such as line and surface.

The wireless communication module transmits and receives a signal to and from any one of the aforementioned display devices according to the embodiments of the present invention. One of the display devices according to the embodiments of the present invention will be described exemplarily.

In this embodiment the remote controller may include RF module that can transmit and receive a signal to and from the display device in accordance with the RF communication standard. The remote controller may further include IR module that can transmit and receive a signal to and from the display device in accordance with the IR communication standard.

In this embodiment the remote controller transmits a signal which includes information on its movement to the display device through the RF module .

The remote controller can receive the signal transmitted from the display device through the RF module . Also the remote controller can transmit a command on power on off channel change and volume change to the display device through the IR module .

The user input module can include a key pad a button a touch pad or a touch screen. The user can input the command related to the display device to the remote controller by manipulating the user input module . If the user input module includes a hard key button the user can input the command related to the display device to the remote controller through a push action of the hard key button.

If the user input module includes a touch screen the user can input the command related to the display device to the remote controller by touching a soft key of the touch screen.

Also the user input module may include various kinds of input means which can be manipulated by the user such as scroll key and jog key within the range that does not limit the scope of the present invention.

The sensor module may include a gyro sensor or an acceleration sensor . The gyro sensor can sense the information on movement of the remote controller . For example the gyro sensor can sense the information on movement of the remote controller based on x y and z axes. The acceleration sensor can sense information on movement speed of the remote controller . In the meantime the sensor module may further include a distance sensor that senses the distance between the display module and the remote controller .

The output module can output the video or audio signal corresponding to the manipulation of the user input module or the signal transmitted from the display device . The user can recognize whether the user input module has been manipulated or whether the display device has been controlled through the output module .

For example if the user input module is manipulated or if the output module transmits and receives a signal to and from the display device through the wireless communication module the output module may include an LED module for lighting a vibration module that generates vibration a sound output module that outputs sound or a display module that outputs image.

The power supply module supplies the power to the remote controller . If the remote controller does not move for a predetermined time the power supply module can save the power by stopping power supply. The power supply module can resume power supply if a predetermined key provided in the remote controller is manipulated.

The memory module may store various kinds of programs and application data required for control or operation of the remote controller . If the remote controller transmits and receives a signal to and from the display device through the RF module the remote controller and the display device transmit and receive the signal to and from each other through a predetermined frequency band. The control module of the remote control module can store information on the frequency band which can be transmitted and received to and from the display device paired with the remote controller and can refer to the stored information.

The control module controls all matters related to control of the remote controller . The control module can transmit the signal corresponding to predetermined key manipulation of the user input module or the signal corresponding to movement of the remote controller which is sensed by the sensor module to the display device through the wireless communication module .

In the list of applications on the network is displayed in the display module . In other words the user can search and download various applications by directly accessing the corresponding content server or network server.

In a list of various applications in the accessed server is displayed in the display module . The list of applications may include icon representing each application and brief information on each application. In the meantime since the display device according to the embodiments of the present invention enables full browsing it can display the icon or brief information received from the server through zoom in. In this case the user can easily identify the list of applications. This will be described later.

In any one of the list of applications is selected using the pointer of the remote controller . In this case the corresponding application can be downloaded conveniently.

In any one of the corresponding list of applications is selected using the pointer of the remote controller . In this case the corresponding application can be implemented conveniently.

In order to select a predetermined item the pointer moves in accordance with movement of the user by using the remote controller illustrated in and . Also in the embodiment of the present invention various examples for selecting a predetermined item may be provided. For example a cursor displayed on the screen by combination of a directional key and a confirmation key which are arranged in a local key not shown or the remote controller may be used to select a predetermined item.

For another example if the remote controller includes a touch pad the pointer is moved on the display module by touch action of the touch pad. In this way a predetermined item may be selected.

In a screen after log in mail service is displayed in the display module . For example read mail item write mail item sent box item received box item and recycle bin item may be displayed in the display module. Also the received box item may be divided into sender item and title item. In this way the received mails may be arranged and displayed in the display module .

Since the display device according to the embodiment of the present invention enables full browsing when the screen for mail service is displayed the user can use the mail service conveniently.

Since the graphic zone of the GPU can be driven faster than NTSC ATSC action zone of the display apparatus a splash screen is first displayed before a terrestrial screen is displayed whereby boredom of a booting time can be reduced.

According to one embodiment the splash screen can be varied by setup. In other words the splash screen could be any one or more of a photo taken by a digital camera a photo taken by a mobile phone and a capture screen captured in the middle of TV watching depending on user setup. The splash screen will be described in detail with reference to .

Also a plurality of photos can be customized in such a manner that they are set as the splash screen to display different photos whenever booting is performed.

Next if it is completely ready for driving of the NTSC ATSC action zone the NTSC ATSC action zone is driven to display a terrestrial broadcast screen S .

In order to complete booting of the operating system for using functions of the smart TV a predetermined booting time is required. Since the driving time of the NTSC ATSC action zone for displaying the terrestrial broadcast screen is shorter than the booting time of the operating system the terrestrial broadcast screen is displayed to reduce an experience standby time.

According to one embodiment a channel of the terrestrial broadcast screen displayed at the standby time can be varied depending on user setup. The terrestrial broadcast screen will be described later in detail with reference to .

Next if booting of the operating system for using functions of the smart TV is completed the operating system is operated on background and then set to the standby state S .

According to one embodiment in a state that the operating system is on standby on background a predetermined message can be displayed for the user. Also at the same time when booting of the operating system is completed the home screen of the smart TV may be displayed to immediately use the functions of the smart TV.

Next if the signal for entering smart TV function is received from the user the operating system is driven to display a home screen of the smart TV S .

According to one embodiment the user can input the signal for entering smart TV function by using various user input interface means and the display apparatus displays the home screen at the same time when the entry signal is received. Also the home screen may be customized depending on user setup.

Through the above steps the user can wait for the standby time for using the functions of the smart TV without boredom.

If the entry signal is input the display apparatus can display a predetermined message indicating that the operating system for using functions of the smart TV is being booted S . Also the message can include an expected standby time to reach booting completion. In this case the user can identify that the entry signal is normally input and booting is being performed.

Next if the operating system is completely booted the operating system is driven to display the home screen of the smart TV S . The home screen can be customized depending on user setup.

Through the above steps the experience standby time can be minimized to reduce inconvenience even if the user intends to use the functions of the smart TV while watching the terrestrial broadcasting through the display apparatus.

Accordingly as illustrated in the terrestrial screen is displayed for the time when the display apparatus is disabled. Referring to the display apparatus includes an AV decoding section parser hereinafter referred to as first module and a CPU for platform software hereinafter referred to as second module .

The first module is for displaying a terrestrial screen and the second module is for driving the operating system of the smart TV.

Accordingly even though the operating system of the smart TV is not driven the first module receives an AV signal from a tuner and transmits a terrestrial broadcast signal to a display module whereby the display module of the display apparatus can display terrestrial broadcasting.

Also since the first module and the second module can transmit and receive data to and from each other if predetermined functions are required to use the functions of the smart TV the second module can transmit a command to the first module and the first module can report its state to the second module and transmit a response to the command to the second module.

Accordingly while the booting procedure is being performed by the second module as illustrated in the first module can display terrestrial broadcasting.

Also since the CPU of the smart TV requires much power than that of a general TV if the two modules perform AV decoding and platform software task respectively overall throughput can be improved and operation speed can also be improved whereby services can actively be provided to the user.

Also image displayed on the splash screen is stored in CMOS RANI of the display apparatus. The image can promptly be loaded and displayed if the power source is applied to the display apparatus.

As illustrated in the splash screen may be displayed to include a predetermined image and may be displayed to include a message indicating that the smart TV is being booted. In this case since the user can view predetermined photos through the splash screen during booting boredom that may occur during the booting procedure can be reduced.

Also according to one embodiment the message indicating that the smart TV is being booted can include a number or graph image indicating a predetermined time required to reach booting completion.

Also the predetermined image can be varied depending on user setup. Also the predetermined image can be displayed in such a manner that several photos are together displayed or sequentially displayed in the form of slide show.

Also the user can stop loading of the operating system of the smart TV and set a mode for watching terrestrial broadcasting only by inputting a signal for selecting a predetermined menu item .

In other words the display apparatus executes booting of the operating system for using the functions of the smart TV on background and displays terrestrial broadcast screens and on the display module whereby boredom of the standby time required for booting can be reduced.

Also according to the embodiment of the present invention the display screen may display a message indicating that the operating system is being booted as illustrated in or may display the message together with a number or a graph indicating a predetermined time to reach booting completion as in .

Also the message can be displayed in opaque color so as not to disturb the display screen of contents currently in service through the display apparatus.

Also according to the embodiment of the present invention the channel of the displayed terrestrial screen can be set previously. The channel of the displayed terrestrial screen will be described later in detail with reference to .

According to one embodiment the completion messages may be displayed to simply include completion functions only as illustrated in or may be displayed to include menu items and for using various functions of the smart TV as illustrated in .

Referring to examples of the menu items for using various functions of the smart TV include a menu item for moving to the home screen of the smart TV a menu item for moving to a list screen of contents stored in the display apparatus and a menu item for moving to a screen for using Internet service in the display apparatus.

Also unlike shown the menu items can be varied depending on user setup and can be set to menu items for immediately executing most used application or latest application.

Also the menu items can include a menu item for canceling screen switching to allow the user to continue to use contents currently in service through the display apparatus.

Also the completion messages and the menu items for using various functions of the smart TV can be displayed in opaque colors so as not to disturb the display screen of contents currently in service through the display apparatus.

Through the menu items the user can promptly use desired services at the same time when the booting procedure of the smart TV is completed.

The menu items included in the menu should be displayed in the display apparatus as the splash screen and include functions only that can be implemented immediately from the booting controller at the same time when the power source is applied to the display apparatus.

According to one embodiment if the user selects the photo a list of photos stored in the display apparatus is displayed and the user can receive one or more selection signals of the photos for being displayed as the splash screen from the list of photos.

Also if the selection signal of the clock is selected from the menu a shape of the clock can be displayed and if the selection signal of the text is selected from the menu a list of text files stored in the display apparatus can be displayed.

If a predetermined item is selected from the menu by the user the display apparatus can store setup information based on the selected item in the booting controller of the display apparatus and load the setup information during booting.

Through the aforementioned embodiment each user who uses the display apparatus can improve convenience by setting a required splash screen.

For example the display apparatus can display a display screen that includes a menu for setting a terrestrial channel displayed for a booting time of the operating system for using the functions of the smart TV.

The menu can include a menu item for selecting predetermined channels recognized by the display apparatus and can include a menu item for setting a random channel not shown or latest channel as the displayed terrestrial channel.

In other words if a predetermined item is selected from the menu by the user the display apparatus stores setup information based on the selected item in its booting controller loads the setup information during booting and displays terrestrial broadcasting transmitted from the selected terrestrial channel.

In this case since the user can watch a desired channel at the booting standby time convenience of the user can be improved.

Also the display apparatus executes a kernel image file loaded in the memory and starts a booting procedure of a kernel zone S . The display apparatus loads drivers of respective devices provided therein in a memory zone by executing the kernel image file S .

The display apparatus operates drivers of devices operated to output broadcasting program video and audio such as a broadcast network interface a broadcast signal processor a display module and a speaker so as to perform a reset operation of the corresponding devices S .

After the reset operation is completed the display apparatus performs a control operation to secondarily output a broadcast screen S . Then the display apparatus performs a root file system mount operation for performing application programs S .

The display apparatus loads and executes various application programs stored in its memory medium and starts a booting procedure of an application program zone S . The application programs correspond programs related to Internet access and application control for example.

Then a reset operation of devices other than the device for outputting a broadcast screen is performed S . Finally events desired by the user are started depending on the operation of the application programs for example Internet access and application control S .

Accordingly it is advantageous in that the display apparatus can primarily display a specific image before a web or application programs are executed and secondarily display a broadcast screen.

The display apparatus accesses a memory in accordance with background operation regardless of BIOS and primarily displays a specific image stored in the memory . Moreover the display apparatus secondarily displays a DTV broadcast screen .

If loading of device driver D D is completed the display apparatus can execute both WEB and application programs. Accordingly it is advantageous in that the display apparatus can primarily display a specific image before a web or application programs are executed and secondarily display a broadcast screen.

One or more of the aforementioned embodiments may be implemented in a recording medium which can be read by a processor provided in the display apparatus as a code that can be read by the processor. The recording medium that can be read by the processor includes all kinds of recording media in which data that can be read by the processor are stored.

Examples of the recording medium include ROM RAM CD ROM magnetic tape floppy disk and optical data memory. Also another example of the recording medium may be implemented in a type of carrier wave such as transmission through Internet. Also the recording medium that can be read by the processor may be distributed in a computer system connected thereto through the network whereby codes that can be read by the processor can be stored and implemented in a distributive mode.

One or more embodiments described here therefore are directed to a display apparatus and a method for controlling the display apparatus which can improve convenience in use of a user.

One or more of these embodiments provide a display apparatus and a method for controlling the display apparatus which can provide various user interfaces.

One or more of these embodiments provide a display apparatus and a method for controlling the display apparatus in which a user can make feel a booting time which requires a long time in a smart TV short.

In accordance with one embodiment a multifunctional display device comprises a display a storage device to store data a tuner to receive a broadcast signal a network interface to receive packet data an input interface to receive signals from a wireless remote controller a processor to control display of information during booting of an operating system. The operating system is booted in response to a predetermined signal and the information includes first information corresponding to visual information and second information indicating that the operating system is currently booting wherein the operating system controls display of multimedia content.

The multimedia content includes information received through the network interface and one or more applications to be executed. The media information may include at least one image stored in the storage device and the visual information may include a plurality of images stored in the storage device the images sequentially displayed during booting of the operating system.

In addition the visual information may include video from a predetermined channel received through the tuner and the second information may include a status bar indicating a status of booting the operating system.

In addition the processor controls the display of third information after operating system booting has been completed the third information includes a menu having one or more options for replacing the first information with fourth information. The fourth information may correspond to execution of an internet browser or may correspond to a media library the media library including one or more files stored in the storage device or a memory coupled to the display device. In addition the visual information corresponds to execution of a predetermined application.

The processor controls display of third information which allows for selection of a change of the first information. Also the first information may be received through the tuner and the third information is generated by an OSD processor. Also the first and third information may be simultaneously displayed. The third information may allow for selection of one of a plurality of predetermined television channels to be displayed during booting of the operating system.

In accordance with one embodiment an information management method comprises displaying information on a screen of a display device during booting of an operating system wherein the operating system is booted in response to a predetermined signal the first information corresponds to visual information and the second information indicates that the operating system is currently booting wherein the operating system controls display of multimedia content and wherein the display device includes a storage device to store data a tuner to receive a broadcast signal a network interface to receive packet data and an input interface to receive signals from a wireless remote controller.

The multimedia content may include information received through the network interface and one or more applications to be executed. In addition the method may include displaying third information after operating system booting has been completed wherein the third information includes a menu having one or more options for replacing the first information with fourth information.

The fourth information may correspond to execution of an internet browser or may correspond to a media library the media library including one or more files stored in the storage device or a memory coupled to the display device. Also the first information may be received through the tuner and the third information is generated by an OSD processor.

The suffixes module and unit may be given or used in common by considering facilitation in writing this disclosure only but fail to have meanings or roles discriminated from each other.

Also the operating system for the smart TV or multimedia application as described herein may be different from a general operating system of the television or monitor. In another embodiment the operating system may be included as part of e.g. included in the software of the operating system used to control the generate television or monitor functions.

Also a display device as described herein may include an intelligent display device additionally provided with for example a computer support function in addition to a broadcasting receiving function.

The display device can be provided with a more convenient interface such as a manual input unit a touch screen and a spatial remote controller in accordance with additional Internet function in addition to a basic broadcasting receiving function.

Also the display device enables e mailing web browsing banking or games by accessing Internet or computer in accordance with the support of wire or wireless Internet function. For these various functions a standardized general purpose operating system OS can be used.

Accordingly since the display device disclosed herein can freely be provided with or delete various applications on a general purpose OS kernel it may perform user friendly various functions. More detailed examples of the display device include network TV HBBTV smart TV. The display device may be applied to a smart phone as the case may be.

Also the terms content or contents may correspond to for example digital information provided through various wire and wireless communication networks and can be used through a display device and its contents.

Any reference in this specification to one embodiment an embodiment example embodiment etc. means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the invention. The appearances of such phrases in various places in the specification are not necessarily all referring to the same embodiment. Further when a particular feature structure or characteristic is described in connection with any embodiment it is submitted that it is within the purview of one skilled in the art to affect such feature structure or characteristic in connection with other ones of the embodiments.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.


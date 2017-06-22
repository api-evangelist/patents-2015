---

title: State-based provisioning of a client having a windows-based embedded image
abstract: Examples of methods and apparatus are provided for state-based provisioning of a local client having a windows-based embedded image. The apparatus may include a retrieval module of the local client that facilitates locating a remote repository server containing a configuration file and that facilitates obtaining the configuration file from the remote repository server. The apparatus may include a reset check module of the local client that determines whether to reset a previous state of the image based on the configuration file. The apparatus may include an apply settings module of the local client that applies, to the image, one of a first configuration change and a second configuration change based on the determination. The first configuration change may include a configuration update to the previous state of the image. The second configuration change may include a change to the image independent of the previous state of the image.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09407502&OS=09407502&RS=09407502
owner: Wyse Technology L.L.C.
number: 09407502
owner_city: San Jose
owner_country: US
publication_date: 20150728
---
The present application is a continuation of application Ser. No. 13 941 971 filed Jul. 15 2013 which is a continuation of U.S. patent application Ser. No. 13 035 760 filed Feb. 25 2011 now U.S. Pat. No. 8 495 183 granted Jul. 23 2013 which claims the benefit of priority under 35 U.S.C. 119 from U.S. Provisional Patent Application Ser. No. 61 436 874 filed on Jan. 27 2011 the contents of which are hereby incorporated by reference in its entirety for all purposes.

The subject technology relates in general to configuration management and more particularly to state based provisioning of a client having a windows based embedded image.

In order for a client device having an embedded image to apply changes that persist across a reboot of the client device manual installation of software or drivers and or a firmware update of the entire image may be needed. This process may involve downloading a customized image and installing the customized image on the client device. However embedded images can be large in size and thus it may be impractical to download and install entire images just to apply changes to the images especially when desired changes are frequent and or relatively minor and or when there are a large number of client devices that require these changes for example in an enterprise environment.

Examples of methods and apparatus are provided for configuration management. For instance examples of methods and apparatus are provided for among others state based provisioning of a local client having a windows based embedded image. The apparatus may include a retrieval module of the local client that facilitates locating a remote repository server containing a configuration file and that facilitates obtaining the configuration file from the remote repository server. The apparatus may include a reset check module of the local client that determines whether to reset a previous state of the image based on the configuration file. The apparatus may include an apply settings module of the local client that applies to the image one of a first configuration change and a second configuration change based on the determination. The first configuration change may include a configuration update to the previous state of the image. The second configuration change may include a change to the image independent of the previous state of the image.

The detailed description set forth below is intended as a description of various configurations of the subject technology and is not intended to represent the only configurations in which the subject technology may be practiced. The appended drawings are incorporated herein and constitute a part of the detailed description. The detailed description includes specific details for the purpose of providing a thorough understanding of the subject technology. However it will be apparent to those skilled in the art that the subject technology may be practiced without these specific details. In some instances well known structures and components are shown in block diagram form in order to avoid obscuring the concepts of the subject technology.

By way of illustration and not limitation a client device can represent a computer a mobile phone a laptop computer a thin client device a personal digital assistant PDA a portable computing device or a suitable device with a processor. In one example a client device is a smartphone e.g. iPhone Android phone Blackberry etc. . In certain configurations a client device can represent a cashier device an audio player a game console a camera a camcorder an audio device a video device a multimedia device or a device capable of supporting a connection to a remote server. In one example a client device can be mobile. In another example a client device can be stationary. According to one aspect of the disclosure a client device may be a device having at least a processor and memory where the total amount of memory of the client device could be less than the total amount of memory in a server . In one example a client device does not have a hard disk. In one aspect a client device may comprise flash memory instead of a hard disk. In one aspect a client device may include one or more client devices.

In a preferred aspect a client device is a specific purpose client device designed for a specific purpose rather than a general purpose . In a preferred aspect a client device is not a conventional personal computer PC . In one aspect a specific purpose client device may be designed to perform one or a few pre defined dedicated functions. For example a specific purpose client device may be designed to perform less than 10 dedicated functions less than 5 dedicated functions less than 3 dedicated functions or 1 dedicated function. A specific purpose client device may be for example a client device designed as a cashier machine at a department store a client device designed to carry out specific tests or measurements a client device designed to carry out a specific medical application for diagnosis and or treatment of a patient etc. A specific purpose client device preferably includes a write filler that is enabled during its normal operation so that if a user e.g. a cashier not an administrator changes any configuration of an embedded image of the client device such change does not persist across a reboot.

In one aspect a server may represent a computer a laptop computer a computing device a database an in house server a repository server a configuration application server a domain name system DNS server a dynamic host configuration protocol DHCP server a virtual machine e.g. VMware Virtual Machine a desktop session e.g. Microsoft Terminal Server a published application e.g. Microsoft Terminal Server or a suitable device with a processor. In a preferred aspect a server is stationary. In another aspect a server can be mobile. In yet another aspect a server can be embedded. In certain configurations a server may be any device that can represent a client device. In a preferred aspect the server is not a client. In one aspect a server may include one or more servers or functions of one or more servers.

In one example a first device is remote to a second device when the first device is not directly connected to the second device. In one example a first remote device may be connected to a second device over a communication network such as a Local Area Network LAN a Wide Area Network WAN and or other network for remote operations.

When a client device and a server are remote with respect to each other a client device may connect to a server over a public network and or the corporate network for example via a modem connection a LAN connection including the Ethernet or a broadband WAN connection including DSL Cable T1 T3 Fiber Optics Wi Fi or a mobile network connection including GSM GPRS 3G WiMax or other remote network connection.

The public network or the corporate network can be a LAN network a WAN network a wireless network the Internet an intranet or other remote network. In one aspect the public network or the corporate network may include one or more routers for routing data between client devices and or servers. A remote device e.g. client device server on a network may be addressed by a corresponding network address such as but not limited to an Internet protocol IP address an Internet name a Windows Internet name service WINS name a domain name or other system name. These illustrate some examples as to how one device may be remote to another device. But the subject technology is not limited to these examples.

According to certain aspects of the present disclosure the terms server and remote server are generally used synonymously in relation to a client device and the word remote may indicate that a server is in communication with other device s for example over a network connection s .

According to certain aspects of the present disclosure the terms client device and remote client device are generally used synonymously in relation to a server and the word remote may indicate that a client device is in communication with a server s for example over a network connection s .

In one aspect of the disclosure a client device may be sometimes referred to as a client or vice versa. Similarly a server may be sometimes referred to as a server device or vice versa.

In one aspect the terms local and remote are relative terms and a client device may be referred to as a local client device or a remote client device depending on whether a client device is described from a client side or from a server side respectively. Similarly a server may be referred to as a local server or a remote server depending on whether a server is described from a server side or from a client side respectively. Furthermore an application running on a server may be referred to as a local application if described from a server side and may be referred to as a remote application if described from a client side.

In one aspect devices placed on a client side e.g. devices connected directly to a client device s or to one another using wires or wirelessly e.g. using Bluetooth having a short range such as 35 feet or Infrared may be referred to as local devices with respect to a client device and remote devices with respect to a server. Similarly devices placed on a server side e.g. devices connected directly to a server s or to one another using wires or wirelessly e.g. using Bluetooth having a short range such as 35 feet or Infrared may be referred to as local devices with respect to a server and remote devices with respect to a client device.

In some aspects the server may comprise a repository server a DNS server a DHCP server and a configuration application server . Although the server is shown as comprising all of these servers one or more of these servers may be placed outside the server . In some aspects one or more of these servers may be combined together as a single server. In some aspects the server may also be referred to as an in house server because the server may primarily operate to communicate with clients and over a private network such as the corporate network . Boundary may represent the boundary of this private network in which the in house server communicates with the clients and . In some aspects client device and are on the same domain e.g. as represented by the dotted line .

In some aspects at least a portion of the server may be accessible from the public network . For example as shown in the repository server is accessible from the public network . Thus the client device may communicate with the server e.g. the repository server via the public network .

According to various aspects of the subject technology the clients may each be running a windows based embedded image such as any of the Windows Embedded family of operating systems e.g. Windows Embedded Compact Windows Embedded Standard Windows Embedded Enterprise Windows Embedded POSReady. Windows Embedded NAVReady Windows Embedded Server etc. or other suitable embedded images.

In general an embedded image may comprise a write filter that may prevent one or more changes applied to the embedded image from persisting across a reboot of a client device running the embedded image. For example an embedded image may comprise a write filter to allow one or more changes applied to the embedded image with the write filter enabled to be discarded when the client device is shut down. In some embodiments the term shut down may refer to shutting down a machine. In some preferred embodiments the term shut down may refer to shutting down a machine. In another aspect it may include logging off from a machine. In some embodiments as used herein the term reboot or restart may include situations in which a user logs off and logs back into a client device or a client device is shut down and then powered back on. In one example if a user applies a new wallpaper to an embedded image running on a particular client device the new wallpaper does not remain on the embedded image after that particular client device has rebooted.

The write filter may be enabled to ensure that a user does not make any permanent changes e.g. changes that persist across a reboot to an embedded image of a client device. Enabling the write filter is beneficial because it allows an administrator to maintain a uniform configuration for all the embedded images of the client devices in a particular system. If a user makes changes to an embedded image of one of the client devices then only that particular client device needs to be rebooted to reset that embedded image back to the original configuration that is uniform with the other embedded images of the other client devices. Another benefit of enabling the write filter is that it may prevent harmful changes from being applied permanently e.g. applied across reboot to an embedded image of a client device. For example if a user of a client device accidentally downloads a virus that causes harmful changes to an embedded image of the client device then only that client device needs to be rebooted to reset the embedded image back to the original configuration that was not harmed by the virus.

However because of the write filter being enabled making a desired change that persists across reboot to an embedded image may be difficult. According to some approaches in order to apply to an embedded image a change that persists across reboot manual installation of software drivers and or a firmware update of the embedded image is performed to create a customized embedded image having the desired change. The customization may typically occur at the server side e.g. at the server and the entire customized embedded image is deployed to a client e.g. the client device . Thus customization of an embedded image may involve transferring an entire customized embedded image from a server to a client device and or installing the entire customized image on the client device . However an embedded image can be large in size. For example Windows embedded images may need a minimum flash size of 2 gigabytes GB e.g. for the Windows Embedded Standard 2009 and a maximum of 4 GB e.g. for the Windows Embedded Standard 7 . Thus transferring and installing images at such sizes may be impractical especially when desired changes are frequent and or relatively minor or when it involves a large number of client devices.

For example in a large cashier system comprising over 100 cashier machines as client devices if an administrator wants to install a new cashier program on each embedded image running on each cashier machine then the administer may need to create a customized embedded image having the new cashier program at a server and then transfer the customized embedded image from the server to each cashier machine for installation. If the customized embedded image is large in size then transferring this image to each of the 100 cashier machines would be cumbersome. Furthermore if the administrator desires to make frequent changes then a new customized embedded image may need to be transferred to each cashier machine each time a change is made.

According to various aspects of the subject technology after boot up of a client device is initiated a change may be automatically applied to an embedded image of the client device without intervention by a user of the client device thereby making the change appear to the user to be persistent across a reboot of the client device . Thus aspects of the subject technology obviate reinstallation of an entire embedded image with the change onto the client device and the problem of downloading and or installing large images onto the client device may be avoided. According to certain aspects a configuration file may be used to apply such a change to the embedded image. The configuration file may contain information related to one or more desired changes to be applied to the client device . For example the configuration file may contain instructions to apply the one or more desired changes parameters related to the one or more desired changes driver information related to the one or more desired changes application information related to the one or more desired changes and or other suitable information. In some aspects a client device may download a configuration file from a server and or apply to the embedded image of the client device a configuration change based on the configuration file each time the client device boots up. In one preferred aspect transferring the configuration file and applying a configuration change in this manner is critical because any changes made according to the configuration file may appear to be persistent to a user of the client device even though the changes may not be retained on the client device when the client device shuts down or is logged off because of an enabled write filter . Such an arrangement may make the client device independent and self provisioning and therefore transferring and or installing large customized images onto the client device may be advantageously avoided.

According to certain aspects the configuration file may be automatically obtained from a server . For example the configuration file may be stored in the repository server . In some aspects the repository server may be a part of the configuration application server . In some aspects the configuration file may be automatically obtained from the remote repository server or a configuration history folder e.g. in stored on the client device . In some aspects the configuration file may be a default configuration file. In some aspects the obtained configuration file may be compared to a previous configuration file that was last used to apply one or more changes associated with the previous configuration file to the embedded image. When the changes are successfully applied to the embedded image such changes may be referred to as last successfully applied changes. For example if a change is a modification of the screen resolution to 1680 1050 pixels and if the client device supports such a resolution then the change would be successfully applied. In some aspects a last successfully applied change may be understood as the change is compatible with or is supported by the embedded image and or a client device . If the obtained configuration file is the same as the previous configuration file then the last successfully applied change is re applied and it would appear to the user that the change persists across reboot of the client device .

According to certain preferred aspects providing an option of applying a last successfully applied change is beneficial because it ensures that at least one configuration change can be applied to an embedded image especially if a new change that is desired to be applied is not compatible with or is not supported by the embedded image and or the client device . Furthermore providing an option of applying a last successfully applied change is beneficial because it can allow a user to revert back to the last successfully applied change especially if a new change that was applied is no longer desired.

According to various aspects of the subject technology a configuration file may be an extensible markup language XML configuration file or any other suitable files. In a preferred aspect a configuration file is an XML configuration file. In some aspects an XML configuration file may refer to an XML based configuration file. In some aspects an XML configuration file may comprise some or all of the following types of settings 1 remote desktop connections settings 2 device settings 3 operating system OS settings and 4 common settings. The remote desktop connections settings which may also be referred to as connections tags may define settings for remote desktop protocol RDP independent computing architecture ICA VMware View and other suitable remote desktop connections. The device settings may define settings for displays keyboards mice networks audio power wireless connections or other suitable settings of a client device . The OS settings section may define settings for Aero Firewall a web browser e.g. Internet Explorer IE or other suitable web browsers one or more clocks or other suitable settings of a client device .

According to certain aspects a configuration file may conform to a suitable schema. For example an XML configuration file may conform to an XML schema definition XSD file. XSD can be used to express a set of rules to which an XML document e.g. an XML configuration file conforms in order to be considered valid according to that schema. In some preferred aspects using an XML configuration file is essential because it allows the XML configuration file to be validated against the XSD file to ensure that the XML configuration file is in a proper format that is compatible and or supported by a client device. The proper format can allow a configuration change based on the XML configuration file to be applied correctly to an embedded image of the client device. Without such a proper format it may not be possible to apply the configuration change correctly. In some aspects validating the XML configuration file using the XSD file before the XML configuration file is transferred and or applied can prevent a XML configuration file in an improper format from being unnecessarily transferred and or applied thereby beneficially saving resources and time.

In one example configuration data may be transferred from the server to a client device and then be applied on the client device . The configuration data may be transferred using any of Method B Method B and or Method B preferably in this order or in another order . Otherwise Method B may be used. For example if a client device fails to connect to the server using DHCP DNS or local registry values then configuration settings from a factory default configuration file may be applied. According to certain aspects a module that implements method Smay be a part of a module referred to as Hagent UI.exe.

In some aspects a configuration file may specify whether to reset a previous state of the embedded image. If the configuration file specifies a reset be applied then a default configuration is applied to the embedded image before a configuration change based on a new configuration file e.g. a retrieved configuration file is applied to the embedded image. This is beneficial in situations where a completely new configuration is desired while an old configuration is not needed anymore. For example if a user of a client device changes from a first job to a second job within the same company but retains the client device for use then the client device can be reset to completely remove any applications on the client device that were directed to the first job. A new configuration e.g. adding applications directed to the second job can then be applied to the client device. In some aspects if the configuration file does not specify a reset then the configuration change based on the new configuration is applied to the embedded image while disallowing the default configuration from being applied to the embedded image. Applying the new configuration while disallowing the default configuration from being applied is beneficial because it may allow new changes to be appended to an existing configuration of the embedded image.

In a preferred embodiment the modules e.g. through are implemented in software e.g. subroutines and code . In another embodiment some or all of the modules may be implemented in hardware e.g. an Application Specific Integrated Circuit ASIC a Field Programmable Gate Array FPGA a Programmable Logic Device PLD a controller a state machine gated logic discrete hardware components or any other suitable devices and or a combination of both. Additional features and functions of these modules according to various aspects of the present disclosure are further described in the disclosure.

In one example an embedded image of a client device may comprise the operating system module and some or all of the following modules and . In another example an embedded image of a client device may comprise the operating system module and some or all of the following modules and . In another example an embedded image of a client device may comprise the operating system module and some or all of the following modules and . In another example an embedded image of a client device may comprise the operating system module and some or all of the following modules and .

According to some approaches to mass deploy thin client firmware through management software a customized firmware image may need to be created as a package. A write filter of the image may need to be disabled software drivers may need to be installed appropriate configurations may need to be set and the write filter may then need to be enabled. After this process the firmware on the client may need to be pulled from a remote server. This firmware image may be of a large size and may need to be pushed to all the appropriate clients using the customized firmware change.

To prevent this process of a large firmware from being pushed on multiple clients over a network drivers applications to be installed may be specified in a configuration file. In some aspects the applications may also be stored along with the configuration file. As soon as a client boots up a retrieval module e.g. Hagent UI.exe may download the configuration file and use an apply settings module e.g. ClientApp.dll to parse the configuration file check for differences e.g. deltas between a previous configuration file and the newly downloaded configuration file and download and install an appropriate application driver.

The retrieval module may also validate the DHCP tag values. In some aspects the server IP may be needed in order to implement Method B . Depending on the protocol tag port values may be fixed. If the DHCP has FTP as a protocol then the port considered may be 21. Port values of 80 and 443 may be considered in the case of HTTP and HTTPS respectively. If the username tag is not set then anonymous login may be considered. If a protocol tag is not configured then HTTP may be considered by default. In some aspects retrieval module may make sure that even if certain tags are not set default values for those fields may be used see e.g. S in . The foregoing tag values and port values are presented as examples. It is understood that other suitable values may be used.

In some aspects a first one of Method B may comprise a DNS service record lookup. An administrator can configure a DNS server e.g. the DNS server to provide server and port number for a service that may for example be referred to as  wyseconfigserver. tcp. Multiple configuration repository server port values can be provided. The retrieval module may access them in order according to the weight and priority associated with each entry. Since the DNS server may not supply a protocol string associated with each server port entry the retrieval module may try HTTP as a protocol if port number is 80. Otherwise it may try HTTPS and then HTTP for all other port numbers. If lookup for  wyseconfigserver. tcp fails retrieval module may try  wyseconfigserver. tcp plus a domain name and then each sub domain name. For example if the domain name is x.y.z the retrieval module may issue a DNS service location lookup using the following names in order until the DNS server returns a valid answer 

In some aspects if the retrieval module is unable to get a valid answer to DNS service record lookup requests then the retrieval module may implement another method. In this regard a second one of Method B may comprise a DNS host name lookup. An administrator can configure the DNS server to provide server IP for a host name e.g. wyseconfigserver . Since the DNS server may not supply a protocol string nor a port number the retrieval module may use HTTPS on port first. If this fails the retrieval module may use HTTP on port . If lookup for wyseconfigserver fails the retrieval module may try wyseconfigserver plus a domain name and then each sub domain name. For example if the domain name is x.y.z the retrieval module may issue DNS host name lookup on the following names below until the DNS server returns a valid answer 

If the retrieval module receives any valid answer for either the DNS service record lookup or the DNS hostname look up the retrieval module will attempt to download the configuration file using the server details that it received from either of these methods.

According to certain aspects a reset feature or state based provisioning feature may help a client device to be reset to factory settings which may be predefined in the client device . The reset feature may be enabled by setting a reset tag to 1 in the configuration file. When this reset tag is set the apply settings module may first set a default configuration using a default configuration file present in the client device and then apply the configuration in the configuration file which may be downloaded as mentioned in . Thus the client device may be ensured to always have settings that are mentioned in the configuration file.

According to certain aspects the reset tag may remove all RDP connections or other suitable connection settings view settings and web browser settings e.g. Internet explorer favorites in addition to resetting the client device and its OS configurations. Below is an example of how the reset tag may be represented in XML 

The reset tag may help with state based application of a client configuration. In some aspects a client configuration can either simply append to an existing configuration state of a client device or completely reset an existing state of the client device to factory defaults and then apply a new configuration.

As an example of an implementation of method S the apply settings module may load a configuration file and parse the configuration file for a particular group of settings related to drivers or applications to be installed on the client device . The apply settings module may be configured to determine if the configuration file specifies a new version of a driver or an application to be installed. The configuration comparison module may be configured to compare the new version of the driver or the application to a previous version of the driver or the application respectively. If the new version is different from the previous version then the apply settings module is configured to determine if the write filter is enabled disable the write filter if it is enabled and install on the client device the new version of the driver or the application while the write filter is disabled. Doing so may advantageously allow the new version of the driver e.g. driver module or the application e.g. application module to remain on the client device even if the client device is restarted or shut down. illustrates another example of an implementation of the method shown in in accordance with various aspects of the subject technology.

According to certain aspects installing the configuration history folder on the embedded image of the client device is beneficial because it allows previous configuration files stored in the configuration history folder to be compared with a newly retrieved configuration file while obviating the need to retrieve the previous configuration files from a location different from the client device . Such an arrangement may also obviate the need to store the previous configuration files at the different location in order to preserve a history of the configuration changes made to the embedded image if the client device is restarted or shut down.

In one example a user interface application module which may sometimes be referred to herein as Pyramid.exe may be installed on the embedded image of the client device to provide a user interface to allow a user to implement process S process S and or process S. illustrates an example of an implementation of the method shown in in accordance with various aspects of the subject technology.

When the remote option is selected the controls under the remote option become enabled and the controls under local option become disabled. Selecting the remote option may make the client device function in a stand alone mode. The user can select either FTP HTTP or HTTPs as the protocol to be used. For example the default FTP path may be Wyse WES7 if no path is specified in the path field. If the path is mentioned in the user module then the configuration file may be located under Wyse WES7 path for example. If a local user has logged in to the client device then the configuration file downloaded from a remote FTP server may be named Wes7Config.xml for example. If the login is a domain login then the .xml file may exist in that FTP path.

In the case of HTTPs a web server e.g. a configuration application server may have webDav installed. A virtual directory called Pyramid for example may be created. This may be the default context. The virtual directory may be nothing but an alias to a path. On the server the Pyramid virtual directory can be c ConfigMgr for example. Under the virtual path another directory named Wyse WES7 for example may be created.

In the user interface application module if no path is mentioned then a default path may be taken such as c ConfigMgr Wyse WES7. If the administrator desires a different path the different path may be created under c ConfigMgr Wyse WES7 for example. The customized path that the administrator has created may be entered under the path field in the user interface application module .

According to certain aspects if a user desires to persist settings across reboot then a Persist settings across reboot option should be selected. If the user desires to persist a locally existing configuration file e.g. preferably on the client device then the local option should be checked and a recently imported applied configuration file may be applied on every boot.

In some aspects the Save Settings button may save the settings into registry. This is useful if the user just wants to set the client device for remote download and import. If the remote option is selected and the Import button is clicked then the configuration file may be downloaded and imported immediately. If the Persist settings across reboot option is selected then the configuration file may be downloaded and imported on every login or on every boot . In some aspects a password may be encrypted and stored in registry. If the username and password paths are empty then anonymous login may be considered.

According to certain aspects clicking on the Export Configuration button may display the screenshot of the user interface application module shown in . If a user wants to store a current device configuration into a configuration file then the Export Configuration option is to be selected. The user can click on the browse button which may open a Save As dialog box. The destination can be any folder within a configuration management folder installed as a component e.g. as discussed with respect to not the configuration history folder or on any external USB device if plugged in . Exporting the configuration file may be useful for example when a configuration of a first client device is desired to be copied onto a second client device . Thus the configuration file of the first client device can be exported and then applied to the second client device .

The processing system may include a processor for executing instructions and may further include a machine readable medium such as a volatile or non volatile memory for storing data and or instructions for software programs. The instructions which may be stored in a machine readable medium and or may be executed by the processing system to control and manage access to the various networks as well as provide other communication and processing functions. The instructions may also include instructions executed by the processing system for various user interface devices such as a display and a keypad . The processing system may include an input port and an output port . Each of the input port and the output port may include one or more ports. The input port and the output port may be the same port e.g. a bi directional port or may be different ports.

The processing system may be implemented using software hardware or a combination of both. By way of example the processing system may be implemented with one or more processors. A processor may be a general purpose microprocessor a microcontroller a Digital Signal Processor DSP an Application Specific Integrated Circuit ASIC a Field Programmable Gate Array FPGA a Programmable Logic Device PLD a controller a state machine gated logic discrete hardware components or any other suitable device that can perform calculations or other manipulations of information.

A machine readable medium can be one or more machine readable media. Software shall be construed broadly to mean instructions data or any combination thereof whether referred to as software firmware middleware microcode hardware description language or otherwise. Instructions may include code e.g. in source code format binary code format executable code format or any other suitable format of code .

Machine readable media e.g. may include storage integrated into a processing system such as might be the case with an ASIC. Machine readable media e.g. may also include storage external to a processing system such as a Random Access Memory RAM a flash memory a Read Only Memory ROM a Programmable Read Only Memory PROM an Erasable PROM EPROM registers a hard disk a removable disk a CD ROM a DVD or any other suitable storage device. Those skilled in the art will recognize how best to implement the described functionality for the processing system . According to one aspect of the disclosure a machine readable medium is a computer readable medium encoded or stored with instructions and is a computing element which defines structural and functional interrelationships between the instructions and the rest of the system which permit the instructions functionality to be realized. In one aspect a machine readable medium is a non transitory machine readable medium a machine readable storage medium or a non transitory machine readable storage medium. In one aspect a computer readable medium is a non transitory computer readable medium a computer readable storage medium or a non transitory computer readable storage medium. Instructions may be executable for example by a client device or server or by a processing system of a client device or server. Instructions can be for example a computer program including code.

An interface may be any type of interface and may reside between any of the components shown in . An interface may also be for example an interface to the outside world e.g. an Internet network interface . A transceiver block may represent one or more transceivers and each transceiver may include a receiver and a transmitter . A functionality implemented in a processing system may be implemented in a portion of a receiver a portion of a transmitter a portion of a machine readable medium a portion of a display a portion of a keypad or a portion of an interface and vice versa.

According to certain aspects process S process S and or process S may be run as stand alone applications. In one example the user interface application module does not support editing of a configuration file. In one example the user interface application module does not support filtering of settings. In some aspects the user interface application module may be provided as a control panel applet e.g. Pyramid.exe that is bundled along with an embedded image. In some aspects a default name for the configuration file may be WesCfg.xml. In some aspects a default configuration file for factory defaults and an active configuration file may be used.

In some aspects a workflow of the subject technology may present two scenarios one as the control panel applet scenario and another as a stand alone scenario. In the control panel applet scenario the control panel applet can be used to 1 capture settings from a device and write it to a configuration file residing locally or on a USB pen drive and 2 apply the settings read from the configuration file residing locally or on the pen drive onto a device. Clicking on a Capture button of the control panel applet may perform the capture settings functionality and clicking on an Apply button of the control panel applet may perform the apply settings functionality.

In the stand alone scenario DHCP option tags may be set on a proper DHCP server e.g. DHCP server or a proxy DHCP server. Once the client device boots up the retrieval module may query the DHCP tag options and download the configuration file from the repository server using HTTP. Once the file is downloaded the apply settings module may call an export function e.g. ClientApp.dll s exported function to apply the settings on to the client device . A file server path can be configured using a user interface e.g. the user interface application module present on the client device . The UI may take the file server path along with a port number to specify whether it will be HTTP or HTTPS. According to certain aspects the configuration file can be derived from capturing the client device settings or built from scratch using the configuration application module and or .

According to certain aspects the user interface e.g. a user interface application module may provide the following functionality a apply to client device the settings from the a configuration file b save the client device settings to a configuration file e.g. capture settings c reset client device to a default configuration d provide a status output and e provide configuration histories which may sometimes be referred to herein as snapshots.

According to certain aspects the apply settings functionality may comprise importing a configuration file and or reading settings from the configuration file and applying the settings to the client device . The capture settings functionality may comprise writing the captured settings to a configuration file and or exporting the settings. In some aspects a no filtering option may be available. According to certain aspects the reset functionality may comprise applying default settings to the client device internally which means the settings of the default configuration file e.g. may be named WyseDefCfg.xml is applied to the client device . In some aspects the provide configuration histories functionality may comprise displaying a list of configuration histories e.g. snapshots present on the client device . A user interface may be provided that will provide an option to create a snapshot and or to revert to a snapshot.

According to certain aspects the apply settings module the reset check module and or the configuration comparison module may implement ClientApp.dll and export the following functions ReadDeviceSettingstoXML ApplyParserSettings RevertToSnapshot ListSnapshots. The ReadDeviceSettingstoXML function may read a client device s settings and write it to a configuration file. The filename may be passed as a parameter. The ApplyParserSettings function may read settings from a configuration file which is passed as a parameter and apply the settings to the client device . These two functions may be called for example by the control panel applet as well as from the retrieval module during the retrieval of configuration settings. The ClientApp.dll may be used by the configuration application module and or .

In some aspects the RevertToSnapshot function may take a snapshot filename as an input parameter and in turn call the ApplyParserSettings function. The ListSnapshots function may return the list of all snapshot files that are residing on the client device .

According to certain aspects an XSD file may be used to express a set of rules to which an XML document e.g. an XML configuration file may conform in order to be considered valid according to that schema. The XSD file may be named as WESTypes.xsd for example.

In some aspects the retrieval module which may include Hagent UI.exe may be modified to query for DHCP options tags to download the configuration file from a repository server e.g. repository server and apply the settings onto the client device .

According to certain aspects the configuration file may be an XML file. In some aspects the XML file can have three main sections 1 connections section 2 device configuration section and 3 an OS configuration section.

The connections section may comprise settings related to RDP ICA view types of connections and other suitable connections. Examples of settings for RDP connections include 

According to certain aspects the device configuration section may comprise settings related to displays mice keyboards time zones audio networks power wireless and other suitable settings. The settings related to displays may include 

Aspects of the subject technology enable small businesses SMBS to have a lightweight application to manage Windows based thin clients. To achieve this objective SMBs may perform four activities 1 configuration management 2 imaging 3 packaging and 4 scheduling. Aspects of the subject technology provide configuration management for SMBs. One objective of configuration management is for information technology IT administrators to easily configure their Windows based thin clients and get them configured for their users in the least amount of time possible. Currently this may be done via customizations in the image which may be pulled and then deployed. This can become time consuming because image files e.g. Windows based image files are large. In addition customization changes may occur frequently per user and hence this consuming process may need to be repeated. Aspects of the subject technology provide configuration management wherein only a single image from the factory is installed onto the thin clients while all customizations may be pushed from a single configuration file rather than an entire image.

According to certain aspects of the subject technology a configuration manager may provide an out of box experience supportability and personalization. With respect to the out of box experience upon IT administrators receiving embedded thin clients e.g. Windows embedded thin clients customers are able to boot directly into Windows and have all global configurations pushed onto the Windows thin clients from either a local or a remote source. A customer may also be able to create a configuration of their choice by exporting an already configured image via OS or by using a configuration editor application e.g. Configuration Application Module and or . In some aspects the user or IT administrator does not have to update the image to get any general functionality working.

With respect to supportability an IT administrator may be able to keep supporting changes in global or user configurations throughout the support lifecycle of a thin client. This may also apply to any configuration changes needed once the support lifecycle for a particular user is over. Features are provided that allow for the IT administrator to easily keep track of any configuration changes made on a particular device. Furthermore in addition to configurations related to the device the IT administrator may also change policies on the client that are configuration manager specific to allow for flexibility and fault tolerance.

With respect to personalization upon a user logging into his her IT environment thin clients may gather domain joined user specific profile s configurations either locally and or from a network. The granularity of OS device and network settings may allow for the user to have a completely personal experience on a thin client. The user may be productive the moment the user logs onto the thin client because the user specific corporate or preferred configurations may have already been applied with little or no down time.

The following scenarios may be implemented by the subject technology. In a first scenario an administrator has three thin clients in his possession. He opens one thin client and configures this client as he desires e.g. he may change the wallpaper RDP connecting via TS and IE favorites . He can export the configuration file and place it on an FTP server which can be for example the repository server and or the configuration application server . He can then open the other two clients connect them via an Ethernet cable and power the two clients up. The remaining two clients may pick the configuration posted on the FTP server through DHCP.

In a second scenario an administrator has three thin clients that are powered up and already domain joined. Three separate configuration files for three users respectively have already been created. These configuration files have different wallpapers RDP connections through TS and IE favorites from one another. The administrator may place the configuration files in respective user s specific folders on an FTP server which can be for example the repository server and or the configuration application server . He may log in to the three clients as three different users. Each of the three clients may pick up the user configuration specific to the user.

In a third scenario an administrator may receive a support request from a user to add a new browser favorite and to lower the display resolution e.g. to 1280 1024 pixels . The administrator may obtain the specific user configuration file open it up using the configuration capture module change the display resolution to the desired display resolution and add in the web browser favorite. The administrator may save this configuration and place the corresponding configuration file in the user s specific folder on an FTP server which can be for example the repository server and or the configuration application server . The administrator may then ask the user to log off and log in again. The updated user settings may then be picked up by the thin client of the user using DHCP.

In a fourth scenario an administrator may receive another support request from the same user in the third scenario. The user may not like the new resolution and request the old resolution to be re applied. The administrator may then ask the user to open the control panel applet e.g. the user interface application module click on the configuration history tab click on the previous configuration history and hit apply in order to return the user s settings back to the previous configuration.

In a fifth scenario a user has a mobile thin client and would like to access his configuration from his home network. To achieve this the specific user s configuration file is placed on an HTTP server on DMZ by the administrator e.g. this contains the same configuration as the user.xml. The user may log onto his thin client e.g. which may be a laptop and wait for the client to connect over wireless to the home network. The new updated user settings may be picked up by the mobile thin client by HTTPS on the home network.

In a sixth scenario a user now has changed his office location permanently and no longer needs the thin client he is using. Thus the administrator may take back the client. The administrator may configure the same client for another new user. The administrator may open up a stand alone configuration manager e.g. the configuration application module and or and make relevant changes for that specific new user e.g. settings related to RDP IE the wallpaper . The configuration file as created or edited by the stand alone configuration manager may indicate that the thin client wipe out any previous settings before applying the settings from this particular configuration file. The administrator may copy the configuration file onto a USB key open the control panel applet select the import configuration option select the local option specify the path of the configuration file and click on the Import button. In this case the existing thin client configuration may be wiped out and the new configuration may be applied locally from a USB key.

According to certain aspects a Windows thin client may obtain and apply configurations from remote locations e.g. FTP server and or HTTP server via DHCP DNS and or other suitable methods. In addition an administrator may be allowed to place the location of the FTP or HTTP server via an IP address or a friendly name. An appropriate message e.g. a balloon tip at the bottom right of a system tray of an OS may be displayed to the user when a configuration is being applied and hence the system state is being changed .

In some aspects DHCP may be used by default when obtaining configurations from remote locations. If DHCP does not work via the default option tags then the location e.g. via the IP address or the friendly name specific in the client may be used. If even the location specified in client does not work then local default settings may be applied.

According to certain aspects a thin client may also have the ability for an administrator to configure the client locally using user interfaces provided by the operating system and to export that configuration locally onto a flash or a USB drive.

According to certain aspects a configuration manager by default may be able to push updated configurations to an already configured device. These updates may be subsets of a full configuration. When pushing updated configurations only those settings that are part of the update may change without changing the overall state of the device. In some aspects configurations being pushed on thin clients may also be able to reset e.g. wipe out the existing configuration on the thin clients and then apply the new configurations. The particular configuration may depend on the reset tag that comes from the configuration definition file. These features may be implemented for example using method S.

In some aspects the configuration history may be exposed to an administrator per thin client. This may be the last five successfully applied unique configurations on a particular thin client although more or less configurations may be stored in the configuration history e.g. in the configuration history folder . An administrator may be able to select any configuration exposed as part of the configuration history and successfully apply it. The configuration history may store configurations for domain joined and non domain joined users. According to certain aspects no two configurations in the configuration history may be the same e.g. if the exact same configuration file is being applied over and over on the same thin client multiple entries of the same configuration may not need to be stored within the configuration history and only the time stamp of the applied configuration may need to be updated .

According to certain aspects an option to apply the last successfully applied configuration may be allowed. In some aspects an application e.g. the configuration application module and or for IT administrators to create view and edit update configuration files may be provided to ensure ease of use in working with the number of settings configurations by providing a human readable format for all settings.

According to various aspects of the subject technology a domain joined user may be able to access or set his her preferred settings either locally or from a network. Local settings may be specific to hardware such as preferred graphics resolution keyboard mouse settings etc. Network level settings may be specific to user profile the presentation layer and domain. This may allow users to log in to the same terminal and give each user a personalized experience reflective of the user s preferences for as long as the user uses that terminal.

Settings that may be applied on a client may fall into the following categories 1 presentation layer settings e.g. ICA RDP View etc. 2 device settings and 3 OS settings. In some aspects all chosen settings by an administrator may be applied when a system of clients is locked and before users see their desktops upon logging in. In some aspects the settings may be applied in less than ten seconds.

With respect to presentation layer settings a user s presentation layer environment and settings e.g. .rdp file may be placed on the user s desktop. An administrator may be able to allow a thin client to boot in a way such that the administrator selected protocol may only be used as a connection broker upon logging in. This may ensure that the USB stacks support for View RDP and ICA do not conflict when using software such as HP remote graphics e.g. RGS .

According to various aspects of the subject technology a primary purpose of OS settings may be to ensure that the operating system is in a best possible state for an end user to use and be productive and for an IT administrator to reduce support calls costs. Whenever applicable the OS settings listed below may have volatile persist options. The volatile option may imply that the respective setting does not persist upon reboot while the persist option may imply that the respective setting persists upon reboot.

The following OS settings with respect to a keyboard may be supported keyboard repeat delay repeat rate and cursor blink rate.

According to various aspects of the subject technology the configuration manager provided may provide two applications with user interfaces 1 a stand alone application e.g. the configuration application module and or and 2 a control panel applet e.g. the user interface application module comprising the configuration capture module the retrieval module the reset check module the configuration comparison module the apply settings module and or the configuration history folder . 

In some aspects the stand alone application may be used primarily for creating and or editing configurations e.g. based on the settings listed above and also for viewing already created configurations. This application may run on various Windows operating systems including Windows 7 Professional and or Enterprise WES7 Windows Server 2003 Windows Server 2008 and Windows Server 2008 R2. In some aspects the stand alone application when running on a PC or a server based Windows OS may only run in create edit and view modes. In some aspects when the stand alone application is running on a Windows thin client for example two additional functions may be exposed 1 capture thin client settings and display them in a human readable format and 2 apply settings from any configuration file.

According to certain aspects the stand alone application may support configuration history functionality. For example the last ten successfully created viewed edited configurations on a non thin client device may be stored although a greater number or a fewer number of configuration histories may be stored. On a thin client device the stand alone application may leverage the last five successfully applied configurations e.g. same as what is exposed in the control panel applet as described below .

According to various aspects of the subject technology the control panel applet may be used primarily for 1 importing applying configurations from local and remote locations 2 exporting current system configuration to a local flash or USB drive and 3 viewing applying configurations stored in the configuration history e.g. configuration history folder . For importing applying an administrator may be able to provide the actual IP address or friendly name of a FTP HTTP server. For exporting the configuration may be exported to a local storage or USB drive. However the configuration may be exported to other suitable locations. For viewing applying the configuration history may be exposed to an administrator per thin client as discussed above. Furthermore options to specify custom DHCP option tags may be available in this the control panel applet for vendor tag port protocol IP address etc.

According to various aspects of the subject technology a configuration manager is provided that may be compatible with WES 7 clients WES 2009 clients or other suitable clients. In some aspects a user interface application module e.g. the user interface application module which may also be referred to herein as Pyramid.exe may exist under c Program Files Wyse ConfigMgmt for example. In some aspects this path is ensured to be in the file based write filter exclusion list. A configuration history folder e.g. a snapshots folder may exist under c Program Files Wyse ConfigMgmt for example. A default xml configuration file WES7Config.xml may restore to factory defaults. The ClientApp.dll and associated bitmaps may exist under windows system32. According to certain aspects the registry entries listed below exist 

In some aspects the user interface application module may be made available to all users. According to certain aspects XML may be designed to describe data and to focus on what data is. The tags in XML may be not predefined. A user can define his her own tags. XML may be self describing and may use a DTD Document Type Definition to formally describe data. According to certain aspects the configuration file may be in an XML format and may be broadly divided into four main tags 1 connections 2 OS configuration 3 device configuration and 4 common configuration.

In some aspects the connections tag may describe data related to RDP View type of connections and other suitable connections. Examples of RDP connections settings is listed below 

In some aspects RDP connections e.g. .rdp files that are present under the document folder may be considered. In some aspects .rdp files stored anywhere else may be not considered for export. If the configuration file contains RDP connect ion entries then except for default.rdip all other .rdp files may be deleted from the document folder and their respective link files may also be deleted.

The OS configuration tag may describe data related to a web browser e.g. IE Firewall Aero additional clocks wallpaper and other suitable data. For example IE settings may include 

In some aspects the device configuration tag may describe data related to displays mice keyboards networks audio power and time zones. In some aspects display settings may include 

In some aspects the wallpaper is stored in a folder having the same name as the configuration file e.g. an XML configuration file . Thus if an XML configuration file named xyz.xml is exported then a folder named xyz may be created in the same path as the XML file and the wallpaper may be stored in that folder. In some aspects if the xyz.xml file for example has been imported then the folder and the XML file does not need to be deleted. If this is done then exporting may cause an issue as the wallpaper may not exist anymore the wallpaper was applied from the xyz folder . According to certain aspects on a remote repository in which a configuration file either WES7Config.xml or .xml is contained a folder by the same name e.g. WES7Config or as the configuration file may be created. Changes such as a new wallpaper may be placed in this folder. In some aspects the preferred format may be JPEG and the size of the JPEG file may be no more than 1 megabyte to save on storage. However other suitable formats and sizes may be used. In some aspects checking may be not performed on a JPEG file size.

In some aspects the language identification is not displayed as country codes but as human readable text.

According to certain aspects the balanced power saver and the customized power plans may be supported.

According to various aspects of the subject technology the common tag may describe extra and or miscellaneous data. An OS type element may specify whether a configuration file is for WES 7 WES 2009 WTOS Linux or some other suitable operating system.

According to certain aspects a reset tag may control a wipeout feature. If the reset tag value is set to 1 then a default configuration file e.g. WES7Config.xml may be applied first. The .rdp files and shortcut in addition to the IE favorites may be deleted. In some aspects vmView registry settings may be cleared. After this the or global configuration file may be applied e.g. WES7Config.xml . This option can only be set from a server side e.g. server user interface. An example of the reset tag settings is shown below 

According to certain aspects a schema language such as XSD can be used to express a set of rules to which an XML configuration file may conform in order to be considered valid according to that schema. For example the XSD file may be named as WESTypes.xsd. The XSD file e.g. validation file may be used to validate the data present in the XML configuration file e.g. Sand or S . The XSD file may also define as to what value a data can have and also the type of data. For example an inquiry may be how to tell what values are valid for a gatewayCredentialsSource. The following line indicates how the gatewayCredentialsSource element is represented 

The above definition may state that the gatewayCredentialsSource can either have 0 1 or 4 as its value in XML. Any other value may result in failure of validation of the xml configuration file.

According to various aspects of the subject technology the following use case scenarios may arise for the control panel applet e.g. Pyramid 1 USB pen drive transfer e.g. for a small organization and 2 stand alone remote mode. In the USB pen drive transfer scenario a company may be a small unit and may be limited in monetary resources. In this case the control panel applet can be used to configure devices. For example an administrator may configure a device thin client with specific requirements. The administrator may want to deploy this to ten other thin clients. Thus the administrator can open the control panel applet export the configuration to a USB pen drive plug that USB drive to another thin client and import the configuration using the control panel applet.

In the stand alone remote mode scenario multiple clients may need to be configured from a remote repository. In this scenario an administrator may select the remote option e.g. as shown in and fill in the data related to remote IP and remote path. The administrator may select either FTP HTTP or HTTPs and click on a Download and Apply button. These settings may be saved after clicking on the Download and Apply button. The Persist settings on reboot may be checked if the configuration is to be applied after every boot of the client device . In one example a default remote path is Wyse WES7.

According to certain aspects a stand alone application e.g. the configuration application module and or may be provided that generates a configuration file from scratch. This application can be used to edit an existing configuration file as well. The created edited configuration file can be used to apply the configuration either in stand alone mode or in remote mode.

According to certain aspects the retrieval module e.g. which may also be referred to herein as Hagent UI.exe may be an engine that that runs at startup of a client device . This engine may look at the registry values under HKEY LOCAL MACHINE Software Wyse ConfigMgmt or other suitable registries. Depending on the protocol the engine may import configurations. If the protocol is local then an ActiveXML may mention a path of an XML configuration file to be applied. If the XML configuration file exists at that path then configurations may be imported.

According to certain aspects if the protocol is FTP or HTTP then the following order may be used for obtaining the XML configuration file 

According to certain aspects except for the DHCPServerTag all the other tags may be of type String. The DHCPServerTag may be configured as an IPAddress type.

If the foregoing DHCP options are not configured connection fails or a configuration file does not exist on the server then the engine may fail over to the remote settings set from the control panel applet. If the remote settings are not configured e.g. from the control panel applet the connection fails or the configuration file does not exist on the server then the engine may fall back to the locally stored WES7Config.xml.

For example on a server using IIs suppose an administrator sets C Pyramid as the virtual directory. Then the engine may expect a Wyse WES7 folder to be existing under C Pyramid. Thus if HTTP or HTTPs is selected and if login is local and no path is specified then the engine may look for a configuration file named WES7Config.xml under C Pyramid Wyse WES7. If the path is specified then the engine may look for WES7Config.xml under C Pyramid Wyse WES7 . In the case of a domain login the engine may look for .

In some aspects if no protocol is mentioned in the DHCPProtocol option e.g. 183 by default then HTTP may be considered. In some aspects if user name and password are not mentioned in the DHCP option tags then anonymous login may be considered. According to certain aspects the port may be considered depending on the protocol. The port may be 21 for FTP 80 for HTTP and 443 for HTTPS although other port values may be used.

According to various aspects of the subject technology in a scenario of a local user and a domain user the user may have either logged in locally or performed a domain log in. In some aspects this scenario may be tested only in the remote mode. In some aspects if a user performs a local log in then the configuration file downloaded from the remote repository server may be WES7Config.xml. In some aspects if the user performs a domain log in then .xml file may be downloaded and applied.

Illustration of Apparatus Method Machine Readable Storage Medium for Self provisioning of Configuration for a Specific purpose Client Having a Windows based Embedded Image with a Write filter Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 1 13 25 and 38.

1. An apparatus for self provisioning of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

2. The apparatus of clause 1 wherein after each reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

3. The apparatus of clause 1 wherein after each reboot of the specific purpose local client is initiated the retrieval module is configured to automatically facilitate locating a repository server containing a configuration file and facilitate obtaining a configuration file.

5. The apparatus of clause 1 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

6. The apparatus of clause 1 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

7. The apparatus of clause 1 wherein after a reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

9. The apparatus of clause 1 wherein the retrieval module is configured to obtain address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

10. The apparatus of clause 1 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the specific purpose local client.

11. The apparatus of clause 1 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client.

12. The apparatus of clause 1 further comprising a reset check module of the specific purpose local client configured to determine whether to reset a previous state of the windows based embedded image based on the configuration file 

13. A method see e.g. method A of for self provisioning of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the method comprising 

14. The method of clause 13 wherein the applying comprises automatically applying after each reboot of the specific purpose local client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

15. The method of clause 13 wherein the facilitating locating the repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the specific purpose local client is initiated.

17. The method of clause 13 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

18. The method of clause 13 further comprising facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

19. The method of clause 13 wherein the applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

21. The method of clause 13 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

22. The method of clause 13 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

23. The method of clause 13 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client.

24. The method of clause 13 further comprising determining whether to reset a previous state of the windows based embedded image based on the configuration file 

25. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for self provisioning of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the instructions comprising code for 

26. The machine readable storage medium of clause 25 wherein the applying comprises automatically applying after each reboot of the specific purpose local client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

27. The machine readable storage medium of clause 25 wherein the facilitating locating the repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the specific purpose local client is initiated.

29. The machine readable storage medium of clause 25 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

30. The machine readable storage medium of clause 25 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

31. The machine readable storage medium of clause 25 wherein the applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client 

32. The machine readable storage medium of clause 25 wherein the configuration file comprises an XML configuration file.

33. The machine readable storage medium of clause 25 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

34. The machine readable storage medium of clause 25 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

35. The machine readable storage medium of clause 25 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client.

36. The machine readable storage medium of clause 25 wherein the instructions further comprise code for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

37. A computing machine comprising the machine readable storage medium of clause 25 wherein the computing machine comprises the specific purpose local client.

38. An apparatus see e.g. apparatus C of for self provisioning of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

39. The apparatus of clause 38 wherein the means for applying comprises means for automatically applying after each reboot of the specific purpose local client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

40. The apparatus of clause 38 wherein the means for facilitating locating the repository server and the means for facilitating obtaining the configuration file comprise means for automatically facilitating locating the repository server containing the configuration file and means for facilitating obtaining the configuration file after each reboot of the specific purpose local client is initiated.

42. The apparatus of clause 38 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

43. The apparatus of clause 38 further comprising means for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

44. The apparatus of clause 38 wherein the means for applying comprises means for automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

46. The apparatus of clause 38 wherein the means for facilitating locating comprises means for obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

47. The apparatus of clause 38 wherein the means for facilitating locating comprises means for obtaining address information of the repository server from a local registry of the specific purpose local client.

48. The apparatus of clause 38 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client.

49. The apparatus of clause 38 further comprising means for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

Illustration of Apparatus Method Machine Readable Storage Medium for Transferring Configuration Data from a Public Cloud Server and Applying Onto a Mobile Client Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 52 53 54 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 52 64 76 and 89. The other clauses can be presented in a similar manner.

52. An apparatus for obtaining a configuration file over a public network e.g. public network of and applying a persistent configuration change to a windows based embedded image with a write filter e.g. write filter of running on a mobile client e.g. client of and obviating reinstallation of an entire windows based embedded image onto the mobile client the apparatus comprising 

53. The apparatus of clause 52 wherein the retrieval module of the mobile client is configured to facilitate obtaining a configuration file over the public network from the remote repository server each time the mobile client boots up and wherein the apply settings module is configured to apply the configuration change to the windows based embedded image while the write filter is enabled.

54. The apparatus of clause 52 wherein the remote repository server is a hypertext transfer protocol HTTP server and the retrieval module is configured to facilitate obtaining the configuration file securely using hypertext transfer protocol secure HTTPS .

55. The apparatus of clause 52 wherein after each reboot of the mobile client is initiated the apply settings module is configured to automatically apply the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the mobile client to be persistent across a reboot of the mobile client.

56. The apparatus of clause 52 wherein after each reboot of the mobile client is initiated the retrieval module is configured to automatically facilitate locating a repository server containing a configuration file and facilitate obtaining a configuration file.

57. The apparatus of clause 52 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the mobile client or a configuration change to the operating system of the mobile client.

58. The apparatus of clause 52 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the configuration file into a storage area that is to be retained on the mobile client across a reboot of the mobile client.

59. The apparatus of clause 52 wherein after a reboot of the mobile client is initiated the apply settings module is configured to automatically apply without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client to allow the configuration change to appear to the user of the mobile client to be persistent across a reboot of the mobile client.

61. The apparatus of clause 52 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the mobile client.

62. The apparatus of clause 52 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client.

63. The apparatus of clause 52 further comprising a reset check module of the mobile client configured to determine whether to reset a previous state of the windows based embedded image based on the configuration file 

64. A method see e.g. method A of for obtaining a configuration file over a public network e.g. public network of and applying a persistent configuration change to a windows based embedded image with a write filter e.g. write filter of running on a mobile client e.g. client of and obviating reinstallation of an entire windows based embedded image onto the mobile client the method comprising 

65. The method of clause 64 wherein the facilitating obtaining comprises facilitating obtaining the configuration file over the public network from the remote repository server each time the mobile client boots up.

66. The method of clause 64 wherein the remote repository server is a hypertext transfer protocol HTTP server and wherein the facilitating obtaining comprises facilitating obtaining the configuration file securely using hypertext transfer protocol secure HTTPS .

67. The method of clause 64 wherein the applying comprises automatically applying after each reboot of the mobile client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the mobile client to be persistent across a reboot of the mobile client.

68. The method of clause 64 wherein the facilitating locating the remote repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the mobile client is initiated.

69. The method of clause 64 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the mobile client or a configuration change to the operating system of the mobile client.

70. The method of clause 64 further comprising facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the mobile client across a reboot of the mobile client.

71. The method of clause 64 wherein the applying comprises automatically applying after a reboot of the mobile client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client to allow the configuration change to appear to the user of the mobile client to be persistent across a reboot of the specific purpose local client.

73. The method of clause 64 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the mobile client.

74. The method of clause 64 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client.

75. The method of clause 64 further comprising determining whether to reset a previous state of the windows based embedded image based on the configuration file.

76. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for obtaining a configuration file over a public network e.g. public network of and applying a persistent configuration change to a windows based embedded image with a write filter e.g. write filter of running on a mobile client e.g. client of and obviating reinstallation of an entire windows based embedded image onto the mobile client the instructions comprising code for 

77. The machine readable storage medium of clause 76 wherein the facilitating obtaining comprises facilitating obtaining the configuration file over the public network from the remote repository server each time the mobile client boots up.

78. The machine readable storage medium of clause 76 wherein the remote repository server is a hypertext transfer protocol HTTP server and wherein the facilitating obtaining comprises facilitating obtaining the configuration file securely using hypertext transfer protocol secure HTTPS .

79. The machine readable storage medium of clause 76 wherein the applying comprises automatically applying after each reboot of the mobile client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the mobile client to be persistent across a reboot of the mobile client.

80. The machine readable storage medium of clause 76 wherein the facilitating locating the remote repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the mobile client is initiated.

81. The machine readable storage medium of clause 76 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the mobile client or a configuration change to the operating system of the mobile client.

82. The machine readable storage medium of clause 76 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the mobile client across a reboot of the mobile client.

83. The machine readable storage medium of clause 76 wherein the applying comprises automatically applying after a reboot of the mobile client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client to allow the configuration change to appear to the user of the mobile client to be persistent across a reboot of the specific purpose local client.

84. The machine readable storage medium of clause 76 wherein the configuration file comprises an XML configuration file.

85. The machine readable storage medium of clause 76 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the mobile client.

86. The machine readable storage medium of clause 76 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client.

87. The machine readable storage medium of clause 76 wherein the instructions further comprise code for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

88. A computing machine comprising the machine readable storage medium of clause 76 wherein the computer machine comprises the mobile client.

89. An apparatus see e.g. apparatus C of for obtaining a configuration file over a public network e.g. public network of and applying a persistent configuration change to a windows based embedded image with a write filter e.g. write filter of running on a mobile client e.g. client of and obviating reinstallation of an entire windows based embedded image onto the mobile client the apparatus comprising 

90. The apparatus of clause 89 wherein the means for facilitating obtaining comprises means for facilitating obtaining the configuration file over the public network from the remote repository server each time the mobile client boots up.

91. The apparatus of clause 89 wherein the remote repository server is a hypertext transfer protocol HTTP server and wherein the means for facilitating obtaining comprises facilitating obtaining the configuration file securely using hypertext transfer protocol secure HTTPS .

92. The apparatus of clause 89 wherein the means for applying comprises means for automatically applying after each reboot of the mobile client is initiated the configuration change to the windows based embedded image to allow the configuration change to appear to a user of the mobile client to be persistent across a reboot of the mobile client.

93. The apparatus of clause 89 wherein the means for facilitating locating the remote repository server and the means for facilitating obtaining the configuration file comprise means for automatically facilitating locating the repository server containing the configuration file and means for facilitating obtaining the configuration file after each reboot of the mobile client is initiated.

94. The apparatus of clause 89 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the mobile client or a configuration change to the operating system of the mobile client.

95. The apparatus of clause 89 further comprising means for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the mobile client across a reboot of the mobile client.

96. The apparatus of clause 89 wherein the means for applying comprises automatically applying after a reboot of the mobile client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client to allow the configuration change to appear to the user of the mobile client to be persistent across a reboot of the specific purpose local client.

98. The apparatus of clause 89 wherein the means for facilitating locating comprises means for obtaining address information of the repository server from a local registry of the mobile client.

99. The apparatus of clause 89 wherein the another configuration file is a default configuration file saved in a storage area that is retained on the mobile client across a reboot of the mobile client.

100. The apparatus of clause 89 further comprising means for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

Illustration of Apparatus Method Machine Readable Storage Medium for Configuring and Customizing a Specific purpose Client Having a Windows based Embedded Image Using Extensible Markup Language XML Configuration Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 103 104 105 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 103 110 117 and 125. The other clauses can be presented in a similar manner.

103. An apparatus for configuring and customizing a specific purpose local client e.g. client of having a windows based embedded image using extensible markup language XML configuration and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

104. The apparatus of clause 103 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the specific purpose local client and wherein the apply settings module is configured to apply the configuration change to the windows based embedded image while the write filter is enabled.

105. The apparatus of clause 104 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

106. The apparatus of clause 103 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client and a configuration change to the operating system of the specific purpose local client.

107. The apparatus of clause 103 wherein the retrieval module is configured to obtain address information of the remote repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

108. The apparatus of clause 103 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the specific purpose local client.

109. The apparatus of clause 103 further comprising a reset check module of the specific purpose local client configured to determine whether to reset a previous state of the windows based embedded image based on the XML configuration file 

110. A method see e.g. method A of for configuring and customizing a specific purpose local client e.g. client of having a windows based embedded image using extensible markup language XML configuration and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the method comprising 

111. The method of clause 110 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the specific purpose local client and wherein the automatically applying comprises applying the configuration change to the windows based embedded image while the write filter is enabled.

112. The method of clause 111 further comprising facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

113. The method of clause 110 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client and a configuration change to the operating system of the specific purpose local client.

114. The method of clause 110 wherein the automatically locating comprises obtaining address information of the remote repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

115. The method of clause 110 wherein the automatically locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

116. The method of clause 110 further comprising determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

117. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for configuring and customizing a specific purpose local client e.g. client of having a windows based embedded image using extensible markup language XML configuration and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the instructions comprising code for 

118. The machine readable storage medium of clause 117 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the specific purpose local client and wherein the automatically applying comprises applying the configuration change to the windows based embedded image while the write filter is enabled.

119. The machine readable storage medium of clause 118 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

120. The machine readable storage medium of clause 117 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client and a configuration change to the operating system of the specific purpose local client.

121. The machine readable storage medium of clause 117 wherein the automatically locating comprises obtaining address information of the remote repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

122. The machine readable storage medium of clause 117 wherein the automatically locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

123. The machine readable storage medium of clause 117 wherein the instructions further comprise code for determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

124. A computing machine comprising the machine readable storage medium of clause 117 wherein the computing machine comprises the specific purpose local client.

125. An apparatus see e.g. apparatus C of for configuring and customizing a specific purpose local client e.g. client of having a windows based embedded image using extensible markup language XML configuration and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

126. The apparatus of clause 125 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the specific purpose local client and wherein the means for automatically applying comprises means for applying the configuration change to the windows based embedded image while the write filter is enabled.

127. The apparatus of clause 126 further comprising means for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

128. The apparatus of clause 125 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client and a configuration change to the operating system of the specific purpose local client.

129. The apparatus of clause 125 wherein the means for automatically locating comprises means for obtaining address information of the remote repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

130. The apparatus of clause 125 wherein the means for automatically locating comprises means for obtaining address information of the repository server from a local registry of the specific purpose local client.

131. The apparatus of clause 125 further comprising means for determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

Illustration of Apparatus Method Machine Readable Storage Medium for State based Provisioning of a Client Having a Windows based Embedded Image Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 134 135 136 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 134 148 162 and 177. The other clauses can be presented in a similar manner.

134. An apparatus for state based provisioning of a local client e.g. client of having a windows based embedded image the apparatus comprising 

136. The apparatus of clause 135 wherein the default configuration is applied based on a default configuration file contained in the local client.

137. The apparatus of clause 134 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

138. The apparatus of clause 137 wherein the retrieval module is configured to facilitate obtaining the configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

139. The apparatus of clause 137 wherein the apply settings module is configured to apply one of the first configuration change and the second configuration change to the windows based embedded image while the write filter is enabled.

140. The apparatus of clause 137 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

141. The apparatus of clause 134 wherein after each reboot of the local client is initiated the apply settings module is configured to automatically apply one of the first configuration change and the second configuration change to the windows based embedded image to allow one of the first configuration change and the second configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

142. The apparatus of clause 134 wherein after each reboot of the local client is initiated the retrieval module is configured to automatically facilitate locating a repository server containing a configuration file and facilitate obtaining a configuration file.

143. The apparatus of clause 134 wherein each of the first configuration change and the second configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

144. The apparatus of clause 134 wherein after a reboot of the local client is initiated the apply settings module is configured to automatically apply without a user s intervention one of the first configuration change and the second configuration change based on the configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow one of the first configuration change and the second configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

146. The apparatus of clause 134 wherein the retrieval module is configured to obtain address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

147. The apparatus of clause 134 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the local client.

148. A method see e.g. method A of for state based provisioning of a local client e.g. client of having a windows based embedded image the method comprising 

150. The method of clause 149 wherein the default configuration is applied based on a default configuration file contained in the local client.

151. The method of clause 148 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

152. The method of clause 151 wherein the facilitating obtaining comprises facilitating obtaining the configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

153. The method of clause 151 wherein the applying comprises applying the one of the first configuration change and the second configuration change to the windows based embedded image while the write filter is enabled.

154. The method of clause 151 further comprising facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

155. The method of clause 148 wherein the applying comprises automatically applying after each reboot of the local client is initiated one of the first configuration change and the second configuration change to the windows based embedded image to allow one of the first configuration change and the second configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

156. The method of clause 148 wherein the facilitating locating the remote repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the local client is initiated.

157. The method of clause 148 wherein each of the first configuration change and the second configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

158. The method of clause 148 wherein the applying comprises automatically applying after a reboot of the local client is initiated and without a user s intervention one of the first configuration change and the second configuration change based on the configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow one of the first configuration change and the second configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

160. The method of clause 148 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

161. The method of clause 148 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the local client.

162. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for state based provisioning of a local client e.g. client of having a windows based embedded image the instructions comprising code for 

164. The machine readable storage medium of clause 163 wherein the default configuration is applied based on a default configuration file contained in the local client.

165. The machine readable storage medium of clause 162 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

166. The machine readable storage medium of clause 165 wherein the facilitating obtaining comprises facilitating obtaining the configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

167. The machine readable storage medium of clause 165 wherein the applying comprises applying the one of the first configuration change and the second configuration change to the windows based embedded image while the write filter is enabled.

168. The machine readable storage medium of clause 165 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

169. The machine readable storage medium of clause 162 wherein the applying comprises automatically applying after each reboot of the local client is initiated one of the first configuration change and the second configuration change to the windows based embedded image to allow one of the first configuration change and the second configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

170. The machine readable storage medium of clause 162 wherein the facilitating locating the remote repository server and the facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and facilitating obtaining the configuration file after each reboot of the local client is initiated.

171. The machine readable storage medium of clause 162 wherein each of the first configuration change and the second configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

172. The machine readable storage medium of clause 162 wherein the applying comprises automatically applying after a reboot of the local client is initiated and without a user s intervention one of the first configuration change and the second configuration change based on the configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow one of the first configuration change and the second configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

173. The machine readable storage medium of clause 162 wherein the configuration file comprises an XML configuration file.

174. The machine readable storage medium of clause 162 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

175. The machine readable storage medium of clause 162 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the local client.

177. An apparatus see e.g. apparatus C of for state based provisioning of a local client e.g. client of having a windows based embedded image the apparatus comprising 

179. The apparatus of clause 178 wherein the default configuration is applied based on a default configuration file contained in the local client.

180. The apparatus of clause 177 wherein the windows based embedded image comprises a write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

181. The apparatus of clause 180 wherein the means for facilitating obtaining comprises means for facilitating obtaining the configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

182. The apparatus of clause 180 wherein the means for applying comprises means for applying the one of the first configuration change and the second configuration change to the windows based embedded image while the write filter is enabled.

183. The apparatus of clause 180 further comprising means for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

184. The apparatus of clause 177 wherein the means for applying comprises means for automatically applying after each reboot of the local client is initiated one of the first configuration change and the second configuration change to the windows based embedded image to allow one of the first configuration change and the second configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

185. The apparatus of clause 177 wherein the means for facilitating locating the remote repository server and the means for facilitating obtaining the configuration file comprise automatically facilitating locating the repository server containing the configuration file and means for facilitating obtaining the configuration file after each reboot of the local client is initiated.

186. The apparatus of clause 177 wherein each of the first configuration change and the second configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

187. The apparatus of clause 177 wherein the means for applying comprises means for automatically applying after a reboot of the local client is initiated and without a user s intervention one of the first configuration change and the second configuration change based on the configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow one of the first configuration change and the second configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

189. The apparatus of clause 177 wherein the means for facilitating locating comprises means for obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

190. The apparatus of clause 177 wherein the means for facilitating locating comprises means for obtaining address information of the repository server from a local registry of the local client.

Illustration of Apparatus Method Machine Readable Storage Medium for Comparing and Provisioning Configurations for a Client Having a Windows based Embedded Image Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 193 194 195 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 193 206 219 and 233. The other clauses can be presented in a similar manner.

193. An apparatus for comparing and provisioning configurations for a local client e.g. client of having a windows based embedded image the apparatus comprising 

195. The apparatus of clause 193 wherein the windows based embedded image comprises the write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

196. The apparatus of clause 195 wherein the retrieval module is configured to facilitate obtaining the new configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

197. The apparatus of clause 195 wherein the apply settings module is configured to apply one of the new configuration change and the previous configuration change to the windows based embedded image while the write filter is enabled.

198. The apparatus of clause 195 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the previous configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

199. The apparatus of clause 193 wherein after each reboot of the local client is initiated the apply settings module is configured to automatically apply one of the new configuration change and the previous configuration change to the windows based embedded image to allow one of the new configuration change and the previous configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

200. The apparatus of clause 193 wherein after each reboot of the local client is initiated the retrieval module is configured to automatically facilitate locating a repository server containing a new configuration file and facilitate obtaining a new configuration file.

201. The apparatus of clause 193 wherein each of the new configuration change and the previous configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

202. The apparatus of clause 193 wherein after a reboot of the local client is initiated the apply settings module is configured to automatically apply without a user s intervention the previous configuration change based on the previous configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow the previous configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

203. The apparatus of clause 193 wherein at least one of the new configuration file and the previous configuration file comprises an XML configuration file.

204. The apparatus of clause 193 wherein the retrieval module is configured to obtain address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

205. The apparatus of clause 193 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the local client.

206. A method see e.g. method A of for comparing and provisioning configurations for a local client e.g. client of having a windows based embedded image the method comprising 

208. The method of clause 206 wherein the windows based embedded image comprises the write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client 

209. The method of clause 208 wherein the facilitating obtaining comprises facilitating obtaining the new configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

210. The method of clause 208 wherein the applying comprises applying one of the new configuration change and the previous configuration change to the windows based embedded image while the write filter is enabled.

211. The method of clause 208 further comprising facilitating saving while the write filter is enabled the previous configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

212. The method of clause 206 wherein the applying comprises automatically applying after each reboot of the local client is initiated one of the new configuration change and the previous configuration change to the windows based embedded image to allow one of the new configuration change and the previous configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

213. The method of clause 206 wherein the facilitating locating the remote repository server and the facilitating obtaining the new configuration file comprise automatically facilitating locating the repository server containing the new configuration file and facilitating obtaining the new configuration file after each reboot of the local client is initiated.

214. The method of clause 206 wherein each of the new configuration change and the previous configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

215. The method of clause 206 wherein the applying comprises automatically applying after a reboot of the local client is initiated and without a user s intervention the previous configuration change based on the previous configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow the previous configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

216. The method of clause 206 wherein at least one of the new configuration file and the previous configuration file comprises an XML configuration file.

217. The method of clause 206 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

218. The method of clause 206 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the local client.

219. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for comparing and provisioning configurations for a local client e.g. client of having a windows based embedded image the instructions comprising code for 

221. The machine readable storage medium of clause 219 wherein the windows based embedded image comprises the write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

222. The machine readable storage medium of clause 221 wherein the facilitating obtaining comprises facilitating obtaining the new configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

223. The machine readable storage medium of clause 221 wherein the applying comprises applying one of the new configuration change and the previous configuration change to the windows based embedded image while the write filter is enabled.

224. The machine readable storage medium of clause 221 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the previous configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

225. The machine readable storage medium of clause 219 wherein the applying comprises automatically applying after each reboot of the local client is initiated one of the new configuration change and the previous configuration change to the windows based embedded image to allow one of the new configuration change and the previous configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

226. The machine readable storage medium of clause 219 wherein the facilitating locating the remote repository server and the facilitating obtaining the new configuration file comprise automatically facilitating locating the repository server containing the new configuration file and facilitating obtaining the new configuration file after each reboot of the local client is initiated.

227. The machine readable storage medium of clause 219 wherein each of the new configuration change and the previous configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

228. The machine readable storage medium of clause 219 wherein the applying comprises automatically applying after a reboot of the local client is initiated and without a user s intervention the previous configuration change based on the previous configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow the previous configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

229. The machine readable storage medium of clause 219 wherein at least one of the new configuration file and the previous configuration file comprises an XML configuration file 

230. The machine readable storage medium of clause 219 wherein the facilitating locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

231. The machine readable storage medium of clause 219 wherein the facilitating locating comprises obtaining address information of the repository server from a local registry of the local client.

232. A computing machine comprising the machine readable storage medium of clause 219 wherein the computing machine comprises the local client.

233. An apparatus see e.g. apparatus C of for comparing and provisioning configurations for a local client e.g. client of having a windows based embedded image the apparatus comprising 

235. The apparatus of clause 233 wherein the windows based embedded image comprises the write filter that prevents one or more changes applied to the windows based embedded image with the write filter enabled from persisting across a reboot of the local client.

236. The apparatus of clause 235 wherein the means for facilitating obtaining comprises means for facilitating obtaining the new configuration file from the repository server while the write filter is enabled while obviating reinstallation of an entire windows based embedded image onto the local client.

237. The apparatus of clause 235 wherein the means for applying comprises means for applying one of the new configuration change and the previous configuration change to the windows based embedded image while the write filter is enabled.

238. The apparatus of clause 235 further comprising means for facilitating saving while the write filter is enabled the previous configuration file into a storage area that is to be retained on the local client across a reboot of the local client.

239. The apparatus of clause 233 wherein the means for applying comprises means for automatically applying after each reboot of the local client is initiated one of the new configuration change and the previous configuration change to the windows based embedded image to allow one of the new configuration change and the previous configuration change to appear to a user of the local client to be persistent across a reboot of the local client.

240. The apparatus of clause 233 wherein the means for facilitating locating the remote repository server and the means for facilitating obtaining the new configuration file comprise means for automatically facilitating locating the repository server containing the new configuration file and means for facilitating obtaining the new configuration file after each reboot of the local client is initiated.

241. The apparatus of clause 233 wherein each of the new configuration change and the previous configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the local client or a configuration change to the operating system of the local client.

242. The apparatus of clause 233 wherein the means for applying comprises means for automatically applying after a reboot of the local client is initiated and without a user s intervention the previous configuration change based on the previous configuration file saved in a storage area that is retained on the local client across a reboot of the local client to allow the previous configuration change to appear to the user of the local client to be persistent across a reboot of the local client.

243. The apparatus of clause 233 wherein at least one of the new configuration file and the previous configuration file comprises an XML configuration file.

244. The apparatus of clause 233 wherein the means for facilitating locating comprises means for obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

245. The apparatus of clause 233 wherein the means for facilitating locating comprises means for obtaining address information of the repository server from a local registry of the local client.

Illustration of Apparatus Method Machine Readable Storage Medium for Automatic Retrieval Parsing and Application of Configuration for a Specific purpose Client Having a Windows based Embedded Image with a Write filter Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 248 249 250 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 248 262 276 and 291. The other clauses can be presented in a similar manner.

248. An apparatus for automatic retrieval parsing and application of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of while obviating reinstallation of an entire windows based embedded image onto the specific purpose local client and while allowing persistent configuration change across a reboot the apparatus comprising 

253. The apparatus of clause 248 wherein the group of settings for the windows based embedded image comprises a connections group and wherein the configuration change comprises a configuration change to a remote desktop connection.

254. The apparatus of clause 248 wherein the group of settings for the windows based embedded image comprises an operating systems group and wherein the configuration change comprises a configuration change to the operating system of the specific purpose local client.

255. The apparatus of clause 248 wherein the group of settings for the windows based embedded image comprises a device configuration group and wherein the configuration change comprises a configuration change to a device of the specific purpose local client.

256. The apparatus of clause 248 wherein the apply settings module is configured to while the write filter is enabled facilitate saving the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

257. The apparatus of clause 248 wherein after a reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

259. The apparatus of clause 248 wherein the retrieval module is configured to obtain address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

260. The apparatus of clause 248 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the specific purpose local client.

261. The apparatus of clause 248 further comprising a reset check module of the specific purpose local client configured to determine whether to reset a previous state of the windows based embedded image based on the configuration file 

262. A method see. e.g. method A of for automatic retrieval parsing and application of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of while obviating reinstallation of an entire windows based embedded image onto the specific purpose local client and while allowing persistent configuration change across a reboot the method comprising 

265. The method of clause 262 wherein the configuration file specifies a new version of a driver to be installed on the specific purpose local client and wherein the method further comprises 

266. The method of clause 262 wherein the configuration file specifies a new version of an application to be installed on the specific purpose local client and wherein the method further comprises 

267. The method of clause 262 wherein the group of settings for the windows based embedded image comprises a connections group and wherein the configuration change comprises a configuration change to a remote desktop connection.

268. The method of clause 262 wherein the group of settings for the windows based embedded image comprises an operating systems group and wherein the configuration change comprises a configuration change to the operating system of the specific purpose local client.

269. The method of clause 262 wherein the group of settings for the windows based embedded image comprises a device configuration group and wherein the configuration change comprises a configuration change to a device of the specific purpose local client.

270. The method of clause 262 further comprising facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

271. The method of clause 262 wherein the automatically applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

273. The method of clause 262 wherein the automatically locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

274. The method of clause 262 wherein the automatically locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

275. The method of clause 262 further comprising determining whether to reset a previous state of the windows based embedded image based on the configuration file 

276. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for automatic retrieval parsing and application of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of while obviating reinstallation of an entire windows based embedded image onto the specific purpose local client and while allowing persistent configuration change across a reboot the instructions comprising code for 

277. The machine readable storage medium of clause 276 wherein the instructions further comprise code for 

278. The machine readable storage medium of clause 276 wherein the instructions further comprise code for 

279. The machine readable storage medium of clause 276 wherein the configuration file specifies a new version of a driver to be installed on the specific purpose local client and wherein the instructions further comprise code for 

280. The machine readable storage medium of clause 276 wherein the configuration file specifies a new version of an application to be installed on the specific purpose local client and wherein the instructions further comprise code for 

281. The machine readable storage medium of clause 276 wherein the group of settings for the windows based embedded image comprises a connections group and wherein the configuration change comprises a configuration change to a remote desktop connection.

282. The machine readable storage medium of clause 276 wherein the group of settings for the windows based embedded image comprises an operating systems group and wherein the configuration change comprises a configuration change to the operating system of the specific purpose local client.

283. The machine readable storage medium of clause 276 wherein the group of settings for the windows based embedded image comprises a device configuration group and wherein the configuration change comprises a configuration change to a device of the specific purpose local client.

284. The machine readable storage medium of clause 276 wherein the instructions further comprise code for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

285. The machine readable storage medium of clause 276 wherein the automatically applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

286. The machine readable storage medium of clause 276 wherein the configuration file comprises an XML configuration file.

287. The machine readable storage medium of clause 276 wherein the automatically locating comprises obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

288. The machine readable storage medium of clause 276 wherein the automatically locating comprises obtaining address information of the repository server from a local registry of the specific purpose local client.

289. The machine readable storage medium of clause 276 wherein the instructions further comprise code for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

290. A computing machine comprising the machine readable storage medium of clause 276 wherein the computing machine comprises the specific purpose local client.

291. An apparatus see e.g. apparatus C of for automatic retrieval parsing and application of configuration for a specific purpose local client e.g. client of having a windows based embedded image with a write filter e.g. write filter of while obviating reinstallation of an entire windows based embedded image onto the specific purpose local client and while allowing persistent configuration change across a reboot the apparatus comprising 

294. The apparatus of clause 291 wherein the configuration file specifies a new version of a driver to be installed on the specific purpose local client and wherein the apparatus further comprises 

295. The apparatus of clause 291 wherein the configuration file specifies a new version of an application to be installed on the specific purpose local client and wherein the apparatus further comprises 

296. The apparatus of clause 291 wherein the group of settings for the windows based embedded image comprises a connections group and wherein the configuration change comprises a configuration change to a remote desktop connection.

297. The apparatus of clause 291 wherein the group of settings for the windows based embedded image comprises an operating systems group and wherein the configuration change comprises a configuration change to the operating system of the specific purpose local client.

298. The apparatus of clause 291 wherein the group of settings for the windows based embedded image comprises a device configuration group and wherein the configuration change comprises a configuration change to a device of the specific purpose local client.

299. The apparatus of clause 291 further comprising means for facilitating saving while the write filter is enabled the configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

300. The apparatus of clause 291 wherein the means for automatically applying comprises means for automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

302. The apparatus of clause 291 wherein the means for automatically locating comprises means for obtaining address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

303. The apparatus of clause 291 wherein the means for automatically locating comprises means for obtaining address information of the repository server from a local registry of the specific purpose local client.

304. The apparatus of clause 291 further comprising means for determining whether to reset a previous state of the windows based embedded image based on the configuration file 

Illustration of Apparatus Method Machine Readable Storage Medium for Generating Validating and Applying Custom Extensible Markup Language XML Configuration on a Client Having a Windows based Embedded Image Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 307 308 309 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 307 319 331 and 344. The other clauses can be presented in a similar manner.

307. An apparatus for generating validating and applying custom extensible markup language XML configuration on a specific purpose local client e.g. client of having a windows based embedded image and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

308. The apparatus of clause 307 wherein the validation file comprises an XML schema definition XSD file.

309. The apparatus of clause 308 wherein the configuration generation module is configured to determine whether the XML configuration file conforms to one or more rules specified in the XML schema XSD file.

310. The apparatus of clause 307 wherein the retrieval module is configured to obtain the XML configuration file by importing the XML configuration file from at least one of a storage device external to the specific purpose local client and a remote repository server.

311. The apparatus of clause 307 wherein the configuration generation module comprises a configuration capture module configured to capture one or more settings of the specific purpose local client the configuration generation module configured to generate the XML configuration file based on the captured one or more settings.

312. The apparatus of clause 311 wherein the one or more settings comprise at least one of settings of a device of the specific purpose local client settings of the operating system and connections settings.

313. The apparatus of clause 307 wherein the configuration generation module is configured to export the XML configuration file to at least one of a storage device external to the specific purpose local client and a remote repository server.

314. The apparatus of clause 307 wherein the configuration generation module is configured to facilitate saving the XML configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

315. The apparatus of clause 307 wherein after a reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply without a user s intervention the configuration change based on the XML configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

316. The apparatus of clause 307 wherein the configuration generation module comprises a configuration application module configured to provide a user interface for generating and or editing the XML configuration file.

317. The apparatus of clause 307 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

318. The apparatus of clause 307 further comprising a reset check module of the specific purpose local client configured to determine whether to reset a previous state of the windows based embedded image based on the XML configuration file 

319. A method see e.g. method A of for generating validating and applying custom extensible markup language XML configuration on a specific purpose local client e.g. client of having a windows based embedded image and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the method comprising 

320. The method of clause 319 wherein the validation file comprises an XML schema definition XSD file.

321. The method of clause 320 wherein the validating comprises determining whether the XML configuration file conforms to one or more rules specified in the XML schema XSD file.

322. The method of clause 319 wherein the automatically obtaining comprises importing the XML configuration file from at least one of a storage device external to the specific purpose local client and a remote repository server.

323. The method of clause 319 further comprising capturing one or more settings of the specific purpose local client wherein the generating the XML configuration file comprises generating the XML configuration file based on the captured one or more settings.

324. The method of clause 323 wherein the one or more settings comprise at least one of settings of a device of the specific purpose local client settings of the operating system and connections settings.

325. The method of clause 319 further comprising exporting the XML configuration file to at least one of a storage device external to the specific purpose local client and a remote repository server.

326. The method of clause 319 further comprising facilitating saving the XML configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

327. The method of clause 319 wherein the automatically applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the XML configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

328. The method of clause 319 further comprising providing a user interface for generating and or editing the XML configuration file.

329. The method of clause 319 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

330. The method of clause 319 further comprising determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

331. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for generating validating and applying custom extensible markup language XML configuration on a specific purpose local client e.g. client of having a windows based embedded image and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the instructions comprising code for 

332. The machine readable storage medium of clause 331 wherein the validation file comprises an XML schema definition XSD file.

333. The machine readable storage medium of clause 332 wherein the validating comprises determining whether the XML configuration file conforms to one or more rules specified in the XML schema XSD file.

334. The machine readable storage medium of clause 331 wherein the automatically obtaining comprises importing the XML configuration file from at least one of a storage device external to the specific purpose local client and a remote repository server.

335. The machine readable storage medium of clause 331 wherein the instructions further comprise code for capturing one or more settings of the specific purpose local client wherein the generating the XML configuration file comprises generating the XML configuration file based on the captured one or more settings.

336. The machine readable storage medium of clause 335 wherein the one or more settings comprise at least one of settings of a device of the specific purpose local client settings of the operating system and connections settings.

337. The machine readable storage medium of clause 331 wherein the instructions further comprise code for exporting the XML configuration file to at least one of a storage device external to the specific purpose local client and a remote repository server.

338. The machine readable storage medium of clause 331 wherein the instructions further comprise code for facilitating saving the XML configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

339. The machine readable storage medium of clause 331 wherein the automatically applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the XML configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

340. The machine readable storage medium of clause 331 wherein the instructions further comprise code for providing a user interface for generating and or editing the XML configuration file.

341. The machine readable storage medium of clause 331 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

342. The machine readable storage medium of clause 331 wherein the instructions further comprise code for determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

343. A computing machine comprising the machine readable storage medium of clause 331 wherein the computing machine comprises the specific purpose local client.

344. An apparatus see. e.g. apparatus C of for generating validating and applying custom extensible markup language XML configuration on a specific purpose local client e.g. client of having a windows based embedded image and obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the apparatus comprising 

345. The apparatus of clause 344 wherein the validation file comprises an XML schema definition XSD file.

346. The apparatus of clause 345 wherein the means for validating comprises means for determining whether the XML configuration file conforms to one or more rules specified in the XML schema XSD file.

347. The apparatus of clause 344 wherein the means for automatically obtaining comprises means for importing the XML configuration file from at least one of a storage device external to the specific purpose local client and a remote repository server.

348. The apparatus of clause 344 further comprising means for capturing one or more settings of the specific purpose local client wherein the means for generating the XML configuration file comprises means for generating the XML configuration file based on the captured one or more settings.

349. The apparatus of clause 348 wherein the one or more settings comprise at least one of settings of a device of the specific purpose local client settings of the operating system and connections settings.

350. The apparatus of clause 344 further comprising means for exporting the XML configuration file to at least one of a storage device external to the specific purpose local client and a remote repository server.

351. The apparatus of clause 344 further comprising means for facilitating saving the XML configuration file into a storage area that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

352. The apparatus of clause 344 wherein the means for automatically applying comprises means for automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the configuration change based on the XML configuration file saved in a storage area that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

353. The apparatus of clause 344 further comprising means for providing a user interface for generating and or editing the XML configuration file.

354. The apparatus of clause 344 wherein the configuration change comprises one or more of the following a configuration change to a remote desktop connection a configuration change to a device of the specific purpose local client or a configuration change to the operating system of the specific purpose local client.

355. The apparatus of clause 344 further comprising means for determining whether to reset a previous state of the windows based embedded image based on the XML configuration file 

Illustration of Apparatus Method Machine Readable Storage Medium for Specific purpose Client with Configuration History for Self provisioning of Configuration and Obviating Reinstallation of Embedded Image Described as Clauses 

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 358 359 360 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clause 358 368 374 and 381. The other clauses can be presented in a similar manner.

358. A specific purpose local client e.g. client of for self provisioning of configuration and for obviating reinstallation of an entire windows based embedded image onto the specific purpose local client the specific purpose local client having a windows based embedded image with a write filter e.g. write filter of the specific purpose local client comprising 

359. The specific purpose local client of clause 358 wherein the configuration comparison module is configured to determine if the new XML configuration file is different from the plurality of extensible markup language XML configuration files and wherein the apply settings module is configured to facilitate saving the new XML configuration file into the configuration history memory unit if the new XML configuration file is different from the plurality of extensible markup language XML configuration files.

360. The specific purpose local client of clause 358 wherein the apply settings module is configured to apply to the windows based embedded image the new configuration change if the new XML configuration file is different from the previous XML configuration file.

361. The specific purpose local client of clause 360 wherein the new XML configuration file is different from the previous XML configuration file and wherein the apply settings module is configured to while the write filter is enabled facilitate saving the new XML configuration file into the configuration history memory unit that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

362. The specific purpose local client of clause 360 wherein the new XML configuration file is different from the previous XML configuration file and wherein after a reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply without a user s intervention the new configuration change based on the new XML configuration file saved in the configuration history memory unit that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the new configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

364. The specific purpose local client of clause 358 wherein the apply settings module is configured to apply to the windows based embedded image the previous configuration change if the new XML configuration file is the same as the previous XML configuration file.

365. The specific purpose local client of clause 358 wherein after each reboot of the specific purpose local client is initiated the apply settings module is configured to automatically apply one of the new configuration change and the previous configuration change to the windows based embedded image to allow one of the new configuration change and the previous configuration change to appear to a user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

366. The specific purpose local client of clause 358 wherein the retrieval module is configured to obtain address information of the repository server using at least one of a dynamic host configuration protocol DHCP or a domain name system DNS .

367. The specific purpose local client of clause 358 wherein the retrieval module is configured to obtain address information of the repository server from a local registry of the specific purpose local client.

368. A method see e.g. method A of for self provisioning of configuration and for obviating reinstallation of an entire windows based embedded image onto a specific purpose local client e.g. client of the specific purpose local client having a windows based embedded image with a write filter e.g. write filter of the method comprising 

369. The method of clause 368 wherein the comparing comprises determining if the new XML configuration file is different from the plurality of extensible markup language XML configuration files and wherein the method further comprises facilitating saving the new XML configuration file into the configuration history memory unit if the new XML configuration file is different from the plurality of extensible markup language XML configuration files.

370. The method of clause 368 wherein the applying comprises applying to the windows based embedded image the new configuration change if the new XML configuration file is different from the previous XML configuration file.

371. The method of clause 370 wherein the new XML configuration file is different from the previous XML configuration file and wherein the method further comprises facilitating saving while the write filter is enabled the new XML configuration file into the configuration history memory unit that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

372. The method of clause 370 wherein the new XML configuration file is different from the previous XML configuration file and wherein the applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the new configuration change based on the new XML configuration file saved in the configuration history memory unit that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the new configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

374. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method for self provisioning of configuration and for obviating reinstallation of an entire windows based embedded image onto a specific purpose local client e.g. client of the specific purpose local client having a windows based embedded image with a write filter e.g. write filter of the instructions comprising code for 

375. The machine readable storage medium of clause 374 wherein the comparing comprises determining if the new XML configuration file is different from the plurality of extensible markup language XML configuration files and wherein the instructions further comprise code for facilitating saving the new XML configuration file into the configuration history memory unit if the new XML configuration file is different from the plurality of extensible markup language XML configuration files.

376. The machine readable storage medium of clause 374 wherein the applying comprises applying to the windows based embedded image the new configuration change if the new XML configuration file is different from the previous XML configuration file.

377. The machine readable storage medium of clause 376 wherein the new XML configuration file is different from the previous XML configuration file and wherein the instructions further comprise code for facilitating saving while the write filter is enabled the new XML configuration file into the configuration history memory unit that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

378. The machine readable storage medium of clause 376 wherein the new XML configuration file is different from the previous XML configuration file and wherein the applying comprises automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the new configuration change based on the new XML configuration file saved in the configuration history memory unit that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the new configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

380. A computing machine comprising the machine readable storage medium of clause 374 wherein the computing machine comprises the specific purpose local client.

381. An apparatus see e.g. apparatus C of for self provisioning of configuration and for obviating reinstallation of an entire windows based embedded image onto a specific purpose local client e.g. client of the specific purpose local client having a windows based embedded image with a write filter e.g. write filter of the apparatus comprising 

382. The apparatus of clause 381 wherein the means for comparing comprises means for determining if the new XML configuration file is different from the plurality of extensible markup language XML configuration files and wherein the apparatus further comprises means for facilitating saving the new XML configuration file into the configuration history memory unit if the new XML configuration file is different from the plurality of extensible markup language XML configuration files.

383. The apparatus of clause 381 wherein the means for applying comprises means for applying to the windows based embedded image the new configuration change if the new XML configuration file is different from the previous XML configuration file.

384. The apparatus of clause 383 wherein the new XML configuration file is different from the previous XML configuration file and wherein the apparatus further comprises means for facilitating saving while the write filter is enabled the new XML configuration file into the configuration history memory unit that is to be retained on the specific purpose local client across a reboot of the specific purpose local client.

385. The apparatus of clause 383 wherein the new XML configuration file is different from the previous XML configuration file and wherein the means for applying comprises means for automatically applying after a reboot of the specific purpose local client is initiated and without a user s intervention the new configuration change based on the new XML configuration file saved in the configuration history memory unit that is retained on the specific purpose local client across a reboot of the specific purpose local client to allow the new configuration change to appear to the user of the specific purpose local client to be persistent across a reboot of the specific purpose local client.

389. A processor comprising one or more modules configured to perform the method or function described in any one of the foregoing clauses e.g. clauses 1 388 .

390. A machine readable storage medium encoded with instructions executable by a processing system to perform the method or function described in any one of the foregoing clauses e.g. clauses 1 388 .

391. A machine readable storage medium comprising code for causing a client or a server e.g. local client a specific purpose client device or a server to perform the method or function described in any one of the foregoing clauses e.g. clauses 1 388 .

392. The machine readable storage medium of clause 390 or 391 wherein the client or the processing system comprises the machine readable storage medium.

393. An apparatus comprising means for performing the method or function described in any one of the foregoing e.g. clauses 1 388 .

394. An apparatus of any one of the foregoing clauses e.g. clauses 1 388 wherein the apparatus comprises a processing system and a memory.

395. An apparatus comprising components operable to perform the method or function described in any one of the foregoing clauses e.g. clauses 1 388 .

In one aspect any of the foregoing clauses may depend from any one of the foregoing independent clauses or any one of the foregoing dependent clauses. In one aspect any of the clauses may be combined with any other clauses. In one aspect the methods means and modules e.g. software modules or hardware modules described above can be represented in drawings.

Those of skill in the art would appreciate that the various illustrative blocks modules elements components methods and algorithms described herein may be implemented as electronic hardware computer software or combinations of both.

For example a module e.g. a configuration generation module a configuration capture module a configuration application module a retrieval module a reset check module a configuration comparison module an apply settings module an application module a driver module an operating system module a user interface application module a configuration application module an operating system module or any other modules may be implemented as electronic hardware computer software or combinations of both. In one aspect a module s may be an apparatus since a module s may include instructions encoded or stored on a machine readable medium on another device or on a portion thereof. In one aspect a module s may be software e.g. an application a subroutine stored in a machine readable medium and executable by a processing system or a processor. In another aspect a module s may be hardware e.g. machine readable medium encoded with instructions a pre programmed general purpose computer or a special purpose electronic or optical device .

Various modules may reside in one machine or in multiple machines. In one example modules for the server side e.g. a configuration application module an operating system module etc. may be located in one server or spread over multiple servers. In another example modules for the client side e.g. a configuration generation module a configuration capture module a configuration application module a retrieval module a reset check module a configuration comparison module an apply settings module an application module a driver module an operating system module a user interface application module etc. may be located in one client device or spread over multiple client devices.

In one aspect of the disclosure when actions or functions are described as being performed by a module or a component e.g. creating retrieving applying capturing validating storing attempting retrieval checking comparing obtaining facilitating loading parsing installing resetting stopping registering adding disabling enabling locating it is understood that such actions or functions are performed by the module or the component directly or indirectly. As an example when a module is described as performing an action it is understood that the module may perform the action directly or may perform the action indirectly for example by facilitating such an action. For instance when a configuration file is described as being obtained by a module it is understood that the module may obtain the configuration file indirectly by facilitating obtaining the configuration file. In some aspects it is understood that certain functions can be divided into different modules to be performed e.g. a function for an apply settings module can be performed by a retrieval module etc. .

To illustrate this interchangeability of hardware and software various illustrative blocks modules elements components methods and algorithms have been described above generally in terms of their functionality. Whether such functionality is implemented as hardware or software depends upon the particular application and design constraints imposed on the overall system. Skilled artisans may implement the described functionality in varying ways for each particular application.

Various components and blocks may be arranged differently e.g. arranged in a different order or partitioned in a different way all without departing from the scope of the subject technology. In one aspect of the disclosure the modules or elements recited in the accompanying claims may be performed by one module or by a smaller number of modules and this arrangement is within the scope of the claims. In another aspect the modules or elements recited in the accompanying claims may be performed by a larger number of modules and this arrangement is within the scope of the claims. In yet another aspect a module or an element recited in the accompanying claims may be performed by multiple modules and this arrangement is within the scope of the claims. In yet another aspect a function s of a module s may be performed by another module s and this arrangement is within the scope of the claims.

It is understood that the specific order or hierarchy of steps in the processes disclosed is an illustration of exemplary approaches. Based upon design preferences it is understood that the specific order or hierarchy of steps in the processes may be rearranged. Some of the steps may be performed simultaneously. The accompanying method claims present elements of the various steps in a sample order and are not meant to be limited to the specific order or hierarchy presented.

The previous description is provided to enable any person skilled in the art to practice the various aspects described herein. The previous description provides various examples of the subject technology and the subject technology is not limited to these examples. Various modifications to these aspects will be readily apparent to those skilled in the art and the generic principles defined herein may be applied to other aspects. Thus the claims are not intended to be limited to the aspects shown herein but is to be accorded the full scope consistent with the language claims wherein reference to an element in the singular is not intended to mean one and only one unless specifically so stated but rather one or more. Unless specifically stated otherwise the term some refers to one or more. Pronouns in the masculine e.g. his include the feminine and neuter gender e.g. her and its and vice versa. Headings and subheadings if any are used for convenience only and do not limit the invention.

A phrase such as an aspect does not imply that such aspect is essential to the subject technology or that such aspect applies to all configurations of the subject technology. A disclosure relating to an aspect may apply to all configurations or one or more configurations. An aspect may provide one or more examples of the disclosure. A phrase such as an aspect may refer to one or more aspects and vice versa. A phrase such as an embodiment does not imply that such embodiment is essential to the subject technology or that such embodiment applies to all configurations of the subject technology. A disclosure relating to an embodiment may apply to all embodiments or one or more embodiments. An embodiment may provide one or more examples of the disclosure. A phrase such an embodiment may refer to one or more embodiments and vice versa. A phrase such as a configuration does not imply that such configuration is essential to the subject technology or that such configuration applies to all configurations of the subject technology. A disclosure relating to a configuration may apply to all configurations or one or more configurations. A configuration may provide one or more examples of the disclosure. A phrase such a configuration may refer to one or more configurations and vice versa.

The word exemplary is used herein to mean serving as an example or illustration. Any aspect or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspects or designs.

All structural and functional equivalents to the elements of the various aspects described throughout this disclosure that are known or later come to be known to those of ordinary skill in the art are expressly incorporated herein by reference and are intended to be encompassed by the claims. Moreover nothing disclosed herein is intended to be dedicated to the public regardless of whether such disclosure is explicitly recited in the claims. No claim element is to be construed under the provisions of 35 U.S.C. 112 sixth paragraph unless the element is expressly recited using the phrase means for or in the case of a method claim the element is recited using the phrase step for. Furthermore to the extent that the term include have or the like is used in the description or the claims such term is intended to be inclusive in a manner similar to the term comprise as comprise is interpreted when employed as a transitional word in a claim.


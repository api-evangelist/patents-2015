---

title: Memory controller, storage device, server virtualization system, and storage device recognizing method performed in the server virtualization system
abstract: A memory controller, a storage device (SD), a server virtualization system, and an SD recognizing method performed in the server virtualization system are provided. The memory controller includes a processor configured to generate a plurality of different pieces of identify device (ID) data in response to an identify device command received from a host so that the host recognizes a single physical SD as a plurality of physical storage devices (SDs), and a host interface which transmits the generated plurality of pieces of identify device data to the host.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09619176&OS=09619176&RS=09619176
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09619176
owner_city: Suwon-si, Gyeonggi-Do
owner_country: KR
publication_date: 20150630
---
This application claims priority to Korean Patent Application No. 10 2014 0107758 filed on Aug. 19 2014 in the Korean Intellectual Property Office the disclosure of which is incorporated by reference in its entirety herein.

The inventive concept relates to a virtualization system and a method of controlling the virtualization system and more particularly to a memory controller a storage device a server virtualization system and a storage device recognizing method performed in the server virtualization system.

With developments in processor technology interest in virtualization technology is increasing. In virtualization technology a single physical device is able to independently operate many operating systems OSs . In general systems to which virtualization technology is applied provide increased resource usage efficiency but have degraded input output I O performances. Accordingly research into virtualization systems having improved I O performances is being conducted.

At least embodiment of the inventive concept provides a memory controller that processes an identify device command so that a host recognizes a single physical storage device as a plurality of storage devices.

At least one embodiment of the inventive concept also provides a storage device that generates identify device data so that a host recognizes a single physical storage device as a plurality of storage devices.

At least embodiment of the inventive concept also provides a server virtualization system that performs device identification so that a plurality of virtual machines are connected to a single physical storage device.

At least one embodiment of the inventive concept also provides a storage device recognizing method performed in a server virtualization system by which a host recognizes a single physical storage device as a plurality of storage devices.

According to an exemplary embodiment of the inventive concept there is provided a memory controller including a processor which generates a plurality of pieces of identify device data in response to an identify device command received from a host and a host interface which transmits the generated plurality of pieces of identify device data to the host.

According to an exemplary embodiment the processor may generate a plurality of different pieces of identify device data so that the host recognizes a single physical device SD as a plurality of physical devices in response to the received identify device command.

According to an exemplary embodiment the plurality of pieces of identify device data may include information that defines a virtual storage device SD corresponding to each of a plurality of storage regions into which the single physical SD is divided.

According to an exemplary embodiment the information that defines the virtual SD may be determined to have a unique device port address when the memory controller communicates with the host.

According to an exemplary embodiment the information that defines the virtual SD may include at least one selected from information about a serial number and information about a world wide name WWN .

According to an exemplary embodiment the processor may generate a plurality of pieces of identify device data in response to a single identify device command and the plurality of pieces of identify device data may include different pieces of serial number information and different pieces of WWN information.

According to an exemplary embodiment the processor may divide a storage region of the single physical SD into a plurality of storage regions based on an initially set command and may set unique identify device data for a virtual SD corresponding to each of the plurality of storage regions.

According to an exemplary embodiment the processor may divide the storage region into the plurality of storage regions by dividing a maximum logical block address of the single physical SD by N wherein N is a natural number equal to or greater than 2.

According to an exemplary embodiment the memory controller may further include a memory that stores the plurality of pieces of identify device data.

According to an exemplary embodiment of the inventive concept there is provided a storage device SD including a memory controller which generates a control signal based on a command received from a host and a memory device which writes or reads data based on the control signal wherein the memory controller transmits a plurality of different pieces of identify device data to the host in response to an identify device command received from the host so that the host recognizes the memory device as a plurality of physical storages devices.

According to an exemplary embodiment the memory controller may transmit to the host a plurality of different pieces of identify device data respectively corresponding to a plurality of storage regions into which a storage region of the memory device is divided in response to the received identify device command.

According to an exemplary embodiment each of the plurality of pieces of identify device data may include at least one selected from information about a serial number and information about a WWN and different serial numbers and different pieces of WWNs may be allocated for the plurality of storage regions.

According to an exemplary embodiment the memory device may be at least one non volatile memory device.

According to an exemplary embodiment the memory controller may read the plurality of pieces of identify device data from the memory device according to the identify device command and may transmit the read plurality of pieces of identify device data to the host.

According to an exemplary embodiment the memory controller may calculate a physical address of the memory device based on device port address information and logical block address information that are received from the host.

According to exemplary embodiment of the inventive concept there is provided a server virtualization system including a server which communicates with devices that are connected to a host bus adaptor HBA and processes data in a virtualization environment and at least one storage device SD that is connected to the HBA. A single physical SD of the at least one SD transmits a plurality of pieces of identify device data to the server in response to an identify device command received from the server so that the server recognizes the single physical SD as a plurality of physical storage devices SDs .

According to an exemplary embodiment the at least one SD may transmit to the server a plurality of different pieces of identify device data respectively corresponding to a plurality of storage regions into which an overall storage capacity of the single physical SD is divided in response to the received identify device command.

According to an exemplary embodiment the server may include a plurality of virtual machines VMs obtained by implementing a computing environment by using software a hypervisor which manages the plurality of VMs and the HBA which is connected to the at least one storage device and performs interfacing for data communication.

According to an exemplary embodiment the HBA may support a single root input output virtualization SR IOV function for providing I O virtualization.

According to an exemplary embodiment the HBA may transmit the identify device command to a device connected to the server.

According to an exemplary embodiment the HBA may allocate a plurality of virtual SDs derived from the single physical SD to the plurality of VMs based on the plurality of pieces of identify device data.

According to an exemplary embodiment the HBA allocates the plurality of VMs to at least one physical SD or to the plurality of virtual SDs.

According to an exemplary embodiment the server may include a plurality of virtual machines VMs obtained by implementing a computing environment by using software a hypervisor which manages the plurality of VMs and a network adaptor which is connected to the at least one storage device on a network and performs interfacing for data communication.

According to exemplary embodiment of the inventive concept there is provided a storage device SD recognition method performed in a server virtualization system the method including receiving by a single physical SD an identify device command from a host during device recognition and transmitting by the single physical SD a plurality of different pieces of identify device data to the host in response to the identify device command. The plurality of pieces of identify device data are generated numbering as many as a number of virtual SDs respectively corresponding to a plurality of storage regions into which the single physical SD is divided.

According to an exemplary embodiment the plurality of pieces of identify device data may include different pieces of serial numbers and different pieces of WWNs for the virtual SDs respectively corresponding to the plurality of storage regions into which the single physical SD is divided.

According to an exemplary embodiment of the inventive concept a server virtualization system is provided. The system includes a plurality of virtual machines comprising a first group of virtual machines and a second group of virtual machines a plurality of first physical storage devices SDs a hypervisor configured to allocate the first physical SDs only to the first group among the virtual machines and an adaptor configured to interface with the first physical SDs and allocate the first physical SDs only to the second group among the virtual machines.

In an exemplary embodiment the system further includes a processor configured to generate different identity device data for each of a plurality of second physical SDs to enable a single one of the first physical SDs to be recognized as the plurality of second physical SDs. In an exemplary embodiment the adaptor or the hypervisor are configured to allocate some of the second physical SDs to a first one of the virtual machines and another one of the second physical SDs to a second one of the virtual machines. In an exemplary embodiment each identity device data includes a different world wide name and serial number pair. In an exemplary embodiment the adaptor is one of a network adaptor and a host bus adaptor.

Hereinafter the inventive concept will be described more fully with reference to the accompanying drawings in which exemplary embodiments of the inventive concept are shown. These embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the inventive concept to one of ordinary skill in the art. As the inventive concept allows for various changes and numerous embodiments particular embodiments will be illustrated in the drawings and described in detail in the written description. However this is not intended to limit the inventive concept to particular modes of practice and it is to be appreciated that all changes equivalents and substitutes that do not depart from the spirit and technical scope of the inventive concept are encompassed in the inventive concept. In the drawings like reference numerals denote like elements and the sizes or thicknesses of elements may be exaggerated for clarity of explanation.

An expression used in the singular encompasses the expression in the plural unless it has a clearly different meaning in the context.

Referring to the computing system A includes a processor a memory an input output I O sub system a host bus adaptor HBA devices and a bus .

Referring to the processor the memory the I O sub system the HBA and the bus constitutes a host A and first through n th storage devices SDs through namely the devices are external devices that are connected to the host A.

For example the computing system A may be assumed to be a server. In another example the computing system A may be a personal computer PC a set top box a modem a mobile device or the like. For example the devices that are connected to the host A may include the first through n th SDs through 

The processor may include a circuit interfaces or a program code for processing data and controlling operations of the components of the computing system A. For example the processor may include a central processing unit CPU an advanced risk machine ARM processor or an application specific integrated circuit ASIC .

The memory may include a static random access memory SRAM or a dynamic random access memory DRAM which stores data commands or program codes which are necessary for operations of the computing system A. The memory may include a non volatile memory. The memory may store program codes that operate to execute at least one operating system OS and virtual machines VMs . The memory may also store program codes that execute a hypervisor for managing the VMs.

The processor using the memory may operate to execute the at least one OS and the VMs. The processor may also operate to execute the hypervisor for managing the VMs or to be controlled by the hypervisor. In such a way the processor may operate to control operations of the components of the computing system A.

The processor may include a software switch that is employed by the hypervisor in order to provide network connectivity between the VMs or connectivity between the VMs and the first through n th SDs through . The software switch is also called a virtual switch. In an exemplary embodiment the software switch is an Internet Protocol IP application programming interface API .

The I O sub system may include a circuit interfaces or a program code capable of operating to perform data communication between the components of the computing system A. The I O sub system may include at least one standardized bus and at least one bus controller. Accordingly the I O sub system may recognize devices connected to the bus list the devices connected to the bus and allocate or deallocate resources for various devices connected to the bus . In other words the I O sub system may operate to manage communications on the bus . For example the I O sub system may be a PCIe system and may include a PCIe root complex and at least one PCIe switch or bridge. For example the I O sub system may be controlled by the hypervisor.

The HBA connects the first through n th SDs through to the computing system A. For example the HBA may include a small computer system interface SCSI adaptor a fiber channel adaptor a serial advanced technology attachment ATA adaptor or the like. In detail the HBA may be directly connected to the first through n th SDs through which are based on a fiber channel FC HBA. The HBA may interface the host A with the first through n th SDs through by being connected to the first through n th SDs through in a storage network area SAN environment.

The HBA may include a single root I O virtualization SR IOV function . For example the SR IOV function has been developed to improve the I O performance of a storage device in a server virtualization environment and directly connects a VM of a server virtualization system to the storage device. Accordingly in the HBA including the SR IOV function at least one storage device needs to be allocated to a single VM.

For reference the SR IOV function has a standard that enables a single PCIe physical device under a single root port to be represented as several individual physical devices on a hypervisor or a guest OS. A PCIe device that supports the SR IOV function represents its own several instances on a guest OS and a hypervisor. The number of virtual functions displayed may vary according to devices.

In a virtualization system to which the HBA including the SR IOV function is applied in an exemplary embodiment the HBA directly connects the VMs with the first through n th SDs through rather than via a hypervisor.

The first through n th SDs through may be implemented by using solid state drives SSDs or hard disk drives HDDs .

At least one selected from the first through n th SDs through generates a plurality of different pieces of identify device data so that the at least one SD is recognized as a plurality of physical devices. For example at least one selected from the first through n th SDs through generates the plurality of different pieces of identify device data in response to an identify device command received from the host A and transmits the plurality of different pieces of identify device data to the host A.

For example during device recognition at least one selected from the first through n th SDs through transmits to the host A a plurality of pieces of identify device data including different serial numbers and different pieces of world wide name WWN information according to virtual storage devices respectively corresponding to a plurality of storage regions into which a storage region of the at least one storage device is divided.

A WWN or a World Wide Identifier WWID is a unique identifier used in storage technologies including Fiber Channel Advanced Technology Attachment ATA or Serial Attached SCSI SAS . A WWN may be employed in a variety of roles such as a serial number for addressability for example in Fiber Channel networks a WWN may be used as a WWNN World Wide Node Name to identify a switch or a WWPN World Wide Port Name to identify an individual port on a switch. In an exemplary embodiment each WWN is an 8 or 16 byte number the length and format of which is determined by the most significant four bits which are referred to as a Network Address Authority NAA . The remainder of the value is derived from an IEEE OUI often the term Company Identifier is used as a synonym for OUI and vendor supplied information. Each format defines a different way to arrange and or interpret these components.

For example at least one SD selected from the first through n th SDs through divides a storage region of a physical storage device thereof into a plurality of storage regions based on an initially set command and generates and stores unique identify device data about a virtual storage device corresponding to each of the plurality of storage regions. When receiving the identify device command from the host A the at least one SD selected from the first through n th SDs through generates the plurality of pieces of identify device data based on a plurality of pieces of device identification information and transmits the same to the host A.

Accordingly the least one SD selected from the first through n th SDs through is recognized as a plurality of storage devices by the host A even when the at least one storage device is physically a single storage device.

The host B includes a processor a memory an I O sub system a network adaptor and a bus . For example the host B may be assumed to be a server. In another example the host B may be a PC a set top box a modem a mobile device or the like. The network adaptor may be a device configured to connect a computer to a computer network. Examples of the network adaptor include a network interface controller a network interface card and a LAN adaptor. The network adaptor may include circuitry required to communicate using a specific physical layer and data link layer standard such as Ethernet Fiber Channel Wi Fi token ring etc.

Since the processor the memory the I O sub system and the bus included in the host B have already been described above with reference to the computing system A of repeated descriptions thereof will be omitted.

The network adaptor may be combined with the network devices via the link unit . For example the link unit may include copper wiring fiber optic cabling at least one wireless channel or a combination thereof.

The network adaptor may include a circuit interfaces or a code capable of operating to transmit and receive data according to at least one networking standard. For example the network adaptor may communicate with the network devices according to at least one Ethernet standard.

The network adaptor includes an SR IOV function . For example the SR IOV function has been developed to improve the I O performance of a network device in a server virtualization environment and directly connects a VM of a server virtualization system to the network device. Accordingly in the network adaptor including the SR IOV function at least one storage device needs to be allocated to a single VM. In an exemplary embodiment the network adaptor includes a transceiver capable of wirelessly transmitting and receiving data.

In a virtualization system to which the network adaptor including the SR IOV function is applied in an exemplary embodiment the network adaptor directly connects a VM with a storage device rather than via a hypervisor.

The network devices may include a plurality of first through n th SDs through . For example the first through n th SDs through may be implemented by using SSDs or HDDs.

At least one SD selected from the first through n th SDs through generates a plurality of different pieces of identify device data so that the at least one SD is recognized as a plurality of physical devices. For example at least one SD selected from the first through n th SDs through generates the plurality of different pieces of identify device data in response to an identify device command received from the host B and transmits the plurality of different pieces of identify device data to the host B.

For example during device recognition at least one SD selected from the first through n th SDs through transmits to the host B a plurality of pieces of identify device data including different serial numbers and different pieces of WWN information according to virtual storage devices respectively corresponding to a plurality of storage regions into which a storage region of the at least one storage device is divided.

For example at least one SD selected from the first through n th SDs through divides a storage region of a physical storage device thereof into a plurality of storage regions based on an initially set command and generates and stores unique identify device data about a virtual storage device corresponding to each of the plurality of storage regions. When receiving the identify device command from the host B the at least one SD selected from the first through n th SDs through may generate the plurality of pieces of identify device data based on a plurality of pieces of device identification information and transmits the same to the host B.

Accordingly the least one SD selected from the first through n th SDs through is recognized as a plurality of storage devices by the host B even when the at least one storage device is physically a single storage device.

Referring to a hypervisor is placed on a first upper layer from hardware and first through i th guest OSs through I are placed on an upper layer from the hypervisor .

The hypervisor is a logical platform for simultaneously executing many OSs in a single host computer. In other words the hypervisor is a program for operating a server virtualization system including various OSs provided therein.

The bare metal hypervisor is installed directly on the hardware and then executed as an OS controls a program. Then the first through i th guest OSs through are executed on a second upper level from the hardware . According to this way connection to a host OS is not necessary and thus high speed processing may be provided because overhead for a command conversion is small. In addition the virtualization system structure is flexible because resources of the hardware are directly controlled.

Referring to first through i th host OSs are placed on a first upper level from hardware a hypervisor is placed on an upper level from the first through i th host OSs and first through i th guest OSs through are placed on an upper level from the hypervisor .

The hosted hypervisor is executed in the first through i th host OSs similar to general programs. The first through i th guest OSs through operating in VMs are executed on a third upper level from the hardware . Accordingly the first through i th guest OSs through operate over the first through i th host OSs and thus types of the first through i th guest OSs through to be used are not restricted. However overhead increases because the hardware is emulated.

The server virtualization system A includes a hypervisor A an HBA A first through n th SDs through and first through j th VMs through . The HBA may be circuit board or an integrated circuit adaptor that provides input output processing and physical connectivity between a server a storage device and a network. The HBA may also be referred to as a host adaptor or a host controller.

First it is assumed that all of the first through j th VMs through of the server virtualization system A are set to be supported by an SR IOV function A included in the HBA A.

Referring to all of the first through j th VMs through are directly allocated to the first through n th SDs through by the HBA A including the SR IOV function A.

The hypervisor A is a virtualization engine that processes allocation of resources and SDs to VMs in a virtualization environment. For example the hypervisor A may be implemented by using the bare metal hypervisor of or the hosted hypervisor of . The hypervisor A includes a virtual switch A for processing allocation of resources and SDs to VMs. The virtual switch A may be driven by software.

The HBA A including the SR IOV function A directly connects the first through j th VMs through to the first through n th SDs through . In other words the HBA A directly connects the first through j th VMs through to the first through n th SDs through rather than via the virtual switch A of the hypervisor A. The HBA A manages the connections so that at least one SD is allocated to one VM. For example the HBA A manages the connections so that at least one SD corresponding to at least one piece of identify device data is allocated to one VM.

The first through j th VMs through are generated by a server virtualizing different OSs. For example the OSs may include Linux Windows and the like.

As such by directly connecting the first through j th VMs through to SDs with the aid of the SR IOV function A without using the virtual switch A of the hypervisor A scheduling delay before communication is performed may be reduced and overhead due to an operation of the virtual switch A may be reduced.

The server virtualization system B includes a hypervisor B an HBA B first through n th SDs through first through x th VMs through and first through j th VMs through 

First it is assumed that the first through j th VMs through in a first group are set to be supported by an SR IOV function B included in the HBA B and the k th through x th VMs through in a second group are not supported by the SR IOV function B included in the HBA B. In other words SDs which the second group of VMs through are to communicate with are selected via a virtual switch B of the hypervisor B.

Referring to all of the first through j th VMs through in the first group are directly allocated to the first through n th SDs through by the HBA B including the SR IOV function B. The k th through x th VMs through in the second group are allocated to the first through n th SDs through connected to the HBA B by the virtual switch B of the hypervisor B.

The hypervisor B is a virtualization engine that processes allocation of resources and SDs to VMs in a virtualization environment. For example the hypervisor B may be implemented by using the bare metal hypervisor of or the hosted hypervisor of . The hypervisor B includes the virtual switch B for processing allocation of resources and SDs to the k th through x th VMs through in the second group. The virtual switch B may be driven by software. In other words the k th through x th VMs through in the second group may be allocated to the first through n th SDs through connected to the HBA B by the virtual switch B of the hypervisor B.

The HBA B including the SR IOV function B directly connects the first through j th VMs through in the first group to the first through n th SDs through . In other words the HBA B may directly connect the first through j th VMs through in the first group to the first through n th SDs through rather than via the virtual switch B of the hypervisor B. The HBA B manages the connections so that at least one SD is allocated to one VM included in the first through j th VMs through in the first group. For example the HBA B manages the connections so that at least one SD corresponding to at least one piece of identify device data is allocated to one VM.

Each of the first group of first through j th VMs through and the second group of k th through x th VMs through may be generated by virtualizing different OSs. For example the OSs may include Linux Window and the like.

As such by directly connecting the first through j th VMs through in the first group to SDs with the aid of the SR IOV function B without using the virtual switch B of the hypervisor B scheduling delay before communication is performed may be reduced and overhead due to an operation of the virtual switch B may be reduced.

For reference since there is no need to fixedly allocate the first through n th SDs through to the k th through x th VMs through in the second group the number of SDs that are connected to a server may be reduced. For example there is no need to dedicate one or more the SDs through to one of the k th through x th VMs through 

The server virtualization system A includes a hypervisor A a network adaptor A network devices and first through j th VMs through 

First it is assumed that all of the first through j th VMs through of the server virtualization system A are set to be supported by an SR IOV function A included in the network adaptor A.

Referring to all of the first through j th VMs through are directly allocated to the first through n th SDs through by the network adaptor A including the SR IOV function A.

The hypervisor A is a virtualization engine that processes allocation of resources and SDs to VMs in a virtualization environment. For example the hypervisor A may be implemented by using the bare metal hypervisor of or the hosted hypervisor of . The hypervisor A includes a virtual switch A for processing allocation of resources and SDs to VMs. The virtual switch A may be driven by software.

The network adaptor A including the SR IOV function A directly connects the first through j th VMs through to the first through n th SDs through . In other words the network adaptor A directly connects the first through j th VMs through to the first through n th SDs through rather than via the virtual switch A of the hypervisor A. The network adaptor A manages the connections so that at least one SD is allocated to one VM. For example the network adaptor A manages the connections so that at least one SD corresponding to at least one piece of identify device data is allocated to one VM.

The first through j th VMs through are generated by a server virtualizing different OSs. For example the OSs may include Linux Window and the like.

As such by directly connecting the first through j th VMs through to SDs with the aid of the SR IOV function A without using the virtual switch A of the hypervisor A scheduling delay before communication is performed may be reduced and overhead due to an operation of the virtual switch A may be reduced.

The server virtualization system B includes a hypervisor B a network adaptor B first through n th SDs through and first through x th VMs through 

First it is assumed that the first through j th VMs through in a first group are set to be supported by an SR IOV function B included in the network adaptor B and the k th through x th VMs through in a second group are not supported by the SR IOV function B included in the network adaptor B. In other words SDs which the second group of VMs through are to communicate with are selected via a virtual switch B of the hypervisor B.

Referring to all of the first through j th VMs through in the first group are directly allocated to the first through n th SDs through by the network adaptor B including the SR IOV function B. The k th through x th VMs through in the second group are allocated to the first through n th SDs through connected to the network adaptor B by the virtual switch B of the hypervisor B.

The hypervisor B is a virtualization engine that processes allocation of resources and SDs to VMs in a virtualization environment. For example the hypervisor B may be implemented by using the bare metal hypervisor of or the hosted hypervisor of . The hypervisor B includes the virtual switch B for processing allocation of resources and SDs to the k th through x th VMs through in the second group. The virtual switch B may be driven by software. In other words the k th through x th VMs through in the second group may be allocated to the first through n th SDs through connected to the network adaptor B by the virtual switch B of the hypervisor B.

The network adaptor B including the SR IOV function B directly connects the first through j th VMs through in the first group to the first through n th SDs through . In other words the network adaptor B may directly connect the first through j th VMs through in the first group to the first through n th SDs through rather than via the virtual switch B of the hypervisor B. The network adaptor B manages the connections so that at least one SD is allocated to one VM included in the first through j th VMs through in the first group. For example the network adaptor B manages the connections so that an SD corresponding to at least one piece of identify device data is allocated to one VM included in the first through j th VMs through in the first group.

Each of the first group of first through j th VMs through and the second group of k th through x th VMs through may be generated by virtualizing different OSs. For example the OSs may include Linux Window and the like.

As such by directly connecting the first through j th VMs through in the first group to SDs with the aid of the SR IOV function B without using the virtual switch B of the hypervisor B scheduling delay before communication is performed may be reduced and overhead due to an operation of the virtual switch B may be reduced.

For reference since there is no need to fixedly allocate the first through n th SDs through to the k th through x th VMs through in the second group the number of SDs that are connected to a server may be reduced.

Referring to at least one SD selected from the first through n th SDs through transmits to a host a plurality of different pieces of identify device data in response to an identify device command received from the host.

For example each of the first through n th SDs through divides a storage region of itself into four storage regions and transmits to the host four pieces of identify device data including different serial numbers and different pieces of WWN information according to the four storage regions.

For example the first SD divides a storage region thereof into four storage regions and transmits to the host four pieces of identify device data including different serial numbers and different pieces of WWN information according to the four storage regions. Accordingly the first SD is recognized as four SDs sda sdb sdc and sdd by the host. For example a first storage region obtained by dividing the storage region of the first SD may be recognized as the SD sda a second storage region obtained by dividing the storage region of the first SD may be recognized as the SD sdb a third storage region obtained by dividing the storage region of the first SD may be recognized as the SD sdc and a fourth storage region obtained by dividing the storage region of the first SD may be recognized as the SD sdd.

The other SDs namely the second through n th SDs through may each generate a plurality of different pieces of identify device data and transmit the same to the host according to the same method as used for the first SD and thus may each be recognized as a plurality of SDs.

Although identify device data is generated in the embodiment of so that one SD is recognized as four SDs embodiments of the inventive concept are not limited thereto and identify device data may be generated so that one SD is recognized as at least two SDs less than four SDs or more than four SDs.

The HBA A or B allocates at least one SD to the first through j th VMs through by using the SR IOV function A or B. For example the HBA A or B may allocate at least one SD to the first through j th VMs through by using identify device data received from the first through n th SDs through during data recognition. For example SD allocation information may be stored in the HBA A or B. The SD allocation information may indicate how SDs or portions thereof are allocated mapped to each virtual machine.

Referring to for example the SD sda corresponding to the first storage region of the first SD may be allocated to the first VM and the SD sdb corresponding to the second storage region of the first SD may be allocated to the second VM . The SD sdc corresponding to the third storage region of the first SD and the SD sdd corresponding to the fourth storage region thereof may be respectively allocated to different VMs.

Thus in the server virtualization system A or B including the HBA A or B including the SR IOV function A or B although the number of VMs greatly increases the number of necessary physical SDs may be reduced.

Referring to at least one SD selected from the first through n th SDs through transmits to a host a plurality of different pieces of identify device data in response to an identify device command received from the host.

For example each of the first through n th SDs through divides a storage region of itself into four storage regions and transmits to the host four pieces of identify device data including different serial numbers and different pieces of WWN information according to the four storage regions.

Since a method in which each of the first through n th SDs through generate a plurality of pieces of identify device data is the same as that in which each of the first through n th SDs through of generate a plurality of pieces of identify device data a repeated description thereof will be omitted.

Although identify device data is generated in the embodiment of so that one SD is recognized as four SDs embodiments of the inventive concept are not limited thereto and identify device data may be generated so that one SD is recognized as at least two SDs less than four SDs or more than four SDs.

The network adaptor A or B allocates at least one SD to the first through j th VMs through by using the SR IOV function A or B. For example the network adaptor A or B may allocate at least one SD to the first through j th VMs through by using identify device data received from the first through n th SDs through during data recognition. For example SD allocation information may be stored in the network adaptor A or B.

Referring to for example an SD sda corresponding to a first storage region of the first SD may be allocated to the first VM and an SD sdb corresponding to a second storage region of the first SD may be allocated to the second VM . An SD sdc corresponding to a third storage region of the first SD and an SD sdd corresponding to a fourth storage region thereof may be respectively allocated to different VMs.

Thus in the server virtualization system A or B including the network adaptor A or B including the SR IOV function A or B although the number of VMs greatly increases the number of necessary physical SDs may be reduced.

For example the SD of may be implemented by using the first through n th SDs through of the computing system A of or the first through n th SDs through of the computing system B of .

Referring to the SD may include a memory controller and a memory device . For example the SD may be implemented by using an SSD.

The memory controller may control the memory device according to a command received from a host. In detail the memory controller may provide an address a command and a control signal to the memory device via a plurality of channels CH through CHM to control a program or write operation a read operation and an erase operation with respect to the memory device .

The memory controller may set one physical SD to be a plurality of virtual SDs. In detail the memory controller may generate a plurality of pieces of identify device ID data ID DATA see for one physical SD.

The memory controller divides a storage region of the memory device into a plurality of storage regions that are initially set and generates unique identify device data ID DATA for a virtual SD corresponding to each of the plurality of initially set storage regions. The memory controller also generates an address signal a command signal and a control signal that are necessary for writing a plurality of pieces of identify device data respectively generated for the plurality of storage regions to the memory device . The memory controller also generates an address signal a command signal and a control signal that are necessary for writing information about a storage capacity and a physical address region for each virtual SD to the memory device .

For example the memory controller may generate a plurality of pieces of identify device data so that one physical SD is recognized as a plurality of SDs based on a device virtualization command that is initially set. The memory controller may control the generated plurality of pieces of identify device data to be written to the memory device .

For example the device virtualization command may be provided to the memory controller via a manufacturer management tool during an SD manufacturing process. In another example the device virtualization command may be provided to the memory controller via the host in a user condition where an SD has been connected to the host.

In detail the processor of the computing system A of may provide the device virtualization command to the memory controller via the HBA . The processor of the computing system B of may provide the device virtualization command to the memory controller via the network adaptor .

In another example after a plurality of pieces of identify device data for a plurality of virtual SDs corresponding to one physical SD are generated in a manufacturer management tool the generated plurality of pieces of identify device data may be provided directly to the memory controller . The memory controller may control the received plurality of pieces of identify device data to be written to the memory device .

For example identify device data for each virtual SD may include at least one of information about a model name a firmware revision a serial number a WWN a physical logical sector size a feature and the like based on the Serial Advanced Technology Attachment SATA standard.

At least the information about the serial number and the WWN from among the pieces of information included in the identify device data for each virtual SD may be set differently according to different pieces of identify device data.

For example it is assumed that a plurality of pieces of identify device data for a plurality of virtual SDs corresponding to one physical SD are ID DATA ID DATA ID DATA and ID DATA . For example each of the pieces of identify device data ID DATA ID DATA ID DATA and ID DATA may include information about a model name a firmware revision a serial number a WWN a physical logical sector size a feature and the like. In this case pieces of information about the serial numbers respectively included in the pieces of identify device data ID DATA ID DATA ID DATA and ID DATA may be set differently and pieces of information about the WWNs respectively included in the pieces of identify device data ID DATA ID DATA ID DATA and ID DATA may also be set differently.

For example when one physical SD is divided into N where N is an integer equal to or greater than 2 virtual SDs the storage capacity of each virtual SD is set to be a capacity obtained by dividing a maximum logical block address LBA of the physical SD by N. Accordingly a storage capacity and a physical address region for each virtual SD are set.

As such when the memory controller receives an identify device command from the host after setting the plurality of pieces of identify device data the memory controller transmits the plurality of pieces of identify device data to the host. In detail the memory controller reads the plurality of pieces of identify device data from the memory device and transmits the read plurality of pieces of identify device data to the host.

For example when the number of virtual SDs corresponding to one physical SD is set to be 4 the memory controller transmits four pieces of identify device data to the host. For example the memory controller may transmit four pieces of identify device data ID DATA ID DATA ID DATA and ID DATA to the host.

The memory device may include at least one non volatile memory chip . For example the non volatile memory chip included in the memory device may be not only a flash memory chip but may also be a phase change RAM PRAM chip a ferroelectric RAM FRAM chip a magnetic RAM MRAM chip or the like. In another example the memory device may include at least one non volatile memory chip and at least one volatile memory chip or may include at least two types of non volatile memory chips.

For example the host and the SD may communicate with each other based on SATA frame information structure FIS layouts of .

In each of the SATA FIS layouts of a PM Port is a field indicating a device port address and is set by the host.

For example when serial numbers respectively included in pieces of identify device data are different and WWNs respectively included therein are also different the PM Port varies. Accordingly each of a plurality of virtual SDs that constitute the single physical SD may have a unique PM Port when communicating with the host.

The memory controller of the SD may calculate a physical address of the memory device by using PM Port information and LBA information. In detail the memory controller may select a virtual SD based on the PM Port information and transform an LBA into a physical address based on a storage capacity and a physical address region for the selected virtual SD.

As shown in the memory controller includes a processor a random access memory RAM a host interface a memory interface and a bus .

The processor may control an overall operation of the SD by using program codes and pieces of data that are stored in the RAM . When the SD is initialized the processor may read from the memory device a program code and data which are necessary for controlling operations performed by the SD and may load the read program code and data into the RAM .

For example the processor may read from the memory device a device virtualization program or identify device data and load the read device virtualization program or identify device data into the RAM .

For example the processor loads one piece of identify device data into the RAM before executing the device virtualization program . After executing the device virtualization program the processor loads a plurality of pieces of identify device data into the RAM .

When the processor receives the device virtualization command via the host interface the processor sets one physical SD to be a plurality of virtual SDs. For example the processor may set a plurality of pieces of identify device data for one physical SD.

For example when receiving the identify device command the processor may read the plurality of pieces of identify device data from the RAM and transmit the same to the host via the host interface .

The RAM stores data that is received via the host interface or data that is received from the memory device via the memory interface . The RAM may also store data that has been processed by the processor . For example the RAM may store the plurality of pieces of identify device data set in response to the device virtualization command.

The host interface includes a protocol for exchanging data with a host that is connected to the memory controller and interfaces the memory controller with the host. The host interface may be implemented by using but is not limited to an Advanced Technology Attachment ATA interface a Serial Advanced Technology Attachment SATA interface a Parallel Advanced Technology Attachment PATA interface a Universal Serial Bus USB or Serial Attached Small Computer System SAS interface a Small Computer System Interface SCSI an embedded Multi Media Card eMMC interface or a Universal Flash Storage UFS interface. The host interface may receive a command an address and data from the host under the control of the processor or may transmit data to the host.

The memory interface is electrically connected to the memory device . The memory interface may transmit a command an address and data to the memory device under the control of the processor or may receive data from the memory device . The memory interface may be configured to support NAND flash memory or NOR flash memory. The memory interface may be configured to perform software or hardware interleaving operations via a plurality of channels.

Referring to the non volatile memory chip may include a memory cell array a control logic a voltage generator a row decoder and a page buffer . The components included in the non volatile memory chip will now be described in detail.

The memory cell array may be connected to at least one string selection line SSL a plurality of word lines WL and at least one ground selection line GSL and may also be connected to a plurality of bit lines BL. The memory cell array may include a plurality of memory cells MC see that are disposed at intersections of the plurality of bit lines BL and the plurality of word lines WL.

When an erasure voltage is applied to the memory cell array the plurality of memory cells MC enter an erasure state. When a programming voltage is applied to the memory cell array the plurality of memory cells MC enter a program state. At this time each memory cell MC may have one selected from an erasure state and first through n th program states P through Pn that are distinguished from each other according to a threshold voltage.

In the first through n th program states P through Pn n may be a natural number equal to or greater than 2. For example when each memory cell MC is a 2 bit level cell n may be 3. In another example when each memory cell MC is a 3 bit level cell n may be 7. In another example when each memory cell MC is a 4 bit level cell n may be 15. As such the plurality of memory cells MC may include multi level cells. However embodiments of the inventive concept are not limited thereto and the plurality of memory cells MC may include single level cells.

The control logic may receive a command signal CMD an address signal ADDR and a control signal CTRL from the memory controller to output various control signals for writing the data DATA to the memory cell array or for reading the data from the memory cell array . In this way the control logic may control overall operations of the non volatile memory chip .

The various control signals output by the control logic may be provided to the voltage generator the row decoder and the page buffer . In detail the control logic may provide a voltage control signal CTRL vol to the voltage generator may provide a row address signal X ADDR to the row decoder and may provide a column address signal Y ADDR to the page buffer .

The voltage generator may receive the voltage control signal CTRL vol to generate various voltages for executing a program operation a read operation and an erasure operation with respect to the memory cell array . In detail the voltage generator may generate a first drive voltage VWL for driving the plurality of word lines WL a second drive voltage VSSL for driving the at least one string selection line SSL and a third drive voltage VGSL for driving the at least one ground selection line GSL.

The first drive voltage signal VWL may be a program or write voltage signal a read voltage signal an erasure voltage signal a pass voltage or a program verification voltage signal. The second drive voltage signal VSSL may be a string selection voltage signal namely an on voltage signal or an off voltage signal. The third drive voltage signal VGSL may be a ground selection voltage signal namely an on voltage signal or an off voltage signal.

According to an exemplary embodiment the voltage generator receives the voltage control signal CTRL vol to generate a program start voltage signal as a program voltage signal when a program loop starts namely when the number of program loops performed is 1. As the number of program loops performed increases the voltage generator may generate a voltage signal that increases from the program start voltage signal by a step voltage in stages as the program voltage signal.

The row decoder may be connected to the memory cell array through the plurality of word lines WL and may activate some of the plurality of word lines WL in response to the row address signal X ADDR received from the control logic . In detail during a read operation the row decoder may apply a read voltage signal to a word line selected from the plurality of word lines WL and apply a pass voltage signal to the remaining unselected word lines.

During a program operation the row decoder may apply a program voltage signal to the selected word line and apply the pass voltage signal to the unselected word lines. According to the exemplary embodiment the row decoder applies a program voltage signal to the selected word line and an additionally selected word line in at least one selected from a plurality of program loops.

The page buffer may be connected to the memory cell array via the plurality of bit lines BL. In detail during a read operation the page buffer may operate as a sense amplifier so as to output data DATA stored in the memory cell array . During a program operation the page buffer may operate as a write driver so as to input the data DATA desired to be stored in the memory cell array .

Referring to the memory cell array may be a flash memory cell array. In this case the memory cell array may include a plurality of memory blocks BLK . . . and BLKa where a denotes a positive integer which is equal to or greater than two and each of the memory blocks BLK . . . and BLKa may include a plurality of pages PAGE . . . and PAGEb where b denotes a positive integer which is equal to or greater than two . In addition each of the pages PAGE . . . and PAGEb may include a plurality of sectors SEC . . . and SECc where c denotes a positive integer which is equal to or greater than two . Although the pages PAGE through PAGEb and the sectors SEC through SECc of only the memory block BLK are illustrated for convenience of explanation in the other memory blocks BLK through BLKa may have the same structures as that of the memory block BLK.

Referring to the first memory block BLKmay be a NAND flash memory having a vertical structure. Each of the memory blocks BLK through BLKa of may have substantially the same configuration as illustrated in . In a first direction is referred to as an x direction a second direction is referred to as a y direction and a third direction is referred to as a z direction. However embodiments of the inventive concept are not limited thereto and the first through third directions may vary.

The first memory block BLKmay include a plurality of cell strings CST a plurality of word lines WL a plurality of bit lines BL a plurality of ground selection lines GSL and GSL a plurality of string selection lines SSL and SSL and a common source line CSL. The number of cell strings CST the number of word lines WL the number of bit lines BL the number of ground selection lines GSL and GSL and the number of string selection lines SSL and SSL may vary according to embodiments.

Each of the cell strings CST may include a string selection transistor SST a plurality of memory cells MC and a ground selection transistor GST that are serially connected to each other between a bit line BL corresponding to the cell string CST and the common source line CSL. However embodiments of the inventive concept are not limited thereto. According to another embodiment each cell string CST further includes at least one dummy cell. According to another embodiment each cell string CST includes at least two string selection transistors SST or at least two ground selection transistors GST.

Each cell string CST may extend in the third direction z direction . In detail each cell string CST may extend on a substrate see in a vertical direction z direction . Accordingly the first memory block BLKincluding the cell strings CST may be referred to as a vertical direction NAND flash memory. As such by extending each cell string CST in the vertical direction z direction on a substrate the integration density of the memory cell array may increase.

The plurality of word lines WL may each extend in the first direction x and the second direction y and each word line WL may be connected to memory cells MC corresponding to itself. Accordingly a plurality of memory cells MC arranged adjacent to each other on the same plane in the first direction x and the second direction y may be connected to each other by an identical word line WL. In detail each word line WL may be connected to gates of memory cells MC to control the memory cells MC. In this case the plurality of memory cells MC may store data and may be programmed read or erased under the control of the connected word line WL.

The plurality of bit lines BL may extend in the first direction x and may be connected to the string selection transistors SST. Accordingly a plurality of string selection transistors SST arranged adjacent to each other in the first direction x may be connected to each other by an identical bit line BL. In detail each bit line BL may be connected to drains of the plurality of string selection transistors SST.

The plurality of string selection lines SSL and SSL may each extend in the second direction y and may be connected to the string selection transistors SST. Accordingly a plurality of string selection transistors SST arranged adjacent to each other in the second direction y may be connected to each other by an identical string selection line SSL or SSL. In detail each string selection line SSL or SSL may be connected to gates of the plurality of string selection transistors SST to control the plurality of string selection transistors SST.

The plurality of ground selection lines GSL and GSL may each extend in the second direction y and may be connected to the ground selection transistors GST. Accordingly a plurality of ground selection transistors GST arranged adjacent to each other in the second direction y may be connected to each other by an identical ground selection line GSL or GSL. In detail each ground selection line GSL or GSL may be connected to gates of the plurality of ground selection transistors GST to control the plurality of ground selection transistors GST.

The ground selection transistors GST respectively included in the cell strings CST may be connected to each other by the common source line CSL. In detail the common source line CSL may be connected to sources of the ground selection transistors GST.

A plurality of memory cells MC connected to an identical word line WL and to an identical string selection line SSL or SSL and arranged adjacent to each other in the second direction y may be referred to as a page PAGE. For example a plurality of memory cells MC connected to a first word line WL and to a first string selection line SSL and arranged adjacent to each other in the second direction y may be referred to as a first page PAGE. A plurality of memory cells MC connected to the first word line WL and to a second string selection line SSL and arranged adjacent to each other in the second direction y may be referred to as a second page PAGE.

To perform a program operation with respect to a memory cell MC 0V may be applied to a bit line BL an on voltage may be applied to a string selection line SSL and an off voltage may be applied to a ground selection line GSL. The on voltage may be equal or greater than the threshold voltage so that a string selection transistor SST is turned on and the off voltage may be smaller than the threshold voltage so that the ground selection transistor GST is turned off. A program voltage may be applied to a memory cell selected from the memory cells MC and a pass voltage may be applied to the remaining unselected memory cells. In response to the program voltage electric charges may be injected into the memory cells MC due to F N tunneling. The pass voltage may be greater than the threshold voltage of the memory cells MC.

To perform an erasure operation with respect to the memory cells MC an erasure voltage may be applied to the body of the memory cells MC and 0V may be applied to the word lines WL. Accordingly data stored in the memory cells MC may be temporarily erased.

Referring to the first memory block BLK may have a substrate having a main surface extending in the first direction x. The substrate may include a semiconductor material for example a Group IV semiconductor a Group III V compound semiconductor or a Group II VI oxide semiconductor. For example the Group IV semiconductor may include silicon germanium or silicon germanium. The substrate may be a bulky wafer or an epitaxial layer.

Semiconductor pillars and may each vertically extend on the substrate . The semiconductor pillars and may include a semiconductor material such as polysilicon or single crystal silicon and the semiconductor material may not be doped or may include p type or n type impurities.

The substrate may include an impurity region formed below the semiconductor pillars and . The impurity region may be a source region and may form a PN junction together with other regions of the substrate . The common source line CSL of may be connected to the impurity region . According to another embodiment the impurity region may be defined by lower ends of the semiconductor pillars and

Each of the memory cells MC may include a storage medium formed on a sidewall of the semiconductor pillar or and a control gate electrode formed on the storage medium . Each storage medium may include a tunneling isolation layer on a sidewall of the semiconductor pillar or a charge storing layer on the tunneling isolation layer and a blocking insulation layer on the charge storing layer .

The charge storage layer may have a charge storing capability. For example the charge storage layer may be of a track type for example may include a silicon nitride layer quantum dots or nanocrystals. Quantum dots or nanocrystals may include fine particles of a conductive substance for example a metal or a semiconductor. The tunneling insulation layer and the blocking insulation layer may include an oxide layer a nitride layer or a high dielectric layer. A high dielectric layer may be referred to as a dielectric layer having a higher dielectric constant than an oxide layer and a nitride layer.

Each string selection transistor SST may include a string selection gate electrode formed on a sidewall of the semiconductor pillar or . The string selection transistors SST may be connected to a bit line . The bit line may be a linear pattern extending in the first direction x. Each ground selection transistor GST may include a ground selection gate electrode formed on a sidewall of the semiconductor pillar or

The storage medium between the string selection transistors SST and the semiconductor pillar or and between the ground selection transistors GST and the semiconductor pillar or may function as a gate insulation layer and thus may be replaced by a single insulation layer. Interlayer insulation layers may be interposed between the ground selection gate electrodes the control gate electrodes and the string selection gate electrodes . The storage medium may extend along respective surfaces of the interlayer insulation layers .

First and second cell strings CST and CST may be arranged adjacent to each other with the semiconductor pillar interposed therebetween and third and fourth cell strings CST and CST may be arranged adjacent to each other with the semiconductor pillar interposed therebetween. An insulation layer may be interposed between the second and third cell strings CST and CST.

The string selection gate electrodes may be connected to string selection lines SSL via contact plugs . The control gate electrodes may be connected to the word lines WL through WLn via contact plugs . The ground selection gate electrodes may be connected to ground selection lines GSL via contact plugs .

Referring to the first memory block BLK may have a substrate having a main surface extending in the first direction x. The substrate may include a semiconductor material for example a Group IV semiconductor a Group III V compound semiconductor or a Group II VI oxide semiconductor. For example the Group IV semiconductor may include silicon germanium or silicon germanium. The substrate may be a bulky wafer or an epitaxial layer.

A semiconductor pillar may vertically extend on the substrate . The semiconductor pillar may include a semiconductor material such as polysilicon or single crystal silicon and the semiconductor material may not be doped or may include p type or n type impurities.

A storage medium may extend in the lengthwise direction of the semiconductor pillar . The storage medium may include a tunneling isolation layer on a sidewall of the semiconductor pillar a charge storing layer on the tunneling isolation layer and a blocking insulation layer on the charge storing layer .

A string selection transistor SST may include a string selection gate electrode formed on a sidewall of the semiconductor pillar . The string selection transistor SST may be connected to a bit line . The bit line may be a linear pattern extending in the first direction x. A ground selection transistor GST may include a ground selection gate electrode formed on a sidewall of the semiconductor pillar .

The storage medium between the string selection transistor SST and the semiconductor pillar and between the ground selection transistor GST and the semiconductor pillar may function as a gate insulation layer and thus may be replaced by a single insulation layer. Interlayer insulation layers may be interposed between the ground selection gate electrodes the control gate electrodes and the string selection gate electrodes .

Referring to the cell string CST may include at least a pair of string selection transistors SST and SST a plurality of memory cells MC and at least a pair of ground selection transistors GST and GST. A bit line BL may be connected to one end of the cell string CST and the common source line CSL may be connected to the other end of the cell string CST .

Some of the components included in the cell string CST according to an exemplary embodiment are substantially the same as the counterparts included in the cell string CST of . Like components are indicated by like reference characters and the components of the cell string CST which are the same as those of the cell string CST of will not be repeatedly described herein. Differences between the cell string CST of and the cell string CST according to the present embodiment will now be focused on and described.

The plurality of memory cells MC may be vertically arranged in series. The plurality of memory cells MC may store data. The plurality of word lines WL may be connected to the memory cells MC to control the memory cells MC. The number of memory cells MC may be appropriately selected according to the capacity of a non volatile memory device.

The at least two string selection transistors SS and SST may be arranged adjacent to each other on one side of the memory cells MC. For example the string selection transistors SST and SST may be interposed between the bit line BL and an n th memory cell MCn and may be serially connected to the n th memory cell MCn. The string selection transistors SST and SST may control signal exchange between the bit line BL and the memory cells MC. A string selection line SSL may be combined with both the string selection transistors SST and SST. Accordingly the string selection transistors SST and SST may interoperate with each other like a single transistor.

The at least two ground selection transistors GST and GST may be arranged adjacent to each other on the other side of the memory cells MC which is opposite to the side where the string selection transistors SST and SST are arranged. For example the ground selection transistors GST and GST may be interposed between the bit line BL and a first memory cell MC and may be serially connected to the first memory cell MC. The ground selection transistors GST and GST may control signal exchange between the common source line CSL and the memory cells MC. A ground selection line GSL may be combined with both the ground selection transistors GST and GST. Accordingly the ground selection transistors GST and GST may interoperate with each other like a single transistor.

According to an exemplary embodiment due to the inclusion of the at least two string selection transistors SST and SST the length of each of the string selection gate electrodes of may be greatly reduced compared to when one string selection transistor is included. Thus each of the string selection gate electrodes may fill the gaps between the interlayer insulation layers of without void. Moreover due to the inclusion of the at least two ground selection transistors GST and GST the length of each of the ground selection gate electrodes of may be greatly reduced compared to when one ground selection transistor is included. Thus each of the ground selection gate electrodes may fill the gaps between the interlayer insulation layers of without void.

Referring to the cell string CST may include at least a pair of string selection transistors SST and SST a plurality of memory cells MC and at least a pair of ground selection transistors GST and GST. A bit line BL may be connected to one end of the cell string CST and the common source line CSL may be connected to the other end of the cell string CST .

Some of the components included in the cell string CST according to an exemplary embodiment are substantially the same as the counterparts included in the cell string CST of . Like components are indicated by like reference characters and the components of the cell string CST which are the same as those of the cell string CST of will not be repeatedly described herein. Differences between the cell string CST of and the cell string CST according to an exemplary embodiment will now be focused on and described.

The at least two string selection transistors SS and SST may be arranged adjacent to each other on one side of the memory cells MC. For example the string selection transistors SST and SST may be interposed between the bit line BL and an n th memory cell MCn and may be serially connected to the n th memory cell MCn. The string selection transistors SST and SST may control signal exchange between the bit line BL and the memory cells MC. A first string selection line SSLa may be connected to the first string selection transistor SST and a second string selection line SSLb may be connected to the second string selection transistor SST.

The at least two ground selection transistors GST and GST may be arranged adjacent to each other on the other side of the memory cells MC which is opposite to the side where the string selection transistors SST and SST are arranged. For example the ground selection transistors GST and GST may be interposed between the bit line BL and a first memory cell MC and may be serially connected to the first memory cell MC. The ground selection transistors GST and GST may control signal exchange between the common source line CSL and the memory cells MC. A first ground selection line GSLa may be connected to the first ground selection transistor GST and a second ground selection line GSLb may be connected to the second ground selection transistor GST.

For example the host may be the host A or B of and the device may be the first through n th SDs through of or the first through n th SDs through of .

First an initialization process based on an OOB sequence according to the SATA standard will now be described.

In operation S the host transmits a COMRESET signal which is an analog signal to the device . In operation S after confirming reception of the COMRESET signal the device transmits a COMINIT signal which is an analog signal to the host . In operation S after confirming reception of the COMINIT signal the host transmits a COMWAKE signal which is an analog signal to the device . In operation S after confirming reception of the COMWAKE signal the device transmits a COMWAKE signal which is an analog signal to the host . Then in operations S and S the host and the device adjust a communication speed while exchanging an align primity signal ALIGN. In this way the initialization process is completed.

Next the device recognizing process which is performed after the initialization process is completed will now be described.

In operation S in response to the identify device command ID CMD the device transmits identify device data ID DATA set by the device to the host . When the device has been virtualized the device transmits a plurality of pieces of identify device data to the host . For example when the device is set to be four virtual devices via device virtualization the device transmits four pieces of identify device data ID DATA ID DATA ID DATA and ID DATA to the host . For example each of the four pieces of identify device data ID DATA ID DATA ID DATA and ID DATA may include information about a model name a firmware revision a serial number a WWN a physical logical sector size a feature and the like. Pieces of information about the serial numbers respectively included in the four pieces of identify device data ID DATA ID DATA ID DATA and ID DATA are set differently and pieces of information about the WWNs respectively included in the four pieces of identify device data ID DATA ID DATA ID DATA and ID DATA may also be set differently.

An SD recognizing method performed in a server virtualization system and a device virtualizing method according to an exemplary embodiment of the inventive concept will now be described.

Methods illustrated in may be performed by the memory controller of the SD . In detail the methods of may be performed under the control of the processor of the memory controller of .

In operation S the memory controller of the SD determines whether a device virtualization command is received. For example the device virtualization command may be received from the host A of or the host B of . In another example the device virtualization command may be received via a manufacturer management tool during an SD manufacturing process.

In operation S in response to the device virtualization command the memory controller of the SD generates a plurality of pieces of identify device data so that one physical SD is recognized as a plurality of SDs. In detail the memory controller divides a storage region of the SD into a plurality of storage regions and generates different pieces of identify device data for the plurality of storage regions.

For example the memory controller may divide the storage region into storage regions the number of which is indicated by the device virtualization command and may generate different pieces of identify device data for the storage regions. In another example the memory controller may divide the storage region into storage regions the number of which is set by default and may generate different pieces of identify device data for the storage regions.

For example the pieces of identify device data generated by the memory controller may include information about a model name a firmware revision a serial number a WWN a physical logical sector size a feature and the like. The memory controller differently sets at least serial number information and WWN information for a plurality of pieces of identify device data derived from one physical SD.

Next in operation S the memory controller stores information about the storage regions and the plurality of pieces of identify device data in the memory device . In detail the memory controller transmits to the memory device a command signal an address signal data and a control signal that are necessary for writing the information about the storage regions and the plurality of pieces of identify device data to the memory device . Accordingly the information about the storage regions and the plurality of pieces of identify device data are written to the memory device .

In operation S the memory controller of the SD determines whether the identify device command ID CMD is received. For example the identify device command ID CMD may be received from the host A of or the host B of .

In operation S when the identify device command ID CMD is received the memory controller of the SD transmits to the host a plurality of pieces of identify device data read from the memory device . The plurality of pieces of identify device data are the pieces of identify device data for the virtual SDs that are derived from one physical SD via the device virtualization of .

An initialization and device recognition method in a server virtualization system according to an exemplary embodiment of the inventive concept will now be described.

For example the initialization and device recognition method of may be performed in the host A or B of the computing system A or B of .

First in operation the host A or B performs an initialization operation for transmission and reception with an SD connected to the host A or B. For example when the SD is connected to the host A or B the host A or B may perform the initialization operation for transmission and reception by using an OOB sequence based on the SATA standard. In detail the initialization operation for transmission and reception may be performed based on operations S through S of .

In operation the host A or B determines whether the initialization operation for transmission and reception has been successfully completed. For example the host A or B determines whether operations S through S of have been successfully completed.

When it is determined that the initialization operation for transmission and reception has been successfully completed the host A or B transmits the identify device command ID CMD to the SD in operation .

In operation S the host A or B receives a plurality of pieces of identify device data from SDs for which the plurality of pieces of identify device data are set via device virtualization based on the identify device command ID CMD.

In operation S the host A or B allocates virtual SDs to VMs based on the received plurality of pieces of identify device data. Accordingly as illustrated in one physical SD for example the first SD or may be allocated to a plurality of VMs of the host A or B. For example a plurality of virtual SDs sda sdb sdc and sdd that constitute one physical SD for example the first SD or may be respectively allocated to different VMs.

Referring to the electronic device includes a processor a random access memory RAM the SD an input output I O device and a bus .

Although not shown in the electronic device may further include ports which are capable of communicating with a video card a sound card a memory card a USB device or other electronic apparatuses. The electronic device may be implemented by using a personal computer a notebook computer a mobile apparatus a personal digital assistant PDA a digital camera or the like.

The bus refers to a transmission channel via which data a command signal an address signal and control signals are transmitted between the other components of the electronic device .

The processor may execute specific calculations or specific tasks. For example the processor may be a micro processor or a central processing unit CPU . The processor may communicate with the RAM the SD and the I O device through the bus such as an address bus a control bus or a data bus. In some embodiments the processor may be connected to an expansion bus such as a peripheral component interconnect PCI bus.

Pieces of data that are necessary for performing a process and generated by the processor are loaded into the RAM . The RAM may operate as a main memory and may be implemented by using a Dynamic Random Access Memory DRAM or Static Random Access Memory SRAM .

The SD includes a memory controller and a memory device . The SD may be the SD of . In other words the memory controller and the memory device may be the memory controller and the memory device of respectively.

The I O device may include an input device such as a keyboard a keypad or a mouse and an output device such as a printer or a display.

The processor may perform a calculation or data processing which correspond to a user command input via the I O device . To perform a calculation or data processing corresponding to the user command the processor may transmit to the SD a request to read data from the SD or write data to the SD .

The SD may perform a read operation or a write operation according to the request received from the processor .

Meanwhile a storage device according to the inventive concept may be mounted by using various types of packages e.g. a package on package POP a ball grid array BGA a chip scale package CSP a plastic leaded chip carrier PLCC a plastic dual in line package PDIP a die in waffle pack a die in wafer form a chip on board COB a ceramic dual in line package CERDIP a plastic metric quad flat pack MQFP a thin quad flat pack TQFP a small outline integrated circuit SOIC a shrink small outline package SSOP a thin small outline package TSOP a system in package SIP a multi chip package MCP a wafer level fabricated package WFP and a wafer level processed stack package WSP .

While the inventive concept has been particularly shown and described with reference to exemplary embodiments thereof it will be understood that various changes in form and details may be made therein without departing from the spirit and scope of the inventive concept.


---

title: Enhanced interface to firmware operating in a solid state drive
abstract: An embodiment of the invention includes a storage subsystem having a storage central processing unit (SCPU) operable to receive and send a command to a host, the command requiring data computation, a compute engine coupled to the SCPU, and a bank of memory devices coupled to the SCPU and the compute engine and configured to store data required by the commands, wherein the SCPU or the compute engine are operable to perform computation of the data and to further invoke an appropriate Flash Translation Layer (FTL) application based on workload.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09335935&OS=09335935&RS=09335935
owner: SMART High Reliability Solutions, LLC
number: 09335935
owner_city: Newark
owner_country: US
publication_date: 20150921
---
This application is a continuation of U.S. Pat. No. 9 141 292 filed on Jan. 7 2015 entitled Enhanced Interface to Firmware Operation In A Solid State Drive by Aswadhati et al. which claims priority to U.S. Provisional Application No. 61 925 188 filed on Jan. 8 2014 by Ajoy Aswadhati and entitled Enhanced Interface to Firmware Are Operating In A Solid State Drive and is a continuation in part of U.S. patent application Ser. No. 14 147 462 filed on Jan. 3 2014 by Ajoy Aswadhati et al. and entitled Compute Offload disclosure of both of which are incorporated herein by reference.

Various embodiment of the invention relate generally to storage subsystems such as solid state disks SSDs and particularly to performance of the SSDs.

SSDs have shown promise in cloud storage and other types of large storage applications in the recent decade with increased anticipation of more to come. For example an entire standard currently employed by SSDs i.e. PCI Express PCIe has been developed.

Currently SSDs are nearly dumb storage devices with no capability of complex data manipulation which is essentially done by external processors or microcontrollers. The act of retrieving and or storing data in the SSDs causes a wait time before computation can be started. As can be appreciated system performance is an essential advantage in large scale storage applications servicing many users.

For example current server architectures perform computation of data that is stored in a storage medium. Performing this computation entails moving data to and from main memory of the processor such as a central processing unit CPU and the storage subsystem. Moving the data hinders system performance.

Therefore the need arises to increase the performance of systems employing storage subsystems such as SSDs.

Briefly an embodiment of the invention includes a storage subsystem having a storage central processing unit SCPU operable to receive and send a command to a host the command requiring data computation a compute engine coupled to the SCPU and a bank of memory devices coupled to the SCPU and the compute engine and configured to store data required by the commands wherein the SCPU or the compute engine are operable to perform computation of the data and to further invoke an appropriate Flash Translation Layer FTL application based on workload.

A further understanding of the nature and the advantages of particular embodiments disclosed herein may be realized by reference of the remaining portions of the specification and the attached drawings.

Referring now to a storage subsystem is shown in accordance with an embodiment of the invention. The storage subsystem is shown to include memory storage central processing unit SCPU host interface a bank of memory controllers N a bank of memory devices an interface compute engine a host interface bus and a bank of memory devices . The storage subsystem is shown coupled to a host which is shown to include an application . The host is shown coupled to the host interface of the storage subsystem through the host interface bus .

In some embodiments each of the memory devices and is made of volatile memory or a combination of volatile and non volatile memory.

The SCPU is shown coupled to the memory and the host interface . The SCPU is further shown to be in communication with the memory controllers N and the compute engine through the interface . Similarly the compute engine and the memory controllers N are in communication with each other through the interface . The host interface is in communication with a host through the host interface bus . The memory controller is shown coupled to the bank of memory devices and the memory controller N is shown coupled to the bank of memories . While not shown there is typically more than two memory controllers and associated bank of memories than that which is shown in . In some embodiments the bank of memory devices and are non volatile memory. The storage subsystem comprises a SSD with the compute engine embedded in the SSD. The storage subsystem need not be a SSD and in some embodiments it is other types of systems or sub systems such as without limitation servers. The storage subsystem is not intended to be limited to a subsystem. For example viewing the subsystem as a subsystem it is an independent entity that is used by a system. In the case where the storage subsystem is viewed as a system the subsystem is not used by another system and is rather plugged into the device it is designed for such as a computer.

In exemplary embodiments of the invention the interface is a processor local bus such as without limitation a PCI Express PCIe bus or a processor interconnect bus such as a hypertransport or QuickPath Interconnect QPI . In exemplary embodiments of the invention the host interface bus is PCIe Ethernet fiber channel infiniband or Serial ATA SATA .

The storage subsystem performs computing by being closest to the data since the data is saved in the bank of memory devices and . Only the interface separates the compute engine from the data. Accordingly the storage subsystem exploits the close locality of data.

In operation the host interface receives or sends commands from and to a host through the host interface bus . Alternatively events are received or sent by the host interface to a host through the host interface bus . The host interface transmits received host commands to the SCPU for processing. The SCPU uses the memory for temporary storage. For example data associated with a host command may be stored in the memory . Upon processing the host command the SCPU instructs the compute engine and the memory controllers N accordingly. For instance an application such as the application shown in that is being executed by the host may require computations such as fast fourier transform FFT or search of the data the data being either stored in the storage subsystem or being transmitted thereto. The compute engine under the direction of the SCPU performs such computation. The memory controller under the direction the SCPU stores or retrieves data to and from the bank of memory devices to which it is coupled. Similarly the memory controller N stores and or retrieves data to and from the bank of memory devices to which it is coupled. Alternatively the SCPU instead of the compute engine performs computations. In this manner and advantageously compute functions as well as data storage are all done by the storage subsystem without the need for data movement to and from the host which frees the host to tend to other matters thereby improving system performance. In other words the host is offloaded. Reduction in system power as data is not moved from volatile memory across many interfaces to the host memory. Accordingly the step s of having to move the data from the host to storage i.e. the bank of memory devices and is avoided. This results in power saving. Furthermore the storage subsystem causes lower latency compared to prior art systems because data movement across multiple interfaces is avoided. Data movement is merely across one interface the interface .

In this respect the storage subsystem allows performing computation within a SSD avoiding data movement of data that is stored in the SSD to the host for computation performing the compute function in the compute engine or the SCPU and reducing latency of applications because data is not moved from memory devices or across many interfaces to the host.

A method and apparatus in accordance with an apparatus and method of the invention for communicating with a Solid State Disk SSD that increases application throughput in a computer system is disclosed.

The embodiments presented herein represent apparatus and methods of the invention to improve the performance of applications running on computer systems that use one or more solid state disks SSDs .

Next at step execution of the application causes the SCPU to send the workload information through appropriate APIs. At step upon receipt of the APIs the storage subsystem configures and or launches invokes the appropriate Flash Translation Layer FTL application that is optimized for the workload sent by execution of the application. In the case of other non volatile memories similar logical to physical translation layers software is invoked. At step the storage subsystem is ready to process work requests associated with the workload from the host. In an embodiment of the invention the FTL application is run by the SCPU .

The APIs can also be used to select optimal algorithms to manage the memory i.e. memory banks and based on the workload.

According to the various methods and apparatus of the invention predictable performance increased endurance reduced latency dynamic ability to turn on off housekeeping select optimal SSD algorithms through APIs and scheduling SSD housekeeping at optimal times based on dynamic work load API calls may be achieved.

Although the description has been described with respect to particular embodiments thereof these particular embodiments are merely illustrative and not restrictive.

As used in the description herein and throughout the claims that follow a an and the includes plural references unless the context clearly dictates otherwise. Also as used in the description herein and throughout the claims that follow the meaning of in includes in and on unless the context clearly dictates otherwise.

Thus while particular embodiments have been described herein latitudes of modification various changes and substitutions are intended in the foregoing disclosures and it will be appreciated that in some instances some features of particular embodiments will be employed without a corresponding use of other features without departing from the scope and spirit as set forth. Therefore many modifications may be made to adapt a particular situation or material to the essential scope and spirit.


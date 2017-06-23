---

title: Computer system, computer and method for performing thin provisioning capacity management in coordination with virtual machines
abstract: In the computer system, a storage system provides a storage level virtual volume based on thin provisioning technology, to a physical server on which a virtual machine is defined. The storage system releases the area of the logical volume corresponding to the storage level virtual volume accessed by a virtual machine which is specified to be deleted, on the basis of storage level virtual volume conversion information which is managed by the storage system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09411746&OS=09411746&RS=09411746
owner: Hitachi, Ltd.
number: 09411746
owner_city: Tokyo
owner_country: JP
publication_date: 20150508
---
This application is a Continuation of U.S. application Ser. No. 14 157 029 filed Jan. 16 2014 now U.S. Pat. No. 9 058 125 incorporated herein by reference in its entirety which is a Continuation of U.S. application Ser. No. 12 745 842 National Stage of PCT JP2010 000705 filed Jun. 2 2010 now U.S. Pat. No. 8 656 136 incorporated herein by reference in its entirety.

The present invention relates to management of a computer system which includes a storage system and a server computer.

Storage capacity virtualization technology called Thin provisioning technology is known. Thin provisioning technology is disclosed in Patent Literature 1.

When a server computer provides virtual machines by means of a server virtualization program the virtual machines can be created and deleted more flexibly. However if virtual volumes are provided using thin provisioning technology then it is not possible readily to perform capacity management of thin provisioning in coordination with the creation and deletion of virtual machines.

Therefore the object of the present invention is to carry out capacity management of thin provisioning in accordance with the creation and deletion of virtual machines.

In the computer system according to the present invention a storage system provides storage level virtual volumes based on thin provisioning technology to a physical server on which a virtual machine is defined. The storage system releases the area of the logical volume corresponding to the storage level virtual volume accessed by a virtual machine specified to be deleted on the basis of storage level virtual volume conversion information which is managed by the storage system.

According to the present invention capacity management of thin provisioning can be carried out readily in accordance with the creation and deletion of virtual machines.

Below embodiments of the present invention are described with respect to the accompanying drawings. The definitions of the terms used in the description of the embodiments are as indicated below. For other terms generic definitions can be applied. Furthermore in the following description processes executed by a computer program are actually carried out by a processor which executes the computer program.

 Leverage ratio is the ratio of the capacity of a virtual storage area corresponding to a physical storage area with respect to the capacity of the physical storage area. In the present embodiment there are leverage ratios of a plurality of types. For example the leverage ratio of a first type is the ratio of the total capacity of one or more server level pools corresponding to a storage level pool with respect to the capacity of the storage level pool. The leverage ratio of a second type is the ratio of the total capacity of one or more server level virtual volumes corresponding to a storage level pool with respect to the capacity of the storage level pool. In the following description the second type of leverage ratio in particular is called end to end capacity leverage ratio .

 Volume means a logical storage area logical volume which is provided on the basis of one or more physical storage devices for example a hard disk drive or flash memory . A volume is provided on the basis of a storage space of a RAID Redundant Array of Independent or Inexpensive Disks group for example. The RAID group contains a plurality of physical storage devices and data is stored in accordance with prescribed RAID levels.

 Storage level virtual volume means a virtual volume which is provided by the storage controller. The whole area of a storage level virtual volume the area is also called a storage region and hereinafter may be referred to as a storage level virtual volume address area or a low level address area LL AA does not necessarily have to be allocated to the storage region of a storage device or volume hereinafter this storage region may be referred to as a low level storage area LL SA . More specifically for instance all or a portion of the area LL AA of the storage level virtual volume is not initially allocated with the area LL SA in one or more volumes belonging to a storage level pool. In other words initially for example a portion of the area LL SA of a storage level pool may be allocated to an area LL AA of a portion of the storage level virtual volume. Here initially means for example immediately after a storage level virtual volume has been defined or immediately after a storage level virtual volume has been defined and has become accessible from a physical server. The storage system sends the capacity of the storage level virtual volume to the physical server on the basis of storage level virtual volume information which represents the capacity of the storage level virtual volume. The data format such as the data structure may differ and may be different due to rounding down or the like between the capacity of the storage level virtual volume which is managed internally in the storage system and the capacity of the storage level virtual volume which is sent to the physical server by SCSI protocol or the like. Of course the capacity of the storage level virtual volume which is managed inside the storage system and the capacity of the storage level virtual volume which is sent to the physical server may be the same.

 Server virtualization program is a program which constructs a virtual server system by virtualizing the physical resources of a physical server. The server virtualization program is for example a hypervisor. Furthermore the physical resources are for example a processor for instance a microprocessor a storage resource for instance a memory and a communications interface apparatus for instance an HBA Host Bus Adapter .

A virtual machine is a virtual computer which is provided by a server virtualization program. By means of a server virtualization program it is possible to construct a system in such a manner that a plurality of computers operate effectively on a single physical server. Each of these effective computers is a virtual machine may be referred to as VM . In a virtual machine for example a computer program such as an OS Operating System or the like is carried out virtually.

 Server level pool is a storage area constructed from one or more storage level virtual volumes allocated from the storage system by the server virtualization program. The server level pool is used from a virtual machine via a server level virtual volume. More specifically if data is being written from a virtual machine to a server level virtual volume then the area of a portion of the server level pool more accurately the volume or virtual machine provided by the storage system included in the server level pool this area may be referred to hereinafter as a high level storage area HL SA is allocated to the area of the server level virtual volume specified as the write destination for that data hereinafter this area is referred to as a server level virtual volume area or a high level address area HL AA . If the virtual volume is included in the server level pool then HL SA indicates the same object as LL AA. However the management units differ as described hereinafter. Thereupon a write request indicating an area HL SA inside the storage level virtual volume which corresponds to the area HL AA of the allocated portion is sent to the storage system that provides that storage level virtual volume from the physical server for example from the server virtualization program executed on the physical server . In response to this write request the storage controller of the storage system allocates a portion of the area inside the storage level pool LL SA to the area indicated in the write request the area inside the storage level virtual volume LL AA and writes data to the allocated area LL AA . When reference is made below to write data to the LL AA in practice this means writing the data to the LL SA which corresponds to the LL AA. Furthermore in the following description reference to the area of a volume or virtual volume provided by a storage system included in the server level pool is abbreviated to the expression area of the server level pool .

 Server level virtual volume is a virtual volume which is constructed by a server virtualization program. The whole of the storage area HL AA of the server level virtual volume does not necessarily have to be allocated to a physical storage area HL SA . The storage area of the server level virtual volume is accessed by a virtual machine.

 Storage level pool is a pool made up of one or more volumes. The area LL SA of one portion of the storage level pool is allocated as a write destination area LL AA from the physical server in the storage level virtual volume. The storage level pool may be a group a virtual pool of a plurality of pools belonging to one or more volumes. In the description given below reference to area of a volume included in the storage level pool is abbreviated to the expression area of the storage level pool .

According to this example there are a plurality of storage level pools for example storage level pools and a storage area topology having a tree structure is constructed on the basis of these respective storage level pools. The constituent elements of the storage area topology are stated in order from the lower level storage level pools storage level virtual volumes server level pools and server level virtual volumes. According to this example the following storage areas A to D correspond to the storage level pool 

 C server level virtual volume which corresponds to server level pool server level virtual volume to which a portion of storage area is allocated from the server level pool and

In other words according to this example the server level virtual volumes to correspond to the storage level pool these server level virtual volumes to being constituent elements of the storage area topology based on the storage level pool .

In the embodiment described below it is possible to calculate the end to end capacity leverage ratio for each storage area topology in other words for each storage level pool. This is because for each storage level pool it is possible to identify the storage area topology forming the basis of that storage level pool in other words to identify the corresponding server level virtual volumes.

As shown in a server level pool may share a plurality of physical servers for example physical servers and . In this case even if a virtual machine in the physical server is migrated to the physical server as indicated by the dotted line for example the end to end capacity leverage ratio of the storage level pool does not change. This is because the migration of the virtual machine means that the server level virtual volume which was mounted on the virtual machine is also migrated to the physical server but no actual change occurs in the capacity of that server level virtual volume . In other words the end to end capacity leverage ratio of the storage level pool changes in cases where a configuration change which alters the total capacity of the server level virtual volumes and corresponding to the storage level pool or a configuration change which alters the capacity of the storage level pool has been carried out.

A server level virtual volume includes a plurality of HL AA but the size of each HL AA may be a common size corresponding to the server level virtual volume. The server level pool includes a plurality of HL SA but the sizes of each HL SA may be a common size corresponding to the server level pool or respectively different sizes. A storage level virtual volume includes a plurality of LL AA but the size of each HL AA may be a common size corresponding to the storage level virtual volume. The storage level pool includes a plurality of LL SA but each LL SA may have a common size corresponding to the storage level pool. In this configuration the correspondences between pages may be managed by means of a table or the like or may be determined by calculation.

When a program executed on a virtual machine has issued a write request indicating a certain HL AA in a sever level virtual volume then if an HL SA is not allocated to that HL AA an unallocated HL SA is duly allocated from the server level pool corresponding to that sever level virtual volume. A write request indicating the LL AA corresponding to the allocated HL SA is then sent to the storage system from the physical server . In the storage system if an LL SA has not be allocated to that LL AA then an unallocated LL SA is allocated to the LL AA from the storage level pool corresponding to the storage level virtual volume having the LL AA. Data corresponding to the write request is then written to the LL SA. If the LL SA is based on a plurality of PDEVs for example then data is stored in the plurality of PDEVs in accordance with a prescribed RAID level for example.

In the first embodiment a management server gathers virtual volume information for the storage system and virtual volume information for the physical servers analyzes the virtual volume information of the storage system and the virtual volume information of the physical server and indicates the end to end capacity leverage ratio to the administrator for example storage administrator on the basis of these analysis results. The details of this are described below.

The computer system comprises a storage system a physical server and a management server . At least one of the storage system the physical server and the management server may be provided in plural fashion.

The storage system and the physical server are mutually connected via a communications network for example a SAN or a LAN . The management server connects the storage system and the physical server via a communications network for example a LAN or a SAN .

The storage system comprises a plurality of PDEVs physical storage devices and a plurality of storage controllers CTL . The PDEVs and the storage controllers are connected to each other by means of an internal network or bus for example. The storage controller stores data in a storage area on the basis of the PDEVs

The PDEVs are disk type storage media drives for example hard disk drives and store data in accordance with write requests received by the storage system from the physical server . The PDEVs may also be flash memory drives for instance. It is also possible to provide one PDEV only.

The storage controller is an apparatus which controls the operation of the storage system . The storage controller comprises an internal network. The internal network is connected for example to a storage port a processor for example CPU and a memory . Storage controllers are connected to each other via the internal network. Furthermore the storage controllers and respective PDEVs are connected to each other by a plurality of back end networks. It is also possible to provide one storage controller only.

The storage port is an interface which is connected to the storage system and the management server via a network such as a SAN .

The memory is formed by a RAM Random Access Memory for example and stores programs to be executed by the processor and information required by the processor and the like. More specifically for example a storage control program is stored in the memory of the storage controller and controls the storage controller on the basis of management operation requests received from the management server . A management operation request is a request for operating the storage system for example a volume construction request storage level pool construction request or the like. The memory may be employed as a cache memory in which data input to or output from the PDEVs is stored temporarily.

The internal networks in the physical server and the storage system desirably have broader bandwidth than the transmission bandwidth of the storage port and all or a portion thereof may be substituted by bus or switch type networks. Furthermore in one storage port is present in the storage controller but in actual practice a plurality of storage ports may be present in the storage controller . The storage controller may be formed by a plurality of components. Similarly the memory may also be formed by a plurality of components.

As described below the storage system forms one or more volumes which belong to a storage level pool for example. The storage level pool may belong to the storage system or may belong to a system other than the storage system for example a system interposed between the storage system and the physical server for instance a switching apparatus .

A storage system may be one storage apparatus or a group of a plurality of storage apparatuses. For example a volume VOL managed by a certain storage apparatus may be a VOL based on a PDEV contained in another storage apparatus.

The whole area LL AA of one or more volumes may have been allocated to the area LL SA of a storage device included in a storage system or a portion of the area LL AA of one or more volumes may not have been allocated to the area LL SA of the storage device.

The physical server is one example of a server computer and comprises a processor a memory and an HBA . The processor the memory and the HBA are connected to each other via an internal network.

The processor carries out processing of various types by executing a program stored in the memory . For example the processor can input or output write or read data to or from one or more storage level virtual volumes provided by the storage system by sending an I O request write request or read request to the storage system .

The memory stores programs which are executed by the processor and information required by the processor and the like. The memory may be a semiconductor memory or storage device or a combination of these. The memory stores a server virtualization program .

The HBA is an interface which is connected to the storage system via a network such as a SAN LAN or the like. More specifically for example the HBA outputs I O requests from the processor to the storage system .

The server virtualization program constructs a virtual server environment virtual machine from the physical resources belonging to the physical server .

The management server is a computer which comprises a processor a memory a management program and a NIC Network Interface Card . The processor the memory the PDEV and the NIC are connected to each other via an internal network.

The processor carries out processing of various types by executing a program stored in the memory . For example the processor controls the allocation of storage level virtual volumes to the physical server as executed by the storage system by sending a management request to the storage system . The management request may include a remote transfer request or a copy control request or the like.

The memory stores programs which are executed by the processor and information required by the processor and the like. For example a management program is stored in the memory . The memory may be a semiconductor memory or storage device or a combination of these.

The NIC is an interface which is connected to the storage system via a network such as a LAN or the like.

The management server may comprise an input output device . The input output device inside the management server is also connected to the internal network.

Examples of an input output device are a display a keyboard and a pointer device but devices other than these may also be used. Furthermore as an alternative to an input output device a serial interface or Ethernet registered trademark interface may be used as an input output device . Moreover a display computer comprising a display keyboard or pointer device may also be connected to this interface. Display information may be sent to a display computer and input information may be received from a display computer. By this means a display can be provided on the display computer and by receiving an input an input operation to the input output device can be performed.

The management program manages the storage system . More specifically for example the management program performs operations such as managing the volume configuration managing the storage level pool configuration managing the storage level virtual volume configuration instructing volume allocations of various types and so on.

The management server may be divided into a device which manages the storage system and a device which manages the physical servers . More specifically for instance the management server is one example of a management system. The management system comprises one or more computers for example a management computer or a combination of a management computer and a display computer. More specifically if the management computer shows display information for example then the management computer forms a management system. Furthermore in order to increase the speed and reliability of processing it is also possible to achieve functions similar to those of the management computer by means of a plurality of computers and in this case the plurality of computers also including a display computer if display is performed by a display computer form a management system.

The memory stores for example storage level pool information storage level virtual volume information volume information storage internal mapping information and a storage control program .

The storage level virtual volume information is information relating to storage level virtual volumes.

The storage internal mapping information is information which indicates the mapping of storage areas of various types volumes storage level pools storage level virtual volumes which are managed by the storage system .

The storage control program is a program in which processing relating to the control of the storage system is defined. The storage control program comprises for example a storage virtualization module a storage configuration management module and a command control module . The respective modules included in the storage control program do not necessarily have to be modules of a single program and may respectively be separate program codes.

The storage level pool information includes for example for each storage level pool information relating to the storage level pool as well as information relating to the volumes belonging to the storage level pool and information relating to the storage level virtual volumes to which storage area is allocated from the storage level pool. More specifically for example the storage level pool information is a table which contains for each storage level pool a record of the following attribute values a storage level pool identifier a storage level pool capacity a storage level pool free capacity volume identifiers storage level virtual volume identifiers a storage level virtual volume total capacity an LL SA size and an unallocated LL SA identifier list .

The storage level pool identifier is an identifier which is allocated to the storage level pool by the storage virtualization module .

The storage level pool allocated capacity is the total capacity of the area out of the capacity of the storage level pool which has been allocated to storage level virtual volumes by the storage control program .

The volume identifiers are identifiers of volumes belonging to the storage level pool. A volume belonging to the storage level pool means a volume which has been set so as to belong to the storage level pool by the storage virtualization module .

The storage level virtual volume total capacity is the sum value of the capacities of all of the storage level virtual volumes corresponding to the storage level pool.

The LL SA size is a value indicating the management unit length more specifically the unit length which is allocated or released of the area LL SA of a volume included in the storage level pool.

The unallocated LL SA identifier list is a list of the identifiers of the areas LL SA which are not allocated to a storage level virtual volume that has been associated with the storage level pool. In the examples of identifiers shown in the drawings an offset number from a list stored in the volume identifier is stated before the colon and an offset number from the start of the area LL SA of the volume indicated by the volume identifier and the offset number is stated after the colon. The areas LL SA are created by dividing up the volume from the start by the LL SA size and offset numbers 0 1 . . . are allocated to the areas in order from the start of the area LL SA . Taking as an example the identifier 01 002 of the unallocated LL SA in the storage level pool STPOOL the 01 before the colon indicates the identifier of the next volume from the start and therefore the volume identifier corresponds to STLDEV while the 002 after the colon indicates the third area LL SA from the start of STLDEV . Incidentally since the LL SA size of the STPOOL is 100 MB where 1 M is 1024 K and 1 K is 1024 then supposing that data is addressed based on units of 512 byte blocks this third area LL SA from the start will range from the 400 k block to the 600 k 1 block. Below unless expressly stated otherwise block addresses are based on units of 512 byte blocks 1 M is 1024 K and 1 K is 1024.

Provided that the storage level pool information contains attribute values relating to a storage level pool a data structure other than a table may be employed and attribute values relating to a storage level pool other than the attribute values described above may also be included. Furthermore the storage level pool information may omit a portion of the attribute values described above apart from the storage level pool identifier. Furthermore shows an example of values stated in byte units but it is also possible to use other units for example SCSI block length or another area management unit length etc. This point is common to the information held by the computer system.

Furthermore as can be seen from the storage level pool capacity is not necessarily the same as the storage level virtual volume total capacity . This is because the storage level pool may be formed by an area of a portion of one or more volumes belonging to the storage level pool.

The storage level virtual volume information includes for each storage level virtual volume information relating to the storage level virtual volume and information relating to the storage level pool which is the allocation source of the area allocated to that storage level virtual volume. More specifically for example the storage level virtual volume information is a table which contains for each storage level virtual volume a record of the following attribute values a storage level virtual volume identifier a storage level virtual volume capacity a storage level virtual volume allocated capacity a storage level pool identifier a storage level pool capacity and a port number LUN Logical Unit Number . Moreover the storage level virtual volume information also includes storage level area conversion information expressed in the drawing as LL area conversion information .

The storage level virtual volume identifier is an identifier which is allocated to the storage level virtual volume by the storage virtualization module .

The storage level virtual volume capacity is the capacity of the storage level virtual volume set by the storage virtualization module .

The storage level virtual volume allocated capacity is the total capacity of the area out of the storage level virtual volume capacity which has been allocated to the storage level virtual volume from the storage level pool by the storage control program .

The storage level pool identifier is an identifier of the storage level pool which is the allocation source of the area allocated to the storage level virtual volume.

The storage level area conversion information is information that includes the identifiers of the areas LL SA of the storage level pool which have been allocated to each area LL AA of the storage level virtual volumes. An area LL AA for which the area LL SA is marked as unallocated means that an area LL SA has not been allocated to the corresponding area LL AA . The storage level area conversion information is created with all or a portion of the LL AA set to unallocated immediately after definition of the corresponding storage level virtual volume and as described below areas LL SA are allocated in accordance with an initial write request which covers the range of a portion or all of the areas LL AA and the write data of the write request is saved in the areas LL SA .

In the example illustrated the storage level area conversion information is expressed in the form of a list and identifiers which respectively indicate an area LL SA allocated to an area LL AA or which indicate the value unallocated are stored in sequence from the area LL AA at the start of the storage level virtual volume.

If the block address specifying an area LL AA is the Y block address then the address of the 512 byte block of the corresponding area LL SA is determined as follows.

 LL SA offset value obtained by dividing Y by LL SA size of corresponding storage level pool rounded down to nearest integer .

 LL SA offset internal address remainder obtained by dividing Y by LL SA size of corresponding storage level pool 

 Volume where corresponding LL SA resides value before colon in identifier of LL SA offset in list . Reference to the x offset value in the list means the x 1 th value from the top of the list.

 Address in volume where corresponding LL SA resides value after in LL SA offset identifier in list LL SA size of corresponding storage level pool LL SA offset internal address .

Therefore when an I O request specifying the 501 K block address of the storage level virtual volume STVVOL is received from the physical server the following calculation is carried out.

Volume where corresponding LL SA resides 02 identified as STLDEV by referring to the volume identifier in 

Provided that the storage level virtual volume information contains attribute values relating to a storage level virtual volume a data structure other than a table may be employed and attribute values relating to a storage level virtual volume other than the attribute values described above may also be included. Furthermore the storage level virtual volume information may omit a portion of the attribute values described above apart from the storage level virtual volume identifier .

The volume information contains for each volume information relating to a volume and information on the storage level pool to which the volume belongs. More specifically for example the volume information is a table which contains for each volume a record of the following attribute values a volume identifier a volume capacity PDEV identifiers and a storage level pool identifier .

The volume identifier is an identifier which is allocated to the volume by the storage virtualization module .

The volume capacity is the capacity of the volume. A volume is constructed for example by the storage virtualization module grouping together the storage area of one of more PDEVs . The storage area of the volume is mapped and distributed to the storage area of one or more PDEVs under control implemented by the storage controller .

The PDEV identifier is an identifier that has been allocated to a PDEV based on the volume by the storage virtualization module . In other words the PDEV identifiers are the identifiers of the PDEVs which form the basis of the volume.

The storage level pool identifier is an identifier of the storage level pool to which the volume belongs.

Provided that the volume information contains attribute values relating to a volume a data structure other than a table may be employed and attribute values relating to a volume other than the attribute values described above may also be included. Furthermore the volume information may omit a portion of the attribute values described above apart from the volume identifier .

The storage internal mapping information is for example a table which contains for each storage level pool a record of the following attribute values a storage level pool identifier storage level virtual volume identifiers volume allocated capacity and PDEV identifiers .

The storage level virtual volume identifiers are identifiers of the storage level virtual volumes to which a portion of storage area is allocated from the storage level pool.

The PDEV identifiers are identifiers of the PDEVs which form the basis of the volumes belonging to the storage level pool.

Provided that the storage internal mapping information contains attribute values relating to mapping of the devices included in the storage system a data structure other than a table may be employed and attribute values relating to mapping information other than the attribute values described above may also be included. Furthermore the storage internal mapping information may omit a portion of the attribute values described above apart from the storage level pool identifier .

As shown in as well the storage control program comprises for example a storage virtualization module a storage configuration management module and a command control module . A process for controlling the storage system is written in the storage control program which is stored in the memory of the storage controller and executed.

The storage configuration management module manages the configuration of the storage areas of various types included in the storage system . In specific terms the management of the configuration of the storage area means for example management of the volumes which make up the storage level pools management of the PDEVs which make up the volumes and so on.

The command control module interprets a command for example an I O request from a physical server or management server and executes processing as stipulated by that command.

The storage virtualization module constructs volumes on the basis of PDEVs . The storage virtualization module also constructs storage level virtual volumes. The storage virtualization module maps one or more volumes and one or more storage level virtual modules to a storage level pool.

The memory stores server level pool information server level virtual volume information and a server virtualization program .

The server virtualization program constructs virtual machines a server level pool server level virtual volumes and the like using the resources of a physical server .

The server level pool information includes for example for each server level pool information relating to the server level pool as well as information relating to the storage level virtual volumes belonging to the server level pool and information relating to the server level virtual volumes to which storage area is allocated form the server level pool. More specifically for example the server level pool information is a table which contains for each server level pool a record of the following attribute values a server level pool identifier a server level pool capacity a server level pool free capacity server level virtual volume identifiers a server level virtual volume total capacity a configuration storage port number LUN Logical Unit Number an HA SA size and an unallocated HL SA identifier list .

The server level pool identifier is an identifier which has been allocated to the server level pool by the server virtualization module .

The server level pool allocated capacity is the total capacity of the area out of the server level pool capacity which has been allocated to server level virtual volumes .

The server level virtual volume identifiers are identifiers of the server level virtual volumes to which a portion of storage area is allocated from the server level pool.

The server level virtual volume total capacity is the sum total of the capacities of all of the server level virtual volumes to which storage area is allocated from the server level pool.

The configuration storage port number LUN is the LUN and port number for identifying a storage level virtual volume belonging to the server level pool the LUN and port number are used in I O requests as a parameter indicating a storage level virtual volume . The port number LUN may be another identifier provided that it enables a storage level virtual volume provided by the storage system to be specified.

The HL SA size is a value indicating the management unit length more specifically the unit length which is allocated or released of the area HL SA of a volume included in the server level pool.

The unallocated LL SA identifier list is a list of the identifiers of the areas HL SA which are not allocated to a server level virtual volume that has been associated with the server level pool.

In the examples of identifiers shown in the drawings an offset number from a list stored in the configuration storage port number LUN is stated before the colon and an offset number from the start of the area HL SA of the storage level virtual volume indicated by the configuration storage port number LUN and the offset number is stated after the colon. The areas HL SA are created by dividing up the volume from the start by the HL SA size and offset numbers 0 1 . . . are allocated to the areas in order from the start of the volume. Taking as an example the identifier 00 002 of the unallocated HL SA in the server level pool SVPOOL the 00 before the colon indicates the identifier of the storage level virtual volume at the start of the pool and therefore the volume identifier corresponds to the storage level virtual volume having a LUN of 0 at PORT Number XXX.XXX while the 002 after the colon indicates the third area HL SA from the start of that storage level virtual volume. Incidentally since the HL SA size of the SVPOOL is 50 MB then the third area HL SA from the start will range from the 200 k block to the 300 k 1 block.

Provided that the server level pool information contains attribute values relating to a server level pool a data structure other than a table may be employed and attribute values relating to the server level pool configuration other than the attribute values described above may also be included. Furthermore the server level pool information may omit a portion of the attribute values described above apart from the server level pool identifier .

The server level virtual volume information includes for example for each server level virtual volume information relating to the server level virtual volume as well as information relating to the server level pool which is the allocation source of the area allocated to the server level virtual volume and information relating to virtual machine which uses the server level virtual volume. More specifically for example the server level virtual volume information contains for each server level virtual volume a record of the following attribute values a server level virtual volume identifier a server level virtual volume capacity a server level virtual volume allocated capacity a server level pool identifier a server level pool capacity a corresponding virtual machine identifier a device identifier for virtual machine recognition and server level area conversion information indicated as HL area conversion information in the figure .

The server level virtual volume identifier is an identifier which has been allocated to the server level virtual volume by the server virtualization program .

The server level virtual volume allocated capacity is the total capacity of the area virtual area out of the server level virtual volume capacity to which storage area has been allocated from the server level pool.

The server level pool identifier is an identifier of the server level pool which is the allocation source of the area allocated to the server level virtual volume.

The server level pool capacity is the capacity of the server level pool which is the allocation source of the area allocated to the server level virtual volume.

The corresponding virtual machine identifier is the identifier of the virtual machine which uses the server level virtual volume.

The device identifier for virtual machine recognition is an identifier whereby the virtual machine recognizes the server level virtual volume a device identifier which indicates the server level virtual volume .

The server level area conversion information is information that includes the identifiers of the areas HL SA of the server level pool which have been allocated to each area HL AA of the server level virtual volumes. An area HL AA for which HL SA is marked as unallocated means that an area HL SA has not been allocated to the corresponding area HL AA . The server level area conversion information is created with all or a portion of the HL AAs set to unallocated immediately after definition of the corresponding server level virtual volume and as described below the areas HL SA are allocated in accordance with an initial write request which covers the range of a portion or all of the areas HL AA and the write data of the write request is saved in the areas HL SA .

In the example illustrated the storage level area conversion information is expressed in the form of a list and identifiers which respectively indicate an area HL SA allocated to an area HL AA or which indicate the value unallocated are stored in sequence from the area HL AA at the start of the server level virtual volume.

If the block address specifying the area HL AA is the Z block address then the address of the 512 byte block of the corresponding area HL SA is determined as follows.

 HL SA offset value obtained by dividing Z by HL SA size of corresponding server level pool rounded down to nearest integer .

 HL SA offset internal address remainder obtained by dividing Z by HL SA size of corresponding server level pool 

 Storage level virtual volume where corresponding HL SA resides value before colon in identifier of HL SA offset in list

 Address in volume where corresponding LL SA resides value after in HL SA offset identifier in list HL SA size of corresponding storage level pool HL SA offset internal address 

Therefore when an I O request specifying the 151K block address of the HDD in other words SVVVOL is received from the virtual machine the following calculation is carried out.

Volume where corresponding HL SA resides 01 identified as LUN 2 at port number ZZZ. KKK by referring to the configuration storage port number LUN in 

Provided that the server level virtual volume information contains attribute values relating to a server level virtual volume a data structure other than a table may be employed and attribute values relating to a server level virtual volume other than the attribute values described above may also be included. Furthermore the server level pool information may omit a portion of the attribute values described above apart from the server level virtual volume identifier .

The server virtualization program constructs virtual machines a server level pool server level virtual volumes and the like using the resources of a physical server . A more detailed description of the processing carried out by the server virtualization program is given in the section below.

The memory stores storage level pool configuration information storage level virtual volume configuration information port LUN correspondence information server level pool configuration information server level virtual volume configuration information end to end capacity leverage ratio information initial settings information and a management program .

The storage level pool configuration information is information relating to the configuration of storage level pools. Details of the storage level pool configuration information are given in .

The storage level virtual volume configuration information is information relating to the configuration of the storage level virtual volumes. Details of the storage level virtual volume configuration information are given in .

The port LUN correspondence information is information relating to the port numbers and LUNs corresponding to the storage level virtual volumes which are provided by the storage system to the physical server . The port LUN correspondence information is described in detail in .

The server level pool configuration information is information relating to the configuration of server level pools . Details of the server level pool configuration information are given in .

The server level virtual volume configuration information is information relating to the configuration of the server level virtual volumes. Details of the storage level virtual volume configuration information are given in .

The end to end capacity leverage ratio information is information relating to the end to end capacity leverage ratios of the storage level pools. The end to end capacity leverage ratio information is described in detail in .

The initial settings information is information relating to the initial settings input by a storage administrator. The initial settings information is described in .

The management program is a program which manages a storage system and physical servers . The management program contains a storage management module a server management module and a leverage management module .

The storage management module is a module which manages a storage system by using the storage level pool configuration information and the storage level virtual volume configuration information .

The server management module is a module which manages a physical server by using the server level pool configuration information and the server level virtual volume configuration information .

The leverage management module is a module which manages the end to end capacity leverage ratio by using the port LUN correspondence information the end to end capacity leverage ratio information and the initial settings information .

The respective modules included in the storage control program do not necessarily have to be modules of a single program and may respectively be separate program codes.

The storage level pool configuration information contains for each storage level pool information relating to the storage level pool and information relating to storage level virtual volumes corresponding to that storage level pool. More specifically for example the storage level pool configuration information is a table which contains for each storage level pool a record of the following attribute values a storage level pool identifier a storage level pool capacity a storage level pool allocated capacity corresponding storage virtual volume identifiers a corresponding storage level virtual volume total capacity pool configuration volume identifiers and a storage apparatus identifier .

The storage level pool allocated capacity is the total capacity of the area out of the storage level pool capacity which has been allocated to the storage level virtual volume.

The corresponding storage level virtual volume identifier is the identifier of a storage level virtual volume which corresponds to the storage level pool.

The corresponding storage level virtual volume total capacity is the sum value of the capacities of all of the storage level virtual volumes corresponding to the storage level pool.

The pool configuration volume identifiers are identifiers of volumes belonging to the storage level pool.

The storage apparatus identifier is an identifier of the storage apparatus containing the volumes belonging to the storage level pool.

Provided that the storage level pool information contains attribute values relating to the composition of the storage level pool a data structure other than a table may be employed and attribute values relating to the configuration of a storage level pool other than the attribute values described above may also be included. Furthermore the storage level pool information may omit a portion of the attribute values described above apart from the storage level pool identifier .

The information elements to described above are obtained for example from the information elements to in the storage level pool information see which is gathered by the management server from the storage apparatuses which make up the storage system. Furthermore the information element is an information element which indicates which storage apparatus the storage level pool information has been gathered from.

The storage level virtual volume configuration information includes for each storage level virtual volume information relating to the storage level virtual volume and information relating to the storage level pool corresponding to that storage level virtual volume. More specifically for example the storage level virtual volume configuration information is a table which contains for each storage level virtual volume a record of the following attribute values a storage level virtual volume identifier a storage level virtual volume capacity a storage level virtual volume allocated capacity and a corresponding storage level pool identifier .

The storage level virtual volume allocated capacity is the total capacity of the area out of the storage level virtual volume capacity which has been allocated to the storage level virtual volume from the storage level pool.

The corresponding storage level pool identifier is an identifier of the storage level pool corresponding to the storage level virtual volume.

Provided that the storage level virtual volume configuration information contains attribute values relating to a storage level virtual volume a data structure other than a table may be employed and attribute values for a storage level virtual volume other than the attribute values described above may also be included. Furthermore the storage level virtual volume information may omit a portion of the attribute values described above apart from the storage level virtual volume identifier .

The information elements to described above are obtained for example from the information elements to in the storage level pool information see which is gathered by the management server from the storage apparatuses which make up the storage system.

The server level pool configuration information contains for each server level pool information relating to the server level pool and information relating to server level virtual volumes corresponding to that server level pool. More specifically for example the server level pool information is a table which contains for each server level pool a record of the following attribute values a server level pool identifier a server level pool capacity a server allocated capacity corresponding server level virtual volumes a corresponding server level virtual volume total capacity volume source storage apparatuses and a configuration storage port number LUN .

The server level pool allocated capacity is the total capacity of the area out of the server level pool capacity which has been allocated to the server level virtual volumes.

The corresponding server level virtual volume identifiers are identifiers of server level virtual volumes which correspond to the storage level pool.

The corresponding server level virtual volume total capacity is the sum value of the capacities of all of the server level virtual volumes corresponding to the server level pool.

The volume source storage apparatus identifiers are identifiers of the storage apparatuses which provide the storage level virtual volumes corresponding to the server level pool to the physical server .

The configuration storage volume port number LUN is a port number which allows the physical server to access a storage level virtual volume corresponding to the server level pool and a LUN whereby the physical server can recognize the storage level virtual volume by SCSI.

Provided that the server level pool configuration information contains attribute values relating to a server level pool a data structure other than a table may be employed and attribute values relating to the server level pool other than the attribute values described above may also be included. Furthermore the server level pool configuration information may omit a portion of the attribute values described above apart from the server level pool identifier .

The information elements to described above are obtained for example from the information elements to in the server level pool information see which is gathered by the management server from the physical servers. Furthermore the information element is an information element that indicates which physical server the server level pool information has been gathered from.

The server level virtual volume configuration information includes for each server level virtual volume information relating to the server level virtual volume and information relating to the server level pool corresponding to that server level virtual volume. More specifically for example the server level virtual volume information is a table which contains for each server level virtual volume a record of the following attribute values a server level virtual volume identifier a server level virtual volume capacity a server level virtual volume allocated capacity a server level virtual volume unallocated capacity a server level virtual volume used capacity a corresponding server level pool identifier a corresponding virtual machine identifier and a device identifier for virtual machine recognition .

The server level virtual volume allocated capacity is the total capacity of the area out of the server level virtual volume capacity which has been allocated to the server level virtual volume from the storage level pool.

The server level virtual volume unallocated capacity is the total capacity of the area virtual area out of the server level virtual volume capacity to which storage area has not been allocated from the server level pool.

The server level virtual volume used capacity is the capacity to which data has been written by a virtual machine out of the server level virtual volume capacity.

The corresponding server level pool identifier is an identifier of the server level pool corresponding to the server level virtual volume.

The corresponding virtual machine identifier is the identifier of the virtual machine which is the allocation destination of the server level virtual volume.

The device identifier for virtual machine recognition is an identifier whereby a virtual machine recognizes a server level virtual volume as a device for example as a hard disk drive .

Provided that the server level virtual volume configuration information contains attribute values relating to a server level virtual volume a data structure other than a table may be employed and attribute values for a server level virtual volume other than the attribute values described above may also be included. Furthermore the server level virtual volume information may omit a portion of the attribute values described above apart from the server level virtual volume identifier .

The information elements to and to described above are obtained for example from the information elements to in the server level virtual volume information see which is gathered by the management server from the physical servers. Furthermore the information element is an information element which is determined by calculating the data volume written to the server level virtual volume by the virtual machine.

The port LUN correspondence information is for example a table which contains for each storage level virtual volume a record of the attribute values port port number LUN and internal volume ID .

The port is the port number used by a physical server to access a provided storage level virtual volume when the storage system has provided a storage level virtual volume to the physical server .

The LUN is an identification number which allows the physical server to recognize by SCSI a storage level virtual volume provided by the storage system .

The internal volume ID is an identifier for identifying a storage level virtual volume provided to a physical server by the storage system .

Provided that the port LUN correspondence information includes attribute values relating to the correspondences between the port number the LUN and the internal volume ID a data structure other than a table may be employed and attribute values for the correspondence between the port number LUN and internal volume ID other than the attribute values described above may also be included. Furthermore the port LUN correspondence information may omit a portion of the attribute values described above apart from the internal volume ID .

The information elements to described above can be created in the following way for example. The correspondence information shown in is constructed using the storage level virtual volume identifiers port numbers and LUNs in the storage level virtual volume information see gathered from the storage apparatuses by the management server.

The end to end capacity leverage ratio information is for example a table which contains for each storage level pool a storage level pool identifier and an end to end capacity leverage ratio .

The end to end capacity leverage ratio is the end to end capacity leverage ratio corresponding to the storage level pool 100 total capacity of all server level virtual volumes corresponding to storage level pool capacity of storage level pool .

Provided that the end to end capacity leverage ratio information includes attribute values relating to the capacity leverage ratio of the pool unit a data structure other than a table may be employed and attribute values relating to the capacity leverage ratio of the pool unit other than the attribute values described above may also be included. Furthermore the end to end capacity leverage ratio may omit a portion of the attribute values described above apart from the storage level pool identifier .

The initial settings information is a table containing one or more records including the attribute values of end to end capacity leverage ratio threshold value and information gathering interval for example.

The end to end capacity leverage ratio threshold value is a threshold value indicating the upper tolerance limit of the capacity leverage ratio relating to the storage level pool which is input by the storage administrator via a setup screen of the management program .

The information gathering interval is the interval between the timings at which the end to end capacity leverage ratio is calculated as input by the storage administrator via the setup screen of the management program .

Provided that the initial settings information contains attribute values relating to the initial settings input by the storage administrator a data structure other than a table may be employed and attribute values relating to the initial settings other than the attribute values described above may also be included. Furthermore the initial settings information may omit a portion of the attribute values described above apart from the information gathering interval .

The leverage ratio display screen is a screen which is displayed by the management program . The reason why for example the end to end capacity leverage ratio of the storage level pool STPOOL is 500 is as follows.

From the information in the capacity 10000 MB of the storage level pool corresponding to the identifier STPOOL is specified. Furthermore the corresponding storage level virtual volume identifiers STVVOL and STVVOL which correspond to the identifier STPOOL are also specified.

The port number and LUN corresponding respectively to the identifiers STVVOL and STVVOL are specified from the information in .

Using these port numbers and LUNs the server level pool identifier SVPOOL is specified from the information in .

Using this identifier SVPOOL the server level virtual volume capacities 30000 MB and 20000 MB in other words a total capacity of 50000 MB are specified from the information in .

As a result of the foregoing a total capacity of 50000 MB in the server level virtual volumes which correspond to the storage level pool is identified in respect of the capacity 10000 MB of the storage level pool STPOOL and consequently an end to end capacity leverage ratio of 100 50000 10000 500 is calculated.

The display format and display information shown in are one example and other information apart from that shown in may be displayed provided that it relates to the end to end capacity leverage ratio. Furthermore the GUI may also employ a different format.

In the storage system volumes a storage level pool and storage level virtual volumes are constructed by a storage virtualization module of the storage control program .

The volumes are constructed by the storage virtualization module grouping together the storage area of one or more PDEVs . The storage areas of the volumes are distributed and mapped to the storage area of one or more PDEVs which make up a volume under control implemented by the storage controller .

The storage level pool is constructed by the storage virtualization module . The storage area of the storage level pool is distributed and mapped to the storage area of one or more volumes which correspond to the storage level pool under control implemented by the storage controller .

The storage level virtual volumes are constructed by the storage virtualization module . The storage level virtual volumes have a virtual area LL AA . In contrast to the areas LL SA of the volumes immediately after the definition of the storage level virtual volumes the areas LL AA of the storage level virtual volume are not associated with the physical storage region of a PDEV

When a write request to a virtual area LL AA of a storage level virtual volume has been issued if a portion of the area LL SA inside the pool has not been allocated to that area LL AA then under the control of the storage controller the unallocated area LL SA of the storage level pool is mapped dynamically.

The whole of the virtual storage area of the storage level virtual volumes does not have to correspond to a physical storage area such as a storage area of a PDEV and therefore it is possible to set the virtual storage area capacity of the storage level virtual volumes to a value that is higher than the physical storage area of the storage system for example the capacity of the pool . Furthermore if the unallocated area LL SA is insufficient immediately after starting access to the storage level virtual volume then it is possible to prevent failure of the write request due to the insufficient unallocated area LL SA by incorporating a new volume into the pool without changing the settings of the computer which is accessing the storage level virtual volume.

The storage system provides the storage level virtual volumes to the physical server . The physical storage area of the PDEV is accessed by the physical server via the storage level virtual volumes and the volumes which form the storage level pool .

 Step S Firstly the storage administrator inputs information about the volumes to be set in the storage level pool to the management program . The identifier of the storage level pool the threshold value the number of volumes and the volume identifiers are established.

 Step S The storage management module generates a command instructing set up of the storage level pool including the input information and sends this command to the storage system via the NIC.

 Step S In the storage system the command sent from the physical server is received by the command control module via the NIC.

The command control module recognizes the contents of the received command. If the contents of the command are invalid then the module rejects the command and returns an error for example .

 Step S If the command instructs the setting up of a storage level pool then the command control module passes on the received command to the storage virtualization module . The storage virtualization module receives the command and starts storage level pool setup processing.

 Step S The storage virtualization module firstly examines the storage level pool information and confirms that the storage level pool identifier relating to the command is valid. Furthermore the storage virtualization module confirms whether the storage level pool identifier has not yet been defined.

 Step S Thereupon the storage virtualization module confirms whether or not the volume relating to the command is usable. More specifically if the volume relating to the command is being formatted for example then that volume cannot be used and therefore the storage virtualization module rejects the command by returning an error for example . Furthermore if the volume relating to the command is already in use for example if the path to the volume has been defined if the volume is in use by a copy function or the like or if the volume has been reserved as a copy destination then the storage virtualization module rejects the command since the volume is not usable.

 Step S Thereupon the storage virtualization module sets the storage level pool capacity and the volume identifier in the storage level pool information . By means of this processing carried out by the storage virtualization module a volume is added to the storage level pool . The storage virtualization module adds all or a portion of the area of the registered volume to the unallocated LL SA identifier list as an LL SA.

 Step S Next the storage control program sends a reply indicating that the command was successful to the management server .

Upon receiving a reply from the storage system the storage configuration management module of the management server ends processing.

The physical server sends an I O request by specifying the LUN of a storage level virtual volume and the block address in the volume. This I O request is a data read request.

 Step S In the storage system the command control module receives an I O request from the physical server . If the content of the received I O request is invalid then this request is rejected an error is returned for example . If the content of the received I O request is valid then the command control module analyzes the content of the I O request. As a result of this analysis the command control module identifies that the I O request is a data read request.

 Step S Next the command control module acquires the block address of the storage level virtual volume relating to the received request which is to be read from.

 Step S Thereupon the command control module acquires the block address of the area LL SA of the volume that has been mapped to the area LL AA including the address of the area in the read request from the storage level pool corresponding to the storage level virtual volume that is to be read. In this case the address of the area of the storage level virtual volume in the read request may have been distributed and mapped to the addresses of a plurality of volumes . This processing is carried out by referencing the storage level pool information and the storage level virtual volume information but the details of this processing have already been described in explaining the respective information.

 Step S Thereupon the command control module refers to the volume information identifies the PDEV corresponding to the address of the area of the volume and acquires the address of that PDEV

 Step S Thereupon the command control module reads out data relating to the request from the address of the PDEV and sends this data to the physical server .

 Step S The command control module then sends a read request completion report to the physical server and ends processing.

If at step S there is no volume area LL SA allocated to the area LL AA including the address of the region in the read request then a clear value for example a string of zeros can be sent to the physical server .

The physical server sends an I O request by specifying the LUN of a storage level virtual volume and the block address in the volume. This I O request is a data write request.

 Step S In the storage system the command control module receives an I O request from the physical server . If the received I O request is invalid then this request is rejected an error is returned for example . The command control module then analyzes the content of this I O request. As a result of this analysis the command control module identifies that the I O request is a data write request.

 Step S Next the command control module acquires the block address of the storage level virtual volume relating to the received write request.

 Step S Thereupon the command control module refers to the storage level virtual volume information identifies the storage level pool corresponding to the storage level virtual volume and acquires the status of the pool.

 Step S The command control module refers to the storage level pool information identifies the volume corresponding to the storage level pool and judges whether or not the volume is usable.

 Step S If the volume is not usable then access to the volume is not possible and therefore the command control module sends an I O error to the physical server .

 Step S If it is judged that the volume is usable then the command control module sends a notification that the transfer of write data is possible to the physical server which sent the request. The physical server receives this and sends write data to the storage system .

 Step S Firstly the storage virtualization module refers to the storage level virtual volume information and the storage level pool information and checks whether an area LL SA of the storage level pool has been allocated to the area LL AA which includes the block address of the write request.

 Step S If it is judged at step S that an area has been allocated then the storage virtualization module refers to the storage level virtual volume information and the storage level pool information and acquires the volume allocated to the area LL AA which includes the specified block address and the block address of the area LL SA of that volume.

 Step S Thereupon the storage virtualization module refers to the volume information identifies the PDEV corresponding to the volume and the block address acquired at step S acquires the address of the region of the PDEV and writes the write data the data appended to the write request .

 Step S Upon completing the writing of the write data the storage virtualization module reports the end of writing to the command control module . The command control module receives this report sends a write request completion report to the physical server and ends processing.

 Step S On the other hand if it is judged at step S that an area has not been allocated then the storage virtualization module refers to the storage level pool information and confirms whether there is an unallocated area LL SA in the corresponding storage level pool . This step can be achieved by referring to the unallocated LL SA identifier list .

 Step S If it is judged at step S that there is an unallocated area LL SA then the storage virtualization module selects the unallocated area LL SA of the storage level pool acquires the volume and block address of the selected area LL SA and allocates same to the area LL AA judged to be unallocated at step S. The process of selecting the area LL SA in this step can be made for example by extracting an unallocated area LL SA from the start of the unallocated LL SA identifier list . Furthermore in the method described in and it is possible to specify the identifier and the block address of the volume of the selected area LL SA .

 Step S The module then updates the storage level pool information and the storage level virtual volume information . More specifically the module increases the allocated capacity of the storage level pool and the allocated capacity of the storage level virtual volume by the capacity of the selected area LL SA . Furthermore the value in the storage level area conversion information which corresponds to the area LL AA from step S is changed from unallocated to the volume and block address just acquired.

 Step S On the other hand if it is judged that there is no or insufficient unallocated area LL SA at step S then the storage virtualization module changes the status of the management information of the storage level pool to pool capacity insufficient .

 Step S The module then reports the pool capacity insufficiency to the physical server that issued the I O request and the storage system .

By means of the processing described above processing of a data write request by the physical server is completed.

In the physical server a server level pool server level virtual volumes and virtual machines are constructed by the server virtualization program . The server level pool is a pool which enables a storage region including a plurality of areas LL AA of a plurality of storage level virtual volumes which are provided by the storage system to be used as an area HL SA . The server level pool is constructed from one or more storage level virtual volumes allocated from the storage system by the server virtualization program . The server level pool principally uses a file system format and stores image files of the virtual machines and image files of the server level virtual volumes and the like. Furthermore when a virtual machine is temporarily halted the data stored virtually in the memory of the virtual machine is also stored as an image file. In other words from the perspective of the physical server it appears as if the various data which has been stored in the image file memory image and server level virtual volume relating to the virtual machine is stored in a storage level virtual volume. A management area for the server level virtual volumes is reserved inside the server level pool . This management area stores address information for the virtual storage areas of the server level virtual volumes mapping information on mapping to the storage level virtual volumes provided by the storage system and the like.

The server level virtual volumes are constructed by the server virtualization program . The server level virtual volumes each have a virtual storage area. In response to a write request from a virtual machine the server virtualization program dynamically maps an area of the required capacity from the virtual storage area of a server level virtual volume to the storage area of the server level pool .

The virtual machines are virtual computers which are constructed by the server virtualization program . In the virtual server environment a plurality of virtual machines operate by sharing the physical resources of a physical server. Similarly to a physical server a virtual machine can be installed with an OS and can be used as an independent server machine. The virtual machine accesses the storage area of the server level pool actually the storage level virtual volume via a server level virtual volume .

Access from a virtual machine to the server level virtual volume is controlled by the server virtualization program . By this means the server level virtual volume is recognized in the same way as a storage device having a physical storage area by the OS of the virtual machine . The control performed by the server virtualization program includes the processes of reading writing and capacity inquiry with respect to the server level virtual volumes and these processes are described hereinafter. A capacity inquiry request issued by the OS running on the virtual machine is a request for acquiring the capacity of a server level virtual volume which is necessary when the OS is to use that volume.

In the description given below SCSI is used as an example of the I O protocol issued to the server level virtual volume by the OS executed on the virtual machine . However as an alternative to a SCSI protocol it is also possible to employ other block access type protocols such as IDE or SAS for example.

 Step S Firstly the storage administrator inputs information about the volumes to be set in the server level pool to the server virtualization program . Storage level virtual volumes provided from the storage system are used as the volumes set in the server level pool . The identifier and threshold value of the server level pool and the number and LUN of the storage level virtual volumes are established.

 Step S The server virtualization program confirms whether or not the command instructing the setup of the server level pool and containing the input information is valid. If the command is invalid then the program rejects the command and returns an error for example .

 Step S The server virtualization program firstly refers to the server level pool information and confirms that the server level pool identifier relating to the command is valid.

 Step S Thereupon the server virtualization module confirms whether or not the storage level virtual volume relating to the command is usable. More specifically if the storage level volume relating to the command is being formatted for example then that storage level virtual volume cannot be used and therefore the program rejects the command by returning an error for example . Furthermore if the storage level virtual volume relating to the command is already in use for example if the path to the storage level virtual volume has been defined then that storage level virtual volume is not usable and the program rejects the command.

 Step S Next the server virtualization program sets the server level pool capacity and the configuration storage port number LUN in the server level pool information . By means of this processing performed by the server virtualization program a storage level virtual volume is set in the server level pool . The server virtualization program then adds all or a portion of the areas of the registered storage level virtual volume to the unallocated HL SA identifier list as an HL SA.

This process is described with respect to a case where the OS running on the virtual machine has issued a capacity inquiry request. Normally the OS subsequently issues a write request or read request and executes file system format processing for the server level virtual volumes .

The OS on the virtual machine specifies a device identifier for virtual machine recognition and issues a capacity inquiry request. In response to this request the server virtualization program returns the capacity of the server level virtual volume to the OS on the virtual machine by carrying out the processing described below. By this means the OS on the virtual machine is able to ascertain the capacity of the server level virtual volume .

 Step A The server virtualization program receives a capacity inquiry request sent by the OS of the virtual machine .

 Step B The server virtualization program analyzes the content of the request. The program then refers to the server level virtual volume information and specifies the server level virtual volume identifier corresponding to the device identifier for virtual machine recognition which is the destination of the inquiry.

 Step C The server virtualization program acquires the server level virtual volume capacity of the identifier specified at step B from the server level virtual volume information .

 Step D The server virtualization program reports the capacity acquired at step C to the OS on the virtual machine as the disk size of the storage device recognized by the OS on the virtual machine and then terminates processing.

By means of the processing described above the OS on the virtual machine is able to ascertain the capacity of the server level virtual volume .

This process is started when the server virtualization program detects the issue of a read request in which the OS on the virtual machine specifies the device identifier for virtual machine recognition of the server level virtual volume that is to be read from and a block address and block length.

 Step S The server virtualization program receives an I O request from the virtual machine . If the content of the received I O request is invalid then the program rejects the request by returning an error for example . If the content of the received I O request is valid then the program analyzes the content of the I O request. As a result of this analysis the server virtualization program identifies that the I O request is a data read request.

 Step S Next the server virtualization program acquires the server level virtual volume relating to the received request which is to be read from and the block address in the object server level virtual volume.

 Step S Next the server virtualization program refers to the server level virtual volume information and acquires the identifier of the storage level virtual volume which has been mapped to the area HL AA that includes the address of the region in the read request and the address of the area HL SA of the storage level virtual volume from the server level pool corresponding to the server level virtual volume that is to be read from. In this case the address of the region in the read request to the storage level virtual volume may have been distributed and mapped to the addresses of a plurality of storage level virtual volumes . This processing is carried out by referring to the server level pool information and the server level virtual volume information but the details of this processing have already been described in explaining the respective information.

 Step S Next the server virtualization program sends the identifier of the storage level virtual volume acquired at step S and a read request which specifies the address of the corresponding area HL SA of the area HL SA storage level virtual volume to the storage system . Data relating to the read request is received from the server virtualization program and the data is sent to the virtual machine .

 Step S A read request completion report is then notified to the virtual machine and processing is terminated.

If at step S there is no volume area HL SA allocated to the area HL AA including the address of the region in the read request then a clear value for example a string of zeros can be sent to the virtual machine .

This process is started when the server virtualization program detects the issuing of a write request in which the OS on the virtual machine specifies the device identifier for virtual machine recognition of the server level virtual volume that is to be written to and a block address and block length.

 Step S In the physical server the server virtualization program receives an I O request from the virtual machine . If the received I O request is invalid the program rejects that I O request. If the received I O request is valid then the program analyzes the content of the I O request. As a result of this analysis the server virtualization program identifies that the I O request is a data write request.

 Step S Thereupon the server virtualization program acquires the identifier of the server level virtual volume relating to the received write request and the block address in that server level virtual volume.

 Step S Next the server virtualization program refers to the server level virtual volume information identifies the server level pool corresponding to the server level virtual volume and acquires the status thereof.

 Step S The server virtualization program refers to the server level pool information identifies the storage level virtual volume corresponding to the server level pool and judges whether or not that storage level virtual volume is usable.

 Step S If the storage level virtual volume is not usable then that storage level virtual volume cannot be accessed and therefore the server virtualization program reports an I O error to the virtual machine which sent the request.

 Step S If it is judged that the storage level virtual volume is usable then the server virtualization program sends a notification that the transfer of write data is possible to the virtual machine which sent the request. Upon receiving this notification the virtual machine sends write data to the server virtualization program .

 Step S Firstly the server virtualization program refers to the server level virtual volume information and the storage level pool information and checks whether an area HL SA of the server level pool has been allocated to the area HL AA which includes the block address of the write request. 0h 

 Step S If it is judged at step S that an area has been allocated then the server virtualization program refers to the server level virtual volume information and the server level pool information and acquires the identifier for example the port number and LUN of the storage level virtual volume allocated to the area HL AA which includes the specified block address and the block address of the area HL SA of that volume.

 Step S Thereupon the server virtualization program sends the write data together with the identifier of the storage level virtual volume acquired at step S and a write request specifying the block address of the storage level virtual volume.

 Step S Upon receiving the writing completion report of the write data from the storage system the server virtualization program sends a write request completion report to the virtual machine that issued the request and then ends processing.

 Step S On the other hand if it is judged at step S that an area has not been allocated then the server virtualization program refers to the server level pool information and confirms whether there is an unallocated area HL SA in the corresponding server level pool . This step can be achieved by referring to the unallocated HL SA identifier list .

 Step S If it is judged at step S that there is an unallocated area HL SA then the server virtualization program selects the unallocated area HL SA of the storage level pool acquires the volume and block address of the selected area HL SA and allocates same to the area HL AA judged to be unallocated at step S. The process of selecting the area HL SA in this step can be made for example by extracting an unallocated area HL SA from the top of the unallocated HL SA identifier list . Furthermore in the method described in and it is possible to specify the identifier and the block address of the volume of the selected area HL SA .

 Step S The sever virtualization program then updates the server level pool information and the server level virtual volume information . More specifically the program increases the allocated capacity of the server level pool and the allocated capacity of the server level virtual volume by the capacity of the selected area HL SA . Furthermore the value in the server level area conversion information which corresponds to the area HL AA from step S is changed from unallocated to the volume and block address just acquired.

 Step S On the other hand if it is judged that there is no or insufficient unallocated area HL SA at step S then the server virtualization program changes the status of the management information of the server level pool to pool capacity insufficient .

 Step S The server virtualization program then reports the pool capacity insufficiency to the virtual machine that issued the I O request and the physical sever .

By means of the processing described above processing of a data write request by the physical server is completed.

If failure of the write request is reported by the storage system at step S then a write failure report is returned to the virtual machine that issued the I O request.

If too large a virtual volume capacity is set in respect of a limited physical storage capacity for instance the capacity of a storage level pool then it is difficult to predict the rate of consumption of the physical storage capacity and the possibility of depletion of the physical storage capacity increases. Therefore it is necessary to keep the ratio of the virtual volume capacity with respect to the physical storage capacity the leverage ratio at or below a set level.

In the processing according to a first embodiment the storage administrator sets a threshold value for the end to end capacity leverage ratio in the management server . If the end to end capacity leverage ratio exceeds the threshold value the management server detects this and indicates that the end to end capacity leverage ratio has exceeded the threshold value. By this means the storage administrator is able to identify sharp rise in the end to end capacity leverage ratio.

The processing carried out by the management program in the first embodiment is now described with reference to and .

 Step S The management program receives initial settings information which has been input by the storage administrator via the setup screen of the management program . The threshold value of the capacity leverage ratio and the interval for gathering capacity information are included in the initial settings information . The threshold value of the capacity leverage ratio is a value which indicates the tolerable upper limit of the virtual volume capacity corresponding to the physical storage capacity and the storage administrator sets this threshold value on the basis of a capacity schedule. Furthermore the interval between gathering capacity information is the interval between the times at which the management program carries out the processing described below. Moreover the storage management module receives information specifying the storage level pool from the storage administrator and on the basis of this information determines the storage level pool identifier for which the end to end capacity leverage ratio is to be calculated. The management program then stores the input threshold value for the capacity leverage ratio as the end to end capacity leverage ratio threshold value in the initial settings information and stores the interval for gathering capacity information as the information gathering interval in same. Furthermore the storage management module stores an identifier of the storage level pool determined as the object of end to end capacity leverage ratio calculation as the storage level pool identifier in the end to end capacity leverage ratio information .

 Step S The management program gathers the capacity information for the storage system and the capacity information for the physical server after the information gathering interval set by the storage administrator has elapsed in other words when the time for gathering capacity information arrives. More specifically for example the storage management module of the management program acquires the capacity information of the storage system from the storage system and the server management module of the management program gathers capacity information for the physical server . The specific method of gathering capacity information is described below.

 Step S A leverage management module of the management program carries out processing for calculating the end to end capacity leverage ratio on the basis of the acquired capacity information of the physical server and the capacity information of the storage level pool specified by the storage administrator. The details of the processing of the end to end capacity leverage ratio are described later with reference to .

 Step S The leverage management module judges whether the end to end capacity leverage ratio value in the end to end capacity leverage ratio information is higher than the end to end capacity leverage ratio threshold value in the initial settings information . If the value is judged to be higher than the threshold value then step S is executed whereas if it is not higher then step S is executed.

 Step S The leverage management module displays an alert which announces that the end to end capacity leverage ratio has risen sharply and the possibility of depletion of the physical storage capacity has increased. Moreover the leverage management module displays a chart of the value of the end to end capacity leverage ratio the storage level pool capacity the storage level virtual volume identifier and the storage level virtual volume capacity on the capacity leverage ratio display screen of the management program . The information reported on the display screen of the management program may be information other than that stated above provided that the information is able to convey to the storage administrator the fact that the possibility of depletion of the physical capacity of the storage level pool has increased.

 Step S On the other hand if the result of the comparison shows that the end to end capacity leverage ratio has not exceeded the end to end capacity leverage ratio threshold value then after the information gathering interval has elapsed the procedure returns to step S.

In the example described above the storage level pool capacity and the server level virtual volume capacity were used in calculating the end to end capacity leverage ratio but it is also possible to use other values from the tables to which these respective columns belong.

Below the details of the capacity information gathering process which is mentioned in overview in step S in will be described.

 Step A The storage management module gathers the identifier of the storage level virtual volume corresponding to the specified storage level pool identifier from the storage level pool information held by the storage system and stores the gathered identifier as the corresponding storage level virtual volume identifier in the storage level pool configuration information .

 Step B The storage management module refers to the port LUN correspondence information and acquires the port number and LUN allocated to the corresponding storage level virtual volume identifier which was gathered at step A.

 Step C The server management module gathers the identifier of the server level pool corresponding to the storage level virtual volume allocated with the port number and LUN acquired by the storage management module at step B from the server level pool information in the physical server and stores this identifier as the server level pool identifier in the server level pool configuration information . The server level pool corresponding to the storage level virtual volume means the server level pool which has been set up so that the storage level virtual volume belongs thereto.

 Step D The server management module gathers the identifiers and capacities of all of the server level virtual volumes corresponding to the gather server level pool identifier from the server level pool information in the physical server . The server management module stores the identifiers of the server level virtual volumes as the corresponding server level virtual volume identifiers in the server level pool configuration information and as the server level virtual volume identifiers in the server level virtual volume configuration information . Furthermore the respective server level virtual volume capacities are stored as the server level virtual volume capacity in the server level virtual volume configuration information .

 Step S The leverage management module sends an inquiry to the storage system about the capacity of the storage level pool corresponding to the storage level pool identifier specified in step A of step S under . The storage system returns the data in the column storage level pool capacity of the storage level pool information to the management server. The leverage management module stores the storage level pool capacity thus received as the storage level pool capacity in the storage level pool configuration information .

 Step S The leverage management module adds up the server level virtual volume capacities gathered by the server management module in step D of step S and stores the result as the corresponding server level virtual volume total capacity of the server level pool configuration information .

 Step S The leverage management module calculates the ratio of the storage level pool capacity acquired at step S to the value of the corresponding server level virtual volume total capacity calculated at step S and stores the result of this calculation as the end to end capacity leverage ratio in the end to end capacity leverage ratio information .

The processing described above is premised on gathering capacity and displaying a leverage ratio in respect of a storage level pool indicated by the administrator but it is also possible to display the leverage ratio in respect of a plurality of storage level pools which are managed by a management server. The processing in this case involves repeating the processes shown in and while the management server successively designates each one of a plurality of storage level pools as the specified storage level pool identifier .

In the computer system relating to a second embodiment of the present invention in addition to the computer system of the first embodiment if the end to end capacity leverage ratio exceeds an end to end capacity leverage ratio threshold value set by the storage administrator and it is judged that the risk of depletion of the physical storage capacity has increased then the location which is the cause of the sudden rise in the end to end capacity leverage ratio is identified and information on the identified location is displayed to the storage administrator via a management screen of the management program.

Furthermore in order to prevent depletion of the physical storage capacity the management program implements processing for automatically changing the configuration of the storage system thereby restricting the leverage ratio to a normal value which does not exceed the end to end capacity leverage ratio threshold value .

Furthermore if a setup operation is accepted by a server virtualization program which includes a callback object then that operation is interrupted the storage control program may also include a callback object described hereinafter instead of or in addition to the server virtualization program . The end to end capacity leverage ratio after execution of the accepted operation is simulated and if it is judged that the end to end capacity leverage ratio would exceed the end to end capacity leverage ratio threshold value set by the storage administrator then the management program automatically carries out configuration change processing for the storage system . By this means it is possible to achieve a structure where the end to end capacity leverage ratio does not exceed the end to end capacity leverage ratio threshold value set by the storage administrator even after the server virtualization program has executed the setup operation. When the processing described above has been carried out successfully by the management program a success notification is sent to the server virtualization program and upon receiving this notification the server virtualization program restarts the accepted setup operation. On the other hand if it is judged that the end to end capacity leverage ratio will not be restricted to the end to end capacity leverage ratio threshold value or lower even after the configuration change processing in the storage system is performed by the management program then a notification is sent to the management program indicating that there is a high risk of depletion of the physical storage capacity by the setup operation and a recommendation to halt the setup operation is issued.

If the end to end capacity leverage ratio calculated at step S in according to the first embodiment exceeds the end to end capacity leverage ratio threshold value set by the storage administrator and if it is judged that there is a high possibility of depletion of the physical storage capacity then information indicating the location that is the cause of the steep rise in the end to end capacity leverage ratio is reported to the storage administrator via the display screen.

 Step S The management program sends an inquiry to the storage system about the identifier of the storage level virtual volumes corresponding to the storage level pool in which the end to end capacity leverage ratio shows a sharp rise. Upon receiving this inquiry the storage system returns the storage level virtual volume identifiers in the storage level pool information . The management program stores the received list of the identifiers of storage level virtual volumes as the corresponding storage level virtual volume identifiers .

 Step S The management program acquires the server level pool identifier corresponding to the respective storage level virtual volumes having the acquired storage level virtual volume identifiers . More specifically for example the management program refers to the port LUN correspondence information and identifies the LUN corresponding to the identifier of the storage level virtual volume which has been registered as an internal volume ID. The management program sends an inquiry to the physical server about the identifier of the server level pool corresponding to the LUN . Upon receiving this the server virtualization program of the physical server identifies the LUN for which the inquiry has been made from the configuration storage port number LUN and returns the corresponding server level pool identifier from the server level pool information to the management server . The management program of the management server stores the received server level pool identifier as the server level pool identifier of the server level pool configuration information .

 Step S The management program sends an inquiry to the physical server about the identifiers of the server level virtual volumes corresponding to the server level pool identifier acquired at step S. Upon receiving this the server virtualization program of the physical server returns the server level virtual volume identifiers corresponding to the server level pool identifier in the server level pool information to the management server . The management program of the management server stores the received server level pool identifiers as the corresponding server level virtual volume identifiers in the server level pool configuration information .

 Step S In respect of each of the server level virtual volumes having the respective corresponding server level virtual volume identifiers acquired at step S the management program sends an inquiry to the physical server about the capacity which has been mapped to the storage area of the server level pool out of the server level virtual volume capacity . Upon receiving this the server virtualization program of the physical server refers to the server level virtual volume information and returns the server level virtual volume allocated capacity corresponding to the server level virtual volume identifier to the management server . The management program of the management server stores the received server level virtual volume allocated capacity as the server level virtual volume allocated capacity in the server level virtual volume configuration information . Moreover the management program subtracts the value of the server level virtual volume allocated capacity from the server level virtual volume capacity and stores the result as the server level virtual volume unallocated capacity .

 Step S The management program compares the respective server level virtual volume unallocated capacities corresponding to the respective server level virtual volume identifiers calculated in step S and identifies the server level virtual volume having the highest value of the compared server level virtual volume unallocated capacities as a location causing sudden rise in the end to end capacity leverage ratio . The management program displays a screen showing information such as the identifier capacity and unallocated capacity of this server level virtual volume . shows one example of this screen. According to the example in the server level virtual volume mounted on the virtual machine VM is highlighted for example surrounded by a thick oval line as a cause location. The method of indicating the cause location is not limited to the example shown in and another method of indicating same may be used.

 Step S The management program checks whether or not there is a volume that has not been registered in the pool configuration volume identifiers of the storage level pool configuration information in other words whether there is a surplus volume which does not belong to a storage level pool in the storage system .

 Step S If there is a surplus volume in the storage system which does not belong to a storage level pool then the management program automatically adds capacity to the storage level pool by newly setting the surplus volume to belong to the storage level pool having the storage level pool identifier specified in step A of step S in of the first embodiment. The capacity added to the storage level pool is set by the management program to a value whereby the end to end capacity leverage ratio is kept equal to or lower than the end to end capacity leverage ratio threshold value . The capacity added to the storage level pool may be set by the storage administrator on the management screen of the physical server .

 Step S If as a result of performing step S the end to end capacity leverage ratio is kept at or below the end to end capacity leverage ratio threshold value set by the storage administrator then the procedure advances to step S. If on the other hand the end to end capacity leverage ratio has exceeded the end to end capacity leverage ratio threshold value then the procedure advance to step S.

 Step S If the end to end capacity leverage ratio has exceeded the end to end capacity leverage ratio threshold value in step S then the management program sends an inquiry to the storage system about whether there is a storage level pool other than the storage level pool in question in the storage system . If there is another storage level pool then the management program sends the storage system an inquiry with regard to the identifier of the storage level pool other than the storage level pool in question which is the subject of the inquiry. The command control module of the storage system refers to the storage level pool information and returns a storage level pool identifier other than the identifier of the storage level pool in question to the management server . The management program of the management server stores the received storage level pool identifier as a storage level pool identifier in the storage level pool configuration information and then proceeds to step S. If there is no other storage level pool then the procedure advances to step S.

 Step S The management program refers to the end to end capacity leverage ratio information and specifies a storage level pool identifier having a low for example the lowest end to end capacity leverage ratio . Image files in the server level virtual volume are migrated between the storage level pool in question and the storage level pool selected at step S in such a manner that the end to end capacity leverage ratio of the storage level pool in question becomes equal to or lower than the end to end capacity leverage ratio threshold value . In this case the server level virtual volume to be migrated is specified as the server level virtual volume identified as a cause location of sudden rise in the end to end capacity leverage ratio at step S in . This cause location may be specified automatically as an object for migration. Provided that the server level virtual volume forming the cause location is migrated to a server level virtual volume corresponding to another storage level pool then the total capacity of the server level virtual volumes corresponding to the storage level pool which is the migration source decreases and therefore the end to end capacity leverage ratio falls. In this case desirably the end to end capacity leverage ratio relating to the other storage level pool described above does not exceed the threshold value even when the server level virtual volume forming the migration object is migrated. More specifically for example it is judged whether or not the end to end capacity leverage ratio relating to the other storage level pool exceeds the threshold value if the capacity of the server level virtual volume which is the migration object is added to the total capacity of the server level virtual volumes corresponding to the other storage level pool and if it is judged that the threshold value is not exceeded then the other storage level pool can be set as a migration destination.

 Step S If as a result of carrying out step S the end to end capacity leverage ratio of the storage level pool is kept at or below the end to end capacity leverage ratio threshold value then the procedure advances to step S. On the other hand if the end to end capacity leverage ratio of the storage level pool has exceeded the end to end capacity leverage ratio threshold value then the procedure advances to step S.

 Step S A notification is issued indicating that the end to end capacity leverage ratio has exceeded the end to end capacity leverage ratio threshold value set by the storage administrator even after carrying out step S and step S.

 Step S If the end to end capacity leverage ratio has been kept at or below the end to end capacity leverage ratio threshold value in step S or step S then this fact is reported to the storage administrator.

 Step S The management program receives initial settings information which has been input by the storage administrator via the setup screen of the management program . The threshold value of the end to end capacity leverage ratio is input to the initial settings information . The management program stores the input threshold value as the end to end capacity leverage ratio threshold value in the initial settings information .

 Step S Next a callback process is carried out. The details of the callback process are described here with reference to .

 Step S Upon accepting a setup operation event the server virtualization program sends a callback object to the management program . The callback object includes the total capacity of the server level virtual volumes before the execution of the setup operation and the contents of the setup operation.

 Step S The management program waits for a callback object to be sent from the server virtualization program and when a callback object arrives from the server virtualization program the management program receives this object.

 Step S The management program calculates the total capacity of the server level virtual volumes after executing the operation accepted by the server virtualization program by simulation on the basis of the information included in the received callback object.

 Step S The management program identifies the storage level pool corresponding to the server level virtual volumes relating to the setup operation. The concrete steps are as follows.

 Step A The server management module sends an inquiry to the physical server about the identifier of the server level pool which corresponds to the identifier of the server level virtual volumes relating to the setup operation. Upon receiving this the server virtualization program of the physical server refers to the server level virtual volume information and returns a server level pool identifier . The management program stores the server level pool identifier thus received as the corresponding server level virtual volume identifier in the server level virtual volume configuration information .

 Step B Thereupon the management program refers to the server level pool configuration information and identifies a server level pool identifier which is the same as the corresponding server level pool identifier in step A. The management program then sends an inquiry to the physical server in respect of the storage port number LUN corresponding to the identified server level pool . Upon receiving this the server virtualization program of the physical server refers to the server level pool information and returns a configuration storage port number LUN to the management server . The management program of the management server stores the received configuration storage port number LUN as the configuration storage port number LUN of the server level pool configuration information .

 Step C Thereupon the management program refers to the port LUN correspondence information and acquires the internal volume ID corresponding to the configuration storage port number LUN acquired in step B.

 Step D Thereupon the management program refers to the storage level virtual volume configuration information and identifies a storage level virtual volume having the same identifier as the internal volume ID . The management program then acquires the corresponding storage level pool identifier which corresponds to the identified storage level virtual volume .

 Step S The leverage management module of the management program carries out processing for calculating the end to end capacity leverage ratio by using the total capacity of the server level virtual volumes obtained by the callback process and the capacity information relating to the identified storage level pool . The details of the process for calculating the end to end capacity leverage ratio are described later with reference to .

 Step S The leverage management module judges whether the value of the end to end capacity leverage ratio in the end to end capacity leverage ratio information is higher than the end to end capacity leverage ratio threshold value in the initial settings information . If the value is judged to be higher than the threshold value then step S is executed whereas if it is not higher then step S is executed.

 Step S The leverage management module displays an alert which announces that the end to end capacity leverage ratio has risen sharply and the possibility of depletion of the physical storage capacity has increased. Moreover the leverage management module displays a chart of the value of the end to end capacity leverage ratio the storage level pool capacity the storage level virtual volume identifier and the storage level virtual volume capacity to the storage administrator on the capacity leverage ratio display screen of the management program . The information reported on the display screen of the management program may be information other than that stated above provided that the information is able to convey to the storage administrator the fact that the possibility of depletion of the physical capacity of the storage level pool has increased.

In the example described above the storage level pool capacity and the server level virtual volume capacity were used in calculating the end to end capacity leverage ratio but it is also possible to use other values from the tables to which these respective columns belong.

 Step S The leverage management module refers to the storage level pool configuration information and acquires the storage level pool capacity corresponding to the storage level pool identifier specified in step S.

 Step S The leverage management module calculates the ratio of the storage level pool capacity acquired at step S under to the value of the corresponding server level virtual volume total capacity calculated at step S and stores the result of this calculation as the end to end capacity leverage ratio in the end to end capacity leverage ratio information .

The processing described above is premised on gathering capacity and displaying an end to end leverage ratio in respect of a storage level pool indicated by the storage administrator but it is also possible to display the leverage ratio in respect of a plurality of storage level pools which are managed by a management server . The processing in this case involves repeating the processes shown in and while the management server successively designates each one of a plurality of storage level pools as the specified storage level pool identifier .

 Step S The management program checks whether or not there is a volume that has not been registered in the pool configuration volume identifiers in the storage level pool configuration information in other words a surplus volume which does not belong to a storage level pool in the storage system .

 Step S If there is a surplus volume in the storage system which does not belong to a storage level pool then the management program automatically adds capacity to the storage level pool by newly setting the surplus volume to belong to the storage level pool having the storage level pool identifier acquired in step S in . The capacity added to the storage level pool is set by the management program to a value whereby the end to end capacity leverage ratio is kept at or below the end to end capacity leverage ratio threshold value . The capacity added to the storage level pool may be set by the storage administrator on the management screen of the physical server .

 Step S If the end to end capacity leverage ratio has exceeded the end to end capacity leverage ratio threshold value in step S then the management program refers to the storage level pool configuration information and checks whether there is a storage level pool other than the storage level pool in question in the storage system . If there is another storage level pool then the procedure advances to step S. If there is no other storage level pool then the procedure advances to step S.

 Step S The management program refers to the end to end capacity leverage ratio information and specifies a storage level pool identifier having a low for example the lowest end to end capacity leverage ratio . Image files in the server level virtual volume are migrated between the storage level pool in question and the storage level pool selected at step S in such a manner that the end to end capacity leverage ratio of the storage level pool in question becomes equal to or lower than the end to end capacity leverage ratio threshold value . The server level virtual volume migrated in this case is specified by the management program referring to the server level virtual volume configuration information and setting the volume having the highest server level virtual volume unallocated capacity .

 Step S If as a result of carrying out step S the end to end capacity leverage ratio of the storage level pool is kept at or below the end to end capacity leverage ratio threshold value then the procedure advances to step S. On the other hand if the end to end capacity leverage ratio of the storage level pool exceeds the end to end capacity leverage ratio threshold value then the procedure advances to step S.

 Step S The management program sends the server virtualization program a recommendation to halt the setup operation because there is a high risk of depletion of the storage capacity by executing the setup operation that the server visualization program is seeking to perform. Upon receiving this the server visualization program reconfirms to the server administrator whether or not the setup operation is to be carried out.

 Step S The management program reports to the server virtualization program that the setup operation it is seeking to carry out is safe. Upon receiving this the server virtualization program restarts the setup operation which had been interrupted.

 Step S The management program reports to the storage administrator that there is a high possibility of depletion of the storage capacity.

 Step S The management program notifies the storage administrator that the possibility of depletion of the storage capacity that had increased sharply is now reduced and displays capacity information for the storage level pool and the like of which the configuration has been changed.

In the foregoing several embodiments of the present invention were described but the present invention is not limited to these embodiments and may of course be modified in various ways without departing from the essence of the invention.

For example the management server may carry out processing for making the end to end capacity leverage ratio equal to or less than a threshold value for example addition of capacity to the storage level pool or migration of a server level virtual volume without displaying the end to end capacity leverage ratio and or without displaying other management information .

Furthermore for example as shown in the management server may display a screen showing both the end to end capacity leverage ratio of the storage level pool and the free capacity ratio of the storage level pool side by side. The free capacity ratio is for example the ratio of the unallocated capacity of the storage level pool with respect to the capacity of the storage level pool the difference between the capacity of the storage level pool and the allocated capacity of the storage level pool .

Moreover for example although not shown in the drawings the management server may manage the change in the free capacity ratio of the storage level pool the free capacity ratio at respective time points and show information representing that change and calculate and display a recommended end to end capacity leverage ratio threshold value for the storage level pool.

Furthermore the end to end capacity leverage ratio threshold value may be different for each storage level pool. More specifically for example it is possible to prepare for each storage level pool an end to end capacity leverage ratio threshold value which is set on the basis of the change in the free capacity ratio of the storage level pool the speed at which the free capacity ratio decreases . Furthermore respective threshold values may be prepared for different types of leverage ratio.

The computer system relating to a third embodiment of the present invention relates to capacity management of the storage system in accordance with the deletion of a virtual machine and in particular to the releasing of the area LL SA of a volume that has become unnecessary. In addition to deleting a virtual machine for reasons relating to the end to end capacity leverage ratio according to the first and second embodiments as described below a virtual machine may also be deleted for reasons unrelated to the end to end capacity leverage ratio. It is necessary for all of the following conditions to be established.

 Reason 1 A virtual machine defined in the past is deleted as a measure for reducing the end to end capacity leverage ratio which has risen excessively.

 Reason 2 A virtual machine judged to be unnecessary is deleted in order to increase the unallocated area of the storage level pool and the server level pool.

 Reason 3 Application processing which has been executed on a virtual machine is switched to execution by a physical server due to reasons of improving reliability and processing performance etc. and the virtual machine therefore has become unnecessary.

 Reason 4 A virtual machine ceases to be used due to the person who was using the virtual machine being transferred or retiring or the end of the contract of use of the virtual machine.

The volume VOL includes one area LL SA in a volume of the same capacity as the LL SA size and the volume VOL includes two areas LL SA in a volume having twice the capacity of the LL SA size .

The volume VOL and the volume VOL are included in the storage level pool and LL VVOL to LL VVOL are defined as storage level virtual volumes using this storage level pool.

The storage level virtual volume LL VVOL is provided to the physical server as a virtual volume which has a capacity of twice the LL SA size in other words a virtual volume containing two areas LL AA .

At a certain point in time the area LL SA of the volume VOL is allocated to the first area LL AA of the storage level virtual volume LL VVOL and the area LL SA of the volume VOL is allocated to the second area LL AA .

As indicated by in the figure the server virtualization program includes the storage level virtual volume LL VVOL in the server level pool and manages the storage level virtual volume LL VVOL by dividing into units of the HL SA size . The capacity of the storage level virtual volume LL VVOL is four times the HL SA size.

The server level virtual volume HL VVOL is provided to the virtual machine VM as a virtual volume which has a capacity of three times the HL SA size in other words a virtual volume containing three areas HL AA .

The server level virtual volume HL VVOL is provided to the virtual machine VM as a virtual volume which has a capacity of three times the HL SA size in other words a virtual volume containing three areas HL AA .

At a certain point in time areas HL SA of the storage level virtual volume are allocated to all of the areas HL AA of the server level virtual volume HL VVOL .

At a certain point in time an area HL SA of the storage level virtual volume is allocated to one of the area HL AA of the server level virtual volume HL VVOL .

In response to the virtual machine deletion request the server virtualization program erases the information constituting the virtual machine VM for example the definition file memory image etc. and also releases the areas HL SA which were allocated to the server level virtual volume HL VVOL . Release of the areas HL SA by the server virtualization program means that the identifiers of the areas HL SA in question are added to the unallocated HL SA identifier list in the server level pool information and this indicates that these areas HL SA can subsequently be reallocated by another virtual machine.

The storage control program in the storage system identifies the areas LL AA of the storage level virtual volume LL VVOL corresponding to the areas HL SA that have been released and duly releases the areas LL SA that were allocated to the identified areas LL AA . Release of the areas LL SA by the storage control program means that the identifiers of the areas LL SA in question are added to the unallocated LL SA identifier list in the storage level pool information and this indicates that these areas LL SA can subsequently be reallocated by another virtual machine.

However if the HL SA area length in the server virtualization program and the LL SA area length in the storage control program are not matching then as shown in the areas LL SA of the volume are not necessarily released in accordance with the capacity of the areas HL SA released by the server virtualization program . One example of a reason why the HL SA area length in the server virtualization program and the LL SA area length in the storage control program may not be matching is described below.

Storage level virtual volumes having a larger capacity than the server level virtual volumes provided by one physical server are provided frequently and the number of physical servers accessing the storage system is high. Therefore by consequently making the LL SA area length a larger value than the HL SA area length the information volume of the storage level pool information and in particular the unallocated LL SA identifier list and the storage level virtual volume information and in particular the LL area conversion information is reduced.

Next the process for releasing an area LL SA in accordance with the deletion of a virtual machine according to a third embodiment of the present invention will be described with reference to .

 Step S The server virtualization program receives a virtual machine deletion request from the management server or other computer. The virtual machine deletion request includes the identifiers of one or more virtual machines which are objects for deletion.

 Step S The server virtualization program refers to the server level pool information and identifies the server level virtual volume corresponding to the virtual machine which is the deletion object. Furthermore the program also refers to the server level virtual volume information and identifies the areas HL SA allocated to the identified server level virtual volume. The areas HL SA which contain the settings information memory images and the like of the virtual machine forming the deletion object can be treated as the identified areas HL SA . Furthermore it is also possible for areas HL SA which are shared with another virtual machine to be omitted from the identified areas HL SA .

 Step S The server virtualization program deallocates the areas HL SA identified in step S and deletes the server level virtual volume identified at step S. A more specific description of the related information handling is given below.

The identified areas HL SA are added to the unallocated HL SA identifier list in the server level pool information and the server level pool allocated capacity is reduced by the capacity of these added areas HL SA .

The total capacity of the sever level virtual volumes in the server level pool information is reduced by the capacity of the identified sever level virtual volume needless to say this calculation alters the end to end capacity leverage ratio .

The information on the identified server level virtual volume is deleted from the server level virtual volume information .

Aside from these processes it is also possible to carry out general virtual machine deletion processing.

 Step S The server virtualization program identifies the SCSI address LUN block address and block length of the areas HL SA identified in step S and sends a region release instruction specifying the identified SCSI address to the storage system . The following modes can be envisaged for issuing a region release instruction. Firstly there is a mode where the instruction from the server virtualization program is issued to the storage system via the management server . More specifically the server virtualization program issues an API Application Programming Interface including the SCSI address of the identified areas HL SA to the management server via a LAN . Thereupon the management server issues an API containing the received SCSI address to the storage system via the LAN . Secondly there is a mode where the server virtualization program issues an API including the SCSI address of the identified areas HL SA directly to the storage system via a LAN . Thirdly there is a mode where the server virtualization program issues an API including the SCSI address of the identified areas HL SA directly to the storage system via a SAN . The destination of the API may be a specific LL VOL which is to receive the API or a LL VOL which is the object of region release. Furthermore the API may be a WRITE SAME command which is a SCSI command for repeatedly writing continuous data or an UNMAP command which is a SCSI command for reporting an unnecessary region.

 Step S The storage control program identifies the block address range on the storage level virtual volume corresponding to the SCSI address specified by the region release instruction. The program then changes the data of the identified block address range to clear values for example zeros . The process for changing to clear values is similar to the process of writing storage data to the specified block address range.

 Step S The storage control program identifies a volume area LL SA allocated to the area LL AA which is contained completely within the block address range on the storage level virtual volume specified at step S. The program refers to the storage level virtual volume information and the storage level pool information in order to make this identification.

 Step S The storage control program releases the volume area LL SA identified in step S. A more specific description of the related information handling is given below.

The identified area LL SA is added to the unallocated LL SA identifier list in the storage level pool information and the storage level pool allocated capacity is reduced by the capacity of the area LL SA which has been added to the list .

In the LL area conversion information of the storage level virtual volume information the value listed for the area LL AA to which the specified area LL SA was allocated is updated to unallocated .

The storage control program waits for the completion of the processing described above and then sends a region release instruction completion report to the physical server . The server virtualization program receives the region release instruction completion report and ends the virtual machine deletion process. The address specified by the region release instruction may be an address other than a SCSI address and the operation of updating the completely contained area LL AA to clear values in the step S may be omitted.

By repeatedly executing step S described below the storage control program attempts to release the allocation of an area LL AA comprising a block address range which is included in the block address range specified in step S but is not included in the area LL AA specified in step S.

 Step S The storage control program searches for an area LL SA having all data set to clear values in the areas LL SA allocated to the area LL AA of the storage level virtual volume and if this search is successful releases the area LL SA thus found from the area LL AA to which it was allocated. The handling of information in relation to release is similar to that of step S.

If the areas LL SA have a large size then a correspondingly long time is required for the process of checking that each individual area LL SA is set entirely to clear values and the data in the areas LL SA may be updated during this checking process. The following countermeasures can be applied in this respect.

 Countermeasure 1 It is made possible to set an additional flag which indicates checking of clear values in progress in the listed values of the LL area conversion information .

 Countermeasure 2 Before checking the clear values in step S a flag indicating checking of clear values in progress is set at a corresponding location in the list of LL area conversion information relating to the area LL AA to which the area LL SA being checked was allocated.

 Countermeasure 3 If an area LL SA having all clear values is found at step S then a release operation is carried out only if a checking of clear values in progress flag is raised for the area LL AA to which the found area LL SA was allocated and the flag is then lowered.

 Countermeasure 4 When data is written to an area LL AA for which a checking of clear values in progress flag has been raised in the storage data writing process the flag is lowered.

The processing in step S is carried out in coordination with step S in respect of the area LL SA allocated to the area LL AA comprising the block address range identified in step S which has not been set as an object for release in step S.

The foregoing is a virtual machine deletion process. As shown in since a clear value is returned if a read operation is performed to the area LL AA to which the released area LL SA was allocated then the server virtualization program is able to reuse that area subsequently without problem. Furthermore if a plurality of virtual machines are to be deleted then from the viewpoint of releasing the areas LL SA better release efficiency is achieved if the plurality of virtual machines are specified together in the deletion request. This is because if the virtual machines are each specified separately then release is attempted in step S without step S being applicable whereas if the virtual machines are specified together then the probability of completely containing the area is raised and the areas LL SA to which step S applies are increased.

The total capacity of the server level virtual volume that was used by the deleted virtual machine s .

The difference in the allocated capacity of the server level pool caused by the deletion request . Since the allocated capacity always decreases with a deletion request then this value is negative.

The difference in the allocated capacity of the storage level pool caused by the deletion request . Since the allocated capacity always decreases with a deletion request then this value is negative.

The information elements and can be found out readily in cases where the management server has issued the virtual machine deletion request. On the other hand in cases where a computer other than the management server has issued the virtual machine deletion request the virtual machine identifiers specified by the virtual machine deletion request and the reception date and time should be acquired from the physical server . The information elements to can be acquired by comparing the storage level pool configuration information the server level pool configuration information and the server level virtual volume configuration information held by the management server before and after the virtual machine deletion request. However these information elements can also be acquired by methods other than these.

In the description given above the management server creates settings information for example storage level pool configuration information storage level virtual volume configuration information port LUN correspondence information server level pool configuration information and server level virtual volume configuration information by gathering information on the settings applied in the storage system and physical server from the storage system and the physical server and the management server calculates and displays an end to end capacity leverage ratio. However if the management server establishes settings for the storage system and the physical server on the basis of setting values received from an administrator or a data source apparatus for example a portable storage medium via an input output device then the process of acquiring all or a part of the aforementioned settings information from the storage system and physical server can be omitted the settings information described above can be created or updated on the basis of these settings values and the end to end capacity leverage ratio can be calculated and displayed accordingly. In the latter case it is possible to assist the setup process performed by the administrator by displaying the end to end capacity leverage ratio before the settings based on the settings value are applied to the storage system or the physical server .

In respect of the portion which has been described using block addresses apart from an I O request from a virtual machine and an I O request sent to the storage system from a physical server it is also possible to employ addressing in other units or separate addresses using a prescribed conversion.


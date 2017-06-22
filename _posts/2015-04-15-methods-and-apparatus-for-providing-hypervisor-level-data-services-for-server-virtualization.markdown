---

title: Methods and apparatus for providing hypervisor level data services for server virtualization
abstract: A cross-host multi-hypervisor system, including a plurality of host sites, each site including at least one hypervisor, each of which includes at least one virtual server, at least one virtual disk read from and written to by the at least one virtual server, a tapping driver in communication with the at least one virtual server, which intercepts write requests made by any one of the at least one virtual server to any one of the at least one virtual disk, and a virtual data services appliance, in communication with the tapping driver, which receives the intercepted write requests from the tapping driver, and which provides data services based thereon, and a data services manager for coordinating the virtual data services appliances at the site, and a network for communicatively coupling the plurality of sites, wherein the data services managers coordinate data transfer across the plurality of sites via the network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09489272&OS=09489272&RS=09489272
owner: ZERTO LTD.
number: 09489272
owner_city: Herzilya
owner_country: IL
publication_date: 20150415
---
This application is a continuation of U.S. patent application Ser. No. 13 175 892 titled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Jul. 4 2011 which is a continuation in part of U.S. application Ser. No. 13 039 446 titled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Mar. 3 2011 which claims priority benefit of U.S. Provisional Application No. 61 314 589 titled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Mar. 17 2010. The entire contents of the foregoing applications are herein incorporated by reference.

Data center virtualization technologies are now well adopted into information technology infrastructures. As more and more applications are deployed in a virtualized infrastructure there is a growing need for recovery mechanisms to support mission critical application deployment while providing complete business continuity and disaster recovery.

Virtual servers are logical entities that run as software in a server virtualization infrastructure referred to as a hypervisor . Examples of hypervisors are VMWARE ESX manufactured by VMware Inc. of Palo Alto Calif. HyperV manufactured by Microsoft Corporation of Redmond Wash. XENSERVER manufactured by Citrix Systems Inc. of Fort Lauderdale Fla. Redhat KVM manufactured by Redhat Inc. of Raleigh N.C. and Oracle VM manufactured by Oracle Corporation of Redwood Shores Calif. A hypervisor provides storage device emulation referred to as virtual disks to virtual servers. Hypervisor implements virtual disks using back end technologies such as files on a dedicated file system or raw mapping to physical devices.

As distinct from physical servers that run on hardware virtual servers run their operating systems within an emulation layer that is provided by a hypervisor. Although virtual servers are software nevertheless they perform the same tasks as physical servers including running server applications such as database applications customer relation management applications and MICROSOFT EXCHANGE SERVER . Most applications that run on physical servers are portable to run on virtual servers. As distinct from virtual desktops that run client side applications and service individual users virtual servers run applications that service a large number of clients.

As such virtual servers depend critically on data services for their availability security mobility and compliance requirements. Data services include inter alia continuous data protection disaster recovery remote replication data security mobility and data retention and archiving policies.

Conventional replication and disaster recovery systems were not designed to deal with the demands created by the virtualization paradigm. Most conventional replication systems are not implemented at the hypervisor level with the virtual servers and virtual disks but instead are implemented at the physical disk level. As such these conventional systems are not fully virtualization aware. In turn the lack of virtualization awareness creates an operational and administrative burden and a certain degree of inflexibility.

Aspects of the present invention relate to a dedicated virtual data service appliance VDSA within a hypervisor that can provide a variety of data services. Data services provided by the VDSA include inter alia replication monitoring and quality of service. The VDSA is fully application aware.

In an embodiment of the present invention a tapping filter driver is installed within the hypervisor kernel. The tapping driver has visibility to I O requests made by virtual servers running on the hypervisor.

A VDSA runs on each physical hypervisor. The VDSA is a dedicated virtual server that provides data services however the VDSA does not necessarily reside in the actual I O data path. When a data service processes I O asynchronously the VDSA receives the data outside the data path.

Whenever a virtual server performs I O to a virtual disk the tapping driver identifies the I O requests to the virtual disk. The tapping driver copies the I O requests forwards one copy to the hypervisor s backend and forwards another copy to the VDSA.

Upon receiving an I O request the VDSA performs a set of actions to enable various data services. A first action is data analysis to analyze the data content of the I O request and to infer information regarding the virtual server s data state. E.g. the VDSA may infer the operating system level and the status of the virtual server. This information is subsequently used for reporting and policy purposes.

A second action optionally performed by the VDSA is to store each I O write request in a dedicated virtual disk for journaling. Since all I O write requests are journaled on this virtual disk the virtual disk enables recovery data services for the virtual server such as restoring the virtual server to an historical image.

A third action optionally performed by the VDSA is to send I O write requests to different VDSAs residing on hypervisors located at different locations thus enabling disaster recovery data services.

The hypervisor architecture of the present invention scales to multiple host sites each of which hosts multiple hypervisors. The scaling flexibly allows for different numbers of hypervisors at different sites and different numbers of virtual services and virtual disks within different hypervisors. Each hypervisor includes a VDSA and each site includes a data services manager to coordinate the VSDA s at the site and across other sites.

Embodiments of the present invention enable flexibly designating one or more virtual servers within one or more hypervisors at a site as being a virtual protection group and flexibly designating one or more hypervisors or alternatively one or more virtual servers within one or more hypervisors at another site as being a replication target for the virtual protection group. Write order fidelity is maintained for virtual protection groups. A site may comprise any number of source and target virtual protection groups. A virtual protection group may have more than one replication target. The number of hypervisors and virtual servers within a virtual protection group and its replication target are not required to be the same.

There is thus provided in accordance with an embodiment of the present invention a cross host multi hypervisor system including a plurality of host sites each site including at least one hypervisor each of which includes at least one virtual server at least one virtual disk that is read from and written to by the at least one virtual server a tapping driver in communication with the at least one virtual server which intercepts write requests made by any one of the at least one virtual server to any one of the at least one virtual disk and a virtual data services appliance in communication with the tapping driver which receives the intercepted write requests from the tapping driver and which provides data services based thereon and a data services manager for coordinating the virtual data services appliances at the site and a network for communicatively coupling the plurality of sites wherein the data services managers coordinate data transfer across the plurality of sites via the network.

Appendix I is an application programming interface for virtual replication site controller web services in accordance with an embodiment of the present invention 

Appendix II is an application programming interface for virtual replication host controller web services in accordance with an embodiment of the present invention 

Appendix III is an application programming interface for virtual replication protection group controller web services in accordance with an embodiment of the present invention 

Appendix IV is an application programming interface for virtual replication command tracker web services in accordance with an embodiment of the present invention and

Appendix V is an application programming interface for virtual replication log collector web services in accordance with an embodiment of the present invention.

Aspects of the present invention relate to a dedicated virtual data services appliance VDSA within a hypervisor which is used to provide a variety of hypervisor data services. Data services provided by a VDSA include inter alia replication monitoring and quality of service.

Reference is made to which is a simplified block diagram of a hypervisor architecture that includes a tapping driver and a VDSA in accordance with an embodiment of the present invention. Shown in is a hypervisor with three virtual servers three virtual disks an I O backend and a physical storage array . Hypervisor uses a single physical server but runs multiple virtual servers . Virtual disks are a storage emulation layer that provide storage for virtual servers . Virtual disks are implemented by hypervisor via I O backend which connects to physical disk .

Hypervisor also includes a tapping driver installed within the hypervisor kernel. As shown in tapping driver resides in a software layer between virtual servers and virtual disks . As such tapping driver is able to access I O requests performed by virtual servers on virtual disks . Tapping driver has visibility to I O requests made by virtual servers .

Hypervisor also includes a VDSA . In accordance with an embodiment of the present invention a VDSA runs on a separate virtual server within each physical hypervisor. VDSA is a dedicated virtual server that provides data services via one or more data services engines . However VDSA does not reside in the actual I O data path between I O backend and physical disk . Instead VDSA resides in a virtual I O data path.

Whenever a virtual server performs I O on a virtual disk tapping driver identifies the I O requests that the virtual server makes. Tapping driver copies the I O requests forwards one copy via the conventional path to I O backend and forwards another copy to VDSA . In turn VDSA enables the one or more data services engines to provide data services based on these I O requests.

Reference is made to which is a simplified data flow chart for a VDSA in accordance with an embodiment of the present invention. Shown in are an I O receiver a hash generator a TCP transmitter a data analyzer and reporter a journal manager and a remote VDSA . Remote VDSA resides on different physical hardware at a possibly different location.

As shown in I O receiver receives an intercepted I O request from tapping driver . VDSA makes up to three copies of the received I O requests in order to perform a set of actions which enable the one or more data services engines to provide various services.

A first copy is stored in persistent storage and used to provide continuous data protection. Specifically VDSA sends the first copy to journal manager for storage in a dedicated virtual disk . Since all I O requests are journaled on virtual disk journal manager provides recovery data services for virtual servers such as restoring virtual servers to an historical image. In order to conserve disk space hash generator derives a one way hash from the I O requests. Use of a hash ensures that only a single copy of any I O request data is stored on disk.

An optional second copy is used for disaster recovery. It is sent via TCP transmitter to remote VDSA . As such access to all data is ensured even when the production hardware is not available thus enabling disaster recovery data services.

An optional third copy is sent to data analyzer and reporter which generates a report with information about the content of the data. Data analyzer and reporter analyzes data content of the I O requests and infers information regarding the data state of virtual servers . E.g. data analyzer and reporter may infer the operating system level and the status of a virtual server .

Reference is made to which is a simplified block diagram of a virtual replication system in accordance with an embodiment of the present invention. Shown in is a protected site designated Site A and a recovery site designated Site B. Site A includes a hypervisor A with three virtual servers A A and A and a VDSA A. Site A includes two physical disks A and A . Site B includes a hypervisor B with a VDSA B. Site B includes two physical disks B and B . All or some of virtual servers A A and A may be designated as protected. Once a virtual server is designated as protected all changes made on the virtual server are replicated at the recovery site.

In accordance with an embodiment of the present invention every write command from a protected virtual server in hypervisor A is intercepted by tapping driver and sent asynchronously by VDSA A to VDSA B for replication via a wide area network WAN while the write command continues to be processed by the protected server.

At Site B the write command is passed to a journal manager for journaling on a Site B virtual disk . After every few seconds a checkpoint is written to the Site B journal and during a recovery one of the checkpoints may be selected for recovering to that point. Additionally checkpoints may be manually added to the Site B journal by an administrator along with a description of the checkpoint. E.g. a checkpoint may be added immediately prior to an event taking place that may result in the need to perform a recovery such as a planned switch over to an emergency generator.

In addition to write commands being written to the Site B journal mirrors B B and B of the respective protected virtual servers A A and A at Site A are created at Site B. The mirrors at Site B are updated at each checkpoint so that they are mirrors of the corresponding virtual servers at Site A at the point of the last checkpoint. During a failover an administrator can specify that he wants to recover the virtual servers using the latest data sent from the Site A. Alternatively the administrator can specify an earlier checkpoint in which case the mirrors on the virtual servers B B and B are rolled back to the earlier checkpoint and then the virtual servers are recovered to Site B. As such the administrator can recover the environment to the point before any corruption such as a crash or a virus occurred and ignore the write commands in the journal that were corrupted.

VDSAs A and B ensure write order fidelity i.e. data at Site B is maintained in the same sequence as it was written at Site A. Write commands are kept in sequence by assigning a timestamp or a sequence number to each write at Site A. The write commands are sequenced at Site A then transmitted to Site B asynchronously then reordered at Site B to the proper time sequence and then written to the Site B journal.

The journal file is cyclic i.e. after a pre designated time period the earliest entries in the journal are overwritten by the newest entries.

It will be appreciated by those skilled in the art that the virtual replication appliance of the present invention operates at the hypervisor level and thus obviates the need to consider physical disks. In distinction conventional replication systems operate at the physical disk level. Embodiments of the present invention recover write commands at the application level. Conventional replication systems recover write commands at the SCSI level. As such conventional replication systems are not fully application aware whereas embodiment of the present invention are full application aware and replicate write commands from an application in a consistent manner.

As indicated hereinabove the architecture of scales to multiple sites having multiple hypervisors. Reference is made to which is a simplified block diagram of a cross host multiple hypervisor system that includes data services managers for multiple sites that have multiple hypervisors in accordance with an embodiment of the present invention. The architecture of includes three sites designated Site A Site B and Site C the three sites being communicatively coupled via a network . Each site includes one or more hypervisors . Specifically Site A includes three hypervisors A A and A Site B includes two hypervisors B and B and Site C includes one hypervisor C . The sites have respective one or more physical disks A B and C.

The hypervisors are shown in system with their respective VDSA s A A . . . and the other components of the hypervisors such as the virtual servers and virtual disks are not shown for the sake of clarity. An example system with virtual servers is shown in and described hereinbelow.

The sites include respective data services managers A B and C that coordinate hypervisors in the sites and coordinate hypervisors across the sites.

The system of may be used for data replication whereby data at one site is replicated at one or more other sites for protection. The solid communication lines in are used for in site traffic the dashed communication lines are used for replication traffic between sites and the dotted communication lines are used for control traffic between data services managers.

Data services managers A B and C are control elements. The data services managers at each site communicate with one another to coordinate state and instructions. The data services managers track the hypervisors in the environment and track health and status of the VDSAs A A . . . .

It will be appreciated by those skilled in the art that the environment shown in may be re configured by moving one or more virtual servers from one hypervisor to another by moving one or more virtual disks from one hypervisor to another and by adding one or more additional virtual servers to a hypervisor .

In accordance with an embodiment of the present invention the data services managers enable designating groups of specific virtual servers referred to as virtual protection groups to be protected. For virtual protection groups write order fidelity is maintained. The data services managers enable designating a replication target for each virtual protection group i.e. one or more sites and one or more hypervisors in the one or more sites at which the virtual protection group is replicated. A virtual protection group may have more than one replication target. The number of hypervisors and virtual servers within a virtual protection group and its replication target are not required to be the same.

Reference is made to which is a user interface screenshot of bi directional replication of virtual protection groups in accordance with an embodiment of the present invention. Shown in are virtual protection groups Exchange WebApp Dummy R1 Windows 2003 and Dummies L . Arrows indicate direction of replication.

Reference is made to which is a user interface screenshot of assignment of a replication target for a virtual protection group in accordance with an embodiment of the present invention. Shown in is an entry for designating a recovery host and an entry for designating a recovery datastore for virtual protection group Windows 2003 of . Respective source and target datastores SAN ZeRTO 30 A and datastore1 B are shown as being paired.

More generally the recovery host may be assigned to a cluster instead of to a single hypervisor and the recovery datastore may be assigned to a pool of resources instead of to a single datastore. Such assignments are of particular advantage in providing the capability to recover data in an enterprise internal cloud that includes clusters and resource pools instead of using dedicated resources for recovery.

The data services managers synchronize site topology information. As such a target site s hypervisors and datastores may be configured from a source site.

Virtual protection groups enable protection of applications that run on multiple virtual servers and disks as a single unit. E.g. an application that runs on virtual servers many require a web server and a database each of which run on a different virtual server than the virtual server that runs the application. These virtual servers may be bundled together using a virtual protection group.

Referring back to data services managers A B and C monitor changes in the environment and automatically update virtual protection group settings accordingly. Such changes in the environment include inter alia moving a virtual server from one hypervisor to another moving a virtual disk from one hypervisor to another and adding a virtual server to a hypervisor .

For each virtual server and its target host each VDSA A A . . . replicates IOs to its corresponding replication target. The VDSA can replicate all virtual servers to the same hypervisor or to different hypervisors. Each VDSA maintains write order fidelity for the IOs passing through it and the data services manager coordinates the writes among the VDSAs.

Since the replication target hypervisor for each virtual server in a virtual protection group may be specified arbitrarily all virtual servers in the virtual protection group may be replicated at a single hypervisor or at multiple hypervisors. Moreover the virtual servers in the source site may migrate across hosts during replication and the data services manager tracks the migration and accounts for it seamlessly.

Reference is made to which is an example an environment for system in accordance with an embodiment of the present invention. As shown in system includes the following components.

As further shown in system includes the following virtual protection groups. Each virtual protection group is shown with a different hatching for clarity.

As such it will be appreciated by those skilled in the art that the hypervisor architecture of scales to multiple host sites each of which hosts multiple hypervisors. The scaling flexibly allows for different numbers of hypervisors at different sites and different numbers of virtual services and virtual disks within different hypervisors.

The present invention may be implemented through an application programming interface API exposed as web service operations. Reference is made to Appendices I V which define an API for virtual replication web services in accordance with an embodiment of the present invention.

In the foregoing specification the invention has been described with reference to specific exemplary embodiments thereof. It will however be evident that various modifications and changes may be made to the specific exemplary embodiments without departing from the broader spirit and scope of the invention as set forth in the appended claims. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.


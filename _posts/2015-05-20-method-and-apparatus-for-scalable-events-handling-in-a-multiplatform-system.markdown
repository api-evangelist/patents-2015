---

title: Method and apparatus for scalable events handling in a multi-platform system
abstract: A method for event handling in a multi-platform system, comprising acquiring an event of a file access from the multi-platform system, processing the event taking account of an auxiliary data to decide an action and activating the action, and an apparatus for performing the same.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09514144&OS=09514144&RS=09514144
owner: VARONIS SYSTEMS, INC.
number: 09514144
owner_city: 
owner_country: US
publication_date: 20150520
---
The present application is a continuation application of U.S. application Ser. No. 13 235 526 filed on Sep. 19 2011 and published as US 2013 0074100.

The present disclosure generally relates to file access events and more specifically to handling file access events in a multi platform system.

Distributed multi platform computerized systems are in common use. For example in banking investment houses large corporations or others such as the military.

Such systems may include for example from tens of platforms to thousands of platforms with a rate of millions or about a billion file accesses per hour.

One exemplary embodiment of the disclosed subject matter is a system for event handling in a multi platform system comprising a process installed in platforms of the multi platform system for intercepting events of file access in the multi platform system and an at least one server connected to an at least one platform the at least one server configured for acquiring events intercepted by the process and for processing the events by an at least one rule for deciding an action responsive to the event while taking into account an auxiliary data that is provided separately from event acquisition

Another exemplary embodiment of the disclosed subject matter is a method for event handling in a multi platform system comprising acquiring an event of a file access in the multi platform system processing the event taking account of an auxiliary data to decide or determine an action and optionally activating the action.

In the context of the present disclosure without limiting a platform implies a computer having data resources such as folders or files possibly shared with another computer wherein different platforms may be of different apparatus and or software and possibly with different organization of the data objects or resources. For example platforms may be different computer types running under different operating systems and using different file systems.

Generally a platform is connected to one or more other platforms forming various connection patterns such as interconnected clusters of platforms where the clusters are linked therebetween.

In the context of the present disclosure without limiting and unless otherwise specified a server implies a computer additional or complementary to the multi platform system.

In the context of the present disclosure without limiting and unless otherwise specified a database implies any data structure additional or complementary to the data resources or objects of the multi platform system not precluding a conventional database of the art nor lookup tables.

For brevity and clarity and without limiting in the present disclosure a reference to an operating system implies any software operative to control functions of a computer and particularly controlling access the file system such as Windows Linux MacOS or others.

For brevity and clarity and without limiting in the present disclosure a reference to a file system implies any repository or organization of data objects or data resources in a platform or shared among a plurality of platforms. For example Microsoft s NTFS of FAT32 Apple s HFS IBM s LTFS Sun Microsystems s ZFS Oracle s ACFS Microsoft SharePoint or any other organization such as emails in mail server as for example Microsoft s Exchange or any other organization such as Joliet ISO 9660 1988 .

In the context of the present disclosure without limiting referring to a file implies any data object or data resource of a file system for example attachment within an email or a link to a web page or an ordinary file as used in the art.

In the context of the present disclosure without limiting an event is referred to as used in the art of computers and software such as an interrupt a signal or a procedure call generally asynchronous yet without precluding a synchronous event.

For brevity and clarity and without limiting in the present disclosure a distributed multi platform computerized system is referred to as a multi platform system.

One technical problem dealt by the disclosed subject matter is responding in real time to intercepted file access events in a multi platform system.

Another technical problem dealt by the disclosed subject matter is condensing and reducing the amount of data related to intercepted file access events in a multi platform system.

Yet another technical problem dealt by the disclosed subject matter is handling intercepted file access events in a multi platform system in or according to an extended or expansive context beyond the event per se.

One technical solution according to the disclosed subject matter is linking or coupling to each platform or a part thereof a process that intercepts file access events. Information of or related to events in one or in a group of platforms is monitored by a server also referred to as a probe connected to one platform or to each of the platforms in the group.

The information of the events is handled by the probe thereby relieving the platform of the overload of processing the events information thereby enabling to handle and respond in real time to the events in the multi platform system.

According to the load or expected load of handling the intercepted events in real time additional probes are connected to the platforms reducing the burden on each probe and balancing the processing loads thereby providing a scalable scheme for load balancing of responding to real time events in a multi platform system.

Another technical solution according to the disclosed subject matter is a process operating in the probes or in apparatus linked to the probes that in conjunction with a data structure such as table or database discard redundant data of intercepted events and or abbreviate redundant data of intercepted events in a related code.

By way of example if a user opened a particular object such as a file or a folder several times within a time interval instead of recording each individual access only the time interval is recorded possibly with the number of access within that interval.

By way of another example an accessed object is assigned a unique code thereby avoiding repeatedly recording the full path string of the object.

By way of yet another example instead of recording a user name an abbreviated unique code for that user name is used thereby avoiding repeatedly recording the full name of that user.

Yet another technical solution according to the disclosed subject matter is one or more data structures such as a database stored in a server connected to the probes and or in the probes the one or more data structures holding auxiliary or extraneous or disjoint information with respect to the events.

Taking into account auxiliary information the event may be handled and or analyzed in a wider context of the multi platform system or beyond.

By way of example an object such as a folder may be noted in the data structure as being of sensitive data to the organization. When that object is accessed an event is generated in a platform storing that object and the event is monitored or captured by a probe.

The data of the event that includes the object path or code thereof is checked with respect to the data in the data structure and in case the object is recognized as sensitive further actions may be performed.

The data in the data structure may be predefined or may be determined or modified according to events or other operations in the multi platform system. Thus the auxiliary or extraneous information may be incrementally updated in the course of operation of the multi platform system. For example if a particular user is repeatedly accessing a particular file within a certain time the information is updated to that effect in the data structure. Consecutively upon further event of access to that file by that user as captured by a probe the information in the data structure is consulted and further access to that file may be prevented from that user.

A potential technical effect of the disclosed subject matter is a multi platform system that handles in real time file access events within an extended context beyond the data included in the events.

As used herein the term real time generally implies a sufficiently fast operation responsive to an event accomplished before another event occurs.

A general non limiting overview of practicing the present disclosure is presented below. The overview outlines exemplary practice of embodiments of the present disclosure providing a constructive basis for variant and or alternative and or divergent embodiments some of which are subsequently described.

Operations on a file of a file system such as a creation or deletion of a file or reading from or writing into a file and in some cases modifying attributes of a file such as read only are generally well defined procedures of an operating system and or a file system. Such operations on a file may be tracked for example by services of the operating system or by using API Application Programming Interface or by hooking onto the file operation procedure or any other method offered by the operating system and or the file system. Obtaining information on the occurrence and nature of a file operation is collectively referred to herein as file operation capturing or for brevity as capturing or variants thereof.

An event may be generated by capturing the file operation. In some cases the operating system and or the file system generate the events. In many cases and or in some embodiments of the present disclosure an event includes or is accompanied by or supplied with data referred to as the event data. For clarity and brevity the event data is also implied when an event is referred to.

The event data comprise items or indications or references thereof such as the accessed file with a partial of a full path referred to as file path the user who accessed the file type of the event according to the performed operation such as open or delete the time of the operations referred to as a time stamp the location or platform where the event originated or any other data associated with the event such as the destination of the event in case of copying or moving or any combination thereof.

In some embodiments a platform comprises or is linked to or is coupled with a process that captures the file operations and generates events or alternatively the process intercepts events generated by the operating system and or file system. The process is also referred to herein as a driver .

The events are acquired from one or more drivers by a server that operates as an agent for the multi platform system with regard to events the server or agent are also referred to herein as a probe . In some embodiments the probe inquires a driver of events or alternatively the driver sends events to the probe. Optionally or alternatively a combination of inquiry and receiving of events by the probe is used.

In some embodiments probe may be connected to one platform or to a plurality of platforms. In some embodiments a plurality of probes is used each probe connected to a different plurality of platforms optionally with connections redundancy.

In some embodiments the probe stores the event data in a database according to a storage regime such as responsive to events or periodically such as once an hour or a day. In some embodiments all the probes are connected to the same database. Optionally or alternatively a plurality of databases is used optionally accessible by all the probes.

In some embodiments the database comprises information about the files or other information regarding the multi platform system or any other auxiliary or disjoint information with respect to the events. Optionally the database is supplied with information gathered during the operation of the multi platform system and or by the probe. For example file permissions classifications of the files such as sensitivity of groups or identity of users who accessed certain files and in what rate or within what time interval or removal or introductions of users to the multi platform system.

Upon acquiring an event the probe checks the event data possibly also with respect to the data in the database and performs one or more operations according to one or more rules resembling to a limited extent mailbox rules of email clients of the art.

For example a rule may read like if a deleted file is marked as sensitive then generate an alert consequently suspending the operation unless acknowledged by an authorized user.

It is noted that using a driver and further processing events by a probe enables at least potentially minimal or negligible intervention in the operation of the multi platform system.

Multi platform system comprises a plurality of instances of a platform representing any number of platform as indicated by broken lines and .

Platform comprises an operating system and a file system or to that effect any structure and or mechanism for holding managing and accessing data objects.

The event handling system comprises a server as a probe connected to one or more platforms such as platform representing any number of platform connected to probe as indicated by dotted lines . The illustrated two instances of probe represent any number of probes such as probe connected to any number of platforms such as platform as indicated by a dashed line .

Probe comprises or coupled with or linked to one or more rules collectively referred to as rules . Rules use events or event data or part thereof as parameters or arguments for logic or a procedure of rules according to which an action is decided or determined.

Platform comprises a process denoted as a driver that generates and or intercepts file access events in platform generally and without limiting referred to as intercepting . The events are provided to and or acquired by probe .

It is noted that driver is not necessarily installed in or coupled with each platform but rather driver is installed in or coupled with any platform having accessible files or for which file access events are being handled.

In some embodiments responsive to obtaining an event probe executes the rules using the obtained event as parameter for the procedural logic of rules . In case an action is decided by rules probe performs the action or invokes or initiates in or delegates the decided action to other components of event handling system or multi platform system .

In some embodiments using probe to process and handle events reduces processing load on multi platform system and or minimizes or reduces intervention with the operation of multi platform system where driver non intrusively captures event of file access in multi platform system .

In some embodiments probe obtains events from platform via another component or components such as proxy servers that reduce communication load in event handling system and or reduce processing load by pre processing such as filtering events before reaching probe .

In some embodiments probe stores the events in a database enabling further reference and or analysis thereof. Optionally probe stores the events via a proxy such as a server and or via intermediate storage such as a cache.

In some embodiments database is implemented on a server or any other apparatus where database represents any kind of storage repository or organization possibly split or distributed in a plurality of servers or apparatuses. Thus in some embodiments events are stored in a structure or apparatus different or separate from where auxiliary data further explained below is stored. Yet for brevity and clarity either storage apparatus or structures are referred to as database .

In some embodiments the events are stored using condensed forms and or structures as described below.

It is noted that rules are not necessarily stored in probe and alternatively or additionally rules may be stored in another apparatus such as a server linked to probe .

It is noted that driver is not necessarily stored in platform and alternatively or additionally driver is stored in another apparatus such as a server linked to platform .

It is noted that probe is not necessarily a separate apparatus from platform and alternatively or additionally probe is comprised in platform such as using an additional processor and memory thereof.

In some embodiments in addition to event data rules use additional information for deciding an action. The additional information also referred to as auxiliary data is used in conjunction with the event data or as reference thereby affecting or enabling to affect the procedural course of the logic or procedures of rules and or the decided actions. In some embodiments the auxiliary data is stored in database and or in any apparatus or structure represented by database .

In some embodiments responsive to obtaining an event probe queries at database for auxiliary data related to the event and in case the auxiliary data is present in database probe retrieves the auxiliary data and incorporates the auxiliary data with rules . Optionally or alternatively probe retrieves optionally repeatedly or periodically auxiliary data from database and stores data according to a regime such as according to frequency of repeated events. In some embodiments probe caches data optionally keeping cached auxiliary data related to frequent events.

In some embodiments the auxiliary data comprise information regarding files in the file system of a platform or file systems of a plurality of platforms.

For example the auxiliary data may include permissions to access a file system or part thereof memberships in groups related to file system or part thereof classification of files or group of files classified such a sensitive or public tagging of files for any purpose or history or recommendations designated owners of files or group thereof or any other data such as sandbox results that is what if results or a combination thereof.

In some embodiments some or part of the auxiliary data is preset before the operation of multi platform system and or event handling system .

In some embodiments the auxiliary data or part thereof is provided from the operation of multi platform system as schematically illustrated by auxiliary data and dashed arrow . For example auditing or collecting history of activities of users with respect to files to generate permissions or input by users.

In some embodiments the auxiliary data or part thereof is provided by operations of event handling system such as records of events and or results of rules provided from probe .

Accordingly in some embodiments database is incrementally supplied or updated with auxiliary data during the operation of multi platform system and or event handling system .

In some embodiments auxiliary data related to an event comprises at least a part of data that is related to or associated with a file or group of files such as a file name or location of destination that belongs to or relates to or associated with the file.

It is emphasized that in some embodiments the events are stored in database by probe separately from the auxiliary data.

In some embodiments probe is connected to and communicates with database via a proxy such as a server optionally the proxy caches some of the events data from probe and or auxiliary data from database .

It is noted that using probe at least potentially facilitates rapid response or real time response to events since multi platform system is relieved from processing the events.

Having to respond to events and analyze and or process the events such as by rules should in principle or theory involve repeatedly and seemingly redundant reference to and or storage of items such as user names files paths or location identifications such as IP or UNC paths.

Such redundant operations could adversely affect the response time and or may necessitate additional processors such as probe in order to respond and process events in real time.

Therefore and possibly for other reasons in some embodiments items of multi platform system or and optionally of event handling system are expressed or coded in a short forms or codes. In some embodiments only items that are repeatedly referenced and or determined to be repeatedly referenced are coded. Coding items is also referred to herein as normalization or a variant thereof.

The codes are stored in a structure or structures such as lookup tables optionally using or assisted by mechanisms for sufficiently rapid retrieval such as binary trees or hash tables.

Thus in some embodiments instead of acquiring and or storing or recording event data with full user name or full file paths of the accessed file or destination or locations UNC Universal Naming Convention and or the like only the respective codes are recorded thereby saving operation times and also storage overhead such as in multiple access to a storage and generally saving storage space.

The lookup tables comprise strings indicated as for file path location and user names respectively and associated with codes as binary numbers shown for clarity as decimal numbers. The codes are used to normalize an event record using codes instead of the respective strings.

Furthermore and or optionally or alternatively in some embodiments similar or redundant information is further reduced by condensing the information in a structure that reflects the repeated or similar information an approach also referred to as aggregation.

For example a file F accessed N times by a user U within between time T and time T is recorded only once as N accesses in time interval T T. Moreover file F and user U are optionally recorded by respective codes thereof rather than full paths and names strings.

As another example accessing records R R and R in a database DB by a user U is not recorded three times but rather as DB and R R R and user U with optional time interval and optionally DB and user U are recorded as the respective codes thereof.

In some embodiments normalization data and structures are stored in database . Optionally or alternatively normalization data and structures or part thereof is stored in auxiliary apparatus or storage such as a proxy cache in probe for rapid reference.

In some embodiments the events are stored in aggregated forms in database separately of the auxiliary data and or in combination with or the auxiliary data or part thereof.

Using normalization and or aggregation at least potentially reduces processing such as applying rules and or storage in database and or communication for acquiring the events from driver thereby facilitating at least potentially to respond to and handle the events in real time.

In some embodiments the auxiliary data is also normalized in codes or formed in aggregations further decreasing the response and or processing of events enabling to reduce the number of probe at least potentially.

In some embodiments rules operate as if then else construct. Optionally or additionally rules operate according to other constructs such as multi branch or as inference machine.

In some embodiments rules stored in probe are executed in parallel or multi tasking or multi threading optionally processing a plurality of events are processed at least partially in parallel.

In some embodiments rules are arranged and or operate according to one or more precedence criteria. For example events from a user input are processed in precedence to events from a background database.

In some embodiments the decisions and or derived actions of rules respective to an event are divided into three categories namely filter alert and workflow wherein the actions are optionally invoked or initiated in real time responsive to an event or designed therefore.

In a filter action the events are dropped or ignored thereby saving processing time and storage space. For example events related to temporary or trivial files or events related to backup operations.

In an alert action a message and or a signal is sent to an appropriate user and or destinations such as by an email or by storing in an event log. For example announcing to a supervisor user when someone tries to access a sensitive file or when a user that is a member of a particular group tries to access files or a different group.

In a workflow action operation and or operations are invoked or initiated. The operations may be user defined or otherwise defined and or based on a computerized or software engine that can be extended or modified such as by API s or other system calls. For example blocking permission to a user that deletes multiple files within a determined or a preset time interval.

At an event from a distributed multi platform computerized system such as multi platform system is acquired or received such as in probe the event intercepted and or generated from the multi platform system by way of driver .

In some embodiments the events implying also data thereof are acquired in a condensed form such as a normalized form by codes.

At auxiliary data or additional data disjoint of the event is retrieved such as from database or from any source optionally from a cache.

At the event is processes such as by rules in view of or by taking into account the auxiliary data optionally determining on one or more actions.

At the determined action is initiated or carried out optionally by an apparatus such as probe or by another apparatus optionally comprised in multi platform system .

At the events in some embodiments implying also data thereof is optionally stored such as in database optionally in a condensed form by using codes and or aggregations.

In some embodiments storing is carried out before and or after processing or activation of the action optionally performed based on a periodic regime or responsive to an event of a plurality of events.

The operations and or order of the operations outlined above may be modified. For example the auxiliary data may have been stored or cached together with the processing codes such as rules so that no further retrieval of the auxiliary data is performed.

Two non limiting examples with respect to a distributed multi platform computerized system of a company such as multi platform system as handled by event handling apparatus such as event handling system are described below.

In one scenario the company receives information that one of the company s employees is about to leave the company. Asserting that the employee has access to sensitive information about the company the administrator of the multi platform system sets a rule such as in rules so that whenever the employee copies data that was flagged as sensitive alert will is sent allowing spotting the employee and or preventing copying the data by the employee.

In another scenario in order to minimize the damage employees can cause to publicly shared data of the company the administrator of the multi platform system sets a rule such as in rules that if a user deleted more than three files within a minute on a folder that has permissions to everyone this user s permissions will be removed ensuring that the user will need to ask for access permissions afterwards.

It is noted that the techniques of the present disclosure is not limited to file access events but in some embodiments may be applied to other events or processes such as input output events or communications between processes or apparatuses.

It is thus provided in accordance with the disclosed subject matter is a system for event handling in a multi platform system comprising a process installed in platforms of the multi platform system for intercepting events of file access in the multi platform system and an at least one server connected to an at least one platform the at least one server configured for acquiring events intercepted by the process and for processing the events by an at least one rule for deciding an action responsive to the event while taking into account an auxiliary data. In some embodiments the auxiliary data is provided separately from acquisition of the events.

In some embodiments the auxiliary data comprises at least one of a preset data related to the multi platform system a data accumulated responsive to the operation of the multi platform system or an updated data responsive to the operation of the multi platform system or any combination thereof.

In some embodiments the database is stored on an at least one apparatus separate from the at least one server and from the multi platform system.

In some embodiments the at least one server is configured to at least one of acquire the events in a condensed form process the events in a condensed form store the events in a condensed form or any combination thereof thereby facilitating real time response to the events.

In some embodiments the condensed form comprises at least one of coded event data or aggregated event data or a combination thereof.

In some embodiments the at least one rule is stored in the at least one server wherein in some embodiments the at least one server is configured to initiate an action decided by the at least one rule.

In some embodiments the process is installed on each platform of the multi platform system having accessible files.

It is thus further provided in accordance with the disclosed subject matter is a method for event handling in a multi platform system comprising acquiring an event of a file access from the multi platform system processing the event taking account of an auxiliary data to decide an action and activating the action.

In some embodiments processing the event comprises using an at least one rule wherein in some embodiments the at least one rule comprises a plurality of rules.

In some embodiments the auxiliary data comprises at least one of a preset data related to the multi platform system a data accumulated responsive to the operation of the multi platform system or an updated data responsive to the operation of the multi platform system or any combination thereof.

In some embodiments acquiring an event is carried out on an at least server connected to and separate from the multi platform system.

In some embodiments the at least one server is configured to at least one of acquire the events in a condensed form process the events in a condensed form store the events in a condensed form or any combination thereof thereby facilitating real time response to the events.

In some embodiments the condensed form comprises at least one of coded event data or aggregated event data or a combination thereof.

The terms processor or computer or server or system thereof are used herein as ordinary context of the art such as a general purpose processor or a micro processor RISC processor or DSP possibly comprising additional elements such as memory or communication ports. Optionally or additionally the terms processor or computer or derivatives thereof denote an apparatus that is capable of carrying out a provided or an incorporated program and or is capable to controlling and or accessing data storage apparatus and or other apparatus such as input and output ports. The terms processor or computer denote also a plurality of processors or computers connected and or linked and or otherwise communicating possibly sharing one or more other resources such as a memory.

The terms software program software procedure or procedure or software code or code may be used interchangeably according to the context thereof and denote one or more instructions or directives or circuitry for performing a sequence of operations that generally represent an algorithm and or other process or method. The program is stored in or on a medium such as RAM ROM or disk or embedded in a circuitry accessible and executable by an apparatus such as a processor or other circuitry.

The processor and program may constitute the same apparatus at least partially such as an array of electronic gates such as FPGA or ASIC designed to perform a programmed sequence of operations optionally comprising or linked with a processor or other circuitry.

The term computerized apparatus or a similar one denotes an apparatus having one or more processors operable or operating according to a program.

The term configuring for a objective or a variation thereof implies using a software and or electronic circuit designed and or operable or operative to achieve the objective.

As used herein without limiting a module represents a part of a system such as a part program operating together with other parts on the same unit or a program component operating on different unit and a process represents a collection of operations for achieving a certain outcome.

The flowchart and block diagrams illustrate an architecture a functionality or an operation of possible implementations of systems methods and computer program products according to various embodiments of the present disclosed subject matter. In this regard each block in the flowchart or block diagrams may represent a module segment or portion of program code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations illustrated operations may occur in deferent order or as concurrent operations instead of sequential operations to achieve the same or equivalent effect.

The corresponding structures materials acts and equivalents of all means or step plus function elements in the claims below are intended to include any structure material or act for performing the function in combination with other claimed elements as specifically claimed. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising when used in this specification specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the disclosed subject matter. While certain embodiments of the disclosed subject matter have been illustrated and described it will be clear that the invention is not limited to the embodiments described herein. Numerous modifications changes variations substitutions and equivalents are not precluded.


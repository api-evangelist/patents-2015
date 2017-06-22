---

title: Database-driven entity framework for internet of things
abstract: Unified and normalized management of an object within a structured data store on any machine and/or across difference machines. In an embodiment, a first agent accesses a first request dataset representing a two-dimensional structure. Each row in the request dataset comprises an identification of an agent, a statement, an identification of a resource to execute the statement, and one of a plurality of request types. Each row in the request dataset is processed according to the identification of the agent in the row. When the identified agent is the first agent, the request type of the row is accessed, and one or more elements in the row are processed based on the request type. When the identified agent is not the first agent, the row is sent within a second request dataset to the identified agent (which may be on a different machine than the first agent) for processing.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09495401&OS=09495401&RS=09495401
owner: 
number: 09495401
owner_city: Newport Beach
owner_country: US
publication_date: 20150413
---
This application claims priority to U.S. Provisional Patent App. Nos. 61 978 440 filed on Apr. 11 2014 and titled X10DATA Metadatabase Cloud Service and 62 008 311 filed on Jun. 5 2014 and titled Digital Automation Platform and 62 130 330 filed on Mar. 9 2015 and titled Digital Automation Platform the entireties of all of which are hereby incorporated herein by reference.

This application is related to U.S. patent application Ser. No. 14 160 403 filed on Jan. 21 2014 and issued as U.S. Pat. No. 9 015 465 on Apr. 21 2015 which is a continuation of U.S. patent application Ser. No. 13 830 249 filed on Mar. 14 2013 which claims priority to U.S. Provisional Patent App. Nos. 61 762 779 filed on Feb. 8 2013 and 61 783 362 filed on Mar. 14 2013 the entireties of all of which are hereby incorporated herein by reference.

The embodiments described herein are generally directed to the unified and normalized management of an object within a structured data store on any machine and or across different machines.

Conventionally data centric software applications and application platforms have incorporated one or more software architecture patterns and programming paradigms including service oriented client server peer to peer event driven and object oriented architectures and object oriented programming object relational mapping and entity relationship modeling.

Conventionally machine to machine and human to machine communications are managed through one or more communication protocols e.g. MQTT XMPP DDS AMQP CoAP RESTful HTTP .

None of the existing software architecture patterns or communication protocols has an abstraction layer capable of effectively supporting the interoperability requirements of the Internet of Things. This leads to fragmented systems within complex and costly integrations between disparate systems.

It would be beneficial to have an architectural pattern and communication protocol that eliminates fragmentation and provides a normalized layer of abstraction that supports universal interoperability among machines and enables unified management of an object within a structured data store on any machine and or across different machines.

Accordingly systems and methods are disclosed for unified and normalized management of an object within a structured data store on any machine and or across different machines.

In an embodiment a method is disclosed. The method comprises using at least one hardware processor to by a first agent on a first machine accessing a first request dataset wherein the first request dataset represents a two dimensional structure having one or more rows and a plurality of columns and wherein each of the one or more rows comprises an identification of an agent a statement an identification of a resource to execute the statement and one of a plurality of request types and process each of the one or more rows in the first request dataset by accessing the identification of an agent in the row when the identification of the agent is the first agent accessing the request type of the row and processing one or more elements in the row based on the request type of the row and when the identification of the agent is not the first agent sending the row in the first request dataset within a second request dataset comprising one or more rows to the identified agent for processing wherein the identified agent is on a machine that is different from the first machine.

In an additional embodiment a system is disclosed. The system comprises one or more hardware processors and one or more modules that when executed by at least one of the one or more hardware processors access a first events dataset wherein the first events dataset represents a two dimensional structure having one or more rows and a plurality of columns and wherein each of the one or more rows comprises an identification of an object dataset an identification of an object within the object dataset an identification of an element of the object within the object dataset and one of a plurality of event types and process each of the one or more rows in the first events dataset by accessing the event type of the row and processing one or more elements in the row based on the event type of the row by when the event type is a first predetermined type creating an object within an object dataset when the event type is a second predetermined type updating an object within an object dataset and when the event type is a third predetermined type deleting an object within an object dataset.

In an additional embodiment a non transitory computer readable medium is disclosed. The medium has instructions stored thereon that when executed by a processor cause the processor to access an object view identifier wherein the object view identifier identifies a view object and one or both of an object dataset within a data store and an object within the identified object dataset wherein the identified object dataset represents a two dimensional structure having one or more rows and a plurality of columns and generate a statement wherein the statement comprises one of a view dataset and a script derived from one or more view datasets wherein each view dataset represents a two dimensional structure having one or more rows and a plurality of columns derived from at least one or more elements in one or both of the two dimensional structure of the identified object dataset and a two dimensional structure of other object datasets within the data store.

A structured program transfer protocol SPTP object event processor OEP object view generator OVG and structured data store SDS are disclosed in various embodiments.

For purposes of understanding the present disclosure the following terms should be understood to include at least the following illustrative non exhaustive definitions 

 Machine An electronic device capable of performing one or more computing processes receiving data from one or more other electronic devices e.g. other machines and or sending data to one or more other electronic devices e.g. other machines . Examples of machines include without limitation a server personal computer PC laptop computer tablet a media system an entertainment system a control system e.g. an in vehicle media entertainment and or controls system smart phone feature phone appliance mechanical controller sensor thermostat etc.

 Agent A hardware or software component or module that acts for a user or program in an agency relationship. Examples of agents include without limitation a central processing unit CPU microprocessor operating system OS native Hypertext Markup Language HTML container web browser window web service database server etc.

 Statement A structured dataset or string of characters that are constructed in the syntax of a scripting language and which can be executed in their entirety by a compatible resource to perform a computing process. Examples of computing processes which may be performed by executing a statement using a resource include without limitation rendering a display or user interface manipulating and or retrieving data printing a document invoking an application programming interface API controlling a mechanism transmitting an XML message to a web service changing the state of a machine or resource etc.

 Resource A computer program that transforms statements written in a high level scripting language to a lower level language that can be executed on a machine to manipulate and or retrieve data render display content etc. Examples of resources include without limitation a data engine layout and or rendering engine machine control and or printing engine etc.

 Remote Resource A resource on a remote machine that can be invoked directly by an agent on another machine. For example two or more machines may be separated by one or more networks such as the Internet rendering each of the machines remote from the other. An example of a remote resource includes without limitation a web service.

 Request A message sent to a resource or remote resource via a communication protocol that is intended to elicit a responding message. An example of a request includes without limitation a Hypertext Transfer Protocol HTTP request.

 Response A message returned from a resource or remote resource via a communication protocol in response to a request e.g. after executing the request . Examples of responses include without limitation an error message user event SQL result set etc.

 Metadata based Method A metadata based subroutine that is associated with a program and includes one or more single line commands method steps which are interpreted by the disclosed command processor to manipulate datasets loaded in a memory on a machine and or invoke machine resources.

 Program A static set of instructions that are executed by a command processor to control the behavior of a machine. The execution of a program is a series of actions following the set of instructions that it contains. Each instruction may produce an effect that alters the state of a machine according to the instruction s predefined meaning. A program manages and integrates a machine s capabilities but typically does not directly apply in the performance of tasks that benefit the user or machine. An example of a program includes without limitation the Microsoft Windows operating system.

 Application Computer software that applies the power of a particular program to a particular purpose. A command processor serves the program which serves the application which serves a specific purpose. Examples of applications include without limitation enterprise software accounting software office suites graphics software media players etc.

 Dataset A collection of data represented in tabular form. Each column in a dataset may represent a particular variable. Each row in a dataset may correspond to a given member of the dataset in question. A dataset may comprise data for one or more members corresponding to the number of rows. Example embodiments of a dataset include a table within a database a file within a file system a two dimensional array serialized within a string and a port pin collection within a microcontroller.

 Dataset Element Any value in a dataset. A dataset element can be referenced by a combination of its column position column index or CI and row position row index or RI within the dataset. Elements within a dataset may be referenced using x y notation where x is the row index and y is the column index. A dataset element can represent an attribute value of an object. Examples of a dataset element include a field within a database table an address within a file an element within a two dimensional array and a port pin within a microcontroller.

 Object Dataset A structured dataset that includes a column representing a unique object identifier and one or more rows that each represent an object.

 View Dataset A read only dataset derived from elements from a base object dataset and one or more related object datasets.

 Nested Dataset A view dataset stored or referenced as a dataset element within another dataset. Nested datasets are one to many relationships embodied in a single parent dataset memory store.

 Metadata There are two types of metadata. Structural metadata is data about the design and specification of data structures. Structural metadata cannot be data about data since at design time the application contains no data. Rather structural metadata is data about the containers of data. Descriptive metadata is data about data content. This data content is the individual instances of application data.

 Communication Protocol A system of digital message formats and rules for exchanging messages in or between computing systems e.g. in telecommunications . Protocols may include signaling authentication error detection capabilities and or correction capabilities. Each message has an exact meaning intended to provoke a defined response by the receiver. The nature of the communication the actual data exchanged and any state dependent behaviors are defined by a technical specification or communication protocol standard. Examples of conventional communication protocols include without limitation HTTP HTTP Secure HTTPS File Transfer Protocol FTP etc.

 Command Processor A software shell with the primary purposes of 1 loading or booting another program and 2 processing commands from the launched program. Processing of these commands can include without limitation data transfers event handling display renderings and machine to machine communications. Examples of conventional command processors include without limitation the Microsoft Disk Operating System MS DOS command line tools e.g. command.exe or cmd.exe Unix or Linux shells etc.

 Command A subroutine within a command processor that can be invoked by an agent or by another command and which executes an instruction set. Certain commands can be referenced by a command code.

 Scripting Language A programming language that supports the writing of scripts. Scripts are programs written for a software environment that automate the execution of tasks which alternatively could be executed one by one by a human operator. Environments that can be automated through scripting include without limitation software applications web pages within a web browser shells of operating systems and several general purpose and domain specific languages such as those for embedded systems. Examples of scripting languages include without limitation Structured Query Language SQL HTML Printer Control Language PCL eXtensible Markup Language XML Computer Numeric Control CNC etc.

 Booting The process of loading and executing bootstrap software by a computer during the start up process. Booting is a chain of events that start with execution of hardware based procedures that may then hand off to firmware and software which is loaded into memory. Booting often involves processes such as performing self tests and loading configuration settings Basic Input Output System BIOS resident monitors a hypervisor an operating system and or utility software.

 Event An action that is initiated outside the scope of a command processor and that is handled by the command processor. Typical sources of events include users e.g. via keystroke s i.e. pressing one or more keys on a keyboard and software or hardware devices e.g. a timer . A computer program that changes its behavior in response to events is said to be event driven often with the goal of being interactive.

 Instruction Set A collection of computer instructions including native data types instructions registers addressing modes memory architecture interrupt and exception handling and external Input Output I O . Instructions are in the form of a programming language i.e. source code or machine language i.e. machine code that is compatible with a machine resource. Source code is written using some human readable computer language usually as text. The source code of a program is specially designed to facilitate the work of computer programmers who specify the actions to be performed by a computer primarily by writing source code. The source code is automatically translated at some point e.g. by a compiler to machine code that the computer can directly read and execute.

 Data Store A repository of a set of objects. A data store can contain one or more object datasets. A data store is a general concept that includes not just repositories like databases but also simpler store types such as flat files or firmware.

 Normalization The process of reducing data and metadata to a canonical form to facilitate interoperability. For instance dataset normalization is the process of organizing datasets and dataset elements within a data store to minimize redundancy and dependency.

 Entity A category of like things or objects which are each recognized as being capable of an independent existence and which can be uniquely identified. Non limiting examples of an entity include physical objects such as houses or cars events such as house sales or car services concepts such as customer transactions or orders personal information such as contacts message appointments and tasks and object schema such as object datasets dataset elements attributes and entities reflectively.

 Attribute A data characteristic of an entity. Every entity has a minimal set of uniquely identifying attributes including a unique identifier.

 Object A data representation of a unique instance of an entity. Data characteristics attribute values of an object can be stored as dataset elements within a row of a dataset.

 GUID A globally unique identifier GUID is a unique reference number generated by an algorithm that is used as an identifier in computer software. Non limiting examples of a GUID include alphanumerical text a sequence of digits e.g. decimal or hexadecimal digits a MAC address and time and may be stored as a 16 byte 128 bit number. An example of a GUID is D9A4F842 AF53 4A49 B752 CE58BE46C72D .

 Object Event A change in the state of an object including for a new object the change from no state into an initial state. For example when a consumer purchases a car the car s state changes from for sale to sold .

 Object Event Notification A type of message typically asynchronous that is produced published propagated detected or consumed and contains one or more object events. For example a car dealer s automated system may notify another system of a car object s state change from for sale to sold .

 Object View A script in a resource compatible scripting language that includes elements from one or more related view datasets and formatting instructions. The script when executed by a resource changes the state of a resource or resource s machine and or generates a response from the resource or resource s machine. An object view when executed by a resource on a machine can render a display or user interface retrieve and or manipulate data print a document invoke an application programming interface API control a mechanism transmit a message to a web service and or change the state of a machine and or resource etc.

 Aggregate Object A cluster of associated objects including a root object that are treated as a unit for the purpose of data changes. An example of an aggregate object is a purchase order object with one or more line item objects assigned to the purchase order object.

 Triggered Action An action performed in response to an object event that meets a defined condition rule or logical test.

 Domain A realm of administrative autonomy authority or control within a network. A domain can represent an addressable location on a network or a tenant within a multi tenancy software architecture.

The disclosed structured program transfer protocol agent object event processor object view generator and structured data store facilitate unified and normalized management of any object within a structured data store on any machine and or across different machines. Such machines may range for example from a sensor e.g. home thermostat to a computer e.g. smart phone and so on. The disclosed embodiments also facilitate the transfer and delivery of programs applications data events and views on one machine e.g. tablet PC to another machine e.g. in vehicle navigation system via a communications interface. The request delivery and transfer of data and metadata for programs program compatible applications events views etc. between machines are facilitated by a novel structured program transfer protocol for communications. The applications can be simple e.g. an on off switch or complex e.g. robotics or business solutions e.g. enterprise resource planning ERP customer relationship management CRM etc. .

For example the disclosed structured program transfer protocol agent object event processor object view generator and or structured data store can facilitate codeless rapid development and on demand delivery of data centric applications on end user devices such as smart phones tablets PCs and in vehicle navigation systems. The data centric application may be a spreadsheet web site client server business solution etc.

In an embodiment the structured program transfer protocol is a type of communication protocol that defines the dataset schema SPTP Request for sending one or more types of request and the dataset schema SPTP Response for receiving one or more types of response from one machine to another and or from one resource to another on a machine.

In an embodiment each of the one or more rows in the SPTP Request comprises a request type an identification of an agent a statement and an identification of a resource to execute the statement. In this embodiment a request type in a row can comprise a statement type i.e. specifying the type of statement included in that row. In this embodiment an identification of an agent can comprise an agent connection type and agent connection string. In this embodiment an identification of a resource can comprise a resource connection type and resource connection string.

In an embodiment while processing a single defined request type within a SPTP Request may only perform a portion of creating reading updating and deleting object datasets within a structured data store e.g. reading the combined processing all of the defined request types within the dataset schema of SPTP Request perform all aspects of creating reading updating and deleting object datasets within a structured data store.

In an embodiment each of the one or more rows in the SPTP Response comprises a response type and a response.

In an embodiment the structured program transfer protocol defines the dataset schema SPTP Events for creating and sending object events as a type of statement within an SPTP Request creating and or processing object events using an object event processor and storing object events within a structured data store.

In an embodiment the structured program transfer protocol defines the string schema SPTP View ID for sending the identification of an object view as a type of statement within an SPTP Request and processing identifications of object views using an object view generator.

In an embodiment the structured program transfer protocol defines the dataset schema SPTP View Definition for sending the definition of an object view as a type of statement within an SPTP Request and creating and or processing definitions of object views using an object view generator.

The object event processor e.g. OEP is a type of resource that processes instances of SPTP Events. The object event processor can reside on multiple machines e.g. OEP on machine and OEP on machine and be a resource available to an agent specific to each machine e.g. agent on machine and agent on machine .

The object view generator e.g. OVG is a type of resource that generates view datasets and object views from instances of an SPTP View ID or SPTP View Definition. The object view generator can reside on multiple machines e.g. OVG on machine and OVG on machine and be a resource available to an agent specific to each machine e.g. agent on machine and agent on machine . The object view generator may also be a resource available to an object event processor specific to each machine e.g. OEP on machine and OEP on machine .

In an embodiment the structured data store e.g. SDS is a type of data store that maintains objects within a data structure that is compatible with an object event processor and object view generator. The structured data store can reside on multiple machines e.g. SDS on machine and SDS on machine and interact with an agent specific to each machine e.g. agent on machine and agent on machine . The structured data store can also interact with an object event processor specific to each machine e.g. OEP on machine and OEP on machine and an object event processor specific to each machine e.g. agent on machine and agent on machine .

In an embodiment a row in the SPTP Request may identify the resource needed to execute a statement within the row. If the resource identified in the SPTP Request is on a remote machine e.g. machine then the SPTP Request also identifies the remote agent e.g. agent on the remote machine that can communicate with the resource e.g. resource on the remote machine. For example if agent on machine is processing an SPTP Request that has a row identifying a needed resource on machine agent may forward the SPTP Request or a new SPTP Request e.g. SPTP Request dataset to the remote agent e.g. agent .

If a row in the SPTP Request specifies a request to execute a statement included in the SPTP Request then the processing agent e.g. agent sends the statement to the identified resource e.g. directly or via forwarding to a remote agent . For example if agent processes a request to execute a statement pertaining to identified resource agent may send the statement e.g. statement to resource directly. On the other hand if agent processes a request to execute a statement pertaining to remote resource agent may forward the request to agent for execution e.g. via statement sent from agent to resource . In either case the executing resource may return a response e.g. response or response to the invoking agent. The invoking agent generates a SPTP Response that includes a row that contains the response from the executing resource.

In an embodiment agent processes rows in the SPTP Request according to the request type specified in the row. In such an embodiment agent may process one or more of the following request types in one or more of the following manners 

 1 If a row in the SPTP Request specifies a request type to send instructions for creating a structured data store then agent or the identified remote agent e.g. agent invokes the identified resource or remote resource e.g. respectively to generate the instructions for creating a structured data store. The invoking agent generates a SPTP Response that includes a row that contains a SPTP Request. The SPTP Request included in the SPTP Response includes a row that contains the instructions within a statement. The row in the SPTP Request within the SPTP Response is returned to a resource e.g. resource via agent that processes the row to execute the statement to generate a structured data store. The generated structured data store may include an object event processor and an object view generator.

 2 If a row in the SPTP Request specifies a request type to process one or more rows in an SPTP Events included in the statement of the row then agent or the identified remote agent e.g. agent invokes an object event processor e.g. or remote object event processor e.g. respectively to create update or delete one or more object datasets within a structured data store e.g. or remote structured data store e.g. respectively.

 3 If a row in the SPTP Request specifies a request type to generate a view dataset based on an SPTP View ID included in the statement of the row then agent or the identified remote agent e.g. agent invokes an object view generator e.g. or remote object view generator e.g. respectively to generate a view dataset.

 4 If a row in the SPTP Request specifies a request type to send a program and or one or more program compatible application datasets then agent or the identified remote agent e.g. agent invokes the identified resource or remote resource e.g. resource respectively to generate the program and or one or more program compatible application datasets. The invoking agent generates an SPTP Response that includes a row that contains the program and or one or more program compatible application datasets e.g. program dataset or application dataset respectively . The row in the SPTP Response may be returned to a command processor as a resource for processing.

 5 If a row in the SPTP Request specifies a request type to generate an object view based on an SPTP View ID included in the statement of the row then agent or the identified remote agent e.g. agent invokes an object view generator e.g. or remote object view generator e.g. respectively to generate a row within SPTP Request for processing by the invoking agent. The generated row includes an identification of a resource and a statement that comprises an object view which was generated by the object view generator from one or more related view datasets which were generated by the object view generator based on the object view identifier.

In an embodiment an object view generated by an object view generator includes a resource compatible script in various scripting languages e.g. HTML SQL XML PCL . When executed by a resource on a machine the script can render a display or user interface retrieve or manipulate data print a document invoke an application program interface control a mechanism of a machine transmit a message to a web service change the state of a machine or resource etc.

 6 If a row in the SPTP Request specifies a request type to send the processing state of a program and one or more program compatible applications then the identified remote agent e.g. agent invokes a command processor as the identified remote resource e.g. to generate a row in an SPTP Response that includes a statement that comprises a program dataset and one or more program compatible application datasets residing on the machine of the identified remote agent. The SPTP Response may then be returned to a command processor as the invoking resource e.g. of the agent e.g. for processing.

The following description illustrates a non limiting embodiment of a structured program transfer protocol request. The structured program transfer protocol request may comprise a multi row SPTP Request dataset which may be sent from an agent e.g. agent to a remote agent e.g. agent or agent . The SPTP Request dataset includes structured dataset elements that any agent or remote agent can interpret and process. In this embodiment the dataset comprises the columns illustrated in Table 1 

In an embodiment the value of the Statement element in a row within the SPTP Request will contain an SPTP Events dataset when the Resource Connect Type element value i.e. CI 3 in the row is 3 i.e. Data Store Resource and the Statement Type element value in the row is 1 i.e. SPTP Events .

In an embodiment the value of the Statement element in a row within the SPTP Request will contain a SPTP View ID when the Resource Connect Type element value i.e. CI 3 in the row is 3 i.e. Data Store Resource and the Statement Type element value in the row is 2 i.e. SPTP View ID .

In an embodiment the value of the Statement element in a row within the SPTP Request will include a SPTP View when the Resource Connect Type element value i.e. CI 3 in the row is 3 i.e. Data Store Resource and the Statement Type element value in the row is 3 i.e. SPTP View .

The following description illustrates a non limiting embodiment of a structured program transfer protocol response. The structured program transfer protocol response may comprise a multi row SPTP Response dataset which may be returned to an agent e.g. agent from a remote agent e.g. agent or agent in response to a SPTP Request . In an embodiment this dataset contains two columns as shown in Table 3 

The Response dataset element may contain a specific nested dataset. Illustrative defined values for the Response Type dataset element are illustrated in Table 4 

In an embodiment the value of the Response element i.e. CI 1 in a row in the SPTP Response will contain a Program dataset when the Response Type element value i.e. CI 0 in the row is 1 i.e. Program dataset .

In an embodiment the Program dataset is a single row dataset with the defined columns illustrated in Table 5. Each dataset element in the Program dataset may contain a specific nested dataset as shown below 

In an embodiment the value of the Response element i.e. CI 1 in a row in the SPTP Response will contain an Application dataset when the Response Type element value i.e. CI 0 in the row is 2 i.e. Application dataset .

In an embodiment an Application dataset is a single row dataset with the defined columns illustrated in Table 6. Each dataset element in the Application dataset may contain a specific nested dataset as shown below 

The columns of the nested datasets within the Program dataset and Application dataset are described in more detail elsewhere herein.

In an embodiment the nested datasets within the Program dataset and the nested datasets within the Application dataset may be generated from a response from an object view processor e.g. OVG or OVG .

In an embodiment the value of the Response element i.e. CI 1 in a row in the SPTP Response will contain a Data dataset when the Response Type element value i.e. CI 0 in the row is 3 i.e. Data dataset .

In an embodiment the Data dataset is a view dataset that may be generated from a response from an object view processor e.g. OVG or OVG .

In an embodiment the value of the Response element i.e. CI 1 in a row in the SPTP Response will contain a Process dataset when the Response Type element value i.e. CI 0 in the row is 4 i.e. Process dataset .

In an embodiment the Process dataset may contain one or more nested datasets that represent the current processing state of a Program dataset and one or more program compatible Application datasets .

In an embodiment the value of the Response element i.e. CI 1 in a row in the SPTP Response will contain a SPTP Request dataset when the Response Type element value i.e. CI 0 in the row is 5 i.e. SPTP Request dataset .

The following description illustrates a non limiting embodiment of structured program transfer protocol events. The structured program transfer protocol events may comprise a multi row SPTP Events dataset which may be sent from an agent e.g. agent to a remote agent e.g. agent or agent or stored in a structured data store e.g. SDS . The SPTP Events dataset includes structured dataset elements that an object event processor interfaced with or comprised in any agent or remote agent e.g. OVG interfaced with or comprised in agent or OVG interfaced with or comprised in agent can interpret and process. In an embodiment the SPTP Events dataset comprises the columns illustrated in Table 7 

The following description illustrates a non limiting embodiment of a structured program transfer protocol view identifier. The structured program transfer protocol view identifier may comprise a SPTP View ID string which may be sent from an agent e.g. agent to a remote agent e.g. agent or agent included in a statement within a row of an SPTP Request. In an embodiment the SPTP View ID string includes delimited values that an object view generator e.g. OVG or OVG interfaced with or comprised in any agent or remote agent can interpret and process. The string may comprise the delimited values illustrated in Table 9 

The following description illustrates a non limiting embodiment of a structured program transfer protocol view definition. The structured program transfer protocol view definition may comprise a single row SPTP View Definition dataset which may be sent from an agent e.g. agent to a remote agent e.g. agent or agent included in a statement within a row of an SPTP Request. The SPTP View Definition dataset includes structured dataset elements that an object view generator e.g. OVG or OVG interfaced with or comprised in any agent or remote agent can interpret and process.

In an embodiment the SPTP View Definition dataset is a single row dataset with the defined columns illustrated in Table 10. Each dataset element may contain a specific nested dataset as shown below 

The following description illustrates a non limiting embodiment of an agent e.g. agent and or . illustrates the relationships between an agent a resource an object event processor as a type of resource an object view generator as a type of resource a structured data store and a remote agent and a remote machine according to an embodiment. As shown agent on machine may comprise receive send monitor booter and resource handler .

In an embodiment receive send monitor monitors incoming requests from remote agents e.g. remote agent . When a SPTP Request is received e.g. SPTP Request dataset receive send monitor may invoke resource handler to process one or more rows in the SPTP Request and generate one or more rows in a SPTP Response. Receive send monitor returns the SPTP Response e.g. SPTP Response dataset to the requesting remote agent.

In an embodiment booter is invoked when agent is initiated on machine . Booter generates one or more rows in a SPTP Request and invokes resource handler to process the rows.

In an embodiment a resource e.g. resource of machine may generate one or more rows in an SPTP Request e.g. SPTP Request dataset and invokes resource handler to process the rows and generate one or more rows in a SPTP Response e.g. SPTP Response dataset that is returned to the resource.

In an embodiment a resource e.g. resource of machine is a command processor that can process a Program dataset Application dataset Process dataset and or Data dataset returned in an SPTP Response.

In an embodiment for each row in a SPTP Request e.g. SPTP Request dataset resource handler may invoke a resource e.g. resource OEP and or OVG of machine that is identified within the row to execute a statement that is contained within the row which may generate a response. Resource handler creates a SPTP Response that contains one or more rows that each contains a resource response.

In an embodiment for one or more rows in a SPTP Response e.g. SPTP Response dataset that contain an SPTP Request e.g. SPTP Request dataset agent may invoke resource handler to process the one or more rows in the SPTP Request.

In an embodiment agent returns one or more rows in a SPTP Response e.g. SPTP Response dataset to a resource that generated the SPTP Request e.g. SPTP Request dataset .

In an embodiment an agent resource handler or resource may generate a row in a SPTP Response e.g. SPTP Response dataset that comprises a Program dataset Application dataset Data dataset Process dataset and or SPTP Request dataset .

In an embodiment a resource can be invoked by resource handler to create retrieve update or delete objects in a structured data store send an SPTP Request to a remote agent for processing send a statement to a remote machine for processing retrieve or process an object view script to render a display or user interface retrieve or manipulate data print a document invoke an application program interface control a mechanism of a machine transmit a message to a web service change the state of a machine or resource etc.

In an embodiment resource handler can generate one or more rows in an SPTP Events dataset that comprise a response from a remote machine e.g. machine .

The following description illustrates a non limiting embodiment of a structured data store SDS . The SDS includes structured datasets and objects within datasets that any object event processor OEP and object view generator OVG can interpret and process.

In an embodiment the SDS contains initial datasets as illustrated in . One or more of these initial datasets may be created by the same resource that created the SDS e.g. during or after creation of the SDS .

In an embodiment SDS and SDS initially contain SPTP Events dataset and respectively. In an embodiment SDS also initially contains certain object datasets including Domain object dataset Entity object dataset Attribute object dataset Action object dataset Trigger object dataset and Dataset object dataset . It should be understood that SDS may also initially contain one or more other object datasets e.g. represented by object dataset .

In an embodiment each row within an object dataset e.g. Domain object dataset Entity object dataset Attribute object dataset Action object dataset Trigger object dataset Dataset object dataset and or additional object dataset s represents an object and each column within an object dataset represents an attribute such that each element in a row within an object dataset represents an attribute value of the object represented by that row.

In an embodiment the processing of an SPTP Events dataset by an OEP e.g. OEP may create one or more of these object datasets e.g. Domain object dataset Entity object dataset Attribute object dataset Action object dataset Trigger object dataset Dataset object dataset and or additional object dataset s .

In an embodiment one or more object datasets e.g. any of object datasets within an SDS e.g. SDS initially comprises an Object Identifier column an Owner Domain column and an Object Entity column as illustrated in Table 11 and . In this embodiment each element in a column of a row of an object dataset represents an attribute of the object represented by that row.

In an embodiment the Object Identifier column may contain any type of unique identifier including without limitation a sequence of any number of digits or alphanumerical characters hexadecimal numbers and the like. An Object Identifier element within a row in an object dataset identifies the object represented by that row. Thus the element in an Object Identifier column of any of the object datasets may be referred to herein as an object identifier. 

In an embodiment an object dataset e.g. any of object datasets within an SDS e.g. SDS can comprise additional initial columns as illustrated for example in Table 12. In this embodiment each element in a column of a row of an object dataset represents an attribute of the object represented by identified in or otherwise associated with that row.

In an embodiment an object dataset e.g. any of object datasets within SDS can be identified by the Object Identifier element within Dataset object dataset for the row representing the object dataset as an object. Dataset object dataset itself can be identified by the Object Identifier element at index location 0 0 within Dataset object dataset which is illustrated in as AC4B . . . .

In an embodiment each of the rows of Attribute object dataset represent a particular attribute as an object that can be associated with other objects e.g. objects within Entity object dataset . As discussed above and illustrated in CI 0 for Attribute object dataset comprises an identifier such that each row represents a uniquely identified attribute. Thus for example a column representing an attribute within an object dataset e.g. any of object datasets including Attribute object dataset within SDS can be identified by the Object Identifier element corresponding to the row in the Attribute object dataset that represents that attribute. A column index e.g. CI 3 in Attribute object dataset representing an attribute within Attribute object dataset itself can be identified by the Object Identifier element at CI 0 within Attribute object dataset . For example as illustrated in CI 3 is identified by the unique identifier for the attribute represented by RI 0 i.e. the unique identifier at index location 0 0 i.e. A0A2 . . . . In addition CI 4 is identified by the unique identifier for the attribute represented by RI 1 i.e. the unique identifier at index 1 0 i.e. 91AA . . . and so on.

In an embodiment the Owner Domain column can identify a domain. A single object dataset can include objects from one domain or multiple domains. Each domain may be represented as a row within Domain object dataset .

In an embodiment an Owner Domain element within an object dataset e.g. any of object datasets within SDS can be set to the value of an object identifier uniquely identifying a domain within Domain object dataset e.g. the element in the Object Identifier column of the row representing the domain object . The Owner Domain element at CI 1 within Domain object dataset itself can be set to the value of the object identifier at CI 0 within Domain object dataset . For example as illustrated in the element at index location 0 1 i.e. E324 . . . representing the domain that owns the domain object represented by RI 0 is the same as the element at index location 0 0 . Such a scenario indicates that the domain owns its own domain object.

In an embodiment objects within Domain object dataset may represent persons organizations locations and the like. In this embodiment a domain object representing an organization and represented as a row in the Domain object dataset can be assigned as the owner domain for a domain object representing a person location or other organization also represented as a row in the Domain object dataset . As another example a domain object representing a person and represented as a row in the Domain object dataset can be assigned as the owner domain for a domain object representing a location or other person also represented as a row in the Domain object dataset . In either case a first domain object is assigned as the owner domain for a second domain object by identifying the first domain object in the Owner Domain column CI 1 of the second domain object.

In an embodiment the Object Entity column can identify an entity. A single object dataset can include objects from one entity or multiple entities. Each entity may be represented as a row within Entity object dataset .

In an embodiment an Object Entity element within an object dataset e.g. any of object datasets within SDS can be set to the value of an object identifier within Entity object dataset . The Object Entity element at CI 2 within Entity object dataset itself can be set to the value of the object identifier at CI 0 within Entity object dataset . For example as illustrated in the element at index location 0 2 i.e. 8F55 . . . is the same as the element at index location 0 0 .

In an embodiment processing SPTP Events e.g. SPTP Events dataset by an OEP on a machine e.g. OEP on machine can create one or more additional object datasets e.g. object dataset within an SDS e.g. SDS on the same machine.

In an embodiment processing SPTP Events e.g. SPTP Events dataset by an OEP on a machine e.g. OEP on machine can create one or more additional rows or columns within an existing object dataset e.g. Entity object dataset within a SDS e.g. SDS on the same machine.

In an embodiment Dataset object dataset can contain rows that represent both object datasets and view datasets as objects. In this embodiment view datasets include dataset elements from one or more related objects in one or more related object datasets within an SDS e.g. SDS . Object relationships are described in more detail elsewhere herein.

In an embodiment one or more view datasets e.g. Views dataset can be included as nested datasets within the program and application datasets e.g. Program dataset and Application dataset .

In an embodiment scripts maintained within a column e.g. CI 5 within Dataset object dataset can generate view datasets. These scripts may be maintained in a scripting language that is compatible with one or more resources interfaced with or comprised in an SDS e.g. SDS .

In an embodiment the functionality of an OEP or OVG may be embodied within a script that can be executed by a resource interfaced with or comprised in an SDS e.g. SDS . For example an OEP script and OVP script can be contained within rows within Dataset object dataset e.g. illustrated in at location indices 4 5 and 5 5 .

In an embodiment Entity object dataset can contain rows that represent both master entities and slave entities as objects. An example is illustrated in according to an embodiment. In this embodiment one or more slave entities can be assigned to a master entity. A column within Entity object dataset e.g. CI 3 can identify the master Entity object assigned to a slave Entity object. In the illustrated example he Master Entity element at index location 5 3 within Entity object dataset is set to the value of the object identifier at index location 4 0 within Entity object dataset which is illustrated as 2C8D . . . . Thus in the example illustrated in the entity represented by RI 5 and identified as 2495 . . . is a slave entity to the master entity represented by RI 4 and identified as 2C8D . . . .

In an embodiment an object identifier for an object dataset within the Dataset object dataset can be set to an object identifier for a master entity within the Entity object dataset . For example as illustrated in the object identifier at index location 6 0 in the Dataset object dataset is set to the value of the object identifier i.e. 2C8D . . . for the master entity represented by row 4 0 in the Entity object dataset .

In an embodiment one or more objects representing attributes within Attribute object dataset can be assigned to a master or slave Entity object within Entity object dataset . In this embodiment a column within Attribute object dataset e.g. CI 3 can identify the Entity object assigned to an attribute object. For example as illustrated in the element at index location 5 3 of the Attribute object dataset is set to the value of the object identifier i.e. 2C8D . . . for the master entity represented by row 4 0 in the Entity object dataset .

In an embodiment Attribute object dataset can contain rows that represent both master attributes and slave attributes as objects. In this embodiment one or more slave attribute objects can be assigned to a slave Entity object and one or more master attribute objects can be assigned to a master Entity object. Also in this embodiment a slave attribute object can be assigned to a master attribute object where the slave Entity object that is assigned to the slave attribute object is assigned to the master Entity object which is assigned to the master attribute object. A column e.g. CI 5 within Attribute object dataset can identify the master attribute object assigned to a slave attribute object. For example as illustrated in the Master Attribute element at index location 6 5 within Attribute object dataset is set to the value of the object identifier i.e. 4A82 . . . at index location 5 0 within Attribute object dataset . Thus the attribute represented by RI 6 in the Attribute object dataset and identified as 9E76 . . . is a slave attribute to the master attribute represented by RI 5 and identified as 4A82 . . . in the Attribute object dataset .

In an embodiment an object dataset e.g. View object dataset A can contain objects associated with a master entity and or one or more slave entities assigned to the master entity. In this embodiment the Object Entity element e.g. at CI 2 within View object dataset A is set to the object identifier e.g. at CI 0 for a master Entity object within Entity object dataset . For example the Object Entity element at index location 0 2 in View object dataset A is set to the value of the Object Identifier element at index location 4 0 within the Entity object dataset indicating that View object dataset A contains the master entity represented by RI 4 in Entity object dataset and identified by 2C8D . . . . In addition the Object Entity element at index location 1 2 within View object dataset A is set to the value of the Identifier element at index location 5 0 within Entity object dataset indicating that View object dataset A also contains the slave entity represented by RI 5 in Entity object dataset and identified by 2495 . . . .

In an embodiment values for master and slave attributes are maintained within the same object dataset column. This object dataset column can be identified as the object identifier of the master attribute. For example as illustrated in the Type element at index location 0 3 within View object dataset A is representing a value of the master attribute identified in RI 5 within Attribute object dataset . In addition the Type element at index location 1 3 within View object dataset A is representing a value of the slave attribute identified in RI 6 within Attribute object dataset .

In an embodiment a Model object assigned to an Entity object can incorporate as Model Attribute objects one or more Attribute objects of the Entity object as illustrated in . For example a Printer Entity object can be assigned to a plurality of Model objects with each Model object supporting a subset of the complete attribute set a universal printer definition.

In an embodiment from a triggered action upon creating or updating an Entity object the object event processor can create Attribute objects from the Parent Entity element and or the Child Entity element of the Entity object as illustrated in .

In an embodiment human readable identifiers for objects within certain object datasets e.g. Entities object dataset Attributes object dataset can be constructed from assigned objects from a Terms object dataset as illustrated in . For example a human readable identifier of Sales Order Item Serial Number can be constructed from four Term objects assigned to elements of Entity object at RI 12 in Entity object . The human readable identifier comprises the Name element of each of the four Term objects i.e. Sales Order Item and Serial Number . In this embodiment the Type element of an Attribute object e.g. RI 15 in Attribute object dataset can be set to a value by processing a row in SPTP Events. From a trigger action the object event processor creates additional Attribute objects to be assigned to Term objects. For example when a dataset element representing the Attribute object at RI 15 is included in an object view the Sales Order Item Serial Number human readable identifier constructed from the assigned Term objects will be displayed in the object view.

In an embodiment the value of Attribute 0BE3 . . . Mailing Address is calculated by replacing the bracketed numbers in the Format String for Type 20 Mailing Address in Table 15 with the value of the Attribute with the corresponding Sequence. For Domain Object xxxx . . . ControlBEAM the value of its 0BE3 . . . Mailing Address is calculated from the values in xxx to derive a calculated value shown in xxx

In an embodiment the value of Attribute 6FE7 . . . Full Name is calculated by replacing the bracketed numbers in the Format String for Type 22 Full Name in Table 17 with the value of the Attribute with the corresponding Sequence. For Domain Object xxxx . . . ControlBEAM the value of its 0BE3 . . . Full Name is calculated from the values in Table xx to derive a calculated value shown in Table xx as illustrated in Table xxx.

The following description illustrates a non limiting embodiment of an Object View Generator OVG as a resource of a machine.

In an embodiment resource handler invokes OVG to process SPTP View ID or SPTP View included in a statement in a row within a SPTP Request e.g. SPTP Request dataset . OVG returns SPTP Request as a response to resource handler .

In an embodiment OEP invokes OVG to process SPTP View ID and OVG returns SPTP Request as a response to OEP .

In an embodiment OVG generates one or more view datasets from objects within object datasets within SDS related to a SPTP View ID e.g. SPTP View ID . OVG nests these view datasets within a SPTP View Definition dataset.

In an embodiment OVG generates a view dataset from objects within object datasets within SDS that comprises elements defined within a SPTP View Definition dataset e.g. SPTP View dataset .

In an embodiment agent nests one or more view datasets generated from OVG within a program dataset or application dataset.

In an embodiment a view dataset generated by OVG from a SPTP View may include elements that represent the state of machine .

In an embodiment OVG generates a statement from a SPTP View that can be executed by a resource. In this embodiment the statement is a resource compatible script that can include object dataset elements and formatting script.

The following description illustrates a non limiting embodiment of an Object Event Processor OEP as a resource of a machine.

In an embodiment resource handler invokes OEP to process SPTP Events included in a statement in a row within a SPTP Request and OEP returns SPTP Request as a response to resource handler .

In an embodiment OEP processes one or more rows in SPTP Events. In an embodiment each row in SPTP Events comprises a type of action.

In an embodiment processing a type of action within SPTP Events creates an object within an object dataset within SDS .

In an embodiment processing a type of action within SPTP Events deletes an object within an object dataset within SDS .

In an embodiment processing a type of action within SPTP Events sets an attribute value of an object within an object dataset within SDS .

In an embodiment processing a type of action within SPTP Events sets an attribute value of an object within an object dataset to a value contained in the same row as the action within SPTP Events.

In an embodiment processing a type of action within SPTP Events sets an attribute value of an object within an object dataset to a value derived from one or more attribute values of related objects within object datasets within SDS .

In an embodiment objects created updated and deleted by OEP may include objects used to create a nested dataset within a program dataset or a nested dataset within an application dataset and may include contact object s message object s task object s appointment object s and the like.

In an embodiment an object within an object dataset within an SDS that is updated by OEP may include the state of the machine on which OEP resides.

In an embodiment a row in an Action object dataset comprises a type of action and an object view identifier e.g. SPTP View ID .

In an embodiment OEP invokes OVG to process a type of action within a row in Action object dataset that also comprises SPTP View ID and OVG returns SPTP Request to OEP . OEP appends the rows within SPTP Request to SPTP Request .

In an embodiment OEP references nested Trigger object dataset and Action object dataset within Application object dataset which are generated from related objects in a SDS including Trigger object dataset and Action object dataset .

The following description illustrates a non limiting embodiment of object datasets within a structured data store that can be incorporated within the nested datasets of a program and or application dataset.

In an embodiment Dataset object dataset can comprise objects that define the view datasets that are nested within a program dataset including the column index within the program dataset and the corresponding View object that defines the elements included in the view dataset as illustrated in Table 22.

In an embodiment View object dataset A can comprise objects that define the view datasets that are nested within a program dataset as illustrated in Table 23.

In an embodiment Relation object dataset M can comprise objects that define the related object datasets included in each of the view datasets that are nested within a program dataset as illustrated in Table 24.

In an embodiment Column object dataset M can comprise objects that define the object dataset columns included in the view datasets that are nested within a program dataset including the column index as illustrated in Table 25.

An implementation of a sample utility which utilizes an embodiment of the disclosed database driven entity framework for the internet of things will now be described.

For purposes of demonstrating the sample utility devices A B C and D are machines that all have the agent component and a profile file installed. The profile file maintains structured content including the Device object identifier and its Model object identifier the identification of a remote agent on a controller device and the identification of one or more local and or remote resources. A program and application dataset is also resident on Devices A B and C.

Device A is owned by and is the controller device e.g. web server for the zebra.com Domain object. Device A has the SDS component installed.

The jsmith zebra.com Domain object is owned by the zebra.com Domain object and is a Member object as a Sales Rep entity of the zebra.com Domain object.

Device B is owned by and is the controller device e.g. web server for the adctech.com Domain object. Device B has the SDS components installed.

Device C is owned by and is an End User Device EUD e.g. smartphone for the jsmith zebra.com Domain object. Device C has the SDS and agent components installed.

Device C has a web socket Connection object to Device A. The jsmith zebra.com Domain object has an active Session object with the zebra.com Domain object using this Connection object.

Device D e.g. printer does not have a resident program and application dataset as the agent on Device D has never been booted and provisioned. The name of the zebra.com Domain object i.e. zebra.com is the identification of the remote agent in its profile file.

The zebra.com Domain object is a Member object as a Vendor entity of the adctech.com Domain object and the adctech.com Domain object is a mirrored Member object as a Customer entity of the zebra.com Domain object with a subscription to Item and Sales Rep objects owned by the zebra.com Domain object. The adctech.com Domain object is also a Member object as a Developer entity of the zebra.com Domain object with a subscription to Entity objects owned by the zebra.com Domain object.

Entities Devices Domains Connections Sessions and Members are represented as objects within object datasets within SDS. The SDS component includes an OEP and OVG. Globally Unique Identifiers GUIDs are used as object identifiers within all object datasets in the SDS.

Tables 26 and 27 represent an ordered sequence of steps for demonstrating the sample utility. In these tables the sequence column in the table represents the sequence the device column represents the Device e.g. Device A performing the sequence step and the component column represents the component of the device e.g. agent identified in the device column that performs the sequence step. The Automation column describes the sequence step being performed.

Through an embodiment of the disclosed database driven entity framework the demonstration in Table 26 illustrates how a user on a smartphone Device C creates an aggregate Printer Entity object and an aggregate QL420 Model object assigned to the Printer Entity object and how those objects are transported as SPTP Events datasets to a vendor s cloud server Device A and stored within its SDS. It further illustrates how automation generates a QL420 Printer Item object based on the new QL420 Model object and associated Printer Entity object and transports the new aggregate Printer Entity object and new QL420 Printer Item object as a SPTP Events dataset to a customer s cloud server Device B based on a subscription and replicates these objects within its SDS.

The demo also illustrates how the booting of an un provisioned printer Device D transports its Device object identifier and Model object identifier which is the identity of the new QL420 model object and current attribute settings of the printer as a SPTP Events dataset to the vendor s cloud server Device A to be stored as a new 00 B0 . . . Device object within its SDS. It further illustrates how automation generates a new 00 B0 . . . Item Serial Number object based on the 00 B0 . . . Device object and generates nested datasets within a program and application dataset from object datasets in the SDS and transports the program and application datasets to the printer Device D . Device D stores the program and application datasets in firmware and processes them using its command processor to control the printer and render a user interface for the printer s control panel.

This demonstration of the sample utility also illustrates how the program and application datasets and current attribute settings of the printer can be transported as a collection of datasets from the printer Device D to the smartphone Device C which processes the datasets using its command processor to render a user interface for a printer s control panel. It further illustrates how the user can change attribute settings of the printer using the printer s control panel rendered on the smartphone Device C and transport the setting changes as an SPTP Events dataset to the printer Device D which processes the rows in SPTP Events to update its attribute settings.

Through an embodiment of the disclosed database driven entity framework the demonstration in Table 27 illustrates how an automated process can generate a new aggregate Purchase Order object from an SPTP Events dataset on a customer s cloud server B which is stored within its SDS. The automation then generates a mirrored aggregate Sales Order object that is transported as an SPTP Events dataset to a vendor s cloud server A which is then stored within its SDS. The automation then generates a new Task object within its SDS from rows in an SPTP Events dataset. The automation then generates a mirrored Task object that is transported as an SPTP Events dataset to a smartphone C which is then stored within its SDS.

The demo also illustrates how the mirrored Task object can be rendered to the user on the smartphone C using its command processor to process its program dataset. It further illustrates how a new Shipment object view linked to the Task object can be rendered to the user. The user can fulfill the Sales Order using the rendered Shipment object view and the new aggregate Shipment object is transported as a SPTP Events dataset to the vendor s cloud server A and stored within its SDS.

The automation then invokes a disparate carrier web service to initiate pickup generates a shipping label object view of the aggregate Shipment object and transports the object view to the printer C which prints a shipping label and broadcasts an out of paper status as a row in an SPTP Events dataset which generates a Task object. The automation then generates a mirrored aggregate Receipt object that is transported as an SPTP Events dataset to a customer s cloud server B which is then stored within its SDS.

The SPTP Events dataset processed by the OEP in Sequence 1.4 and 2.3 in Table 26 is illustrated in Table 28.

The OEP creates a Printer Entity object by processing RIs 1 through 2 in the SPTP Events dataset as illustrated in Table 29.

The OEP creates child Attribute objects of the Printer Entity object by processing RIs 2 through 10 in the SPTP Events dataset as illustrated in Table 30.

The OEP creates child Attribute Value objects of the Attribute objects by processing RIs 11 through 16 in the SPTP Events dataset as illustrated in Table 31.

As the Printer Entity object is a new master entity from a triggered action the OEP creates a Dataset object with the Dataset object identifier set to the Printer Entity object identifier 4132 . . . as illustrated in Table 32.

From a triggered action the OEP creates a Printer object dataset within SDS that is referenceable by the Printer Entity object identifier 4132 . . . as illustrated in Table 33. From a triggered action the OEP also creates additional elements within the Printer object dataset corresponding to child Attribute objects of the Printer Entity object with each additional element referenceable by the corresponding child Attribute object identifier e.g. 9E28 . . . .

The OEP creates a QL420 Model object by processing RIs 0 through 1 in the SPTP Events dataset as illustrated in Table 35.

In Sequence 3.4 and 4.3 in Table 26 the OEP processes the additional rows RI 10 through 11 in the SPTP Events dataset to create a QL420 Printer Item object from dataset elements in the QL420 Model object and associated Printer Entity object as illustrated in Table 37. The QL420 Printer Item object identifier set to the QL420 Model object identifier.

This demonstration of the sample utility also illustrates how the program and application datasets The OEP creates child Model Attribute objects of the QL420 Model object by processing RIs 2 through 5 in the SPTP Events dataset as illustrated in Table 38.

This demonstration of the sample utility also illustrates how the program and application datasets The OEP creates child Model Attribute Value objects of the Model Attribute objects by processing RIs 6 through 9 in the SPTP Events dataset as illustrated in Table 39.

The OEP creates a 00 B0 . . . Device object by processing RIs 0 through 1 in the SPTP Events dataset as illustrated in Table 41.

As the 00 B0 . . . Device object s Model element is assigned to the QL420 Model object with an Entity element assigned to the Printer Entity object from a triggered action the OEP creates additional rows in the SPTP Events dataset as illustrated in Table 42.

The OEP processes the additional rows RI 2 through 3 in the SPTP Events dataset to create a supplemental 00 B0 . . . Printer object with its object identifier set to the Device object identifier as illustrated in Table 43.

From a triggered action the OEP creates additional rows in the SPTP Events dataset as illustrated in Table 44.

The OEP processes the additional rows RI 4 through 6 in the SPTP Events dataset to create a Connection object from dataset elements in the 00 B0 . . . Device object as illustrated in Table 45.

From a triggered action the OEP creates additional rows in the SPTP Events dataset as illustrated in Table 46.

The OEP processes the additional rows RI 7 through 8 in the SPTP Events dataset to create a 00 B0 . . . Item Serial Number object from dataset elements in the 00 B0 . . . Device object with the 00 B0 . . . Item Serial Number object identifier set to the 00 B0 . . . Device object identifier and the Number element of the 00 B0 . . . Item Serial Number object set to the MAC Address of the 00 B0 . . . Device object as illustrated in Table 47.

The objects created by the OEP in Sequence 1.2 of Table 27 are illustrated in . The Purchase Order object is shown in RI 0 of the Order object dataset. The Purchase Order Item object is shown in RI 0 of the Order Item object dataset.

The mirrored rows in the SPTP Events dataset created by the OEP in Sequence 1.2 are based on element values within the Entity object dataset illustrated in . The Mirror Entity element of Purchase Order Entity object index location 13 10 is set to the object identifier of the Sales Order Entity object index location 8 0 . The Mirror Attribute element of Purchase Order Entity object index location 13 11 is set to the object identifier of the Vendor Attribute object which is shown as Column Index 3 in the Order object dataset.

The Mirror Entity element of Purchase Order Item Entity object index location 14 10 is set to the object identifier of the Sales Order Item Entity object index location 10 0 .

The mirrored Sales Order object is shown in RI 1 of the Order object dataset which can be an object dataset within an SDS on the same machine or different machine than the Purchase Order object. The mirrored Sales Order Item object is shown in RI 1 of the Order Item object dataset which can be an object dataset within an SDS on the same machine or different machine than the Purchase Order Item object.

The Owner Domain element of the mirrored Sales Order object index location 1 1 is set to the Vendor element of the Purchase Order object index location 0 3 . The Vendor column of the Order object dataset also stores element values for the Customer attribute of the Sales Order Entity object. The Vendor element of the mirrored Sales Order object index location 1 3 is set to the Owner Doman element of the Purchase Order object index location 0 1 .

The Object Identifier element of the mirrored Sales Order object index location 1 0 is set to the Object Identifier element of the Purchase Order object index location 0 0 .

The Date element and other elements of the mirrored Sales Order object are set to the corresponding element values of the Purchase Order object.

The Object Entity of the Sales Order object is set to the Mirror Entity element of the Purchase Order Entity object at index location 13 10 .

The system preferably includes one or more processors such as processor . Additional processors may be provided such as an auxiliary processor to manage input output an auxiliary processor to perform floating point mathematical operations a special purpose microprocessor having an architecture suitable for fast execution of signal processing algorithms e.g. digital signal processor a slave processor subordinate to the main processing system e.g. back end processor an additional microprocessor or controller for dual or multiple processor systems or a coprocessor. Such auxiliary processors may be discrete processors or may be integrated with the processor . Examples of processors which may be used with system include without limitation the Pentium processor Core i7 processor and Xeon processor all of which are available from Intel Corporation of Santa Clara Calif.

The processor is preferably connected to a communication bus . The communication bus may include a data channel for facilitating information transfer between storage and other peripheral components of the system . The communication bus further may provide a set of signals used for communication with the processor including a data bus address bus and control bus not shown . The communication bus may comprise any standard or non standard bus architecture such as for example bus architectures compliant with industry standard architecture ISA extended industry standard architecture EISA Micro Channel Architecture MCA peripheral component interconnect PCI local bus or standards promulgated by the Institute of Electrical and Electronics Engineers IEEE including IEEE 488 general purpose interface bus GPIB IEEE 696 S 100 and the like.

System preferably includes a main memory and may also include a secondary memory . The main memory provides storage of instructions and data for programs executing on the processor such as one or more of the functions and or modules discussed above. It should be understood that programs stored in the memory and executed by processor may be written and or compiled according to any suitable language including without limitation C C Java JavaScript Perl Visual Basic .NET and the like. The main memory is typically semiconductor based memory such as dynamic random access memory DRAM and or static random access memory SRAM . Other semiconductor based memory types include for example synchronous dynamic random access memory SDRAM Rambus dynamic random access memory RDRAM ferroelectric random access memory FRAM and the like including read only memory ROM .

The secondary memory may optionally include an internal memory and or a removable medium for example a floppy disk drive a magnetic tape drive a compact disc CD drive a digital versatile disc DVD drive other optical drive a flash memory drive etc. The removable medium is read from and or written to in a well known manner. Removable storage medium may be for example a floppy disk magnetic tape CD DVD SD card etc.

The removable storage medium is a non transitory computer readable medium having stored thereon computer executable code i.e. software and or data. The computer software or data stored on the removable storage medium is read into the system for execution by the processor .

In alternative embodiments secondary memory may include other similar means for allowing computer programs or other data or instructions to be loaded into the system . Such means may include for example an external storage medium and an interface . Examples of external storage medium may include an external hard disk drive or an external optical drive or and external magneto optical drive.

Other examples of secondary memory may include semiconductor based memory such as programmable read only memory PROM erasable programmable read only memory EPROM electrically erasable read only memory EEPROM or flash memory block oriented memory similar to EEPROM . Also included are any other removable storage media and communication interface which allow software and data to be transferred from an external medium to the system .

System may include a communication interface . The communication interface allows software and data to be transferred between system and external devices e.g. printers networks or information sources. For example computer software or executable code may be transferred to system from a network server via communication interface . Examples of communication interface include a built in network adapter network interface card NIC Personal Computer Memory Card International Association PCMCIA network card card bus network adapter wireless network adapter Universal Serial Bus USB network adapter modem a network interface card NIC a wireless data card a communications port an infrared interface an IEEE 1394 fire wire or any other device capable of interfacing system with a network or another computing device.

Communication interface preferably implements industry promulgated protocol standards such as Ethernet IEEE 802 standards Fiber Channel digital subscriber line DSL asynchronous digital subscriber line ADSL frame relay asynchronous transfer mode ATM integrated digital services network ISDN personal communications services PCS transmission control protocol Internet protocol TCP IP serial line Internet protocol point to point protocol SLIP PPP and so on but may also implement customized or non standard interface protocols as well.

Software and data transferred via communication interface are generally in the form of electrical communication signals . These signals are preferably provided to communication interface via a communication channel . In one embodiment the communication channel may be a wired or wireless network or any variety of other communication links. Communication channel carries signals and can be implemented using a variety of wired or wireless communication means including wire or cable fiber optics conventional phone line cellular phone link wireless data communication link radio frequency RF link or infrared link just to name a few.

Computer executable code i.e. computer programs or software such as the disclosed application is stored in the main memory and or the secondary memory . Computer programs can also be received via communication interface and stored in the main memory and or the secondary memory . Such computer programs when executed enable the system to perform the various functions of the disclosed embodiments as previously described.

In this description the term computer readable medium is used to refer to any non transitory computer readable storage media used to provide computer executable code e.g. software and computer programs to the system . Examples of these media include main memory secondary memory including internal memory removable medium and external storage medium and any peripheral device communicatively coupled with communication interface including a network information server or other network device . These non transitory computer readable mediums are means for providing executable code programming instructions and software to the system .

In an embodiment that is implemented using software the software may be stored on a computer readable medium and loaded into the system by way of removable medium I O interface or communication interface . In such an embodiment the software is loaded into the system in the form of electrical communication signals . The software when executed by the processor preferably causes the processor to perform the inventive features and functions previously described herein.

In an embodiment I O interface provides an interface between one or more components of system and one or more input and or output devices. Example input devices include without limitation keyboards touch screens or other touch sensitive devices biometric sensing devices computer mice trackballs pen based pointing devices and the like. Examples of output devices include without limitation cathode ray tubes CRTs plasma displays light emitting diode LED displays liquid crystal displays LCDs printers vacuum florescent displays VFDs surface conduction electron emitter displays SEDs field emission displays FEDs and the like.

The system also includes optional wireless communication components that facilitate wireless communication over a voice and over a data network. The wireless communication components comprise an antenna system a radio system and a baseband system . In the system radio frequency RF signals are transmitted and received over the air by the antenna system under the management of the radio system .

In one embodiment the antenna system may comprise one or more antennae and one or more multiplexors not shown that perform a switching function to provide the antenna system with transmit and receive signal paths. In the receive path received RF signals can be coupled from a multiplexor to a low noise amplifier not shown that amplifies the received RF signal and sends the amplified signal to the radio system .

In alternative embodiments the radio system may comprise one or more radios that are configured to communicate over various frequencies. In one embodiment the radio system may combine a demodulator not shown and modulator not shown in one integrated circuit IC . The demodulator and modulator can also be separate components. In the incoming path the demodulator strips away the RF carrier signal leaving a baseband receive audio signal which is sent from the radio system to the baseband system .

If the received signal contains audio information then baseband system decodes the signal and converts it to an analog signal. Then the signal is amplified and sent to a speaker. The baseband system also receives analog audio signals from a microphone. These analog audio signals are converted to digital signals and encoded by the baseband system . The baseband system also codes the digital signals for transmission and generates a baseband transmit audio signal that is routed to the modulator portion of the radio system . The modulator mixes the baseband transmit audio signal with an RF carrier signal generating an RF transmit signal that is routed to the antenna system and may pass through a power amplifier not shown . The power amplifier amplifies the RF transmit signal and routes it to the antenna system where the signal is switched to the antenna port for transmission.

The baseband system is also communicatively coupled with the processor . The central processing unit has access to data storage areas and . The central processing unit is preferably configured to execute instructions i.e. computer programs or software that can be stored in the memory or the secondary memory . Computer programs can also be received from the baseband processor and stored in the data storage area or in secondary memory or executed upon receipt. Such computer programs when executed enable the system to perform the various functions of the disclosed embodiments as previously described. For example data storage areas may include various software modules not shown .

Various embodiments may also be implemented primarily in hardware using for example components such as application specific integrated circuits ASICs or field programmable gate arrays FPGAs . Implementation of a hardware state machine capable of performing the functions described herein will also be apparent to those skilled in the relevant art. Various embodiments may also be implemented using a combination of both hardware and software.

Furthermore those of skill in the art will appreciate that the various illustrative logical blocks modules circuits and method steps described in connection with the above described figures and the embodiments disclosed herein can often be implemented as electronic hardware computer software or combinations of both. To clearly illustrate this interchangeability of hardware and software various illustrative components blocks modules circuits and steps have been described above generally in terms of their functionality. Whether such functionality is implemented as hardware or software depends upon the particular application and design constraints imposed on the overall system. Skilled persons can implement the described functionality in varying ways for each particular application but such implementation decisions should not be interpreted as causing a departure from the scope of the invention. In addition the grouping of functions within a module block circuit or step is for ease of description. Specific functions or steps can be moved from one module block or circuit to another without departing from the invention.

Moreover the various illustrative logical blocks modules functions and methods described in connection with the embodiments disclosed herein can be implemented or performed with a general purpose processor a digital signal processor DSP an ASIC FPGA or other programmable logic device discrete gate or transistor logic discrete hardware components or any combination thereof designed to perform the functions described herein. A general purpose processor can be a microprocessor but in the alternative the processor can be any processor controller microcontroller or state machine. A processor can also be implemented as a combination of computing devices for example a combination of a DSP and a microprocessor a plurality of microprocessors one or more microprocessors in conjunction with a DSP core or any other such configuration.

Additionally the steps of a method or algorithm described in connection with the embodiments disclosed herein can be embodied directly in hardware in a software module executed by a processor or in a combination of the two. A software module can reside in RAM memory flash memory ROM memory EPROM memory EEPROM memory registers hard disk a removable disk a CD ROM or any other form of storage medium including a network storage medium. An exemplary storage medium can be coupled to the processor such that the processor can read information from and write information to the storage medium. In the alternative the storage medium can be integral to the processor. The processor and the storage medium can also reside in an ASIC.

Any of the software components described herein may take a variety of forms. For example a component may be a stand alone software package or it may be a software package incorporated as a tool in a larger software product. It may be downloadable from a network for example a website as a stand alone product or as an add in package for installation in an existing software application. It may also be available as a client server software application as a web enabled software application and or as a mobile application.

The above description of the disclosed embodiments is provided to enable any person skilled in the art to make or use the invention. Various modifications to these embodiments will be readily apparent to those skilled in the art and the general principles described herein can be applied to other embodiments without departing from the spirit or scope of the invention. Thus it is to be understood that the description and drawings presented herein represent a presently preferred embodiment of the invention and are therefore representative of the subject matter which is broadly contemplated by the present invention. It is further understood that the scope of the present invention fully encompasses other embodiments that may become obvious to those skilled in the art and that the scope of the present invention is accordingly not limited.


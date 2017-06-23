---

title: Management system and control method
abstract: A job history processing server issues second agent information for use of when first agent information cannot be acquired from an agent management server. Then, the job history processing server exports, as incomplete information, data received from a collection agent together with the issued second agent information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09423992&OS=09423992&RS=09423992
owner: Canon Kabushiki Kaisha
number: 09423992
owner_city: Tokyo
owner_country: JP
publication_date: 20150818
---
The present invention relates to the control of a management system for receiving data to be collected from an agent operating on a network device such as an image forming apparatus or an information processing apparatus.

In recent years with the spread of printers and digital multifunction peripherals MFPs there is a digital MFP for saving job history information in a storage device to prevent the leakage of information or to trace an information leaker when a job such as a print copy FAX or electronic mail transmission job is executed. Further it is also possible to add a function to a printer driver and save job history information in a storage device when a printing job from a print client personal computer PC is executed.

The job history information includes information about a user having executed the job information about the date and time of the execution of the job information an Internet Protocol IP address a serial number or a media access control MAC address for identifying a digital MFP or a print client PC having executed the job and log attribute information such as the type of the executed job. The job history information may further include image data which is obtained by forming data from an image input to the digital MFP or is obtained by forming data from a print target in the print client PC and reduced image data which is obtained by reducing the image data.

A job history information processing system for processing such job history information includes the digital MFP the print client PC and the like i.e. a job history processing server and an agent management server.

In the digital MFP and the print client PC a client application hereinafter referred to as a collection agent for transmitting job history information recorded by the digital MFP or the printer driver to the job history processing server is installed.

Further the job history processing server is a management system having an image processing function and a function of saving job history information in a storage device. Further the agent management server has a function of saving setting information of the collection agent and information for issuing unique identification information in the system to the collection agent.

In such a job history information processing system if the agent management server is stopped it becomes not possible to issue unique identification information in the system to the collection agent.

As discussed in the publication of Japanese Patent Application Laid Open No. 2006 166040 in a case where a server is stopped it is possible to substitute a temporary server for the function of the server. The publication of Japanese Patent Application Laid Open No. 2006 166040 is also directed to communicating with a server closest to the destination of a mobile terminal and has a necessary function as a temporary server whereby the throughput and response time are improved.

As described above in the job history information processing system in a case where the agent management server is stopped for some cause it becomes not possible to issue unique identification information in the system to the collection agent. In the job history information processing system in a case where the agent management server is stopped it becomes not possible to perform a process where issuing of unique identification information is required for example a process of registering the collection agent in the agent management server.

In a conventional job history processing server it is not possible to receive data transfer from a collection agent to which identification information has not been issued and perform processing. The reason for this is as follows. Job history information that is not associated with identification information of an agent is insufficient as information for identifying a collection agent a digital MFP or a PC having executed a job. Thus such job history information prevents an external system such as a job history checking system from referencing information.

For this reason in a case where the agent management server is stopped for example the job history processing server cannot receive job history information of a network device such as a digital MFP or a printer even though the network device is newly placed. Consequently it is not possible to practically use the network device due to a security issue. This is because of the security problem that if the network device is used in such a state it becomes not possible to transfer job history to an external system such as a job history checking system and therefore it is not possible to trace the leakage of information.

The system discussed in the publication of Japanese Patent Application Laid Open No. 2006 166040 has a configuration in which it is not necessary to issue unique identification information. Thus the system cannot be applied to a job history information processing system for strictly managing identification information of a collection agent.

The present invention is directed to providing a mechanism for for example even in a case where a failure occurs in a service for managing an agent receiving data from a network device that is transmitted from the agent and allowing the use of the network device in a state where traceability of when information is leaked is ensured.

According to an aspect of the present invention a management system for receiving data to be collected from an agent operating on a network device includes an issuance unit configured to issue second agent information for use of when first agent information cannot be acquired from an agent management service a reception unit configured to receive a data transfer reservation request including identification information of an agent a request unit configured to request from the agent management service the first agent information corresponding to the identification information included in the reservation request and an output unit configured to in a case where the first agent information is acquired from the agent management service export data received from the agent together with the acquired first agent information to an area where the data and the first agent information can be referenced by an external system wherein in a case where the first agent information cannot be acquired from the agent management service the output unit exports as incomplete information data received from the agent together with the second agent information issued by the issuance unit to an area where the data and the second agent information can be referenced by the external system.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Exemplary embodiments of the invention will be described in detail below with reference to the drawings.

The agent management server corresponds to an agent management service for managing a collection agent and has a function of saving setting information of the collection agent illustrated in . Further the agent management server holds information for issuing unique identification information in the system for the collection agent . An example of the information for issuing unique identification information in the system is illustrated in .

According to the present exemplary embodiment an application is not present in the agent management server the job history processing server references information saved in the agent management server and performs processing. That is only a folder and a file are present in the agent management server and the job history processing server references the folder and the file and performs processing. Alternatively an application for performing part or all of the processing performed by the job history processing server according to the present exemplary embodiment may be installed in the agent management server .

The job history processing server is a management system having an issuance function a reception function an image processing function and a saving function.

The issuance function is a function of referencing the information for issuing unique identification information in the system held in the agent management server and issuing unique identification information in the system.

The reception function is a function of receiving job history information from the collection agent . The job history information received by the reception function is subjected to a data conversion process by the image processing function and then is saved by the saving function.

The image processing function is a function of performing a data conversion process on job history information received by the reception function. The data conversion process is a process of performing an optical character recognition OCR process on image data to extract text information and converting the format of the image data. The text information obtained by the data conversion process is saved in such a manner that the text information is associated with the job history information and the text information is used for searching the job history information.

The saving function is a function of saving in a database or the like job history information subjected to data conversion by the image processing function and text information and the like associated with the job history information. According to the present exemplary embodiment a folder in an external memory of the job history processing server are used for the saving function. Alternatively any unit such as a database or middleware capable of saving job history information may be used for the saving function. Further the location where the saving function saves data may be a storage area in an external system such as a job history checking system having the function of storing and searching data to check job history. The location where the saving function saves data may only need to have a storage area where the data can be referenced by an external system such as a job history checking system.

Each of the digital MFPs is an MFP having functions for example scan print copy electronic mail and FAX and having a function of recording job history information relating to a job executed on the digital MFP . According to the present exemplary embodiment the job history information is recorded for example simultaneously with the execution of the job. The present invention however is not limited to this.

Further a collection agent is installed as a client application in the digital MFP . In a case where a job is executed the digital MFP temporarily saves job history information in a storage area e.g. a hard disk drive HDD illustrated in on the digital MFP . Then when the collection agent receives a transmission instruction or immediately after a transmission time arrives the collection agent transmits the job history information to the job history processing server . According to the present exemplary embodiment a description is given using the digital MFP in which the collection agent is implemented. Alternatively an image forming apparatus capable of submitting a print job to a printer e.g. an information processing apparatus such as a PC capable of acquiring job history information by adding a function of a printer driver may be used.

The HDD saves system software a program for the collection agent job history information and image data in a user box. The program saved in the HDD is loaded into the RAM and executed. The processing of the collection agent in each flowchart described below can be achieved in such a manner that the CPU executes a program for the collection agent the program being saved in the HDD . Instead of the HDD another storage device such as a solid state drive SSD may be used.

An operation unit interface I F is an interface unit with an operation unit and outputs screen data to be displayed on the operation unit to the operation unit . Further the operation unit I F serves to transmit to the CPU information input by an operator through the operation unit . It does not matter whether the operation unit is a screen placed in the digital MFP or a screen provided remotely to an external device such as a PC a remote user interface UI displayed on a display illustrated in by a program in the digital MFP .

A network unit Network connects to a network LAN and inputs and outputs information. A modem MODEM connects to a public line WAN and inputs and outputs image data and digital MFP information.

An image processing unit performs the process of rasterizing a page description language PDL code into a bitmap image and image processing such as correction processing and editing on input image data or output image data. Specifically the image processing unit performs a rotation process a compression decompression process and a resolution conversion process on image data.

A device I F unit connects a scanner unit and a printer unit which are image input and output devices to the controller unit via an image input unit interface and a printing unit interface and converts image data.

In a CPU executes programs for an operating system and an application that are stored in a program ROM in a ROM or loaded from the external memory into a RAM thereby achieving various types of control. The processing of each flowchart described below can be achieved by the CPU executing these programs.

The RAM functions as a main memory or a work area for the CPU . A keyboard controller controls a key input from a keyboard or a pointing device not illustrated . A display controller controls the display of various displays . A disk controller controls data access in the external memory such as an HDD or a Universal Serial Bus USB storage medium for storing various types of data. As the external memory another storage device such as an SSD may be used. A network card NC is connected to the network and performs the process of controlling communication with another device connected to the network .

In the software configuration of the digital MFP the digital MFP includes a digital MFP controller not illustrated and the collection agent .

The digital MFP controller not illustrated is implemented as a program system software saved in the ROM or the HDD and functions in such a manner that the CPU executes the program. The digital MFP controller controls the entire system of the digital MFP . Further the digital MFP controller executes a job based on an instruction received from a user through the operation unit I F . When executing the job the digital MFP controller generates job history information and saves the job history information in the HDD . The job history information is for example log information of the job executed by the digital MFP the log information including an image to be input or output according to the type of the job a job history image and job history attribute information having information about for example the date and time of the execution of the job and a user having executed the job. As described above the job history information is recorded by the digital MFP .

The collection agent is implemented as a program installed in the digital MFP a program saved in the HDD and functions in such a manner that the CPU executes the program.

In the collection agent a main control unit controls the entire collection agent and instructs and manages components described later. The main control unit gives a communication instruction to a communication control unit a setting control instruction to a setting control unit according to the content of a user instruction through a UI control unit and a job history information control instruction to a job history information control unit .

The communication control unit transmits job history information setting information and a processing request to the job history processing server and receives a response from the job history processing server .

The UI control unit performs overall control of processing relating to a user operation in the collection agent . Specifically the UI control unit displays a UI on the operation unit of the digital MFP or displays on a display a screen a remote UI provided remotely to an external device such as a PC and transfers to the main control unit the content of an instruction received from the user.

The setting control unit controls setting information such as an operating condition relating to the collection agent . The setting control unit receives an instruction to set an operating condition from the UI control unit via the main control unit references and saves setting information via a file operation unit and transmits the setting information to the job history processing server via the communication control unit . The setting information to be referenced and saved by the setting control unit includes identification information an agent identification ID of the collection agent an agent name and a MAC address or a serial number for identifying a digital MFP having executed a job. Further the setting information may also include a status and a schedule for transmitting job history information to the job history processing server . The setting control unit updates the setting information at a predetermined timing such as when the setting control unit receives a change instruction from the user through the UI control unit and when the collection agent inquires of the job history processing server about the latest information at regular intervals.

According to an instruction from the main control unit the job history information control unit acquires job history information via the file operation unit and transmits the job history information to the job history processing server via the communication control unit .

The file operation unit is a control unit for inputting and outputting setting information image data and job history information in the HDD and receives a processing request from each component thereby performing processing.

In the job history processing server a main control unit controls the entire job history processing server and instructs and manages components described below.

A communication control unit receives job history information and setting information from the communication control unit of the collection agent and also transmits a response to a processing request from the collection agent . The job history information received by the communication control unit is saved in a saving unit via the main control unit and a setting control unit . Further the setting information received by the communication control unit is transferred to the setting control unit via the main control unit .

A UI control unit displays a user interface on the display of the job history processing server and receives an instruction from the user through the keyboard or a pointing device not illustrated . Setting information specified by the user is saved in the saving unit via the main control unit and the setting control unit .

The setting control unit controls the job history processing server and identification information of the collection agent and setting information relating to the operation of the collection agent . The setting control unit receives via the main control unit a request to register the collection agent in the system references the information for issuing unique identification information in the system in the agent management server issues identification information of the collection agent and then saves the identification information in the saving unit . Further the setting control unit receives an instruction to set an operation from the user or the collection agent via the main control unit and saves the setting information in the saving unit .

A job history information control unit receives via the main control unit an instruction to reference and store job history information and controls job history information according to the instruction.

An image processing unit performs an OCR process on job history information image data and converts the image format of the image data according to an instruction from the job history information control unit .

A file operation unit receives an instruction from each control unit and references and saves identification information setting information and job history information in the saving unit .

The saving unit is a storage device corresponds to the external memory of the job history processing server illustrated in in the present exemplary embodiment and saves identification information setting information and job history information. The saving unit may only need to be a storage area where the identification information the setting information and the job history information can be referenced by an external system such as a job history checking system. The saving unit may be present on any of the apparatuses.

In step S the UI control unit acquires communication server information from the user through the operation unit of the digital MFP or a screen provided remotely to an external device such as a PC and saves the communication server information in the HDD . Specifically the UI control unit displays on the operation unit or the display of the PC a screen for urging the user to input the IP address or the host name of a communication server and waits for an input from the user. In a case where the user inputs information about the communication server the UI control unit acquires the input value via the operation unit I F or the keyboard controller and transfers the input value to the main control unit . The main control unit instructs the setting control unit to save in the HDD via the file operation unit the information about the communication server input by the user. According to the present exemplary embodiment as illustrated in the information about the communication server is held as a file together with setting information of the collection agent and saved as the value of a tag.

In step S the main control unit transmits an agent registration request together with the setting information to the job history processing server via the communication control unit . The agent registration request is performed to request the job history processing server to perform the process of registering the collection agent in the system. Specifically the job history processing server is requested to issue unique collection agent identification information in the system and save the setting information of the collection agent in the agent management server or the saving unit .

As described above the setting information includes an agent name a MAC address or a serial number for identifying a digital MFP having executed a job a status and a schedule for transmitting job history information to the job history processing server . According to the present exemplary embodiment the agent registration request and the setting information are simultaneously transmitted. Alternatively communication in different sequences the process of calling different application programming interfaces APIs may be performed.

In step S the communication control unit receives a response from the job history processing server . The received response includes the success or failure in response to the agent registration request and identification information final identification information or temporary identification information of the collection agent issued by the job history processing server .

In step S the communication control unit confirms the content of the response received in step S and determines whether the agent registration request is in an agent management server access error . In this determination in a case where the received response includes information indicating an agent management server access error it is determined that the agent registration request is in an agent management server access error .

Then in a case where it is determined that the agent registration request is in an agent management server access error YES in step S the processing proceeds to step S.

In step S the communication control unit saves the identification information included in the response received in step S as temporary identification information in the HDD via the file operation unit . An example of the data to be saved is illustrated in .

In the example illustrated in the temporary identification information is saved as A in an tag. According to the present exemplary embodiment temporary identification information and final identification information are saved and managed in the same tag but may be saved and managed in different tags.

In step S the communication control unit sets an agent management server unusable flag on and the processing of this flowchart ends.

The agent management server unusable flag may be information held on a memory the RAM . Alternatively the agent management server unusable flag may be saved as a file in the HDD and determined based on the presence or absence of the file. Yet alternatively some value may be saved in a database. Further information for determining the on off state of the flag may be a numerical value of 0 or 1 bit or may be text such as yes or no. According to the present exemplary embodiment the agent management server unusable flag is saved as part of the setting information in the HDD via the file operation unit . Specifically in the example of the agent management server unusable flag is managed as a value of on or off in an tag.

In a case where on the other hand it is determined in step S that the agent registration request is not in an agent management server access error NO in step S the processing proceeds to step S.

In step S the communication control unit saves the identification information included in the response received in step S as final identification information in the HDD via the file operation unit and the processing of this flowchart ends. As described above in step S according to the present exemplary embodiment temporary identification information and final identification information are saved in the same tag and therefore the final identification information is saved as the value of the tag illustrated in .

In step S the communication control unit receives an agent registration request from the collection agent . The communication control unit also simultaneously receives setting information transmitted from the collection agent in step S in .

In step S the communication control unit instructs via the main control unit the setting control unit to issue final identification information and save in the agent management server the final identification information and the setting information received in step S. According to the instruction the setting control unit accesses the agent management server references the information for issuing unique identification information in the system held in the agent management server and issues final identification information. In the example illustrated in the value of the tag as the information for issuing unique identification information in the system is 5 and therefore the setting control unit counts up this value by 1 to issue 6 as the final identification information. In a case where the issuance of the final identification information is successful the setting control unit saves the final identification information in the external memory of the agent management server in such a manner that the final identification information is associated with the setting information received in step S. An example of the data saving the final identification information is AgentID in .

In step S the setting control unit determines whether the saving process in step S is successful or failed.

Then in a case where it is determined that the saving process in step S is successful NO in step S the processing proceeds to step S.

In step S the setting control unit transmits to the collection agent via the main control unit and the communication control unit information indicating the success of the agent registration process and the final identification information and the processing of this flowchart ends.

In a case where on the other hand it is determined that the process of step S is failed YES in step S the processing proceeds to step S.

The agent management server unusable flag may be information held on a memory the RAM of the job history processing server . Alternatively the agent management server unusable flag may be saved as a file in the external memory of the job history processing server and determination is performed based on the presence or absence of the file. Yet alternatively some value may be saved in a database. Further information for determining the on off state of the flag may be a numerical value of 0 or 1 bit or may be text such as yes or no. According to the present exemplary embodiment the agent management server unusable flag is saved as part of setting information of the job history processing server in the external memory via the file operation unit . Specifically in the agent management server unusable flag is managed as a value of on or off in a tag.

In step S the setting control unit issues temporary identification information. The setting control unit confirms whether existing temporary identification information is present. In a case where existing temporary identification information is present the setting control unit issues temporary identification information using a value that makes the identification information unique. The temporary identification information may be a simple numerical value or may be a value e.g. a MAC address or a serial number in the setting information received from the collection agent in step S. Further the temporary identification information may be a value obtained by combining a value in the setting information with the current date and time.

In step S the setting control unit saves the temporary identification information issued in step S and the setting information received from the collection agent in step S in such a manner that the temporary identification information and the setting information are associated with each other. At this saving process the setting control unit saves the temporary identification information and the setting information in the saving unit via the file operation unit .

In the temporary identification information is saved as A in an tag. Further as the setting information information such as the serial number and the IP address of the digital MFP in which the collection agent is installed the status of the collection agent and a schedule for transferring job history information is saved.

In step S the setting control unit transmits information indicating an agent management server access error and the temporary identification information to the collection agent via the main control unit and the communication control unit and the processing of this flowchart ends.

In step S the communication control unit confirms the agent management server unusable flag the value of the tag in .

In step S the communication control unit determines whether the agent management server unusable flag is on.

Then if it is determined that the agent management server unusable flag is off NO in step S the processing proceeds to step S.

In step S the communication control unit transmits a data transfer reservation together with final identification information saved in step S in to the job history processing server . The data transfer reservation refers to the process of notifying the job history processing server that job history information is to be transmitted to the job history processing server . In this process preparations are performed in order that the job history processing server appropriately processes a sequence in which the collection agent transmits job history information. The details will be described below with reference to . The communication control unit identifies the job history processing server as the transmission destination using the information about a communication server saved in step S in . At this process the final identification information saved in step S in is also simultaneously transmitted whereby the job history processing server becomes capable of identifying the collection agent .

In step S the communication control unit receives a response from the job history processing server . At this process the response includes at least the success or failure of the data transfer reservation process and a connection ID. The connection ID is information for the job history processing server to manage the sequence of the job history information transmission process. This connection ID is used until the current job history information transmission process is completed. Thus the communication control unit needs to hold the connection ID on a memory the RAM or the HDD .

In step S the communication control unit confirms the content of the response received in step S and determines whether the data transfer reservation process is successful.

Then in a case where it is determined that the data transfer reservation process is failed NO in step S then in step S the communication control unit performs an error process. The details will be described later.

In a case where on the other hand it is determined in step S that the data transfer reservation process is successful YES in step S the processing proceeds to step S.

In step S the communication control unit transmits job history information together with the connection ID received in step S to the job history processing server . The job history information is acquired from the job history information control unit via the main control unit by the communication control unit . The job history information control unit acquires the job history information from the HDD via the file operation unit . Further in the process of transmitting the job history information the communication control unit transmits log attribute information included in the job history information and image data according to a prescribed sequence. In a case where the data size is large as in image data it is possible to perform transmission in such a manner that the image data is divided into pages or the image data is divided into smaller data sizes.

In step S the communication control unit receives a response from the job history processing server . This response includes at least the success or failure of the job history information transmission process.

In step S the communication control unit confirms the content of the response received in step S and determines whether the job history information transmission process is successful.

Then in a case where it is determined that the job history information transmission process is failed NO in step S then in step S the communication control unit performs an error process. The details will be described later.

In a case where on the other hand it is determined in step S that the job history information transmission process is successful YES in step S the processing proceeds to step S.

In step S the communication control unit transmits a data conversion process request together with the connection ID received in step S to the job history processing server . The data conversion process request is made to request the job history processing server to perform an OCR process on the job history information image data transmitted in step S and convert the image format of the image data.

In step S the communication control unit receives a response from the job history processing server . This response includes at least the success or failure of the data conversion process request process.

In step S the communication control unit confirms the content of the response received in step S and determines whether the data conversion process request process is successful.

Then in a case where it is determined that the data conversion process request process is failed NO in step S then in step S the communication control unit performs an error process. The details will be described later.

In a case where on the other hand it is determined in step S that the data conversion process request process is successful YES in step S the processing proceeds to step S.

In step S the communication control unit transmits a data transfer reservation cancellation together with the connection ID received in step S to the job history processing server . The data transfer reservation cancellation is performed to cancel the data transfer reservation transmitted to the job history processing server in step S. That is the data transfer reservation cancellation is the process of notifying the job history processing server that the transmission of the job history information the sequence is completed.

In step S the communication control unit receives a response from the job history processing server . This response includes at least the success or failure of the data transfer reservation cancellation process.

In step S the communication control unit confirms the content of the response received in step S and determines whether the data transfer reservation cancellation process is successful.

Then in a case where it is determined that the data transfer reservation cancellation process is successful YES in step S the processing of this flowchart ends.

In a case where on the other hand it is determined in step S that the data transfer reservation cancellation process is failed NO in step S the processing proceeds to step S.

In step S the communication control unit performs an error process and the processing of this flowchart ends. In the error process the communication control unit varies the processing content according to the response received from the job history processing server . For example in the error process the communication control unit may release an unnecessary resource end the process of transmitting the job history information and wait for the next transmission timing. Alternatively the communication control unit may ignore the error in the response and end the process of transmitting the job history information. Further in the error process the communication control unit may display an error message on the operation unit or transmit an error email thereby notifying the user of the error.

Further in a case where it is determined in step S that the agent management server unusable flag is on YES in step S the processing proceeds to step S.

In step S the communication control unit transmits a data transfer reservation together with temporary identification information saved in step S in to the job history processing server . The process of step S is similar to that of step S except that temporary identification information saved in step S in is transmitted instead of the final identification information. Thus the process of step S is not described here.

In step S similarly to step S the communication control unit receives a response from the job history processing server .

In step S similarly to step S the communication control unit confirms the content of the response received in step S and determines whether the data transfer reservation process is successful.

Then in a case where it is determined that the data transfer reservation process is successful YES in step S the processing proceeds to step S.

In a case where on the other hand it is determined that the data transfer reservation process is failed NO in step S the processing proceeds to step S.

In step S the communication control unit determines whether information indicating agent management server recovery is included in the response received in step S. It is assumed that the information indicating agent management server recovery also includes final identification information. According to the present exemplary embodiment a notification of final identification information is given by the job history processing server . Alternatively after recognizing agent management server recovery the collection agent may perform a request for issuance of final identification information.

Then in a case where it is determined in step S that information indicating agent management server recovery is not included in the response received in step S NO in step S then in step S the communication control unit performs the above error process.

In a case where on the other hand it is determined in step S that information indicating agent management server recovery is included in the response received in step S YES in step S the processing proceeds to step S.

In step S similarly to step S in the communication control unit saves the final identification information in the HDD via the file operation unit .

In step S the communication control unit changes the agent management server unusable flag the value of the tag in to off and the processing of this flowchart ends.

In step S the communication control unit receives a data transfer reservation from the collection agent . At this process the communication control unit also receives the identification information final identification information or temporary identification information transmitted from the collection agent in step S or S in .

In step S the communication control unit confirms the agent management server unusable flag the value of the tag in and determines whether the agent management server unusable flag is on.

Then in a case where it is determined that the agent management server unusable flag is off NO in step S the processing proceeds to step S.

In step S the communication control unit accesses the agent management server and acquires setting information of the collection agent corresponding to the identification information received in step S. The setting information is setting information saved in step S in . If however information is added by another function or an external application after the process of step S is performed the setting information may include the added information.

In step S the communication control unit determines whether the acquisition of the setting information in step S is successful.

Then in a case where it is determined that the acquisition of the setting information is failed NO in step S the processing proceeds to step S. In step S the communication control unit performs an error process and the processing of this flowchart ends. In the error process for example the communication control unit transmits to the collection agent information indicating that the data transfer reservation process is failed .

In a case where on the other hand it is determined that the acquisition of the setting information is successful YES in step S the processing proceeds to step S.

In step S the communication control unit performs the process of issuing a connection ID. Specifically the communication control unit confirms the number of collection agents currently connected to the communication control unit . If the number is less than or equal to a prescribed value the communication control unit issues a connection ID. The connection ID may be a value such as alphanumeric characters a numerical value or a date and time or the combination of these values and may only need to be in a form with which connection to the collection agents is uniquely determinable.

In step S the communication control unit transmits to the collection agent the connection ID issued in step S.

In step S the communication control unit receives job history information from the collection agent . The job history information is information transmitted from the communication control unit of the collection agent in step S in .

In step S the communication control unit determines whether the reception of the job history information in step S is normally completed.

Then in a case where it is determined that the reception is not normally completed NO in step S the processing proceeds to step S. In step S the communication control unit performs an error process and the processing of this flowchart ends. In the error process for example the communication control unit transmits to the collection agent information indicating that the transmission of the job history information is failed .

In a case where on the other hand it is determined that the reception is normally completed YES in step S the processing proceeds to step S.

In step S the communication control unit transmits to the collection agent information indicating that the transmission of the job history information is successful .

In step S the communication control unit receives a data conversion process request from the collection agent . The details of the data conversion process request have already been described in step S in and therefore are not described here.

In step S the communication control unit adds the job history information received in step S to a data conversion process target list. The data conversion process target list is a list for managing job history information as a target to be subjected to a data conversion process. Thus in the process of adding the job history information to the data conversion process target list the communication control unit may manage identification information e.g. a connection ID associated with the job history information or may manage file information a file name or a file path of the job history information. Further the communication control unit may add to the data conversion process target list the content of the process to be performed on the job history information.

In step S the communication control unit instructs via the main control unit the job history information control unit to start a data conversion process on the job history information added to the data conversion process target list. According to the present exemplary embodiment the communication control unit performs processing until the communication control unit instructs the job history information control unit to start a data conversion process. Alternatively the communication control unit may perform processing until the process of adding the job history information to the data conversion process target list and the job history information control unit may periodically reference the data conversion process target list and start the process. Further according to the present exemplary embodiment the data conversion process performed by the job history information control unit will be described as the data conversion process performed by another process or another thread with reference to and the communication control unit is not concerned in the data conversion process. Alternatively the exemplary embodiment may be implemented such that the communication control unit waits without proceeding to the next step until the data conversion process of the job history information control unit is completed.

In step S the communication control unit determines whether the processes of steps S and S are successful.

Then in a case where it is determined that the process of at least either step S or S is failed NO in step S the processing proceeds to step S. In step S the communication control unit performs an error process and the processing of this flowchart ends. In the error process for example the communication control unit transmits to the collection agent information indicating that the data conversion process request is failed .

In a case where on the other hand it is determined that the processes of steps S and S are successful YES in step S the processing proceeds to step S.

In step S the communication control unit transmits to the collection agent information indicating that the data conversion process request is successful .

In step S the communication control unit receives a data transfer reservation cancellation. When receiving a data transfer reservation cancellation the communication control unit discards the connection ID issued in step S. At this process the transmission of the job history information includes a termination process after completion of the transmission of the job history information. In the termination process the communication control unit discards the connection ID for managing the sequence of the job history information transmission process. If a connection ID associated with job history information included in the data conversion process target list is present separately this connection ID does not need to be deleted.

In step S the communication control unit transmits to the collection agent information indicating that the process of step S the data transfer reservation cancellation is successful and the processing of this flowchart ends.

Although not illustrated in in a case where the process of step S the data transfer reservation cancellation is failed then in an error process for example the communication control unit transmits to the collection agent information indicating that the data transfer reservation cancellation is failed and the processing of this flowchart ends.

Further in a case where it is determined in step S that the agent management server unusable flag is on YES in step S the processing proceeds to step S.

In step S the communication control unit instructs via the main control unit the setting control unit to acquire setting information of the collection agent corresponding to the identification information temporary identification information received in step S and locally saved in the external memory .

In step S the communication control unit determines whether the acquisition of the setting information in step S is successful.

Then in a case where it is determined that the acquisition of the setting information in step S is successful YES in step S the processing proceeds to step S.

In a case where on the other hand it is determined that the acquisition of the setting information in step S is failed NO in step S the processing proceeds to step S.

In step S to confirm whether the communication control unit becomes able to access the agent management server the communication control unit attempts to access the agent management server .

In step S the communication control unit determines whether the access process in step S is successful.

Then in a case where it is determined that the access process in step S is failed NO in step S the processing proceeds to step S. In step S the communication control unit performs an error process and the processing of this flowchart ends. In the error process for example the communication control unit transmits to the collection agent information indicating that the data transfer reservation is failed .

In a case where on the other hand it is determined in step S that the access process in step S is successful YES in step S the processing proceeds to step S.

In step S the communication control unit acquires final identification information from the agent management server .

In step S the communication control unit changes the agent management server unusable flag to off. Specifically the communication control unit changes the value of the tag in to off.

In step S the communication control unit transmits to the collection agent information indicating agent management server recovery and the final identification information and the processing of this flowchart ends. The final identification information to be transmitted in step S is the information issued by the setting control unit in step S and acquired by the communication control unit via the main control unit . The process of issuing the final identification information has already been described in step S in and therefore is not described here.

In step S the job history information control unit acquires the data conversion process target list created in step S in .

In step S the job history information control unit determines whether a processing target is present in the data conversion process target list acquired in step S.

Then in a case where it is determined that a processing target is present YES in step S the processing proceeds to step S.

In step S the job history information control unit acquires a single piece of job history information as the processing target from the data conversion process target list and performs the data conversion process on the single piece of job history information. In the data conversion process the image processing unit receives an instruction from the job history information control unit and performs an OCR process on image data to acquire text and converts the image format of the image data. Further the image processing unit may perform resolution conversion or rotation on the image data. Further as part of the data conversion process the image processing unit may convert log attribute information into a data format that allows cooperation with another system e.g. an XML format or a comma separated values CSV format . The log attribute information includes information about a job such as information about a user having executed the job information about the date and time of the execution of the job information an IP address a serial number or a MAC address for identifying a digital MFP having executed the job and the type of the executed job. Specifically as illustrated in the log attribute information includes information identification information or an IP address that allows the identification of a collection agent and job information the type of the job the date and time of the start of the job or the result of the execution of the job .

In step S the job history information control unit saves in the saving unit via the file operation unit the result data of performing the data conversion process in step S. According to the present exemplary embodiment the result data is saved such that the log attribute information and the image data are saved in a folder in file formats such as a log attribute information file and an image data file as illustrated in . Alternatively the formats may be such that the log attribute information and the image data are saved in a database. is a diagram illustrating an example of the configuration of the job history information saved in the job history processing server .

In step S the job history information control unit confirms the agent management server unusable flag the value of the tag in and determines whether the agent management server unusable flag is on.

Then in a case where it is determined that the agent management server unusable flag is on YES in step S the processing proceeds to step S.

In a case where on the other hand it is determined that the agent management server unusable flag is off NO in step S the processing proceeds to step S.

In step S the job history information control unit creates an end file in the saving unit via the file operation unit and the processing of this flowchart ends. According to the present exemplary embodiment as illustrated in a folder is assigned to each piece of job history information and a log attribute information file an image data file and an end file are created in this folder. The end file is information indicating that the processes of steps S and S on the job history information are completed. That is the end file means that the user or another system becomes able to reference the job history information.

Specific examples of the end file include a zero byte file having a fixed file name indicating the completion of the processes a file of which the file name holds status information indicating the completion of the processes and a file in which status information indicating the completion of the processes is written or a form obtained by combining these examples .

Further in a case where the result data is saved in a database in step S information as a substitute for the end file information indicating the completion of the processes may be held as a value for a particular key to the database.

A description is given of the reason why an end file is not created in a case where it is determined in step S that the agent management server unusable flag is on.

This is because job history information using temporary identification information is too incomplete for the user to search the job history information to trace an information leaker. Specifically incomplete job history information includes temporary identification information and is insufficient as information for identifying a collection agent a digital MFP having executed a job. Essentially temporary identification information included in job history information should be promptly rewritten immediately after final identification information is issued. If however the incomplete job history information is referenced by an external system another system such as a job history checking system and copied to another location the final identification information cannot be reflected. An end file is prescribed as an external system cooperation interface in the system whereby it becomes possible to prevent another system from referencing incomplete job history information.

Further in a case where it is determined in step S that a processing target is not present NO in step S the processing of this flowchart ends.

In step S the setting control unit confirms the agent management server unusable flag the value of the tag in and determines whether the agent management server unusable flag is on.

Then in a case where it is determined that the agent management server unusable flag is off NO in step S the processing of this flowchart ends.

In a case where on the other hand it is determined in step S that the agent management server unusable flag is on YES in step S the processing proceeds to step S.

In step S the setting control unit confirms whether the setting control unit can access the agent management server . Specifically the setting control unit confirms the presence of a folder by using access information set in advance by the user. The determination of whether the setting control unit can access the agent management server may be made by creating a folder or a file instead of confirming the presence of a folder. The access information is acquired by the UI control unit displaying a dedicated screen on the display and receiving an instruction from the user through the keyboard or a pointing device not illustrated . The setting control unit receives information from the UI control unit via the main control unit . As illustrated in the access information includes at least a user name a password and a path to the agent management server for connection and may include a path to a folder or a file.

Then in a case where it is determined that the access confirmation in step S is failed NO in step S the processing of this flowchart ends.

In a case where on the other hand it is determined that the access confirmation in step S is successful YES in step S the processing proceeds to step S.

In step S the setting control unit issues final identification information and saves the final identification information and setting information in the agent management server . This process is similar in content to that described in step S in and therefore is not described in detail here. As the setting information the setting information saved in step S in is used. According to the present exemplary embodiment a file saved in the saving unit using temporary identification information the value of the tag is A as illustrated in is rewritten so that the value of the tag is 6 which is final identification information as illustrated in . Then the final identification information is saved in the agent management server . The location for saving the final identification information in the agent management server is a folder indicated by the value of a tag illustrated in .

In step S the setting control unit deletes the temporary identification information and the setting information saved in the saving unit in step S in .

In step S in the job history information saved in the saving unit in step S in i.e. the output result of exporting job history information as incomplete information including temporary agent information the setting control unit rewrites the temporary agent information as formal agent information and the processing of this flowchart ends. This rewriting process includes at least the process of rewriting temporary identification information as final identification information and may rewrite another piece of information that allows the identification of a collection agent .

The example illustrated in corresponds to the result of rewriting the value A of the tag which is the temporary identification information in the example of as 6 which is the final identification information. After the rewriting process the setting control unit creates an end file in the saving unit via the file operation unit . The end file has already been described in step S in and therefore is not described here.

As described above according to the first exemplary embodiment even if some failure occurs in a service the agent management server for managing information about an agent it is possible to collect job history from a new collection agent and export the job history as incomplete information. Further when the failure in the agent management server is removed the new collection agent is registered in the agent management server . Then based on information acquired from the agent management server the job history exported as the incomplete information is promptly complemented to obtain complete information so that it is possible to promptly transfer the job history to an external system such as a history checking system. Thus even in a case where some failure occurs in the agent management server for example the operation is enabled in a state where the security e.g. traceability when information is leaked of a newly placed digital MFP is ensured.

In a configuration has been described in which in a case where it is not possible to acquire from the agent management server the setting information of the collection agent corresponding to the identification information of the agent in step S NO in step S or NO in step S the communication control unit performs an error process and the processing of the flowchart ends. Alternatively in a case where it is not possible to acquire from the agent management server the setting information of the collection agent corresponding to the identification information of the agent in step S in NO in step S or NO in step S the communication control unit may request the setting information of the agent to the collection agent having transmitted the data transfer reservation received in step S acquires the setting information of the agent and save the acquired setting information of the agent in the saving unit . Then the processes of step S and thereafter may be performed using the setting information of the agent saved in the saving unit . That is in a case where it is not possible to acquire from the agent management server the setting information of the collection agent corresponding to the identification information of the agent included in a data transfer reservation request the communication control unit may acquire the setting information of the agent from the collection agent having transmitted the data transfer reservation request and locally save the acquired the setting information of the agent . Then the communication control unit may export data transferred from the collection agent together with the locally saved setting information of the agent to an area where the data and the setting information can be referenced by an external system such as a job history checking system.

As described above alternatively the job history processing server may include the agent management server . Even with this configuration it is possible to obtain a similar effect.

In a second exemplary embodiment a case is described where there is a plurality of job history processing servers . In the second exemplary embodiment only the differences from the first exemplary embodiment are described and components similar to those of the first exemplary embodiment are not described here.

In the system according to the second exemplary embodiment an agent management server and two or more job history processing servers are connected to a network and digital MFPs are connected to a network . The networks and are connected together via a load balancer .

The load balancer is a general network device and has a function of sorting requests from collection agents on the digital MFPs while distributing load to the job history processing servers . To achieve the process sequence of repeating successive requests and responses the load balancer has a function of generating a cookie for a received request or response attaching the cookie to the request or response and transmitting the request or response. A cookie to be attached to a request or response received from each of the job history processing servers includes at least network information the IP address or the host name of the corresponding job history processing server as the connection destination. That is the load balancer distributes to the plurality of job history processing servers the transfer destinations of data from the collection agents . Further the load balancer also has a function of interpreting server specifying information included in a request transmitted from each collection agent and transmitting the request to a specified job history processing server .

The functions of the agent management server the job history processing servers and the digital MFPs are similar to those in the first exemplary embodiment and therefore are not described here. The job history processing servers according to the second exemplary embodiment receive data to be collected from the collection agents via the load balancer .

In step S similarly to step S in the UI control unit acquires load balancer information from a user through the operation unit of the digital MFP or a screen provided remotely to an external device such as a PC and saves the load balancer information in the HDD . The process of step S is similar to that of step S in except that load balancer information is acquired instead of the communication server information. The load balancer information refers to information such as the IP address or the host name of the load balancer that allows network communication with the load balancer . According to the present exemplary embodiment the load balancer information is held as the value of the tag in . Alternatively another tag may be prepared.

In step S similarly to step S in the communication control unit receives a response from one of the job history processing servers . The response received at this process includes communication server information in addition to the success or failure of the agent registration request and identification information final identification information or temporary identification information issued by the job history processing server . The communication server information is information that allows the identification of communication information the IP address or the host name of the job history processing server to which communication is distributed by the load balancer . Specifically according to the present exemplary embodiment a cookie issued by the load balancer is used. Alternatively the job history processing server may transfer to the collection agent communication information as a response. Moreover the communication server information may be information in any form that allows the identification of the job history processing server to which communication is distributed by the load balancer .

The processes of steps S and S are similar to those of steps S and S in and therefore are not described here.

In step S the communication control unit saves in the HDD via the file operation unit the communication server information included in the response received in step S. In the communication control unit for example after the job history processing server issues temporary identification information according to the agent registration request transmitted in S the destination of data transfer is fixed to the job history processing server having issued the temporary identification information.

The processes of steps S and S are similar to those of steps S and S in and therefore are not described here.

In the description of only the differences from are described. In the first exemplary embodiment the job history processing server is the communication partner of the collection agent . In the second exemplary embodiment the load balancer is the communication partner of the collection agent .

The processes of steps S and S are similar to those of steps S and S in and therefore are not described here.

In step S similarly to step S in the communication control unit transmits a data transfer reservation to the load balancer . At this process the communication control unit identifies the transmission destination using load the balancer information of the load balancer saved in step S in .

In step S the communication control unit receives a response from the load balancer . This response includes at least communication server information in addition to the success or failure of the data transfer reservation process and a connection ID. The connection ID has been described in step S in and therefore is not described here. The communication server information is information that when the job history information is transmitted allows the identification of communication information the IP address or the host name of the job history processing server to which communication is distributed by the load balancer . The communication server information is as described in step S in a cookie issued by the load balancer and information included in the response from the job history processing server . The communication server information is information for transmitting the sequence of the job history information transmission process to the same job history processing server . Thus similarly to the connection ID the communication server information is used until the current job history information transmission process is completed. Thus the communication control unit needs to hold the communication server information on a memory the RAM or the HDD .

In step S the communication control unit transmits job history information together with the connection ID and the communication server information received in step S to the load balancer .

The processes of steps S and S are similar to those of steps S and S and therefore are not described here.

In step S the communication control unit transmits a data conversion process request together with the connection ID and the communication server information received in step S to the load balancer .

The processes of steps S and S are similar to those of steps S and S in and therefore are not described here.

In step S the communication control unit transmits a data transfer reservation cancellation together with the connection ID and the communication server information included in the response received in step S to the load balancer .

The processes of steps S to S are similar to those of steps S to S in and therefore are not described here.

In step S the communication control unit transmits a data transfer reservation to the load balancer . The process of step S is similar to that of step S in except that the temporary identification information saved in step S in and the communication server information saved in step S in are also simultaneously transmitted. Thus the process of step S is not described here.

In step S similarly to step S the communication control unit receives a response from the load balancer .

In step S the communication control unit confirms the content of the response received in step S and determines whether the data transfer reservation process is successful.

Then in a case where it is determined that the data transfer reservation process is successful YES in step S the processing proceeds to step S.

In a case where on the other hand it is determined that the data transfer reservation process is failed NO in step S the processing proceeds to step S.

In step S similarly to step S in the communication control unit saves the identification information included in the response received in step S as final identification information in the HDD via the file operation unit .

In step S the communication control unit deletes the communication server information saved in step S in .

The process of step S is similar to that of step S in and therefore is not described here. When the process of step S ends the processing of this flowchart ends.

As illustrated above according to the second exemplary embodiment in the case of the configuration in which load is distributed to the plurality of job history processing servers via the load balancer even if some failure occurs in a service the agent management server for managing information about an agent it is possible to collect job history from a new collection agent and export the job history as incomplete information. Further in a case where the failure in the agent management server is removed a new collection agent is registered in the agent management server . Then based on information acquired from the agent management server the job history exported as the incomplete information is promptly complemented to obtain complete information so that it is possible to promptly transfer the job history to an external system such as a history checking system. Thus in the case of the configuration in which load is distributed to the plurality of job history processing servers via the load balancer even if some failure occurs in the agent management server for example the operation is enabled in a state where the security e.g. traceability when information is leaked of a newly placed digital MFP is ensured.

According to the above exemplary embodiments the collection source of information to be received by the job history processing server is an image forming apparatus a printing apparatus such as the digital MFP . However the collection source of information to be received by the job history processing server is not limited to an image forming apparatus and may be any of an information processing apparatus such as a PC and a network device such as a network household electrical appliance.

Further a configuration has been described in which the collection agent operates on a network device as an information collection source such as the digital MFP . Alternatively a program corresponding to the collection agent may be installed in another network device such as a PC capable of collecting from a device as an information collection source job history recorded by the device and the collection agent may operate on another network device. In the case of this configuration the collection agent that operates on another network device collects from a device such as the digital MFP job history recorded by the device and transmits the job history to the job history processing server . With such a configuration the job history processing server can receive even information about a device on which the collection agent cannot operate.

Further according to the above exemplary embodiments job history is recorded by a device as an information collection source such as the digital MFP and transmitted to the job history processing server . Alternatively instead of the device as the information collection source such as the digital MFP another network device such as a PC for submitting a job to the device may record job history and transmit the job history to the job history processing server . That is a program corresponding to the collection agent may be installed in another network device such as a PC and the collection agent may operate on another network device.

Further according to the above exemplary embodiments in view of the processing efficiency of the job history processing server the recovery of the agent management server is periodically checked. Alternatively every time the job history processing server receives a job history transmission reservation the recovery of the agent management server may be checked.

As illustrated above according to the exemplary embodiments for example in a case where a request to register the collection agent is performed and in a case where the job history processing server cannot connect to the agent management server the job history processing server issues temporary identification information for use of when the job history processing server cannot access the agent management server and saves job history information in an incomplete state using the temporary identification information. Then after the job history processing server becomes able to connect to the agent management server the job history processing server issues final identification information and notifies the collection agent of the final identification information. At this process after issuing the final identification information the job history processing server complements based on the final identification information the incomplete job history information saved using the temporary identification information. Then the job history processing server creates an end file meaning the completion of the job history information thereby obtaining complete job history information.

With such a configuration even while a service the agent management server for managing an agent operating on a network device to collect data is stopped it is possible to newly place a collection agent it is possible to receive data from an unregistered collection agent . This enables the operation of for example a newly placed network device such as a digital MFP a printer or a network household electrical appliance in a state where the security for example traceability when information is leaked of the network device is ensured.

That is it becomes possible to solve the issue that even in a case where a failure in an agent setting information management function used by a job history processing server is prolonged a network device such as a digital MFP a printer or a network household electrical appliance cannot be used practically due to the fact that a collection agent cannot be registered even though the network device is newly placed.

Embodiments of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present invention and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a central processing unit CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2014 169272 filed Aug. 22 2014 which is hereby incorporated by reference herein in its entirety.


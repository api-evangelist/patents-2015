---

title: Image forming apparatus capable of executing authentication processing, method of controlling the same, and storage medium
abstract: An image forming apparatus that is capable of executing authentication processing improved in security of a command including authentication information, which is received over a network from an external apparatus. A CPU receives a command including authentication information via a network. The CPU determines whether or not authentication information included in the received command is a hash value. The CPU causes processing in accordance with the received command to be executed depending on authentication performed based on the authentication information when it is determined that the authentication information is a hash value, and causes the processing not to be executed when it is determined that the authentication information is not a hash value.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09461988&OS=09461988&RS=09461988
owner: CANON KABUSHIKI KAISHA
number: 09461988
owner_city: Tokyo
owner_country: JP
publication_date: 20150423
---
The present invention relates to an image forming apparatus that is capable of executing authentication processing a method of controlling the same and a storage medium.

A digital multifunction peripheral is conventionally known which executes jobs such as print jobs scan jobs document storage jobs and facsimile transmission jobs according to commands received from external apparatuses via a network. Further a technique is also conventionally known in which an operation mode of the digital multifunction peripheral is set or changed according to a command received from an external apparatus via the network.

The above mentioned commands sometimes include secret information such as a password associated with a user or a section and a password associated with a job. When the digital multifunction peripheral has received a command including a password it performs authentication based on the received password. If authentication is successful the digital multifunction peripheral permits execution of processing in accordance with the received command whereas if authentication fails the digital multifunction peripheral interprets the command as an error without executing the processing.

By the way conventionally there has been proposed a method of performing authentication in the following manner In a system in which a server authenticates clients first an authentication method permitted to be used by a client is set in advance and the client determines whether or not an authentication method which the client intends to use when exchanging authentication information with the server via a network is the permitted authentication method. If the authentication method which the client intends to use is not the permitted authentication method the client does not execute exchanging of the authentication information with the server and terminates the authentication attempt as an error.

For example in Japanese Patent Laid Open Publication No. 2004 213534 when transmitting a mail using SMTP the following processing is performed If an SMTP authentication method intended to be used between a client and a mail server to which the mail is to be transmitted is permitted mail transmission is executed whereas if not mail transmission is handled as an error without performing SMTP authentication.

However according to the conventional techniques the image forming apparatus cannot permit or reject processing in accordance with a command received from an external apparatus and including authentication information by considering whether or not the command has been transmitted and received in a proper form.

The present invention provides an image forming apparatus that is capable of executing authentication processing improved in security of a command including authentication information and received over a network from an external apparatus a method of controlling the same and a storage medium.

In a first aspect of the present invention there is provided an image forming apparatus comprising a reception unit configured to receive a command including authentication information via a network a determination unit configured to determine whether or not the authentication information included in the command received by the reception unit is a hash value and a control unit configured to cause in a case where it is determined by the determination unit that the authentication information is a hash value processing in accordance with the received command to be executed depending on authentication performed based on the authentication information and cause in a case where it is determined by the determination unit that the authentication information is not a hash value the processing in accordance with the received command not to be executed.

In a second aspect of the present invention there is provided a method of controlling an image forming apparatus comprising receiving a command including authentication information via a network determining whether or not the authentication information included in the command received by said receiving is a hash value and causing in a case where it is determined by said determining that the authentication information is a hash value processing in accordance with the received command to be executed depending on authentication performed based on the authentication information and causing in a case where it is determined by said determining that the authentication information is not a hash value the processing in accordance with the received command not to be executed.

In a third aspect of the present invention there is provided a non transitory computer readable storage medium storing a computer executable program for causing a computer to execute a method of controlling an image forming apparatus wherein the method comprises receiving a command including authentication information via a network determining whether or not the authentication information included in the command received by said receiving is a hash value and causing in a case where it is determined by said determining that the authentication information is a hash value processing in accordance with the received command to be executed depending on authentication performed based on the authentication information and causing in a case where it is determined by said determining that the authentication information is not a hash value the processing in accordance with the received command not to be executed.

According to the present invention it is possible to provide an image forming apparatus that is capable of executing authentication processing improved in security of a command including authentication information and received over a network from an external apparatus a method of controlling the same and a storage medium.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

The present invention will now be described in detail below with reference to the accompanying drawings showing embodiments thereof.

Referring to the network system comprises the MFP denoted by reference numeral a PC and a server which are connected to a network .

The MFP includes a scanner and a printer. The PC as an information processing apparatus which is an external apparatus is capable of requesting the MFP to execute processing using a command described hereinafter and performing state management of the MFP or the PC and management of a job being executed using a command such as a scan job a print job and a copy job. As described above the MFP is an image forming apparatus that executes processing in accordance with a received command.

The server is a settings management server and is capable of sending a setting in response to a setting acquisition request from the MFP or the PC .

Referring to the MFP comprises a CPU a RAM an LCD an input device a FAX board a ROM a scanner engine a printer engine a disk and a network interface which are connected to a system bus .

The CPU controls the overall operation of the MFP . The ROM stores a program for controlling the MFP etc. The program etc. stored in the ROM are loaded into the RAM and the RAM is also used as a work area for the CPU .

The disk stores attribute information indicative of functions and a status of each job which is executed by the MFP print data and so forth.

The LCD displays information to a user. The input device is used by the user for performing inputting operations. The FAX board is used for performing facsimile communication.

The printer engine prints an image on a recording sheet or the like. The scanner engine reads an original and generates image data representative of the original.

The network interface is for connecting to the network . The MFP may include other interfaces compatible with USB IEEE1394 Bluetooth and so forth.

With the above described configuration the CPU performs communication with the external apparatus PC connected to the network via the network interface receives a command for performing a print operation managing the image forming apparatus MFP or the like stores the received command in the RAM and executes processing in accordance with the received command.

The setting screen shown in is a screen for causing the user to set whether or not to permit the MFP to exchange authentication information which is not concealed with the PC and the server via the network interface .

Note that the authentication information includes a password used for section authentication or user authentication a password of a secure job which is required to be input when executing printing a password which is set in association with an F code in facsimile transmission and so forth. In the following description exchange of authentication information which is not concealed is referred to as plain text authentication.

A person who is allowed to make a setting on the above mentioned setting screen is an administrator of the MFP and the setting made on this setting screen is stored in the disk . In if a checkmark is entered in a checkbox of plain text authentication is not permitted this indicates that plain text authentication is not permitted whereas if a checkmark is not entered in the checkbox this indicates that plain text authentication is permitted.

Note that a job in the present embodiment indicates processing which is executed by the MFP such as printing scanning copying facsimile transmission reception print data storage and print data transmission. Therefore the job input command is a command for causing the MFP to execute any of these.

In the present embodiment some job input commands include a password as authentication information. For example in the case of the print job a secure print job includes a password. The secure print job is a job for printing print data by receiving a job input command including the print data provided with a password from an external apparatus and having the password input from a console section of the MFP by the user. That is the password included in the command for inputting the secure print job can be said to be a password required to cause the printer engine of the MFP to print the print data. The secure print job is also sometimes referred to as a reservation print job or an authentication print job.

A print job that includes a section ID and a section password may be mentioned as another example. This type of print job is a job in which the number of copies is managed for each section ID included in the print job. The print job including a section ID and a section password is subjected to section authentication based on the section ID and the section password when the job is input to the MFP and if the section authentication is successful printing is started whereas if the section authentication fails printing is not executed. That is the section password included in this type of print job is also a password required to cause the printer engine of the MFP to perform printing similarly to the password included in the secure print job.

A scan job including a section ID and a section password may be mentioned as a still another example. This is similar to the above mentioned print job including a section ID and a section password but is distinguished therefrom in that section authentication is executed when the scanner is caused to read an original.

As described above in the present embodiment the MFP can execute a job such as a print job a scan job a copy job a facsimile transmission reception job and a print data storage job and the job input commands for executing these jobs sometimes include the above described authentication information.

Further other examples of the job input command including authentication information include one for inputting a facsimile transmission job including an F code password one including a password used for accessing a storage area also referred to as a BOX for storing print data and so forth.

In Header ID is an ID for identifying a command system and is set to a value of 0xabcd in . Note that Header ID of a device management command described hereinafter has the same value and a command type can be determined based on Operation Code referred to hereinafter for processing.

Version is a value indicative of a version of the command system. In Version is set to a value of 0x10 which indicates a version 1.0 of the command system.

Authentication Mode represents indication as to whether to perform authentication determination by using User ID and Password included in the header section or using authentication information attributes included in the parameter section. If Authentication Mode is True this indicates that authentication determination is to be performed using not User ID and Password but the authentication information attributes included in the parameter section. Although described hereinafter in the present embodiment the value password of each authentication information attribute is a hash value and if Authentication Mode is True the CPU determines to execute authentication processing using the password described as the hash value.

On the other hand if Authentication Mode is False this indicates that authentication determination is to be performed using User ID and Password . In the present embodiment Password used for authentication processing in a case where Authentication Mode is False has a possibility of being described in plain text. Therefore a command having Authentication Mode which is False is rejected except a specific case. This will be described in detail with reference to .

Note that when a job input command is transmitted from a printer driver or a client application of the PC which supports only plain text authentication Authentication Mode is always False.

Operation Code indicates a value for identifying a command type. In Operation Code indicates that the command is a JobStart command. The JobStart command is a command which is transmitted when execution of a job is requested and is to be subjected to authentication processing before execution of the job.

Parameter Length indicates data length of the parameter section in terms of the number of bytes. User ID indicates a user identifier used for authentication processing of the JobStart command in the case where Authentication Mode is False. The Password indicates a password used for authentication processing of the JobStart command in the case where Authentication Mode is False.

Attribute Count indicates the number of attributes designated within the JobStart command. In Attribute Count indicates a value of 5 and hence the JobStart command has five attributes.

Attribute indicates a first attribute and in the illustrated example in Attribute indicates that a user identifier as an authentication information attribute is 0x12345678 and a hash value calculated from an associated password is 0x1234abcd .

If Authentication Mode is True authentication is performed based on the user identifier of the authentication information attribute and the hash value calculated from the associated password which are indicated in Attribute .

Attribute indicates a second attribute and indicates that a hash value calculated from the job password required to execute the print job is 0x012345abc .

Then Attribute and Attribute follow Attribute but are omitted in this example. Attribute indicates that a Job Name is written report .

In the description of description of items having the same contents as those described with reference to is omitted.

Referring to Authentication Mode is False. In this case authentication determination is performed using User ID and Password .

Further Operation Code indicates a Set command for setting an attribute of the MFP . Further User ID indicates 0x12345678 and Password indicates that 0xabcd1234 is a password associated with User ID . Attribute indicates that an attribute setting for enabling the section management is to be performed.

The above described job input command and device management command are received not only from the PC but also by calling an internal API application programming interface by an application operating on the MFP .

The above described job input command and device management command both include a user ID and a password or a hash value thereof which are authentication information for authenticating a user.

Referring to when the CPU receives a job input command the CPU determines whether or not plain text authentication is permitted step S . This can be determined based on the setting described with reference to .

If it is determined in the step S that plain text authentication is permitted YES to the step S the CPU performs an authentication process step S and determines whether or not the authentication result is OK step S .

If it is determined in the step S that the authentication result is OK YES to the step S the CPU executes the requested job and notifies a sender of the command of the success of the job input command process step S followed by terminating the present process.

On the other hand if it is determined in the step S that the authentication result is not OK NO to the step S this means that the authentication has failed and hence the CPU notifies without executing the job the sender of the command that the job input command process has failed due to an authentication error step S followed by terminating the present process.

Referring again to the step S if it is determined in the step S that plain text authentication is not permitted NO to the step S the CPU determines whether or not Authentication Mode described with reference to is True step S .

If it is determined in the step S that Authentication Mode is True YES to the step S the CPU proceeds to the step S. Thus when the possibility of the use of plain text authentication is excluded by the command user authentication is performed.

On the other hand if it is determined in the step S that Authentication Mode is False NO to the step S the CPU determines whether or not the job input command has been received as a packet an example of which is shown in step S .

If it is determined in the step S that the job input command has not been received as a packet NO to the step S the CPU proceeds to the step S. Note that when the command has not been received as a packet this means that the command has been issued by calling the above mentioned internal API.

On the other hand if it is determined in the step S that the job input command has been received as a packet YES to the step S the CPU determines whether or not the job input command has been transmitted from the outside of the MFP and has been received via the network interface step S . In doing this for example an IP address of the sender of the job input command is checked and if the IP address of the sender is a local loopback address ... it is determined that the job input command has been transmitted from the inside of the MFP .

If it is determined in the step S that the job input command has not been transmitted from the outside of the MFP NO to the step S the CPU proceeds to the step S.

On the other hand if it is determined in the step S that the job input command has been transmitted from the outside of the MFP YES to the step S the CPU determines whether or not the received command uses plain text authentication step S . In the step S if a hash value of a password is included in the command it is determined that the command is not a command transmitted in plain text. Whether or not a hash value is included in the command may be determined based on whether or not the value of Attribute indicates an effective value. For example it may be determined that an effective value is indicated when a value other than 0 is set as the value of Attribute .

If it is determined in the step S that the job input command does not use plain text authentication NO to the step S i.e. if the job input command designates a user ID and a password using a hash value or an encrypted value the CPU proceeds to the step S.

On the other hand if it is determined in the step S that the job input command uses plain text authentication YES to the step S the command using plain text authentication has been transmitted from the outside and hence the CPU executes reception rejection processing step S followed by terminating the present process.

The reception rejection processing refers to processing executed as a response to the received job input command for sending an error notification indicative of access rejection handling the job input command as an error job or executing the like processing and then entering a job history record to the effect that the use of unpermitted plain text authentication was attempted in the job history stored in the disk of the MFP .

According to the job input command process in if it is determined that user authentication using authentication information in a command written in plain text is not permitted also if it is determined that the command has been received from an external apparatus and also if it is determined that the authentication information in the command is in plain text reception of the command is rejected and hence it is possible to suppress user authentication using plain text which makes it possible to improve security of commands which include authentication information received from an external apparatus over a network.

Referring to the CPU determines whether or not a device management command received by the CPU uses plain text authentication step S .

If it is determined in the step that the received device management command does not use plain text authentication NO to the step S the CPU proceeds to a step S wherein the CPU executes the authentication process. Thus when a command is received which does not use plain text authentication user authentication is performed.

On the other hand if it is determined in the step S that the received device management command uses plain text authentication YES to the step S the CPU determines whether or not plain text authentication is permitted step S . This can be determined based on the setting described with reference to .

If it is determined in the step that plain text authentication is permitted YES to the step S the CPU executes the authentication process step S and determines whether or not the authentication result is OK step S .

If it is determined in the step that the authentication result is OK YES to the step S the CPU executes the requested management command and notifies a sender of the command of the success of the device management command process step S followed by terminating the present process.

On the other hand if it is determined in the step that the authentication result is not OK NO to the step S this means that the authentication has failed and hence the CPU notifies without executing the job the sender of the command that the device management command process has failed due to an authentication error step S followed by terminating the present process.

Referring again to the step S if it is determined in the step that plain text authentication is not permitted NO to the step S the CPU determines whether or not the device management command has been received as a packet an example of which is shown in step S .

If it is determined in the step that the device management command has not been received as a packet NO to the step S the CPU proceeds to the step S. Note that when the device management command has not been received as a packet this means that the device management command has been issued by calling the above mentioned internal API.

On the other hand if it is determined in the step that the device management command has been received as a packet YES to the step S the CPU determines whether or not the device management command has been received by non secure communication step S . The non secure communication refers to e.g. communication in which a communication path is not encrypted using SSL Secure Socket Layer TLS Transport Layer Security or IPSec Security Architecture for Internet Protocol .

If it is determined in the step that the device management command has not been received by non secure communication in other words has been received by secure communication NO to the step S even when the authentication information shown in is not a hash value or an encrypted value the authentication information is concealed on the communication path and hence the CPU proceeds to the step S. Thus when a command has been received by secure communication user authentication is performed.

On the other hand if it is determined in the step that the device management command has been received by non secure communication YES to the step S the CPU determines whether or not the device management command has been transmitted from the outside of the MFP and has been received via the network interface step S .

If it is determined in the step that the device management command has not been received from the outside of the MFP NO to the step S the CPU proceeds to the step S.

On the other hand if it is determined in the step that the device management command has been received from the outside of the MFP YES to the step S this means that the command using plain text authentication has been transmitted from the outside and hence the CPU executes the reception rejection processing step S followed by terminating the present process.

The reception rejection processing refers to processing executed as a response to the received job input command for sending an error notification indicative of access rejection handling the device management command as an error job or executing the like processing and then entering a history record of the device management command as an unauthorized access in the job history stored in the disk of the MFP

In the step S in and the step S in described above by storing a setting indicative of whether or not to permit plain text authentication in the server connected via the network interface the determination may be executed by inquiring the setting of the server from the MFP .

Referring to the CPU determines whether or not authentication is required step S . Whether or not authentication is required is determined according to whether or not a command to be processed requires authentication.

For example the job input command requires section authentication or user authentication so as to perform account management and job management. Further the device management command which involves a change of a setting of the MFP requires user authentication so as to check whether or not the user has administrative authority.

If it is determined in the step that authentication is not required NO to the step S the CPU proceeds to a step S.

On the other hand if it is determined in the step that authentication is required YES to the step S the CPU reads authentication information from the received command step S . The CPU reads e.g. User ID and Hash of Attribute in or User ID and Password in according to the type and format of the command.

Then the CPU checks the read authentication information against authentication database information stored in the disk in advance step S . Then the CPU determines whether or not the check result is OK step S .

If it is determined in the step that the check result is OK YES to the step S the CPU returns a notification indicative of authentication result OK step S followed by terminating the present process.

On the other hand if it is determined in the step that the check result is not OK NO to the step S the CPU returns a notification indicative of authentication result NG step S followed by terminating the present process.

Note that the authentication database is not necessarily required to be stored in the MFP but for example the CPU of the MFP transmits authentication information read in the step S to the server via the network interface for the server to perform authentication processing and the determination in the next step S may be performed based on the authentication result received from the server .

In this case the server checks the authentication information transmitted from the MFP and received via the network against the authentication database DB which has been stored in the server in advance and transmits the check result to the MFP .

Note that in this case it is assumed that the authentication information is exchanged between the server and the MFP by concealing data on the communication path using SSL TLS.

As described above the MFP can be configured to determine whether or not plain text authentication is permitted and execute if plain text authentication is not permitted the reception rejection processing for a command using plain text authentication or a command received from the PC by non secure communication without executing the authentication process to thereafter notify a user of reception rejection.

As a result it is possible to prevent authentication information to be concealed from flowing in plain text on a communication path.

Embodiments of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present invention and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a central processing unit CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2013 034814 filed Feb. 25 2013 which is hereby incorporated by reference herein in its entirety.


---

title: Information processing system and authentication information providing method for providing authentication information of an external service
abstract: An information processing system includes an electronic device; a service providing system including information processing devices connected to the image forming device via a network; a single sign on unit configured to send a request from the electronic device to the service providing system, to acquire authentication information of an external service that performs a process in cooperation with an application operating in the image forming device; an access control unit configured to receive the request from the single sign on unit whose validity has been confirmed, based on a result obtained by using identification information of the single sign on unit, in the service providing system; and a data management unit configured to acquire the authentication information of the external service from a storage unit based on the request from the single sign on unit that is valid, and to provide the authentication information of the external service to the single sign on unit via the access control unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09594895&OS=09594895&RS=09594895
owner: Ricoh Company, Ltd.
number: 09594895
owner_city: Tokyo
owner_country: JP
publication_date: 20150306
---
The present invention relates to an information processing system and an authentication information providing method.

Conventionally there is known a proxy management method and an agent device by which an agent device provided between a service provider device and a user device manages the information of the user device. In the conventional proxy management method and the agent device the user s load of managing authentication information has been reduced see for example Patent Document 1 .

In recent years various external services have started to be provided by cloud computing etc. As external services provided by cloud computing etc. have become widespread there have been cases where applications which operate in an image forming apparatus such as a multifunction peripheral perform processes in cooperation with external services.

In these cases the user needs to perform a plurality of authentication operations in order to use a plurality of external services. Note that there is known a technique of a single sign on SSO which is for reducing the load of authenticating a user. By single sign on the user does not need to execute another authentication operation after completing the sign on operation i.e. after being authenticated.

However there has been a problem in that when an image forming apparatus such as a multifunction peripheral and an external service cooperate with each other to perform a process there has been a need to develop a cooperation function for cooperating with the external service for each application operating in the image forming apparatus.

The present invention provides an information processing system and an authentication information providing method in which one or more of the above described disadvantages are eliminated.

According to an aspect of the present invention there is provided an information processing system including an electronic device a service providing system including one or more information processing devices that are connected to the electronic device via a network a requesting unit configured to send a request from the electronic device to the service providing system to acquire authentication information of an external service that performs a process in cooperation with an application operating in the electronic device an access control unit configured to receive the request from the requesting unit whose validity has been confirmed based on a result of confirming the validity of the requesting unit obtained by using identification information of the requesting unit in the service providing system and a data management unit configured to acquire the authentication information of the external service from a storage unit based on the request from the requesting unit whose validity has been confirmed and to provide the authentication information of the external service to the requesting unit via the access control unit.

According to an aspect of the present invention there is provided an authentication information providing method executed by an information processing system including an electronic device and a service providing system including one or more information processing devices that are connected to the electronic device via a network the authentication information providing method including sending a request from a requesting unit of the electronic device to the service providing system to acquire authentication information of an external service that performs a process in cooperation with an application operating in the electronic device receiving the request from the requesting unit whose validity has been confirmed based on a result of confirming the validity of the requesting unit obtained by using identification information of the requesting unit in the service providing system and acquiring the authentication information of the external service from a storage unit based on the request from the requesting unit whose validity has been confirmed and providing the authentication information of the external service to the requesting unit.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

The image forming apparatus is a device having an image forming function such as a multifunction peripheral. The image forming apparatus includes a means for performing wireless communication or a means for performing wired communication. The image forming apparatus is a device for performing processes relevant to image forming such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard.

The example of the information processing system illustrated in includes the image forming apparatus in which the application operates however any electronic device may be used as long as an application for performing processes in cooperation with the external service device can operate in the electronic device. Furthermore the example of includes one image forming apparatus however a plurality of image forming apparatuses may be included.

The image forming apparatus is able to provide for example a new application by causing an application operating in the image forming apparatus and the external service device to cooperate with each other. For example the information processing system illustrated in may translate a document scanned by the image forming apparatus by using a translation service of the external service device and send the document obtained as a translation result to a user by mail. The external service device is a device for providing external services such as a translation service and an online storage. Note that the external service device may be a system that is realized by a plurality of information processing devices.

The service providing system is realized by one or more information processing devices. The service providing system stores authentication information for passing authentication needed for using the API Application Programming Interface of the external service device .

The authentication of the external service device may be hidden as an internal process of the image forming apparatus . After registering the authentication information of the image forming apparatus in the service providing system the user of the image forming apparatus is able to seamlessly without having to input authentication information use single sign on the external service device from the image forming apparatus .

The authentication information of the external service device stored in the service providing system may be used from a plurality of image forming apparatuses . Therefore the user of the image forming apparatus is able to easily set up the image forming apparatus for performing processes in cooperation with the external service device . Furthermore in addition to the authentication information of the external service device the service providing system may store for example information specialized for an application operating in the image forming apparatus such as translation conditions and print conditions.

Note that the configuration of the information processing system illustrated in is an example the information processing system may have other configurations.

The service providing system and the external service device illustrated in is realized by a computer having a hardware configuration for example as illustrated in .

The input device includes a keyboard a mouse and a touch panel and is used by the user for inputting various operation signals. The display device includes a display etc. and displays processing results obtained by the computer . Note that the input device and the display device may have a configuration of being connected and used when necessary.

The communication I F is an interface that connects the computer to the network N. Accordingly the computer is able to perform data communication via the communication I F .

Furthermore the HDD is an example of a non volatile storage device for storing programs and data. The stored programs and data include an OS that is the basic software for controlling the entire computer and application software for providing various functions in the OS. Note that the computer may use a drive device for example a solid state drive SSD using a flash memory as the storage medium instead of the HDD .

The HDD manages the stored programs and data by a predetermined file system and or a DB. The external I F is an interface between the computer and an external device. An example of the external device is a recording medium

Accordingly the computer is able to read and or write in the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD a DVD an SD memory card and a USB memory.

The ROM is a non volatile semiconductor memory storage device that can store programs and data even after the power is turned off. The ROM stores programs and data such as a BIOS that is executed when the computer is activated OS settings and network settings. The RAM is a volatile semiconductor memory storage device for temporarily storing programs and data.

The CPU is a processor for controlling the entire computer and realizing functions of the computer by loading the programs and data from the storage devices such as the ROM and the HDD into the RAM and executing processes. The service providing system and the external service device are able to realize various processes described below by the hardware configuration of the computer .

The image forming apparatus illustrated in is realized by a computer having a hardware configuration for example as illustrated in . illustrates a hardware configuration of an example of the image forming apparatus according to the present embodiment. The image forming apparatus illustrated in includes a controller an operation panel an external I F a communication I F a printer and a scanner .

The controller includes a CPU a RAM a ROM a NVRAM and a HDD . The ROM stores various programs and data. The RAM temporarily stores programs and data. The NVRAM stores for example setting information. Furthermore the HDD stores various programs and data.

The CPU controls the entire image forming apparatus and realizes functions of the image forming apparatus by loading the programs and data setting information from the ROM the NVRAM and the HDD into the RAM and executing processes.

The operation panel includes an input unit for receiving input from a user and a display unit for displaying information. The external I F is an interface between the image forming apparatus and an external device. An example of the external device is a recording medium . Accordingly the image forming apparatus is able to read and or write in the recording medium via the external I F . Examples of the recording medium are an IC card a flexible disk a CD a DVD an SD memory card and a USB memory.

The communication I F is an interface that connects the image forming apparatus to the network N. Accordingly the image forming apparatus is able to perform data communication via the communication I F . The printer is a printing device for printing print data onto a sheet. The scanner is a reading device for reading image data electronic data from an original document.

The image forming apparatus according to the present embodiment can be realized by for example processing blocks as illustrated in . illustrates processing blocks of an example of the image forming apparatus according to the present embodiment. Note that in the image forming apparatus of processing blocks that are unnecessary for describing the present embodiment are not illustrated.

In the image forming apparatus one or more applications and a common SSO single sign on unit are operating. Note that the application may use a SDK application that is an application developed by using SDK Software Development Kit .

The application performs processes in cooperation with the external service device . The common SSO unit provides to the application a common IF interface for storing acquiring authentication information of the external service device . The registering of authentication information of the external service device in the service providing system and the acquiring of authentication information of the external service device from the service providing system are performed by the common SSO unit .

The application uses the authentication information of the external service device that is acquired via the common SSO unit to acquire an authentication ticket token needed for using the external service device . Then the application uses the acquired authentication ticket token to use a function of the external service device . The application may store the setting information unique to the application in the service providing system .

The service providing system according to the present embodiment is realized by for example processing blocks as illustrated in . illustrates processing blocks of an example of the service providing system according to the present embodiment.

The service providing system illustrated in realizes an existing service layer a common service layer a database layer a public API an API layer and a platform API by executing programs. The common service layer and the database layer constitute a platform layer .

The public API is an interface for the image forming apparatus to use the service providing system . The public API is an interface defined in advance which is provided for the API layer to receive requests from the image forming apparatus . The public API is constituted by for example functions and classes.

The API layer has a role as a wrapper layer for providing the platform API to a vendor. The API layer includes an application data management wrapper an authentication wrapper and an access controller .

The application data management wrapper has a role of a mini storage for managing data such as setting information unique to an application. The authentication wrapper has a role of a wrapper of an authentication allowance unit a tenant management unit a user management unit and a ticket management unit of the common service layer . The access controller checks the validity of the image forming apparatus that is a client when using the platform API .

The existing service layer provides existing services. The existing service layer includes for example a portal service application a scan service application and a print service application. The existing service layer may include other service applications.

The service applications of the existing service layer provide various services by using the platform API . The platform API is an interface for the service applications of the existing service layer to use the platform layer .

The platform API is an interface that is defined in advance which is provided for the platform layer to receive requests from the service applications of the existing service layer . The platform API is constituted by for example functions and classes.

When the service providing system is constituted by a plurality of information processing devices the platform API may be realized by for example a web API that can be used via the network.

The common service layer includes an authentication allowance unit a tenant management unit a user management unit a license management unit a device management unit a temporary image saving unit a log collection unit a ticket management unit an application management unit an application data management unit and an image processing workflow control unit . Furthermore the image processing workflow control unit includes a message queue and one or more workers. A worker realizes functions such as image conversion and image transmission.

The authentication allowance unit executes authentication allowance based on a login request from an electronic device such as the image forming apparatus . The authentication allowance unit authenticates allows a user by accessing a user information storage unit and a license information storage unit . Furthermore the authentication allowance unit authenticates an electronic device such as the image forming apparatus by accessing a tenant information storage unit the license information storage unit and a device information storage unit .

The tenant management unit manages tenant information stored in the tenant information storage unit . The user management unit manages user information stored in the user information storage unit . The license management unit manages license information stored in the license information storage unit .

The device management unit manages device information stored in the device information storage unit . The temporary image saving unit saves a temporary image in a temporary image storage unit and acquires a temporary image from the temporary image storage unit .

The log collection unit manages log information stored in a log information storage unit . The ticket management unit has functions such as issuing an authentication ticket associated with the user checking the validity of the authentication ticket managing the expiration date and managing the upper limit. The application management unit manages application information stored in an application information storage unit . The application data management unit manages setting information unique to an application stored in a setting information storage unit unique to an application.

The image processing workflow control unit controls a workflow relevant to image processing based on a request. The message queue includes a queue corresponding to the type of process. The image processing workflow control unit inputs a message of a request relevant to the process job to a queue corresponding to the type of the job.

The worker monitors a corresponding queue. When a message is input to a queue the worker performs processes such as image conversion and image transmission according to the type of the corresponding job. The message input to the queue may be proactively read pulled by the worker or may be provided pushed from the queue to the worker.

The database layer includes a log information storage unit a tenant information storage unit a user information storage unit a license information storage unit a device information storage unit a temporary image storage unit a job information storage unit a setting information storage unit unique to the application a ticket information storage unit and an application information storage unit .

The log information storage unit stores log information. The tenant information storage unit stores tenant information. The user information storage unit stores user information. The license information storage unit stores license information. The device information storage unit stores device information.

The temporary image storage unit stores a temporary image. A temporary image is for example a file and data such as a scan image to be processed by the worker. The job information storage unit stores information job information of a request relevant to a process job . The setting information storage unit unique to an application stores setting information unique to an application. The ticket information storage unit stores ticket information. The application information storage unit stores application information.

Note that the authentication information of the external service device is stored in the setting information storage unit unique to an application of the platform layer via the application data management wrapper of the API layer . In order to use the public API for example the image forming apparatus needs an application ID and an application key issued by the company managing the service providing system . The application ID and the application key are stored in the application information storage unit via the application management unit .

The service providing system of is provided with the API layer and is thus able to upgrade the version of the public API and to perform maintenance on the public API without affecting the existing service layer . Furthermore the service providing system of is able to limit the API to be open to the public by the public API without providing the entire platform API to the vendor.

The service providing system functions as an integration base for providing a common service and a database as a platform and as a service group for providing application services by using the functions of the integration base. The integration base is constituted by for example the common service layer the database layer and the platform API . The service group is constituted by for example the public API the API layer and the existing service layer .

The service providing system illustrated in is able to easily develop the service applications using the platform API by a configuration in which the service group and the integration base are separated.

Note that the classification mode of the process blocks of the service providing system of is one example it is not essential that the process blocks are classified by the hierarchy as illustrated in . As long as processes of the service providing system according to the present embodiment may be performed the hierarchal relationships etc. illustrated in are not particularly limited.

The application that operates in the image forming apparatus needs to perform service registration as illustrated in as a precondition for storing authentication information of the external service device by using the public API of the service providing system .

In step S the user activates the application that the user wants to use from the top screen. When the service registration has not been done the activated application displays a service registration screen on the operation panel .

In step S the user inputs a password in the service registration screen and requests service registration. Note that in step S the input password is the password for tenant authentication described below and this password is determined by the user.

In step S the application requests the common SSO unit to perform service registration according to the password input by the user. In step S the common SSO unit acquires an application ID and an application key stored in itself.

In step S the common SSO unit uses the password the application ID and the application key to request the service providing system to perform service registration. In step S the service providing system which has received the request for service registration performs application authentication and confirms the validity of the common SSO unit that is the client. Note that details of the application authentication of step S are described below. Here the description is continued assuming that the validity of the common SSO unit has been confirmed.

In step S the access controller of the service providing system requests the authentication wrapper to perform service registration. In step S the authentication wrapper applies a serial number as the tenant ID to be registered in the service providing system .

In step S the authentication wrapper requests the tenant management unit to create a tenant according to the applied tenant ID. In step S the tenant management unit performs tenant registration by registering a tenant ID in a tenant information table as illustrated in which is stored in the tenant information storage unit . illustrates an example of a tenant information table. The tenant information table is for managing tenants registered in the service providing system .

In step S the authentication wrapper requests the user management unit to create a tenant user for registered tenant. The request for creating a tenant user in step S is made by using a tenant ID and a password. In step S the user management unit registers the user for the tenant by registering the tenant ID the user ID and the password in a user information table as illustrated in which is stored in the user information storage unit .

Note that the password registered in the user information table is the password input by the user in step S. Furthermore the user ID registered in the user information table is the user ID of the tenant user. The tenant user is a user who is registered based on a certain rule. For example the user ID of the tenant user may be the same as the tenant ID.

In step S the authentication wrapper returns a tenant ID to the access controller as a response to the request for service registration in step S. Furthermore in step S the access controller returns the tenant ID to the common SSO unit of the image forming apparatus . In step S the common SSO unit returns to the application the tenant ID received from the service providing system .

In step S the application acquires an MFP user ID of the user who has logged in from the operation panel . In step S the application records the MFP user ID the tenant ID and the password as tenant authentication information in a tenant authentication table as illustrated in . illustrates an example of a tenant authentication table. The tenant authentication table of is used by the application for storing a tenant ID and a password in association with an MFP user ID after the service registration in the service providing system . In step S the application displays the tenant ID on for example the operation panel and reports the tenant ID to the user.

The application authentication of step S is performed for example as illustrated in . is a sequence diagram of an example of an application authentication process. When the image forming apparatus uses the public API of the service providing system there is a need to pass the application authentication. The common SSO unit that is the client is able to use the public API of the service providing system by using the pair of the application ID and the application key stored in itself. Note that the pair of the application ID and the application key stored in the common SSO unit itself is for example the application ID and the application key issued by the company managing the service providing system .

In step S the common SSO unit acquires the application ID and the application key stored in itself. In step S the common SSO unit requests the usage of the public API to the service providing system by using the password input in step S of and the application ID and the application key acquired in step S.

In step S the access controller which has received the request to use the public API from the image forming apparatus requests the authentication wrapper to perform application authentication by the application ID and the application key. In step S the authentication wrapper requests the application management unit to perform application authentication by the application ID and the application key.

In step S the application management unit performs matching of the pair of the application ID and the application key included in the request for application authentication in step S and the pair of the application ID and the application key recorded in an application information table as illustrated in . illustrates an example of an application information table.

The application information table stores as application information the pair of the application ID and the application key stored by the common SSO unit that can use the public API . The service providing system checks whether usage is possible by the application ID and the application key when using the public API and allows the common SSO unit which has passed the usage possibility check to use the public API . The adding of the pair of the application ID and the application key to the application information table of is performed by for example a company managing the service providing system .

The application management unit determines that the common SSO unit is valid application authentication is successful when the pair of the application ID and the application key which is included in the request for application authentication is recorded in the application information table. Furthermore the application management unit determines that the common SSO unit is invalid application authentication is unsuccessful when the pair of the application ID and the application key which is included in the request for application authentication is not recorded in the application information table.

To the access controller OK indicating that the application authentication is successful or NG indicating that application authentication is unsuccessful is returned. When the application authentication is successful in step S the access controller makes a request to the process block of the API layer that responded to the original request.

Note that in the case of the application authentication process of step S in the access controller requests the authentication wrapper to perform service registration. When the application authentication is unsuccessful the access controller does not make a request to the process block of the API layer that responded to the original request but reports to the common SSO unit that the application authentication is unsuccessful.

By making the application authentication process of essential the service providing system is able to protect the resources from being accessed by an unauthorized client.

The service registration process may also be realized by the procedures as illustrated in . is a sequence diagram of another example of the service registration process. In the service registration process of service registration processes are performed from the respective applications . In the service registration process of the service registration processes are not performed from the respective applications the service registration process is performed from the common SSO unit . In the respective applications use the tenant authentication information recorded by the common SSO unit . Once the common SSO unit records the tenant authentication information the tenant authentication information may be used from all of the applications .

In step S the user inputs in the operation panel an MFP user ID and an MFP password for using the image forming apparatus and logs into the image forming apparatus . When the login is successful the image forming apparatus displays a top screen on the operation panel .

In step S the user opens the service registration screen from the top screen and displays the service registration screen on the operation panel . In step S the user inputs a password in the service registration screen and requests the common SSO unit to perform service registration.

In step S the common SSO unit acquires the application ID and the application key stored in itself. In step S the common SSO unit requests the service providing system to perform service registration by using the password the application ID and the application key.

In step S the service providing system performs the service registration process as indicated in steps S through S of . In step S the service providing system returns a tenant ID to the common SSO unit of the image forming apparatus . In step S the common SSO unit records the tenant ID received from the service providing system as tenant authentication information in a tenant information table as illustrated in . illustrates an example of a tenant authentication table. The tenant authentication table of is used by the common SSO unit for storing the tenant ID and the password in association with each other after the service registration in the service providing system . In step S the common SSO unit displays the tenant ID on for example the operation panel and reports the tenant ID to the user.

The application operating in the image forming apparatus needs to perform data registration as illustrated in in order to store the authentication information of the external service device by using the public API of the service providing system .

In step S the user inputs in the top screen the user ID of an external service and the password of the external service as authentication information of the external service device and requests to register external service information.

In step S the application acquires an encoding key held in itself. Note that the encoding key held by the application differs according to the application . Therefore if the application erroneously acquires the authentication information encoded by another application the information cannot be decoded.

In step S the application acquires the MFP user ID of the user who has logged in from the operation panel . In step S the application acquires from the tenant authentication table as illustrated in the tenant ID and password associated with the MFP user ID.

In step S the application requests the common SSO unit to perform data registration by using the user ID of the external service and the password of the external service input by the user and the acquired encoding key tenant ID and password.

In step S the common SSO unit acquires the application ID and the application key stored in itself. Furthermore in step S the common SSO unit performs tenant authentication and acquires an authentication of the service providing system . Note that details of the tenant authentication of step S are described below. Here the description is continued assuming that the authentication ticket of the service providing system has been acquired.

In step S the common SSO unit encodes by the encoding key received from the application the user ID of the external service and the password of the external service as authentication information of the external service device and acquires an encoded user ID and encoded password. In step S the common SSO unit requests the service providing system to perform data registration by using the encoded user ID the encoded password the MFP user ID the external service identifier the application ID the application key and the authentication ticket.

In step S the service providing system checks the validity of the authentication ticket. Note that details of the validity check of the authentication ticket of step S are described below. Here the description is continued assuming that the authentication ticket is valid as a result of the validity check of the authentication ticket.

Because the authentication ticket is valid the access controller requests the application data management wrapper to perform data registration by using the encoded user ID the encoded password the application ID the MFP user ID the tenant ID and the external service identifier.

In step S the application data management wrapper requests the application data management unit to perform data registration by using the encoded user ID the encoded password the application ID the MFP user ID the tenant ID and the external service identifier. In step S the application data management unit registers data in a setting information table unique to the application as illustrated in which is stored in the setting information storage unit unique to the application. illustrates an example of a setting information table unique to the application.

It is assumed that the setting information table unique to the application is also used in cases other than cooperating with the external service device and therefore the table has a general table configuration. The data stored in the setting information table unique to the application differs according to the application operating on the image forming apparatus .

The setting information table unique to the application illustrated in includes as items an application ID a tenant ID a Key1 a Key2 a Key3 and a Value. When cooperating with the external service device the items of the setting information table unique to the application are used as follows. Note that in the top two records are examples of cases of cooperating with the external service device .

The application ID is an application ID stored in the common SSO unit itself. The tenant ID is a tenant ID applied by the service providing system . The Key1 is the MFP user ID. The Key2 is the external service identifier. The Key3 is a column for storing the data type to be stored. The Value is the actual data to be stored.

For example in User id is stored as the data type expressing the encoded user ID in the first Key3 from the top. In password is stored as the data type expressing the encoded password in the second Key3 from the top.

The setting information table unique to the application of is constituted by multiple tenants and therefore in order to acquire information from the setting information storage unit unique to the application the tenant authentication of step S needs to be passed.

Note that when the common SSO unit holds the tenant authentication information the processes of steps S and S of are not performed. The common SSO unit acquires the MFP user ID of the user who has logged in from the operation panel after receiving the request for data registration from the application in step S.

The tenant authentication of step S is performed for example as illustrated in . is a sequence diagram of an example of a tenant authentication process. In step S the common SSO unit acquires the application ID and the application key stored in itself. In step S the common SSO unit requests to log into the service providing system by using the tenant ID the password the application ID and the application key.

At the service providing system that has received the request to log in first application authentication is performed in step S. Application authentication is the process illustrated in . Here the description is continued assuming that the validity of the common SSO unit has been confirmed passed application authentication .

In step S the access controller makes a login request to the authentication wrapper by using the tenant ID and the password. In step S the authentication wrapper makes a login request to the authentication allowance unit by using the tenant ID and the password. Here the description is continued assuming that the login is successful.

In step S the authentication allowance unit issues an authentication ticket. In step S the authentication allowance unit stores the issued authentication ticket in association with the tenant ID and the user ID in the authentication ticket table as illustrated in which is stored in the ticket information storage unit . illustrates an example of an authentication ticket table. The authentication ticket table is for managing authentication tickets issued by the service providing system . In order to access the resources of the service providing system protected by a tenant an authentication ticket issued by tenant authentication of is needed.

Furthermore the validity check of the authentication ticket of step S is performed for example as illustrated in . is a sequence diagram of a process of checking the validity of an authentication ticket. When using the resources of the service providing system protected by the authentication ticket the image forming apparatus needs to pass the validity check of an authentication ticket.

In step S the common SSO unit requests to use the public API to the service providing system by using the password input in step S of and the application ID and the application key acquired in step S. The validity check of the authentication ticket is performed when the request is made to use the public API .

The service providing system that has received the request to use the public API performs application authentication in step S. The application authentication is the process illustrated in . Here the description is continued assuming that the validity of the common SSO unit has been confirmed passed the application authentication .

In step S the access controller requests the authentication allowance unit to perform the validity check of the authentication ticket. In step S the authentication allowance unit performs matching of the authentication ticket included in the request for the validity check in step S and the authentication ticket recorded in the authentication ticket table as illustrated in . When the authentication ticket included in the request for the validity check is recorded in the authentication ticket table the authentication allowance unit determines that the authentication ticket is valid. When the authentication ticket is valid in step S the access controller makes a request to the process block of the API layer that responded to the original request.

The service registration process performed by the second image forming apparatus and onward is performed by for example the procedures as illustrated in . is a sequence diagram of an example of a service registration process performed by the second image forming apparatus and onward.

In step S the user inputs in the operation panel an MFP user ID and an MFP password for using the image forming apparatus and logs into the image forming apparatus .

When the login is successful in step S the image forming apparatus activates the application and displays a top screen on the operation panel . In step S the user inputs a tenant ID and a password in the top screen and requests service registration. The top screen may be provided with a mechanism that prompts the user to select a service registration process by the first image forming apparatus or a service registration process by the second image forming apparatus and onward.

In step S the operation panel acquires the MFP user ID of the user who has logged in. In step S the operation panel requests the application to perform service registration by using the tenant ID and the password. In step S the application records the MFP user ID the tenant ID and the password as tenant authentication information in the tenant authentication table illustrated in .

As described above in the service registration process performed by the second image forming apparatus and onward illustrated in the tenant ID issued by the service providing system in the service registration process performed by the first image forming apparatus is recorded as the tenant authentication information. Therefore the second image forming apparatus and onward is able to perform authentication with respect to the service providing system by the same tenant ID as that of the first image forming apparatus . In the information processing system according to the present embodiment once the authentication information of the external service device is registered in the service providing system the authentication information of the external service device can be used by the applications of a plurality of image forming apparatuses .

In step S the user activates the application that the user wants to use from the top screen. In step S the user requests to use an external service from the operation panel .

In step S the application acquires an encoding key held in itself. In step S the application acquires the MFP user ID of the user who has logged in from the operation panel . Furthermore in step S the application acquires a tenant ID and password associated with the MFP user ID from the tenant authentication table as illustrated in .

In step S the application requests the common SSO unit to acquire data by using the MFP user ID of the user who has logged in from the operation panel and the acquired encoded key tenant ID and password.

In step S the common SSO unit acquires the application ID and the application key stored in itself. Furthermore in step S the common SSO unit performs tenant authentication and acquires the authentication ticket of the service providing system . Here the description is continued assuming that the authentication ticket of the service providing system has been acquired.

In step S the common SSO unit requests the service providing system to acquire data by using the MFP user ID the external service identifier the application ID the application key and the authentication ticket.

In step S the service providing system performs a validity check of the authentication ticket illustrated in . Here the description is continued assuming that the authentication ticket is valid as a result of the validity check of the authentication ticket. Because the authentication ticket is valid the access controller requests the application data management wrapper to acquire data by using the application ID the MFP user ID and the tenant ID.

In step S the application data management wrapper requests the application data management unit to acquire data by using the application ID the MFP user ID and the tenant ID. In step S the application data management unit acquires data from the setting information table unique to the application illustrated in which is stored in the setting information storage unit unique to the application. The application data management unit acquires the encoded user ID and the encoded password from the setting information table unique to the application illustrated in .

The encoded user ID and the encoded password acquired from the setting information table unique to the application are returned to the common SSO unit of the image forming apparatus . In step S the common SSO unit decodes the encoded user ID and the encoded password with the encoding key received from the application and acquires the user ID of the external service and the password of the external service as the authentication information of the external service device .

In step S the common SSO unit returns to the application the user ID of the external service and the password of the external service as the authentication information of the external service device which are acquired by the decoding process performed in step S. As described above the application is able to acquire the user ID of the external service and the password of the external service as authentication information of the external service device .

In step S the application logs into the external service device by using the user ID of the external service and the password of the external service as authentication information of the external service device . When the login is successful the application acquires a ticket external service ticket issued by the external service device . In step S the application becomes capable of using a function provided by the external service device by using the external service ticket.

According to the external service usage process of the application is able to acquire the authentication information of the external service device stored in the service providing system via the common SSO unit . The authentication information of the external service device acquired from the service providing system is for example as illustrated in . illustrates an example of authentication information of the external service device . Therefore the application is able to use a function of the external service device by using the authentication information of the external service device acquired from the service providing system .

In the first embodiment the authentication information of the external service device is stored in the service providing system . In a second embodiment the authentication information of the external service device may be stored in an information storage device provided in the same intranet etc. as that of the image forming apparatus .

In the case of the information processing system immediately after step S of the data registration process of it is determined whether to use the service providing system or the information storage device as the data registration destination. When it is determined to use the information storage device as the data registration destination the common SSO unit skips from step S to step S and requests the information storage device to perform data registration in step S.

Furthermore in the case of the information processing system immediately after step S of the external service usage process of it is determined whether to use the service providing system or the information storage device as the data acquisition destination. When it is determined to use the information storage device as the data acquisition destination the common SSO unit skips from step S to step S and requests the information storage device to perform data acquisition in step S.

Furthermore in the information processing system according to the present embodiment the public API of the service providing system is used from the common SSO unit however the service providing system may be used from the application . In this case an application ID and an application key are issued for each application . The application is able to use the service providing system by using the application ID and the application key that have been issued for each application .

In the information processing system according to the present embodiment the service providing system may also be used from an application operating in the external service device or a terminal device such as a smartphone or a PC other than the application operating in the image forming apparatus .

According to the information processing system according to the present embodiment it is easy to develop and operate the application which operates in an electronic device such as the image forming apparatus and which performs processes in cooperation with the external service device .

For example in the information processing system according to the present embodiment by transferring the function of storing the authentication information of the external service device from the external service device to the service providing system it is possible to reduce the development processes of the application .

Furthermore once the application operating in the image forming apparatus registers the authentication information of the external service device in the service providing system a plurality of the image forming apparatuses are able to share the authentication information of the external service device . Furthermore in the information processing system according to the present embodiment the authentication information of the external service device can be held without depending on resource restrictions of the image forming apparatus . By providing the common SSO unit in the image forming apparatus it is possible to easily develop the application operating in the image forming apparatus by using the common SSO unit .

The information processing system and the authentication information providing method are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention.

Note that the common SSO unit is an example of a requesting unit. The access controller is an example of an access control unit. The application data management wrapper and the application data management unit are examples of a data management unit. The application ID and the application key are examples of identification information of the requesting unit. The API layer is an example of a public interface layer. The platform API is an example of a non public interface. The application data management unit is an example of a data acquiring unit. The application data management wrapper is an example of a non public interface hiding unit. The authentication wrapper and the authentication allowance unit are examples of an authentication unit. The tenant ID is an example of identification information of a group for grouping users of the electronic device.

According to one embodiment of the present invention an information processing system and an authentication information providing method are provided which are capable of easily developing an application that performs a process in cooperation with an external service.

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2014 047969 filed on Mar. 11 2014 the entire contents of which are hereby incorporated herein by reference.


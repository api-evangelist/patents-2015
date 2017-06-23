---

title: Information processing apparatus enabling cooperation with a network service and control method therefor
abstract: A first application installed on a multifunction peripheral (MFP) request a network communication unit to check a second application installed on the MFP to use an external service. The first application controls, according to a result of checking of the second application, registration processing for registering function information (intent element) used to cooperate with the external service by a relay function using a mechanism of Web Intents, or invocation processing by the relay function for invoking the external service using the registered function information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09516185&OS=09516185&RS=09516185
owner: Canon Kabushiki Kaisha
number: 09516185
owner_city: Tokyo
owner_country: JP
publication_date: 20150603
---
The present invention relates to technology for service management in information processing apparatuses that are capable of cooperating with an external service via a network.

Recently there has been developed an environment that allows an image processing apparatus which is an example of an information processing apparatus to expand functions of the image processing apparatus by installing an application thereon. Such an application can be prevented from being illegally installed or transferred generally by managing the application using a license associated with information that identifies image processing apparatuses. In this way the method of managing an application using a license can prevent an application that has been previously installed on an image processing apparatus and then has been copied onto another image processing apparatus from normally running.

Furthermore with the advancement of sophisticated functions of image processing apparatuses some image processing apparatuses have become equipped with a web browser. This has enabled image processing apparatuses to readily connect to a network.

Moreover there has been published a technique called Web Intents which facilitates the cooperation or collaboration between a plurality of applications without the use of a custom application programming interface API unique to a web application. It may be considered that the above mentioned Web Intents technique can be loaded onto a web browser or the like mounted in image processing apparatuses.

Japanese Patent Application Laid Open No. 2008 197824 discusses a method in which a main application utilizing an external application stores authentication information and plug ins of an external service in association with the external application and uses the authentication information to access the external application.

However in a case where an application running in an image processing apparatus cooperates with an external web application hereinafter referred to as an external service via a network according to the method discussed in Japanese Patent Application Laid Open No. 2008 197824 the conventional management of the application using a license cannot be applied to the cooperation with the external service.

In other words the method discussed in Japanese Patent Application Laid Open No. 2008 197824 does not enable the cooperation of an application running in an image processing apparatus which is an example of an information processing apparatus with a particular external service to be managed based on a license associated with the image processing apparatus. However there is a demand to appropriately manage the cooperation between an information processing apparatus and an external service based on a license.

According to an aspect of the present invention an information processing apparatus in which a relay function operates to cooperate with a service provided on a network includes a management unit configured to manage a plurality of applications installed on the information processing apparatus the plurality of applications including a first application capable of using the service provided on the network a checking unit configured to check with the management unit a second application different from the first application and installed to use the service provided on the network and a control unit configured to control according to a result of checking by the checking unit registration processing by the relay function for registering function information used to cooperate with the service provided on the network or invocation processing by the relay function for invoking the service provided on the network using the registered function information.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings. Constituent elements described in the following exemplary embodiments are merely examples and the scope of the present invention is not intended to be limited only to those elements.

Referring to servers and each function as an information processing apparatus that provides an external service. The servers and each include a web application serving as a service. The web application transmits content information to a web browser in response to an instruction from the web browser or the like.

An image processing apparatus functions as a device onto which various applications can be installed. All types of information processing apparatuses that allow various applications to run thereon can be the device according to the present exemplary embodiment. In the present exemplary embodiment for ease of description a multifunction peripheral MFP having a plurality of functions such as a printer function and a scanner function is taken as an example of the device . In the following description the term MFP means an image processing apparatus that allows an application to be installed thereon. Furthermore hereinafter the device is referred to as the MFP .

The MFP includes a web browser . The web browser receives an instruction from the user communicates with a specified server according to the received instruction acquires content from the server or and displays the content on a display unit not illustrated .

The MFP has an application A and an application B installed thereon. The application A corresponds to a first application in the present exemplary embodiment. The application A provides various functions on the MFP . The first application is able to use able to cooperate with a service provided on a network such as the web application via a network communication unit illustrated in which is described below. The web browser is also included in the first application.

The application B corresponds to a second application in the present exemplary embodiment. In a case where a specified application installed on the MFP the first application cooperates with an external service it becomes necessary to install the second application on the MFP . The second application is installed to use a service provided on the network and thus contains information used to identify an external service with which the MFP is permitted to cooperate the details of which are described below. In the present exemplary embodiment it is presumed that the second application does not have any special functions except containing information used to identify an external service with which the MFP is permitted to cooperate the details of which are described below.

A network is for example the Internet or an intranet. The MFP can be connected to the server the server or another information processing apparatus via the network .

To enable an application that is managed by the present network system it is necessary to install a license file on the MFP . Unless the license file is installed the application is stopped from operating by the application management function of the MFP . The license file contains identification information of a target application and information used to identify an MFP serving as an install destination of the application.

The information used to identify an MFP is for example a serial number of the MFP but may be other information such as a media access control MAC address as long as it is information that is usable to identify an MFP. To install the same application on another MFP it is necessary to additionally install a license file containing identification information of the corresponding MFP. Such a mechanism can prevent unauthorized copying of software in an MFP.

Referring to a control unit which includes a central processing unit CPU a read only memory ROM and a random access memory RAM controls operations of the entire MFP . The CPU reads control programs stored in the ROM and executes various control processing operations such as reading control and transmission control. The RAM is used as a temporary storage region such as a main memory or a work area for the CPU . Furthermore the control unit is connected to a functional unit and controls operations of an operation display unit a scanner unit and a printer unit which are included in the functional unit .

The operation display unit is provided with a display unit such as a liquid crystal display having a touch panel function and a keyboard. The operation display unit has a web browser function which is provided by the web browser . The web browser analyzes a HyperText Markup Language HTML file received from the server or another information processing apparatus and then displays on the operation display unit an operation screen generated based on the description of the analyzed HTML file.

The printer unit prints image data output from the control unit on a sheet. The scanner unit reads the image of an original to generate image data and outputs the generated image data to the control unit . An interface unit connects the control unit to the network to enable the control unit to receive from an external information processing apparatus not illustrated image data to be printed or image data to be displayed on the operation display unit . The image data to be printed received from the external information processing apparatus is temporarily stored into an image memory and is then printed by the printer unit via the control unit .

A hard disk drive HDD is a storage device configured to store image data or various programs. The HDD may be replaced by another storage device such as a solid state drive SSD .

Various pieces of software to illustrated in which are stored in the ROM or the HDD are executed by the CPU to provide various functions to the MFP .

An operating system OS is generally a real time OS but may be a general purpose OS such as Linux registered trademark . A Java virtual machine VM such as Java registered trademark provides an execution environment of applications. An application framework provides a function to manage life cycles of applications. An installer service performs installation processing by registering a plurality of applications such as an application A and an application B with the application framework . The Java VM or the application framework may be included in the OS .

The application A and the application B which were installed by the installer service provides various functions on the MFP . The application A and the application B can be downloaded from outside the MFP or can be read out from a recording medium to be installed. Although in the example illustrated in two applications are installed three or more applications may be installed.

At least one of the application A and the application B can interact with the user via the operation display unit . Furthermore at least one of the application A and the application B can generate image data using the scanner unit .

In the present exemplary embodiment the application A is supposed to be the first application and the application B is supposed to be the second application. Thus the application A corresponds to the application A or the web browser illustrated in and the application B corresponds to the application B illustrated in .

A Native function unit provides functions incorporated in the MFP . Examples of the Native functions include a function to perform printing by the printer unit based on print data received via the interface unit . In the present exemplary embodiment it is supposed that execution modules of the Java VM the application framework the application A and the application B are stored in the HDD . Furthermore it is supposed that an execution module of the Native function unit is stored in the ROM .

The network communication unit performs data communication with other devices connected to the network . For example the web browser which is mounted on the MFP can acquire hypertext type information from a web server on the network and display the acquired information on the operation display unit . The network connection configuration of the network communication unit is not limited to a wireless connection or wired connection.

Furthermore in the present exemplary embodiment the network communication unit executes request transmission or exchanges data between the first application for example the application A or the web browser and an external service for example the web application . Thus the network communication unit operates as a relay function for causing the first application and the external service to cooperate with each other.

Examples of the first application include an application for generating image data using the scanner unit then invoking an image processing service provided by a server present outside the MFP processing the generated image data and storing the processed image data into the HDD . Examples of the image processing service include a photo editor service for clipping photographic data at a predetermined size and an icon creation service for creating an icon usable for a web page from photographic data.

Furthermore it is supposed that the first application is previously installed on the MFP and is enabled. The user can register a service with the first application by after activating the first application invoking the service registration screen at a desired timing with a predetermined operation and then entering via the operation display unit the address of a server that provides the service.

In the present exemplary embodiment Web Intents is used as an example of a unit for causing an application and a service to cooperate with each other. In other words the cooperation between the first application and the external service is performed using a mechanism of Web Intents. Hereinafter Web Intents is referred to as an intent .

Referring to the service registration screen contains an address entry field . The user can enter into the address entry field the address of a server that provides a service that the user wants to register. It is supposed that the address is to be entered in the Uniform Resource Locator URL format and index.html is located immediately below the entered directory. It is supposed that an intent element such as that illustrated in which is described below is written in the header of index.html . The intent element contains function information for invoking a service. The user can enter the address into the address entry field and press an OK button to acquire the intent element from a server with the entered address and to register the service. The service that has been registered via the service registration screen illustrated in is registered with an intent list such as that illustrated in which is described below.

For example the first application generates image data using the scanner unit in response to the user instruction then displays the service selection screen and prompts the user to select an image processing destination via the service selection screen. The user selects a desired service from among image processing services in the example illustrated in photo editor synthesis generator and icon creation displayed in an image processing service list and requests the selected service to perform image processing. When the image processing service has completed the image processing the first application stores the processed image data into the HDD and displays a completion screen not illustrated on the operation display unit .

The service selection screen illustrated in contains the image processing service list . In the image processing service list services related to image processing are displayed among the services entered in an intent list illustrated in which is described below. The user can select a service in the image processing service list and press an OK button to request the service to perform image processing.

As mentioned in the foregoing in the present exemplary embodiment an intent is used as an example of a mechanism for joining applications software or functions included in software. An application displays a list of other applications or services that are able to perform processing on data to the user based on the intent element. The user when wanting to perform some processing operation on data specifies an application or service among the displayed applications or services so that the user can perform a desired processing operation on the data without performing a special operation for passing the data to the specified application or service.

An html header that a web browser or the like acquires from a server based on a predetermined procedure contains an intent element indicated by . In the present exemplary embodiment the network communication unit reads the intent element and registers the read intent element with an intent list which is described below. The intent list indicates intent elements which are returned by servers that provide services for performing processing operations on image data in predetermined formats. Examples of the intent elements are as follows.

An element action indicates the category of a function that the service provides in the URL format. In other words the element action indicates what function or service the provided function provides. In the example illustrated in the element action means edit . Examples of the categories of the provided functions include besides the category edit which means editing of data a category share which means sharing of data a category save which means saving of data a category view which means viewing of data and a category pick which means acquisition of data.

An element type indicates the data format of content that the provided function is able to process. In the example illustrated in image means image data and means all image formats. Furthermore a specific image format such as jpeg or bmp may be used instead of . Moreover the element type may indicate a data format other than image data. For example the element type may indicate a data format of text or audio data or a data format of a specific application.

An element href indicates the address at which the entity of the service is present. An html file which is the entity of the service is stored at the address indicated by the element href . An element title indicates the title of the service.

A service of the intent in which the element action indicates edit and the element type indicates image data is listed as an image processing service and a character string specified by the element title is displayed in the image processing service list illustrated in .

The intent list is stored in a region previously allocated in a storage device such as the HDD or the RAM and contains a list of external services registered via the service registration screen illustrated in .

Referring to a column represents an identifier ID in the list. A column indicates a title. A column indicates the storage location of an html file which is the entity of the service. A column indicates the type of data that the service handles. A column indicates an action function information that the service provides . A column indicates the address of a server that provides an external service. The values of the elements title href type and action of the intent element that the external service specified via the service registration screen returns are respectively stored in the columns to . In the example illustrated in three external services are registered.

The record indicated by ID 1 corresponds to a registration example in a case where the external service represented by http mysite.org has returned the intent element illustrated in . An application conforming to intents an application classified into the first application can display to the user an external service registered with the intent list as a candidate for cooperation as illustrated in .

Furthermore the intent list illustrated in FIG. is common to all of the applications conforming to intents the applications classified into the first application . Each service registered with the intent list is able to be invoked by any application classified into the first application.

Referring to an application file itself is composed of a single file generated by compressing a plurality of files such as a CAB file a Java registered trademark Archive JAR file and a ZIP file.

The manifest file contains description of an application name an application ID for uniquely identifying the present application and application ancillary information such as a version. The application program is encrypted to prevent the program from being altered by a third party.

The application file is distributed to users via a storage medium such as a compact disc CD or a communication medium such as the Internet and is decrypted and executed by an MFP onto which the application file is installed.

In the present exemplary embodiment items to be described in the manifest file are defined as follows. An application name represents the name of an application. An application ID represents an identifier for uniquely identifying the application. An application type represents the type of the application. If the value of the application type is 70 the type of the application is a general application i.e. the first application in the present exemplary embodiment. If the value of the application type is 100 the type of the application is an application used to permit the MFP to use cooperate with an external service i.e. the second application in the present exemplary embodiment. A version represents the version of the application.

A service host represents the address of a server that provides the service in the URL format. The address written in the service host is set as the address of a service which the application permits the MFP to use. An intent reference represents the reference of the entity of the service. The reference destination of the service is obtained by joining the service host and the intent reference . The service host and the intent reference are set when the application type is 100 i.e. the second application. The service indicated by the reference destination specified by the service host and the intent reference means an external service with which the second application permits a specific application to cooperate.

Referring to a license ID represents a unique ID for identifying a license. An application ID represents an ID for uniquely identifying an application that is a target for setting the license. An expiration date represents the expiration date for use of the application targeted for setting the license.

A device ID represents an ID for example a serial number for uniquely identifying an MFP on which the application targeted for setting the license is able to be installed. Information used for decrypting the encrypted application program of the application targeted for setting the license is stored in decryption data .

The installer service illustrated in determines whether the application is enabled or disabled based on information described in a license file such as that illustrated in . If the following conditions are satisfied the installer service enables the license for the application.

Relevant information of the application installed via the installer service is stored as appropriate in a region previously allocated in a storage device such as the HDD or the RAM . The relevant information includes for example information described in a manifest file and information required for application management.

Referring to a column represents an index for discriminating between applications in the application list. A column represents the name of an application. A column represents an ID for uniquely identifying an application. A column represents the type of an application. If the type is 70 the type of an application is the first application. If the type is 100 the type of an application is the second application.

A service host represents the address of a host that provides a service. An application with the service host in blank does not provide any service. A reference represents the address of a storage location for an html file which is the entity of a service. An expiration date represents the expiration date for use of an application. A license represents the ID of a license file.

Values of the columns to are set based on information described in a manifest file of the corresponding application. Furthermore the expiration date and the license can be registered with the application list when the installer service recognizes that the program the manifest file and the license file are not the forged ones based on a predetermined procedure. In the example illustrated in three applications are registered.

The first application when activated starts the processing in the flowchart of . First in step S the first application performs initialization based on a predetermined procedure. During the initialization the first application allocates a work area in a storage device such as the HDD or the RAM .

Next in step S the first application determines whether an instruction for service registration has been received from the user. For example when an address has been entered and the OK button has been pressed on a service registration screen such as that illustrated in the first application determines that an instruction for service registration has been received from the user.

If in step S the first application determines that an instruction for service registration has been received from the user YES in step S the processing proceeds to step S.

In step S the first application performs service registration processing which is described below. When the first application has completed the service registration processing the processing returns to step S.

On the other hand if in step S the first application determines that no instruction for service registration has been received from the user NO in step S the processing proceeds to step S.

In step S the first application determines whether an instruction for function execution has been received from the user. Here it is supposed that the instruction for function execution is an instruction for scan execution issued from the user in the first application. For example when an operation indicating a scan instruction has been performed by the user via a scan instruction screen not illustrated of the first application the first application determines that an instruction for function execution has been received from the user. The term operation indicating a scan instruction means for example an operation to press a scan execution button via a scan instruction screen not illustrated .

Then if in step S the first application determines that an instruction for function execution has been received from the user YES in step S the processing proceeds to step S.

In step S the first application performs processing for function execution which is described below. When the first application has completed the processing for function execution the processing returns to step S.

On the other hand if in step S the first application determines that no instruction for function execution has been received from the user NO in step S the processing proceeds to step S.

In step S the first application determines whether a termination instruction has been received from the user. For example when an operation indicating termination has been performed by the user via a termination instruction screen not illustrated of the first application the first application determines that a termination instruction has been received from the user.

If in step S the first application determines that no termination instruction has been received from the user NO in step S the processing returns to step S.

On the other hand if in step S the first application determines that a termination instruction has been received from the user YES in step S the processing ends.

Next the service registration processing performed in step S illustrated in is described with reference to .

In step S the first application displays the service registration screen which is illustrated in on the operation display unit .

Next in step S the first application determines whether an address has been entered via the service registration screen. For example when an address for specifying a server has been entered into the address entry field and the OK button has been pressed by the user the first application determines that an address has been entered. The entered address is stored into a work area previously prepared in a storage device such as the HDD .

If in step S the first application determines that no address has been entered NO in step S the processing repeats the determination in step S. Furthermore although not illustrated in a case where the service registration screen is closed without an address being entered the first application directly ends the service registration processing.

On the other hand if in step S the first application determines that an address has been entered YES in step S the processing proceeds to step S.

In step S the first application acquires an intent element. More specifically the first application transmits a request from the network communication unit to the server address which is stored in the work area in step S via the application framework . The server when receiving the request transmits to the network communication unit a response with a header containing an intent element such as that illustrated in . The network communication unit extracts the intent element from the header of the response generates one record for an intent list such as that illustrated in based on the intent element and stores the generated record into a work area allocated in a storage device such as the HDD .

Next in step S the network communication unit adds and stores the record generated and stored in the work area in step S to the intent list stored in a region previously prepared in a storage device such as the HDD . Then the network communication unit issues a notification to the first application indicating that the registration of the record with the intent list has been completed. When receiving the notification the first application ends the service registration processing.

Next the function execution processing performed in step S illustrated in is described with reference to .

First in step S the first application performs scan processing. More specifically the first application acquires image data from the scanner unit based on a predetermined procedure and stores the acquired image data into a work area allocated in a storage device such as the HDD via the control unit .

Next in step S the first application determines whether the number of registered intents is 0 . More specifically the first application checks the number of records in an intent list such as that illustrated in which is stored in a region previously allocated in a storage device such as the HDD or the RAM . If the number of records is 0 the first application determines that the number of registered intents is 0 .

Then if in step S the first application determines that the number of registered intents is 0 YES in step S the processing directly proceeds to step S.

On the other hand if in step S the first application determines that the number of registered intents is not 0 NO in step S the processing proceeds to step S. In step S the first application displays the service selection screen. More specifically the first application refers to information of type for example Image and action for example edit of processing with which the first application intends to cooperate and acquires information of the corresponding record from the intent list such as that illustrated in . Then the first application generates the image processing service list such as that illustrated in based on the acquired information generates the service selection screen such as that illustrated in and displays the generated service selection screen on the operation display unit . Then if a service is selected on the displayed service selection screen the first application specifies a list item that is in a selected state from among the image processing service list . Then the processing proceeds to step S. Furthermore also in a case where there is no record in the intent list corresponding to type for example Image and action for example edit of processing with which the first application intends to cooperate it is supposed that the processing directly proceeds to step S.

Next in step S the first application acquires the values of host and href from an intent corresponding to the service selected via the service selection screen joins the acquired values to generate a reference destination of the service and stores the reference destination into a work area previously allocated in the RAM or the like. Furthermore the first application requests the network communication unit to collate the reference destination of the service.

In step S the network communication unit acquires one record from the application list such as that illustrated in . More specifically the network communication unit acquires one record the expiration date of which is not exceeded from the application list illustrated in acquires information of an application the license of which is enabled and stores the acquired record into a work area previously allocated in the RAM or the like.

Next in step S the network communication unit determines whether the references coincide. The network communication unit determines that the references coincide in a case where a value generated from the service host and the reference of the record in the application list stored in the work area in step S coincides with the reference destination of the service stored in the work area in step S. In other words the network communication unit determines that an application the second application that permits the MFP to use to cooperate with the user s desired service is present among applications which are installed on the MFP and the licenses of which are enabled.

If in step S the network communication unit determines that the references do not coincide NO in step S the processing proceeds to step S.

In step S the network communication unit determines whether all of the records in the application list have been searched the processing in steps S to S has been executed with respect to all of the records . If the network communication unit determines that not all of the records in the application list have been searched NO in step S the processing returns to step S.

On the other hand if in step S the network communication unit determines that all of the records in the application list have been searched YES in step S since there is no application that permits the MFP to cooperate with the user s desired service the network communication unit notifies the first application of stopping the invocation of the service. Then the processing proceeds to step S.

In step S the first application displays an error screen not illustrated on the operation display unit . Then the processing proceeds to step S. In other words the cooperation of the MFP with the service selected by the user acquired in step S is inhibited stopped since there is no application that permits the MFP to cooperate with the service in the list of applications installed on the MFP.

If in step S the network communication unit determines that the references coincide YES in step S the processing proceeds to step S.

In step S the network communication unit acquires page data. More specifically the network communication unit accesses the reference destination of the service stored into the work area in step S and acquires page data from the reference destination based on a predetermined procedure. It is supposed that the page data contains a script required for data processing which is described below. The network communication unit passes the acquired page data to the first application.

In step S the first application processes image data stored into the work area allocated in a storage device such as the HDD in step S according to the script contained in the page data acquired in step S and stores the processed image data into the work area. Then the processing proceeds to step S.

In step S the first application stores as appropriate the image data stored in the work area allocated in a storage device such as the HDD into an image data storage region previously allocated in a storage device such as the HDD and discards the image data stored in the work area. Then the first application ends the function execution processing.

Next the entire sequence of processing in the first exemplary embodiment is described with reference to .

In step S the first application displays on the operation display unit the service registration screen such as that illustrated in in response to the instruction issued in step S. The present step corresponds to step S in the flowchart of .

Next in step S the user instructs the first application via the service registration screen displayed in step S to register the service.

In step S in response to the instruction issued in step S the first application requests the network communication unit to access a server specified by the instruction issued in step S.

In step S in response to the request issued in step S the network communication unit requests content from the specified server based on a predetermined procedure. The present step corresponds to step S in the flowchart of .

In step S in response to the request issued in step S the server returns as a response content containing an intent element to the network communication unit . Then the network communication unit receives the content sent as a response from the server.

Next in step S the network communication unit adds an intent acquired in step S to an intent list such as that illustrated in . The present step corresponds to step S in the flowchart of .

Next in step S the network communication unit returns to the first application a response indicating the success of service registration. Then the first application receives the response.

Next in step S the first application generates a service registration success screen not illustrated and displays the service registration success screen on the operation display unit to inform the user of the success of service registration.

Then in step S the user instructs the first application to execute functions included in the first application.

In step S in response to the instruction issued in step S the first application executes a function . Here it is supposed that the function is a scan function. The present step corresponds to step S in the flowchart of .

Next in step S the first application acquires the intent list. For ease of description a sequence performed in a case where the number of registered intents is 0 omitted. Furthermore a sequence performed in a case where there is no intent of the type and action with which the MFP is intended to cooperate is also omitted.

Next in step S the first application generates a service selection screen such as that illustrated in based on the intent list acquired in step S and displays the service selection screen on the operation display unit . The present step corresponds to step S in the flowchart of .

Next in step S the user issues to the first application via the service selection screen generated in step S an instruction specifying a service with which the MFP is intended to cooperate.

In step S in response to the instruction issued in step S the first application requests the network communication unit to collate the reference destination of the service specified by the user as a cooperation destination in step S.

In step S in response to the request issued in step S the network communication unit searches an application list such as that illustrated in and checks whether there is a record in the application list coinciding with the reference destination. Then the network communication unit causes the processing to branch depending on a result of checking in step S.

If in step S the network communication unit determines that there is no record coinciding with the reference destination in the case of reference destination noncoincidence the processing proceeds to step S.

In step S the network communication unit returns to the first application a response indicating the noncoincidence of the reference destination. Then the first application receives the response from the network communication unit .

In step S based on the response in step S the first application displays an error screen not illustrated on the operation display unit . The present step corresponds to step S in the flowchart of .

On the other hand if in step S the network communication unit determines that there is a record coinciding with the reference destination in the case of reference destination coincidence the processing proceeds to step S.

In step S the network communication unit issues a request for content to a server corresponding to the reference destination. The present step corresponds to step S in the flowchart of .

In step S in response to the request issued in step S the server returns to the network communication unit page data as a response to the request issued in step S. Then the network communication unit receives the response from the server.

In step S the network communication unit returns to the first application the page data acquired in step S as a response. Then the first application receives the response from the network communication unit .

In step S the first application executes a function . Here it is supposed that the function is a function to process the image data obtained by the function executed in step S and to store the processed image data into a storage device. In other words the first application processes the image data obtained in step S using a script contained in the page data returned from the network communication unit in step S and stores the processed image data into the HDD . The present step corresponds to steps S and S in the flowchart of .

Next in step S the first application generates a completion screen not illustrated and displays the completion screen on the operation display unit to inform the user of the completion of the processing.

As described above according to the first exemplary embodiment among services specified by the user as cooperation destinations at the time of execution of a first application only a service for which a second application which is used to permit the MFP to use the service is enabled is permitted to be used. On the other hand a service for which the second application is not enabled is not permitted to be used. This enables the first application to cooperate with only a service with which the MFP is permitted to cooperate among services specified by the user as cooperation destinations. In this way the cooperation of the MFP with an external service can be managed based on the license of the second application installable on the MFP.

In steps S and S illustrated in and steps S to S illustrated in the MFP acquires page data containing a script from the server and processes image data according to the script. However instead of steps S and S illustrated in and steps S to S illustrated in the first application may transmit image data acquired in step S to the server the server may process the image data and the MFP may receive the processed image data from the server.

Furthermore the service is not limited to processing of image data. For example the service may be an operation for posting image data or comments to a viewing website of a social networking service SNS . Furthermore in a case where user authentication or a user s operation is required for the service to provide a function the user may perform an operation on the operation display unit of the MFP .

Furthermore in the foregoing description the network communication unit is configured to register a service with an intent list for example step S illustrated in . However the first application or another function may register a service with an intent list. For example a web browser may perform registration or there may be dedicated software for registering a service with an intent list.

Furthermore the network communication unit may perform step S SEARCH INTENT LIST illustrated in or step S DISPLAY SERVICE SELECTION SCREEN illustrated in . In this case it is supposed that the first application notifies the network communication unit of information of type for example Image and action for example edit of processing with which the MFP is intended to cooperate.

Moreover the first application may perform step S SEARCH APPLICATION LIST illustrated in and the processing for branching depending on a result of the search.

Additionally a web browser may operate between the first application and the network communication unit and the web browser may perform step S DISPLAY SERVICE REGISTRATION SCREEN step S INTENT LIST REGISTRATION step S SEARCH INTENT LIST step S DISPLAY SERVICE SELECTION SCREEN step S SEARCH APPLICATION LIST and the processing for branching. In this case it is supposed that the first application notifies the web browser of information of type for example Image and action for example edit of processing with which the MFP is intended to cooperate.

The above described first exemplary embodiment is configured to search installed applications at the timing of execution of a service and to prevent other than a service or services that are permitted to be executed among the searched applications from being executed. On the other hand the following second exemplary embodiment is configured to search installed applications at the timing of registering a service with an intent list and to prevent other than a service or services that are permitted to be executed among the searched applications from being registered with the intent list. For ease of description a configuration of the second exemplary embodiment similar to that of the first exemplary embodiment is omitted from the following description and only points different from those of the first exemplary embodiment are described. Hereinafter the second exemplary embodiment is described with reference to .

In step S the network communication unit generates a reference destination for the entity of a service. More specifically the network communication unit joins the value of href of the intent element acquired in step S and the address stored in the work area in step S to generate a reference destination for the entity of a service and stores the reference destination into a work area allocated in a storage device such as the HDD .

Next in step S the network communication unit acquires one record from the application list such as that illustrated in . More specifically the network communication unit acquires one record the expiration date of which is not exceeded from the application list illustrated in and stores the acquired record into a work area previously allocated in the RAM or the like.

Next in step S the network communication unit determines whether the references coincide. The network communication unit determines that the references coincide in a case where the reference destination of the service stored in the work area in step S coincides with a value generated from service host and reference of the record in the application list stored in the work area in step S. In other words the network communication unit determines that an application the second application that permits the MFP to cooperate with the user s desired service is present among applications which are installed on the MFP and the licenses of which are enabled.

If in step S the network communication unit determines that the references do not coincide NO in step S the processing proceeds to step S.

In step S the network communication unit determines whether all of the records in the application list have been searched the processing in steps S to S has been executed with respect to all of the records . If the network communication unit determines that not all of the records in the application list have been searched NO in step S the processing returns to step S.

On the other hand if in step S the network communication unit determines that all of the records in the application list have been searched YES in step S since there is no application that permits the MFP to cooperate with the user s desired service the network communication unit notifies the first application of stopping the registration of the service. Then the processing proceeds to step S.

In step S the first application displays an error screen not illustrated on the operation display unit . Then the first application ends the service registration processing. In other words the registration of the service specified by the user in step S is inhibited stopped since there is no application that permits the MFP to cooperate with the service in the list of applications installed on the MFP.

If in step S the network communication unit determines that the references coincide YES in step S the processing proceeds to step S.

In step S the network communication unit registers the intent element acquired in sep S with an intent list such as that illustrated in and issues a notification to the first application indicating that the intent element has been registered with the intent list. When receiving the notification the first application ends the service registration processing.

As described above according to the second exemplary embodiment only a service for which a second application which is used to permit the MFP to use the service is enabled at the time of registration of the service is permitted to be registered. On the other hand a service for which the second application is not enabled is not permitted to be registered. This enables the first application to cooperate with only a service with which the MFP is permitted to cooperate among services specified by the user as cooperation destinations. In this way the cooperation of the MFP with an external service can be managed based on the license of the second application installable on the MFP.

The above described first and second exemplary embodiments are configured to acquire an intent element from a server that provides a service and to register the intent element with an intent list. On the other hand the following third exemplary embodiment is not configured to acquire an intent element from a server that provides a service but configured to allow an intent element to be previously described in a manifest of a second application and to acquire the intent element from the manifest. For ease of description a configuration of the third exemplary embodiment similar to that of the first or second exemplary embodiment is omitted from the following description and only points different from those of the first or second exemplary embodiment are described. Hereinafter the third exemplary embodiment is described with reference to .

A manifest file illustrated in contains in addition to the constituents illustrated in an intent title an intent type and an intent action . In other words the third exemplary embodiment is configured to describe in the manifest file the same information as the information described in an intent element sent as a response from a server that provides a service together with the intent reference .

Although details are described below the third exemplary embodiment is configured to generate information to be registered with an intent list using information of the intent title the intent type and the intent action in the manifest file. For ease of description it is supposed that the server that provides a service returns one intent and one intent is described in the manifest illustrated in .

A difference between and is an intent ID illustrated in . The intent ID indicates an ID in the intent list illustrated in . In a row in which a numerical value is stored in the intent ID the intent of a service that is permitted by the corresponding application to be accessed by the MFP is indicated by the ID in the intent list.

The first application requests the network communication unit to check the server address stored in the work area in step S.

In step S the network communication unit acquires one record from the application list such as that illustrated in . More specifically the network communication unit acquires one record the expiration date of which is not exceeded from the application list illustrated in and stores the acquired record into a work area previously allocated in the RAM or the like.

Next in step S the network communication unit determines whether the addresses about the server that provides an external service coincide. The network communication unit determines that the addresses about the server that provides an external service coincide in a case where the address entered in step S and stored in the work area coincides with the value of the service host of the record in the application list acquired in step S.

If in step S the network communication unit determines that the addresses about the server that provides an external service do no coincide NO in step S the processing proceeds to step S.

On the other hand if in step S the network communication unit determines that the addresses about the server that provides an external service coincide YES in step S the processing proceeds to step S.

In step S the network communication unit acquires an intent element. More specifically the first application acquires information of the intent element for example the intent title the intent type and the intent action from the manifest file corresponding to the record in the application list acquired in step S generates one record for an intent list such as that illustrated in based on the intent element and stores the generated record into a work area allocated in a storage device such as the HDD .

Next in step S the first application adds and stores registers the one record for an intent list stored in the work area in step S to the intent list stored in a region previously prepared in a storage device such as the HDD . Furthermore the first application registers the value of the ID of the registered record in the intent list with the intent ID of the record in the application list acquired in step S.

Furthermore although not illustrated in a case where a value is already stored in the intent ID of the record in the application list in which the addresses coincide in step S the first application determines that the corresponding service is already registered with the intent list thus directly ending the service registration processing. In this instance the first application may display on the operation display unit a message indicating that the corresponding service is already registered thus informing the user of that effect.

Furthermore at the time of registration of the second application the installer service may register the path of the application file or the manifest file of the second application with the application list. Then the network communication unit may find the manifest file using information of the path and register the service with the intent list in steps S and S illustrated in .

Furthermore at the time of registration of the second application the installer service may register information of the intent title the intent type and the intent action with the application list. Then the first application may register the service with the intent list using information contained in the application list in steps S and S illustrated in .

Moreover at the time of registration of the second application the installer service may register with the intent list a service with which the second application permits the MFP to cooperate using information of the manifest file the service host the intent title the intent type the intent action and the intent reference .

As described above according to the third exemplary embodiment if an application that permits the MFP to cooperate with a service specified by the user is enabled an intent element of the service can be acquired from the application and then registered with an intent list. Accordingly processing for accessing a server that provides the service at the time of service registration can be omitted and the registration of the service with a device can be completed even if the server is temporarily unable to be accessed for example even if the server is not powered on at the time of service registration. This enables the first application to cooperate with only a service with which the MFP is permitted to cooperate among services specified by the user as cooperation destinations. In this way the cooperation of the MFP with an external service can be managed based on the second application installable on the MFP.

Furthermore the MFP in the second exemplary embodiment and the third exemplary embodiment periodically checks the application list. Then if the intent of a service with which an application the expiration date of which is exceeded permits the MFP to cooperate is registered with the intent list the MFP deletes the registration of the intent from the intent list. Alternatively the MFP periodically checks the application list. Then if the intent of a service with which an application that is not present that is uninstalled permits the MFP to cooperate is registered with the intent list the MFP deletes the registration of the intent from the intent list. Alternatively if a second application is uninstalled deleted and the intent of a service with which the second application permits the MFP to cooperate is registered with the intent list the MFP deletes the registration of the intent from the intent list.

In the above described first to third exemplary embodiments the operation of the second application does not affect the operations of the first application and an external service and the cooperation action. Accordingly when the present invention is applied the second application does not need to be activated. Furthermore the present invention can be applied even when the second application is implemented as a program that can be activated or a program that cannot be activated.

Moreover while an example has been described in which the first application and the second application are applications that are additionally installed the present invention can be applied even if either or both of the first application and the second application are implemented as functions Native functions previously provided to an image processing apparatus. Additionally the present invention can be applied even if the first application is used as a web browser and a web application cooperates with a service.

Furthermore while an example has been described in which a service with which the first application cooperates is used as an external service the present invention can be applied even if the service with which the first application cooperates is a function Native function previously provided to an image processing apparatus. In other words some functions that are incorporated in the MFP as Native functions can be configured to be unable to be executed unless the second application is enabled. Accordingly some of functions that are incorporated in the MFP as Native functions can be configured to be unable to be used until after the license of the second application is purchased and the second application is enabled. In other words the present invention can be applied even when a combination of the first application and the service runs within the same system within the same apparatus .

Furthermore a function for causing the first application and an external service to cooperate with each other can be implemented by the OS .

In the above described first to third exemplary embodiments an MFP is taken as an example of an information processing apparatus on which a first application that cooperates with an external service runs. However examples of the information processing apparatus can include a computer peripheral apparatus such as a printer a scanner and a camera a personal computer a smartphone a tablet computer a car navigation apparatus a television apparatus a hard disk recorder and other home electric appliances connectable to networks.

Furthermore in the above described first to third exemplary embodiments Web Intents is used as a technique for cooperation with a web application. However Web Intents is merely an example and another mechanism for allowing a client and a service to cooperate with each other via a similar relay function may be used. For example another technique called Web Activities may be used or a similar proprietary specification may be used to implement the present invention. In such a case pieces of information equivalent to action type href and title may be defined with different names.

As described above according to each exemplary embodiment of the present invention an MFP can access only a service with which the MFP is permitted to cooperate among services specified by the user as cooperation destinations. Therefore the first application is enabled to cooperate with only a service with which the MFP is permitted by the second application to cooperate.

Furthermore only a service with which the MFP is permitted to cooperate at the time of service registration can be registered with an intent list. Therefore the first application is enabled to cooperate with only a service with which the MFP is permitted by the second application to cooperate.

Moreover a service with which the MFP is permitted to cooperate can be registered without accessing a server at the time of service registration. Therefore the first application is enabled to cooperate with only a service with which the MFP is permitted by the second application to cooperate.

Accordingly for example without the provision of a special license management function on an external service or an external server that provides the external service an external service with which an application running on an image processing apparatus cooperates can be managed based on a license associated with the image processing apparatus. Thus the use of the external service by the image processing apparatus can also be managed in a similar way as that of the application running on the image processing apparatus. In this way the cooperation between an information processing apparatus such as an MFP and a service can be appropriately managed. Therefore any decrease in security which may be caused by an application cooperating without permission with a service that should be prevented from cooperation from a viewpoint of security can be prevented or reduced.

Furthermore the configuration and content of the above mentioned various data are not restrictive. Various configurations and contents can be used according to uses and purposes.

While various exemplary embodiments have been described above the present invention can be embodied in the form of for example a system an apparatus a method a program or a storage medium. Specifically the present invention can be applied to a system composed of a plurality of devices or can be applied to an apparatus composed of a single device.

Furthermore a configuration obtained by combining some or all of the above described exemplary embodiments is also encompassed by the present invention.

Embodiments of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present invention and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a central processing unit CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2014 117650 filed Jun. 6 2014 which is hereby incorporated by reference herein in its entirety.


---

title: Terminal device and data passing method
abstract: A terminal device passes data between programs. The terminal device includes a data passing unit configured to receive the data from a first program and pass the received data to a second program selected from among one or more second programs associated with a type of the received data; the first program configured to convert the type of the data, which is a passing target, from an original type into a unique type, and then pass the data to the data passing unit; and the second program configured to convert the type of the data received from the data passing unit into the original type from the unique type, the second program being associated with the unique type.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09417937&OS=09417937&RS=09417937
owner: RICOH COMPANY, LTD.
number: 09417937
owner_city: Tokyo
owner_country: JP
publication_date: 20150122
---
Conventionally there is known a data passing method in which the load of applications can be reduced when passing data between a plurality of applications see for example Patent Document 1 .

For example there is an operating system hereinafter OS for providing a file passing function for passing files between different applications. In order to use a file passing function of a conventional OS the applications specify the type of processable file for example pdf in the OS.

When the application of the file passing side performs a process of passing a file the file passing function of the OS presents to the user a list of applications that can process the file that is the target of passing. The user selects from the list an application for passing a file such that the file can be passed.

However in a conventional file passing function when the type of file is a generally well known file type the number of applications that can process the file to be passed increases and therefore the number of applications included in the list increases.

The present invention provides a terminal device and a data passing method in which one or more of the above described disadvantages are eliminated.

According to an aspect of the present invention there is provided a terminal device for passing data between programs the terminal device including a data passing unit configured to receive the data from a first program and pass the received data to a second program selected from among one or more second programs associated with a type of the received data the first program configured to convert the type of the data which is a passing target from an original type into a unique type and then pass the data to the data passing unit and the second program configured to convert the type of the data received from the data passing unit into the original type from the unique type the second program being associated with the unique type.

According to an aspect of the present invention there is provided a non transitory computer readable recording medium storing a program that causes a computer to execute a process the computer constituting a terminal device for passing data between a first program and a second program the terminal device including a data passing unit configured to receive the data from the first program and pass the received data to the second program selected from among one or more second programs associated with a type of the received data the process including converting by the first program the type of the data which is a passing target from an original type into a unique type and then passing the data to the data passing unit and converting by the second program the type of the data received from the data passing unit into the original type from the unique type the second program being associated with the unique type.

According to an aspect of the present invention there is provided a data passing method executed by a terminal device for passing data between programs the data passing method including converting by a first program a type of the data which is a passing target from an original type into a unique type and then passing the data to a data passing unit receiving by the data passing unit the data from the first program and passing the received data to a second program selected from among one or more second programs associated with the type of the received data and converting by the second program the type of the data received from the data passing unit into the original type from the unique type the second program being associated with the unique type.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

A terminal device according to the present embodiment is realized by a computer having a hardware configuration for example as illustrated in . illustrates an example of a hardware configuration of the computer according to the present embodiment.

The computer illustrated in includes an input device a display device an external I F a RAM a ROM a CPU a communication I F and a HDD which are interconnected by a bus B.

The input device includes a touch panel a keyboard and a mouse and is used for inputting various operation signals to the computer . The display device includes a display and displays processing results obtained by the computer . Note that the input device and the display device may have a form of being connected and used according to need.

The communication I F is an interface for connecting the computer to a network. Accordingly the computer can perform data communication with other computers via the communication I F .

Furthermore the HDD is an example of a non volatile storage device storing programs and data. The stored programs and data include an OS which is the basic software for controlling the entire computer and applications for providing various functions on the OS. Note that the computer may use a drive device for example a solid state drive SSD using a flash memory as a storage medium. The storage areas in the HDD that can be used by the applications are determined and managed by the OS as described below.

The external I F is an interface between the computer and an external device. An example of the external device is a recording medium . Accordingly the computer can perform reading and or writing with respect to the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD a DVD an SD memory card and a USB memory. The computer may have a configuration without the external I F .

The ROM is an example of a non volatile semiconductor memory storage device that can store programs and data even after the power is turned off. The ROM stores programs and data such as BIOS which is executed when the computer is activated OS settings and network settings. The RAM is an example of a volatile semiconductor memory for temporarily storing programs and data.

The CPU is a processor for implementing control and realizing functions of the entire computer by loading programs and data in the RAM from storage devices such as the ROM and the HDD and executing processes. Note that the computer may have a hardware configuration other than that illustrated in for example the computer may have a built in camera a microphone and a speaker.

The terminal device according to the present embodiment can realize various processes as described below by executing programs in the computer having the above hardware configuration for example.

A terminal device according to the present embodiment is realized by for example the following functional blocks.

The terminal device is realized by for example the functional blocks as illustrated in . is a functional block diagram of an example of the terminal device . The terminal device includes a plurality of applications an OS and an API Application Programming Interface .

The plurality of applications include an application for passing files and an application for receiving files. The OS provides a file passing function for passing files between the applications . An example of the OS for providing a file passing function is an iOS registered trademark . The iOS provides an Open In function as a mechanism for passing files between different applications .

The OS includes a file passing function unit and an application information storage unit . As described below the file passing function unit passes a file specified by the application of the file passing side to the application of the file receiving side. The application information storage unit stores application information needed for the file passing function. In the application information the type of file that is processable by each application is specified.

The API is an interface for the application to use functions of the OS such as the file passing function unit . The API is a pre defined interface that is provided for the OS to receive requests from the application and is constituted by functions classes etc.

The render processing unit is a module for performing a process of rendering files etc. The operation processing unit is a module for determining an operation that the user has made with respect to the input device and performing a process according to the operation. The communication processing unit is a module for performing communication processes with other terminal devices . The communication processing unit is not essential and may be omitted in the case of an application that does not need to perform communication processes with other terminal devices .

The file format conversion processing unit is a module for performing a conversion process on the format type of the file. The file format conversion processing unit implements a restriction on the application of the file receiving side to which the file is passed as described below by converting the format of a file into a unique format that is not generally used.

The file pass processing unit is a module for performing a process of passing files to other applications such as the application . The file pass processing unit uses the API to call the file passing function unit of the OS and performs a process of passing files to other applications such as the application

The database DB stores various types of information used by the application of the file passing side. The control unit is a module that manages the processes of the render processing unit the operation processing unit the file pass processing unit the file format conversion processing unit and the communication processing unit .

The render processing unit is a module for performing a process of rendering files etc. The operation processing unit is a module for determining an operation that the user has made with respect to the input device and performing a process according to the operation. The communication processing unit is a module for performing communication processes with other terminal devices . The communication processing unit is not essential and may be omitted in the case of an application that does not need to perform communication processes with other terminal devices .

The file format conversion processing unit is a module for performing a conversion process on the format type of the file. The file format conversion processing unit converts the file that has been converted into a unique format at the application of the file passing side back to the original file format such that the file can be handled by the application of the file receiving side.

The file copy processing unit is a module for performing a process of copying files. The access authentication processing unit is a module for performing an authentication process for accessing the copy destination of the file. Note that the file copy processing unit expresses an example of a module for performing a process on a file. Furthermore the access authentication processing unit is not essential and may be omitted in the case of an application that does not require an authentication process.

For example in the application information of as the extensions of files processable by the application names application A and application C doc jpg and pdf are specified as examples of typical extensions. Furthermore in the application information of as the extension of files processable by the application name application B ric abc is specified which is an example of a unique extension determined in advance.

When the file passing function unit receives a specification of a file from the application of the file passing side by using the application information of the file passing function unit can create a list of applications of the file receiving side that can process the specified file.

For example as the extension of the file processable by the application name application B in a unique extension that is determined in advance for example ric abc is specified. Therefore when the file passing function unit receives a specification of a file having a unique extension for example ric abc from the application of the file passing side the file passing function unit creates a list of application names associated with the unique extension in the application information of .

Therefore in the terminal device of by converting the format of the file into a unique format at the application of the file passing side it is possible to restrict the application names displayed in the list to those intended by the user.

In the following a description is given of details of processes by the terminal device according to the present embodiment. The application of the terminal device passes files to the application by using the file passing function of the OS .

Here as one example a description is given of a process of passing a file which has been used at the application of the terminal device to the application by the file passing function of the OS and storing the file in a predetermined folder at the application

When a user operating the terminal device wants to pass a file which has been used at the application to the application the user presses taps for example a file transfer button that is displayed on a screen by the render processing unit of the application . When the file transfer button is pressed the control unit of the application starts a file passing function illustrated in . is a flowchart of an example of a file passing process.

In step S the control unit specifies a file to be a target of the file passing process and requests the file format conversion processing unit to perform a process of converting the file format. The file format conversion processing unit converts the extension for example pdf of a target file in the storage area of the HDD assigned to the application to a unique extension for example ric abc that is determined in advance.

In step S the control unit sends a request for a file passing process to the file pass processing unit . The file pass processing unit sends the request for the file passing process to the file passing function unit of the OS by passing to the API of the file passing function the path character string of the target file whose extension has been converted into a unique extension.

The file passing function unit of the OS which has received the request to perform the file passing process starts a target application icon display process as illustrated in . is a flowchart of an example of a target application icon display process.

In step S the file passing function unit acquires a unique extension determined in advance for example ric abc as extension information from the path character string of the target file of the file passing process.

In step S the file passing function unit lists the applications that are associated with the unique extension determined in advance in the application information of which is acquired as extension information from the path character string of the target file of the file passing process.

In step S the file passing function unit displays on a screen the icons of the applications that have been listed as applications that can process the target file of the file passing process.

Note that in step S when the file passing function unit has acquired a generally used extension for example pdf icons of applications that have been listed are displayed as illustrated in .

As described above in the terminal device according to the present embodiment the file passing side converts the extension of a file into a unique extension and the unique extension is declared as the extension of the file that can be processed by the file receiving side such that the icons displayed in the list can be restricted to those intended by the user.

Therefore even in a case where a generally used type of file is passed to the application of the file receiving side the terminal device according to the present embodiment is able to restrict the icons displayed in the list to those intended by the user. As a result it is possible for the terminal device according to the present embodiment to prevent the user from erroneously selecting an icon that is not intended by the user.

The user operating the terminal device can select the application of the file receiving side to which the target file is to be passed by pressing the icon displayed in for example the screen image of . For example when the icon displayed in the screen image of is pressed the file passing function unit of the OS starts a file receiving process as illustrated in .

In step S the file format conversion processing unit of the application converts the extension of the target file that has been copied into the storage area for the application from the unique extension to the original extension determined in advance for example pdf .

In step S the render processing unit of the application performs a process of rendering contents of the file. Furthermore in step S the file copy processing unit of the application performs a process of copying the target file such as copying the target file into a remote folder.

Note that in step S it is possible to confirm with the user whether to execute the process of step S on the file whose contents are displayed or the process of step S may be executed without confirming with the user.

According to the terminal device according to the present embodiment it is possible to pass a target file of a generally used type from the application of the file passing side to an intended specific application of the file receiving side.

In the first embodiment it is assumed that the application of the file receiving side knows in advance of the original extension of the target file converted into a unique extension by the application of the file passing side. However in the second embodiment the application of the file receiving side is able to convert the unique extension to the original extension even when the application does not know in advance of the original extension of the target file converted into a unique extension by the application of the file passing side.

Note that the hardware configuration and the software configuration of the second embodiment are the same as those of the first embodiment and therefore descriptions thereof are omitted.

In the following a description is given of details of processes by the terminal device according to the present embodiment. The application of the terminal device passes files to the application by using the file passing function of the OS .

Here as one example a description is given of a process of passing a file which has been used at the application of the terminal device to the application by the file passing function of the OS and storing the file in a predetermined folder at the application

When a user operating the terminal device wants to pass a file which has been used at the application to the application the user presses taps for example a file transfer button that is displayed on a screen by the render processing unit of the application . When the file transfer button is pressed the control unit of the application starts a file passing function illustrated in . is a flowchart of another example of a file passing process.

In step S the control unit specifies a file to be a target of the file passing process and requests the file format conversion processing unit to perform a process of converting the file format. The file format conversion processing unit converts an arbitrary extension for example XYZ of a target file in the storage area of the HDD assigned to the application to a unique extension for example ric abc that is determined in advance.

In step S the control unit sends a request for a file passing process to the file pass processing unit . The file pass processing unit sends a request for the file passing process to the file passing function unit of the OS by passing to the API of the file passing function the path character string of the target file whose extension has been converted into a unique extension and the original extension character string for example XYZ .

The target application icon display process performed by the file passing function unit of the OS which has received the request to perform the file passing process is the same as that of the first embodiment and therefore descriptions thereof are omitted.

The user operating the terminal device can select the application of the file receiving side to which the target file is to be passed by pressing the icon displayed in for example the screen image of . For example when the icon displayed in the screen image of is pressed the file passing function unit of the OS starts a file receiving process as illustrated in .

In step S the file format conversion processing unit of the application reads the original extension character string from the specific address in the memory space of the application

In step S the file format conversion processing unit of the application converts the extension of the target file that has been copied into the storage area for the application into the original extension for example XYZ read in step S.

In step S the render processing unit of the application performs a process of rendering contents of the file. Furthermore in step S the file copy processing unit of the application performs a process of copying the target file such as copying the target file into a remote folder.

According to the terminal device according to the present embodiment it is possible to convert the unique extension to the original extension at the application of the file receiving side even when the application does not know in advance the original extension of the target file whose extension has been converted into a unique extension by the application of the file passing side.

According to the terminal device according to the present embodiment it is possible to pass a target file of a generally used type from the application of the file passing side to an intended specific application of the file receiving side.

In the third embodiment a function for improving security is added to the first and second embodiments. Note that the hardware configuration of the third embodiment is the same as those of the first and second embodiments and therefore descriptions thereof are omitted.

The terminal device according to the present embodiment is different from that of the first and second embodiments in terms of the configurations of the application of the file passing side and the application of the file receiving side.

The terminal device is realized by for example the functional blocks as illustrated in . The application of the file passing side has a configuration as illustrated in . is a functional block diagram of an example of the application of the file passing side.

The application of the file passing side has a file encode processing unit added to the configuration illustrated in . The file encode processing unit is a module for performing a process of encoding binary data of the target file into another format determined in advance for example Base64 and zip .

In the following a description is given of details of processes by the terminal device according to the present embodiment. The application of the terminal device passes files to the application by using the file passing function of the OS .

Here as one example a description is given of a process of passing a file which has been used at the application of the terminal device to the application by the file passing function of the OS and storing the file in a predetermined folder at the application

When a user operating the terminal device wants to pass a file which has been used at the application to the application the user presses taps for example a file transfer button that is displayed on a screen by the render processing unit of the application . When the file transfer button is pressed the control unit of the application starts a file passing function illustrated in . is a flowchart of another example of a file passing process.

In step S the control unit specifies a file to be a target of the file passing process and requests the file format conversion processing unit to perform a process of converting the file format. The file format conversion processing unit converts an extension for example pdf of a target file in the storage area of the HDD assigned to the application to a unique extension for example ric abc that is determined in advance.

In step S the control unit requests the file encode processing unit to perform a process of encoding the target file whose extension has been converted into a unique extension at step S. The file encode processing unit converts the binary data of the target file into a format determined in advance for example Base64 .

In step S the control unit sends a request for a file passing process to the file pass processing unit . The file pass processing unit sends a request for the file passing process to the file passing function unit of the OS by passing to the API of the file passing function the path character string of the target file whose extension has been converted into a unique extension and whose binary data has been encoded into a format determined in advance.

The target application icon display process performed by the file passing function unit of the OS which has received the request to perform the file passing process is the same as that of the first embodiment and therefore descriptions thereof are omitted.

The user operating the terminal device can select the application of the file receiving side to which the target file is to be passed by pressing the icon displayed in for example the screen image of . For example when the icon displayed in the screen image of is pressed the file passing function unit of the OS starts a file receiving process as indicated in .

In step S the file format conversion processing unit of the application converts the extension of the target file that has been copied into the storage area for the application from the unique extension to the original extension determined in advance for example pdf .

In step S the file decode processing unit of the application decodes the binary data of the target file from the format determined in advance for example Base64 .

In step S the render processing unit of the application performs a process of rendering contents of the file. Furthermore in step S the file copy processing unit of the application performs a process of copying the target file such as copying the target file into a remote folder.

Note that in the third embodiment a description is given of an example of improving the security of the first embodiment as details of the process however the same applies to the case of improving the security of the second embodiment.

According to the terminal device according to the present embodiment the target file cannot be normally handled or displayed unless the file has been decoded at the application of the file receiving side and therefore security is improved.

According to the terminal device according to the present embodiment the security is improved in a case of passing a target file of a generally used type from the application of the file passing side to a specific intended application of the file receiving side.

The terminal device according to the first through third embodiments can be applied to for example various systems as illustrated in .

It is assumed that in each of the terminal devices a data sharing application which is an example of the application of the file passing side and a file server access application which is an example of the application of the file receiving side are activated.

For example it is assumed that one of the users operating the terminal device user A has a file which is to be shared with other users users B and C registered in advance in the data sharing application of the terminal device of itself. The data sharing application of the terminal device of the user A displays the registered files.

The users B and C access the terminal device of the user A via the data sharing application of the respective terminal devices of themselves and download the file to be shared from the terminal device of the user A to the terminal devices of themselves. Then the data sharing applications in the terminal devices of the users B and C display the downloaded files.

There may be cases where the users A B and C want to send the displayed file from the terminal devices of themselves to the file server device to be stored in the file server device . In this case the users A B and C need to pass the displayed file from the data sharing application to the file server access application. The contents of the first through third embodiments may be applied to the process performed by the terminal device of passing the displayed file from the data sharing application to the file server access application.

It is assumed that in each of the terminal devices a data sharing application which is an example of the application of the file passing side and a file server access application which is an example of the application of the file receiving side are activated.

There may be cases where the user wants to send the displayed file from the terminal device of itself to a remote folder in the PC to be stored in the remote folder in the PC . In this case the user needs to pass the displayed file from the data sharing application to the file server access application. The contents of the first through third embodiments may be applied to the process performed by the terminal device of passing the displayed file from the data sharing application to the file server access application.

The conference registration PC has a function of registering in the conference server device conference information in which various types of information relevant to the conference are set and files conference materials to be shared in the conference. The user is able to register the conference information and files from the conference registration PC in the conference server device .

The conference server device manages the conference information and files. Furthermore the conference server device has a function of holding a conference controlling the attendance in the conference and distributing the input operations by the presenter to the terminal devices attending the conference in a real time manner.

It is assumed that in each of the terminal devices a data sharing application which is an example of the application of the file passing side and a file server access application which is an example of the application of the file receiving side are activated.

The user attending the conference uses the conference application of the terminal device of itself to download the file to be shared in the conference from the conference server device and to display the file. There may be cases where the user attending the conference wants to send the displayed file from the terminal device of itself to the file server device to be stored in the file server device .

In this case the user needs to pass the displayed file from the conference application to the file server access application and the file needs to be stored in the file server device by transferring the file from the server access application. The contents of the first through third embodiments may be applied to the process performed by the terminal device of passing the displayed file from the conference application to the file server access application.

The terminal device and the data passing method are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention.

For example as examples of systems to which the contents of the first through third embodiments may be applied the data sharing system the data storing system and the conference system are indicated however the contents of the first through third embodiments may be applied to various systems for passing files between applications.

For example the application of the file passing side is an example of a first program. The application of the file receiving side is an example of a second program. The file passing function unit is an example of a data passing unit.

Note that the above configuration of the terminal device is one example and it is needless to say that various configuration examples are applicable according to the applications and purposes.

According to an embodiment of the present invention it is possible to restrict the passing of data between programs regardless of the type of the data.

The present invention can be implemented in any convenient form for example using dedicated hardware or a mixture of dedicated hardware and software. The present invention may be implemented as computer software implemented by one or more networked processing apparatuses. The network can comprise any conventional terrestrial or wireless communications network such as the Internet. The processing apparatuses can compromise any suitably programmed apparatuses such as a general purpose computer personal digital assistant mobile telephone such as a WAP or 3G compliant phone and so on. Since the present invention can be implemented as software each and every aspect of the present invention thus encompasses computer software implementable on a programmable device. The computer software can be provided to the programmable device using any storage medium for storing processor readable code such as a floppy disk hard disk CD ROM magnetic tape device or solid state memory device.

The hardware platform includes any desired kind of hardware resources including for example a central processing unit CPU a random access memory RAM and a hard disk drive HDD . The CPU may be implemented by any desired kind of any desired number of processor. The RAM may be implemented by any desired kind of volatile or non volatile memory. The HDD may be implemented by any desired kind of non volatile memory capable of storing a large amount of data. The hardware resources may additionally include an input device an output device or a network device depending on the type of the apparatus. Alternatively the HDD may be provided outside of the apparatus as long as the HDD is accessible. In this example the CPU such as a cache memory of the CPU and the RAM may function as a physical memory or a primary memory of the apparatus while the HDD may function as a secondary memory of the apparatus.

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2014 032497 filed on Feb. 24 2014 the entire contents of which are hereby incorporated herein by reference.


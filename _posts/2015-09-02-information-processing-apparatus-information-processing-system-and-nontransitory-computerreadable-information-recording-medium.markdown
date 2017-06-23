---

title: Information processing apparatus, information processing system and non-transitory computer-readable information recording medium
abstract: An information processing apparatus includes a print data generation part that receives, via an operating system, a print execution instruction including a file and a first print setting from the application, and generates print data; an application management part that sends a printing instruction to the application; an extended interface part other than an interface part defined by the operating system; and a print setting storing part that stores a second print setting that is input from the application management part via the extended interface part. The print data generation part changes a print setting to be used to generate the print data from the first print setting to the second print setting.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09442678&OS=09442678&RS=09442678
owner: RICOH COMPANY, LTD.
number: 09442678
owner_city: Tokyo
owner_country: JP
publication_date: 20150902
---
The present invention relates to an information processing apparatus an information processing system and a non transitory computer readable information recording medium.

As a result of the DEVMODE structure being thus sent to the printer driver from the application the application can output a rendering instruction to the GDI while understanding the capability of the printer such as the area to render and so forth. This is because as shown in the printer driver returns the rendering capability the information concerning the capability with which rendering can be carried out to the GDI based on the DEVMODE structure that the printer drive receives when receiving the print execution instruction and the information of the printer that is the printing device to which the printer driver itself is connected.

According to one embodiment of the present invention an information processing apparatus includes a print data generation part that receives via an operating system a print execution instruction including a file and a first print setting from the application and generates print data an application management part that sends a printing instruction to the application an extended interface part other than an interface part defined by the operating system and a print setting storing part that stores a second print setting that is input from the application management part via the extended interface part. The print data generation part changes a print setting to be used to generate the print data from the first print setting to the second print setting.

Other objects features and advantages of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings.

The embodiments relate to information processing apparatuses information processing systems and non transitory computer readable recording media. More specifically the embodiments relate to information processing apparatuses information processing systems and non transitory computer readable recording media with each of which it is possible to change print settings in an application without modifying the application or inputting instructions to a print setting screen page.

Note that according to the configuration of the Windows print architecture shown in the application can send the DEVMODE structure to the printer driver only when outputting the print execution instruction. Also another application another process or another thread even in the same application same process cannot access the print settings used by the application in the printing.

Further the printer driver can display a print setting screen page also called a printing dialog in a printer folder and determine the default print settings the DEVMODE structure as a system default . These print settings can be acquired from the application via an Application Programming Interface API .

At this time the GDI sends a print setting instruction to the printer driver via a Device Drive Interface DDI . Concerning the DDI only an interface I F is defined. Therefore the manufacturer of the printer driver can design a way of implementing the inside of the DDI a process of the printer driver carried out when being called via the DDI . However even if the manufacturer uniquely defines the I F the Windows OS cannot know the I F and therefore the I F is not called.

The Private part is unique to each manufacturer. Therefore it is possible to define the information therein for each manufacturer or for each printer driver. An application and a Windows OS cannot know the information in the Private part. Therefore only one way to change the Private part is changing the settings in the Private part that is displayed by a User Interface UI driver of the printer driver. The Private part includes the setting items of features unique to each manufacturer or each printer type such as a printing type an authentication and or the like.

After acquiring the DEVMODE structure from the application the GDI invokes a rendering driver of the printer driver by using a DDI call and sends the DEVMODE structure print execution instruction thereto. The rendering driver reads the DEVMODE structure thus acquired from the GDI print setting instruction creates the print data reflecting the print settings based on the DEVMODE structure and the document file received from the application print execution instruction and sends the print data to a spooler. The print data includes the rendering data for example PDL data and the control data for example PJL print commands .

Thus each of the UI driver and the rendering driver can read the DEVMODE structure . The UI driver can display the Private part of the DEVMODE structure and receive a print setting change instruction.

Thus the UI driver stores the print settings in the DEVMODE structure and the rendering driver reads the print settings from the DEVMODE structure . The application sends the DEVMODE structure so that the print settings can be thus stored read. Actually the application provides a memory sends it to the UI driver via the OS and the UI driver fills it. Also when the application outputs the print execution instruction via the OS the rendering driver reads the contents of the DEVMODE structure .

Thus in order to change the Private part of the DEVMODE structure there is only a way that the printer driver displays a print setting screen page and receives the user s operation. Thus the user s operation is necessary.

However there is a process desired to be completed automatically without the need of such user s operation. For example a process of printing a spread sheet a process of transmitting a Direct Mail DM via facsimile or so is such a case. For such a process if the user is required to change the Private part of the DEVMODE structure by inputting an instruction to the print setting screen page every time printing a spread sheet or transmitting a DM even using the same print settings the controllability may be degraded.

Thus there is a demand to be able to cause the application suitable to the process to change the print settings stored in the Private part of the DEVMODE structure of the printer driver without the need of the user s operation.

In order to satisfy the demand a manufacturer proposes an extended I F of a printer driver such that an application can directly carry out communication with the printer driver for example see Japanese Laid Open Patent Application No. 2005 148928 . Also depending on the user s request an application suitable to the process is developed.

The application can invoke the extended I F part send the print settings print setting instruction and change the print settings in the Private part of the DEVMODE structure via the UI driver . The rendering driver reads the print settings in the Private part of the DEVMODE structure in response to the print execution instruction. Thus after the user inputs the print execution instruction to the application it is possible to complete the process without the need of the user s operation.

According to the Windows print architecture printing by a printer driver can use two spooling types i.e. a RAW spooling type and an EMF spooling type. According to the RAW spooling type document data acquired by the printer driver from the application is converted into RAW data interpretable by the printer converting process during a process of the application. In this type the user cannot operate the application until the converting process is finished.

According to the EMF spooling type document data acquired by the OS from the application is converted into an EMF data format independent of the printer during a process of the application and the EMF data is spooled spooler process . Then the printer driver converts the EMF data thus spooled in the spooler process into RAW data interpretable by the printer. In this type the user can operate the application after the finish of converting the document data into the EMF data in the process of the application.

Next a relationship between a type of installing a printer driver and the print settings after the start of printing will be described. Concerning the Windows printer driver an installing type called Point Print is available.

In such a system the same printer driver as that of the server PC needs to be installed in the client PC . However considerable time and labor may be required of the administrator or so to install the printer driver in each client PC connected to the communication network .

In order to improve this circumstance downloading and installing the printer driver from the server PC to the client PC is enabled according to the Point Print technology. This is enabled according to the Windows standard function. Note that also the printer driver thus installed according to the Point Print technology can use the RAW spooling type and the EMF spooling type in a printing process.

In case of the printer driver thus installed according to the Point Print technology in case of the EMF spooling type the user can change the PC which carries out rendering through the rendering driver between the client PC and the server PC . Rendering by the client PC is called client side rendering whereas rendering by the server PC is called server side rendering .

There is such a solution called IT BOX that a shared folder is monitored and printing is carried out after an added file is detected there. illustrates the IT BOX technology.

The IT BOX technology is implemented using the Windows OS. A server PC where the IT BOX technology is employed has a management application and a shared folder . The management application monitors the shared folder . When detecting that a file is added there the management application starts an application which can output a print execution instruction for the added file to the OS and thus prints the file.

In the management application detects that the client PC adds a file a in the shared folder reads the file a starts an application a which can output a print execution instruction for the file a to the OS sends the file a to the application a and outputs a printing instruction thereto. If the file a is for example a doc. file Word Viewer or MS Word is used as the application a 

As a result of the application a outputting a print execution instruction to the OS the OS outputting a print execution instruction to the printer driver and the printer driver transmitting rendering data to the printer the printer prints the file.

In each of almost all of Office applications this IT BOX solution is implemented using such a function that a file can be printed by giving the file with an argument to the Office application. According to the IT BOX technology it is possible that an external PC or smart device finds a file added to the shared folder and prints the file through the printer . The type of installing the printer driver in the IT BOX technology may be different depending on each particular customer environment.

The IT BOX technology can be improved in consideration of a situation where when the printer driver is used to carry out printing the print settings in the application a cannot be changed and thus the printing is carried out with the default print settings.

That is the management application is a unique application of a vendor who develops solutions. In contrast thereto the Office application which is used to print an Office document or so is an application developed by another vendor or so. As a result the Office application is not modified or cannot be modified. The management application can output an Office file and a printing instruction to the Office application only using an argument. Therefore it is not possible to change the print settings.

Therefore the user of another PC or smart device cannot print a file after it is transferred to the shared folder according to the desired print settings such as N in 1 duplex or so from the PC or the smart device.

In the above described case of the printer driver according to Japanese Laid Open Patent Application No. 2005 148928 using the extended I F part to be able to access the DEVMODE structure it is a presupposition to store all the setting items in the DEVMODE structure. Therefore the application that actually sends a print execution instruction to the printer driver needs to know the unique extended I F part of the printer driver. Therefore in case of the IT BOX solution or so where the application the management application which sends a trigger to start printing is different from the application which actually sends a print execution instruction to the printer driver it is not possible to change the print settings.

A reason why it is a presupposition to store all the setting items in the DEVMODE structure according to the printer driver disclosed by Japanese Laid Open Patent Application No. 2005 148928 will now be described. As shown in when the application changes the print settings using the extended I F part uniquely extended from the printer driver the following processes i ii and iii are required.

 ii The application receives the DEVMODE structure having the print settings therein changed as an output.

 iii The application uses the received DEVMODE structure as the DEVMODE structure to be sent to the rendering driver for starting the printing.

In other words when using the extended I F part even if the print settings other than the DEVMODE structure are stored the application cannot acquire the print settings other than the DEVMODE structure from the extended I F part . This is the reason why all the print settings need to be stored in the DEVMODE structure .

Also according to the printer driver disclosed by Japanese Laid Open Patent Application No. 2005 148928 it is necessary to modify the application into one suitable to the user s process or one that can invoke the extended I F part .

Also the printer driver disclosed by Japanese Laid Open Patent Application No. 2005 148928 may have such a problem that it cannot work in the same way not only in case of a specific spooling type or a case of being installed in a local environment but also in both the RAW spooling type and the EMF spooling type. Also when the printer driver is installed according to the Point Print technology it cannot work.

There is also a printer driver which executes such a method that the print settings are stored in a file a registry a shared memory space or so other than the DEVMODE structure. The printer driver then reads the thus stored print settings and as a result the print settings can be changed from the outside.

According to this method the above described problem is solved with regard to the point that the print settings are not stored in the DEVMODE structure. However other problems may occur due to not using the DEVMODE structure in the following two cases 1 and 2 

In the case 1 the above mentioned method depends on a DDI call sequence at a time of printing and can be implemented in case of the RAW spooling type. However if the spooling type is different the DDI call sequence of being invoked from the OS is changed. That is the EMF spooling type requires two times of converting process sequences inside the OS i.e. the process of converting print data acquired from the application into the EMF data and the process of converting the EMF data into the data interpretable by the printer.

Between these two times of converting process sequences the process of converting the print data acquired from the application into the EMF data and the process of converting the EMF data into the data interpretable by the printer are mutually different processes. Whether access is permitted or inhibited depends on the authority of each process. Therefore depending on the place of the file or the registry there is a case where the print settings that have been previously set via the extended I F part cannot be acquired from the setting storing area when the EMF data is finally converted into the data interpretable by the printer. In fact according to the recent Windows OS from the security viewpoint there is a case where access is completely impossible if the authority is different.

In the case 2 the above mentioned method can be implemented when the printer driver is installed in a PC used by the user in a local environment. However there is a case where the above mentioned method cannot be implemented when the printer driver is installed according to the Point Print technology.

That is in the driver installed according to the Point Print technology it is possible that the place where the UI driver works and the place where the rendering driver works are mutually different. For example according to client side rendering the UI driver and the rendering driver work in the client PC whereas according to server side rendering the UI driver works in the client PC while the rendering driver works in the server PC .

In server side rendering the PCs where the respective drivers and work are physically different from one another. Therefore the print settings temporarily stored in the setting storing area such as a file or a registry by the extended I F part of the printer driver cannot be acquired by the rendering driver when the EMF data is finally converted into the data interpretable by the printer.

The embodiments have been devised for the purpose of solving these possible problems and an object is to be able to change the print settings in the application without modifying the application that outputs the print execution instruction to the operating system and without the need of the user s operation of the print setting screen page.

Below the embodiments of the present invention will be described using the accompanying drawings. Note that in the drawings described now the same reference numerals are given to the same or corresponding elements as those of the drawings described above.

The printing system includes a PC a smart device and a printer each thereof being connected to a communication network . The PC corresponds to an information processing apparatus and the above described IT BOX technology is employed therein.

The PC receives the user s operation generates the print data by using a printer driver from a file created by an application such as a document creation software and transmits the print data to the printer via the communication network . Thus it is possible to print the file. The smart device can use the IT BOX technology employed in the PC via the communication network . The printer includes an image formation part of an inkjet type or an electrophotographic type and can be a multifunction peripheral.

The PC includes a CPU a ROM a RAM an external I F a communication device an input device a display control part and a storage device each thereof being mutually connected together via a bus .

The CPU reads an OS a management application an application and a printer driver from the storage device and executes various processes using the RAM as a work memory.

The ROM stores a BIOS data that is initially set a start program and so forth. The RAM is a work memory main memory temporarily storing necessary data.

The external I F is an interface to which a cable such as a USB cable a portable recording medium or so is connected loaded. The communication device is a LAN card an Ethernet registered trademark card or so and transmits packet data that is mainly the print data in the embodiments to the printer in response to an instruction from the CPU .

The input device is a user interface receiving various operation instructions of the user such as a keyboard a mouse and or the like. It is also possible that a touch panel a voice input device or so can be used as the input device .

The display control part controls rendering on the display device with the predetermined resolution number of colors and so forth based on screen page information that is sent from the application as instructions. The display device is a Flat Panel Display FPD such as a liquid crystal device an organic EL device or so.

The storage device is a nonvolatile memory such as a Hard Disk Drive HDD a flash memory or so and stores the OS the management application the application and the printer driver . Also the storage device includes a shared folder not shown in . The recording medium is for example a nonvolatile memory such as a SD card a USB memory or so.

The OS can be the Windows OS. Note that as the OS although the Windows OS is preferable it is also possible to use an OS having the equivalent functions as those of the Windows OS.

The application can be any application as long as it can create edit display manage and so forth document data and can carry out a printing process of the document data. For example any one of various applications such as a document creation software a document viewing software a document viewer a document reader or so a browser software a presentation material creation software and so forth can be used as the application . Note that the document data can include not only characters letters signs marks numerical values and so forth but also data of various image formats for example JPEG TIFF and so forth .

The management application the printer driver and the shared folder will be described later in detail.

The PC includes the management application the application the printer driver a language monitor and a communication part . Thereamong the language monitor is provided by the Windows OS as a bidirectional communication interface part software for bidirectional communication between the printer driver and the printer a printing device . Therefore the language monitor is a part of the OS in a broad sense. Although other elements such as a GDI a spooler a printer processor and so forth have been omitted from the description also they are installed in the PC together with the OS .

The management application is a program for monitoring the shared folder as a shared storage area and when detecting that a file is added to the shared folder starting the application which can carry out a printing process of the added file i.e. sending the print execution instruction to the OS and so forth giving the added file to the started application and causing the application to carry out the printing process. The management application functions both as an application management part unit and as a monitoring part unit .

The printer driver includes a UI driver an extended I F part and a rendering driver . The UI driver has a display part . The display part of the UI driver displays a print setting screen page on the display device as a result of the user inputting a printing operation to the application .

The user is then allowed to input the print settings from the print setting screen page such as the number of sheets of printing duplex N in 1 book binding change in size or zoom in out and or the like. Even after the user inputs a printing start instruction the display part can receive a change in the print settings while displaying the print setting screen page on the display device . The print settings are stored in a structure a data table called the DEVMODE structure. The DEVMODE structure is a data structure where member variables are defined for setting various printing conditions in common for various printer drivers that operate under the control of the Windows OS. The DEVMODE structure is sent to the printer driver via the GDI that is an interface part defined by the OS .

The extended I F part is an interface unique to the printer driver enabling direct reception of the print settings without using the DEVMODE structure. In other words the extended I F part is an extended interface other than interface parts defined by the OS . The extended I F part receives the print settings of the application from the management application . The language monitor as a print setting storing part unit stores the print settings.

The rendering driver as a print data generation part unit reads the print setting stored by the DEVMODE structure and the print settings stored by the language monitor and creates the print data based on a document file concerning the print execution instruction sent from the application the print data reflecting the print settings. At this time if the language monitor stores the print settings these print setting are used. If the language monitor stores no print settings the print settings stored by the DEVMODE structure are used. Thus the print settings stored by the language monitor are preferentially used.

The language monitor has a data storage part and a communication part . Thereamong the communication part carries out communication control as the Windows print architecture when the printer driver transmits the print data to the communication part . The communication part is included in a language monitor of the related art as a bidirectional communication interface that is a standard part for the Windows OS. The communication part can receive also a message from the printer via the communication part .

In contrast thereto the data storage part is unique to the embodiments and stores the print settings that are input from the extended I F part . The data storage part is implemented by the printer driver using a function of a language monitor of the prior art. Therefore it is not necessary to modify the Windows OS or it may be necessary to only slightly modify the Windows OS if any. The data storage part will be described later in detail.

The communication part carries out communication with the smart device and the printer connected to the communication network and executes a communication process according to a protocol such as TCP IP.

Note that in the extended I F part is separate from the UI driver . However the UI driver can include the extended I F part .

As a result of the management application using the extended I F part of the printer driver it is possible to send the print settings of the application to the printer driver . Only as a result of being started by the management application and receiving the document file to be printed the application can output the print execution instruction together with the document file and the print settings to the OS . Even if the application sends the default print settings first print setting to the OS it is possible to implement the printing reflecting the intention of the user of the smart device as a result of the rendering driver reading the print settings second print setting sent by the management application via the extended I F part .

The management application outputs a setting instruction including the print settings to the extended I F part of the printer driver and the extended I F part stores the print settings in the language monitor . The print settings which the management application thus sets in the extended I F part can be those acquired from any device as long as they can be known by the management application such as the print settings that are set by an external device for example the smart device to the management application the print settings stored at a specific path the fixed values or so.

The management application selects the application for each document file to be printed starts the selected application sends the document file thereto and sends a printing instruction thereto. In the example of the management application outputs printing instructions to the application a and the application b . The document files to be printed are for example designated by the user from the smart device not shown in .

The application a and the application b then output print execution instructions with the default print settings first print setting as they are to the OS . The OS then outputs the print execution instructions to the rendering driver .

The rendering driver receives the print execution instructions together the default print settings DEVMODE first print setting . Next the rendering driver queries the language monitor whether the language monitor stores the print settings second print setting that are set by the extended I F part . If the language monitor stores the print settings second print setting the rendering driver acquires the print settings second print setting . If the rendering driver thus acquires the print settings second print setting from the language monitor the rendering driver generates the print data reflecting the print settings second print setting and transmits the print data to the printer . If the rendering driver acquires no print settings from the language monitor the rendering driver generates the print data reflecting the default print settings first print setting stored by the DEVMODE structure and transmits the print data to the printer .

A plurality of logical printers can be registered in a single PC. Logical printers mean those displayed as icons of printers in a printer folder of the Windows OS. The Windows OS can create a plurality of logical printers for a single printer driver. The logical printers can be said as virtual output destinations of an application. The print data acquired through a rendering operation of a printer driver is output to a logical printer designated by the user and is provided by the Windows OS from the logical printer to a physical printer.

For each logical printer a single name can be given. The user or so can freely give the name the name can be automatically given as a package name of the printer driver or so. For each logical printer it is possible to set a function whether it is shared a spooling type options and so forth. That is it is possible to change the initial settings of the single physical printer.

When a plurality of logical printers are registered in a single PC it is possible to improve the convenience of the user if the print settings can be changed for each of the logical printers. For this purpose it is preferable that the print settings can be stored for each of the logical printers. In this case the extended I F part registers the print settings in the language monitor by using logical printer names as keys. In other words the print settings are registered in association with logical printer names .

The logical printer names are IDs of the logical printers designated as output destinations by the user. Thus the UI driver and the rendering driver can know the logical printer names to refer to. Therefore it is possible to acquire the corresponding print setting by querying the language monitor by the logical printer name. Similarly also the extended I F part works according to the designation of the logical printer name. Therefore the extended I F part can store the corresponding setting data in the language monitor by using the logical printer name.

The smart device and the PC as other information processing apparatuses can access the shared folder that is in the PC . The PC transfers document files to the shared folder . The smart device reads the document files stored in the shared folder selects one of the document files to be printed and outputs the corresponding printing instruction to the management application while designating the selected document file. At this time the smart device can set the print settings.

Note that in the PC transfers the file a and the smart device selects the file a . However the smart device can also select other files the file b and the file c . Also the PC can select the file to be printed.

After receiving the print settings second print setting print setting instruction from the smart device the management application stores them in the language monitor via the extended I F part . Then the management application reads the file a designated with the printing instruction from the shared folder starts the application a which can carry out a printing process of the file a and outputs the printing instruction thereto.

The application a outputs the corresponding print execution instruction to the OS together with the default print settings first print setting as they are. The OS outputs the corresponding print execution instruction to the rendering driver . The rendering driver receives the default print settings DEVMODE first print setting together with the print execution instruction. Next the rendering driver acquires the print settings second print setting from the language monitor . Then the rendering driver creates the print data reflecting the print settings second print setting and transmits the print data to the printer .

Thus after designating the file from the shared folder to the management application by using the smart device or the PC setting the print settings second print setting and outputting the printing instruction it is possible to change the print settings to be actually used from the default print settings first print setting of the application which can carry out a printing process of the designated file to the print settings second print setting .

The PC or the smart device sends according to the user s operation thereof a print setting instruction together with the print settings to the management application of the PC step S . The management application includes a setting change part and receives the print settings second print setting after displaying a setting screen page in response to a request from the PC or the smart device .

The management application sends a request to store the print settings received from the PC or the smart device to the extended I F part of the printer driver step S . The extended I F part verifies determines the validity of the print settings step S and stores the print settings in the language monitor step S .

At this time the extended I F part uses an API of the Windows OS i.e. SendRecvBidiDataFromPort . The SendRecvBidiDataFromPort function is an API implemented in the language monitor . As same as the printer driver also the language monitor has I Fs determined by the Windows OS. The SendRecvBidiDataFromPort function is one thereof and supports bidirectional communication between an application and a printer and between an application and a print server.

Next the PC or the smart device designates according to the user s operation thereof a document file and sends the corresponding printing instruction to the management application of the PC step S . The management application starts the application that can carry out a printing process of the designated document file step S and outputs the corresponding printing instruction thereto step S .

The application sends the corresponding print execution instruction and the DEVMODE structure storing the default print settings first print setting to the GDI of the OS step S . Specifically the application calls the GDI with a CreateDC function having the default print settings as the argument.

The GDI sends the DEVMODE structure storing the default print settings first print setting to the rendering driver step S . Specifically the print settings the DEVMODE structure thus sent as the argument of CreateDC by the application to the GDI is then sent to the rendering driver in such a form that they first print setting are stored as the argument of DrvEnablePDEV .

The rendering driver needs to return the rendering capability in response to this printing start preparation instruction DrvEnablePDEV . Therefore the rendering driver acquires the print settings that second print setting are set by the extended I F part from the language monitor step S . Specifically a value indicating a query is set in the argument of SendRecvBidiDataFromPort which is then sent to the language monitor . If the language monitor has the print settings second print setting that are set by the extended I F part the language monitor sets them in SendRecvBidiDataFromPort and returns them second print setting to the rendering driver .

Next the rendering driver merges the print settings second print setting thus acquired from the language monitor with the print settings first print setting received together with the printing start preparation instruction and returns the rendering capability to the GDI .

The application queries the GDI about the rendering capability step S GetDeviceCaps . Next the application sends an instruction to start printing to the GDI step S . Specifically the application calls the GDI with a StartDoc function having DocINFO or so as the argument. The GDI sends a printing start instruction to the rendering driver step S . Specifically the GDI sends a DrvStartDoc function to the rendering driver .

After receiving the printing start instruction DrvStartDoc from the GDI the rendering driver acquires from the language monitor the print settings second print setting to be reflected in the printer driver N in 1 color balance and or the like and or the print settings second print setting to be reflected in the printer body duplex stapling and or the like step S . Note that in an actual printing process the validity of the final settings is verified thereafter.

The rendering driver generates the print data PJL and PDL based on the print settings second print setting acquired from the language monitor and transmits the print data to the printer .

In the server PC a printer driver is installed. The server PC copies the printer driver and distributes the thus acquired copies to the client PCs to respectively. Thus without the need of the user s operation the server PC and the client PCs to can cooperatively install the printer drivers . Note that hereinafter it is assumed that the client PC is connected to the server PC and the client PC installs the printer driver according to the Point Print technology. In this case the client PC and the server PC constitute an information processing system.

In server side rendering in the Point Print environment the client PC receives the print settings that are input by the user whereas the server PC carries out the rendering. Therefore it may be difficult to share the print settings and so forth therebetween.

However the above described language monitor is a function inside the Windows OS. Therefore the Windows OS of the client PC where the printer driver is installed according to the Point Print technology can transmit the print settings to the server PC . Thus the server PC can acquire the print settings from the client PC through a process inside the print architecture.

As described above the language monitor is one module incorporated into the print architecture of the Windows OS. Therefore even if the client PC plays a roll of processes of the UI driver and the extended I F part while the server PC plays a roll of a process of the rendering driver in the Point Print environment the single language monitor works only in the server PC . Although also the client PC has the language monitor the language monitor in the client PC does not work in this case.

The printer driver in the client PC and the printer driver in the server PC access the single the language monitor . The OS in the client PC and the OS in the server PC establish communication between the client PC and the server PC for example by using Remote Procedure Call RPC . Then in a case where the UI driver is to access the language monitor of the client PC the language monitor in the client PC does not work and the spooler transmits the print settings to the language monitor of the server PC .

Thus because the client PC and the server PC install the same Windows OSs the client PC and the server PC can use the language monitor of the print architecture of the Windows OS in a sharing manner. Therefore access disablement communication error or so which is likely to occur due to a difference in access authority in a module originally developed by a manufacturer is not likely to occur. In the same reason the affinity with the Windows OS is high in this configuration.

The first example described above using relates to the method of changing the print settings for each job and carrying out the printing. Therefore for example a case where the management application prints files from the shared folder collectively at a specific time is not considered. A second example that will now be described relates to a method of even in such a case changing the print settings for each specific unit for each specific job application user or so and carrying out the printing.

A setting change part receives a print setting change request from an external device in this example the smart device and provides an interface for changing the print settings for example a print setting change UI of . When providing the interface for changing the print settings the setting change part receives the printing area of the printer driver from the UI driver shows information concerning the settable items based on the acquired printing area of the printer driver and receives a setting change instruction the print settings through the interface via the smart device . After thus receiving the setting change instruction the print settings through the interface the setting change part generates a print setting file based on the print settings that are thus set and stores the print setting file in the shared folder .

Note that in the print setting file the print settings that are thus set can be stored for each job for each application for each user and or the like. As a result by designating a specific application for example it is possible to acquire extract the corresponding print settings from the print setting file .

Then after receiving a print setting instruction from an external device the smart device or the PC the management application reads the print setting file from the shared folder acquires the corresponding print settings from the print setting file based on the information written in the print setting file and sets the thus acquired print settings by using the extended I F part . Then after receiving a printing instruction from the external device it is also possible that the printing instruction is generated automatically at a designated time in a way of time designated printing or so the management application starts an application for printing that can carry out a printing process of the designated file in this example the application a and sends a printing instruction to the application a 

When the user selects for each application from among the respective options of for each application for each job for each user and so forth in the selection input frame on a print setting screen page the print setting change UI shown in and inputs AdobeReader as the application name in the application name input frame the print setting AdobeReader is stored. Note that although the print setting change UI such as the print setting screen page of the printer driver has been thus illustrated the configuration of the print setting change UI is not limited thereto.

First the PC or the smart device sends a print setting change request step S according to the user s operation thereof . The setting change part acquires the capability of the printer driver from the UI driver step S starts print setting change UI and provides it to the PC or the smart device step S .

The PC or the smart device designates according to the user s operation thereof through the print setting change UI displayed thereon the application to set application for printing and thus changes the print settings step S . The setting change part stores the thus changed print settings in a form of the print setting file in the shared folder step S .

As mentioned above in the print setting file the print settings that are thus set can be stored for each application. As a result by designating a specific application application for printing it is possible to acquire extract the corresponding print settings from the print setting file .

Next the PC or the smart device sends to the management application a printing instruction step S . The management application acquires from the shared folder the print setting file step S and from the print setting file determines extracts therefrom the printing settings corresponding to the application for printing step S .

Note that because the printing instruction of step S includes the designation of the document file to be printed the management application can determine the application for printing therefrom. For example if the document file to be printed is a PDF file the management application can determine the application for printing as AdobeReader accordingly and determine extract the corresponding print settings from the print setting file in step S.

Next the management application sends to the extended I F part a request to store the printing settings of the application for the printing step S . The extended I F part verifies determines the validity of the print settings step S and stores them in the language monitor step S . Steps S S S S S S S S and S thereafter are the same as S S S S S S S S and S of the first example respectively and duplicate explanations thereof will be omitted.

Note that according to a sequence for a case where the print settings are changed for each user the PC or the smart device designates a user to set through the print setting change UI in step S in the same way and adds the corresponding user ID to the printing instruction in step S. Then the management application determines extracts the thus designated user s print settings according to the user ID in the same way in step S.

In this example it is assumed that a first printer driver supporting a function No. and a function No. and a second printer driver supporting the function No. and a function No. are provided.

A first rendering driver and a second rendering driver are included in respective packages of the first printer driver and the second printer driver. The packages of the first printer driver and the second printer driver include also extended I F parts respectively. However these extended I F parts are modules having the same names of the same versions or updated versions. Therefore after these two printer drivers are installed these extended I F parts are overwritten by the extended I F parts of the new versions and thus the only single extended I F part is present. The single extended I F part stores in a first the language monitor and a second the language monitor the corresponding sets of the print settings to be used respectively when the first printer driver and the second printer driver work. The first rendering driver and the second rendering driver acquire the respective sets of the print settings from the first the language monitor and the second the language monitor

First the PC or the smart device sends according to the user s operation thereof a print setting change request to the setting change part of the PC step S . The setting change part provides a printer driver selection UI to the PC or the smart device and requests to select a printer driver step S .

After the PC or the smart device selects according to the user s operation thereof a printer driver printer driver for printing step S the setting change part acquires the capability of the printer driver from the UI driver of the thus selected printer driver i.e. a printer driver for printing step S . In this example it is assumed that the first printer driver is selected.

Next the setting change part provides to the PC or the smart device a print setting change UI according to the thus acquired capability of the printer driver step S . After the PC or the smart device then designates the application to set and changes the print settings through the print setting change UI according to the user s operation thereof step S the setting change part stores the changed print settings in a form of a print setting file in the shared folder step S .

Note that the setting change part also includes the information identifying the printer driver for printing selected in step S in the print setting file stored in the shared folder in step S.

Next the PC or the smart device sends to the management application a printing instruction according to the user s operation thereof step S . The management application then acquires the print setting file from the shared folder step S and determines extracts the print settings for the application for printing from the print setting file step S .

Next the management application determines the printer driver for printing from the thus acquired print setting file and sets the determined printer driver as a default printer step S . Through this procedure it is possible to carry out printing by using the printer driver that is thus set as the default printer .

Next the management application sends the printer icon name of the default printer and the print settings determined in step S to the extended I F part of the printer drivers and sends a request to store the print settings thereto step S .

The extended I F part verifies the validity of the print settings step S determines the corresponding language monitor from the printer icon name step S and stores the print settings in the determined language monitor step S .

Next the management application starts the application which can carry out a printing process of the designated document file designated in step S step S and sends a printing instruction thereto step S . The printer to be then used for the printing is the default printer . The procedure to be executed thereafter is the same as steps S S of and thus duplicate illustration and explanation thereof are omitted.

In the above described configurations the extended I F part is incorporated in the system i.e. the printer driver as a single module. Therefore in order to add or delete a function to or from the extended I F part the extended I F part itself needs to be changed and again installed. Thus certain labor is required.

In order to improve this point a function of dynamically incorporating a new function can be provided. Thereby it becomes possible to easily add a new function to or delete a function from the extended I F part . illustrates an extended I F part having such a function of dynamically incorporating a new function.

The extended I F part includes an extended I F part and first second and third extended I F parts and for addition. The first to third extended I F parts to are interfaces to be used to set functions corresponding to the above mentioned functions No. No. and No. for example. The first to third extended I F parts to are separate modules that are added each time when the corresponding functions are added respectively.

Specific examples of functions that can be thus set or added by using the interfaces namely the first to third extended I F parts to and or the like will now be described. Bookbinding stapling sorting N in 1 change in printing sheet size and so forth can be cited as setting items . In addition to these setting items themselves long edge binding short edge binding and so forth concerning the setting item bookbinding top left top right and so forth concerning the setting item stapling return postcard and so forth concerning the setting item change in printing sheet size can be cited as setting values .

By thus configuring the first to third extended I F parts to and or the like the third extended I F part for example can be appropriately used for a new function for example sorting merely as a result of the corresponding extended I F part for example an interface for displaying a dialog or so for a user to input a setting value concerning the setting item sorting being added without the need of newly creating the extended I F part again even when the new function is added as a result of a new printer driver being added for example.

The extended I F part functions as a window for a module such as the management application which requests actually to set the print settings through the extended I F part . In other words in this case the module which requests to set the print settings is to request to set the print settings usually through the extended I F part .

The extended I F part invokes any one of the first to third extended I F parts to according to a predetermined rule. The predetermined rule is for example to invoke all the extended I F parts included in a folder to read a file that shows a path to the extended I F part s to invoke and invoke the extended I F part s according to the path or so.

By previously determining the predetermined rule as to invoke the first extended I F part and the second extended I F part for the first printer driver and invoke the first extended I F part and the third extended I F part for the second printer driver the first extended I F part and the second extended I F part are invoked for the first printer driver whereas the first extended I F part and the third extended I F part are invoked for the second printer driver.

Note that as mentioned above the first rendering driver and the second rendering driver are included in the respective packages of the first printer driver and the second printer driver. Therefore above mentioned for the first printer driver can also mean for the first rendering driver and for the second printer driver can also mean for the second rendering driver

Note that all of the extended I F part and the first to third extended I F parts to have the same interfaces functions . The interface is for example as follows 

This example is an interface for setting the printer icon name in the first argument and a printer setting list in the second argument. Each of the first to third extended I F part to invoked according to the above mentioned rule extracts the print settings relevant to itself from the print setting list that is set in the second argument verifies the validity of the extracted print settings and stores the print settings in the language monitor.

Thus in this example the extended I F part functioning as the window for the module which requests to set the print settings and the extended I F parts to to be used to add the new functions have the same interfaces as mentioned above. Thereby it is possible to add a new function A only by creating the corresponding extended I F part A and placing the extended I F part A at a position according to the rule which is used to invoke the extended I F part A through the extended I F part .

It is also possible to implement adding the extended I F part A for a new function A in such a manner as to provide a UI therefor and the user performs an operation or inputs an instruction to the UI.

According to the embodiments described above generally it is possible to change the print settings of the application that outputs the print execution instruction to the operating system without modifying the application and without the need of the user s operation of the print setting screen page.

Furthermore as described above the embodiments provide at least the following advantageous effects 1 to 6 

 1 The printer driver has in addition to the DDI defined by the OS the unique extended I F part . It is possible to receive a request to change the print settings through the extended I F part . Therefore it is possible to change the default print settings of the application into the print settings that the user desires without modifying the application that carries out the printing process and without performing operation or inputting an instruction to the print setting screen page.

 2 The rendering driver can generate the rendering capability information to be returned to the GDI based on the print settings that are input by the user received by the extended I F part and stored in the language monitor . Therefore the application carrying out the printing process can output a rendering instruction using the maximum available rendering capability based on the print settings that are input by the user and the capability information of the printer .

 3 The print settings that are input by the user and received by the extended I F part are stored in the language monitor that is a module incorporated into the print architecture of the Windows OS. As a result it is possible to implement the printing process in any one of the RAW spooling type and the EMF spooling type according to the print settings that are input by the user and received by the extended I F part .

 4 The print settings that are input by the user and received by the extended I F part are stored in the language monitor that is a module incorporated into the print architecture of the Windows OS. As a result it is possible to implement the printing process by the printer driver installed according to the Point Print technology in the print settings that are input by the user and received by the extended I F part without regard to the spooling type.

 5 The print settings to be stored in the language monitor can be changed from an external device such as the smart device or the PC for each predetermined unit job unit application unit user unit or so . Therefore by previously storing the print settings for each predetermined unit a work to change the print settings for each job is not needed.

 6 The extended I F part can have the function of dynamically incorporating a new function into the system. Therefore it is possible to easily add or delete a new function to from the extended I F part.

The information processing apparatuses the information processing systems and the non transitory computer readable information recording media storing therein the processor executable programs have been described above in the embodiments. However the present invention is not limited to such particular embodiments and variations and modifications may be made without departing from the scope of the present invention.

The present patent application is based on and claims the benefit of priority of Japanese Priority Application No. 2014 186701 filed on Sep. 12 2014 the entire contents of which are hereby incorporated herein by reference.


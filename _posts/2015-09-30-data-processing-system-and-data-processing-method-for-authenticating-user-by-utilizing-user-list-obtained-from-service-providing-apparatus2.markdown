---

title: Data processing system and data processing method for authenticating user by utilizing user list obtained from service providing apparatus
abstract: A data processing system includes a data processing apparatus providing a service to a service using apparatus and the service using apparatus that includes an authentication requesting unit that requests the data processing apparatus to authenticate the user by user specifying data input via an input screen, an obtaining unit that obtains, when the user is successfully authenticated, association data associated with the user specifying data from the data processing apparatus to store in a storage unit, and an accepting unit that displays, when the association data is stored in the storage unit, a user list of users specified from the association data in the input screen, reads out, upon a selection of a user from the user list, a part of the user specifying data from the association data corresponding to the selected user, and accepts an input of information except the read out part from the input screen.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09661184&OS=09661184&RS=09661184
owner: Ricoh Company, Ltd.
number: 09661184
owner_city: Tokyo
owner_country: JP
publication_date: 20150930
---
Recently service providing configurations have been increased in which a user only uses a necessary function only when it is necessary. For example such configurations include a software using configuration called Software as a Service SaaS in which a user arbitrarily selects only a desired function and uses the service a combination of computing resources on the INTERNET a cloud computing that provides a service with a high added value to end users or the like.

In order to provide a customized screen to a user of the above described service a method is known in which a screen is generated using specific screen definition data that is associated with client identifier see Patent Document 1 for example .

However the above described method of Patent Document 1 is not related to log in to a cloud service by a user. For example a user needs to input authentication data necessary for log in on a screen when logging in to the cloud service. Thus there has been a problem that time and efforts are necessary when inputting authentication data on a small screen such as an operation panel or the like for example.

The present invention is made in light of the above problems and provides a method of simplifying inputting data used for authentication.

According to an embodiment there is provided a data processing system including a service using apparatus and a data processing apparatus that provides a service to the service using apparatus wherein the service using apparatus includes an authentication requesting unit that requests based on a request to authenticate from a user accepted via an input screen the data processing apparatus to authenticate the user by user specifying data input via the input screen an obtaining unit that obtains when the user is successfully authenticated by the data processing apparatus association data associated with the user specifying data from the data processing apparatus to cause a storage unit stores the association data and an accepting unit that when displaying the input screen displays when the association data is stored in the storage unit a user list of users specified from the association data in the input screen reads out upon a selection of a user from the displayed user list a part of the user specifying data from the association data corresponding to the selected user and accepts an input of information except the read out part from the input screen.

Note that also arbitrary combinations of the above described elements and any changes of expressions in the present invention made among methods devices systems recording media computer programs and so forth are valid as embodiments of the present invention.

The invention will be described herein with reference to illustrative embodiments. Those skilled in the art will recognize that many alternative embodiments can be accomplished using the teachings of the present invention and that the invention is not limited to the embodiments illustrated for explanatory purposes.

It is to be noted that in the explanation of the drawings the same components are given the same reference numerals and explanations are not repeated.

The user system the application market providing system the service providing system and the service platform providing system are connected with each other via a network N such as the INTERNET or the like. The service platform providing system and the operation platform providing system are connected via a private line or the like.

The user system includes an image forming apparatus such as a multifunction peripheral or the like a user terminal a network N and the like.

The network N is a private network and a firewall FW is provided between the network N and the network N. The firewall FW detects and closes an unauthorized access. The image forming apparatus the user terminal and the like are connected to the network N. The image forming apparatus is an example of an electronic device by which a user experimentally or actually uses a service.

The user terminal may be actualized by a data processing apparatus on which a general Operating System OS or the like is mounted. The user terminal includes a wireless communication means or a wired communication means. The user terminal may be a terminal operable by a user such as a smartphone a mobile phone a tablet terminal a Personal Computer PC or the like.

The image forming apparatus is an apparatus that has an image forming function such as a multifunction peripheral or the like. The image forming apparatus includes a wireless communication means or a wired communication means. The image forming apparatus is an apparatus that performs a process regarding an image formation and on which a browser is mounted such as a multifunction peripheral a copying machine a scanner a printer a laser printer a projector an electronic whiteboard or the like for example. Although an example is illustrated in in which the user system includes one user terminal and one image forming apparatus the user system may include a plurality of them.

The application market providing system includes an application market providing server . The application market providing server is connected to the network N via a firewall FW. The application market providing server may be actualized by one or more data processing apparatuses on each of which a general OS or the like is mounted.

The application market providing system may be provided for each sales territory each sales company or the like. The application market providing server provides an application market screen such as a service list screen an applying screen or the like to the user terminal or the image forming apparatus for example.

The service providing system is connected to the network N via a firewall FW. The service providing system provides various services to the user terminal or the image forming apparatus . The service providing system may be actualized by one or more data processing apparatuses on each of which a general OS or the like is mounted.

The services provided by the service providing system may be services provided external service providers or the like in addition to services provided by an administrator of the service platform providing system . The services provided by the service providing system is a translation service or the like for example. When using the translation service a user of the image forming apparatus may scan a manuscript to obtain an image data or the like perform an OCR optical character recognition process on the obtained image data and send it to the service providing system . Then the user may view a translated result by accessing the service providing system via the user terminal or may receive a translated result by an electronic mail or the like.

The service platform providing system is connected to the network N via a firewall FW. The service platform providing system may be actualized by one or more data processing apparatuses on each of which a general OS or the like is mounted.

The service platform providing system has functions such as an authentication permission function a tenant user management function a license management function an account registration function or the like for example. The service platform providing system receives a request to register an account or a request to log in from the user terminal or the image forming apparatus . The service platform providing system also receives a request to confirm an authentication ticket or request to obtain user data from the service providing system .

The operation platform providing system includes an operation terminal a license management server and the network N. The network N is a private network and a firewall FW is provided between the network N and the network N. The operation terminal and the license management server are connected to the network N. Each of the operation terminal and the license management server may be actualized by one or more data processing apparatuses on each of which a general OS or the like is mounted.

The operation terminal includes a wireless communication means or a wired communication means. The operation terminal may be a terminal operable by a work operator such as a smartphone a mobile phone a tablet terminal a PC or the like. The work operator is capable of requesting issuance of a license from the operation terminal to the license management server .

The license management server has a function to manage licenses or the like. The license management server receives a request of issuance of a license or the like from the service platform providing system or the operation terminal . The structure of the data processing system illustrated in is just an example and the data processing system may have another structure.

The computer illustrated in includes an input device a display device an external I F a RAM Random Access Memory a ROM Read Only Memory a CPU Central Processing Unit a communication I F a HDD Hard Disk Drive and the like and each of them is connected with each other via a bus B. The input device and the display device may be connected only when it is necessary.

The input device includes a keyboard a mouse or the like and is used by a user to input various operation signals. The display device includes a display or the like and displays a processed result by the computer .

The external I F is an interface for an external device. As the external device a recording medium or the like may be raised. With this configuration the computer can read and or write data from and on the recording medium via the external I F . As the recording medium a flexible disk a Compact Disk CD a Digital Versatile Disk DVD an SD Memory card a Universal Serial Bus memory USB memory or the like may be raised.

The RAM is a volatile semiconductor memory storage device that temporarily stores programs and data. The ROM is a non volatile semiconductor memory storage device that can store programs and data even when the switch is turned off. The ROM stores programs and data such as a Basic Input Output System BIOS that is executed when activating the computer an OS setting a network setting or the like.

The CPU is an arithmetic unit that actualizes control and functions of the entirety of the computer by reading out programs or data from the storage device such as the ROM the HDD or the like on the RAM and executing the processes.

The communication I F is an interface that connects the computer to the network N N or N. With this configuration the computer can perform data communication via the communication I F .

The HDD is a non volatile storage device that stores programs or data. The programs or data stored in the HDD include an OS that is basic software for controlling the entirety of the computer application software that provides various functions on the OS or the like for example. Here the computer may include a Solid State Drive SSD instead of the HDD .

Each of the user terminal the application market providing server the operation terminal and the license management server of the embodiment is capable of actualizing the various processes which will be explained later by the hardware structure of the computer . Further the data processing apparatus that actualizes each of the service providing system and the service platform providing system of the embodiment is capable of actualizing the various processes which will be explained later by the hardware structure of the computer .

The controller includes a CPU a RAM a ROM a NVRAM a HDD and the like. The ROM stores various programs and data. The RAM temporarily stores programs or data. The NVRAM stores setting data or the like for example. The HDD stores various programs and data.

The CPU actualizes control and functions of the entirety of the image forming apparatus by reading out programs data setting data or the like from the ROM the NVRAM the HDD or the like on the RAM and executing the processes.

The operation panel includes an input unit that receives input from a user and a display unit that displays data. The external I F is an interface for an external device. As the external device a recording medium or the like may be raised. With this configuration the image forming apparatus can read and or write data from and on the recording medium via the external I F . As the recording medium an IC card a flexible disk a CD a DVD an SD memory card a USB memory or the like may be raised.

The communication I F is an interface that connects the image forming apparatus to the network N. With this configuration the image forming apparatus can perform data communication via the communication I F . The printer is a printing device that prints print data on a paper. The scanner is a reading device that reads image data electronic data from a manuscript. As each of the firewalls FW illustrated in has a general function of a firewall an explanation of a hardware structure for each of the firewalls FW illustrated in is omitted.

The service platform providing system of the embodiment is actualized by a process block as illustrated in for example. is a process block diagram illustrating an example of the service platform providing system of the embodiment. The service platform providing system actualizes the process block as illustrated in by executing a program.

The service platform providing system illustrated in actualizes application a common service a database DB and a platform Application Programming Interface API .

The application includes portal service application scan service application print service application and account registration application as an example.

The portal service application is application that provides a portal service. The portal service provides a service that becomes an entrance to use the data processing system . The scan service application is a UI user interface of application that provides a scan service.

The print service application is a UI of application that provides a print service. The account registration application is a UI of application that provides an account registration service. The application may include another service application.

The UI of each of the scan service application the print service application and the account registration application may include Native application or HTML JavaScript registered trademark data that is displayed or executed at the user terminal or the image forming apparatus . The Native application counterparts Web application and is a type of application whose main process is performed by the user terminal or the image forming apparatus . The Web application is a type of application whose main process is performed by the service platform providing system .

The platform API is an interface for the application such as the portal service application or the like to use the common service .

The platform API is a previously defined interface provided for the common service to receive a request from the application and is configured by a function a class or the like for example. When the service platform providing system is configured by a plurality of data processing apparatuses the platform API can be actualized by a Web API that can be usable via a network for example.

The common service includes a scan service unit a print service unit an account registration unit an authentication certification unit a tenant management unit a user management unit a license management unit a device management unit a temporary image storing processing unit a data storing processing unit an image processing work flow control unit and a log collecting unit . The image processing work flow control unit includes a message queue and one or more workers . The workers actualize functions such as image transformation image transmission and the like.

The database includes a log data storing unit a tenant data storing unit a user data storing unit a license data storing unit a device data storing unit a temporary image storing unit a job data storing unit and a storing unit for setting data specific to application hereinafter referred to as setting data storing unit .

The scan service unit functions as a logic API of the scan service application . The print service unit functions as a logic API of the print service application . The account registration unit functions as a logic APT of the account registration application .

The authentication certification unit authenticates and certificates based on a request to log in from the office device such as the user terminal the image forming apparatus or the like. The office device is a generic name of the user terminal the image forming apparatus and the like.

The authentication certification unit authenticates and certificates a user by accessing the user data storing unit the license data storing unit or the like for example. Further the authentication certification unit authenticates the image forming apparatus or the like as a client by accessing the tenant data storing unit the license data storing unit the device data storing unit or the like for example.

The tenant management unit manages tenant data stored in the tenant data storing unit . The user management unit manages user data stored in the user data storing unit .

The license management unit manages license data stored in the license data storing unit . The device management unit manages device data stored in the device data storing unit . The temporary image storing processing unit stores a temporary image in the temporary image storing unit and obtains the temporary image from the temporary image storing unit . The data storing processing unit stores data in the job data storing unit or the like.

The image processing work flow control unit controls a work flow regarding image processing based on a request from the application . The message queue includes a queue that corresponds to a kind of a process. The image processing work flow control unit inputs a message of a request regarding a process job to a queue that corresponds to a kind of the job.

The workers monitor corresponding queues respectively. Then when a message is input in the respective queue the worker performs a process such as image transformation image transmission or the like that corresponds to a kind of the respective job. The message input in the queue may be mainly read out by the worker Pull or the queue may provide the message to the worker Push . The log collecting unit stores collected log data in the log data storing unit for example.

The log data storing unit stores log data. The tenant data storing unit stores tenant data. The user data storing unit stores user data. The license data storing unit stores license data. The device data storing unit stores device data. The temporary image storing unit stores a temporary image. The temporary image is a file or data such as a scan image or the like processed by the worker for example.

The job data storing unit stores information of request job data regarding the process job . The setting data storing unit stores setting data specific to the application .

The service platform providing system functions as an integrated base that provides a common service such as authentication certification a work flow regarding image processing or the like and a service group that provides application services such as a scan service a print service and the like using a function of the integrated base.

The integrated base is configured by the common service the database and the platform API for example. The service group is configured by the application for example. As such the service platform providing system illustrated in has a structure in which the service group and the integrated base are separated.

As the service platform providing system illustrated in has the structure in which the service group and the integrated base are separated it is easy to develop the application that uses the platform API . Further with the service platform providing system illustrated in it is easy to develop the service providing system that uses the platform API .

Here the embodiment of classification of the process block of the service platform providing system illustrated in is just an example and it is not essential to classify the application the common service and the database by layers as illustrated in . For example as long as it is possible to perform the processes of the service platform providing system a layer relationship or the like illustrated in is not limited to a specific structure.

The image forming apparatus is actualized by a functional structure illustrated in for example. is a process block diagram illustrating an example of the image forming apparatus of the embodiment. A browser of the image forming apparatus illustrated in includes a display input unit a screen generating unit a script interpreting unit a data storage unit and a communication unit for example.

The display input unit accepts an input instruction by an operation from a user via the operation panel or the like and displays a log in screen or the like that is generated by the screen generating unit on the operation panel.

The screen generating unit performs a rendering process on an HTML file or the like obtained from the service platform providing system via the communication unit . The screen generating unit generates the log in screen or the like based on JavaScript data analyzed by the script interpreting unit .

The script interpreting unit analyzes JavaScript or the like obtained from the service platform providing system via the communication unit for example. The data storage unit is configured by a local storage a session storage or the like for example and stores HTML JavaScript data or the like obtained from the service platform providing system via the communication unit .

The communication unit sends a request to log in to the service platform providing system and obtains various files from the service platform providing system .

Next an example of the tenant data stored in the tenant data storing unit or the like of the service platform providing system is explained. is a view illustrating an example of the tenant data of the embodiment.

Although the tenant data illustrated in includes data items such as tenant ID license and the like for example this is not limited so. The tenant ID is data that specifies a group organization such as a company a department or the like. The tenant ID is not limited to an idiom tenant and may be tenant data that identifies a contract for example. The tenant ID is uniquely provided.

The license is data that indicates whether a license is issued for each of the services for the respective tenant ID. For the example of it is illustrated whether a license is issued for each of the services such as translate translation service signage or the like.

For the example of it is illustrated that a license is issued for a translate service is issued but a license is not issued for a signage service for the tenant ID 600000000 .

Next an example of the user data stored in the user data storing unit or the like of the service platform providing system is explained. is a view illustrating an example of the user data of the embodiment.

Although the user data illustrated in includes data items such as mail address tenant ID user name authority of service utilization and the like for example this is not limited so. The mail address is data of a mail address for log in that is set to correspond to a user name for example. The tenant ID corresponds to the tenant ID illustrated in . The user name indicates a name of the user.

The authority of service utilization is data that indicates whether the respective user has an authority of utilization for a service for example.

For the example of a user whose user name is Taro Yamada belongs to the tenant ID 600000000 and is capable of logging in by a mail address taro yamada example.com . Further the user whose user name is Taro Yamada has an authority of service utilization for translate .

Next an example of a service class that is set in association with the tenant data or the user data is explained. is a view illustrating an example of service data of the embodiment.

Although the service data illustrated in includes data items such as service class and the like for example this is not limited so. The service class is data that specifies a service such as translate translation service signage or the like.

In the data processing system the image forming apparatus logs in to the service platform providing system when using a service provided by the service providing system for example. is a view illustrating an example of a sequence for logging in of the embodiment.

For the example of when a user successfully logs in the image forming apparatus stores the tenant ID of the tenant to which the user belongs and controls display of a log in screen based on whether the tenant ID is stored or not when displaying the log in screen for example.

Usually the image forming apparatus is provided at a place like a workplace for example and the image forming apparatus is commonly used by a plurality of users who belong to the place. In this case such users may be set to belong to the same tenant. In other words the users who belong to the same place and the tenant are provided with the same tenant ID.

Then in this embodiment if either of the users successfully logs in to the service platform providing system from the image forming apparatus the tenant ID of the user is stored in the data storage unit of the image forming apparatus . Then if either of the users tries to log in to the service platform providing system thereafter if the tenant ID is stored a log in screen in which a user list of users who belong to the tenant is displayed is displayed. Thus if either of the users a first user is already succeeded in logging in it is unnecessary for another user who belongs to the same tenant as the first user to input the mail address.

On the other hand when the tenant ID is not stored it means that no user is succeeded in logging in and thus a log in screen for inputting user specifying data a mail address and a password for example is displayed.

Specifically the sequence illustrated in is performed by the display input unit the screen generating unit the script interpreting unit the data storage unit and the communication unit of the image forming apparatus and the service platform providing system .

As illustrated in at the image forming apparatus the display input unit accepts from a user a selection of a service from an application list screen of an application market S and a request to display a log in screen of the selected service S for example. The screen generating unit upon receiving a request to generate the log in screen from the display input unit S requests the communication unit to obtain the log in screen from the service platform providing system S .

The service platform providing system upon receiving the request to obtain the log in screen as obtaining a resource via the communication unit of the image forming apparatus S sends generated HTML data to the image forming apparatus . At the image forming apparatus the screen generating unit requests the script interpreting unit to execute the script based on the HTML data obtained from the service platform providing system S .

The script interpreting unit obtains a service class of the service selected in the process of S S . In the process of S the script interpreting unit obtains the service class from a character string translate for the case of the translation service that identifies a service that is set as a query in URL http example.com login service class translate for example of the service selected in the process of S.

Further the script interpreting unit requests the data storage unit to obtain the tenant ID S . When the tenant ID is not stored in the data storage unit the script interpreting unit generates a mail address password input screen as a first input screen S .

On the other hand when the tenant ID is stored in the data storage unit the script interpreting unit requests the data storage unit to obtain a user list by designating the service class obtained in the process of S S . In the process of S it is possible for the script interpreting unit to obtain a user list of users who have authority of utilization for the designated service by designating the service class when obtaining the user list.

When there is no user list or less than one in the data storage unit the script interpreting unit requests the communication unit to obtain a user list from the from the service platform providing system by designating the tenant ID and the service class S .

The service platform providing system receives the request to obtain the user list in which the tenant ID and the service class are designated as obtaining a resource via the communication unit of the image forming apparatus S . In the process of S the service platform providing system refers to the user data as illustrated in and sends a user list of users who belong to the designated tenant ID and who have authority of utilization for a service corresponding to the service class to the image forming apparatus .

At the image forming apparatus the script interpreting unit stores the user list obtained from the service platform providing system in the data storage unit S and generates a screen user list screen for selecting a user from the user list as a second input screen S .

According to the above described sequence for a first time log in as the user list is not stored in the data storage unit the user list of the users who belong to the designated tenant ID and who have authority of utilization of the designated service is obtained from the from the service platform providing system . For a second or later time login the log in screen is generated using the user list stored in the data storage unit . With this configuration the number of times for requesting to the service platform providing system is reduced and performance for displaying a screen can be improved.

Next the application list screen that is displayed on the operation panel of the image forming apparatus is explained. illustrates an example of an application list screen . The application list screen illustrated in is an example of a screen for a user to select a service to use. The application list screen includes buttons for the user to select the service to use.

When the button of the service to use XXX service for example is selected from the application list screen illustrated in the image forming apparatus displays either of the following two patterns of log in screens based on whether the tenant ID is stored or not. A first pattern is a log in screen first input screen for the case when the tenant ID is not stored to input a mail address. is a view illustrating an example of a log in screen to input a mail address.

The log in screen illustrated in is displayed on the operation panel of the image forming apparatus . The log in screen illustrated in includes input sections for a mail address and a password and a log in button . When the mail address and the password are input in the input sections and the log in button is selected in the log in screen the image forming apparatus requests the service platform providing system to log in by designating the input mail address and the password as user specifying data.

Next as a second pattern for the case when the tenant ID is stored the image forming apparatus displays a log in screen second input screen using a user list. to are views illustrating an example of a log in screen using a user list. Log in screens to illustrated in to respectively are displayed on the operation panel of the image forming apparatus .

The log in screen illustrated in includes a user list buttons for selecting a user from the user list a button indicating log in by the mail address and the password and an update list button . In the user list of the log in screen user names of users who belong to the stored tenant ID and who have an authority of service utilization for the designated service class are displayed for example.

Here when obtaining the user list from the service platform providing system the image forming apparatus obtains association data that is associated with the user specifying data of the user who is successfully logged in among the user data illustrated in . The image forming apparatus obtains as the association data the tenant ID of the succeeded user and the service class for which the succeeded user has an authority of service utilization the user name the mail address or the like of each of the users who belong to the tenant ID and have an authority of service utilization for the service class for example.

When the button for selecting the user from the user list is selected in the log in screen the image forming apparatus transits to the log in screen illustrated in . Further when the button indicating log in by the mail address and the password is selected in the log in screen the image forming apparatus transits to the log in screen illustrated in . Further when the update list button is selected in the log in screen the image forming apparatus requests the service platform providing system to obtain a user list and updates the user list illustrated in .

The log in screen illustrated in includes a display section for displaying the user name of the user selected from the user list an input section of a password and a log in button .

When the password is input in the input section and the log in button is selected in the log in screen the image forming apparatus reads out the mail address of the user displayed at the display section from the data storage unit and requests the service platform providing system to log in by designating the read out mail address and the input password.

As described above it is possible to request the service platform providing system to log in using the user specifying data mail address of the user password similar to that of the first pattern just by selecting a user from the user list and inputting a password. Further as it is unnecessary for the user to input a part mail address of the user for example of the user specifying data necessary to log in and the user needs to input the password only efforts for inputting data for logging in for the user can be reduced.

The log in screen illustrated in includes input sections for a mail address and a password a log in button and an adding account button . When the mail address and the password are input in the input sections and the log in button is selected in the log in screen the image forming apparatus request the service platform providing system to log in by designating the mail address the password and the stored tenant ID. Here as the tenant ID is designated even if the mail address and the password match a user with a different tenant ID fails to log in.

Here when the mail address and the password are input and the adding account button is selected in the log in screen the image forming apparatus requests the service platform providing system to add an account by designating the mail address the password the service class and the tenant ID. The service platform providing system upon receiving the request to add the account from the image forming apparatus registers the account based on the designated user specifying data or the like. With this configuration when the update list button illustrated in is selected a user whose account is newly registered is also added in the user list illustrated in .

The data of the user list illustrated in is generated by obtaining the user name and the mail address of each of the users who belong to the tenant ID and have an authority of service utilization for the service class of the succeeded user who is successfully logged in among the user data illustrated in from the service platform providing system . Here the data of the user list illustrated in may be generated for each of the service classes for example.

Among data of the user list illustrated in the user name is displayed on the log in screen illustrated in . Further as described above when the password is input in the input section and the log in button is selected in the log in screen as illustrated in the mail address of the user whose name is displayed at the display section is read out from the data storage unit .

Next a sequence for logging in by the mail address is explained. is a view illustrating an example of a sequence for logging in by a mail address. For the example of the user logs in by the mail address and the password user specifying data input in the log in screen or the like generated in the process of S of .

The sequence illustrated in is performed by the display input unit the screen generating unit the script interpreting unit the data storage unit and the communication unit of the image forming apparatus and the service platform providing system .

As illustrated in at the image forming apparatus the display input unit accepts from a user an input of the mail address and the password in the log in screen illustrated in S and pressing of the log in button S for example. The screen generating unit upon receiving pressing of the log in button from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit requests the communication unit to log in by designating the mail address and the password S . Here in the process of S when the tenant ID is stored in the data storage unit such as a case that the mail address and the password are input from the log in screen illustrated in or the like for example the tenant ID is also sent as a parameter.

The service platform providing system receives the request to log in by the mail address in which the mail address and the password are designated as generating a resource via the communication unit of the image forming apparatus S .

Here the service platform providing system refers to the user data illustrated in authenticates the user using the mail address and the password received in the process of S and notifies the authentication result to the image forming apparatus . When the user is successfully authenticated the service platform providing system sends the tenant ID to which the user specified by the mail address and the password belongs with a notification of authentication OK. Further when the authentication of the user is failed the service platform providing system sends a notification of authentication NG error .

Here when the service platform providing system receives the tenant ID with the mail address and the password and the tenant ID of the user specified by the mail address and the password and the received tenant ID are different the service platform providing system sends a notification of authentication error.

At the image forming apparatus when the notification of authentication OK is received based on the authentication result notified from the service platform providing system the tenant ID is stored in the data storage unit S . Further at this time the image forming apparatus redirects the application service that is selected from the application list screen by the user in the process of S in S .

When the tenant ID is stored in the process of S even when the newly accepted mail address and password are right if the user does not belong to the tenant of the stored tenant ID an authentication error is sent from the service platform providing system . As such it is possible to control that after once the tenant ID is stored a user who belong to another tenant cannot log in from the image forming apparatus to use the application.

Next a sequence for logging in from the log in screen using the user list is explained. is a view illustrating an example of a sequence for logging in from the user list. The sequence illustrated in is performed by the display input unit screen generating unit the script interpreting unit and the data storage unit of the image forming apparatus .

As illustrated in at the image forming apparatus the display input unit accepts from a user a selection of a user name to be logged in from the user list displayed on the log in screen illustrated in for example S . The screen generating unit upon receiving the selected user name from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit upon obtaining the mail address corresponding to the user name selected from the user list from data storage unit and internally storing it S generates the log in screen password input screen illustrated in for inputting a password and displays it S .

The display input unit accepts from the user an input of a password and pressing of the log in button in the log in screen illustrated in the process of S S . The screen generating unit upon receiving pressing of the log in button from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit upon obtaining the tenant ID stored in the data storage unit S requests the service platform providing system to log in via the communication unit by designating the mail address stored in the process of S the password input by the user and the tenant ID. As subsequent processes are the same as the processes after S illustrated in explanations are not repeated.

As the mail address and the password are used for the service platform providing system in the log in process illustrated in it is similar to that illustrated in . However in this case as the user is unnecessary to input the mail address time and efforts can be simplified.

By selecting the button indicating log in by the mail address and the password illustrated in the log in screen of the user may log in by the mail address and the password using the log in screen illustrated in instead of logging in from the user list. Here for the log in process using the user list information regarding users who belong to the tenant a status of the authority of utilization for the service or the like is displayed so that the user who tries to log in can see the information or the like. Thus whether the log in process using the user list is permitted or not may be controlled.

Next a sequence for executing setting whether to permit usage of a user list to the service platform providing system is explained. is a view illustrating an example of a sequence for setting whether to permit usage of a user list.

The sequence illustrated in is performed by the display input unit the screen generating unit the script interpreting unit the data storage unit and the communication unit of the image forming apparatus and the service platform providing system . In this case the information indicating whether to permit usage of a user list that is previously set by the administrator or the like of the image forming apparatus is stored in the service platform providing system in association with the tenant ID for example.

As illustrated in at the image forming apparatus the display input unit accepts from a user a request to display the setting screen illustrated in for example S . The screen generating unit upon receiving a request to generate the setting screen from the display input unit S requests the communication unit to obtain the setting screen from the service platform providing system S .

The service platform providing system upon receiving the request to obtain the setting screen as obtaining a resource via the communication unit of the image forming apparatus S sends generated HTML data to the image forming apparatus . At the image forming apparatus the screen generating unit requests the script interpreting unit to execute the script based on the HTML data obtained from the service platform providing system S .

The script interpreting unit obtains the tenant ID from the data storage unit and requests the communication unit to obtain information indicating whether to permit usage of a user list from the service platform providing system by designated the tenant ID S . The service platform providing system upon receiving the request to obtain the information indicating whether to permit usage of a user list as obtaining a resource via the communication unit of the image forming apparatus S notifies the image forming apparatus the information indicating whether to permit usage of a user list.

At the image forming apparatus the script interpreting unit updates the setting screen based on the information indicating whether to permit usage of a user list notified from the service platform providing system S . The script interpreting unit based on the information indicating whether to permit usage of a user list notified from the service platform providing system adds a check in the check box when usage of the user list is permitted and deletes the check of the check box of the setting screen when usage of the user list is not permitted in the setting screen .

The display input unit accepts from the user setting of the check in the check box from the setting screen S and pressing of the OK button S . The screen generating unit upon receiving pressing of the OK button from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit upon obtaining a status of the check box of the setting screen S requests the communication unit to update the information indicating whether to permit usage of a user list by designating the tenant ID and the information indicating whether to permit set by the user in the service platform providing system S . The service platform providing system upon receiving a request to update a resource via the communication unit of the image forming apparatus S updates the information indicating whether to permit usage of a user list for the tenant ID.

 Sequence for obtaining User List based on Information indicating whether to permit usage of User List 

Next a sequence for obtaining a user list based on the information indicating whether to permit usage of a user list set in the service platform providing system in the sequence illustrated in is explained.

For the example of in response to a request to display a log in screen by the user when the tenant ID is not stored in the data storage unit in the process of S the script interpreting unit of the image forming apparatus generates the mail address password input screen S .

On the other hand when the tenant ID is stored in the data storage unit the script interpreting unit requests the communication unit to obtain information indicating whether to permit usage of a user list from the service platform providing system by designating the tenant ID S . The service platform providing system upon receiving the request to obtain the information indicating whether to permit usage of a user list as obtaining a resource via the communication unit of the image forming apparatus S notifies the information indicating whether to permit usage of a user list to the image forming apparatus .

When the usage of the user list is permitted based on the information indicating whether to permit usage of a user list notified from the service platform providing system the script interpreting unit refers to the data storage unit to obtain the user list by designating the service class obtained in the process of S S . When the usage of the user list is not permitted the script interpreting unit generates the mail address password input screen illustrated in

As whether to permit usage of a user list is set stored in the service platform providing system in the sequences illustrated in and it is possible to set whether to permit usage of a user list for each tenant ID for example.

Next a sequence for setting and storing whether to permit usage of a user list as described above in the image forming apparatus is explained. is a view illustrating an example of a sequence for setting whether to permit usage of a user list at the image forming apparatus .

The sequence illustrated in is actualized by the display input unit the screen generating unit the script interpreting unit the data storage unit and the communication unit of the image forming apparatus and the service platform providing system . In this case the information indicating whether to permit usage of a user list that is previously set by the administrator or the like of the image forming apparatus is stored in the data storage unit for example. Here as processes of S to S illustrated in are the same as those of S to S illustrated in explanations are not repeated.

For the example of in response to a request to display the setting screen for setting whether to permit usage of a user list the script interpreting unit of the image forming apparatus refers to the data storage unit to obtain the information indicating whether to permit usage of a user list S . The script interpreting unit updates the setting screen based on the information indicating whether to permit usage of a user list obtained from the data storage unit S . Here in the process of S as the information indicating whether to permit usage of a user list is not stored in the data storage unit for a first time the script interpreting unit may add permitted to use or not add not permitted to use a check in the check box of the setting screen as a default.

At the image forming apparatus the display input unit accepts from a user a setting of the check in the check box from the setting screen S and pressing of the OK button S . The screen generating unit upon receiving pressing of the OK button from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit upon obtaining the above described status of the check box of the setting screen S updates the information indicating whether to permit usage of a user list set by the user S .

 Sequence for obtaining User List based on Information indicating whether to permit usage of a User List Set at Image Forming Apparatus 

Next a sequence for obtaining a user list based on the information indicating whether to permit usage of a user list set in the image forming apparatus in the sequence illustrated in is explained. is a view illustrating an example of a sequence for obtaining a user list based on the information indicating whether to permit usage of a user list at the image forming apparatus .

The sequence illustrated in is performed by the display input unit the screen generating unit script interpreting unit data storage unit communication unit of the image forming apparatus and the service platform providing system . Here as process of S to S illustrated in are the same as those of S to S illustrated in explanations are not repeated.

For the example of in response to a request to display a log in screen by the user when the tenant ID is not stored in the data storage unit in the process of S the script interpreting unit of the image forming apparatus generates the mail address password input screen S .

On the other hand when the tenant ID is stored in the data storage unit the script interpreting unit refers to the data storage unit to obtain information indicating whether to permit usage of a user list S .

When the usage of the user list is permitted based on the information indicating whether to permit usage of a user list obtained from the data storage unit the script interpreting unit refers to the data storage unit to obtain the user list by designating the service class obtained in the process of S S . When the usage of the user list is not permitted the script interpreting unit generates the mail address password input screen illustrated in S . Here in the process of S the mail address password input screen is controlled not to display a switching link to the log in screen in which the user list is displayed illustrated in for example.

As whether to permit usage of a user list is set in the image forming apparatus in the sequences illustrated in and it is possible to set the setting of whether to permit usage of a user list for each image forming apparatus .

Next a sequence for cooperation with authentication by the image forming apparatus is explained. In this case when cooperating with the authentication by the apparatus it is unnecessary for the user who is already successfully logged in to the image forming apparatus to perform a log in process again for using the above described application. is a view illustrating an example of a sequence for cooperation with the authentication by the apparatus.

The sequence illustrated in is performed by the display input unit the screen generating unit the script interpreting unit the data storage unit and the communication unit of the image forming apparatus and the service platform providing system .

For the sequence illustrated in the user data illustrated in further includes a data item on premises ID or the like for example for registering second user specifying data user ID for example that is used for the authentication of the user to log in to the image forming apparatus . Upon receiving a request to log in by the on premises ID from the image forming apparatus the service platform providing system may refer to the second user specifying data of the user data illustrated in and authenticate the user.

Here as processes of S to S illustrated in are the same as those of S to S illustrated in explanations are not repeated. For the example of at the image forming apparatus in response to a request to display a log in screen by the user the script interpreting unit refers to the data storage unit to obtain the tenant ID S . When the tenant ID is not stored in the data storage unit the script interpreting unit generates the mail address password input screen S . On the other hand when the tenant ID is stored in the data storage unit the script interpreting unit obtains the second user specifying data hereinafter referred to as authenticated data by the apparatus as well that was used for the user to log in to the image forming apparatus S . This means that when the user is logged in to the image forming apparatus the second user specifying data of the user is stored in the data storage unit or the like in the image forming apparatus . Thus this second user specifying data of the user is used as the authenticated data by the apparatus in this example.

The script interpreting unit upon obtaining the authenticated data by the apparatus in the process of S authenticated data by the apparatus exists request the communication unit to log in by the on premises ID by designating the tenant ID obtained in the process of S and the authentication by the apparatus user ID obtained in the process of S S .

The service platform providing system receives the request to log in by the on premises ID in which the tenant ID and the user ID used for the authentication by the apparatus are designated as generating a resource via the communication unit of the image forming apparatus S . The service platform providing system authenticates the user using the tenant ID and the user ID used for the authentication by the apparatus received in the process of S and notifies an authentication result to the image forming apparatus .

At the image forming apparatus when the authentication result notified from the service platform providing system is authentication OK success the script interpreting unit redirects the application service selected from the application list screen S . For the case of authentication NG failure the script interpreting unit generates the mail address password input screen S . Further the script interpreting unit when the authenticated data by the apparatus cannot be obtained no authenticated data by the apparatus generates the user list screen illustrated in S .

Here the case of the failure in authentication of the user using the on premises ID includes a case that the user ID used for the authentication by the apparatus is not set in the data item of the on premises ID of the user data illustrated in . Thus after the process of S when the user is successfully authenticated by the mail address and the password the script interpreting unit requests the communication unit to set identification data by designating the user ID used for the authentication by the apparatus S .

Upon receiving a request to update the resource via the communication unit of the image forming apparatus S the service platform providing system may set the user ID used for the authentication by the apparatus for the data item of the on premises ID in the user data illustrated in .

As described above when the user is already logged in the image forming apparatus the user can use the application service without performing a log in process to the service platform providing system again.

In each of the above described sequences the user list is obtained using the tenant ID. This means that it is possible to obtain data regarding users who belong to the tenant based on the tenant ID. Thus the service platform providing system may authenticate an apparatus in order to limit the usage of the user list to the previously set image forming apparatus in response to a request to obtain the user list.

For authenticating an apparatus for example a client authentication of SSL Secure Sockets Layer may be used or the apparatus may be authenticated by embedding a previously set password in a browser or the like.

Further the script interpreting unit or the like of the image forming apparatus may generate an apparatus authentication password the authentication certification unit or the like of the service platform providing system may generate an apparatus authentication ticket by the apparatus authentication password obtained from the image forming apparatus and send it to the image forming apparatus . The service platform providing system may when receiving a request to obtain a user list from the image forming apparatus limit the access for obtaining the user list based on whether the apparatus authentication ticket exists or not.

Next a sequence for logging in without using the tenant ID is explained. For example it is possible to control such that a log in is performed without designating tenant ID based on a setting by setting whether to log in by designating tenant ID using the setting screen illustrated in .

As illustrated in at the image forming apparatus the display input unit accepts from a user an input of the mail address and the password in the log in screen illustrated in S and pressing of the log in button S for example. The screen generating unit upon receiving pressing of the log in button from the display input unit S requests the script interpreting unit to execute the script S .

The script interpreting unit requests the communication unit to log in by designating the mail address and the password S . The service platform providing system receives the request to log in by the mail address in which the mail address and the password are designated as generating a resource via the communication unit of the image forming apparatus S .

The service platform providing system authenticates the user using the mail address and the password received in the process of S and notifies the authentication result to the image forming apparatus . When the user is successfully authenticated the service platform providing system sends the tenant ID to which the user specified by the mail address and the password belongs with a notification of authentication OK. Further when the authentication of the user is failed the service platform providing system sends a notification of authentication NG error .

The image forming apparatus stores the tenant ID notified from the service platform providing system in the data storage unit S . Further the image forming apparatus redirects the application service selected from the application list screen by the user in the process of S in S .

As the tenant ID is not designated in the above described sequence when requesting to log in if the mail address and the password are right in the next request to log in the user is successfully authenticated. At this time if a user who belongs to a tenant different from the tenant of the tenant ID currently stored in the image forming apparatus logs in a new tenant ID is stored.

In this embodiment a unit may be provided that deletes periodically or explicitly by an instruction the user list stored in the data storage unit . By periodically deleting the stored user list as such an updated user list can be obtained that corresponds to increase decrease and change of users registered in the service platform providing system .

The individual constituents of the data processing system may be embodied by arbitrary combinations of hardware and software typified by a CPU of an arbitrary computer a memory a program loaded in the memory so as to embody the constituents illustrated in the drawings a storage unit for storing the program such as a hard disk and an interface for network connection. It may be understood by those skilled in the art that methods and devices for the embodiment allow various modifications.

Although a preferred embodiment of the data processing system and the data processing method has been specifically illustrated and described it is to be understood that minor modifications may be made therein without departing from the spirit and scope of the invention as defined by the claims.

The present invention is not limited to the specifically disclosed embodiments and numerous variations and modifications may be made without departing from the spirit and scope of the present invention.

The image forming apparatus is an example of a service using apparatus. The script interpreting unit is an example of an authentication requesting unit an obtaining unit a setting unit a password generating unit and an authentication unit. The display input unit is an example of an accepting unit or a switching unit. The service platform providing system is an example of a data processing apparatus. The authentication certification unit is an example of a ticket generating unit and an access control unit.

The present application is based on and claims the benefit of priority of Japanese Priority Application No. 2014 223518 filed on Oct. 31 2014 the entire contents of which are hereby incorporated by reference.


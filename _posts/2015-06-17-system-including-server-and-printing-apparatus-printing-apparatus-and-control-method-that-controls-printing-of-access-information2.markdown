---

title: System including server and printing apparatus, printing apparatus, and control method that controls printing of access information
abstract: Print control of access information for which a valid period is set is performed properly. A printing apparatus acquires access information which is to be used for accessing a server and which has a valid period set for the access. If an elapsed time from the acquisition of the access information exceeds a predetermined time, the printing apparatus does not print the access information even if the valid period has not expired. If the elapsed time does not exceed the predetermined time, the printing apparatus prints the access information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09639316&OS=09639316&RS=09639316
owner: Canon Kabushiki Kaisha
number: 09639316
owner_city: Tokyo
owner_country: JP
publication_date: 20150617
---
The present invention relates to a print control device a print control method and a program which cause a printing apparatus to print access information for accessing an external device.

There is a case in which authentication processing for registering user information is performed in order to utilize a service provided on an Internet site. As such authentication processing a method for issuing a right of use as an access token is available.

Japanese Patent Laid Open No. 2012 113696 describes a technique in which when a user inputs using a multifunction printer MFP a provisional registration ID acquired by a personal computer PC a Web server which provides a service issues an access token to the MFP.

A method for registering a right of use as described below is also available. First a server which provides a service transmits to a client apparatus a uniform resource locator URL of an authentication page for granting a right of use invite page url hereinafter referred to as an authentication URL . The authentication URL is presented to a user when it is displayed or printed by the client apparatus. Then the user accesses the authentication page in accordance with the authentication URL by using an apparatus provided with a browsing function and requests the server to issue an access token. In response to the request the server issues the access token to the client apparatus. Accordingly the client apparatus becomes able to utilize the service by using the access token issued as described above.

In the server which provides a service as described above in order to reduce the risk that the authentication URL is utilized by a third party who is not the user of the client apparatus a validity period may be set for authentication processing using the authentication URL.

However for example in the case where the authentication URL is printed by a printer a long time may be required to perform printing due to various factors including waiting for permission of printing by the user waiting for completion of another printing process recovering from various errors and preparation for a recording material and a paper sheet and the like. Thus when printing of the authentication URL is completed and the user accesses the authentication page in accordance with the authentication URL the valid period for authentication based on the authentication URL may have already expired.

If the valid period of the authentication URL expires not only acquisition of the right of use access token will fail but also a paper sheet and a recording material used to print the authentication URL will be wasted.

The present invention provides proper print control of access information for which a valid period is set.

Accordingly in a system according to an aspect of the present invention a server includes a transmission unit configured to transmit to the printing apparatus access information which is to be used for accessing the server and which has a valid period set for the access and an execution unit configured to execute processing based on the access if the access based on the access information transmitted by the transmission unit is made before the valid period has expired. The printing apparatus includes an acquisition unit configured to acquire the access information transmitted by the transmission unit if an elapsed time from the acquisition of the access information by the acquisition unit exceeds a predetermined time the printing apparatus does not print the access information even if the valid period has not expired and if the elapsed time does not exceed the predetermined time the printing apparatus prints the access information.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Hereinafter a first embodiment of the present invention will be described in detail with reference to figures. is a diagram illustrating an example of a system configuration according to the first embodiment.

An MFP is connected to a relay server via the Internet and is connected via the relay server to a picture sharing site hereinafter referred to as site as a Web application server. The server of the site stores images uploaded from devices such as a PC a smartphone and a tablet. The MFP is capable of downloading images from such a server and printing the images by utilizing a service provided by the site. The MFP is also capable of uploading read images which are obtained by reading documents to such a server.

In order for the MFP to utilize such a service it is necessary to register the MFP with a site A or a site B . Specifically an access token which corresponds to an account of the MFP needs to be issued to the MFP as the right to use a service provided by the site. The access token includes account information of the MFP and information for specifying a service available with the access token. When utilizing a service provided by the site the MFP transmits the access token together with a use request to the server of the site. When the account information included in the access token matches an account registered with the server the server permits to provide the service to the MFP . In the first embodiment the issuance of an access token is executed by OAuth 2.0 authentication.

In order for the MFP to utilize each of the site A and the site B the MFP needs to acquire access tokens corresponding to each site. Each of the site A and the site B provides a Web page for authentication to issue the corresponding access token. When the MFP issues a request for issuance of an access token information which includes a URL of the Web page for authentication and a user code is transmitted to the MFP and the information is printed at the MFP . Communication between the MFP and the site A or the site B is executed through the relay server .

In accordance with the URL printed as above a user accesses the Web page for authentication. Specifically a PC has a browsing function and the user inputs the URL to a Web browser of the PC to access the Web page for authentication. The user does not necessarily access the authentication page by using the PC . The user may access the authentication page by using a device such as a smartphone a tablet or a mobile phone in place of the PC . If the MFP has a browsing function access using the MFP is possible.

On the Web page that the user accesses using the PC in accordance with the above URL the user inputs a user account managed by the site and the user code printed as described above. Thus the site associates the user account as the owner s account of the MFP with the MFP . Furthermore an access token as the right to use a service relating to an image corresponding to the user account is issued to the MFP .

With the site A and the site B an image which may be provided is distinguished by the user account. That is the site A and the site B are designed such that a specific image is provided to a specific user. Therefore the authority of an access token issued to the MFP is limited to the use of an image which may be browsed by the user account corresponding to the MFP . For example by using the access token issued as described above the MFP is capable of printing an image that corresponds to the user account in the picture sharing site without through a PC. Specifically the MFP is capable of displaying a selection screen for selecting album image data stored in the site selecting an image as a printing target in accordance with a user instruction acquiring the image from the site and performing printing.

Furthermore the MFP does not implement an individual application programming interface API corresponding to each of the multiple sites but implements an API for the relay server . The relay server communicates with the multiple sites using APIs corresponding to the individual sites. Therefore the MFP designates a site and issues a request to the relay server . The relay server specifies the site designated by the request from the MFP and acquires information from the site using the API corresponding to the site which is provided beforehand. The relay server also assists the MFP in processing for registering the right to use the site. Specifically the relay server notifies the site designated by the MFP of a request from the MFP for issuance of an access token acquires the access token transmits the acquired access token to the MFP and the like.

As described above the site A and the site B provides Web pages for authentication and notify the MFP of URLs as access information for accessing the Web pages for authentication. However there is a risk for example that the user of the MFP loses a print medium on which the URL is printed and the URL is used by a third party who is not the user of the MFP . In this case a user account which has no relation to the MFP may be associated with the MFP and registered with the site. In order to avoid this the site A and the site B each provide the URL to be transmitted to the MFP with a valid period for example 30 minutes from the issuance of the URL . Therefore the user of the MFP needs to perform a registration operation of the MFP within the valid period.

The MFP includes an operation unit a card interface a reading unit and a printing unit . The MFP also includes a central processing unit CPU a read only memory ROM a random access memory RAM a nonvolatile RAM a display unit an image processing unit a compression decompression unit a driving unit and a sensor unit .

The CPU executes on the RAM a program stored in the ROM in accordance with a user operation on the operation unit and thereby controls the MFP . The ROM stores a control command program of the MFP and the like. Since access to an authentication page is performed by the PC as described above the ROM does not need to include a program of a Web browser. In such a case communication with the relay server is executed through an API for the relay server . For example applications dedicated to the use of the site A and site B are stored in the ROM and the applications communicate with the relay server through the above API. Thus it is possible to access the site A and the site B through the relay server even if a Web browser is not provided in the MFP .

The RAM is used as a storage area of a spooler for print jobs and also operates as a working memory of the CPU as described above.

The nonvolatile RAM is a nonvolatile memory in which information acquired by the MFP is stored. For example an access token issued by a site is stored in the nonvolatile RAM . Therefore even if power supply to the MFP is interrupted the access token may be stored.

Furthermore the MFP includes a wireless network unit and a wired network unit . The wireless network unit is able to wirelessly communicate with a wireless local area network LAN access point which conforms to a standard such as IEEE 802.11a. The wired network unit includes an Ethernet connector which is capable of connecting a twisted pair cable such as 100 Base Tx.

By using the wireless network unit or the wired network unit the MFP is able to communicate with other devices connected to the Internet using a transmission control protocol Internet protocol TCP IP technology.

The operation unit is an operation device which includes a key a touch pad and the like to be operated by a user. The display unit is a display which displays a screen for presenting images and various types of information to a user. A touch panel including the display unit and a touch pad as the operation unit that are integrated together may be provided.

The reading unit includes an optical sensor for reading a document. With the optical sensor a read image is generated on the RAM .

An ink tank for storing ink and a recording head for ejecting ink may be mounted at the printing unit . The printing unit also includes a conveyance part for conveying a print sheet and prints an image on a print medium by an ink jet method. The printing unit does not necessarily adopt the ink jet method. For example the printing unit may print an image by an electrophotographic method.

The MFP has a scanner function by the reading unit in addition to a printing function by the printing unit . The MFP also has a copying function using the reading unit and the printing unit .

The card interface is an interface for example to be used by a user to insert a memory card that stores an image to be printed by the printing unit . The image processing unit executes various types of image processing for an image to be printed by the printing unit or an image read by the reading unit . The compression decompression unit executes compression processing for an image read by the reading unite or decompression processing for an image as a printing target received from an external device. The driving unit causes the conveyance part included in the printing unit to operate and drives the recording head. The sensor unit is a sensor for detecting the position size and type of the print medium being conveyed by the conveyance part.

In the first embodiment the printing unit of the MFP prints on a print medium a URL with a valid period as an InvitePage. For example in the case where the display unit is a compact display it may be difficult for a user to see a URL displayed on the display. In order to avoid this by printing the URL on a print medium the visibility of the URL may be enhanced. Furthermore even in the case where the user moves to the PC to input the URL the print medium on which the URL is printed is easy to carry around which enhances the user s operability.

Furthermore the MFP has a network communication function and has a configuration corresponding to an API of the relay server . Specifically the MFP issues a request through an application executing on the MFP to an API of the relay server and thereby acquires authentication registration and information for a picture sharing site. Specifically by performing HTTP POST communication with the relay server through an API of the relay server the MFP issues various requests.

Hereinafter APIs at the time of authentication registration of the relay server and the MFP will be explained. The definition of APIs is as follows 

A request for acquiring the right of use access token of a site designated by the MFP . A return value of the request includes information necessary for generating the InvitePage. The return value also includes polling control information cycle and period for the relay server to wait for a response of an authentication result from the site.

A request for instructing the relay server to wait for a response of an authentication result. The MFP issues the request to the relay server in response to the issuance of an InvitePage. After that the MFP waits for a response from the relay server until receiving the right of use access token as an authentication result.

A request for causing the relay server to acquire album information a URL of an image etc. of the site designated by the MFP . The MFP adds authentication information such as an access token which is necessary for using the site to the request. After issuing the request the MFP enters a waiting state for the album information.

The MFP issues various requests to the relay server through the above APIs. Thus without direct communication with a server of a site being performed or without an API corresponding to each site being implemented the MFP is able to issue a request to each site or acquire information from each site.

The relay server is a server whose main function is an API conversion function which acts as an intermediary for information acquisition between the MFP and a site that provides a picture sharing site function as a Web application server. The relay server functions as a Web server in relation to the MFP whereas the relay server functions as a client in relation to a server of individual picture sharing sites.

A function for interpreting with a parser an eXtensible Markup Language XML list which includes information uniquely defined from individual sites.

A function for deleting data other than information to be transmitted to the MFP from among data acquired from individual sites. The data to be deleted includes content whose valid period has expired image information of an undesignated file type and a file size that exceeds an upper limit and the like.

A function for checking in response to a condition check request from the MFP whether or not connection to servers of individual sites is possible based on an IP address of the MFP and transmitted information.

A control function such as a function for assigning to the server of a site to connect based on destination information of the MFP .

The relay server uses the above functions to perform communication with the MFP and servers of individual sites acquisition of information and various requests.

In step the MFP issues a registration request to the relay server through the API 20. The registration request is issued by a user operation on the operation unit of the MFP . For example when the user activates for the first time an application corresponding to the site A on the display unit a registration request is issued. The registration request includes information indicating that the request is regarding the site A .

In step the relay server recognizes that the registration request is a request for registration with the site A and issues a registration request to the server of the site A using the site A API . At this time device identification information for identifying the MFP is transmitted to the server of the site A and the device identification information is registered with the server. The device identification information is also registered with the relay server . The device identification information is transmitted to the relay server together with the registration request by the MFP in step and is registered with the relay server and the server of the site. Alternatively in the case where information for identifying the MFP has been registered with the relay server beforehand the information may be registered with the server of the site as the device identification information.

In step the server of the site A returns information illustrated in in response to the registration request. illustrates an example of information acquired by the relay server from the site A . Part of the information is printed as an InvitePage.

A portion device code is the above mentioned device identification information for identifying the MFP and is used when the relay server transmits an InvitePage and an access token to the MFP . The portion device code is registered with the relay server as well as the server of the site. For example for data transmission from the site to the MFP the site transmits device code to the relay server along with the data. Then the relay server uses device code to identify the MFP from among many MFPs that the relay server administrates so that data may be transmitted to the MFP .

A portion verification url is URL information necessary for generating an InvitePage and is printed as the InvitePage. The URL information indicates a URL with which the user of the MFP accesses an authentication page of the site A using a device such as the PC .

A portion user code is information to be printed as the InvitePage and to be input in the authentication page that the user accesses in accordance with the URL information. Based on the authentication URL and user code the server of the site is able to confirm that the user who accesses the authentication page in accordance with the authentication URL is the user who has caused printing of the InvitePage that is the access is made from the user of the MFP .

A portion expires in indicates an authentication valid time and is represented in units of seconds. That is expires in represents a period of time up to the expiry time for authentication which uses verification url and user code from the issuance of the information illustrated in . The information is also used as a polling period of the relay server . In order to receive from the site A an access token issued by the site A and transmit the access token to the MFP the relay server executes polling to the site A. The relay server executes polling during the authentication valid time. A portion interval indicates an interval of polling and is represented in units of seconds. The relay server executes polling to the site A in response to an authentication wait request issued by the MFP using the API 21 and acquires the access token.

In step the relay server analyzes the information acquired in step with the parser function extracts information that matches the API as information necessary for the MFP and transmits the extracted information. For example information other than device code is extracted.

The MFP further issues to the relay server an authentication wait instruction which includes polling control information through the API 21 step . The polling control information indicates expires in and interval illustrated in acquired by the MFP in step .

In response to the authentication wait instruction the relay server starts polling to the site step . In step the relay server analyzes with the parser function the polling control information cycle and period acquired from the MFP and executes polling in accordance with the polling control information. In this example polling is performed for 30 minutes at the longest at cycles of five seconds until the access token is issued.

In step the MFP analyzes using parser the data acquired from the relay server extracts information necessary for generating the InvitePage and generates a print data of the InvitePage. Then the MFP causes the printing unit to print the InvitePage on a print medium step .

The MFP sets as a reference time the time when a response is received from the relay server in step . Based on the elapsed time from the reference time the MFP determines whether or not to print the InvitePage. Details will be described later with reference to .

The user inputs the URL information described in the InvitePage printed by the MFP to the PC which has a browsing function and accesses the site A . Then the user requests the server of the site A to grant the MFP the right of use access token step . The device which has the browsing function is not limited to the PC . For example a smartphone a mobile phone a tablet or other types of devices may also be used. Alternatively if a Web browsing function is implemented in the MFP an access token may be requested from the MFP by inputting the URL using the operation unit of the MFP .

When the site A issues information including an authentication URL in the relay server authentication processing using the authentication URL is valid only during the authentication valid time. When the authentication valid time has passed the MFP makes a request for reissuance of an access token by performing processing which will be described later with reference to . The site A transmits to the relay server an access token and a refresh token in response to the polling immediately after the issuance of the right of use step . The relay server transmits the access token and the refresh token to the MFP that is waiting for authentication and the MFP acquires the access token and the refresh token step . The MFP stores the access token and the refresh token acquired in step in a storage management area of the nonvolatile RAM step .

The refresh token is information for reissuing an access token which has a valid period. Specifically when the valid period of the access token has expired the client apparatus for example the MFP presents the refresh token to a server and the server reissues to the client apparatus an access token corresponding to the refresh token. However the issuance of the refresh token is not an essential configuration. When the valid period of the access token has expired the MFP may make a request for a new access token and the new access token which is newly created by the server may be issued.

The flow illustrated in is executed when the user issues by using the operation unit an instruction for registering the MFP with the site A or the site B . For example when the user activates an application corresponding to the site A or site B for the first time the process illustrated in is executed.

In step the CPU causes the display unit to display a screen with which the user issues an instruction for printing an InvitePage which corresponds to a service provided by the site A or the site B .

In step the CPU determines whether or not the user has issued a print instruction on the screen displayed in step . When the user has issued the print instruction printing of the InvitePage is permitted.

When it is determined in step that the printing of the InvitePage is permitted by the user the CPU issues a registration request of the API 20 to the relay server and acquires the authentication related information illustrated in step . The processing of step corresponds the processing of steps and in . The user designates beforehand whether the registration is regarding the site A or the site B . The registration request includes information indicating the site designated by the user. In this example an explanation will be provided on the assumption that the user designates the site A for registration.

In step the CPU starts measuring a time from the acquisition of the authentication related information. In step which will be described later the time measured in such a way is set as the elapsed time from the acquisition of the authentication related information.

When the authentication related information is acquired in step the CPU analyzes the acquired data using the parser function illustrated in step .

Next based on the polling control information extracted using the parser function the CPU sets a time valid for printing the InvitePage printing valid time based on the authentication related information step . The printing valid time is a time T T for example 25 minutes which is obtained by subtracting the time T for example 5 minutes which is required for the user to register the MFP with the site using the URL of the InvitePage from the authentication valid time T for example 30 minutes for an authentication URL.

The authentication valid time T is a period of time up to the expiry time of authentication processing based on the authentication related information set at the site A . The authentication valid time is included as period information in the authentication related information acquired in step and is acquired from the period information. For example even if an authentication valid time set for the site B for example 60 minutes is different from the authentication valid time set for the site A the authentication valid time is acquired from the authentication related information and therefore an authentication valid time corresponding to each site can be acquired.

Furthermore T includes the time for printing the InvitePage and the time for operating the PC by the user. The operation time of the PC is a time for accessing the URL of the InvitePage by the PC and inputting a user code and the like. The printing time varies depending on the state of the MFP for example depending on whether printing is being performed or whether there is a shortage of ink or paper . Therefore the CPU may detect the state of the MFP and T may be dynamically set according to the state.

In step the CPU generates a printing page from the information URL information and user code for generating the InvitePage extracted using the parser function in step .

In step the CPU acquires an elapsed time T which is the time elapsed from the acquisition of the authentication related information in step .

In step the CPU determines whether or not to print the InvitePage generated in step in accordance with a condition based on the acquisition of the authentication related information in step . Specifically regarding a condition that the elapsed time set in step does not exceed the printing valid time set in step time is not out a determination is made as to whether or not the condition is satisfied. Specifically when Expression 1 provided below is satisfied it is determined that time is out and the condition for printing is not satisfied accordingly. In contrast when Expression 1 is not satisfied it is determined that time is not out and the condition for printing is satisfied accordingly. 0 1

In other words a determination is made as to whether or not printing of the InvitePage and registration of the MFP time T are executable during the remaining valid time T T .

When Expression 1 is satisfied the CPU determines that the elapsed time has exceeded the printing valid time and discards the InvitePage generated in step accordingly step . Then the process returns to step and the InvitePage information is acquired again.

In step regardless of whether or not printing of the InvitePage by the MFP is possible that is even if printing is possible the InvitePage is discarded so that printing is not executed. Therefore the InvitePage whose printing valid time has passed and which cannot be used for authentication accordingly can be prevented from being printed.

At this time a registration request of the API 20 is issued again to the relay server and the authentication related information is acquired again. Therefore new URL and user code which are different from the discarded InvitePage and an InvitePage for which a new authentication valid time is set are generated in step . One of a URL and a user code needs to be new and the other may be the same as that for the previous InvitePage.

When Expression 1 is not satisfied it is determined that the elapsed time is within the printing valid time and the process proceeds to step . In step the CPU starts printing of the InvitePage by the printing unit . In step the CPU determines whether or not the printing of the InvitePage is completed. When the printing is completed the process of ends.

When it is determined in step that the printing is not completed the process proceeds to step . In step the CPU determines whether or not an error from a cause such as ink shortage or a paper jam which may not be resolved without an intervention by an operator has occurred. When it is determined in step that such an error has occurred the CPU determines whether or not the MFP has been recovered from the error state step . If no error has occurred No in step the CPU continues printing. If the MFP has not been recovered from the error No in step the CPU waits for error recovery.

In step if the CPU determines that the MFP has been recovered from the error state the process returns to the processing of setting the elapsed time in step and the processing of determining whether time is out in step . If the authentication valid time has passed the authentication related information is acquired again in step as described above.

In the case where an error occurs during printing of the InvitePage printing is therefore interrupted and time is not out when the error is resolved printing is resumed from the point before the process is interrupted in step . In contrast if time is out when the error is resolved printing of the current page is canceled and the sheet of the print medium on which printing is being performed is discharged.

According to the process illustrated in in the case where an error occurs after the start of printing when the error is resolved it is determined whether or not the elapsed time T from acquisition of the authentication related information exceeds the printing valid time T T . For example for printing of the InvitePage running out of ink a paper jam or other errors may occur. In such a case the elapsed time T from the acquisition of the authentication related information may exceed the printing valid time T T before the user completes an operation for causing the MFP to recover from the error resulting in authentication related information being invalidated. By performing the determination in step the InvitePage based on the invalidated authentication related information is prevented from being printed even if the printing of the InvitePage is possible. Therefore a print sheet and a recording material can be prevented from being wasted.

When the authentication related information is invalidated new authentication related information is automatically acquired in step without the user issuing the registration instruction again in step . Therefore the user is able to print the InvitePage within the printing valid period without issuing the registration instruction after the operation for recovery from an error.

Furthermore in determining whether or not time is out instead of T which is the authentication valid time for the authentication URL T T which takes into consideration T that is the time required to perform an operation for registering the MFP using the URL of the InvitePage is compared with the elapsed time T. For example assuming that T which is the authentication valid time of the authentication URL is 30 minutes when the elapsed time T is 29 minutes and 59 seconds there is an allowance of only one second for printing the InvitePage and for an operation on the PC by the user. However in reality the operations will not be completed in one second. Therefore in the first embodiment T T which is shorter than the above time T is set as the printing valid time. In this example it is assumed that the above time T is five minutes. However arbitrary time may be set.

In the first embodiment the determination of step is performed based on the elapsed from a reference time which is the time at which the authentication related information is acquired in step . However the determination is not limited to the above example. The printing validity time may be set in step and the determination may be made as to whether the current time is before or after the print validity time in step .

In step the MFP issues a request for album information to the relay server through the API 1000 together with the access token stored in the storage management area of the nonvolatile RAM in step of . In step the relay server converts the album information request acquired in step into an API of the site designated by the album information request and issues a request for the album information to the site.

After the permission for use is confirmed at the server of the site the server provides the album information to the relay server step . Within the site device identification information for identifying the MFP is registered in association with the account information. In step the server transmits to the relay server the device identification information corresponding to the account information together with the album information.

The relay sever converts the album information into information designated by the MFP and provides the converted information to the MFP step . The album information includes layout information which indicates the location where an image is positioned and the size of the image information file name for identifying the image and the like. Furthermore the relay server may identify the MFP as the transmission destination of the album information based on the device identification information received from the site.

In step the MFP parses the album information acquired in step and requests image data necessary for displaying the album from the site step . The request for the image data is issued by using the file name included in the album information. In response to the request for the image data the server of the site transmits the image data to the MFP step . The MFP rasterizes the image data acquired in step in accordance with the layout information included in the album information and causes the display unit to display the album.

In the example described above an access token is issued to the MFP and the access token is used when the MFP acquires an image as a printing target which is selected by the user through an operation on the MFP . However the present invention is not limited to a service in which the MFP requests an image from a site. A service in which selection of an image and instruction for printing of the image are performed through a device such as a PC or a smartphone may also be included in the present invention.

When the user utilizes such a service the user first accesses a site through a device such as a PC or a smartphone and inputs a user account managed within the site. The server of the site authenticates the user account and presents to the user images corresponding to the account. The user selects a printing target from among the presented images and issues a print instruction.

As described above the device identification information and the user account are registered with the server of the site in association with each other. In accordance with the print instruction issued by the user the server transmits a print job and the device identification information for the MFP to the relay server . The relay server identifies the MFP based on the device identification information and transmits the print job to the MFP .

Thus processing in the first embodiment and processing in the subsequent embodiments described below are not limited to a service of issuing an access token to the MFP but may be applied to various services of registering a client apparatus such as the MFP with the site. The printing target is not limited to an image but may be a document a table and the like. Furthermore when a site provides a Web email service an email may be a printing target.

As described above according to the first embodiment in the case where the elapsed time from the acquisition of the InvitePage by the MFP exceeds the printing valid time even if printing is possible by the MFP the MFP is controlled so as not to perform printing of the InvitePage. Therefore a print sheet and a recording material such as ink or toner can be prevented from being wasted by printing an invalid InvitePage.

Furthermore when printing is not performed an InvitePage is regenerated automatically. Therefore the user is able to cause a valid InvitePage to be printed easily. Regeneration of an InvitePage is not necessarily performed automatically. For example an inquiry screen for inquiring the user whether or not to perform regeneration may be displayed on the display unit of the MFP and in accordance with an instruction by the user on the screen regeneration may be performed.

In the first embodiment as illustrated in after the InvitePage is discarded in step authentication related information is reacquired in step . In a second embodiment an example is provided in which instead of reacquiring an InvitePage a user is notified that the InvitePage has been discarded.

A detailed description will be omitted for the processing which is in common with that of . When the InvitePage is discarded in step the CPU causes the display unit to display an error display for informing the user that the InvitePage will not be printed step . As an error display method a character indicating an error may be displayed or the occurrence of an error may be indicated by lighting or flashing of a light emitting diode LED or the like.

According to the process of if an authentication validity period expires due to an error occurrence during printing of the InvitePage the MFP ends the process without reacquiring authentication related information. The user may execute acquisition of the InvitePage by redisplaying a registration instruction screen in step to issue a registration instruction.

Therefore for example in case it takes a long time for error recovery it is possible to prevent the reacquisition of the authentication related information from being executed many times despite being in a state in which printing may not be performed. The user then confirms the display in step and by reissuing a registration instruction when the MFP enters a state in which execution of printing is possible the InvitePage may be printed.

In a third embodiment a configuration is illustrated in which the MFP and a server of a site are able to communicate without via the relay server . The MFP is responsible for the role that is performed by the relay server in a different embodiment. Other configuration contents are similar to those of .

First the MFP issues a registration request using an API of the site A step . In response to the registration request the site A returns the information illustrated in including the authentication URL step . The MFP analyzes acquired data using a parser and generates an InvitePage by extracting information required for generating the InvitePage. Furthermore a time at which the response was received is set as a reference time. Moreover polling control information cycle and period is acquired in the parser analysis. The MFP prints the generated InvitePage step . Then the MFP starts polling to the site step . In this example the polling is performed for 30 minutes at the longest at cycles of 5 seconds until the right of use is issued. The user connects the MFP with the URL information described in the InvitePage printed by the MFP through the PC which has a Web browsing function and causes the site A to grant the MFP the right of use step . The site A issues an access token refresh token in response to the polling performed immediately after the issuance of the right of use. The MFP stores the acquired access token refresh token step .

The processes of and provide examples in which the MFP acquires authentication related information in accordance with a user instruction for printing an InvitePage. In a fourth embodiment an example is provided in which the MFP acquires authentication related information in advance before a print instruction is performed and an InvitePage is printed in accordance with a print instruction by a user.

In step the CPU causes the display unit to display a screen with which a user issues an instruction for registration of the MFP with the site A or the site B . In step the CPU determines whether the user has issued an instruction for registration using the operating unit . When the registration instruction has been issued by the user the MFP issues a registration request to the relay server . Then an InvitePage is generated by the processing of steps to . Details of the processing of steps to are as illustrated in .

When the InvitePage is generated the CPU causes the display unit to display a screen with which the user issues an instruction for printing the InvitePage in step . Then in step the CPU determines whether or not a print instruction has been issued by the user.

When a print instruction has been issued by the user it is determined by the processing of steps and whether or not a valid period of the InvitePage has timed out. If the valid period has not timed out the printing of the InvitePage starts in step . If the valid period has timed out the InvitePage is discarded in step . The processing of steps to is as illustrated in . Furthermore the processing of steps to is similar to that in and therefore a description for the similar processing will be omitted.

When the InvitePage is discarded in step an InvitePage is regenerated in step . In step the same processing as that of steps to is executed. Furthermore if authentication related information is acquired in step as in step a reference time is set for elapsed time measurement.

In an InvitePage is generated steps to before the user issues an instruction for printing the InvitePage step . Therefore the printing may be started quickly when the user issues the instruction for printing the InvitePage.

However the valid period of the InvitePage is measured based on the acquisition of the authentication related information in step as the reference time. Therefore when there is a delay in the print instruction by the user it is determined in step that time is out.

Since the regeneration of the InvitePage is executed in the step it is possible to print a valid InvitePage even after time is out. Furthermore when it is determined that time is out the processing of steps and is not performed. That is when time is out regeneration and printing of the InvitePage is automatically performed without a print instruction being newly issued by the user. Therefore it is possible to easily print a valid InvitePage without printing an invalid InvitePage.

As described in the foregoing embodiments the MFP receives a print job with a valid period. Next an example will be provided in which printing of a print job with a valid period is prioritized over printing of a print job without a valid period.

The RAM of the MFP may also be used as a storage area for spooling print jobs. Hereinafter management by the CPU for print jobs spooled within the RAM will be described.

As described above in step of the MFP is able to acquire a validity period for example 30 minutes of a print job to print an InvitePage. Thus in a case where a print job received by the MFP includes a validity period the CPU stores the validity period as information illustrated in in the RAM .

In step the CPU determines whether or not a print job is spooled. When a print job is spooled the process proceeds to step .

In step the CPU determines whether or not a print job with a valid period is spooled. When a print job with a valid period is spooled a remaining valid time T is confirmed step . The remaining valid time is the difference between the current time and the expiry time which is illustrated in .

In step the CPU determines whether or not a print job outside a validity period is present. Specifically the determination is made based on a time T for example five minutes which is the time required to perform an operation for registering the MFP using the URL of the InvitePage and a time T for example two minutes which is the time up to the completion of the job that is currently being executed. Then when Expression 2 is satisfied it is determined that a print job outside a valid period is present. 130 Expression 2

That is it is not determined whether or not there is a remaining valid time but it is determined whether or not execution of printing of the InvitePage and registration of the MFP is possible within the remaining valid time. The time up to the completion of the job that is currently being executed may be dynamically set according to the amount of data as a printing target in the job. Furthermore when there is no job that is currently being executed the time may be set to zero minutes .

For example in the case of the job ID the remaining valid time T is calculated as fifteen minutes based on the relationship between the current time and the expiry time. Thus since Expression 2 is not satisfied the print job corresponding to the job ID is determined to be within the validity period. In contrast in the case of the job ID the remaining valid time T is calculated as five minutes based on the relationship between the current time and the expiry time. Thus Expression 2 is satisfied. Therefore the print job corresponding to the job ID is determined to be outside the validity period.

In step the CPU sets the print job that is determined to be outside the validity period in step at the top level printing order of the printing order in the list illustrated in . Incidentally if there are multiple jobs outside the validity period a job whose printing order is the earliest is set at the top level.

In step the CPU regenerates an InvitePage. This processing is similar to the processing of steps to in .

On the other hand when it is determined in step that there is no print job outside the validity period the print job with a valid period is set at the top level of the printing order. When there are multiple print jobs with a valid period a job whose printing order is the earliest is set at the top level or a job whose expiry time is the earliest is set at the top level step S .

In step the CPU causes the printing unit to execute printing in accordance with the print job at the top level of the printing order.

As described above the print job of the InvitePage that is managed in the spooler is printed preferentially over print jobs with no validity period. Therefore it is possible to reduce the chance of executing reacquisition of InvitePage information and to effectively utilize the InvitePage information that has already been acquired.

In the example of the print job outside the valid period is set at the top level. However since the valid period is updated by regeneration of the InvitePage another print job within the valid period may be printed preferentially over the print job outside the valid period.

Next an example in which after InvitePages corresponding to all the print jobs outside the valid period are regenerated the printing order is rearranged in the order of closeness to the expiry time will be described.

In step when it is determined that a print job outside the valid period is present the process proceeds to step . In step InvitePages for all the print jobs outside the valid period are regenerated. For the processing of regenerating the InvitePages the processing of steps to in is executed for each print job. When the regeneration of the InvitePages is completed the process proceeds to step .

In step the CPU changes the printing order of the print jobs in the order of closeness to the expiry time. The priority of a job without a valid period is lower than a job with a valid period. Furthermore when multiple jobs without a valid period are present the priority level in the printing order before the rearrangement is maintained.

By the above processing the print job of ID which is outside the valid period is replaced with a reacquired print job and the time up to the expiry time becomes longer. After the time up to the expiry time is extended in this way a change in the printing order is executed in step .

Then as is clear from the print job of the job ID has been changed into the top level of the printing order. In other words in the state of which is before the change the expiry time of the print job of the job ID is earlier than the expiry time of the print job of the job ID . However by the regeneration of the InvitePage the expiry time of the job ID becomes later. Therefore the job ID is prioritized.

In the fifth embodiment the spooler is described with a configuration using a storage area inside the MFP . However the spooler may be located in an external area on the network.

Prior to execution of printing the MFP may perform a recovery operation of the recording head included in the printing unit . An example of the recovery operation includes suction of ink adhered to the recording head. A specific length of time is required to execute a recovery operation. Therefore the validity of printing of an InvitePage may differ depending on the presence or absence of the recovery operation.

Furthermore the MFP may be in an exclusive state by control other than the printing of an InvitePage. In such a case the printing of the InvitePage may not be performed immediately. Therefore the validity of the printing of the InvitePage may differ depending on whether or not the MFP is in the exclusive state.

Therefore in a sixth embodiment a process for re determining whether or not printing of an InvitePage is valid is executed when the MFP is in the exclusive state at the time of printing or when the MFP performs a recovery operation.

When it is determined in step that the printing of the InvitePage has not timed out is valid or when an InvitePage is regenerated in step the process proceeds to step .

In step the CPU determines whether or not the MFP is in the exclusive state. When the MFP is not in the exclusive state the CPU determines whether or not to perform a recovery operation in the printing in step .

When the determination result in step or step is Yes the process proceeds to step . In step the CPU resets a printing valid time.

For example it is assumed that the authentication valid time of a site is represented by T and the time required for a user to perform an operation for registering the MFP using the URL of the InvitePage is represented by T . In addition it is assumed that the time for transition from the exclusive state to a normal state is represented by T and the time required for the recovery operation is represented by T .

In step for example when it is determined in step that the MFP is in the exclusive state the CPU subtracts the T from the printing valid time. For example if the printing valid time is represented by T T in step the time represented by T T is set as a new printing valid time.

On the other hand when it is determined in step that a recovery operation is to be performed the time T is subtracted from the printing valid time. For example if the printing valid time is represented by T T in step the time represented by T T T is set as a new printing valid time.

When determination results of both step and step are Yes the time represented by T T T T is set in step . However in this case the processing of step is executed twice. Therefore for example by performing the processing of step and step in one determination process a single subtraction processing may be performed by selecting from among the times T T and T T the time to be subtracted from the printing valid time in accordance with the determination result.

In step it is determined by comparing the printing valid time which has been reset in step with the elapsed time whether or not the printing of the InvitePage has timed out.

Ink suction of the recording head has been described as an example of a recovery operation. However a recovery operation is not limited to this but may be various maintenance operations. For example for sheet printing and reading for registration adjustment to adjust the timing to eject ink from the recording head the time required for the maintenance operation may be subtracted from the printing valid time similarly to the recovery operation. In the case where the time required differs depending on the type of recovery operation and maintenance operation the time corresponding to the type may be subtracted from the printing valid time.

According to the process of described above the determination as to whether or not time is out is performed by subtracting the time required for the recovery operation or for recovering from the exclusive state from the printing valid time. With such a determination it may be appropriately determined whether or not the printing of the InvitePage is valid an invalid InvitePage may be prevented from being printed and a valid InvitePage may be printed.

In the foregoing embodiments the validity of the printing of an InvitePage is determined based on a printing valid time.

In a seventh embodiment instead of the printing valid time a determination is made as to whether or not a delay event which delays the start of printing has occurred or whether or not an error has occurred during a printing operation. In accordance with the determination result discarding and regeneration of an InvitePage is performed.

When an instruction for printing an InvitePage is input by a user in step the CPU determines whether or not a delay event is occurring in step . A delay event is processing which occurs before execution of a print job. Specifically a delay event is a recovery operation for performing suction of ink or registration adjustment.

When it is determined in step that a delay event is occurring the CPU determines whether or not the delay event has been resolved in step . When it is determined that the delay event has been resolved discarding and regeneration of the InvitePage is executed.

Furthermore in step it is determined whether or not an error such as running out of ink running out of paper or a paper jam has occurred during printing. After the error has been resolved discarding and regeneration of the InvitePage is executed.

That is in the seventh embodiment in accordance with the presence or absence of a factor for delaying the completion of printing a delay event before printing or an error occurring during printing the validity of the printing of the InvitePage is determined. Therefore compared to the case in which the above determination is performed based on a printing valid time it is easier to perform the determination.

Furthermore for example in the case of a delay event such as a recovery operation or waiting for completion of another print job it is comparatively easy to predict the time for the delay event to be resolved by the MFP . Therefore in the case of such a delay event the determination may be performed based on a printing valid time. In contrast an error such as recovering from the exclusive state shortage of ink running out of paper or a paper jam may not be resolved without user intervention. Therefore it is comparatively difficult to predict the time for such an event to be resolved. Thus in the case of the occurrence of such an event the discarding and regeneration of the InvitePage may be performed regardless of the printing valid time as illustrated in .

In the foregoing embodiments a photo sharing site has been described as an example of a service provided by a server on the Web. However a service provided by a server is not limited to this. For example a cloud print service may be provided. In the cloud print service when a user issues a print instruction using a device such as a PC or a smartphone connected to the Internet an MFP is notified of the print instruction via a server that provides the service. Upon receiving the print instruction the MFP executes printing. In addition print data may be transmitted along with the print instruction to the MFP and the MFP may print the print data. Alternatively the MFP may be notified of information indicating the storage location of the print data URL or the like as a print instruction and the MFP may acquire the print data based on the information.

Furthermore a service provided by a site may be a storage service which stores various data such as documents images tables and graphs. Alternatively a Web email service or a social network service SNS may be provided by a site.

Furthermore the relay server and a server of a site may each be constructed as a single server or may each be a server system including multiple servers. In the case of a server system including multiple servers a server may be allocated to each function or multiple servers having a common function may be provided.

Furthermore if the valid period of the URL of an authentication page expires in the foregoing embodiments authentication using the URL is prohibited in the site. As a prohibiting method the access itself according to the URL may be prohibited or an error display may be executed after the access is made.

Furthermore in the foregoing embodiments as a print control device which performs print control processing the case where the CPU of the printing apparatus operates has been explained as an example. However the present invention is not limited to this. An external device which is connected to the printing apparatus may operate as a print control device according to an embodiment of the present invention. In such a case the external device may be various devices such as a PC a smartphone and a tablet.

In the foregoing embodiments an example in which a client apparatus accesses a server on the Web via the Internet has been described. However the present invention is not limited to this. For example the client apparatus may access a server on a LAN. In such a case access information may be folder path information for example instead of a URL.

Embodiments of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present invention and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a central processing unit CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

Furthermore a program code for implementing functions of an embodiment may be executed by a single computer a CPU or a microprocessing unit MPU or may be executed by multiple computers which cooperate with each other. Furthermore a program code may be executed by a computer or hardware such as a circuit for implementing the functions of the program code may be provided. Furthermore part of the program code may be implemented by hardware and the other parts may be executed by a computer.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2014 127489 filed Jun. 20 2014 which is hereby incorporated by reference herein in its entirety.


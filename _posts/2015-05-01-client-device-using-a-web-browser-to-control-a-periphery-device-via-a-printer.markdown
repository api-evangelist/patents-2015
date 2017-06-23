---

title: Client device using a web browser to control a periphery device via a printer
abstract: A device control system has a terminal  with a web browser , and a printer  that controls a connected device. The terminal  calls an object that controls a device and is instantiated by the device API  to support the device, and sends a request to the printer , by the web application ; and the printer  executes a device control script  that controls the device, receives requests sent through the device API , and controls the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09274730&OS=09274730&RS=09274730
owner: Seiko Epson Corporation
number: 09274730
owner_city: Tokyo
owner_country: JP
publication_date: 20150501
---
This application is a continuation of and claims priority under 35 U.S.C. 120 on application Ser. No. 14 140 268 filed Dec. 24 2013 which claims priority under 35 U.S.C. 119 e on provisional application No. 61 748 232 filed Jan. 2 2013. The content of each such related application is incorporated by reference herein in its entirety.

The present invention relates to a device control system that controls a device a printer and a control method of the device control system.

A device such as a computer used as a controller for controlling devices is conventionally part of a system that controls devices such as a keyboard and barcode scanner by means of a terminal connected to a network.

The present invention is directed to the foregoing problem and an object of the invention is to provide a device control system a printer and a control method of a device control system that can control devices by a terminal connected to a network.

To achieve the foregoing object a device control system according to the invention has a device a device control device including a connection unit configured to connect to the device and a device control unit configured to control the device connected to the connection unit and a terminal that runs a web browser executing a device application programming interface that connects to the device control device displays a web application and controls the device.

The invention enables controlling a device connected to a device control device through the web browser of a terminal.

In the invention the device application programming interface has an object that supports the device and the web application calls the object and sends a request to the device control device.

In another aspect of the invention the device control device executes a device control script that controls the device and the device control script connects to the object receives the request sent by the terminal and controls the device connected to the connection unit.

In another aspect of the invention the device control script has a device connection object that sends and receives data with the device and a client connection object that sends data to the device API.

In another aspect of the invention the request is a start control request specifying the device connected to the device control device and instructing starting control of the device the command is a start control command instructing starting control of the device and when the terminal sends the start control request to the device control device the device control device sends the start control command to the device specified by the start control request and enables control of the device by the terminal.

Another aspect of the invention also has a second terminal running a web browser that executes a second device application programming interface that connects to the device control device displays a second web application and controls the device the second the device application programming interface having a second object that supports the device.

In another aspect of the invention when the device can be controlled by the terminal the device control device exclusively locks the device and if the second web application calls the second object and sends a second request to the device control device does not allow control of the device in the second request.

In another aspect of the invention if the second terminal sends the second request to the device control device when the device can be controlled by the terminal the device control device sends a report indicating the device is busy to the second terminal.

In another aspect of the invention the device is a printer configured to print and if the second terminal sends the second request to the device control device when the printer can be controlled by the terminal the device control device enables the second terminal to control the printer by the device control script based on the second request.

In another aspect of the invention the web application of the terminal calls the object and sends a stop control request specifying the device and instructing ending control of the device to the device control device and when the terminal sends the stop control request to the device control device the device control device sends a second command instructing stopping control by the device control script to the device specified by the stop control request and stops control of the device by the terminal.

In another aspect of the invention when the second terminal sends the second request to the device control device after the device control device stops control of the device by the terminal the device control device enables control by the second terminal of the device by the device control script based on the second request.

In another aspect of the invention the device application programming interface detects connection of the object and the device control script of the device control device.

In another aspect of the invention the device is a display configured to display content the request is a display request that specifies the display and requests displaying content on the display and when the terminal sends the display request to the device control device the device control device sends a display command requesting display by the device control script to the display specified by the display request.

In another aspect of the invention the request is a registration request that specifies the device and requests registering image data in the device and when the terminal sends the registration request to the device control device the device control device sends a registration command instructing registering the image by the device control script to the device specified by the registration request.

The terminal also sends the image data to the device control device and the device control script converts the image data to the raster image data.

The request is also an encryption request that specifies the device and instructs whether or not to encrypt data sent and received between the device and the terminal.

Another aspect of the invention is a printer including a connection unit configured to connect to a device a device control unit configured to execute a device control script that controls a device and to control the device connected to the connection unit and a print unit configured to print.

Another aspect of the invention is a control method of a device control system including a terminal that runs a web browser a device and a device control device configured to connect to the device calling an object supporting the device by a web application that runs on the web browser sending a request to the device control device executing a device control script that controls the device by the device control device sending to the device a command that controls the device by the device control script based on the request received by the device control device and establishing control of the device by the terminal.

The request is a start control request specifying the device connected to the device control device and instructing starting control of the device and when the terminal sends the start control request to the device control device the device control device sends the control command to the device and starts control of the device by the terminal.

A preferred embodiment of the invention is described below with reference to the accompanying figures.

The device control system includes the application server a terminal and a printer intelligent printer . In this device control system the application server terminal and printer are connected over a communication network. In the example shown in the device control system has a wireless LAN access point and the application server printer and wireless LAN access point are connected by a wired LAN. The wireless LAN access point connects the terminal to the wired LAN. The terminal can therefore be used anywhere within communication range of the wireless LAN access point .

A network printer customer display and barcode scanner are connected to the printer as controlled devices. The network printer is connected to the printer through a network. The customer display and barcode scanner are connected through a USB interface described below. These devices are generally called peripheral devices peripherals and are referred to below as devices.

Devices that connect to the printer are not limited to the devices shown in . For example displays and key input devices such as keyboards are also included. Also included are devices that can be controlled by a HID human interface device driver standard to the OS serial communication devices that can be operated using a serial communication driver standard to the OS and USB devices that can be controlled in the same way as serial communication devices.

The terminal has a network connectable web browser and devices connected to the printer can be controlled through this web browser.

The terminal can be any terminal with a network connectable web browser and a tablet computer known from the literature such as shown in can be used. A separate device such as a computer used as a controller for controlling the devices does not to be included in the device control system .

 4 The printer receives the request message. Based on the received request message the printer sends data to a device that can be controlled by the printer .

 4 The printer receives the request message. Based on the received request message the printer sends data to a device that can be controlled by the printer .

Ina system applying the invention a terminal with an installed web browser can thus display a web application and control a device connected to the printer .

The printer has a CPU RAM flash ROM nonvolatile memory a video controller an auxiliary storage device SSD solid state drive interface and a local printer print unit . The printer could also have a speaker. The local printer is a thermal printer that can print on 80 mm wide or 58 mm wide roll paper.

The printer can be installed in a POS point of sale system. The operating system OS of the printer is Windows R based for example and is stored in the auxiliary storage device.

A device control program which is software for the terminal to control devices connected to the printer is installed to the printer . As a result installing a driver program to the terminal is not necessary.

The printer also has a Windows R standard device driver program APD UPOS driver OPOS driver or other software for controlling devices and the local printer of the printer .

A web application can be installed to the printer . This enables using the printer as an application server as shown in . The web application could for example be a PHP and Perl server side script or SQLite database access script server side script .

The foregoing network printer customer display and barcode scanner can be connected to the printer . A display cash drawer and keyboard can also be connected to the printer . shows the external appearance of the printer .

A roll paper cover is disposed to the top of the printer . The roll paper cover opens when the cover open button is pressed and roll paper can be loaded. A manual cutter for manually cutting the roll paper and a cutter cover are disposed to the paper exit from which the roll paper is discharged after printing. The cutter cover is opened when a paper jam occurs in the local printer of the printer and when the roll paper cover does not open. The blade of the manual cutter returns to the home position when the cutter cover opens. The printer also has a power switch B reset button A LED display unit and control panel . The LED display unit includes a disc access LED indicating accessing the auxiliary storage device and status LEDs. The status LEDs report the operating state of the OS the standby mode of the OS that the power is off the OS start up sequence and a high CPU temperature warning.

The control panel includes a power LED error LED roll paper LED and paper feed button. The power LED lights when power is supplied. The error LED is off during normal operation and lights when the printer resets and when the end of the roll paper is detected and printing stops. The paper LED is off when sufficient roll paper remains lights steady when little paper is left and blinks when the self diagnostic test is running. Pressing the feed button advances the roll paper one line at a time or continuously.

A connector cover is disposed to the back of the printer . Removing the connector cover exposes the connector panel connection panel on the back of the printer .

The cash drawer or an optional buzzer is connected to the drawer kick out connector . The Ethernet connector is connected to the network. The USB connector has six USB ports. The customer display barcode scanner keyboard and other devices are connected to the USB connector . The display is connected to the VGA connector . A serial interface for serial communication devices connects to the COM connector . The line output connects to an external speaker.

An embodiment of the invention is described in detail below using the device control system as an example.

The web browser of the terminal displays a web application provided by the application server . The web application calls a device application programming interface API of the web browser . The device API is for example a Java R script and as described below instantiates an object that controls a device connected to the printer . The web application calls APICall an object of the device API . The device API sends a request Request to the printer by a function of the called object.

The device service interface of the printer receives the request and controls a device control script . The device control script controls a key input device and serial communication device . The device control script acquires data input by the key input device and outputs data to the device service interface . The device control script handles data communication with the serial communication device and outputs data received from the serial communication device to the device service interface . The key input device in this example includes the keyboard and the serial communication devices include the barcode scanner and cash drawer .

The device service interface exchanges data with the local printer . The local printer is the local print unit of the printer . The device service interface also exchanges data with the network printer and customer display . The device service interface outputs device events Event and device responses Response to the device API . The device API outputs a response Callback to the web application .

A terminal controls a device connected to a printer in the device control system by the operation described above.

The invention is thus used to control devices peripherals connected to a printer in a multi platform environment. By using this system devices can be controlled using a personal computer smartphone or tablet computer in which a web browser is installed.

Configure the system and printer network. These settings can be made using the same procedure used for configuring a windows R network.

The printer can function as a web server to register web content. The registered web content can be viewed from the web browser of the terminal .

The registered web content is compressed to a single file in ZIP format containing all content files. The name of the ZIP file can be specified as desired. The ZIP file name and subfolder names are written using ASCII characters.

Web content cannot be appended and all files are registered by overwriting the old files. When accessing web content registered in the printer from the terminal for example the URL that is accessed differs according to the folder structure of the ZIP file. Specific examples are shown in and .

Connect a device to the printer . As described above connectable devices include the customer display barcode scanner display cash drawer and keyboard . Also included are devices that can be controlled by a HID driver standard to the OS serial communication devices that can be operated using a serial communication driver standard to the OS and USB devices that can be controlled in the same way as serial communication devices. The connection panel in shows only one COM connector but plural serial communication devices can be connected if a serial USB conversion cable is used and the driver program is compatible with serial USB conversions.

A device control script prepared by the user is registered in order for the printer to control devices other than products with which the printer is compatible. Registration is done from the web browser.

Register the device connected to the printer in the printer software. Registration is done from the web browser.

The web content registration file is registered by the web browser displaying the TMNetWebConfig utility as shown in .

 4 The TMNetWebConfig utility starts. Click on Web service settings Update settings in the window shown in .

 5 The Web Content Update Settings screen is displayed. Click on Browse in the web content file field and select the ZIP file containing the web content that was prepared in step 1 .

The device control script prepared by the user is registered by the web browser displaying the TMNetWebConfig tool as shown in . This method enables the user to connect a prepared device to the printer and control the device and enables the user to develop and register a device control script to customize device data processing.

 4 Start the TMNetWebConfig utility. Click on Web service settings Register delete in the window shown in .

 5 The Control Script screen is displayed. Click on Browse in the Control script to be registered field and select the device control script to register.

 6 Click Register . The device control script is registered and listed in the Registered control scripts field in the bottom of the window.

 2 Start the TMNetWebConfig utility. From Web service settings Device registration in the window shown in click on the type of device to register. A device list is displayed under Device registration in the screen shown in . Click on the type of device to register from the device list . The type of device in this embodiment can be selected from five types printer display key input device serial communication device and other as shown in . Details about the types of devices are as shown in .

 3 A configuration screen is displayed for each device. The connected device is registered in the printer .

 3 1 1 Check that printer is registered for the device ID local printer in the Registered Printer field in the screen shown in .

 3 1 3 1 Set the items shown in device ID type model number IP address retry interval and click Register .

 3 1 3 2 After confirming the printer is added to the Registered Printer list click Test printing . Confirm that TEST PRINT is printed by the registered network printer .

The device ID of the customer display is a constant local display . Register the connected customer display by the following steps.

 3 3 2 After confirming the registered device was added to the Registered Key Input Device field click Operating test .

 3 3 3 A screen will be displayed by the web browser. Operate the key input device and confirm that the result is displayed as operated.

 3 4 1 Set the items device ID device name control script communication speed data bit parity stop bit flow control shown in for the connected serial communication device and click Register .

The device API is provided to enable using the device control function of this system from a client side JavaScript. The device API is written in JavaScript. An example of a filename is device .js.

Applications in corresponds to a web application Device Control corresponds to a device control function device API and device service interface and Device denotes the controlled device.

2 Web application sends the Connect command and establishes a communication path to the device control function.

Specifies the callback that receives the process result. A string shown in is returned in the first parameter of the callback.

When this method executes successfully the specified device is exclusively locked and DEVICE IN USE is returned when createDevice is called from another browser. Because the printer is not exclusively locked a device object can be obtained by createDevice from plural browsers.

If createDevice is executed immediately during a return process after an ondisconnect event DEVICE IN USE is returned. In this event the createDevice method retries until a value other than DEVICE IN USE is obtained.

Specifies the callback that receives the process result. If the second parameter of the callback is OK the device object is returned in the first parameter. The second parameter is a string shown in .

Specifies the callback that receives the process result. The parameter of the callback is a string shown in .

Obtains the administrator set in the printer . The administrator can be set using the TMNetWebConfig utility.

Gets the installation location value set in the printer . The location string can be set using the TMNetWebConfig utility.

Obtains failure of the reconnect process. When this event occurs a process for handling the network disconnection such as establishing a connection again is executed.

Calls any event on the device control script side corresponding to the device object. Details about device control script events are described below in the description of the device control script .

Adds the initialization settings of the customer display to the command buffer. Initialization results in the following.

Adds window settings to the command buffer. Windows are defined to not overlap previously defined windows. A window size that fits in the size of the display 20 columns 20 rows is specified.

Adds a setting to change the current window to the command buffer. Makes the specified window the current window and then moves the cursor to the origin of the current window.

Adds a marquee display to the command buffer. The marquee is displayed in the horizontal scroll mode on one line regardless of the scroll mode setting of the display window.

Specifies the number of times to repeat the string display. A value from 0 to 127 can be set. Display repeats indefinitely if 0 is specified.

Specifies the blinking interval ms . Specify a number from 0 to 12700. The specified setting is rounded in 50 ms increments. The display lights steady when 0 is specified.

When the clock is displayed all displayed strings are cleared. Clock display ends if another command is sent while the clock is displayed.

Receives the result of command execution. The properties shown in are included. Success values are shown in code values are shown in .

Specifies the key code used to detect the beginning of a string when keyboard input is received as a batch of strings.

Receives a string of character input starting with any character combination specified by setPrefix and ending when the Enter key is detected.

To set text rotation when the print mode is set to the page mode use the addPageDirection method described below instead of this API.

To set text rotation when the print mode is set to the page mode use the addPageDirection method described below instead of this API.

In the page mode characters are printed from the current character position referenced to the baseline dot of the character see appendix on page .

lang Required parameter object type String Specifies the target language as shown in . The printable character codes depend upon the printer specifications.

When both dw and dh parameters are set to ture double width and double height characters are printed. Settings are shown in .

Converts the specified range in a RGBA full color HTML5 Canvas image to raster image data according to the halftone property and brightness property settings. One pixel in an image equals one printer dot. When an image includes a transparent color the background of the image is assumed to be white.

To print a raster image at high speed specify ALIGN LEFT for the addTextAlign method described above and set the width parameter of this API to a multiple of 8 not exceeding the paper width of the printer.

Inpagemode a raster image is printed at the current print position referenced to the bottom left dot of the raster image. The print position does not move.

HTML5 Canvas images containing images downloaded from a different domain cannot be printed. A security error is returned in accordance with JavaScript s same origin policy.

The logo is previously registered in the printer using a model specific utility or a logo registration utility TMFLogo .

In page mode a logo is printed from the current printing position referenced to the bottom left dot of the logo.

In page mode the barcode is printed fromthe current print position referenced to the bottom left dot except for HRI of the barcode.

In page mode the barcode is printed from the current printing position referenced to the bottom left dot of the 2D symbol.

Specifies an escape sequence shown in to pass binary data that cannot be expressed by a character string.

The error correction level is selected according to the type of two dimensional symbol. LEVEL DEFAULT is selected for MaxiCode and two dimensional GS1DataBar symbols.

Specifies the module width. Specify an integer from 0 to 255. This parameter is ignored for MaxiCode symbols.

Specifies the module height. Specify an integer from 0 to 255. This parameter is ignored for QRCode and MaxiCode symbols.

Specifies the maximum size of the two dimensional symbol. Specify an integer from 0 to 65535. This parameter is ignored for QRCode and MaxiCode symbols.

Adds horizontal line printing to the command buffer. Draws horizontal lines. Cannot be used in page mode.

Adds the beginning of a vertical line to the command buffer. Starts drawing vertical lines. Cannot be used in page mode. Vertical lines are drawn until the end is specified by addVLineEnd. This API function is used together with the addVLineEnd method.

Adds the end of a vertical line to the command buffer. Finishes drawing vertical lines. Cannot be used in page mode. This API is used together with the addVLineBegin method described above.

Vertical lines are processed in page mode until the page mode is ended by the PageEnd method described below. This API is used together with the PageEnd method.

Adds the end of the page mode to the command buffer. Processing in page mode ends. This API is used together with the addPageBegin method described above.

Adds the page mode print area to the command buffer. Specifies the page mode print area coordinates . After this API function specify a print data API function such as the addText method.

The print area is specified according to the content to be printed. If the print data extends beyond the print area the print data will not be completely printed in the printout. This API is used between the above addPageBegin method and the above PageEnd method.

Specifies the origin of the horizontal axis in dots . Specify an integer from 0 to 65535. 0 is at the left edge of the printable area of the printer.

Specifies the origin of the vertical axis in dots . Specify an integer from 0 to 65535. 0 is the position without feeding the paper.

The width and height of the print area are determined according to the print direction setting. The print data may otherwise not be completely printed.

Adds the page mode print direction setting to the command buffer. Specifies the print direction in page mode. This function can be omitted if rotation is not required. This API is used between the above addPageBegin method and the PageEnd method.

Adds the print position setting area in the page mode to the command buffer. Specifies the print start position coordinates in the area specified by the addPageArea method. This API is used between the above addPageBegin method and the PageEnd method.

The print start position coordinates is set according to the content to be printed. Refer to the following.

Specify the left end of the baseline for the first character. This can be omitted for left aligned printing of standard sized characters. To print double sized height characters specify a value equal to or greater than 42 for y.

Adds line drawing in page mode to the command buffer. Draws a line in page mode. Diagonal lines cannot be drawn. This API is used between the above addPageBegin method and the PageEnd method.

Adds drawing a rectangle in the page mode. Draws a rectangle in the page mode. This API is used between the above addPageBegin method and the PageEnd method.

Adds a drawer kick to the command buffer. Sets the drawer kick. Cannot be used in page mode. The drawer cannot be used with the buzzer.

To stop the buzzer after setting the repeat parameter to 0 execute this API again and set the pattern parameter to PATTERN NONE.

When sending a command to the command buffer with the addCommand method declare the command data strings using Ix as a separator.

Converts the specified range in a RGBA full color HTML5 Canvas image to raster image data according to the halftone property and brightness property settings. One image pixel equals one printer dot. When an image contains a transparent color the background color of the image is assumed to be white.

HTML5 Canvas images containing images downloaded from a different domain cannot be printed. A security error is returned in accordance with JavaScript s same origin policy.

Enables a status event. Reports the printer status as an event. Updates the status at the interval specified in the interval property.

Specifies the halftone processing method to apply to monochrome two tone printing. The default is HALFTONE DITHER.

Specifies the timeout time ms of the message sent with the send method described above. The default value is 10 000.

By using a device control script provided by the device control function of the invention data processing by a device can be customized and new devices can be used from a web application. As shown in a device control script has a DeviceConnection object and a ClientConnection object . In devices of the printer are collectively referred to as device .

When the createDevice method of the Device object described above is executed an object is instantiated so that the device service interface of the printer can use the device control script corresponding to the requested device. The device can then be controlled through the instantiated object.

The objects shown in are then passed to the device control script from the device service interface . By using the DeviceConnection object and ClientConnection object the device control script can communicate with the web application and device as shown in . The DeviceConnection object is an object that sends receives data with the device . The ClientConnection object is an object that sends data to a device object on the web browser side and accesses the device service interface .

An example is shown in . In this example the onkeypress event of the device object is called and 49 is received from data.keycode and 1 is received from data.ascii using the data parameter of the onkeypress event.

This event is used to receive the results of API execution by a device object that runs on a browser.

The sample program described below enables use as a POS system. Sample code for a device API can be created for each device.

If the Windows Security screen appears while using the TMNet TMNetWebConfig utility enter your username and password.

3. The Web content update settings screen is displayed as shown in the frame on the right side of . Click on Browse indicated by in and select the sample program.

2. The customer display settings screen shown in is displayed. Select Use indicated by in and click the Apply button. There is no need to change the settings in this example.

3. The Key Input device screen shown in is displayed. Set the Device ID Device name and Control script for each device in the appropriate places indicated by in and click the Registration button. Sample settings are shown in . Register one device at a time.

1. Start the web browser and enter the IP address of the printer to the address bar. The default IP address of the printer is 192.168.192.168 .

2. The sample program is displayed. An example of the display is shown in . If the sample program is not displayed check if the LAN cable is connected.

The sample program includes the following items. Selecting an item goes to the corresponding screen. Details of each sample are described below.

This sample program enables operating the customer display and generating sample code for the customer display.

2. The Customer Display Sample screen shown in is displayed. Click the Connect button in this screen. If connection is successful the following message will be displayed in the Console frame. The display on the customer display will also change.

There is no need to change the settings in the Device Setting frame. However if the IP address for example has changed change the setting in the Device Setting frame accordingly.

4. The source code of the function added in step 3 is displayed in the Display Object Sample Code frame in . This code can be copied and reused.

5. When the Send button in the screen in is clicked the screen display will change according to the function added in step 3.

2. The Keyboard Sample screen shown in is displayed. Click the Connect button. If connection is successful the following message will be displayed in the Console frame.

There is no need to change the settings in the Device Setting frame. However if the IP address for example has changed change the setting in the Device Setting frame accordingly.

4. When there is input from the POS keyboard the input result is displayed in the ePOS Device API Keyboard Object shown in . An example of input and the result is shown in .

2. The Printer Sample screen in is displayed. Click the Connect button. If connection is successful the following message will be displayed in the Console frame.

There is no need to change the settings in the Device Setting frame. However if the IP address for example has changed change the setting in the Device Setting frame accordingly.

4. The source code of the function added in step 3 is displayed in the printer Print API Sample Code frame in . This code can be copied and reused.

5. When the Send button in the screen is clicked a test print will be printed according to the function added in step 3.

2. The Barcode Scanner Sample screen in is displayed. Click the Connect button. If connection is successful the following message will be displayed in the Console frame.

There is no need to change the settings in the Device Setting frame. However if the IP address for example has changed change the setting in the Device Setting frame accordingly.

3. When there is input from the barcode scanner the read information is displayed in the ePOS Device API Scanner Object shown in .

Preparation is required first. In this preparation start the sample program and configure each device.

3. The Settings screen in is displayed. The IP address port and device ID can be set in this screen. If a setting is changed click the Connect button and confirm that the status is OK. After confirmation close the window. Note that there is usually no need to change a setting.

2. Enter the amount received in the screen shown in . Click the Ent button after entering the amount.

As described above a device control system according to this embodiment of the invention has an application server that serves a web application a terminal that is connected to the application server through a network and has a web browser that displays the web application and a printer that has a connection panel to which a device connects and controls the device connected to the connection panel . By means of the web application the terminal calls an object that controls a device and is instantiated by the device API to support the device and sends a request to the printer by the web application and the printer executes a device control script that controls the device receives requests sent through the device API and controls the device connected to the connection panel .

The invention is not limited to device control system and device control systems can be similarly configured. In device control system the printer has the functions of the application server .

In device control system the device control script has a DeviceConnection object that sends receives data with a device and a ClientConnection object that sends data to the device control API.

In device control system the terminal specifies a device connected to the printer and sends a request to start control of the device to the printer and the printer sends a command by the device control script to the device specified by the request and enables controlling the device.

When the device control system has a first terminal and a second terminal the first terminal specifies a device connected to the printer sends a request to start control of the device to the printer and the printer enables controlling the device specified in the request the device is exclusively locked and cannot be controlled by a request sent by the second terminal .

In this configuration the printer reports to the second terminal that the device is busy when the second terminal calls an object corresponding to the device of the device API .

In the device control system the device connected to the printer is a local printer or a network printer and when the printer enables control of the device specified by the request the local printer or the network printer can be controlled by the device control script according to the request sent by the second terminal .

In the device control system the terminal specifies a device connected to the printer and sends a request instructing ending device control to the printer and the printer sends a command by the device control script to the device specified by the request and terminates the state enabling control of the device.

In the device control system the terminal specifies a device connected to the printer and sends a request instructing ending device control to the printer the printer sends a command by the device control script to the device specified by the request and terminates the state enabling control of the device and the device can be controlled by the printer in response to a request sent by the second terminal .

In the device control system the terminal detects the connection status of an object instantiated by the device API and the device control script of the printer by means of the device API .

In the device control system the terminal controls an object of the device API by the web application and calls an event of the device control script .

In the device control system a customer display is connected to the printer as a device the terminal sends a request to display on the customer display and the printer controls displaying on the customer display by the device control script in response to the request.

In the device control system a customer display is connected to the printer as a device the terminal sends a request to display on the customer display and the printer displays the time on the customer display by the device control script in response to the request and stops displaying the time when a second request is sent while the time is displayed.

In the device control system a printer is connected to printer as a device the terminal sends a request to register image data in the printer by an object of the device control API the printer registers the image data in the printer specified by the request and the printer prints the registered image data.

In the device control system color image data rendered by HTML5 Canvas is converted to raster image data and registered in the printer according to a request sent by the terminal .

In the device control system the terminal specifies a device and sends a request instructing whether or not to encrypt data sent and received between the device and the terminal by an object of the device control API.

The terminal has an application server that serves a web application and a connection panel to which devices connect is connected through a network to a printer that controls a device connected to the connection panel has a web browser that displays a web application and through the web application calls an object that controls a device and is instantiated by the device API to support the device sends a request to the printer and causes the printer to execute a device control script that controls the device.

The foregoing embodiment obviously describes one example of the invention and can be modified and adapted as desired within the scope of the accompanying claims.


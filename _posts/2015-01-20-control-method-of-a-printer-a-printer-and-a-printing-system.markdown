---

title: Control method of a printer, a printer, and a printing system
abstract: A printer, a control method of a printer, and a control system enable a printer to efficiently inform a control device that cancelling a print job was instructed by operation of an operating unit. The printer detects if a cancel button was operated, stores button operation information indicating if the cancel button was operated based on the detection result, and if a status response request is received from a host computer, adds and returns button operation information in status information indicating the requested status.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09442685&OS=09442685&RS=09442685
owner: Seiko Epson Corporation
number: 09442685
owner_city: Tokyo
owner_country: JP
publication_date: 20150120
---
Priority is claimed under 35 U.S.C. 119 to Japanese Application No. 2014 189613 filed on Sep. 18 2014 and Japanese Application No. 2014 006769 filed on Jan. 17 2104 which are hereby incorporated by reference in their entireties.

The present disclosure relates to a method of controlling a printer that prints a printer and a printing system.

Control systems in which a control device host device and a printing device printer communicate and the printer prints as controlled by the control device are known. See for example JP A 2006 123318. Printers that have an operating unit operated by the user to cancel a print job and cancel a print job in progress when the operating unit is operated are also known.

There is a need in such printing devices that can cancel a print job in response to operation of an operating unit to efficiently inform the control device that the operating unit was operated.

An objective of at least one embodiment of the present invention is to provide a control method of a printer a printer and a printing system that enables a printer to efficiently inform a control device that cancelling a print job was instructed by an operation of an operating unit.

One aspect of at least one embodiment of the present invention is a control method of a printer that can connect to a control device including printing based on a print job created by the control device detecting if an operating unit that receives a print job cancel command was operated storing operation information indicating if the operating unit was operated based on the detection result and adding the operation information to status information indicating a status and responding to the control device if a status response request is received from the control device.

Thus comprised when a status response request is received the printer adds operation information to the status information that is returned. As a result the control method of at least one embodiment of the present invention enables more efficient notification using status information than a configuration that uses a proprietary protocol for sending operation information from the printer to the control device and reports cancellation of a print job by sending the operation information according to the proprietary protocol.

A control method according to another aspect of at least one embodiment of the present invention also includes receiving from the control device a reset command that sets the operation information to information indicating that the operating unit has not been operated and when the operation information is information indicating that the operating unit was operated setting the operation information to information indicating the operating unit has not been operated.

Thus comprised the printer can reset the operation information to information indicating that the operating unit has not been operated in response to a command from the control device.

Another aspect of at least one embodiment of the present invention is a printer that can connect to a control device the printer including a print unit that prints based on a print job created by the control device an operating unit that receives a print job cancel command and a control unit that detects if the operating unit was operated stores information indicating if the operating unit was operated based on the detection result and adds the operation information to status information indicating a status and responds to the control device if a status response request is received from the control device.

Thus comprised when a status response request is received the printer adds operation information to the status information that is returned. As a result the printer of at least one embodiment of the present invention can send notifications more efficiently using status information than a configuration that uses a proprietary protocol for sending operation information from the printer to the control device and reports cancellation of a print job by sending the operation information according to the proprietary protocol.

Further preferably in a printer according to another aspect of at least one embodiment of the present invention when a reset command that sets the operation information to information indicating that the operating unit has not been operated is received from the control device and the operation information is information indicating the operating unit was operated the control unit sets the operation information to information indicating the operating unit has not been operated.

Thus comprised the printer can reset the operation information to information indicating that the operating unit has not been operated in response to a command from the control device.

Another aspect of at least one embodiment of the present invention is a printing system including a printer and a control device connected to the printer wherein the printer comprises a print unit that prints based on a print job an operating unit for instructing cancelling a print job and a control unit that detects if the operating unit was operated stores information indicating if the operating unit was operated based on the detection result and adds the operation information to status information indicating a status and responds to the control device if a status response request is received from the control device and the control device comprises a host control unit that creates the print job sends control data for the created print job to the printer and controls the printer to execute the print job and sends a status response request to the printer and cancels a print job queued for execution by the printer when the operation information added to the status information received in response to the response request is information indicating the operating unit has not been operated.

Thus comprised when a status response request is received the printer adds operation information to the status information that is returned. As a result the printing system of at least one embodiment of the present invention can send notifications more efficiently using status information than a configuration that uses a proprietary protocol for sending operation information from the printer to the control device and reports cancellation of a print job by sending the operation information according to the proprietary protocol.

In addition when the operating unit of the printer is operated the control device detects operation of the operating unit based on the operation information added to the status information and cancels print jobs queued for printing by the printer. As a result when the control device creates and queues multiple print jobs the user can cancel any print jobs that remain queued for the printer by simply operating the operating unit once instead of operating the operating unit for each individual print job to cancel. The user s task is thereby simplified and user convenience is improved.

In a printing system according to another aspect of at least one embodiment of the present invention the host control unit of the control device can send a reset command that sets the operation information to information indicating the operating unit has not been operated and the control unit of the printer sets the operation information to information indicating the operating unit has not been operated when the reset command is received from the control device and the operation information is information indicating the operating unit was operated.

Thus comprised the control device can reliably reset the operation information to information indicating the operating unit has not been operated by sending a reset command.

In a printing system according to another aspect of at least one embodiment of the present invention the host control unit of the control device receives print requests requesting printing by the printer and when a print request is received sends the reset command to the printer before sending control data for the print job based on the print request to the printer.

Thus comprised because the operation information is reset to information indicating that the operating unit has not been operated by the control device sending a reset command before starting to print with the printer problems such as operation information indicating that the operating unit was operated being sent from the printer to the control device and the print job being cancelled by the control device even though the operating unit was not operated while printing can be prevented.

In a printing system according to another aspect of at least one embodiment of the present invention the host control unit of the control device receives print requests requesting printing by the printer creates a plurality of print jobs for printing based on the print request when a print request is received sequentially executes the plural print jobs on the printer by sending control data for the next print job to the printer after one print job ends sends a status response request while sequentially executing the print jobs and cancels the print jobs that have not been executed by the printer if the operation information added to the status information received in response to the status response request while sequentially executing the print jobs is information indicating the operating unit was operated.

Thus comprised if a series of print jobs based on a print request are queued and the operating unit is operated while the printer is executing any one of the print jobs the control device can cancel the queued print jobs that have not been executed.

In a printing system according to another aspect of at least one embodiment of the present invention the host control unit of the control device sends the status response request before sending control data for any one of the plural print jobs to the printer.

Thus comprised the control device can detect if the operating unit was operated before executing a print job on the printer and if the operating unit was operated can cancel the print job before starting the print job.

Further preferably the print request requests printing plural pages and the host control unit of the control device creates a print job for each page.

Thus comprised when the operating unit is operated while the printer is executing the print job for any one of multiple pages based on a print request the control device can cancel the print jobs for the pages that have not been printed.

Other objects and attainments together with a fuller understanding of the invention will become apparent and appreciated by referring to the following description and claims taken in conjunction with the accompanying drawings.

Some embodiments of the present invention are described below with reference to the accompanying figures.

The printer can be a serial inkjet printer. The printer loads cut sheet print media such as A4 paper and prints images on the loaded print media. The printer can have an inkjet head that can be is mounted on a carriage. The carriage scans in a primary scanning direction intersecting the conveyance direction of the print medium. The printer prints images by driving the carriage to scan the primary scanning direction with the inkjet head while ejecting ink at a specific timing from specific nozzles of the inkjet head and forming dots of specific colors on the print medium.

As shown in the printer has a rectangular box like printer unit that extends in a length direction is long across the width of the printer . A paper cassette loading unit is assembled inside the printer unit . A paper cassette can be removably installed in the paper cassette loading unit . The paper cassette is a box shaped member that can hold multiple sheets of print media for supply to the printer . A discharge tray is disposed above the paper cassette . The discharge tray is a tray that temporarily holds the print media after being printed. A paper exit from which the print media is discharged after printing is disposed above the discharge tray .

Rectangular access doors are disposed on opposite sides of the discharge tray and paper exit at the front of the case of the printer unit . When the user opens these access doors the ink cartridge loading units thereinside are exposed and the ink cartridges can be replaced.

An openable cover is disposed on the top of the case . Opening the cover exposes the inside of the case and makes accessible the mechanisms housed in the case .

As shown in a power button for turning the power on and off is disposed at the left end of the operating panel . A cleaning button for starting the inkjet head cleaning operation is disposed on the operating panel on the right side of the power button . A paper feed discharge button for feeding the print media stored in the paper cassette or discharging the print media from the paper exit is disposed on the operating panel on the right side of the cleaning button lib. A cancel button operating unit that accepts a command to cancel a print job in progress is disposed on the operating panel on the right side of the paper feed discharge button . The process executed by the printer and the host computer described below when the cancel button is operated is described further below. A first warning indicator which is an LED indicating the status of the cover is disposed on the operating panel on the right side of the cancel button . A second warning indicator which is an LED indicating the status of the print media set in the printer is disposed on the operating panel on the right side of the first warning indicator . A third warning indicator which is a group of LEDs indicating the status of ink in the ink cartridges holding black K magenta M cyan C and yellow Y ink is disposed on the right side of the second warning indicator

The control system includes the printer and a host computer control device which are communicatively connected to each other.

As shown in the printer includes a control unit print unit input unit LED driver storage unit and communication interface .

The control unit includes a CPU ROM RAM and other peripheral circuits and controls the printer . The control unit controls the printer by functions of a control program including firmware for example.

In addition to the inkjet head and carriage described above the print unit includes a mechanism for conveying the print media various sensors and the mechanisms devices and parts needed for other printing related processes and processes associated with printing. The print unit prints images on the print media as controlled by the control unit .

The input unit detects operation of the buttons including the cancel button described above and outputs to the control unit .

The LED driver drives the LEDs of the first warning indicator second warning indicator and third warning indicator as controlled by the control unit .

The storage unit includes nonvolatile memory and stores data. A button flag area that stores a button flag which is set when the cancel button is operated is formed as a 1 bit button flag area that can be read by the firmware in the storage area of the storage unit . The button flag area is a storage area storing a button flag that is set when the cancel button is operated. After the button flag is set in response to operation of the cancel button the flag remains set until the printer receives a reset command described below. Therefore by referencing the state of this button flag the control unit can know whether or not the cancel button was operated. Information indicating whether or not the cancel button was operated which is indicated by the button flag is also referred to as button operation information below.

Note that setting the button flag as used herein means setting the button flag to 1. Clearing the button flag means setting the button flag to 0.

The communication interface communicates with the host computer according to a specific communication protocol as controlled by the control unit . The communication standard is not specifically limited and may be a communication standard compatible with USB a communication standard compatible with RS232 C or other serial port interface standard or a communication standard compatible with Ethernet T for example.

As shown in the host computer includes a host control unit control device control unit a host input unit host display unit host storage unit and host communication interface .

The host control unit includes a CPU ROM RAM and other peripheral circuits and controls the host computer . Function blocks of the host control unit includes an application execution unit and a printer driver execution unit . These function blocks are described further below.

The host input unit connects to an input means such as a mouse keyboard button or switch detects operation of the input means and outputs to the host control unit .

The host display unit has a display panel such as an LCD panel and displays images on the display panel as controlled by the host control unit .

The host communication interface communicates with the printer according to a specific communication protocol as controlled by the host control unit .

As described above the printer has a operating panel operating unit . The operation of the printer related to the cancel button is described below.

The control unit of the printer reads and executes the process show in the flow chart in from firmware or associated programs.

As shown in when the printer power turns on step SA the control unit of the printer clears the button flag step SA .

As shown in the control unit of the printer monitors whether or not the cancel button is operated while the power is on step SA .

If operation of the cancel button is detected step SA returns YES the control unit sets the button flag step SA . Note that in step SA the control unit accesses the button flag area and sets the button flag. If the button flag has already been set the control unit simply keeps the button flag set.

As long as the printer power is on power on state the control unit of the printer according to this embodiment monitors whether or not the cancel button is operated. If the cancel button is operated the control unit sets the button flag.

Note that the control unit executes the operation of steps SA and SA in the flow chart in in parallel to the process shown in column B in the flow chart in described below. The control unit therefore sets the button flag if the cancel button is operated while the process shown in B in the flow chart in is executing as described below.

When the flow chart in starts a specific application program installed on the host computer starts. The application can be software such as a word processor spreadsheet web browser or other program that displays images on the display panel of the host display unit and accepts commands to print an image corresponding to the imaged presented on the display panel. These two functions are not limited to being performed independently by a single application and may be embodied using an operating system OS a printer driver described below and other software.

To print with the printer the user uses a user interface provided by the application to issue a print request step SX . A print request means requesting the printer to print.

In this example the application is a word processing program and in step SX the user requests printing 10 pages. Printing one page means printing an image on one sheet of paper. Therefore an instruction to print 10 pages means an instruction to print images on ten sheets of paper. The printer driver generates a print job for each page.

A print job means a job corresponding to a continuous printing sequence executed by the printer as controlled by the host computer . The control unit and the printer execute a printing process for each print job. Therefore when the number of pages to print is 10 and a print job is created for each page when 10 print jobs corresponding to the 10 pages are created the host computer sends control data for printing each page and when printing one page based on the control data is completed creates control data for printing the next page.

If the number of pages to print is 10 and one print job is created for the 10 pages when one print job corresponding to the 10 pages is created the host computer sends the control data instructing printing one page continuously for the 10 pages and the printer sequentially prints the individual pages based on the control data to print the 10 pages one after another.

The effect of creating plural print jobs corresponding to the plural pages to be printed is described below.

More specifically as will become understood below the host computer controls the printer to sequentially print plural print jobs one at a time. As a result the user can check the print media on which an image is printed one sheet at a time to confirm the printed result. Therefore the user can know early in the printing process if the printed result is not what the user expected. For example when the user requests printing images on 10 sheets of print media the user can know when printing the image on the first sheet of print media whether the printed result differs from the expected result. If the printed result differs from what was expected the user can cancel printing by operating the cancel button on the printer . Because the user can know at an early state in the printing process if the result is as desired the user can cancel printing at an early stage and can thereby reduce the waste of print media. Note that the control system according to this embodiment simplifies user operation and improves user convenience related to instructing cancel printing as described further below.

If the host computer is configured to create one print job to print images on plural sheets of print media and control the printer to print the one print job when printing plural sheets of print media is requested the following can occur.

That is in this configuration because the printer continuously prints images on plural sheets of print media when executing a single print job processing is efficient and the time required to complete the process can be shortened. On the other hand printing an image on plural sheets of print media runs continuously. As a result the user may not be able to determine that the printed result differs from the expected result early in the process of printing images on the plural sheets of print media.

As shown in column A of when a print request is asserted the application execution unit of the host control unit of the host computer outputs the information required for printing referred to below as application print information to the printer driver execution unit step SB .

The application execution unit and printer driver execution unit are function blocks that executes processes by reading and running an application and associated programs.

In step SB the application execution unit calls an API application programming interface provided by the OS and using functions of the API outputs the application print information to the printer driver execution unit

Based on the input application print information the printer driver execution unit creates a print job for each page step SB . In this example the printer driver execution unit creates 10 print jobs for the 10 pages to be printed.

After creating the plural print jobs in step SB the printer driver execution unit sends a reset command to the printer step SB .

As shown in column B of the control unit of the printer clears the button flag in response to receiving the reset command step SC . More specifically if the button operation information is information indicating that the cancel button was operated already operated the control unit changes the button operation information in step SC in response to receiving the reset command to indicate that the cancel button has not been operated not operated . Note that if the button flag is not set the control unit does not change the flag setting in step SC and the button flag remains unset.

Next the control unit sends a reset completion report reporting that the flag was cleared to the control unit step SC .

Next the control unit checks if the status response request command described below was received step SC .

As shown in column A of the printer driver execution unit of the host control unit of the host computer executes the following process when the reset completion report is received.

First the printer driver execution unit selects the print job for the printer to execute from among the plural print jobs created in step SB step SB .

More specifically when plural print jobs are created the printer driver execution unit controls the printer to sequentially execute the print jobs. In step SB the printer driver execution unit selects the next print job for the printer to execute according to the print job sequence.

For example if no print job has been completed the printer driver execution unit selects the print job related to printing an image on the first sheet of print media in step SB. If the print jobs related to printing images on the first five pages of print media have already been completed the printer driver execution unit selects the print job for printing the sixth page of the print media in step SB.

Below the print job the printer driver execution unit selects in step SB is referred to as the target print job.

Next the printer driver execution unit sends a status response request command to the printer step SB . The printer driver execution unit in this embodiment thus sends the status response request command after selecting the target print job and before sending control data for processing the target print job.

The status response request command is a command requesting the printer to return status information data. This status information data is data including status information indicating one or more statuses of the printer . These statuses include for example the state of the cover if various errors have occurred and the remaining ink level.

Button operation information indicating the state of the button flag is also included in the status information data. The button operation information may be represented by a particular flag in the status information data for example. Further alternatively the button operation information may be expressed by storing data indicating the state of the button flag in a specific area reserved in the status information data.

As shown in the status information data has a 1 bit area A. This area A is an area where information indicating the status of the cover is set. Setting this area A to a 1 indicates that the cover is open setting it to 0 indicates the cover is closed.

The status information data also has a printer unit 2 bit area A. This area A is an area where information related to various errors is stored. Setting area A to 00 means that no error has occurred. Setting area A to 01 means that an error has occurred in the print mechanism. Setting area A to 10 means that an error has occurred in the conveyance mechanism. Setting area A to 11 means that another error has occurred.

The status information data also has a 1 bit area A. This area A is an area where information related to the remaining ink level is set. When area A is set to 0 the ink end is near. When area A is set to 1 there is sufficient ink.

The status information data also has a 1 bit area A. This area A is the area where the button flag is stored. More specifically area A stores a 1 indicating the cancel button was operated or a 0 indicating the cancel button has not been operated.

As shown in column B of when the status response request command is received step SC returns YES the control unit of the printer reads the state of the button flag and gets the button operation information step SC . If the button flag is set set state the button operation information is information indicating that the cancel button was operated. If the button flag is not set the button operation information is information indicating that the cancel button has not been operated.

Next the control unit gets the values of various sensors gets specific statuses by executing processes acquiring specific statuses and acquires the status information based on the acquired statuses step SC .

Next the control unit generates status information data including the button operation information acquired in step SC and the status information acquired in step SC step SC . In other words the status information data is data created by adding the button operation information to the status information.

As shown in column A of when the status information data is received the printer driver execution unit of the host control unit of the host computer executes the following process step SB .

Based on the status information contained in the status information data the printer driver execution unit determines whether the printer is in a state that enables the execution of the printing process. In step SB the printer driver execution unit determines that the printing process cannot be executed in the current state of the printer if the cover is open a specific error has occurred or there is insufficient remaining ink for example.

If the printer cannot execute the printing process in its current state step SB returns NO the printer driver execution unit executes an appropriate process step SB .

In step SB the printer driver execution unit interrupts execution of the print job by the printer and controls the host display unit to display that the printer cannot print and the cause for example.

If the state of the printer enables the execution of the printing process step SB returns YES the printer driver execution unit executes the following process step SB .

Specifically the printer driver execution unit determines if the cancel button was operated based on the button operation information contained in the status information data. If the button flag is set in the printer the printer driver execution unit determines that the cancel button was operated in step SB. If the button flag is not set in the printer the printer driver execution unit determines that the cancel button was not operated in step SB.

The printer driver execution unit may determine in step SB that the cancel button was operated in the following situations for example.

For example the printer driver execution unit may determine that the cancel button was operated when starting the print job related to the printing of the first page of print media if the cancel button was operated after the button flag was cleared based on the reset command sent in step SB and before the status response request command was sent in step SB.

The printer driver execution unit may also determine that the cancel button was operated when starting the print job related to the printing of the fifth page of print media if the cancel button was operated while executing the print job related to the printing of the fourth page of print media.

The process described in steps SA and SA in the flow chart in is also executed while running a print job.

If it is determined in step SB that the cancel button was not operated step SB returns NO the printer driver execution unit executes the following process.

The printer driver execution unit generates control data comprising the commands controlling the sequence of steps appropriate to the target print job and sends the control data to the printer step SB .

As shown in column B of when the control unit of the printer receives the control data it controls the print unit based on the control data to print an image on the print medium step SC . In this example the control unit prints an image on the first sheet of the print medium in step SC. When printing the image is completed the control unit sends a printing completed report indicating that the printing of the image based on the print job was completed to the host computer step SC . Next the control unit determines whether all print jobs created in step SB have been completed step SC . The control data that the host computer sends in step SB includes information indicating whether the control data is for the last print job and based on this information the control unit determines if printing is completed in step SC.

If all print jobs are completed step SC returns YES the control unit ends the process. If all print jobs are not completed step SC returns NO the control unit returns to step SC.

As shown in column A of when the printing completed report is received the printer driver execution unit of the host control unit of the host computer executes the following process.

The printer driver execution unit determines if all print jobs created in step SB have finished step SB . If all print jobs created in step SB have finished step SB returns YES the printer driver execution unit ends the process. If all print jobs created in step SB have not finished step SB returns NO the printer driver execution unit returns to step SB.

However if it is determined in step SB that the cancel button was operated step SB returns YES the printer driver execution unit executes the following process step SB . Specifically the printer driver execution unit in step SB cancels any print job created in step SB that has still not be executed by the printer print jobs still queued for execution by the printer . This means that generating and sending control data for the print jobs is cancelled and the printer is not caused to execute another print job.

For example when the user requests printing images on 10 sheets of print media as described in the foregoing embodiment of the present invention the user may look at the result of printing the first page of the printed print media and determine that the printed result differs from what was expected. After printing the image on the first sheet of print media is completed the user then operates the cancel button while the print job related to printing an image on the second sheet of print media is executing.

As a result the printer driver execution unit sends the status response request command in step SB before sending control data for the print job related to printing an image on the third sheet of print media.

The button operation information contained in the status information data that the printer driver execution unit receives in response to the status response request command is information indicating that the cancel button was operated because the cancel button was operated while the immediately preceding print job was running. The printer driver execution unit therefore determines in step SB that the cancel button was operated and in step SB cancels the print jobs that have still not executed.

By operating the cancel button once the user can therefore cancel the print jobs related to printing the third to tenth sheets of print media.

Note that when the user requests printing on multiple sheets of print media and the user cancels the print job in the middle of printing the intention is often to also cancel printing images on the remaining pages that have not finished printing.

To cancel plural print jobs in the related art however the user must typically operate the cancel button for each print job to cancel each of the print jobs. For example to cancel printing on the third to tenth sheets of print media the user must operate the cancel button eight times and cancel the eight print jobs. In comparison the control system according to some embodiments of the present invention reduces the number of operations required by the user and therefore improves user convenience.

As described above the control system according to some embodiments of the present invention has a printer and a host computer control device .

The printer includes a print unit that prints a cancel button operating button that receives a command to cancel a print job the print unit is executing and a control unit that detects whether the cancel button was operated stores button operation information as information indicating whether or not the cancel button was operated based on the detection result and if a response request for status data is received from the host computer adds the button operation information to the status information indicating the status and responds to the host computer .

The host computer has a host control unit control device control unit that creates a print job sends control data for the created print job to the printer controls the printer to execute the created print job requests the printer to return status data and cancels a print job queued for the printer if the button operation information added to the status information received in response to the response request is information indicating the operating button was operated.

Thus some embodiments of the present invention enable more efficient notification using status information than a configuration that uses a proprietary protocol for sending button operation information from the printer to the host computer and reports cancellation of a print job by sending the button operation information according to the proprietary protocol.

Furthermore when the cancel button of the printer is operated in at least one embodiment of the present invention the host computer detects that the cancel button was operated based on the button operation information added to the status information and therefore cancels print jobs that were queued for execution by the printer . As a result when the host computer creates and queues multiple print jobs the user can cancel any print jobs that remain queued for the printer to execute by simply operating the cancel button once instead of operating the cancel button for each individual print job to cancel. The user s task is thereby simplified and user convenience is improved.

In some embodiments of the present invention the host control unit of the host computer can send a reset command instructing resetting of the button operation information. When this reset command is received from the host computer and the button operation information is information indicating that the cancel button was operated the control unit of the printer changes the button operation information to indicate that the cancel button has not been operated.

The button operation information is information indicating that the cancel button was operated when the button flag is set and information indicating that the cancel button was not operated when the button flag is cleared.

Thus comprised the host computer can reliably reset the button operation information to information indicating that the operating button has not been operated by simply sending the reset command.

In some embodiments of the present invention the host control unit of the host computer receives print requests requesting the printer to print and when a print request is received sends a reset command to the printer before controlling the printer to execute control data for the print job based on the print request.

This embodiment can therefore prevent problems such as button operation information indicating that the cancel button was operated from being sent from the printer to the host computer and the print job being cancelled by the host computer even though the cancel button has not been operated while printing.

In some embodiments of the present invention the host control unit of the host computer receives print requests requesting the printer to print and when a print request is received creates plural print jobs for printing based on the print request sends the control data for the next print job to the printer after one print job ends and thereby controls the printer to sequentially print plural print jobs. When the host control unit sends a status response request while running plural print jobs and the button operation information added to the status information received in response to the status response request is information indicating that the operating button was operated the host control unit cancels any remaining plural print jobs that have not been executed by the printer .

Thus comprised if a series of print jobs based on a print request are queued and the cancel button is operated while the printer is executing any one of the print jobs the host computer can cancel the queued print jobs that have not been executed.

Furthermore when multiple print jobs are queued the host control unit of the host computer sends a status response request to the printer before sending the control data for any single print job.

Thus comprised the host computer can detect if the cancel button was operated before executing a print job on the printer and if the cancel button was operated can cancel the print job before starting the print job.

The print request of a user in some embodiments of the present invention is a request to print multiple pages. The host control unit of the host computer creates a print job for each page.

Thus comprised when the cancel button is operated while the printer is executing the print job for any one of the multiple pages based on the print request the host computer can cancel the print jobs for the pages that have not been printed.

The present invention is described above with reference to some embodiments thereof but the present invention is not limited thereto and can be modified and adapted in many ways without departing from the scope of the accompanying claims.

For example the printer may have plural operating modes and be configured to execute the process described above when the active operating mode is a specific operating mode. This can also be applied to the host computer .

The function blocks shown in can be achieved by the cooperation of hardware and software. PLEASE MAKE SURE THAT THIS HARDWARE AND SOFTWARE corresponding to any claimed functional blocks e.g. operating unit control unit host control unit print unit control device etc. are clearly disclosed in the specification. This may be necessary to satisfy 35 U.S.C. 112 f . The function of the printer may also be handled by a separate device externally connected to the printer . The printer may also execute processes by running a program stored in an externally connected storage medium.

The disclosure being thus described it will be apparent that it may be varied in many ways. Such variations are not to be regarded as a departure from the spirit and scope of the disclosure and all such modifications as would be apparent to one skilled in the art are intended to be included within the scope of the following claims.


---

title: Printer and printing system
abstract: In a system of a data processing apparatus coupled to a printer, the apparatus sends a status information transmission request to the printer and, in response, receives status information from the printer. The status information includes cartridge identification information written in a memory device contained in a cartridge, device identification information identifying the printer in which the cartridge is installed, and ink usage amount information for use by the printer in calculating an ink usage amount.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09333759&OS=09333759&RS=09333759
owner: Seiko Epson Corporation
number: 09333759
owner_city: Tokyo
owner_country: JP
publication_date: 20150731
---
This application is a continuation of and claims priority under 35 U.S.C. 120 on U.S. application Ser. No. 14 547 168 filed Nov. 19 2014 which is a continuation of U.S. application Ser. No. 13 946 040 filed Jul. 19 2013 now U.S. Pat. No. 8 919 914 which is a continuation of U.S. application Ser. No. 13 074 190 filed Mar. 29 2011 now U.S. Pat. No. 8 511 789 which is a divisional of U.S. application Ser. No. 11 555 096 filed Oct. 31 2006 now U.S. Pat. No. 7 950 766 which claims priority under 35 U.S.C. 119 on Japanese patent application nos. 2005 316284 and 2005 363318 filed Oct. 31 2005 and Dec. 16 2005 respectively. Each of the above identified applications is incorporated by reference herein in its entirety.

The present invention relates generally to a data processing apparatus configured to couple with a printer and a method of controlling such apparatus. The printer uses a cartridge that stores ink toner organic material for printing or other printing fluids or materials. Status information obtained from the printer by the data processing apparatus includes cartridge identification information written in a memory device contained in a cartridge device identification information identifying the printer in which the cartridge is installed and ink usage amount information for use by the printer in calculating an ink usage amount. To simplify the following discussion the term ink will be used in the specification and the claims as a generic term that represents liquids or other materials for printing such materials including ink toner organic materials and the like.

Printers such as inkjet printers and laser printers generally print text pictures or other content on plain paper special paper or other recording media by placing or fusing ink onto the recording medium. The ink is typically stored in a cartridge that can be freely installed in and removed from the printer. When the ink inside the cartridge is depleted in the course of using the printer ink can be added by simply replacing the cartridge.

Printer manufacturers also usually supply the ink cartridges that are used in their printers to the end users and are therefore also in the business of selling cartridges filled with ink.

More recently manufacturers have developed new billing systems printing systems for charging the printer user based on the amount of ink consumed instead of selling individual cartridges.

Japanese Unexamined Patent Appl. Pub. 2000 309147 for example discloses a billing system in which the printer stores information about the consumption of consumable supplies such as how toner is consumed and how much paper is used for each user ID. The printer then sends this consumption information to a data processing terminal when requested and the data processing terminal calculates the printer usage fee according to a predetermined formula based on this consumption information.

Japanese Unexamined Patent Appl. Pub. 2004 90517 discloses an inkjet printer having a billing information management unit for managing ink usage. The billing information management unit calculates ink consumption based on the size and number of ink droplets discharged from the print head.

Japanese Unexamined Patent Appl. Pub. 2002 36582 discloses a billing system in which the inkjet printer uses optical sensors to measure how much ink remains in the ink cartridge and calculates ink usage based on how much ink remains. A data processing device connected to the inkjet printer acquires data relating how much ink is used referred to below as simply ink usage from the inkjet printer and sends data relating to ink usage over a network to a server in a service center. The billing module that runs on the service center server then references an ink billing table to calculate the billing amount based on ink usage and bills the user.

The above billing system simultaneously manages plural printers and plural cartridges for plural users and therefore requires a system that can identify each printer and each cartridge to acquire the ink usage information.

In businesses where this billing system is actually used however the billing system operator the party providing the printer or cartridge and the actual printer user are often in separate places. In the case of an inkjet printer this requires constructing a system in which the user is only billed for the ink actually consumed from the specific ink cartridge provided by the operator to the user.

In order to reliably acquire ink usage data from a user in a remote location it is also necessary to improve the reliability of the data acquired from the printer by for example preventing errors in the transmitted data.

In the operation of this billing system the billing system operator must understand how ink cartridges are used in the remote location where the user is located recover the depleted ink cartridges in a timely manner and keep the user supplied with new ink cartridges filled with ink. The system operator must therefore reliably store accurate information relating to the depleted ink cartridges and what ink cartridges have been newly installed in the printer.

A server that is located in the service center and that handles the calculations could be used to receive and store the ink cartridge data received from the printer. However if the service center server loses the ink cartridge data for some reason the operator becomes unable to acquire data for the ink cartridge used by the user. Furthermore because the operator cannot know when the depleted ink cartridges should be collected if the ink cartridge data cannot be acquired from the printer filled ink cartridges cannot be supplied to the user when needed. This creates obvious business problems.

Embodiments of the invention entail a data processing apparatus configured to couple with a printer and a method of controlling such apparatus. Status information obtained from the printer by the data processing apparatus includes cartridge identification information written in a memory device contained in a cartridge device identification information identifying the printer in which the cartridge is installed and ink usage amount information for use by the printer in calculating an ink usage amount.

In embodiments directed to the data processing apparatus such apparatus includes a communication unit configured to send a status information transmission request to the printer and to receive status information from the printer.

In some embodiments the cartridge stores a plurality of inks and the ink usage amount information includes ink usage amount information for each ink that the cartridge stores.

In some embodiments the ink usage amount is calculated by counting the number of ink shots discharged.

Moreover in calculating the ink usage amount the calculation may disregard the amount of ink discharged when calculating the ink usage amount.

The cartridge identification information may include a designator identifying the cartridge installed in the printer.

The cartridge identification information may include a designator that indicates when the amount of ink inside the cartridge becomes less than or equal to a predetermined level.

Other objects and attainments together with a fuller understanding of the invention will become apparent and appreciated by referring to the following description and claims taken in conjunction with the accompanying drawings.

Preferred embodiments of a printer and printing system according to the present invention are described below with reference to the accompanying figures. Embodiments of a printer and printing system according to the present invention that use a cartridge that stores ink are described in detail below with reference to a billing system in which the printer and printing system are used. As mentioned previously to simplify the following discussion the term ink will be used in the specification and the claims as a generic term that represents liquids or other materials for printing such materials including ink toner organic materials and the like.

In an ink billing system according to this embodiment of the invention a terminal device run by the printer manufacturer the supplier of cartridges containing the ink manages the supply of cartridges filled with ink to company X the cartridge user which has purchased a plurality of color inkjet printers and company X pays an ink fee through the terminal device of the printer manufacturer according to the amount of ink that was used for printing by the printers .

In this ink billing system company X is a company that issues coupons for particular products and obtains advertising income according to the number of coupons issued. Company X installs an in store server data processing system and a plurality of printers purchased from the printer manufacturer in a plurality of stores to that are owned or managed by company Y such as a customer of company X only the in store server and printers in stores and are shown in for brevity . Each printer is in communication by a LAN with the in store server .

Company Y in this example is a supermarket or other retailer. The printers can be printers for printing receipts but are described as a different kind of printer in this embodiment of the invention. More particularly the printers are installed near each POS terminal in each store to as printers for printing coupons. Each printer is configured to issue coupons for example linked to specific product information input from the POS terminal according to instructions from the in store server installed in the same store. The issued coupons are then handed to the customer by the POS terminal operator of company Y .

The main server is maintained by company X and is in communication over a private or public communication network such as the Internet with each of the in store servers located in the stores to . The main server sends product information to the in store servers . The main server is also used to manage the product information and sends data used to print the coupons that are output by the printers in conjunction with the product information and receives from the in store servers information about the type and number of coupons issued by the printers for example.

The printer manufacturer in this ink billing system supplies ink cartridges cartridges below containing ink to company X according to demand. Demand can be predicted by the terminal device run by the printer manufacturer based on ink usage by the user. The printers are installed at the checkout counters with the POS terminals in company Y . The ink cartridges supplied by company X are installed in the printers . A scanner located at the POS terminal scans the barcode including a product code affixed to each product and the in store server then acquires product information corresponding to each product code and determines if there is coupon information to be printed. If there is coupon information to be printed the server sends appropriate print data to the printer to issue a coupon. The in store server in each of the stores to regularly collects information relating to ink usage from each of the connected printers and sends the information to the main server .

The main server then sends the ink usage information for the printers collected in the main server over a network to a terminal device operated by the printer manufacturer. The ink usage information collected in the main server could alternatively be recorded on a CD Compact Disc DVD Digital Versatile Disc or other data storage medium that is then delivered to the printer manufacturer. The printer manufacturer or terminal device then tabulates the ink usage information received from company X and periodically bills company X for the ink usage. The company X also returns empty ink cartridges collected from company Y to the printer manufacturer. The printer manufacturer refills the returned ink cartridges and then returns the refilled ink cartridges to company X .

The ink billing system according to this embodiment of the invention only bills for the amount of ink used for printing coupons and other content. Ink that is not used for printing includes for example ink that is consumed by cleaning processes print head recovery processes and ink supply replenishing operations including the ink that is used to flush the nozzles and ink that is vacuumed from the nozzles as part of print head nozzle maintenance. More specifically there is no charge for ink that is consumed by operations that are run so that ink can be discharged from the print head. An advantage of this system is therefore that company X does not need to pay for ink that is not used to print the coupons.

A printer according to this embodiment of the invention as shown in and is a color printer that uses plural inks i.e. different colors of ink to print images on roll paper used as the recording medium and to issue coupons.

As shown in a printer according to this embodiment of the invention has a power switch roll paper cover and an ink cartridge compartment cover located from left to right at the front of the printer case which includes a front top panel and a printer case cover . Above the power switch are a plurality of LED indicators for reporting information about the printer status to the user. The roll paper cover and ink cartridge compartment cover can each pivot forward on a hinge not shown positioned at the bottom part of each cover to open and close.

Opening the roll paper cover opens the paper compartment in which the roll paper used as the printing paper is stored as shown in . The roll paper can be replaced when the roll paper cover is thus opened.

Opening the ink cartridge compartment cover provides access to the cartridge compartment and enables loading and replacing the ink cartridge in the cartridge compartment .

The ink cartridge in this embodiment is a single package containing three color ink packs one containing yellow one cyan and one magenta ink inside the cartridge case . In a printer according to this embodiment the ink cartridge inside the cartridge compartment slides between the cartridge replacement position and the cartridge usage position in conjunction with opening and closing the ink cartridge compartment cover .

As shown in two positioning holes are formed at the bottom part of the back of the ink cartridge . When an ink cartridge is loaded into the cartridge compartment of the printer the ink cartridge is guided to and held in position by these positioning holes sliding on positioning pins not shown. Three ink supply openings are also formed in the middle of the back and the three inks inside the ink cartridge are supplied through these ink supply openings to the printer .

A waste ink recovery opening located between the positioning holes is used to recover waste ink that is used for print head cleaning clogged nozzle recovery and ink supply replenishing that is ink that is not used by the printer for printing but is used instead to maintain the print head in printing condition so that ink can be properly discharged from the print head. Waste ink is recovered through this waste ink recovery opening into the ink cartridge . An ink cartridge according to this embodiment of the invention thus functions both as an ink tank for supplying ink and a waste ink tank for collecting and holding waste ink.

A memory device is embedded in one side of the ink cartridge with the surface of the contact pins exposed. This memory device is a rewritable nonvolatile memory device such as flash ROM that stores a cartridge ID cartridge identification information or other information for identifying the particular ink cartridge. The memory device is electrically connected by the exposed contact pins to matching pins not shown located in the cartridge compartment of the printer thereby enabling the printer to write data into the memory device .

The relationship between the in store server and printers of the printing system according to this embodiment of the invention is described next with reference to and .

As shown in the main parts of the in store server including in store server and other servers are the CPU ROM nonvolatile memory RAM volatile memory a hard disk drive as a large capacity storage device an input device and communication interface . The in store server controls the printer as a result of the CPU running the operating system and software applications stored in the hard disk drive and by sending commands and print data to the printer through communication interface .

The printer include for example a CPU flash ROM rewritable nonvolatile memory RAM volatile memory communication interface a printing control unit for controlling discharging of ink onto the roll paper to print images thereon a paper transportation mechanism print head a cover open sensor for detecting if the roll paper cover or ink cartridge compartment cover is open or closed and a cartridge compartment into which the ink cartridge is loaded. The printer receives commands and print data by communicating with the in store server through the communication interface while the CPU runs firmware stored in flash ROM . Based on the received control commands and print data the printing control unit conveys roll paper using the paper transportation mechanism while driving the print head to print on the roll paper to issue coupons.

Operation of the printer is described first. As shown in the printer has a reception unit and a reception buffer . The reception unit receives commands and print data sent from the in store server . The reception buffer temporarily stores the commands and print data received by the reception unit . A command interpretation unit then interprets the data received in the reception buffer and sends control commands to the control command buffer and sends print data to the print buffer by direct memory access DMA .

The print data buffered in the print buffer is then converted for printing by the print data generating unit to produce dot pattern data corresponding to the nozzle arrangement of the print head and to store it in the print buffer. This dot pattern data is for example 2 bit gray scale data denoting whether the ink from the nozzles of the print head is 1 not discharged or discharged as a 2 small dot 3 medium dot or 4 large dot.

The printing control unit drives the print head based on the dot pattern data stored in print buffer to form an image on the roll paper and create a coupon.

The control command data buffered in the control command buffer is read by the main control unit which executes processes such as advancing the paper a specific distance based on the control commands.

The shot count analyzing unit counts the amount of ink discharged from the print head as the number of shots of each color of ink in dot units based on the print data stored in the print buffer or the dot pattern data generated from the print data. The amount of ink discharged from the print head differs according to the size of each dot that is whether each dot is small medium or large. The shot count analyzing unit converts each size of dot to a corresponding shot count and calculates how many shots were discharged. The shot counts calculated by the shot count analyzing unit are then stored in data storage unit . The cumulative shot count from a particular point in time such as when the ink cartridge is replaced is also stored.

The shot count analyzing unit counts the amount of ink discharged from the print head to print on the roll paper in dot units converted to a shot count for each color and does not count disregards as part of ink usage the amount of ink consumed to ensure that the print head can discharge ink including the ink discharged from the print head during nozzle flushing the ink vacuumed from the print head by an ink suction mechanism not shown and the ink used for clogged nozzle recovery and ink loading operations.

The remaining ink analyzing unit calculates for each color the amount of ink remaining in the ink cartridge . A value denoting the amount of ink remaining in the ink cartridge is stored for each color in the memory device of the ink cartridge .

When the cartridge is recharged with ink a specific initialization value is stored and the amount of remaining ink can be calculated at any time by subtracting from this initial value the amount of ink used for printing plus the total amount of ink used to enable discharging ink from the print head including the ink consumed by flushing ink vacuuming and other cleaning operations and clogged nozzle recovery and ink loading operations as noted above.

The remaining ink level can alternatively be calculated from the total discharged shot count. The remaining ink level can also be expressed as the value of a ratio to the initialized value. The calculated remaining ink level is then stored in data storage unit and in the memory device of the ink cartridge utilizing the cartridge control unit at a predetermined time. When the remaining ink level becomes less than or equal to a specified level the cartridge is considered empty the out of ink level .

The cartridge control unit is a control unit for controlling reading data from the memory device of the ink cartridge installed in the printer and writing data to the memory device . The processes run by the cartridge control unit are linked to the cartridge ID read from the installed ink cartridge as further described below.

The data storage unit is a memory area for storing information about the printer and can be created by reserving a specific area in flash ROM .

As shown in the data storage unit has a printer serial number storage area remaining ink storage area cumulative ink shot count storage area and ink cartridge ID storage area

The printer serial number storage area stores a printer serial number device identification number which is a unique number for differentiating this printer from other printers of the same or different model.

The remaining ink storage area stores the amount of ink remaining in the ink cartridge currently loaded in the printer.

The cumulative ink shot count storage area accumulates and stores the total number of shots used only for printing as counted by the shot count analyzing unit .

The ink cartridge ID storage area stores the ID of the newly installed ink cartridge and the ID of the empty ink cartridge that was replaced.

The ink cartridge ID storage area separately stores the ID of the newly installed ink cartridge and the ID of the replaced empty ink cartridge and is configured to store both IDs. The ink cartridge ID storage area is described below as having a limited capacity for storing ink cartridge identification numbers but if a large capacity storage device is used for the data storage unit the ink cartridge ID storage area can be configured with no particular storage capacity limit.

The ink cartridge ID storage area includes a flag unit an ink cartridge ID storage unit and an ink cartridge status storage unit

The flag unit stores flags r ID transmission status flag indicating whether the ink cartridge ID has already been sent to the in store server .

The ink cartridge ID storage unit stores the ink cartridge ID read from the memory device by the cartridge control unit .

The ink cartridge status storage unit stores the ink cartridge status as a designator representing either NEW or OLD. The ink cartridge status flag is used to determine whether the ink cartridge ID read from an ink cartridge is the ID number of an ink cartridge installed for the first time NEW or is the ID of an ink cartridge that reached the ink end OLD .

In this embodiment of the invention the ink cartridge ID storage area is configured to store data sequentially from a predetermined address such as each time the cartridge control unit reads an ink cartridge ID from the memory device .

The transmission data generating unit acquires the billing information referred to below as the billing status stored in the data storage unit of the printer to produce the billing status information in response to a billing status transmission request from the in store server or generates cumulative ink shot count information in response to a cumulative ink shot count transmission request and returns the requested information to the in store server .

This billing status includes the new ink cartridge IDs as well as the IDs for empty ink cartridges stored in the ink cartridge ID storage area . The printer serial number and remaining ink information can also be included.

The cumulative ink shot count information includes only the cumulative ink shot count used for printing or the remaining ink level converted from the cumulative ink shot count .

Information including both this billing status information and the cumulative ink shot count information could alternatively be used as the billing status information. When the in store server sends a transmission request in this case the transmission data generating unit returns information including both the billing status information and the cumulative ink shot count information as the requested billing status information.

When a billing status information transmission request is received the transmission data generating unit compiles this information into a single transmission unit adds a checksum to improve data reliability and returns the result as the billing status information. A checksum is also added to the cumulative ink shot count to return the cumulative ink shot count information. The resulting billing status information or cumulative ink shot count information is then sent through the transmission unit to the in store server .

The transmission data generating unit is not limited to sending the billing status information in one block and could instead sequentially send the printer serial number remaining ink level cumulative ink shot count newly installed ink cartridge ID and the empty ink cartridge IDs. The ink cartridge IDs can also be sent with other combinations of data including only the cumulative ink shot count thus improving transmission efficiency by transmitting only the necessary information.

The in store server can execute various processes by running the operating system and software applications stored on the hard disk drive . A system for acquiring the coupon printing and billing status information using a printer located in a store is shown in . The in store server includes a communication unit coupon image storage unit coupon selection unit shot information acquisition unit ink usage acquisition unit billing status acquisition unit and billing status storage unit .

The communication unit communicates with the printer and sends commands and print data to the printer according to instructions from an upstream application or API application programming interface and receives information from the printer through a port a LAN port in this example for communicating with the printer .

The coupon image storage unit stores image data for the plural coupons that can be printed by the printer .

The coupon selection unit selects the appropriate image data from the image data for the plural coupons stored in the coupon image storage unit . The coupon selection unit in this embodiment executes the selection process when triggered by the POS terminal completing a transaction for example.

More specifically the coupon selection unit selects image data for a coupon linked to a specific product purchased by the customer. The selected image data is sent through the communication unit to the printer which then prints and issues the coupon. As a result coupons related to the products purchased by the customer are issued substantially at the same time as the receipt printer not shown connected to the POS terminal issues a sales receipt so that the coupons can be handed to the customer together with the receipt. By handing the coupons to the customer the company Y hopes to entice the customer to come again and make additional purchases. The coupon image data can be sent from the in store server to the printer for printing.

The shot information acquisition unit requests the printer to send the cumulative ink shot count information and based on commands from a higher level application not shown sends the cumulative ink shot count information transmission request through the communication unit to the printer . When the cumulative ink shot count information is received from the printer after sending a cumulative ink shot count information transmission request the cumulative ink shot count information is passed to the application that requested the information. A cumulative ink shot count information reception receipt is also returned to the printer . The cumulative ink shot count information is also stored in the billing status storage unit .

The billing status acquisition unit requests the printer to send the billing status information and sends a billing status information transmission request through the communication unit to the printer when instructed by a higher level application not shown. When the billing status information is received from the printer after sending the billing status information transmission request the billing status acquisition unit passes the billing status information to the application. A billing status information reception receipt is also returned to the printer . The information in the received billing status information is interpreted and stored in the billing status storage unit .

When storing the information in the billing status information in the billing status storage unit the billing status acquisition unit stores the printer serial number remaining ink level data cumulative ink shot count new ink cartridge ID and old ink cartridge ID as a single record whether the billing status information is received as a single block or as separate pieces of data.

The shot information acquisition unit and billing status acquisition unit add a checksum or other error correction code to the total ink shot count information and billing status information. This error correction code is designed to ensure the integrity of a specific data unit and is calculated by obtaining the checksum or the binary sum of all data for example. Using an error correction code enables verifying whether the data has been modified by some other process or whether the data is correctly communicated to the printer manufacturer s terminal device for example so that retransmission or other error handling process can be executed if the value is different.

More specifically by adding an error correction code to the billing status information the billing status acquisition unit prevents tampering and improves data reliability by enabling detecting errors in the received data.

This error correction code is added to the billing status information by the billing status acquisition unit of the in store server in this example but the invention is not so limited. For example the transmission data generating unit of the printer could add the error correction code to the billing status information so that billing status information containing an error correction code is sent from the printer to the in store server .

A process for reading the ink cartridge ID when an ink cartridge is installed in the printer is described next with reference to the flow chart in . is a flow chart describing the process that runs when the printer power is turned on or an ink cartridge is installed.

When a new ink cartridge is installed in the printer the cartridge control unit reads the ink cartridge ID from the memory device of the ink cartridge .

More specifically when the printer power turns on or when the cover open sensor detects that the ink cartridge compartment cover was closed step S returns Yes the remaining ink level value stored in the memory device of the ink cartridge is read step S and compared with the remaining ink level value stored in the data storage unit step S .

If the two remaining ink level values are the same the currently installed ink cartridge is determined to be the same ink cartridge as before the power turned on or the ink cartridge was replaced.

If the remaining ink level values are not the same the currently installed ink cartridge is different from the ink cartridge that was installed before the power turned on or the ink cartridge was installed and the cartridge control unit stores the ink cartridge ID read from the ink cartridge memory device as the ID of a new ink cartridge step S .

After storing the new ink cartridge ID the cartridge control unit updates the remaining ink level value stored in the remaining ink storage area of the data storage unit to the value read from the memory device of the ink cartridge step S . As a result the remaining ink level value stored in the ink cartridge and the remaining ink level value stored by the printer are the same.

The cartridge control unit also increments and updates the installation counter stored in the memory device of the ink cartridge . Information denoting the number of times the ink cartridge has been installed in a printer is thus updated in the ink cartridge . The printer can also read the value of this installation counter and execute an appropriate error handling process such as notifying the in store server that a problem has occurred when the installation counter is a value that should not occur during normal use.

The ink cartridge ID reading process when the ink cartridge in the printer is empty out of ink state is described next with reference to the flow chart in . is a flow chart describing the process executed when an ink cartridge becomes empty.

The remaining ink analyzing unit determines if an ink cartridge is empty is in this embodiment of the invention. The remaining ink analyzing unit calculates the amount of remaining ink of each color in the ink cartridge to obtain the remaining ink level value and if the remaining ink level value is less than or equal to a predetermined value for any single color the ink cartridge is determined to be in the out of ink state.

If the remaining ink level value is less than or equal to the predetermined level for any one color step S returns Yes the printer reports an out of ink status to the in store server using the transmission data generating unit and causes an LED indicator on the outside of the printer to flash thereby prompting the user to replace the ink cartridge step S .

The cartridge control unit then reads the ink cartridge ID from the memory device of the ink cartridge and stores the read ink cartridge ID in the ink cartridge ID storage area of the data storage unit as the ID of an empty ink cartridge step S .

The ink cartridge ID storage process executed in step S in and step S in is described further with reference to and .

Step S in is the process for storing the ink cartridge ID when an ink cartridge is installed. is a flow chart describing the process for storing the ink cartridge ID in the ink cartridge ID storage area . The ink cartridge identification number ID storage capacity of the ink cartridge ID storage area is assumed below to be limited to twenty ink cartridge IDs.

In this example a new ink cartridge is installed in the cartridge compartment when four ink cartridge IDs are already stored in the ink cartridge ID storage area . More specifically in the example shown in a new ink cartridge with ink cartridge ID is installed when new ink cartridge IDs and are stored at addresses and and out of ink ink cartridge ID is stored at address

The cartridge control unit then determines if there is enough space in ink cartridge ID storage area to store the ink cartridge ID read from the memory device . If there is step S returns Yes the ink cartridge ID of the newly installed ink cartridge is stored step S . More specifically ink cartridge ID is written to address in the ink cartridge ID storage unit and NEW or other specific flag designator is written to the corresponding field in the ink cartridge status storage unit

However if step S determines no space is available step S returns No the cartridge control unit determines if the twenty ink cartridge IDs stored in the ink cartridge ID storage area have been sent by checking if the flag r is set in the flag unit . If all twenty flags r are set step S returns Yes one of the twenty transmitted ink cartridge IDs is erased and the ink cartridge ID of the ink cartridge newly installed in the cartridge compartment is stored to the ink cartridge ID storage area step S .

Which of the twenty transmitted ink cartridge IDs to delete can be chosen for example on a FIFO first in first out basis so that the oldest ink cartridge ID is deleted and the new ink cartridge ID is stored overwritten to the same address. Using the example shown in the values stored at address in each storage unit would thus be erased the ink cartridge ID for the newly installed ink cartridge would be written to the same address in the ink cartridge ID storage unit and NEW would be written to the same address in the ink cartridge status storage unit

If none of the twenty flags r is set in step S step S returns No a problem occurred. The cartridge control unit therefore reports an error and executes an appropriate error handling process step S . More specifically by running an error handling process instead of overwriting memory if the ink cartridge IDs stored in the ink cartridge ID storage unit have not been sent to the in store server but the storage capacity is full the ink cartridge IDs that have not been sent to the in store server can be reliably saved and not accidentally erased. The user can also be informed of a problem with the data storage unit so that the user can have the printer repaired or checked by the printer manufacturer to keep the printing system running smoothly.

The ink cartridge ID storage process when the cartridge is out of ink in step S in is described next. As shown in when an ink cartridge installed in the cartridge compartment runs out of ink the cartridge control unit reads the ink cartridge ID and determines if space is available in the ink cartridge ID storage area . If there is at address in this example step S returns Yes the ink cartridge ID is stored at that address in ink cartridge ID storage unit step S and OLD is written to the same address in the ink cartridge status storage unit

If there is no available storage space step S returns No the cartridge control unit determines if the twenty ink cartridge IDs stored in the ink cartridge ID storage area have been sent by checking if the flag r is set in the flag unit . If all twenty flags r are set step S returns Yes one of the twenty transmitted ink cartridge IDs is erased and the ink cartridge ID of the ink cartridge newly installed in the cartridge compartment is stored to the ink cartridge ID storage area step S . Which of the twenty transmitted ink cartridge IDs to delete is preferably determined on a FIFO first in first out basis in this situation too so that the oldest ink cartridge ID is deleted and the new ink cartridge ID is stored overwritten to the same address.

When an ink cartridge reaches the out of ink state the in store server stops printing from the printer until the ink cartridge is replaced. When the user replaces the ink cartridge after the ID for the out of ink ink cartridge is stored the sequence shown in causes the printer to recognize the new ink cartridge and resume printing if the new ink cartridge is not also empty.

Instead of deleting ink cartridge IDs that have been sent to the in store server this embodiment of the invention thus stores new ink cartridge IDs read from the memory device of the ink cartridge in the ink cartridge ID storage area by adding the IDs to memory. As a result if the ink cartridge IDs received by the in store server are later lost because the in store server crashed after receiving the ink cartridge IDs for example the required ink cartridge IDs can be recovered by the in store server sending another transmission request to the printer because the transmitted ink cartridge IDs are still stored in the ink cartridge ID storage area on the printer.

More specifically because both the printer and the in store server store the ink cartridge IDs the printing system can be operated stably without losing the ink cartridge IDs even if a problem develops on the printing system.

Furthermore when there is no available storage space in the ink cartridge ID storage area new ink cartridge IDs are stored in FIFO order by sequentially deleting the oldest ink cartridge ID for which the transmission flag r is set. The invention can therefore be used in printing systems that use different ink cartridges for each color and therefore frequently read and store the ink cartridge IDs.

The ink cartridge IDs thus stored in the printer are then collected in the in store server and eventually reported to the terminal device of the printer manufacturer by the process described below. The ink cartridge ID collection process is described below.

The billing status information including the total ink shot count is sent from the printer to the in store server in response to a command from the in store server . As described above the billing status information includes the printer serial number remaining ink level total ink shot count the ink cartridge IDs for new ink cartridges and the ink cartridge IDs for out of ink cartridges and the in store server collates this information into a billing status information report with an error correction code. At a predetermined time the billing status information is then collected on the main server and the billing status information on the main server is sent periodically to the printer manufacturer s terminal device . The printer manufacturer s terminal device the printer manufacturer can then determine ink usage by the printers and the condition of each ink cartridge .

The process of collecting the billing status information is described in further detail below with reference to the flow chart thereof in .

First each printer counts the total number of shots using the shot count analyzing unit and collects all ink cartridge IDs stored in the ink cartridge ID storage area including newly installed ink cartridges and cartridges that are out of ink by means of the remaining ink analyzing unit and cartridge control unit and thus collects the billing status information step S .

The in store server collects the billing status information from each of the printers at a predetermined time by sending a billing status information transmission request to all of the printers in the store step S .

When a printer receives the billing status information transmission request step S the printer reads the information needed to report the billing status from the data storage unit and adds a checksum to produce the billing status information step S . The transmission data generating unit then sends the resulting billing status information through the transmission unit to the in store server step S .

When the in store server receives billing status information from a printer step S the server adds an error correction code to assure data reliability to the received billing status information if a checksum is not included in the received billing status information and temporarily stores the information step S . After step S the in store server sends a confirmation acknowledging receipt of the billing status information to the printer step S .

When the printer receives confirmation of the billing status information step S the printer sets transmitted ink cartridge IDs stored in the ink cartridge ID storage area step S as having been sent. More specifically the printer sets the transmission flag r in the flag unit

Referring again to the ink cartridge IDs and for which the transmission flag r is set were previously sent to the in store server but when sending the billing status information all ink cartridge IDs including these four previously sent IDs and the new ink cartridge IDs and and cartridge status flags from address to address are sent to the in store server . When the printer then receives the billing status information confirmation from the in store server the printer sets the transmission flags r in the flag unit at the addresses and where the new ink cartridge IDs and are stored.

By thus setting the transmission flag when receipt of the billing status information is confirmed the printer can easily determine whether a stored ink cartridge ID is an ink cartridge ID that has already been sent or is an ink cartridge ID that has not been sent. As a result the printer can also prevent accidentally writing a new ink cartridge ID at the address of an ink cartridge ID that has not been sent. Writing to the data storage unit can therefore be controlled more accurately because the printer separates write protected addresses for which the transmission flag r is not set from writable addresses for which the transmission flag r is not set in the ink cartridge ID storage area

After setting the transmission flag for transmitted ink cartridge IDs in step S the printer returns to step S collects the billing status information and repeats steps S to S. As a result each time a billing status information transmission request is received the printer sends the billing status information to the in store server and adds and stores any subsequently read ink cartridge ID.

At a predetermined time after the in store server collects the billing status information from the printers the main server sends a billing status information transmission request requesting transmission of the billing status information to the in store server step S .

When a billing status information transmission request step S is received the in store server sends the stored billing status information to the main server step S . When the main server receives billing status information from an in store server step S the main server stores the billing status information. As a result billing status information is collected by the main server from all printers insofar as the printers are operating normally that is unless there is a problem with a particular printer or a printer is turned off.

When requested by the terminal device of the printer manufacturer the main server or the operator of the main server at company X sends the billing status information collected from all printers to the printer manufacturer or the terminal device used by the printer manufacturer step S . The billing status information can be sent on line electronically to the terminal device used by the printer manufacturer or the billing status information could be recorded to a recordable data storage medium such as a CD or DVD that is delivered to the printer manufacturer. As a result all billing status information stored on the main server is transmitted or delivered to the printer manufacturer or the terminal device designated by the printer manufacturer.

Requests from the terminal device of the printer manufacturer do not need to be processed on demand. Alternatively the company X could assemble the billing status information according to a predetermined monthly schedule and send the monthly billing status information to the terminal device designated by the printer manufacturer by a certain date each month for example.

Because an error correction code is automatically added to the billing status information on the in store server in this billing status information collection model data errors can be detected if an error occurs during transmission between the main server and terminal device designated by the printer manufacturer and the accuracy of the data can be assured. Tampering can also be detected and handled appropriately because tampering will cause a mismatch between the error correction code and the content of the billing status information.

The terminal device of the printer manufacturer uses the ink shot count and the ink cartridge ID information in the billing status information for different purposes.

The ink shot count indicates how much ink was used by each printer each month for example and billing is based on this ink shot count.

As shown in two printers were in used as of 2006 Jul. 1. The previous count in each table in is the total ink shot count as of the last tabulation and is 0 in because the billing system was just introduced. The received count is based on the billing status information received by the terminal device designated by the printer manufacturer from the main server company X for the current billing tabulation cycle and the difference is the difference of the received count minus the previous count. The current count is a value corresponding to the ink shot count used by each printer as known to the terminal device designated by the printer manufacturer based on the received count at the current tabulation date and is normally equal to the current received count. This current count becomes the previous count that is the basis for the next tabulation.

Each printer stores the cumulative ink shot count calculated from the start of operation and reports this cumulative ink shot count to the terminal device designated by the printer manufacturer at each tabulation date. As a result ink usage from the previous tabulation date to the current tabulation date is denoted by the difference value in each table.

The total of these differential counts obtained for each printer therefore denotes the total ink usage by company X from the previous tabulation to the current tabulation. The terminal device of the printer manufacturer can therefore determine the billing amount from the previous tabulation to the current tabulation that is the current billing period by multiplying the ink cost per shot times this total ink usage. The terminal device of the printer manufacturer then sends a bill based on this billing amount to the company X and the company X remits payment for the invoiced amount to the printer manufacturer.

The data table in shows that the number of printers has increased from the number of printers reporting in . This is because a new printer was added to the printing system by company X and an ink shot count carrying a printer serial number corresponding to the new printer is transmitted with the billing status information. A new printer record based on this information is therefore added to the data table and the customer is billed based on the total number of ink shots reported by all printers including the new printer.

If billing status information is not reported by a particular printer for some reason such as the printer being turned off when the data is reported the record for that printer is blank as shown in . The difference field is therefore also blank equals 0 not included in the total count and the current count of that printer for the current billing period is the previous count.

When billing status information is received for the same printer the next time the billing status information is reported as shown in the received count is the total ink shot count for two billing periods and the ink usage that was not previously reported or billed for is added to the current billing amount.

This data collection and tabulation process assures that the printer manufacturer can reliably bill the customer for ink usage by each printer even when the printers are located remotely to the printer manufacturer. If billing status information is not received from a particular printer for a certain period of time a problem may have occurred and an inquiry can also be initiated.

The ink cartridge IDs that are sent with the billing status information indicate whether the ink cartridge was positively installed in a printer and whether the ink cartridge was used continuously until it ran out of ink.

In the table shown in the ink cartridge IDs of the ink cartridges shipped to company X by the printer manufacturer are stored together with the shipping date based on the shipping records maintained by the terminal device of the printer manufacturer. Whether an ink cartridge was used or not is recorded based on the ink cartridge IDs contained in the received billing status information. More specifically when the ink cartridge ID of a newly installed ink cartridge or the ink cartridge ID of an out of ink ink cartridge is received the ink cartridge IDs are stored in the date of first use and out of ink date fields. This date of first use and the out of ink date can be approximate dates and if date the billing status information is collected from the printers is included in the billing status information the data collection date can be recorded.

Furthermore if an ink cartridge ID and dates received by the terminal device of the printer manufacturer match a previously received ink cartridge ID and dates the terminal device knows that the ink cartridge ID and dates were already received therefore ignores the ink cartridge ID and dates and records only the ink cartridge IDs and dates that are received for the first time.

By thus compiling this ink cartridge data table the terminal device of the printer manufacturer can determine the status of ink cartridges shipped from the printer manufacturer to company X.

Except for the initial introduction the terminal device of the printer manufacturer can statistically predict the cycle from ink cartridge shipping to use and final collection by the printer manufacturer as data is collected and tabulated. Ink cartridges that deviate from this cycle and are not used or are not recovered by the printer manufacturer even though the cartridge is empty can then be investigated to determine what if any problem there is.

This embodiment of the invention is described with reference to an ink cartridge that contains multiple colors of ink in a single cartridge but the invention is not so limited and can be applied to ink cartridges containing only one color of ink.

The invention is also described using by way of example an inkjet printer and ink cartridge but the invention is not so limited and can be used with laser printers and toner cartridges for example by using a value that can be converted to toner usage such as a charging time instead of the ink shot count.

Identifying each printer that is each printer serial number when billing based on the ink shot count in order to count the total number of ink shots for each printer . Each printer also cumulatively counts the number of ink shots since the printer is first used and the total count since the printer was first used will be lost if the total count buffer is cleared.

If a printer needs repair necessitating replacing the control circuit board containing the flash ROM or other memory device storing the printer serial number and ink shot count the billing status information including the printer serial number ink shot count an ink cartridge ID is preferably read from the circuit board being replaced and written to the new circuit board being installed.

Although the present invention has been described in connection with the preferred embodiments thereof with reference to the accompanying drawings it is to be noted that various changes and modifications will be apparent to those skilled in the art. Such changes and modifications are to be understood as included within the scope of the present invention as defined by the appended claims unless they depart therefrom.


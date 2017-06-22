---

title: Data processing apparatus for page ordering, data processing method, and nontransitory storage medium for same
abstract: A data processing apparatus extracts operators (including particular operators) describing character strings in a text format, at least one by one, from among acquired page data. The data processing apparatus determines an order in which two or more of the page data containing the particular operators whose font information coincides with each other are to be arranged according to a sequence indicated by particular characters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09367525&OS=09367525&RS=09367525
owner: FUJIFILM Corporation
number: 09367525
owner_city: Tokyo
owner_country: JP
publication_date: 20150127
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2014 013114 filed on Jan. 28 2014 the contents of which are incorporated herein by reference.

The present invention relates to a data processing apparatus and a data processing method for carrying out a desired data processing process on a plurality of page data expressed in a page description language and a nontransitory storage medium storing therein a data processing program for enabling a computer to function as a means for performing a data processing process.

Recently in the printing and platemaking fields printing workflows have been digitized in their entirety thanks to the widespread use of desktop publishing DTP and computer to plate CTP technologies. For example there have been a growing number of cases wherein a plurality of designers create page by page contents using respective information processing terminals of their own and then submit the created contents as electronic data to a printing company. It will be convenient for the operator of the printing company if a function to automatically arrange the successively submitted electronic data according to the order of page numbers is available to the operator.

Japanese Laid Open Patent Publication No. 2010 086151 for example discloses an apparatus for identifying page numbers by checking numbers in particular areas of the page extent indicated in scanned images image data in a raster format according to a so called template matching process.

Recently in particular there have been developed various fonts typeface styles that are highly decorative or distinguishable. In addition the number of languages included in contents has been increasing with the globalization of markets.

The apparatus disclosed in Japanese Laid Open Patent Publication No. 2010 086151 has been problematic in that not only the total number of templates to be readied for use is huge but also the greater the number of candidates becomes the lower the accuracy with which to detect page numbers becomes. Particularly an excessively decorative font or a small font is more likely to give false positives.

The present invention has been made in view of the above problems. It is an object of the present invention to provide a data processing apparatus a data processing method and a nontransitory storage medium storing a program for carrying out a page arranging process with a very high accuracy even if the number of types of fonts that are to be used for page numbers is huge.

According to the present invention there is provided a data processing apparatus comprising a page acquirer for acquiring a plurality of page data expressed in a page description language an operator extractor for extracting operators describing character strings in a text format at least one by one from among the page data acquired by the page acquirer an operator classifier for analyzing the operators extracted by the operator extractor and classifying those operators which contain particular characters indicating a sequence in the character strings and whose font information about the character strings coincide with each other as particular operators and a page order determiner for determining an order in which two or more of the page data containing the particular operators classified by the operator classifier are to be arranged according to the sequence indicated by the particular characters.

As described above the data processing apparatus includes the operator extractor for extracting operators including particular operators describing character strings in a text format at least one by one from among the page data and the page order determiner for determining an order in which two or more of the page data containing the particular operators whose font information coincides with each other are to be arranged according to the sequence indicated by the particular characters. Since the data processing apparatus is configured as described above it is possible to easily and reliably judge a commonality in the typeface of page numbers using the font information itself thereby increasing the accuracy with which to detect whether there are page numbers or not and the contents of the page numbers. As a result it is possible to carry out a page arranging process highly successfully even if the number of types of fonts that can be used for page numbers is huge.

The operator classifier should preferably further classify those operators describing the character strings whose positional information coincides with or corresponds to each other.

The operator classifier should preferably further classify those operators describing the character strings whose positions are identified by the positional information belong to margins of pages represented by the page data.

The operator classifier should preferably classify those operators whose font names and font sizes identified by the font information coincide with each other.

The data processing apparatus should preferably further comprise an image generator for generating a page arrangement image representing the order determined by the page order determiner.

According to the present invention there is also provided a data processing method for enabling a computer to execute the steps of acquiring a plurality of page data expressed in a page description language extracting operators describing character strings in a text format at least one by one from among the acquired page data analyzing the extracted operators and classifying those operators which contain particular characters indicating a sequence in the character strings and whose font information about the character strings coincide with each other as particular operators and determining an order in which two or more of the page data containing the classified particular operators are to be arranged according to the sequence indicated by the particular characters.

According to the present invention there is further provided a nontransitory storage medium storing therein a data processing program for enabling a computer to execute the steps of acquiring a plurality of page data expressed in a page description language extracting operators describing character strings in a text format at least one by one from among the acquired page data analyzing the extracted operators and classifying those operators which contain particular characters indicating a sequence in the character strings and whose font information about the character strings coincide with each other as particular operators and determining an order in which two or more of the page data containing the classified particular operators are to be arranged according to the sequence indicated by the particular characters.

According to the present invention as described above operators including particular operators describing character strings in a text format are extracted at least one by one from among the acquired page data and an order in which two or more of the page data containing the particular operators whose font information coincides with each other are to be arranged according to the sequence indicated by the particular characters is determined. Therefore it is possible to easily and reliably judge a commonality in the typeface of page numbers using the font information itself thereby increasing the accuracy with which to detect whether there are page numbers or not and the contents of the page numbers. As a result it is possible to carry out a page arranging process highly successfully even if the number of types of fonts that are to be used for page numbers is huge.

The above and other objects features and advantages of the present invention will become more apparent from the following description when taken in conjunction with the accompanying drawings in which a preferred embodiment of the present invention is shown by way of illustrative example.

A data processing method according to a preferred embodiment of the present invention in relation to a data processing apparatus for carrying out the data processing method and a nontransitory storage medium storing a data processing program will be described in detail below with reference to the accompanying drawings.

As shown in the print production system includes a router serving as a device for connection to a network a server which is accessible through the network from terminal devices not shown belonging to external networks a desktop publishing DTP terminal for performing DTP processes including a process of editing data acquired from the server etc. an imposing apparatus data processing apparatus for imposing contents data processed by the DTP terminal a raster image processor RIP for performing various image processing processes including a rasterizing process a color conversion process etc. on output data imposed by the imposing apparatus a proof press capable of printing a proof based on proofread data sent from the RIP a platesetter for producing printing plates based on platemaking data sent from the RIP and an offset press capable of producing a print with the printing plate set therein.

The server is an apparatus that plays a central role in the workflow management in the print production system . The server is connected to various terminal devices of designers and or production companies not shown for communication therewith through the router and the network . The server is also connected to the DTP terminal the imposing apparatus and the RIP for communication therewith through a LAN Local Area Network constructed in the print production system .

Specifically the server is capable of performing a function as a file server for storing and transferring various data files a function as an authorization management server for managing task authorizations that are available for terminal devices users or print jobs and a function as a mail server for generating and distributing notification mails at certain times such as process starting and ending times.

The data files that can be managed by the server as the file server include contents data printing data e.g. platemaking data printing plate data or proofreading data job ticket files e.g. job definition format JDF files international color consortium ICC profiles color sample data files etc.

The DTP terminal generates page by page image data hereinafter also referred to as page image from contents data representing characters figures patterns pictures etc. which have been processed by a preflight process. The imposing apparatus performs an imposing process according to a binding process and a page folding process which have been designated by referring to the tag information of a job ticket.

The RIP functions as a printing processing server for at least one type of printing press. In the RIP is connected to the proof press and the platesetter for communication therewith. The RIP converts data expressed in a page description language PDL hereinafter also referred to as page data Dp into output data suitable for each output device and supplies the output data to the proof press or the platesetter .

The proof press prints a proof having images formed on a proof sheet print medium on the basis of the proofreading data supplied from the RIP . The proof press may comprise a direct digital color proofer DDCP an ink jet color proofer a low resolution color laser printer electrophotographic printer an ink jet printer or the like.

The offset press produces a print which has images printed on a print sheet print medium by applying inks to one or both surfaces of the print sheet through printing plates and intermediate transfer members not shown. The offset press may be replaced with a digital printing press for direct printing. The digital printing press may comprise an ink jet printing press a wide format printing press an ink jet color proofer a color laser printer or the like.

The communication I F is an interface I F for sending electric signals to and receiving electric signals from external apparatus. The imposing apparatus can acquire various data e.g. submitted files from the server through the communication I F and can supply various data e.g. imposition data to the server through the communication I F .

The display controller comprises a control circuit for controlling the display unit under the control of the controller . Specifically when the display controller outputs a display control signal via an I F not shown to the display unit the display unit is energized to display various images including windows W see .

The memory stores programs and data which are required for the controller to control various components. In the memory stores the submitted files in a PDF format and the imposition data in a JDF format.

The memory may comprise a nontransitory computer readable storage medium. The computer readable storage medium comprises a portable medium such as a magnetooptic disk a ROM a CD ROM a flash memory or the like or a storage medium such as a hard disk or the like incorporated in a computer system. The storage medium may also include a medium for dynamically holding programs for a short period of time or a medium for holding programs for a certain period of time.

The controller comprises a processor such as a CPU Central Processing Unit . The controller reads and executes programs stored in the memory to perform the functions of an imposition processor a display data generator and a rasterization processor .

The imposition processor generates imposition data including an order in which a plurality of page data Dp are to be arranged by analyzing a submitted file acquired in advance. Specifically the imposition processor includes a page acquirer for acquiring a plurality of page data Dp an operator extractor for extracting a text description operator or simply an operator to be described later an operator classifier for classifying text description operators a page order determiner for determining an order in which page data Dp are to be arranged and an imposition data generator for generating imposition data .

The display data generator includes a screen generator for generating display data for an editing screen etc. and an image generator for generating display data for a page arrangement image etc. . The display data may comprise image data generated by application software or various parameters for using an application programming interface API function provide by basic software.

The rasterization processor performs a rasterization process on imposed page data. The rasterization process includes a data format converting process for converting page data from a PDL format to a raster format and a color matching process using ICC profiles.

The input unit comprises various input devices including a mouse a trackball a keyboard a touch sensor etc. The display function of the display unit and the input function of the input unit are combined into a graphical user interface GUI .

The imposing apparatus according to the present embodiment is basically configured as described above. Operation of the imposing apparatus shown in will be described in detail below mainly with reference to a flowchart shown in .

Prior to the operation of the imposing apparatus one or more designers belonging to a production company or the like creates contents of a print and electronically sends the created contents as data files to the print production system . The server receives submitted files through the network the router and the LAN and stores the submitted files in a database. At this time the DTP terminal may perform a desired DTP process on the contents data to edit a plurality of submitted files on a page by page basis in response to an action of the operator.

The server is arranged so as to be capable of sending the submitted files which have been saved therein to a demanding party including the imposing apparatus . When the server sends the submitted files to the imposing apparatus the imposing apparatus receives the submitted files through the LAN and the communication I F and thereafter temporarily stores the submitted files in the memory .

In step S shown in the imposing apparatus displays an editing screen for use in editing a print job. In response to an instruction to start an editing process the screen generator generates display data for the editing screen and supplies the generated display data to the display controller . Based on the display data the display controller controls the display unit to display a window W including the editing screen .

As shown in the editing screen includes a first setting field a second setting field a third setting field a fourth setting field and a button group of two buttons marked CANCEL SAVE respectively. The operator as the user can enter various settings through the setting fields by operating the input unit see .

A button marked ADD is disposed in an upper portion of the first setting field . When the ADD button is clicked on it triggers the addition of a data file to be imposed. In the example shown in the first setting field displays three icons to which respective file names Train.pdf Bus.pdf Giraffe.pdf are given in order from top to bottom. In view of the display icons it is assumed that the submitted files have been selected and added according to the sequence of the icons .

Two buttons marked ADD SORT respectively are disposed in an upper portion of the second setting field . When the ADD button is clicked on it triggers the addition of a page to be read. In the illustrated example the second setting field displays part of the page arrangement image made up of a plurality of thumbnails or more specifically the thumbnails wholly or partly of first through four pages.

A button marked ADD is disposed in an upper portion of the third setting field . When the ADD button is clicked on it triggers the addition of a section of a job structure. The third setting field displays a hierarchical menu which shows all pages six pages in the illustrated example at one hierarchical layer level.

The fourth setting field includes a pull down menu a button group of three buttons marked with SEARCH NEW DOCUMENT EDIT and a double sided template image composed of a face image and a reverse image . In the illustrated example the template image schematically represents a 2 page imposed double sided printing format entitled Custom Template . The format represented by the template image changes in a case where a different template is selected on the pull down menu .

In step S the imposition processor decides whether it has received an instruction to save the settings or not. More specifically the imposition processor decides whether the button group particularly the SAVE button is clicked on or not. If the button group is not clicked on step S NO then control goes to next step S.

In step S the imposition processor decides whether it has received an instruction for automatic arrangement. The term automatic arrangement refers to a process of deciding whether there are page numbers in the plural page data Dp or not analyzing page numbers in the page data Dp and determining an order in which the page data Dp are to be arranged.

The page data Dp on the leftmost end will be described in detail below. The page data Dp represent a page extent containing an illustration that schematically indicates a train in a central portion thereof and a headline indicating Train in an upper left portion thereof. Since a page number indicating 2 is positioned in a lower left portion of the page extent the operator can recognize that the page data Dp correspond to the second page by seeing the page number .

If one designer is in charge of all pages alone then one file is submitted wherein the contents data of all the pages are arranged in a proper order. If a plurality of designers take charge of parts of all pages then a plurality of files are submitted at random irrespectively of the order of the pages.

It is assumed that one submitted file contains contents data of one page in the second setting field . If the contents data are selected in the order of Train.pdf Bus.pdf Giraffe.pdf Car.pdf Dog.pdf and Ostrich.pdf for example then the page numbers are presented in the order of 2 4 7 1 6 and 8 see .

As described above the submitted files may be acquired irrespectively of the page numbers or may be allotted file names not related to the page numbers. Therefore the operator has to open the submitted files one by one and browse and confirm the contents of the page numbers page by page and will find the process tedious and time consuming. An automatic arrangement function to be described later can be performed to greatly reduce the trouble which would otherwise be caused to the operator and hence is highly convenient for the operator.

In step S specifically the imposition processor decides whether the SORT button is clicked on or not. If the SORT button is not clicked on step S NO then control goes back to step S and repeats steps S through S successively. If the SORT button is clicked on step S YES then control goes to next step S.

In step S the page acquirer reads one or two or more submitted files from the memory and acquires a plurality of six in the example shown in page data Dp to be arranged. It is assumed here that the page acquirer acquires a plurality of page data Dp from at least two submitted files .

In step S the operator extractor extracts operators each composed of one or two or more descriptors described in a text format hereinafter also referred to as text description operators or simply operators from each of the page data Dp acquired in step S.

As shown in three operators are extracted from the page data Dp indicated as Train.pdf . The variables of each of the operators include font information positional information position in an arbitrary coordinate system and text contents. The font information represents information that specifies a font of characters and includes for example a font name a font size and decorative information bold italic underline etc. .

The first operator from the top describes a character string whose font name is font A whose font size is 20 unit point whose position is 10 10 unit mm and whose text contents are 2 . The second operator from the top describes a character string whose font name is font B whose font size is 40 whose position is 25 260 and whose text contents are Train . The third operator from the top describes a character string whose font name is font C whose font size is 24 whose position is 50 160 and whose text contents are choo choo .

Similarly the operator extractor successively extracts operators from all of the remaining page data Dp. The operator extractor temporarily stores the extracted operators in association with the page data Dp.

In step S the operator classifier obtains a particular operator that satisfy prescribed descriptive conditions by analyzing and classifying the operators extracted in step S. The prescribed descriptive conditions refer to conditions regarding the positional information the font information etc. of the character strings through .

For example it is known that the page numbers are positioned in margins of pages by nature. Prior to classifying operators therefore the operator classifier may exclude in advance those operators that cannot represent page numbers in view of the positional features of the page numbers .

Referring back to a rectangular shape shown in the broken lines within the page extent represents a border frame for deciding whether an operator is to be excluded or not. The border frame surrounds an area whose dimensions correspond to 15 through 85 of one side x axis direction of the page extent and 15 through 85 of another side y axis direction of the page extent . The operator classifier excludes the operator whose position x y belongs to the area within the border frame leaving the operators whose positions x y belong to the outside margins of pages of the border frame . In the illustrated example the operator classifier excludes only the operator that describes the character string from among the character strings through .

As a result as shown in twelve text description operators are extracted from the six page data Dp. shows a list of page data information and variables of operators see . The page data information refers to information for identifying the page data Dp and specifically represents file names and page numbers inherent in data files for example.

Thereafter the operator classifier classifies operators that simultaneously satisfy the four assessment conditions described below as particular operators . Specific examples of the particular conditions will be described below.

 1 According to the first condition the operator classifier decides whether the text contents contain a character indicating a sequence hereinafter referred to as particular character or not. Since 2 is a particular character the operator describing the character string satisfies the first condition. On the other hand since Train does not contain a particular character the operator describing the character string does not satisfy the first condition.

 2 According to the second condition the operator classifier decides whether there is an overlapping particular character in a plurality of page data Dp or not. In the example shown in since the text contents are 2 4 7 1 6 and 8 there are six operators that do not overlap each other.

A particular character is not limited to a single character but may be made up of a plurality of characters such as 16 or 128 . Text contents may be represented by not only Arabic numerals but also a combination of various characters.

In the third and fourth examples the text contents include numbers 8 in the third example and 1 in the fourth example not indicating page numbers as well as the page numbers. If these numbers are detected in error as page numbers then a process of arranging the page data Dp may possibly fail.

For the above reasons if a character string includes a plurality of particular characters at spaced positions hereinafter referred to as particular character candidates then the operator classifier calculates the degree of coincidence of characters in a plurality of page data Dp to determine one of the particular character candidates. In the third example the operator classifier calculates the degree of coincidence of the first character 1 through 8 and the third character 8 of 1 8 and selects the character first character whose degree of coincidence is the lowest.

 3 According to the third condition the operator classifier decides whether there are a plurality of operators whose font names and font sizes coincide with each other in a plurality of page data Dp or not. In the example shown in there are six operators whose font names are font A and whose font sizes are 20 three operators whose font names are font B and whose font sizes are 40 and three operators whose font names are font C and whose font sizes are 40 .

 4 According to the fourth condition the operator classifier decides whether or not there are a plurality of operators whose positional information coincides with or correspond to each other in a plurality of page data Dp. If the positional information of operators coincides with each other then it means that the positions of the operators are equal to each other or the distance between the operators are smaller than an allowable error e.g. 10 mm. If the positional information of operators corresponds to each other then it means that the operators satisfy a certain positional relationship with each other e.g. symmetry with respect to a central axis.

In the example shown in there are six operators whose positions 30 260 coincide with each other four operators whose positions 10 10 coincide with each other two operators whose positions 200 10 coincide with each other and six operators whose positions 10 10 and positions 200 10 correspond to each other. The positions of the operators are symmetrical with respect to the central axis x 105 of the page extent .

If there are operators that satisfy all the first through four conditions then the operator classifier classifies them as particular operators. In the example shown in six operators whose text contents are 2 4 7 1 6 and 8 are obtained as particular operators.

The particular conditions are not limited to those described above but may be of any types and in any numbers insofar as they can be used to appropriately decide a common format of the page numbers . For example a prescribed percentage including 100 at which particular operators are contained in page data Dp to be arranged may be used as a particular condition.

In step S shown in the page order determiner determines an order in which two or more of the page data Dp containing the particular operators classified in step S are to be arranged according to the sequence indicated by the particular characters. It is assumed here that the page order determiner arranges the six page data Dp in the ascending order of page numbers.

At page number 6 the page data Dp corresponding to the first page of Dog.pdf i.e. the fifth page data Dp from the left in are placed. At page number 7 the page data Dp corresponding to the first page of Giraffe.pdf i.e. the third page data Dp from the left in are placed. At page number 8 the page data Dp corresponding to the first page of Ostrich.pdf i.e. the sixth page data Dp from the left in are placed.

At page number 3 and page number 5 Not available none is set because there are no page data Dp whose text contents correspond to 3 and 5 . According to the above process in a case where page data Dp are added and arranged a plurality of times it is not necessary to update the sequence of the page data Dp which have already been arranged. Therefore the above process is convenient for adding and arranging page data Dp.

After step S control goes back to step S wherein the imposing apparatus updates the displayed contents of the editing screen . Prior to displaying the editing screen the image generator generates a page arrangement image representing the order determined by the page order determiner . Then the screen generator generates display data for an editing screen including the page arrangement image and supplies the generated display data to the display controller . The display controller then controls the display unit to display a window W on the basis of the supplied display data.

As shown in the page arrangement image which is different from the page arrangement image shown in is newly displayed in the second setting field of the editing screen . The page arrangement image shown in includes the thumbnail of Car in the first page the thumbnail of Train in the second page the thumbnail of NONE in the third page and the thumbnail partial of Bus in the fourth page.

A hierarchical menu which is different from the hierarchical menu shown in is newly displayed in the third setting field of the editing screen . The hierarchical menu shown in shows eight pages including the original six pages and two blank pages at one hierarchical layer level.

In step S shown in if the imposition processor decides that the button group particularly the SAVE button in is clicked on then control goes to next step S.

In step S the imposition data generator generates imposition data that represent imposition information finalized in steps S through S. Specifically the imposition data generator generates imposition data including associative information settings in the second setting field that associates the page numbers and the page data Dp with each other. Alternatively the imposition data generator may newly generate or add page data Dp representing a table of contents or an index about the associative information as part of imposition data .

Then the imposition data generator stores and saves the generated imposition data in the memory . Thereafter the imposing apparatus may send out the imposition data through the communication I F in order for the server to keep the imposition data in storage.

The imposing apparatus according to the present embodiment includes the page acquirer for acquiring a plurality of page data Dp expressed in a page description language the operator extractor for extracting operators describing character strings through in a text format at least one by one from among the page data Dp the operator classifier for analyzing the operators and classifying those operators which contain particular characters indicating a sequence in the character strings through and whose font information about the character strings through coincide with each other as particular operators and the page order determiner for determining an order in which two or more of the page data Dp containing the particular operators are to be arranged according to the sequence indicated by the particular characters.

Since the imposing apparatus is configured as described above it is possible to easily and reliably judge a commonality in the typeface of page numbers using the font information itself thereby increasing the accuracy with which to detect whether there are page numbers or not and the contents of the page numbers . Consequently it is possible to carry out a page arranging process highly successfully even if the number of types of fonts that can be used for page numbers is huge.

The present invention is not limited to the embodiment described above but various changes and modifications may be made therein without departing from the scope of the invention.

For example the types of particular characters are not limited to Arabic numerals and Roman numerals described above but may be any characters conjuring up a sequence such as Chinese numerals Indian numerals alphabet etc.


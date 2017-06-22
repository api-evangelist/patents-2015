---

title: Optical disc library apparatus having magazine-disc association information, optical disc, and optical disc library system
abstract: The optical disc library apparatus of the present disclosure includes one or more magazines configured to store a plurality of optical discs, a plurality of optical disc drives configured to perform recording or reproducing on or from the optical discs, a changer mechanism configured to perform loading or ejecting any optical disc stored in the magazine to or from any optical disc drive, and a controller configured to control the changer mechanism. The magazine includes magazine-disc association information associating magazine information specifying the magazine with disc information specifying a plurality of optical discs to be stored in the magazine. The controller outputs the magazine-disc association information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09542971&OS=09542971&RS=09542971
owner: Panasonic Intellectual Property Management Co., Ltd.
number: 09542971
owner_city: Osaka
owner_country: JP
publication_date: 20151120
---
The present disclosure relates to an optical disc library apparatus for taking out a portable optical disc stored in a magazine from the magazine and carrying the optical disc to any optical disc drive an optical disc to be used in the apparatus and an optical disc library system configured by using an optical disc library apparatus.

In recent years an amount of data to be stored in a large scale data center is rapidly increasing and accordingly an amount of less accessed data in the data to be stored also tends to increase. Therefore a library apparatus for archiving less accessed data into a portable information recording medium which is able to reduce power consumption and to be suitable for long period storage attracts attention.

The portable information storage medium is an optical disc such as a DVD Digital Versatile Disc or a Blu ray registered trademark Disc hereinafter BD . The optical disc roughly includes a rewritable information storage medium such as a DVD RAM or a BD RE and a recordable information storage medium such as a DVD R a DVD R or a BD R. Further in recent years a new more large capacity BD disc is being developed.

The optical disc is superior to a hard disc drive HDD or a magnetic tape such as a Linear Tape Open LTO in terms of warranty of the data for fifty years namely semi permanently.

According to the high capacity of the optical disc in recent years a recordable optical disc that is more inexpensive than a rewritable optical disc has a greater opportunity to be used for archiving less accessed data.

As a library apparatus for archiving in an optical disc a library apparatus that includes a plurality of optical disc drives and utilizes a plurality of optical discs which is stored in a cartridge case hereinafter magazine is disclosed for example see Patent Literature 1 . This library apparatus performs recording or reproducing on or from the plurality of optical discs by unit of magazine collectively and transfer speeds of the recording or reproducing can be improved. Further the optical discs are put into the magazine so that the library apparatus can restrain lowering factors in reliability of the optical discs such as fingerprints and scratches.

Further as the library apparatus using the magazine storing the plurality of optical discs a disc array as one virtual large volume is structured in a plurality of optical discs in a magazine and in a plurality of optical disc drives. The library apparatus performs recording or reproducing on or from the disc array i.e. a RAID Redundant Array of Inexpensive Disks . As a result the library apparatus in which recording or reproducing data is highly reliable is disclosed for example see Patent Literature 2 .

Both the above library apparatuses are presupposed that the plurality of optical discs in the magazine is treated in a collective manner and thus are configured with no regard for treating the optical discs and the optical disc drives one by one. However some users desire to treat the plurality of optical discs by unit of magazine in a collective manner but to treat the optical discs one by one for recording or reproducing namely do not desire to treat them by unit of magazine for recording or reproducing in a collective manner. More concretely such users desire to perform recording or reproducing on or from one optical disc in the plurality of optical discs in the magazine independently in the plurality of optical disc drives namely desire to use the library apparatus as a multi accessible apparatus.

Further when the plurality of optical discs is stored in the magazine the library apparatus is not sufficiently considered about a case where a correspondence between the plurality of optical discs and the magazine falls apart. Concretely an abnormal state such that combinations of the plurality of optical discs configuring RAID become unclear is considered a little in the above library apparatuses but the library apparatuses basically presuppose simultaneous formatting and recording on all the optical discs in the magazine. For this reason the abnormal state such that when recorded optical discs and unrecorded optical discs coexist in one magazine combinations of the plurality of optical discs become unclear is not taken into consideration. For this reason in the above library apparatuses ability and reliability of the library apparatuses are not sufficient.

The present disclosure is devised in view of such a problem and its object is to provide an optical disc library apparatus an optical disc and an optical disc library system that when any of a plurality of optical discs stored in a magazine can be taken out and taken in one by one from the magazine and recorded optical discs and unrecorded optical discs coexist in the magazine appropriate combination of the magazine and the optical discs can be restored even if a failure or abnormal stop of the library apparatus occurs.

The optical disc library apparatus of the present disclosure includes one or more magazines configured to store a plurality of optical discs a plurality of optical disc drives configured to perform recording or reproducing on or from the optical discs a changer mechanism configured to perform loading or ejecting any of optical discs stored in the magazine to or from any of optical disc drives and a controller configured to control the changer mechanism. The magazine includes magazine disc association information associating magazine information specifying each magazine with disc information specifying a plurality of optical discs to be stored in each magazine. The controller outputs the magazine disc association information.

In the optical disc library apparatus of the present disclosure where the plurality of optical discs is stored in each magazine and any of the plurality of optical discs can be taken out and taken in each magazine one by one magazine specific Identification ID information specifying the magazines uniquely disc specific ID information specifying all the optical discs stored in each magazine uniquely and position information of the optical discs in each magazine can be managed. For this reason if any trouble such as a failure or abnormal stop of the optical disc library apparatus occurs the optical discs can be returned to the original positions of each magazine. Further when recorded optical discs and unrecorded optical discs coexist in the magazine the optical discs can be returned to original positions of the magazine if a failure or abnormal stop of the optical disc library apparatus occurs.

Exemplary embodiments are described in detail below suitably with reference to the drawings. Description that is detailed beyond necessity is occasionally omitted. For example detailed description about already well known matters and overlapped description about the practically same constitutions are occasionally omitted. This is because the following description is avoided from becoming redundant beyond necessity and a person skilled in the art is made to easily understand the description.

The accompanying drawings and the following description are given in order to make the person skilled in the art to sufficiently understand the present disclosure and they are not intended to limit the subject matter described in Claims.

An optical disc and an optical disc library system according to a first exemplary embodiment are described below with reference to the drawings. Identical components are denoted by identical reference symbols and repetition of the description is omitted.

The present exemplary embodiment presupposes that a plurality of optical discs in a magazine is treated one by one and a plurality of optical disc drives is treated one by one.

Each of tracks is generally formed by combinations of the grooves and lands inter grooves . However in a case of the optical disc such that data in the optical disc is recorded in both the grooves and the lands to improve recording density the address information may be given to one spiral of the grooves and the lands of each of tracks .

A track pitch that is a width of each track is 0.32 m in a case of for example BD. Further each of blocks is a unit of error correction and is a minimum unit in which recording or reproducing operations are performed. In a case of for example DVD each of blocks has a size of 1 ECC size 32 Kbytes and in a case of BD each of blocks has a size of 1 cluster size 64 Kbytes . When a sector size 2 Kbytes that is a minimum unit of data in the optical disc is used ECC 16 sectors and 1 cluster 32 sectors.

Further optical disc is roughly divided into inner periphery area data area and outer periphery area .

Inner periphery area and outer periphery area mainly include areas where management information necessary for the recording or reproducing on or from optical disc is recorded. For this reason inner periphery area and outer periphery area serve as overlap widths when an optical pick up accesses an end of data area and overruns the optical pickup can follow track . Inner periphery area and outer periphery area are areas where user data cannot be recorded or reproduced differently from user data area .

BCA is a prerecording area which includes information relating to optical disc and information specific to optical disc and is formed on a bar code during manufacturing of optical disc by using a special apparatus. BCA is formed by removing a reflective film using a laser. For example information such as a serial number specific to optical disc is stored in BCA .

Drive Area is an area where information necessary for controlling an optical disc drive described later is recorded.

Management information area is an area where management information such as information relating to an area structure of data area in optical disc information relating to a defective block and information representing a recording state of optical disc is recorded transiently.

Inner periphery area includes an Optimum Power Calibration OPC area where a recording power of optical disc drive described later is adjusted and a prewrite area where tracking focus adjustment is made but description thereof is omitted.

Outer periphery area does not need to be always provided. Similarly to inner periphery area management information area an OPC area and a prewrite area may be stored in outer periphery area .

Magazine is not provided with a tray in order to improve an accumulation capacity of optical discs . Optical discs are directly stacked to be stored in magazine in a direct stacking manner. Further magazine is formed by an exterior frame case and a disc storage box and when optical disc is taken out the disc storage box is taken out from the exterior frame case.

The constitution of magazine is one example and magazine may have any mode and shape as long as magazine can store the plurality of optical discs .

As shown in Radio Frequency IDentifier RFID tag for storing information relating to magazine is embedded in an outside of magazine . Further similarly to RFID tag bar code for storing information relating to magazine is stuck to the outside of magazine .

Magazine information is information to be specified during manufacturing of magazine . Magazine information includes magazine specific ID information as information specific to magazine related information about magazine such as a manufacturing date and a manufacturing place of magazine and a number of stored optical discs and the like. In 0123456789 as the magazine specific ID information Dec. 2 2014 as the manufacturing date A factory line as the manufacturing place and 12 as the number of stored discs are stored in magazine information . Magazine information is information which is not rewritten when the information is specified during manufacturing of the magazine.

In the foregoing description magazine information is one example and magazine information may be any information as long as magazine can be identified uniquely by the information.

Information relating to twelve optical discs stored in magazine is stored in disc information . Concretely disc information includes disc specific ID information as serial numbers stored in BCAs of twelve optical discs stored in magazine and position information of twelve optical discs in magazine .

In disc information stores optical disc with disc specific ID information 00110000001 as a first disc on the top of magazine optical disc with disc specific ID information 00110000005 as a second disc optical disc with disc specific ID information 00110000013 as a third disc optical disc with disc specific ID information 00110000024 as a fourth disc optical disc with disc specific ID information 00110000050 as a fifth disc optical disc with disc specific ID information 00110000032 as a sixth disc optical disc with disc specific ID information 00110000102 as a seventh disc optical disc with disc specific ID information 00110000064 as an eighth disc optical disc with disc specific ID information 00110000087 as a ninth disc optical disc with disc specific ID information 00110000022 as a tenth disc optical disc with disc specific ID information 00110000049 as an eleventh disc and optical disc with disc specific ID information 00110000071 as a twelfth disc.

When twelve optical discs are specified in magazine during manufacturing of the magazine disc information cannot be rewritten.

User information can be freely recorded by a user who uses magazine . As user information unfixed or predetermined information is recorded during manufacturing of magazine and any information is recorded according to necessity during use of magazine . For example in magazine ABC is stored as magazine name in user information .

The magazine disc association information of RFID tag includes magazine information disc information and user information . Information for specifying magazine is associated with information for specifying twelve optical discs stored in specified magazine and these pieces of information are recorded so as to be managed by an optical disc library apparatus described later.

The information for specifying magazine and the information for specifying twelve optical discs stored in specified magazine are associated with each other so as to be recorded and recovery is enabled when abnormality occurs. For example in the optical disc library apparatus described later when abnormality occurs during using any optical disc taken out from any magazine or when twelve optical discs stored in any magazine scatter by accident the optical disc library apparatus can recover that stored magazine for optical disc outside of magazine is specified and an original position for optical disc in specified magazine is specified.

Magazine is associated with optical discs in this manner optical discs can be specified for magazine .

The magazine disc association information may include at least the magazine specific ID information of magazine information and the disc specific ID information and the position information of disc information .

Bar code may be a one dimensional bar code of a stripe pattern or a two dimensional bar code such as a QR code registered trademark .

In the present exemplary embodiment both RFID tag and bar code are on an outside of magazine but any one of them may be on an outside of magazine .

In the description the disc specific ID information stores serial number stored in BCA of each of twelve optical discs stored in magazine respectively but such information may be any information specified optical discs uniquely. For example the RFID tags are given specific information with respect to optical discs respectively and the specific information may be the disc specific ID information.

Further during manufacturing of magazine optical disc is preformatted and specific information with respect to optical disc is recorded in a predetermined area of optical disc before optical disc is stored in magazine . This specific information may be recorded as the disc specific ID information of disc information in the magazine disc association information of RFID tag . The specific information with respect to optical disc may be generated by for example combining the magazine specific ID information stored in RFID tag of magazine with the position information of optical disc in magazine . For example the specific ID information of first optical disc may be 012345678901 obtained by combining the magazine specific ID information 0123456789 with the position information 01 and the specific ID information of twelfth optical disc may be 012345678912 obtained by combining the magazine specific ID information 0123456789 with the position information 12 .

The magazine disc association information recorded in RFID tag is not guaranteed semi permanent reading and deterioration progresses with time after final writing and proper data is in danger of not being able to be read after elapsing a predetermined time. For this reason the magazine specific ID information and the position information of optical discs in magazine are recorded as the disc specific ID information in predetermined area of optical disc so that association information of magazine and optical discs can be stored for fifty years namely semi permanently. Further the magazine disc association information stored in RFID tag of magazine associated with optical disc is restored from optical disc and the restored magazine disc association information is again recorded in RFID tag so that data of RFID tag can be recovered.

Optical disc library apparatus includes changer mechanism and twelve optical disc drives . Further a plurality of magazines is attachable to optical disc library apparatus . Each of magazines is configured so as to be detachable from optical disc library apparatus via a drawer and a mail box.

First host I F is an I F for communicating with and controlling changer mechanism of optical disc library apparatus and for example an iSCSI Internet Small Computer System Interface or an USB Universal Serial Bus is used.

Second host I F is an I F for communicating with and controlling twelve optical disc drives of optical disc library apparatus and for example a parallel communication system such as an SAS Serial Attached SCSI an iSCSI an FC Fiber Channel or an SATA Serial ATA is used. Twelve optical disc drives are connected from host server one by one via second host I F so as to be controllable.

Optical disc library apparatus may be provided with an SAS SATA converting substrate host server and optical disc library apparatus are connected by SAS connection and host server and twelve optical disc drives in optical disc library apparatus are connected by STAT connection respectively.

Changer mechanism of optical disc library apparatus is composed of two mechanisms including magazine carrier mechanism and disc carrier mechanism and controller such as a microcomputer for controlling these two mechanisms.

Magazine carrier mechanism selects one magazine from the plurality of magazines based on an instruction from host server and carries selected magazine to optical disc drive . Magazine carrier mechanism includes an RFID reader and a bar code reader not shown in order to read RFID tag of magazine and information of bar code .

Disc carrier mechanism captures twelve optical discs stored in magazine carried by magazine carrier mechanism based on an instruction from host server and loads predetermined one optical disc to predetermined optical disc drive . Further disc carrier mechanism ejects predetermined optical disc from predetermined optical disc drive based on an instruction from host server and returns ejected optical disc to original magazine .

In optical disc library apparatus magazine carrier mechanism and disc carrier mechanism need physical position information representing that twelve optical disc drives are disposed and physical position information representing that the plurality of magazines is disposed for operating. The physical positions of twelve optical disc drives and the physical positions of the plurality of magazines are predetermined.

Stacks for attaching magazines are equipped inside optical disc library apparatus and the plurality of magazines is attached to the stacks respectively. The physical positions of the plurality of magazines are specified at the timing of an initializing process or the timing of setup of optical disc library apparatus .

Controller controls that magazine carrier mechanism reads RFID tags and bar codes for stacks attached with magazine and identifies relation between positions of the stacks and magazine specific ID information of magazines . And controller generates magazine correspondence information for relating the physical positions of magazines with magazine specific ID information of magazines .

Twelve optical disc drives specify physical positions of optical disc drives based on signal information from physical wire connection of optical disc drives .

Drive specific ID information as serial numbers to be uniquely allocated to optical disc drives during manufacturing is used for information of specifying optical disc drives .

Controller generates optical disc drive correspondence information for relating the physical positions of optical disc drives to the drive specific ID information.

The magazine correspondence information and the optical disc drive correspondence information are managed by optical disc library apparatus or host server and controller operates magazine carrier mechanism and disc carrier mechanism based on these pieces of information.

Optical disc library apparatus according to the present exemplary embodiment has a function for notifying host server of information for recovering optical disc library apparatus at a time of abnormal stop and failure.

Concretely optical disc library apparatus has a function for notifying host server of the magazine disc association information stored in RFID tag and bar code via first host I F .

Further optical disc library apparatus has a function for notifying host server of changer specific ID information for specifying changer mechanism as a serial number to be allocated during manufacturing of changer mechanism in order to recover from abnormal stop or a failure. Further optical disc library apparatus has a function for notifying host server of state information about changer mechanism specifically a state whether magazine carrier mechanism captures magazine or not and the magazine specific ID information about magazine captured in a state that magazine carrier mechanism captures magazine .

Further optical disc library apparatus has a function for notifying host server of the drive specific ID information about twelve optical disc drives provided to optical disc library apparatus in order to recover from abnormal stop or a failure. The optical disc library apparatus has a function for notifying host server of state information about optical disc drives specifically a state representing whether optical discs are loaded to optical disc drives or not and disc specific ID information about optical discs loaded in a state that optical discs are loaded to optical disc drives .

Further when information about RFID tag cannot be read or bar code is damaged so as to be incapable of being read optical disc library apparatus cannot notify host server of the magazine disc association information. In order to avoid such a trouble a memory such as a nonvolatile memory is provided to optical disc library apparatus and the same information as RFID tag and bar code may be stored in the memory.

Even when the memory is provided to optical disc library apparatus replacement and repair of parts including the memory occasionally causes erasing of the magazine disc association information stored in the memory.

In view of a cost of magazines RFID tags and bar codes occasionally do not have enough capacities for storing the magazine disc association information.

Further when the magazine disc association information as well as information about all optical discs stored in magazines during manufacturing of magazines is recorded in RFID tags takt times during manufacturing magazines increase and this causes an increase in the manufacturing cost. As a result disc information cannot be occasionally stored in RFID tags .

When controller of optical disc library apparatus has low performance all information about magazines cannot be managed in some cases.

In order to cope with such circumstances optical disc library apparatus has a function for notifying host server of information necessary for obtaining the magazine disc association information. For example an Application Programming Interface API provides a mechanism in which host server obtains the magazine disc association information. As a result it is possible to handle the magazine disc association information with redundancy.

Since optical disc library apparatus has the functions for notifying host server of the magazine disc association information the changer specific ID information and the drive specific ID information via first host I F host server can manage these pieces of information. Further host server is connected to an external memory such as a Solid State Drive SSD or an HDD so as to maintain redundancy.

In the above description memory is a nonvolatile memory but a volatile memory also can achieve the similar effect. For example optical disc library apparatus obtains BCA information as serial numbers of optical discs attached to the magazines corresponding to disc specific ID information and the magazine specific ID information about the attached magazines at any timing so as to be stored in a volatile memory. When a request is received by the API optical disc library apparatus may notify these pieces of information.

Further a magazine manufacturer may manage the magazine disc association information during manufacturing of the magazines. In this case host server accesses a server of the magazine manufacturer via an internet and obtains the magazine disc association information during manufacturing of the magazines.

According to this constitution for example even when RFID tag cannot be read or bar code is damaged the magazine disc association information can be restored by rewriting the magazine disc association information in RFID tag or sticking new bar code because host server retains the magazine disc association information.

Further even when optical disc library apparatus abnormally stops that optical disc stored in magazine from which the magazine disc association information of RFID tag cannot be read is loaded to any optical disc drive host server obtains the state information about optical disc drive and the disc specific ID information about loaded optical disc . And host server checks the pieces of obtained information against the magazine disc association information stored in host server or the magazine disc association information stored in a database of the magazine manufacturer so that host server finds optical disc drive to return the loaded optical disc and recovers.

Even when not the magazine disc association information but only the magazine specific ID information is recorded in RFID tag and bar code host server checks the magazine specific ID information against the magazine disc association information stored in host server or the server of the magazine manufacturer so that optical disc can be specified.

The constitution where host server is connected to optical disc library apparatus via first host I F and second host I F as the host I Fs in the optical disc library system according to the present exemplary embodiment is described but a connecting form is not limited to this form. For example optical disc library apparatus is provided with a CPU board which can control both changer mechanism and optical disc drive host server and optical disc library apparatus may be connected by one host I F so as to be controlled.

In general the changer system and the library system mostly perform respective operations and obtain information in element address unit. An element means a media transfer unit a data transfer unit a storage and the like. For example in optical disc library apparatus changer mechanism as the media transfer unit or one optical disc drive as the data transfer unit is one element. An attention should be paid to the storage. For example since the apparatuses disclosed in the citation list are presupposed that the plurality of optical discs provided to the magazine is treated in a collective manner the magazine is one element as the storage and an element address is given to each magazine. In the present exemplary embodiment one optical disc stored in magazine is one element as the storage and an element address is given to each optical disc . More concretely element addresses are given to the physical positions of twelve optical discs in magazine respectively as an accessible unit. That is to say when twelve optical discs are stored in one magazine twelve element addresses are given to one magazine and when the plurality of magazines is present in optical disc library apparatus element addresses are given to all optical discs of all magazines respectively.

If the element address is changed while in use a host cannot control elements. For this reason optical discs present in optical disc library apparatus should be always given same element addresses. For example a control is made by using the magazine specific ID information included in magazine information provided to RFID tag and the like the position information or disc specific ID information included in disc information shown in so that one element address is given to one optical disc . For example element addresses 0 to 11 are allocated to magazine with the magazine specific ID information 0123456789 and element addresses 12 to 23 are allocated to another magazine . Further as to the position information the element addresses are given to twelve optical discs in magazine with the magazine specific ID information 0123456789 in a manner that element address 0 is allocated to first optical disc 1 is allocated to second optical disc . . . and 11 is allocated to twelfth optical disc .

The present exemplary embodiment described that even when abnormal stop occurs each combination of each magazine and optical discs stored in each magazine and the positions of optical discs in each magazine can be always returned to original positions. In other words also when optical disc library apparatus is brought into an abnormal state during the use of the apparatus determined element addresses can be given to optical discs .

The description refers to the constitution where changer mechanism is constituted so as to have two mechanisms including magazine carrier mechanism and disc carrier mechanism but the present disclosure is not limited to this constitution. For example when magazine is not stored in a direct stack system and optical discs can be taken out one by one from provided trays magazine carrier mechanism is not necessary and only disc carrier mechanism may be provided.

Second host I F may be used for not only a parallel communication system but also a serial communication system. Further changer mechanism may be connected to optical disc drive by the serial communication system. When optical disc drive is a tray type drive it can be controlled separately from second host I F at a time of tray control.

A recovery process at the time of the abnormal stop of optical disc library apparatus is described below. The recovery process in a case where abnormal stop occurs with optical disc being loaded to optical disc drive is described.

 Step S Host server transfers optical disc drive to an activate request of optical disc via second host I F . Optical disc drive receives the activate request from host server so as to activate optical disc . When optical disc is loaded to optical disc drive optical disc is activated but when optical disc is not loaded to optical disc drive optical disc is not activated. Optical disc drive returns a result of the activate request to host server via second host I F . When optical disc drive is activated Good as the result is returned and when optical disc drive is not activated No Disc as the result is returned. Host server can determine whether optical disc is loaded to optical disc drive based on the result of the activate request. When optical disc is loaded to optical disc drive Yes the process proceeds to step and when optical disc is not loaded to optical disc drive No the process is ended.

 Step Host server requests optical disc drive to obtain disc specific ID information about loaded optical disc via second host I F . Optical disc drive reads a serial number stored in BCA of optical disc and returns a disc specific ID number to host server via second host I F .

 Step S Host server requests changer mechanism to obtain the magazine disc association information of RFID tag of magazine via first host I F . Changer mechanism reads the magazine disc association information of RFID tag of any magazine and notifies host server of the read information via first host I F .

The magazine disc association information of RFID tag includes at least the magazine specific ID information the disc specific ID information about stored optical disc and the position information about corresponding optical disc . As described above in optical disc library apparatus instruction is performed at element address unit. However element addresses are not given to magazines . For this reason since twelve elements are present in one magazine the magazine disc association information of RFID tag about magazine is obtained at step in a manner that for example the magazine disc association information of RFID tag about magazine storing an element with element address 0 the magazine disc association information of RFID tag about magazine storing an element with element address 12 and the like are obtained.

 Step S Host server checks whether disc specific ID information that matches with disc specific ID information about optical disc loaded to optical disc drive is present in the obtained magazine disc association information. When the matched disc specific ID information is present Yes the process proceeds to step S and when the matched disc specific ID information is not present No the process returns to step S.

 Step S Host server instructs changer mechanism to return optical disc to original magazine using the magazine specific ID information the disc specific ID information and the position information about optical disc based on the obtained magazine disc association information and the magazine correspondence information via first host I F . Changer mechanism returns optical disc to original magazine .

The description refers to that host server obtains the magazine disc association information of RFID tag of magazine during the recovery process. However a timing of obtaining the magazine disc association information is not limited to this. The information may be obtained before the recovery process such as at a time of powering on optical disc library apparatus .

The description refers to that host server executes the above recovery process for each optical disc drive but the execution of the process is not limited to this. Host server may first determine whether optical discs are loaded to all twelve optical disc drives and may execute step S to step S on all loaded optical discs collectively.

 Step S Host server requests optical disc drives to obtain disc specific ID information about loaded optical discs and magazine disc association information via second host I F . Optical disc drives obtain the disc specific ID information about optical discs and the magazine disc association information and notify host server of the disc specific ID information about optical discs and the magazine disc association information via second host I F .

 Step S Host server requests changer mechanism to obtain the magazine disc association information of RFID tag of any magazine via first host I F . Changer mechanism reads the magazine disc association information of RFID tag of any magazine and notifies host server of the magazine specific ID information about any magazine from the read magazine disc association information via first host I F . Host server obtains the magazine specific ID information.

 Step S Host server checks whether the obtained magazine specific ID information is present in the magazine disc association information. When the magazine specific ID information is present Yes the process proceeds to step S and when the magazine specific ID information is not present No the process returns to step S.

The description refers to that host server obtains the magazine specific ID information from the magazine disc association information of RFID tag of magazine during the recovery process. However a timing of obtaining the magazine specific ID information is not limited to this. The information may be obtained before the recovery process such as at a time of powering on optical disc library apparatus .

The description refers to that the magazine disc association information is stored in RFID tag but the storage is not limited to this. Only the magazine specific ID information may be stored in RFID tag .

The description refers to that host server executes the above recovery process for each optical disc drive but the execution of the process is not limited to this. Host server may first determine whether optical discs are loaded to all twelve optical disc drives and may execute step S to step S and step S on all loaded optical discs collectively.

2 3. Case where the Magazine Disc Association Information of a Server of a Magazine Manufacturer is Used

 Step S Host server obtains magazine disc association information including the obtained disc specific ID information from the server of the magazine manufacturer.

 Step S Host server requests changer mechanism to obtain magazine specific ID information about any magazine via first host I F . Changer mechanism obtains the magazine specific ID information recorded in RFID tag of any magazine and notifies host server of the obtained information via first host I F .

 Step S Host server checks whether the obtained magazine specific ID information matches with disc specific ID information of the magazine disc association information. When the obtained magazine specific ID information matches with the disc specific ID information Yes the process proceeds to step S and when the obtained magazine specific ID information does not match with the disc specific ID information No the process returns to step S.

The description refers to that host server obtains the magazine specific ID information of RFID tag of magazine during the recovery process. However a timing of obtaining the magazine specific ID information is not limited to this. The magazine specific ID information of RFID tag of all magazines may be obtained before the recovery process such as at the time of powering on optical disc library apparatus .

The description refers to that host server executes the recovery process on each optical disc drive but the execution of the process is not limited to this. Host server may first determine whether optical discs are loaded to all twelve optical disc drives and may execute step S step S to step S and step S on all loaded optical disc collectively.

In the optical disc library apparatus according to the present exemplary embodiment when troubles such as a failure and abnormal stop occur in the optical disc library apparatus magazine storing optical discs and locations of optical discs in magazine can be specified so that an original state can be recovered.

Further as a failure and abnormal stop of optical disc library apparatus apparatus occasionally stops with disc carrier mechanism of changer mechanism holding optical disc . As the recovery process in this case after host server obtains the state information of changer mechanism and optical disc held by disc carrier mechanism is loaded to any optical disc drive the recovery process may be executed.

The first exemplary embodiment refers to the presupposition that the positions of twelve optical discs in any magazine are fixed.

A second exemplary embodiment refers to a case where locations of twelve optical discs in any magazine are not fixed. Concretely the description refers to a case where when optical disc taken out of magazine is returned to magazine optical disc is returned to the lowest location in magazine .

In the present exemplary embodiment RFID tag is embedded in magazine and magazine disc association information is stored in RFID tag . In the present exemplary embodiment the magazine disc association information is rewritten every time when actual locations of optical discs in magazine are changed.

In optical disc library apparatus according to the present exemplary embodiment disc information of the magazine disc association information in RFID tag includes the actual position information and when the locations of twelve optical discs in any magazine are not fixed magazine storing optical discs and the locations of optical discs in magazine can be specified even if a trouble such as a failure or abnormal stop occurs in the optical disc library apparatus so that the original state can be recovered.

The present exemplary embodiment refers to that when optical disc returns to magazine the disc is returned to the lowest location but present disclosure is not limited to this. For example optical disc may be returned to the highest location.

The above describes the first to second exemplary embodiments as technical examples of the present disclosure. However a technique in the present disclosure is not limited to the exemplary embodiments and the technique can be applied also to any exemplary embodiments where modifications replacements additions and omissions are carried out. Further the components described in the first and second exemplary embodiments can be combined so that new exemplary embodiments can be formed.

In the first exemplary embodiment and the second exemplary embodiment twelve optical discs are stored in magazine but a number of optical discs is not limited to this and any plural number of optical discs may be stored. Further optical disc is a recordable optical disc but the type of optical disc is not limited to this and it may be a rewritable one.

Further the first exemplary embodiment and the second exemplary embodiment describe that twelve optical disc drives are provided to optical disc library apparatus and twelve optical discs are embedded in magazine but numbers of them are not limited to identical twelve.

The first exemplary embodiment and the second exemplary embodiment describe that one optical disc library apparatus is provided to optical disc library system but a number of optical disc library apparatus is not limited to one. A plurality of optical disc library apparatuses may be connected to host server . Further each of the plurality of optical disc library apparatuses does not include magazine carrier mechanism and one magazine carrier mechanism may be shared by the plurality of optical disc library apparatuses .

Since the above exemplary embodiments illustrate the technique in the present disclosure various modifications replacements additions and omission can be made within the scope of claims or an equivalent scope of claims.


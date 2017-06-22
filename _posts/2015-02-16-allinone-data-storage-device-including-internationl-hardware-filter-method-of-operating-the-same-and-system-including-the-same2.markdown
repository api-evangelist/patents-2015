---

title: All-in-one data storage device including internationl hardware filter, method of operating the same, and system including the same
abstract: A data storage device includes a central processing unit (CPU) executing an application and a hardware filter. A method of operation the data storage device may include initializing the hardware filter based on initialization information corresponding to a changed application when the application is changed so that the hardware filter supports the changed application, filtering read data that is output from a second memory based on filtering condition data, outputting the filtered data using the hardware filter that has been initialized, and transmitting the filtered data to a host via a first memory.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652162&OS=09652162&RS=09652162
owner: Samsung Electronics Co., Ltd.
number: 09652162
owner_city: Suwon-si, Gyeonggi-do
owner_country: KR
publication_date: 20150216
---
A claim of priority under 35 U.S.C. 119 a is made to Korean Patent Application No. 10 2014 0017917 filed on Feb. 17 2014 the disclosure of which is hereby incorporated by reference in its entirety.

Embodiments of the present disclosure relate to a data storage device and more particularly to a device for initializing an internal hardware filter when an application is changed so that the hardware filter supports the application a method of operating the same and a system including the same.

Typically in servers and data server systems including a database a large quantity of data is stored in a relational database or NoSQL Not only SQL database. Data that includes data desired from among the large quantity of data is extracted from the relational database or the NoSQL database using a special purpose programming language such as a structured query language SQL .

The extracted data is transmitted from a database to a main memory of a server and a processor of the server retrieves the data from among the extracted data transmitted to and stored in the main memory. However since only part of the extracted data stored in the main memory of the server is retrieved by the processor of the server the data extraction process from the database is inefficient in terms of data traffic.

Some embodiments of the present disclosure may provide a data storage device capable of initializing an internal hardware filter when an application is changed based on initialization information corresponding to a changed application without replacing the internal hardware filter a method of operating the same and a system including the same.

According to some embodiments of the present disclosure a method of operating a data storage device which includes a central processing unit CPU executing an application and a hardware filter may be provided. The method may include initializing the hardware filter based on initialization information corresponding to a changed application when the application is changed so that the hardware filter supports the changed application filtering read data that is output from a first memory based on filtering condition data outputting the filtered data using the hardware filter that has been initialized and transmitting the filtered data to a host via a second memory.

The initializing the hardware filter may include setting layout data related with a data format supported by the changed application in a register of the hardware filter.

The initializing the hardware filter may include receiving indication data indicating the data format corresponding to the changed application from the host executing the changed application based on the indication data and initializing the hardware filter based on the initialization information that is output from the CPU.

The executing the changed application may include selecting the changed application supporting the data format related with the indication data among a plurality of applications stored in the data storage device and executing the changed application.

The executing the changed application may include generating a confirmation signal indicating whether the data storage device is able to support the changed application supporting the data format related with the indication data transmitting the confirmation signal to the host receiving the changed application that is output from the host based on the confirmation signal and executing the changed application.

The application may be firmware allowing the data storage device to support the data format corresponding to the application.

According to other embodiments of the present disclosure an all in one data storage device may be provided. The all in one data storage device may include a CPU configured to execute an application a first memory configured to output read data in response to a read command an internal hardware filter configured to set layout data corresponding to a data format supported by a changed application based on initialization information that is output from the CPU when the application is changed configured to filter the read data based on the layout data and filtering condition data and configured to output the filtered data a second memory a host controller and a memory controller configured to transmit the filtered data to the host controller using the second memory.

The all in one data storage device may further include a third memory configured to store a plurality of applications. The CPU may select the changed application supporting the data format among the plurality of applications based on indication data which indicates the data format and has been output from a host and the CPU may execute the changed application.

The first memory may be a flash memory and the second memory may be a dynamic random access memory DRAM . The all in one data storage device may be a solid state drive.

According to further embodiments of the present disclosure a data processing system including the above described all in one data storage device and a host configured to control an operation of the all in one data storage device may be provided.

The embodiments of the inventive concepts now will be described more fully hereinafter with reference to the accompanying drawings. The inventive concepts may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the present disclosure to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like numbers refer to like elements throughout.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present. As used herein the term and or includes any and all combinations of one or more of the associated listed items and may be abbreviated as .

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first signal could be termed a second signal and similarly a second signal could be termed a first signal without departing from the teachings of the disclosure.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the present disclosure. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising or includes and or including when used in this specification specify the presence of stated features regions integers steps operations elements and or components but do not preclude the presence or addition of one or more other features regions integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which the present disclosure belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and or the present application and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

The host may control the overall operation of the data storage device A. For example the host may control a write operation a read operation or a filtering operation of the data storage device A. The host may output a filtering command FCMD and a read command RCMD to the data storage device A.

The data storage device A may include a bus a central processing unit CPU a third memory a second memory controller a second memory a first internal hardware H W filter a first memory controller a first memory and a host controller .

The data storage device A may be implemented as an all in one data storage device. For example the data storage device A may be implemented as a solid state drive SSD or a hard disc drive HDD .

The CPU may control the operations of the third memory the second memory controller the first internal H W filter the first memory controller and the host controller . The CPU may execute an application e.g. a database application DB A. At this time the application may be firmware. Here the database application may be a computer program aiming at entering and retrieving information from a computerized database.

In the present disclosure the application is one that can manage data stored in a data storage device which will be described below. The application is described as the concept that includes various kinds of applications that can perform the same function as or a similar function to the database application.

When the application is changed according to a type of data format the first internal H W filter may be reconfigured using information related with the application.

In some embodiments the data storage device A may support a data format e.g. a database format corresponding to the changed application DB A. In other embodiments the changed application DB A may be stored in the first memory or the second memory . In further embodiments the changed application DB A may be stored in the third memory .

When a target application is changed the CPU may transmit initialization information IIM corresponding to the changed application DB A to the first internal H W filter such that the first internal H W filter can support the changed application DB A. In other words the first internal H W filter may be reconfigured using the initialization information IIM.

The CPU may receive the filtering command FCMD from the host interpret or analyze the filtering command FCMD generate filtering condition data FCD based on an interpretation analyzing result and transmit the generated filtering condition data FCD to the first internal H W filter .

In some embodiments the filtering command FCMD may include query or various commands requesting information from a database. In other embodiments the filtering command FCMD may be a vendor specific command. In further embodiments the filtering command FCMD may include the read command RCMD. In other embodiments the filtering condition data FCD may be programmed to the first internal H W filter using the changed application DB A or an application programming interface API .

The CPU may generate a command based on the read command RCMD received from the host and may output the command to the second memory controller .

The third memory may be implemented as a volatile memory or a non volatile memory. The volatile memory may be implemented as a dynamic random access memory DRAM a static RAM SRAM a thyristor RAM T RAM a zero capacitor RAM Z RAM or a twin transistor RAM TTRAM . The non volatile memory device may be implemented as an electrically erasable programmable read only memory EEPROM a flash memory a magnetic RAM MRAM a spin transfer torque MRAM STT MRAM a conductive bridging RAM CBRAM a ferroelectric RAM FeRAM a phase change RAM PRAM a resistive RAM RRAM a nanotube RRAM a polymer RAM PoRAM a nano floating gate memory NFGM a holographic memory a molecular electronics memory device or an insulator resistance change memory.

The second memory controller may generate a first read command RCMD in response to a command that is output from the CPU and may transmit the first read command RCMD to the second memory . The second memory may output first read data RDATA to the first internal H W filter in response to the first read command RCMD. The first read data RDATA may be big data.

The first read data RDATA may include metadata and or data. For example the metadata may include a header an offset and or a pointer. Data in the first read data RDATA may be referred to as a row a record or a tuple. A column in the data may be referred to as a field or an attribute.

The second memory may function as a database that stores data. The second memory may be implemented as the non volatile memory e.g. a NAND flash array.

The first internal H W filter may be adaptively initialized based on the initialization information IIM which corresponds to the changed target application DB A and has been output from the CPU . In other words when a target application is changed the first internal H W filter may support the changed application DB A based on the initialization information IIM corresponding to the changed application DB A. The first internal H W filter that has been initialized may filter the first read data RDATA based on the filtering condition data FCD and may output first filtered data FDATA to the bus .

Since the first internal H W filter is implemented within the data storage device A the first internal H W filter may filter the first read data RDATA and transmit the first filtered data FDATA to the first memory so that the traffic of the first filtered data FDATA transmitted from the second memory to the first memory is minimized.

In addition since the first internal H W filter filters or scans the big data e.g. the first read data RDATA in the vicinity of the second memory the traffic of the big data transmitted from the second memory to the first memory can be decreased.

When the data storage device A is implemented as an SSD and the second memory is implemented as a NAND flash memory the first internal H W filter may be implemented close to the NAND flash memory and therefore data traffic in the SSD can be decreased.

The first memory controller may receive the first filtered data FDATA from the first internal H W filter via the bus and may store the first filtered data FDATA in the first memory . The first memory controller may also read the first filtered data FDATA from the first memory and may transmit the first filtered data FDATA to the host controller via the bus . The first memory may store the first filtered data FDATA. The first memory may be implemented as a volatile memory.

The host and the data storage device A may communicate data or a signal and or a command with each other via the host controller . The host controller may transmit the first filtered data FDATA to the host via a signal line . For example the signal line may be implemented as an electrical signal line or an optical signal line. The signal line may include at least one signal lines.

Referring to data that is output from the host may be stored in the second memory in a data or database format supported by an application. In other words the first read data RDATA may be stored in the second memory in any one of the data storage formats respectively illustrated in .

A first data layout DL stored in a first database e.g. the second memory may be different from a second data layout DL stored in a second database e.g. the second memory . For example positions e.g. storage positions of a header HEADER rows ROW through ROWN where N is a natural number and row offsets OFF through OFFN may vary with data layouts DL through DL. Here each of the rows ROW through ROWN may indicate data.

In addition an increasing direction of an address of the rows ROW through ROWN and an increasing direction of an address of the row offsets OFF through OFFN may vary with the data layouts DL through DL. Accordingly the first internal H W filter may be adaptively initialized based on the initialization information IIM corresponding to the changed application DB A that is output from the CPU so that the first internal H W filter can support a data format or database format e.g. the data layout DL DL or DL corresponding to the changed application DB A.

The control logic may control the overall operation e.g. filtering and or initialization of the first internal H W filter . In other words the control logic may control operations of the configuration register the data buffer the data extractor and the data comparator . The control logic may extract from the initialization information IIM a data layout e.g. layout data L DATA corresponding to a data format supported by the changed application DB A and may set the layout data L DATA in the configuration register .

The configuration register may store the layout data L DATA and may transmit the stored layout data L DATA to the data extractor . The configuration register may be implemented as an SRAM that can function as a data buffer. The layout data L DATA related with the data format supported by a changed application may be set in the configuration register .

Referring to the layout data L DATA may include data PT NR BR BO SO and ADO respectively stored at areas corresponding to addresses ADR through ADR. The data PT corresponding to or stored in an area corresponding to the first address ADR may be address data regarding a field to which a page type is written. The page type may be data for distinguishing an index page from a data page. The data NR corresponding to or stored in an area corresponding to the second address ADR may be address data regarding a field to which the number of rows e.g. data items is written.

The data BR corresponding to or stored in an area corresponding to the third address ADR may be start address data about a start address to which a row or data is written. The data BO corresponding to or stored in an area corresponding to the fourth address ADR may be base address data about a base address to which a row offset is written.

The data SO corresponding to or stored in an area corresponding to the fifth address ADR may be size data regarding a field to which the row offset is written. The data ADO corresponding to or stored in an area corresponding to the sixth address ADR may be data about an address increasing direction of an offset.

Referring to the layout data L DATA may also include data ADR stored at an address ADR of the configuration register . The data ADR corresponding to or stored in an area corresponding to the seventh address ADR may be data about an address increasing direction of a row e.g. data.

In other words the layout data L DATA may include data used to parse data e.g. columns or fields included in a row in the first read data RDATA stored in a data format e.g. data layout supported by the changed application DB A.

When an application is changed the first internal H W filter may set the layout data L DATA corresponding to a data format supported by the changed application DB A based on the initialization information IIM corresponding to the changed application DB A. Accordingly when the application is changed the data storage device A may initialize the first internal H W filter based on the initialization information IIM corresponding to the changed application DB A without replacing or modifying the first internal H W filter .

The data buffer may buffer the first read data RDATA received from the second memory . For example the data buffer may buffer page data. The data buffer may be implemented as an SRAM.

The data extractor may parse columns included in a row of the first read data RDATA using the layout data L DATA and extraction condition data ECD included in the filtering condition data FCD. The data extractor may extract first extraction data FD and second extraction data FD based on a parsing result. The extraction condition data ECD may include identification data TIF for identifying a column and column extraction data QIF for extracting a column that is to be a comparison target.

The data comparator may compare matching key data MKD included in the filtering condition data FCD with the first extraction data FD and may decide whether to output the second extraction data FD as the first filtered data FDATA based on a comparison result.

The register may store the matching key data MKD. The register may be implemented as an SRAM that functions as a data buffer. The matching key data MKD may include type indication data D TYPE indicating a data type an operator indication data C TYPE indicating a type of operator and extraction indication data R DATA indicating data e.g. a column value or a field value that is to be actually extracted.

The data type may be classification for identifying each of various data types. For example the data types may include integers Booleans characters floating point numbers and alphanumeric strings.

The comparator may compare reference data S DATA that is output from the register with the first extraction data FD and may generate a comparison signal CRS based on a comparison result. The comparator may include a plurality of comparators. The reference data S DATA may be generated based on all or part of the matching key data MKD.

The output control circuit may decide whether to output the second extraction data FD in response to the comparison signal CRS. For example when the operator indication data C TYPE indicates equal and the extraction indication data R DATA included in the reference data S DATA is the same as the first extraction data FD the output control circuit may output the second extraction data FD as the first filtered data FDATA. In otherwise cases the output control circuit may not output the second extraction data FD.

Column names i.e. PID NAME and CITY may indicate a column list PERSONS may indicate a table and CITY CITY may indicate a column operator value.

Referring to when an application is changed the CPU may execute the changed application DB A. The CPU may transmit the initialization information IIM corresponding to the changed application DB A to the first internal H W filter .

The first internal H W filter may set the layout data L DATA corresponding to a data format supported by the changed application DB A based on the initialization information IIM. The CPU may receive the filtering command FCMD from the host interpret or analyze the filtering command FCMD generate the filtering condition data FCD based on the interpretation analyzing result and transmit the filtering condition data FCD to the first internal H W filter .

According to the SQL illustrated in the type indication data D TYPE indicates characters the operator indication data C TYPE indicates equal the extraction indication data R DATA indicates a column value of CITY. Also the identification data TIF includes data for identifying a column name PID NAME or CITY to be extracted among column names PID NAME ADDRESS and CITY included in a table TAB. The column extraction data QIF indicates a name i.e. CITY of a column to be extracted.

The second memory may output the table TAB as the first read data RDATA to the first internal H W filter in response to the first read command RCMD. For clarity of the description the table TAB illustrated in includes rows ROW through ROW unlike the data storage formats illustrated in .

The data buffer of the first internal H W filter may receive the table TAB from the second memory and may buffer the rows ROW through ROW included in the table TAB. The data buffer may output the buffered table TAB as the first read data RDATA to the data extractor . In other words the data extractor or may read necessary data from the data buffer .

The data extractor may parse the column names PID NAME ADDRESS and CITY included in the first row ROW based on the identification data TIF the column extraction data QIF and the layout data L DATA. The data extractor may extract column values PID NAME and CITY based on a parsing result.

The data extractor may transmit the column value CITY included in the column CITY in order to be extracted to the comparator as the first extraction data FD. The data extractor may also transmit the second extraction data FD including the column values PID NAME and CITY to the output control circuit .

The comparator may compare the column value CITY included in the reference data S DATA with the column value CITY corresponding to the first extraction data FD and may output the comparison signal CRS indicating an agreement based on a comparison result.

The output control circuit may output the second extraction data FD including the column values PID NAME and CITY to the bus as the first filtered data FDATA in response to the comparison signal CRS indicating the agreement. The first memory controller may store a row ROW including the column values PID NAME and CITY in the first memory .

Continuously the data extractor may parse the column names PID NAME ADDRESS and CITY included in the second row ROW based on the identification data TIF the column extraction data QIF and the layout data L DATA. The data extractor may extract column values PID NAME and CITY based on a parsing result. The data extractor may transmit the column value CITY included in the column CITY in order to be extracted to the comparator as the first extraction data FD. The data extractor may also transmit the second extraction data FD including the column values PID NAME and CITY to the output control circuit .

The comparator may compare the column value CITY included in the reference data S DATA with the column value CITY corresponding to the first extraction data FD and may output the comparison signal CRS indicating a disagreement based on a comparison result. The output control circuit may not output the second extraction data FD including the column values PID NAME and CITY to the bus as the first filtered data FDATA in response to the comparison signal CRS indicating the disagreement.

Continuously the data extractor may parse the column names PID NAME ADDRESS and CITY included in the third row ROW based on the identification data TIF the column extraction data QIF and the layout data L DATA. The data extractor may extract column values PID NAME and CITY based on a parsing result.

The data extractor may transmit the column value CITY included in the column CITY in order to be extracted to the comparator as the first extraction data FD. The data extractor may also transmit the second extraction data FD including the column values PID NAME and CITY to the output control circuit .

The comparator may compare the column value CITY included in the reference data S DATA with the column value CITY corresponding to the first extraction data FD and may output the comparison signal CRS indicating an agreement based on a comparison result. The output control circuit may output the second extraction data FD including the column values PID NAME and CITY to the bus as the first filtered data FDATA in response to the comparison signal CRS indicating the agreement. The first memory controller may store a row ROW including the column values PID NAME and CITY in the first memory .

Continuously the data extractor may parse the column names PID NAME ADDRESS and CITY included in the fourth row ROW based on the identification data TIF the column extraction data QIF and the layout data L DATA. The data extractor may extract column values PID NAME and CITY based on a parsing result. The data extractor may transmit the column value CITY included in the column CITY in order to be extracted to the comparator as the first extraction data FD. The data extractor may also transmit the second extraction data FD including the column values PID NAME and CITY to the output control circuit .

The comparator may compare the column value CITY included in the reference data S DATA with the column value CITY corresponding to the first extraction data FD and may output the comparison signal CRS indicating a disagreement based on a comparison result. The output control circuit may not output the second extraction data FD including the column values PID NAME and CITY to the bus as the first filtered data FDATA in response to the comparison signal CRS indicating the disagreement.

A table TAB generated by the first memory controller may be stored in the first memory . Thereafter the first memory controller may read the table TAB from the first memory and then may transmit the table TAB to the host controller via the bus . The host controller may transmit the table TAB including the column value CITY based on the SQL illustrated in to the host .

The host may control the operation of the data storage device B. When an application is changed the data storage device B may adaptively initialize the first internal H W filter based on the initialization information IIM corresponding to the changed application DB A so that the first internal H W filter can support the changed application DB A.

The host may output to the data storage device B indication data IDA indicating a data format corresponding to the changed application DB A. In other embodiments the indication data IDA may be included in the filtering command FCMD.

The CPU may control operations of the third memory the second memory controller the first internal H W filter the first memory controller and the host controller . The CPU may execute the changed application DB A based on the indication data IDA. For example the CPU may select and execute the changed application DB A that supports a data format related with the indication data IDA among a plurality of applications DB A through DB AN stored in the third memory . In other embodiments the applications DB A through DB AN may be stored in the first memory or the second memory .

When the application is changed the CPU may transmit to the first internal H W filter the initialization information IIM corresponding to the changed application DB A so that the first internal H W filter can support the changed application DB A. The first internal H W filter may set the layout data L DATA corresponding to the data format supported by the changed application DB A based on the initialization information IIM. In other words the first internal H W filter may be adaptively initialized based on the initialization information IIM which corresponds to the changed application DB A and has been output from the CPU .

The host may control the operation of the data storage device C. When an application is changed the data storage device C may adaptively initialize the first internal H W filter based on the initialization information IIM corresponding to the changed application DB A so that the first internal H W filter can support the changed application DB A.

The host may output to the data storage device C indication data IDA indicating a data format corresponding to the changed application DB A. In other embodiments the indication data IDA may be included in the filtering command FCMD.

The CPU may control operations of the third memory the second memory controller the first internal H W filter the first memory controller and the host controller . The CPU may execute the changed application DB A based on the indication data IDA. For example the CPU may generate a confirmation signal IDS indicating whether the data storage device C supports the changed application DB A that supports the data format related with the indication data IDA and the CPU may transmit the confirmation signal IDS to the host .

The CPU may receive the changed application DB A that has been output from the host based on the confirmation signal IDS and may execute the changed application DB A. In other words the host may transmit the changed application DB A to the data storage device C in response to the confirmation signal IDS indicating that the data storage device C cannot support the changed application DB A. In some embodiments the changed application DB A that is output from the host may be stored in the first memory or the second memory . In other embodiments the changed application DB A that is output from the host may be stored in the third memory .

When the application is changed the CPU may transmit to the first internal H W filter the initialization information IIM corresponding to the changed application DB A so that the first internal H W filter can support the changed application DB A. The first internal H W filter may set the layout data L DATA corresponding to the data format supported by the changed application DB A based on the initialization information IIM. In other words the first internal H W filter may be adaptively initialized based on the initialization information IIM which corresponds to the changed application DB A and has been output from the CPU .

Except for the fourth memory and the second internal H W filter A structure and operations of the data storage device D illustrated in may be substantially the same as those of the data storage device A illustrated in . Structure and operations of the second internal H W filter A may be substantially the same as those of the first internal H W filter .

For clarity of the description the two internal H W filters and A respectively corresponding to two memories e.g. an auxiliary memories and are illustrated in but the present disclosure is not restricted to the current embodiments. In other embodiments an internal H W filter may be provided for each channel or each auxiliary memory.

The host may output the filtering command FCMD and the read command RCMD to the data storage device D. The CPU may execute the changed application DB A whenever an application is changed. When the application is change the CPU may transmit to the internal H W filters and A the initialization information IIM corresponding to the changed application DB A so that the internal H W filters and A can support the changed application DB A. The internal H W filters and A may set the layout data L DATA corresponding to a data format supported by the changed application DB A based on the initialization information IIM.

The CPU may receive the filtering command FCMD from the host interpret the filtering command FCMD generate the filtering condition data FCD based on an interpretation result and transmit the filtering condition data FCD to the internal H W filters and A. The CPU may generate a command based on the read command RCMD received from the host and may output the generated command to the second memory controller .

The second memory controller may generate a first read command RCMD and a second read command RCMD in response to the command generated by the CPU and may transmit the first read command RCMD and the second read command RCMD to the second memory and the fourth memory respectively. The second memory may transmit first read data RDATA to the first internal H W filter in response to the first read command RCMD.

The first internal H W filter may filter the first read data RDATA based on the layout data L DATA and the filtering condition data FCD and may output the first filtered data FDATA to the bus . The first memory controller may store the first filtered data FDATA in the first memory .

The fourth memory may transmit second read data RDATA to the second internal H W filter A in response to the second read command RCMD. The second internal H W filter A may filter the second read data RDATA based on the layout data L DATA and the filtering condition data FCD and may output the second filtered data FDATA to the bus .

The first memory controller may store the second filtered data FDATA in the first memory . The first memory controller may transmit the first filtered data FDATA and the second filtered data FDATA to the bus . The host controller may transmit the first filtered data FDATA and the second filtered data FDATA to the host .

The host may output to the data storage device E the indication data IDA indicating a data format corresponding to the changed application DB A. In other embodiments the indication data IDA may be included in the filtering command FCMD.

The CPU may execute the changed application DB A based on the indication data IDA. For example the CPU may select and execute the changed application DB A that supports the data format related with the indication data IDA among a plurality of the applications DB A through DB AN stored in the data storage device E e.g. the third memory . In other embodiments the applications DB A through DB AN may be stored in the first memory or the second memory .

When an application is changed the CPU may transmit to the internal H W filters and A the initialization information IIM corresponding to the changed application DB A so that the internal H W filters and A can support the changed application DB A. The internal H W filters and A may set the layout data L DATA corresponding to the data format supported by the changed application DB A based on the initialization information IIM. In other words the internal H W filters and A may be adaptively initialized based on the initialization information IIM which corresponds to the changed application DB A and has been output from the CPU .

The host may output to the data storage device F the indication data IDA indicating a data format corresponding to the changed application DB A. In other embodiments the indication data IDA may be included in the filtering command FCMD.

The CPU may execute the changed application DB A based on the indication data IDA. For example the CPU may generate a confirmation signal IDS indicating whether the data storage device F supports the changed application DB A that supports the data format related with the indication data IDA and the CPU may transmit the confirmation signal IDS to the host .

The CPU may receive the changed application DB A that has been output from the host based on the confirmation signal IDS and may execute the changed application DB A. In other words the host may transmit the changed application DB A to the data storage device F in response to the confirmation signal IDS indicating that the data storage device F cannot support the changed application DB A. In some embodiments the changed application DB A that is output from the host may be stored in the first memory the second memory or the fourth memory . In other embodiments the changed application DB A that is output from the host may be stored in the third memory .

When an application is changed the CPU may transmit to the internal H W filters and A the initialization information IIM corresponding to the changed application DB A so that the internal H W filters and A can support the changed application DB A. The internal H W filters and A may set the layout data L DATA corresponding to the data format supported by the changed application DB A based on the initialization information IIM. In other words the internal H W filters and A may be adaptively initialized based on the initialization information IIM which corresponds to the changed application DB A and has been output from the CPU .

When an application is changed the CPU may transmit to the one or more internal H W filters and A the initialization information IIM corresponding to the changed application DB A in operation S so that the one or more internal H W filters and A can support the changed application DB A. The one or more internal H W filters and A may set the layout data L DATA corresponding to a data format supported by the changed application DB A based on the initialization information IIM in operation S.

The one or more auxiliary memories and may execute the read commands RCMD and RCMD respectively in operation S and may transmit the read data RDATA and RDATA to the one or more internal H W filters and A respectively in operation S. The one or more internal H W filters and A may respectively filter the read data RDATA and RDATA using the layout data L DATA and the filtering condition data FCD and may respectively store the filtered data FDATA and FDATA in the first memory via the bus and the first memory controller in operation S.

The first memory controller may transmit the filtered data FDATA and or FDATA from the first memory to the host via the bus and the host controller in operation S.

The data storage device may receive the changed application DB A that is output from the host based on the confirmation signal and may execute the changed application DB A in operation S.

The data server system may be a search portal or an internet data center IDC . The clients may communicate with the web servers and via a network . Each of the clients may be implemented as a personal computer PC a laptop computer a smartphone a tablet PC a personal digital assistant PDA or a mobile internet device MID .

The web servers and may communicate with the database servers and via the network . Each of the database servers and may function as the host .

The database servers and may control operations of the databases DB and DB respectively and may access the databases DB and DB respectively. Each of the databases DB or DB may include a plurality of data storage devices .

As described above according to some embodiments of the present disclosure an all in one data storage device including a CPU and an internal H W filter may initialize and use the internal H W filter when an application is changed without replacing the internal H W filter. As a result the all in one data storage device may minimize traffic of data transmitted from non volatile memory to volatile memory.

Since the internal H W filter filters big data near the non volatile memory in the all in one data storage device traffic related with transmission of the big data may be reduced. As a result the all in one data storage device may reduce its internal data traffic.

Since the all in one data storage device filters the big data using the internal H W filter and transmits the filtered data to a host or a server data traffic between the all in one data storage device and the host may be reduced. In addition since the host processes the data that has been filtered by the all in one data storage device the load on the host may be reduced.

While the present disclosure has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in forms and details may be made therein without departing from the spirit and scope of the present disclosure as defined by the following claims.


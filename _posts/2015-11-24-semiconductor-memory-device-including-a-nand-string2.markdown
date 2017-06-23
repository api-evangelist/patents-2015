---

title: Semiconductor memory device including a NAND string
abstract: A semiconductor memory device includes a first NAND string and a second NAND string are connected to a bit line. One of the first and second NAND strings is selected by first to fourth select memory cells. At the write time, data is written in a first memory cell of the first NAND string selected by of the first to fourth select memory cells, then data is written in a second memory cell of the second NAND string selected at the same time as the first memory cell, data is written in a third memory cell adjacent to the first memory cell of the first NAND string and finally data is written in a fourth memory cell of the second NAND string selected at the same time as the third memory cell.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09558828&OS=09558828&RS=09558828
owner: KABUSHIKI KAISHA TOSHIBA
number: 09558828
owner_city: Tokyo
owner_country: JP
publication_date: 20151124
---
This application is a Continuation application of U.S. Ser. No. 14 023 202 filed Sep. 10 2013 which is based upon and claims the benefit of priority from Japanese Patent Application No. 2012 286092 filed Dec. 27 2012 the entire contents of both of which are incorporated herein by reference.

Embodiments described herein relate generally to a semiconductor memory device for example a NAND flash memory capable of storing binary and multi valued data.

A NAND flash memory has a plurality of memory cells arranged in a row direction and connected to a write and read latch circuit via bit lines and data is simultaneously written or read with respect to the memory cells arranged in the row direction.

Further in the NAND flash memory the source and drain diffusion layers of a plurality of memory cells arranged in a column direction are serially connected to configure a NAND string and the NAND string is connected to a bit line through a via.

However recently it becomes more difficult to form vias used for connecting the NAND strings to the bit lines as a device becomes more miniaturized.

In general according to one embodiment a semiconductor memory device includes a first NAND string a second NAND string a bit line a first source line a second source line and a plurality of word lines. The second NAND string includes a plurality of memory cells and first and second select memory cells whose source and drain are serially connected. The first NAND string includes a plurality of memory cells a third select memory cell that is selected at the same time as the first select memory cell and has a threshold voltage different from that of the first select memory cell and a fourth select memory cell that is selected at the same time as the second select memory cell and has a threshold voltage different from that of the second select memory cell the source and drain thereof being serially connected. The bit line is arranged in correspondence to the first and second NAND strings. The first source line is connected to the second NAND string. The second source line is connected to the first NAND string. The plural word lines are used to select plural memory cells that are arranged in a row direction among the plurality of memory cells. At the write time data is written in a first memory cell of the first NAND string selected by the first to fourth select memory cells then data is written in a second memory cell of the second NAND string selected at the same time as the first memory cell data is written in a third memory cell adjacent to the first memory cell of the first NAND string and finally data is written in a fourth memory cell of the second NAND string selected at the same time as the third memory cell.

A memory cell array includes a plurality of bit lines a plurality of word lines and a common source line and for example electrically data reprogrammable memory cells each formed of an EEPROM cell are arranged in a matrix form therein. A bit line control circuit for controlling the bit lines and a word line control circuit are connected to the memory cell array .

The bit line control circuit reads data of a memory cell in the memory cell array via the bit line detects the state of a memory cell in the memory cell array via the bit line and applies a write control voltage to a memory cell in the memory cell array via the bit line to write data in the memory cell. The bit line control circuit is connected to a column decoder and data input output buffer . One of data storage circuits in the bit line control circuit is selected by the column decoder . Data of a memory cell read to the data storage circuit is output to the exterior from a data input output terminal via the data input output buffer . The data input output terminal is connected to a host not shown provided outside the memory chip. The host is configured by for example a microcomputer and receives data output from the data input output terminal . Further the host outputs various types of commands CMD for controlling the operation of the NAND flash memory address ADD and data DT. Write data input from the host to the data input output terminal is supplied to the data storage circuit selected by the column decoder via the data input output buffer and the command and address are supplied to a control signal and control voltage generation circuit .

The word line control circuit is connected to the memory cell array . The word line control circuit selects a word line in the memory cell array and applies a voltage required for reading writing or erasing to the selected word line.

The memory cell array bit line control circuit column decoder data input output buffer and word line control circuit are connected to the control signal and control voltage generation circuit and are controlled by the control signal and control voltage generation circuit . The control signal and control voltage generation circuit is connected to a control signal input terminal and is controlled by control signals ALE Address Latch Enable CLE Command Latch Enable WE Write Enable and RE Read Enable input from the host via the control signal input terminal . The control signal and control voltage generation circuit generates voltages of the word lines and bit lines at the data write time and generates a voltage supplied to a well as will be described later. The control signal and control voltage generation circuit includes for example a booster circuit such as a charge pump circuit and is designed to generate voltages such as a program voltage read voltage and erase voltage.

The bit line control circuit column decoder word line control circuit and control signal and control voltage generation circuit configure a write circuit and read circuit.

For example each NAND string NS is configured by serially connecting 128 memory cells MC first select memory cell SMO second select memory cell SME and select gates S S. Each of memory cells MC first select memory cell SMO and second select memory cell SME is configured by an EEPROM for example. Select gate S is connected to bit line BL BL BLi BLn and select gate S is connected to first source line SRC or second source line SRC .

The control gates of memory cells MC arranged on each row are commonly connected to a corresponding one of word lines WL to WL. The control gate of first select memory cell SMO is connected to select line SGDO and the control gate of second select memory cell SME is connected to select line SGDE. Further select gates S are commonly connected to select line SGD and select gates S are commonly connected to select line SGS.

As indicated by broken lines the memory cell array includes a plurality of blocks. Each block is configured by a plurality of NAND strings NS and for example data is erased in the block unit.

One of two NAND strings NS connected to one bit line is selected by first and second select memory cells SMO and SME and is connected to the bit line. In one of NAND strings NS connected to one bit line a plurality of memory cells memory cells in a range surrounded by broken lines connected to one word line configure one page and a plurality of remaining memory cells connected to one word line also configure one page in the other NAND string.

The data writing and reading operations are performed for each page. That is at the data write or read operation time half of the memory cells among the plurality of memory cells arranged in the row direction are connected to a corresponding bit line. Therefore the write or read operation is performed for each half of the plurality of memory cells arranged in the row direction.

In the write or read operation bit lines BL BL BLio BLno connected to the data storage circuits are selected according to addresses YA YA YAi YAn .

The data write or read operation is performed in the page unit. When one bit is stored in one cell one page is used when two bits are stored in one cell two pages are used when three bits are stored in one cell three pages are used and when four bits are stored in one cell four pages are used. The page is switched according to an address.

Each of NAND strings NS NS is configured by for example serially connecting the source and drain AA of 128 memory cells first select memory cell SMO second select memory cell SME and select gates S S. The drain of select gates S of NAND strings NS NS are connected by a connecting portion and the connecting portion is connected to bit line BL through via or contact plug V. That is bit line BL is connected to first and second NAND strings NS NS through via V in the connecting portion . For example bit line BL is formed of a first layered metal wiring layer M .

Further the source of select gate S of NAND string NS is connected to the source of select gate S of NAND string NS via a connecting portion and the connecting portion is connected to second source line SRC. Further the source of select gate S of NAND string NS is connected to the source of select gate S of NAND string NS via a connecting portion and the connecting portion is connected to first source line SRC.

Additionally Vpass is provided as a voltage applied to the word line of the non selected cell at the data write time and Vread is provided as a voltage applied to the non selected word line at the data read time.

In the sense amplifier unit includes a plurality of N channel MOS transistors that are hereinafter referred to as NMOSs to a plurality of P channel MOS transistors that are hereinafter referred to as PMOSs transfer gates latch circuit and capacitor . For example the latch circuit is configured by clocked inverter circuits 

One end of the current path of NMOS is connected to a node supplied with power source voltage Vdd and the other end thereof is grounded via the transfer gate NMOS and transfer gate . One end of the current path of NMOS is connected to the connection node of NMOS and the transfer gate . The other end of NMOS is connected to bit line BL arranged in the memory cell array. A series circuit of NMOSs and is connected in parallel with NMOS .

Further one end of the current path of PMOS is connected to a node supplied with power source voltage Vdd and the other end thereof is connected to an input terminal of the inverter circuit configuring the latch circuit via PMOS and grounded via NMOS . The input terminal of the clocked inverter circuit that is cross coupled with the inverter circuit is connected to the data control unit DCU via NMOS . Further the gate of PMOS is connected to a connection node of NMOSs and and the connection node is connected to one end of the capacitor . The other end of the capacitor is supplied with clock signal CLK.

The gate of NMOS is supplied with signal BLX. The gate of the NMOS configuring the transfer gate is supplied with signal LAT of the output terminal of the inverter circuit configuring the latch circuit and the gate of the PMOS transistor is supplied with signal INV of the input terminal of the inverter circuit . The gate of NMOS is supplied with signal BLC and the gate of NMOS is supplied with signal BLS.

The gate of PMOS is supplied with signal STB and the gate of NMOS is supplied with reset signal RST. The gate of NMOS is supplied with signal NCO.

When data is written in the memory cell first signal STB is set to a high level reset signal RST is once set to the high level to reset the latch circuit signal LAT is set to the high level and signal INV is set to a low level.

After this signal NCO is set to the high level and data is fetched from the data control unit . When the data is set at the low level 0 indicating writing signal LAT is set to the low level and signal INV is set to the high level. Further when the data is set at the high level 1 indicating non writing data of the latch circuit is kept unchanged signal LAT is held at the high level and signal INV is held at the low level.

Next if signals BLX BLC BLS are set to the high level and when signal LAT of the latch circuit is set at the low level and signal INV is set at the high level writing the transfer gate is turned off and the transfer gate is turned on to set bit line BL to Vss. In this state if the word line is set to program voltage Vpgm data is written in the memory cell.

On the other hand if signal LAT is set at the high level and signal INV is set at the low level non writing in the latch circuit bit line BL is charged to Vdd since the transfer gate is turned on and the transfer gate is turned off. Therefore since the channel of the cell is boosted to a higher potential when the word line is set to Vpgm data is not written in the memory cell.

When data is read from the memory cell first set signal RST is once set at the high level to reset the latch circuit signal LAT is set at the high level and signal INV is set at the low level. Then signals BLS BLC BLX HLL XXL are set to preset voltages to charge bit line BL. At this time Node of the capacitor is charged to Vdd. In this case if the threshold voltage of the memory cell is higher than the read level the memory cell is set in the off state and the bit line is kept at the high level. That is Node is kept at the high level. Further if the threshold voltage of the memory cell is lower than the read level the memory cell is set in the on state and charges of bit line BL are discharged. Therefore bit line BL is set to the low level. As a result Node is set to the low level.

Next since Node is set at the Level if signal STB is set to the low level and when the memory cell is kept on PMOS is turned on signal INV of the latch circuit is set to the high level and signal LAT is set to the low level. On the other hand if the memory cell is kept off signal INV of the latch circuit is set to the low level and signal LAT is kept at the high level.

After this if signal NCO is set to the high level NMOS is turned on and data of the latch circuit is transferred to the data control unit

After the write operation the program verify operation for verifying the threshold voltage of the memory cell is performed substantially similarly to the read operation.

The data control unit shown in includes an operation circuit a plurality of data latch circuits ADL BDL XDL and NMOS .

The operation circuit includes a bus that is hereinafter referred to as IBUS transfer gates connected to both ends of the IBUS and operated in a complementary fashion a latch circuit that latches data of the IBUS and a setting circuit that sets the levels of the data latch circuits ADL BDL XDL according to the data of the latch circuit .

The transfer gate is operated according to complementary signals COND and CONS and connects the bus that is expressed as SBUS of the sense amplifier unit SAU to the IBUS. The transfer gate is operated according to complementary signals COND and CONS and connects the IBUS to the bus that is hereinafter referred to as DBUS to which data latch circuits ADL BDL XDL are connected. When the transfer gate is set on the transfer gate is set off and when the transfer gate is set off the transfer gate is set on.

The latch circuit includes a plurality of PMOSs to a plurality of NMOSs to and inverter circuit . The gates of PMOS and NMOS are supplied with set signal SET and the gate of PMOS is supplied with reset signal REST. The gate of NMOS is supplied with signal IFH and the gate of NMOS is supplied with signal IFL. The gate of NMOS is connected to the IBUS via the inverter circuit and the gate of NMOS is connected to the IBUS.

The setting circuit includes PMOSs to and NMOSs to . The gates of PMOS and NMOS are supplied with signal FAIL. Signal FAIL is a signal of a connection node of PMOS and NMOS used as one of the output terminals of the latch circuit . The gates of PMOS and NMOS are supplied with signal MTCH. Signal MTCH is a signal of a connection node of PMOS and NMOS used as the other output terminal of the latch circuit . Further the gate of PMOS is supplied with signal MHB and the gate of PMOS is supplied with signal FHB. The gate of NMOS is supplied with signal FL and the gate of NMOS is supplied with signal ML.

Data latch circuits ADL BDL XDL have the same configuration and each include a latch circuit and a transfer gate that connects the latch circuit to the DBUS. The transfer gates are controlled by signals BLCA BLCA B signals BLCB BLCB B and signals BLCX BLCX B. Data latch circuit XDL is connected to an external IO via NMOS . The gate of NMOS is supplied with signal CSL.

As described before the data control unit holds write data and holds data read from the memory cell at the read time.

For example 2 bit write data supplied from the data input output buffer is latched for each bit in for example data latch circuits ADL BDL via data latch circuit XDL.

The operation circuit shown in can perform the operation of AND OR exclusive NOR and the like with respect to data of data latch circuits ADL BDL. For example in the case of the AND operation data held in data latch circuits ADL BDL is output to DBUS and IBUS. In this case IBUS is set to the high level only if data items held in data latch circuits ADL BDL are both and is set to the low level in the other cases. That is IBUS becomes 1 only at the non written time and IBUS becomes 0 at the written time. The data is transferred to the sense amplifier unit shown in via SBUS to perform the write operation.

The operation of the operation circuit can be variously modified and for example various control methods can be applied to one logical operation and the control method can be changed as required.

As shown in data of the memory cell is set to a threshold voltage of 11 by the erase operation. If data of the first page is written the memory cell is kept in the erase state or level LMV is written therein and data of the memory cell is set to a threshold voltage of 11 or 10.

As shown in if data of the second page is written one of the levels of AV BV and CV is written in the memory cell while the memory cell is kept in the erase state and data of the memory cell is set to a threshold voltage of 11 01 00 10. The verify level at the write time is set at a level slightly higher than the level at the read time since it is required to provide a data retention margin. In the read level is expressed by LMR AR BR CR and the verify read level is expressed by LMV AV BV CV.

In the erase operation first word lines WL to WL of a selected block BLK and select lines SGDO SGDE connected to the first and second select memory cells are set to 0 V the word lines of non selected blocks and select lines SGDO SGDE are made to float and the well having the memory cell array formed therein is set to erase voltage VERA. As a result the memory cells in the selected block and first and second select memory cells SMO SME are set in the erase state ST .

After this the first select memory cell SMO and second select memory cell SME are selectively written to permit one of the two NAND strings connected to each bit line in the selected block to be freely selected.

For example if the two NAND strings connected to one bit line BL shown in are defined as first NAND string NS and second NAND string NS first select memory cell SMO of first NAND string NS is set in the written state second select memory cell SME thereof is set in the non written state first select memory cell SMO of second NAND string NS is set in the non written state and second select memory cell SME thereof is set in the written state.

Specifically first and second select memory cell SME of second NAND string NS in the selected block is selectively written to enhance the threshold voltage. At this time it is supposed that first select memory cell SMO is set in the non written state. Further first select memory cell SMO and second select memory cell SME of first NAND string NS are also set in the non written state ST . Therefore first source line SRC is set to for example Vss ground voltage second source line SRC is set to Vdd power source voltage select line SGD is set to Vss select line SGS is set to VSGD Vdd Vth Vth is the threshold voltage of the MOS transistor select line SGDE connected to second select memory cell SME is set to Vpgm program voltage select line SGDO connected to first select memory cell SMO is set to Vpass intermediate voltage and word lines WL to WL are set to Vpass to write second select memory cell SME.

Next first select memory cell SMO of first NAND string NS in the selected block is selectively written to enhance the threshold voltage. At this time it is supposed that second select memory cell SME is set in the non written state. Further first select memory cell SMO and second select memory cell SME of second NAND string NS are also set in the non written state ST . Therefore first source line SRC is set to Vdd second source line SRC is set to Vss select line SGD is set to Vss select line SGS is set to VSGD select line SGDE connected to second select memory cell SME is set to Vpass select line SGDO connected to first select memory cell SMO is set to Vpgm and word lines WL to WL are set to Vpass to write first select memory cell SMO.

The threshold voltages of second select memory cell SME of second NAND string NS and first select memory cell SMO of first NAND string NS that are written are set to threshold level LMV shown in or more for example.

In first and second select memory cells SMO SME surrounded by broken lines are set in the written state and the other first and second select memory cells SMO SME are set in the non written state erase state . That is every two of first and second select memory cells SMO SME are alternately written in the row direction.

One of the two NAND strings connected to one bit line can be selected according to the potentials of select lines SGDO SGDE by thus setting the threshold voltages of first and second select memory cells SMO SME.

In this embodiment the select memory cells are erased at the erase time of the selected block and then the write operation is performed. However the write operation can be performed for the select memory cells of the blocks to set the preset threshold voltage of the memory cells before shipment and the threshold voltages of the select memory cells can be inhibited from being erased at the block erase time after shipment. If the above operation is performed it is possible to omit the write operation with respect to the select memory cells at the erase time of each block.

In a case where the select memory cells of the blocks are written to have the preset threshold voltage in the process before shipment and the threshold voltages of the select memory cells are inhibited from being erased at the block erase time after shipment the threshold voltages of the select memory cells are checked at the erase time of each block and if the threshold voltage is not set at a preset level the select memory cell may be erased and written to set the threshold voltage of the select memory cell to the preset threshold voltage level.

As described above data writing can be performed with respect to the memory cell after the erase sequence is completed. Data writing is sequentially performed starting from word line WL that is set close to first and second source lines SRC SRC towards word line WL set close to the bit line.

One of the two NAND strings connected to one bit line is selected and data is written therein. In this case memory cells contained in NAND strings NS NS NS NS . . . shown in are defined as odd numbered memory cells and memory cells contained in NAND strings NS NS . . . are defined as even numbered memory cells.

The write operation is performed by taking the coupling capacitance between adjacent memory cells into consideration. Therefore first the program sequence of the first page is executed with respect to even numbered NS NS . . . memory cells connected to word line WL ST . The program sequence includes data writing program and write verify program verify read operations. After writing the write verify operation is performed. If the write operation is insufficient the write operation is performed again and the write and write verify operations are repeatedly performed to set a preset threshold voltage in the memory cell.

Next the program sequence of the first page is executed with respect to odd numbered NS NS NS NS . . . memory cells connected to word line WL ST . Then the program sequence of the first page is executed with respect to even numbered NS NS . . . memory cells connected to adjacent word line WL ST . Subsequently the program sequence of the first page is executed with respect to odd numbered NS NS NS NS . . . memory cells connected to word line WL ST .

After this the program sequence of the second page is executed with respect to even numbered NS NS . . . memory cells connected to word line WL ST . Next the program sequence of the second page is executed with respect to odd numbered NS NS NS NS . . . memory cells connected to word line WL ST . Then the program sequence of the first page is executed with respect to even numbered NS NS . . . memory cells connected to word line WL ST . Further the program sequence of the first page is executed with respect to odd numbered NS NS NS NS . . . memory cells connected to word line WL ST . Thus the write operation is controlled.

Data of one page among data to be written in the memory cells is stored in data latch circuit XDL that configures the data storage circuit shown in .

In this case select line SGD is set to VSGD select line SGS is set to Vss select lines SGDE SGDO are set to VON a voltage for example Vread that can turn on first and second select memory cells SMO SME in the written state and the bit line is set to Vdd.

Next a to be written NAND string containing even numbered memory cells is connected to the bit line ST .

In this case select line SGD is set to VSGD select line SGS is set to Vss select line SGDE is set to VON and select line SGDO is set to VOFF a voltage for example Vss that can turn off first and second select memory cells SMO in the written state . The bit line is set to Vdd when write data is 1 and set to Vss when write data is 0.

After this first source line SRC is set to VthD for example the threshold voltage of the depletion type NMOS transistor second source line SRC is set to Vdd program voltage Vpgm is applied to word line WL and Vpass is applied to the non selected word lines ST . Thus data is written in the even numbered memory cells connected to word line WL. After this a program verify operation not shown is performed and the write operation is performed again if the voltage is lower than the target threshold voltage.

First the NAND strings in the selected block are charged ST like the write operation of the even numbered memory cells.

In this case select line SGD is set to VSGD select line SGS is set to Vss select lines SGDE SGDO are set to VON and the bit line is set to Vdd.

Next a to be written NAND string containing odd numbered memory cells is connected to the bit line ST .

In this case select line SGD is set to VSGD select line SGS is set to Vss select line SGDE is set to VOFF and select line SGDO is set to VON. The bit line is set to Vdd when write data is 1 and set to Vss when write data is 0.

After this first source line SRC is set to VthD for example the threshold voltage of the depletion type NMOS transistor second source line SRC is set to Vdd program voltage Vpgm is applied to word line WL and Vpass is applied to the non selected word lines ST . Thus data is written in the odd numbered memory cells connected to word line WL. After this a program verify operation not shown is performed and the write operation is performed again if the voltage is lower than the target threshold voltage.

In the case of the program sequence shown in since the odd numbered memory cells are written after the even numbered memory cells are written there occurs a possibility that the threshold voltage of the even numbered memory cells that are previously written will vary.

In this modification the program operation for even numbered NS NS . . . memory cells the program operation for odd numbered NS NS NS NS . . . memory cells the program verify read operation for even numbered NS NS . . . memory cells and the program verify read operation for odd numbered NS NS NS NS . . . memory cells are performed in one program sequence. Further the write verify operation is performed after writing the write operation is performed again if the write operation is insufficiently performed the write and write verify operations are repeatedly performed to write data of one word line to a preset threshold voltage and then the program sequence for a next word line is executed.

That is the program sequence of the first page is executed for the memory cells connected to word line WL ST and then the program sequence of the first page is executed for the memory cells connected to word line WL ST . Next the program sequence of the second page is executed for the memory cells connected to word line WL ST and then the program sequence of the first page is executed for the memory cells connected to word line WL ST . Further the program sequence of the second page is executed for the memory cells connected to word line WL ST .

If the above program sequence is used the threshold voltage of the memory cells can be prevented from being varied.

Like the write operation in the read operation data items in even numbered memory cells and odd numbered memory cells connected to the word line are separately read.

As shown in when data of the even numbered memory cells is read select lines SGD SGS are set to VSG select line SGDE is set to VON select line SGDO is set to VOFF and preset potential VBL is applied to the bit line. Further first and second source lines SRC SRC are both set to VSRC for example 1 V . At this time as shown in the selected word line is set to one of read levels of LMR AR BR CR according to to be read data. Further the non selected word line is set to Vread and the read operation is performed ST .

When the threshold voltage of the memory cell is lower than the level of the word line the memory cell is turned on and the potential of the bit line is set to the low level. When the threshold voltage of the memory cell is higher than the level of the word line the memory cell is turned off and the potential of the bit line is held at the high level. The voltage of the bit line is read by the data storage circuit .

On the other hand when data of the odd numbered memory cells is read select lines SGD SGS are set to VSG select line SGDE is set to VOFF select line SGDO is set to VON and preset potential VBL is applied to the bit line. Further first and second source lines SRC SRC are both set to VSRC. At this time as shown in the selected word line is set to one of read levels of LMR AR BR CR according to to be read data. Further the non selected word line is set to Vread and the read operation is performed ST .

According to the first embodiment adjacent two NAND strings are connected to the bit line through one via. Therefore the number of vias can be reduced and adjacent two NAND strings can be connected to the bit line even when the cell is miniaturized.

Further each NAND string includes first and second select memory cells SMO SME. Therefore one of the adjacent two NAND strings can be set in the selected state and the other NAND string can be set in the non selected state by the first and second select memory cells SMO SME and one or the other of the two NAND strings can be selected.

Further one of the adjacent two NAND strings is connected to the first source line and the other NAND string is connected to the second source line. Therefore first and second select memory cells SMO SME of the adjacent two NAND strings can be selectively written.

As shown in first and second NAND strings NS NS are alternately selected and data is sequentially written in the memory cells from the memory cells on the side of source lines SRC SRC. Therefore the threshold voltage of the memory cell can be prevented from being varied.

In the first embodiment first and second select memory cells SMO SME in the selected block are written after the erase operation but the verify operation is not performed.

In the second embodiment after first and second select memory cells SMO SME are written the verify operation is performed and the distribution range of the threshold voltages of first and second select memory cells SMO SME is narrowed by repeatedly performing the write and verify operations until the threshold voltages of first and second select memory cells SMO SME reach the verify level.

That is as shown in the selected block is erased ST and second select memory cell SMO is written ST . Then the verify read operation is performed ST . Next whether or not the write operation is sufficiently performed is verified based on read data ST . If it is detected as the verify result that second select memory cell SME that is not sufficiently written is present the above second select memory cell SME is written again ST . Thus the operation of steps ST ST ST is repeatedly performed until the verify result becomes OK.

Specifically in step ST first source line SRC is set to Vss second source line SRC is set to Vdd select line SGD is set to Vss and select line SGS is set to VSGD. Further the bit line connected to the memory cell to be selected by select line SGDE is set to the low level and the bit line connected to the memory cell to be selected by select line SGDO is set to the high level.

After this select line SGS is set to Vss from VSGD select line SGD is set to approximately 0.6 V from Vss and bit line BL is set to Vss. Then if the bit line corresponding to select line SGDE that sets the non written state is set to Vdd data from Vss second select memory cell SGD connected to the above bit line is turned on and potential Vdd is supplied to the drain of first select memory cell SGDO that is set in the non written state.

Subsequently after select line SGD is set to Vss from approximately 0.6 V select line SGDE is set to Vpgm select line SGDO is set to Vpass and word lines WL to WL are set to Vpass. Then only second select memory cell SME that is connected to the select line SGDE is written.

After this in step ST the verify read operation is performed for second select memory cell SME. The sequence of the verify read operation is the same as that of the read operation.

Next in step ST the result of verify read is determined and second select memory cell SME that is insufficiently written is written.

Further like the case of second select memory cell SME first select memory cell SMO is written ST and subjected to the verify read operation ST and the result of verify read is determined ST . If it is detected as the determination result that first select memory cell SMO that is not sufficiently written is present the operation of steps ST ST ST is repeatedly performed.

According to the second embodiment the verify read operation is performed after first select memory cell SMO and second select memory cell SME are written and if first or second select memory cell SMO SME that is not sufficiently written is present the corresponding memory cell is written again. Therefore the distribution range of the threshold voltages of first and second select memory cell SMO SME can be narrowed and first and second select memory cell SMO SME can be stably selected.

In the first and second embodiments first and second select memory cells SMO SME select lines SGDO SGDE and first and second source lines SRC SRC are provided and even numbered or odd numbered memory cells connected to the word line can be selected by selectively writing first and second select memory cells SMO SME after erasing.

On the other hand in the third embodiment as shown in and first and second select memory cells SMO SME select lines SGDO SGDE and first and second source lines SRC SRC are not used and first and second select gates S S used as select gate S that connects the bit line to the NAND string and first and second select lines SGD SGD connected to first and second select gates S S are provided and one source line SRC is further provided.

For example two NAND strings NS NS adjacent to bit line BL are connected to the bit line in a connecting portion that connects the drain of first select gates S S thereof. Further for example two NAND strings NS NS adjacent to bit line BL are connected to bit line BL in a connecting portion that connects the drain of first select gates S S thereof.

The source of two select gates S S that connect source line SRC used as the cell source to NAND strings NS NS are connected in a connection portion . The connecting portion is connected to source line SRC. Further the source of two select gates S S that connect source line SRC to NAND strings NS NS are connected in a connection portion . The connecting portion is connected to source line SRC.

First and second select gates S S provided in the respective NAND strings are formed to have an enhancement type E type and depletion type D type by ion implantation. That is first and second select gates S S surrounded by broken lines shown in and are of the E type and the other first and second select gates S S are of the D type.

Further the broken lines shown in and show openings of a mask used for ion implantation. First opening A corresponds to first select gate S and second opening A corresponds to second select gate S. First opening A also corresponds to first select gate S of an adjacent block and has an area larger than that of second opening A.

When attention is paid to a plurality of first and second select gates S S connected to first and second select lines SGD SGD it is understood that every two of the D type and E type of a plurality of first select gates S connected to first select line SGD are alternately arranged in a row direction. Further every two of the D type and E type of a plurality of second select gates S connected to second select line SGD are alternately arranged in the row direction.

When attention is paid to a plurality of first and second select gates S S contained in two NAND strings NS NS connected to bit line BL it is understood that first select gate S of NAND string NS is of the D type and second select gate S is of the E type. Further first select gate S of NAND string NS is of the E type and second select gate S is of the D type.

With the above configuration if first select line SGD is set to the low level and second select line SGD is set to the high level second select gate S of the E type connected to second select line SGD is turned on. Further since first select gate S of the D type connected to first select line SGD is set in the on state NAND string NS is connected to bit line BL and NAND string NS is connected to bit line BL.

Further if first select line SGD is set to the high level and second select line SGD is set to the low level first select gate S of the E type connected to first select line SGD is turned on. Further since second select gate S of the D type connected to second select line SGD is set in the on state NAND string NS is connected to bit line BL and NAND string NS is connected to bit line BL.

Thus one or the other of the two NAND strings connected to one bit line can be selectively connected to the bit line by first and second select lines SGD SGD by arranging first and second select gates S S of the D type and E type.

According to the third embodiment the drain of adjacent NAND strings NS NS are connected by the connecting portion the drain of adjacent NAND strings NS NS are connected by the connecting portion the connecting portion is connected to bit line BL and the connecting portion is connected to bit line BL. Therefore even when the device is miniaturized the number of bit line contacts can be suppressed from being increased.

Further every two of a plurality of first select gates S connected to first select line SGD and a plurality of second select gates S connected to second select line SGD are alternately set to the D type and E type in the row direction and first and second select gates S S used for selecting two NAND strings connected to one bit line are alternately set to the D type and E type. Therefore two NAND strings connected to one bit line can be selected without writing first and second select gates S S after erasing. Therefore the erase sequence can be simplified.

In the case of the third embodiment first and second select gates S S are formed to have the E type and D type by ion implantation using a mask. As described before second opening A for second select gate S is formed to have an area smaller than that of first opening A for first select gate S. Therefore the number of lithography steps is increased and the manufacturing cost is increased.

Therefore as shown in and in the fourth embodiment first select gate S of one of the two NAND strings connected to one bit line is formed with the E type and the other first select gates S and second select gates S are formed with the D type.

Further as shown in and first select memory cells SMO connected to select line SGDO are provided. As shown in the first and second embodiments first select memory cells SMO are written two at a time in the row direction after erasing and the threshold voltages thereof are set. In and first select memory cells SMO surrounded by broken lines indicate written memory cells. That is data is written in first select memory cell SMO of the NAND string in which first select gate S is not set to the E type among the two NAND strings connected to one bit line.

With the above configuration if select line SGD is set to the high level and select lines SGD SGD are set to the low level first select gate S of the E type is turned on and first select memory cell SMO that is written is turned off. Therefore NAND string NS is connected to bit line BL and NAND string NS is connected to bit line BL.

Further if select line SGD is set to the low level and select lines SGD SGD are set to the high level first select gate S of the E type is turned off and first select memory cell SMO that is written is turned on. Therefore NAND string NS is connected to bit line BL and NAND string NS is connected to bit line BL.

According to the fourth embodiment since opening A for second select gate S becomes unnecessary the lithography process can be simplified and the manufacturing cost can be reduced.

While certain embodiments have been described these embodiments have been presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel embodiments described herein may be embodied in a variety of other forms furthermore various omissions substitutions and changes in the form of the embodiments described herein may be made without departing from the spirit of the inventions. The accompanying claims and their equivalents are intended to cover such forms or modifications as would fall within the scope and spirit of the inventions.


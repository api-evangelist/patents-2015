---

title: Memory device having resistance change element and method of controlling the same
abstract: According to one embodiment, a memory device includes a semiconductor layer connected between a first conductive line and one end of a third conductive line, resistance change elements connected between second conductive lines and the third conductive line respectively, a select FET having a select gate electrode, and using the semiconductor layer as a channel, and a control circuit executing a write/erase of at least one of the resistance change elements, and executing a recovering operation which adjusts a threshold voltage shift of the select FET after the write/erase.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09472283&OS=09472283&RS=09472283
owner: KABUSHIKI KAISHA TOSHIBA
number: 09472283
owner_city: Minato-ku
owner_country: JP
publication_date: 20150204
---
This application is a continuation of U.S. application Ser. No. 14 025 146 filed on Sep. 12 2013 and is based upon and claims the benefit of U.S. Provisional Application No. 61 823 026 filed on May 14 2013 the entire contents of each of which are incorporated herein by reference.

Embodiments described herein relate generally to a memory device and a method of controlling a memory device.

Recently there has been proposed a memory called a resistive RAM ReRAM in which a memory cell is formed by a resistance change material. A memory cell of a ReRAM is expected to be highly integrated beyond a conventional trend.

In general according to one embodiment a memory device comprising a first conductive line extending in a first direction second conductive lines each extending in a second direction intersect with the first direction a third conductive line extending in a third direction intersect with the first and second directions resistance change elements connected between the second conductive lines and the third conductive line respectively a semiconductor layer connected between the first conductive line and one end of the third conductive line a select FET having a select gate electrode and using the semiconductor layer as a channel and a control circuit which is configured to execute a write erase of at least one of the resistance change elements and execute a recovering operation which adjusts a threshold voltage shift of the select FET by setting the first conductive line to a first potential setting the select gate electrode to a second potential setting all of the second conductive lines connected with the resistance change elements to a single third conductive line to a third potential and setting at least one of the first potential or the third potential to higher than the second potential after the write erase.

A plurality of global column lines row lines and column lines is provided within a memory cell array. The global column lines are formed in parallel to each other along a first direction and for example are disposed in the lowermost layer of the memory cell array. The row lines are formed in parallel to each other along a second direction perpendicular to the first direction and are provided at positions higher than the global column lines in a third direction perpendicular to the first and second directions. Layers of the row lines first layer second layer third layer . . . of are provided plurally in the third direction normal direction of a surface on which the global column lines are disposed .

The column lines extend along the third direction between the adjacent row lines and are disposed plurally in the first and second directions. One end lower end of the column line is electrically connected to any one of the global column lines . More specifically in a two dimensional plane formed in the first direction and the second direction the column lines disposed on the same column along the first direction are electrically connected to the same global column line .

A memory cell MC including a resistance change element is formed between each of the row lines and each of the column lines . In the present example a resistance change material is formed on an entire surface of a side surface of the column line surface facing the row line . A part of the resistance change material disposed between the column line and the row line functions as the memory cell MC.

Also of the two sets facing side surfaces of the bit line the resistance change material in the present example is provided on two side surfaces facing in the first direction two side surfaces facing the row line and is not provided on two side surfaces facing in the second direction two side surfaces not facing the row line .

A select element sheet selector SS is provided between the global column line and the column line corresponding thereto. The select element SS is for example a field effect transistor FET . Herein the FET may also be referred to as a select FET . In this case the select element SS includes a source region formed on the global column line a semiconductor layer channel region formed on the source region and a drain region formed on the semiconductor layer . The semiconductor layer is for example a silicon layer.

Also a select gate line select gate electrode of the select FET is formed between adjacent semiconductor layers in the second direction. The select gate line is disposed in parallel to the row line . Moreover a gate insulating layer is formed between the select gate line and the semiconductor layer .

Also hereinafter as in the general MOS memory device the global column line the row line and the column line may also be referred to as a global bit line GBL a word line WL and a bit line BL respectively.

The select gate line SSG is provided between adjacent channel regions in the second direction. A select FET for example MOS transistor which is the select element SS is formed by the source region the channel region the drain region the gate insulating layer and the select gate line SSG .

That is the select element SS has two gates connected to different select gate lines SSG with respect to a set of the source region the channel region and the drain region . In other words two select FETs are provided per a bit line BL. The select FETs share the source region the channel region and the drain region and the gates are connected to different select gate lines SSG. Also the select elements SS connected to different bit lines BL and adjacent in the first direction share the gate select gate line SSG with each other.

A pillar shaped bit line BL is formed on the drain region of each of the select elements SS. A resistance change material functioning as a memory cell MC is formed on a side surface of the bit line BL. Moreover a word line WL is formed in a region between the bit lines BL adjacent in the first direction. The resistance change material is formed using for example HfO so as to be in contact with the bit line BL and the word line WL.

The resistance change material which is represented by HfO is a material that transitions between at least two resistance values a low resistance state LRS and a high resistance state HRS . It is known that a resistance change material of a high resistance state transitions to a low resistance state when a voltage of a predetermined level or higher is applied thereto and a resistance change material of a low resistance state transitions to a high resistance state when more than a predetermined amount of a current flows therethrough.

In particular an element in which a transition from a high resistance state to a low resistance state and a transition from a low resistance state to a high resistance state are performed by application of voltages with different polarities is called a bipolar operation element. The resistance change material performing such an operation can be provided with a thin film that is made of at least one of materials including TiO ZnMnO NiO SrZrO PrCaMnO and carbon in addition to HfO.

By the above manner the memory cell MC including the resistance change material provided between the word line WL and the bit line BL is disposed within the memory cell array for example in a three dimensional matrix form. In the present structure the word line WL and the bit line BL are just line and space patterns. The word line WL and the bit line BL have only to intersect with each other in a positional relationship and it is unnecessary to consider a misalignment in a word line direction and a bit line direction.

Therefore it is possible to loosen alignment accuracy in the memory cell during manufacture. This makes it possible to easily perform the manufacture. This structure is a highly integrated structure that can store 1 bit information in a 2Fregion.

That is illustrates a pattern of a word line WL within any one of a plurality of layers of . In a shaded region represents a layout of the word line WL.

As illustrated the word line WL in one layer is commonly connected with every other line. In other words the memory cell array includes two sets of word lines WL each having the comb shaped structure and regions of the word lines WL on a straight line along the second direction alternately belong to any one of the comb shaped structures.

When the word lines WL are labeled with WL WL WL . . . WL in order from the right side of the paper plane of an electrically equal voltage is applied to odd word lines WL WL . . . WL or these are commonly connected . On the other hand an electrically equal voltage is also applied to even word lines WL WL . . . WL or these are commonly connected . Different voltages may be applied between the odd word lines and the even word lines or the odd word lines and the even word lines are separated from each other .

Hereinafter the set of the odd word lines will be referred to as a word line comb WLcomb a and the set of the even word lines will be referred to as a word line comb WLcomb b. Also in the case of not distinguishing between both sides the two combs will be simply referred to as word line comb WLcomb.

Also although illustrates the case of including eight word lines five global bit lines GBL and forty five bit lines BL this is merely exemplary and the number of these conductive lines can be appropriately changed.

The storage device includes a memory cell array a WL decoder a GBL decoder a selector decoder a controller and a power supply .

The memory cell array has the configuration described with reference to . is an equivalent circuit of the memory cell array . As illustrated in a memory cell MC including a resistance change element resistance change material of is disposed in the memory cell array in a matrix form. In the memory cell MC one end of the resistance change element is connected to any one of the bit lines BL BL BL . . . and the other end of the resistance change element is connected to any one of the word line combs WLcomb WLcomb a WLcomb b .

Also in the word line combs WLcomb a and WLcomb b are denoted by WLcomb ai and WLcomb bi respectively but i represents number of a layer where a corresponding word line comb is formed represents what layer is in order if the first layer i 1 if the second layer i 2 the same hereinafter .

Each of the bit lines BL is connected to the corresponding global bit line GBL through the corresponding select element SS SS SS SS . . . . Furthermore gates of the adjacent select elements SS are connected to a common select gate line SSGj j is a natural number . The select element SS may be considered as a set of two select FETs TR and TR connected in parallel and commonly having a source and a drain.

A gate of one of the two select FETs constituting a certain select element SS for example TR is shared with a gate of one of the two select FETs constituting the adjacent select element SS for example TR .

Also a gate of the one of the two select FETs constituting the certain select element SS for example TR is shared with a gate of the other of the two select FETs constituting the adjacent select element SS for example TR .

However the select element SS disposed at the endmost portion is configured by only one of the transistor TR and the transistor TR.

That is corresponds to the illustration of the example of the memory cell array MS included in the two dimensional plane formed in the first direction and the third direction in . The memory cell array MS is disposed plurally along the second direction. In this case the word line combs WLcomb ai the word line combs WLcomb bi and the select gate lines SSGj are commonly connected each other between the memory cell arrays MS. On the contrary the bit lines BL and the global bit lines GBL are separated between the memory cell arrays MS.

Returning to the description will be continued. The WL decoder includes a word line selection unit and a word line driver. The word line selection unit selects a word line WL based on a WL address received from the controller . The word line driver can apply voltages necessary for reading writing and erasing data to a selected word line and an unselected word line.

The GBL decoder includes a global bit line selection unit and a global bit line driver. The global bit line selection unit selects a global bit line GBL based on a column address received from the controller . The global bit line driver can apply voltages necessary for reading writing and erasing data to a selected global bit line and an unselected global bit line.

The selector decoder includes a selector selection unit and a select gate line driver. The selector selection unit selects a select gate line SSG based on a sheet address received from the controller . The select gate line driver can apply voltages necessary for reading writing and erasing data to a selected select gate line and an unselected select gate line.

Also the sheet represents a set of memory cells selected by any one of the select gate lines . That is in the sheet is a set of memory cells existing in the plane formed in the second direction and the third direction.

The controller controls an overall operation of the storage device . Also the controller can transmit a row address to the WL decoder transmit a column address GBL address to the GBL decoder and transmit a selector address to the selector decoder .

Also at the time of writing data the controller can instruct the WL decoder the GBL decoder and the selector decoder to apply necessary voltages so as to change a resistance state of a resistance change element of a selected memory cell MC.

At the time of reading data the controller can instruct the WL decoder the GBL decoder and the selector decoder to apply necessary voltages so as to detect a resistance value of a resistance change element of a selected memory cell MC as a storage state of the corresponding memory cell MC.

Moreover the controller includes a sense amplifier and can sense amplify data read in the global bit line GBL by the sense amplifier.

The power supply generates predetermined voltages necessary for reading writing and erasing data. The voltages generated by the power supply are applied to the word line WL and the bit line BL.

For example when writing data a large potential difference is generated between a selected word line and a selected bit line and a resistance state of a resistance change element is transitioned. Also when reading data a potential difference can be generated between a selected word line and a selected bit line in a range where a transition of a resistance state does not occur and a current flowing through the bit line or the word line can be detected.

A CMOS circuit including an interconnection layer is formed on a semiconductor substrate for example silicon substrate by a commonly used process. A layer including a plurality of memory cell units is formed on the CMOS circuit . Each of the memory cell units of corresponds to the memory cell array of and wires are formed based on for example a 20 nm design rule. Also a portion called a peripheral circuit in a general memory is included in the CMOS circuit of . This portion contains the decoders to and the controller of .

Also with the exception of the connection portion to the memory cell unit the CMOS circuit can be designed and manufactured based on for example a 100 nm design rule which is looser than the memory cell unit . The layer includes an electrical connection portion for the CMOS circuit around each of the memory cell units . Blocks based on units of the memory cell unit and the connection portion are disposed in a matrix form.

Furthermore a through hole is formed in the layer . An input output unit of the present device including a terminal electrically connected to an input output unit of the CMOS circuit through the through hole can be formed in for example an end portion of the layer .

On the other hand since the memory cell unit and the CMOS circuit are connected in a vertical direction to a substrate surface an operating time can be reduced or the number of cells capable of being read and written at the same time can be significantly increased without any increase in a chip area.

Also an interconnection drawing pad is formed in the input output unit of the device and can be bonded to a lead frame in a package process.

In the following description among global bit lines GBL a selected global bit line is labeled with GBL s and an unselected global bit line is labeled with GBL u. Also among word lines WL a selected word line is labeled with WL s and an unselected word line is labeled with WL u. Furthermore among select gate lines SSG two select elements SS corresponding to a bit line BL to which a selected memory cell MC is connected are selected and labeled with SSG s and SSG n. The other select gate lines SSG are considered as unselected and are labeled with SSG u.

For example one block includes k global bit lines GBL and includes word line layers of p layers. Also one block includes two word line combs WLcomb. Herein n 2 word lines are connected to one block one word line layer and one global bit line GBL. That is n memory cells MC are connected to one block one word line layer and one global bit line GBL to form n sheet selectors select elements SS configured to select the memory cells MC. Herein selecting loop of the sheet selectors configured to sequentially select the select elements SS belonging to one word line comb are defined as a sheet selector loop. For example the sheet selectors belonging to WLcomb a are the select elements SS to SSn 1. Likewise the sheet selectors belonging to WLcomb b are the select elements SSn 1 and SS to SSn 2. That is when the word line WLcomb a is selected and the select elements SS are selected in order of SS to SSn 1 the memory cells c c c c . . . cn 2 and cn 1 are selected. Also when the word line WLcomb b is selected and the select elements SS are selected in order of SSn 1 and SS to SSn 2 the memory cells c c c c . . . cn 4 and cn 3 are selected.

In a write operation the GBL decoder applies a write voltage Vw 0 V to the selected global bit line GBL s and applies Vwf for example a half of the write voltage Vw 2 to the unselected global bit line GBL u.

Also the WL decoder applies 0 V to the selected word line WL s and applies Vwf for example Vw 2 to the unselected word line WL u.

Furthermore the selector decoder applies a write gate voltage Vg w 0 V to both of the two select gate lines SSG s and SSG n and applies 0 V to the other select gate lines SSG u.

As a result in the select element SS connected to the selected bit line BL a channel is formed by the two select gate lines SSG s and SSG n and the write voltage Vw is transferred from GBL s to the selected memory cell MC. On the other hand 0 V is transferred from WL s to the selected memory cell MC.

Therefore data is written to the memory cell MC by applying a potential difference of Vw to both terminals of the resistance change element of the memory cell MC and the resistance state of the memory cell MC becomes a high resistance state. As a result the data is written to the memory cell.

Next an operation of erasing information retained in the memory cell will be subsequently described with reference to .

In an erase operation considering that the element performs a bipolar operation the WL decoder applies Ves Vof for example a voltage Ve 1 obtained by adding an offset voltage Vof 1 V to an erase voltage Ve Ves to the selected word line WL s and applies Vef Vof for example a voltage Ve 2 1 obtained by adding the offset voltage Vof to a half of the erase voltage Ve Vef to the unselected word line WL u.

Also the GBL decoder applies an offset voltage of 1 V to the selected global bit line GBL s and applies Vef Vof for example Ve 2 1 to the unselected global bit line GBL u.

Furthermore the selector decoder applies an erase gate voltage Vg e to both of the select gate lines SSG s and SSG n and applies 0 V to the other select gate lines SSG u.

As a result as described at the time of the writing the voltage Ve is transferred to the selected memory cell MC. Data is erased by applying a potential difference of Ve to both terminals of the resistance change element and the resistance state of the memory cell MC becomes a low resistance state. As a result the data of the memory cell MC is erased.

Herein the reason why the offset voltage Vof of about 1 V is input to the global bit line and the word line is as follows due to characteristics of the select element to be described below it is possible to significantly reduce a leakage current to the unselected memory cell by setting the potential of the selected global bit line GBL s to be about 1 V higher than the unselected select gate line SSG u and technique for raising the entire voltages of the global bit line and the word line is effective to provide a predetermined potential difference by avoiding a negative voltage circuit whose required circuit area is relatively large.

Next an operation of reading information from the memory cell will be subsequently described with reference to .

In a read operation the GBL decoder applies a voltage Vr Vo which is obtained by adding an offset voltage Vo to a read voltage Vr to the selected global bit line GBL s and the unselected global bit line GBL u.

Also the WL decoder applies the offset voltage Vo to the selected word line WL s and applies Vr Vo to the unselected word line WL u.

Furthermore the selector decoder applies a read gate voltage Vg r to one of the select gate lines SSG s and SSG n applies 0 V to the other and applies 0 V to the remaining select gate lines SSG u.

As a result as described at the time of the writing the voltage Vr is transferred to the selected memory cell MC through the selected bit line BL. Herein a current flowing through the selected memory cell MC is different by the resistance state HRS or LRS of the selected memory cell MC. For example data stored in the selected memory cell MC is determined by detecting the current value in the sense amplifier connected to the selected global bit line GBL s.

Also generally for the selected word lines WL s only one word line is selected per a memory cell array however for the selected global bit lines GBL s a plurality of global bit lines may be selected at the same time. Therefore simultaneously a bandwidth can be improved due to an increase in the number of bits on which writing erasing and reading can be performed.

The select element SS has an FET structure and uses a region whose channel width is very narrow in F as a channel. Therefore in order to ensure a current necessary for cell driving it is required to use a bias condition of a relatively high source drain voltage and a so called hot carrier generation probability is relatively high.

Simultaneously like a so called SOI element the select element SS is configured so that hot carriers cannot escape to a substrate. Also there can be many cases where a gate oxide film is a film having a high defect density as compared with a general planar MOSFET. Therefore hot carriers are easily trapped in the gate oxide film and it is likely that a long term characteristic variation such as a reduction of an ON current and or an increase of an OFF current will become remarkable.

Therefore the following description will be given of technique for aiming at avoiding the occurrence of reliability deterioration due to the long term characteristic variation and solving the phenomenon by providing recovering processing of the select element SS. Specifically by utilizing the fact that a polarity of a carrier easily to take in a condition of a high gate voltage and a polarity of a carrier easily to take in a condition of a low gate voltage are reversed a carrier trapped in the gate oxide film is neutralized or detrapped.

For example a common characteristic of the storage devices of the following embodiments is to include a first conductive line extending in a first direction second conductive lines extending in a second direction intersecting with the first direction a plurality of third conductive lines extending in a third direction intersecting with the first and second directions a plurality of resistance change elements each connected between the second conductive line and the third conductive lines a semiconductor layer connected between one end of the third conductive layer and the first conductive layer a select FET using the semiconductor layer as a channel and having a select gate electrode and a control circuit configured to execute a write erase of at least one of the resistance change elements and execute a recovering operation which adjusts a threshold value shift of the select FET by setting the first conductive line to a first potential setting the select gate electrode to a second potential setting all of the second conductive lines connected through the resistance change elements to a single third conductive line to a third potential and setting at least one of the first potential and the third potential to higher than the second potential after the write erase.

Also for example the first and third potentials are different from each other and the recovering operation is executed by flowing a current for example a punch through current flow to the select FET. Herein a direction of the current is the same as a direction of a current which flows to the select FET in the write erase.

Also for example the first and third potentials are equal to each other and the recovering operation may be executed by applying an electric field to the gate insulating layer of the select FET.

Furthermore it is desirable that the first potential is equal to a potential of the first conductive line in the write erase the second potential is smaller than a potential of the select gate electrode in the write erase and the third potential is different from a potential of a selected conductive line among the second conductive lines and a potential of each of unselected conductive lines among the second conductive lines in the write erase.

Also a potential difference between the first and third potentials for example is larger than a potential difference between a potential of the first conductive line and a potential of each of unselected conductive lines among the second conductive lines in the write erase. It is desirable that the control circuit is configured to change a condition of the recovering operation based on an output value of a current detection circuit connected to the first conductive line.

The control circuit is set to a standby state by applying an un select voltage for example 3.0 V to all of the global word lines GWL and the global bit lines GBL. Subsequently the control circuit sets a GWL address which selects a word line group. The control circuit for example sets the selected global word line to a global word line select voltage for example 6.5 V step ST . Also global word lines other than the selected global word line maintain the un select voltage.

Subsequently the control circuit sets a GBL address which is to be a selected global bit line. The control circuit for example sets the selected global bit line to a global bit line select voltage for example 0.8 V step ST . High speed can be achieved by simultaneously selecting selected global bit lines and executing a parallel operation.

Subsequently the control circuit sets a WL address which is to be a selected word line. The control circuit for example sets the selected word line to a word line select voltage for example 4.0 V and sets unselected word lines except for the selected word line to 3.0 V as an example of an un select voltage unselected word line voltage step ST .

Subsequently the control circuit sets a gate voltage of the select element SS according to an address of a bit line to be selected step ST . In the present example the select element SS is selected and the control circuit applies for example the select voltage of 3.0 V to gate electrodes SSG  and SSG  of both sides of the select element SS. Also the control circuit applies 0 V to gate electrodes of the unselected select elements SS. Also since 3.0 V is applied to one gate electrode of the select element SS sharing the gate electrode with the select element SS the control circuit applies 0 V to only the other gate electrode.

Also the control circuit executes SET RESET of the select element by applying a voltage of a pulse length corresponding to SET REST time to the gate electrode of the select element SS step ST . Also the control circuit repeats steps ST to ST within a sheet selector loop and completes the SET RESET of the selected word line step ST .

As a result the memory cells c c . . . cn 1 of the left diagram of are sequentially selected and the operation of one sheet selector loop is completed. Also the gate electrode SSG  or the like need not maintain the select voltage between steps ST to ST and may change according to the SET RESET operation.

Since the above steps cause a variation in the characteristic of the select element SS for example threshold value shift a recovering operation of the select element SS is executed.

First while setting the sheet selector of the selected word line group GWL address to the un select voltage the control circuit sets all word lines of the group to a SET recovery voltage when SET processing is in progress sets all word lines of the group to a RESET recovery voltage when RESET processing is in progress and applies a compensation pulse for example 4.1 V of a predetermined time step ST .

A processing time can be shortened because potentials of the global word line and the global bit line whose line delay is long can be maintained between the application of the Set pulse and the application of the compensation pulse.

A series of such processing is repeated in the other sheet selector loop WL layer loop and global bit line loop in a page steps ST and ST . Also after checking whether data of the page is equal to desired data the SET RESET operation is completed steps ST and ST . For example when read data is different from planned write data the control circuit repeats the loop of steps ST to ST again with respect to the different data.

Also although the SET RESET of page unit data as the file memory has been described in the present embodiment other data units such as segment unit or bit unit may also be used herein.

The set values of the voltages and the principle of recovering the characteristic variation of the select element SS will be described in more detail with reference to the illustrative drawings of .

Also as illustrated in when the selected cell is set a pulse of a predetermined SET time length is applied for example by setting a voltage of the selected global bit line to 0.8 V a voltage of the unselected global bit line to 3 V a voltage of the selected word line to 4 V a voltage of the unselected word line to 3 V and a voltage of the sheet selector gate voltage to 3 V.

An enlarged schematic diagram of the state of the select element at this time is illustrated in the right diagram of . However in the schematic diagram for convenience the source voltage is set to be 0 V by lowering all voltages of the left diagram of by 0.8 V.

In this case since a drain voltage of the select element is 1.2 V which is relatively large impact ionized hot carriers are generated by an electric field at the drain terminal Note and since electrons generated by this are attracted to the gate electrode having a large voltage electrons are easily taken into the gate oxide film near the drain Note . Therefore if electrons are accumulated in the gate oxide film by the long term use there occur phenomenon such as a remarkable reduction of an ON current.

Also holes are moved to the source of the select element by the electric field at the drain terminal and then disappeared in a grain boundary or the like Note .

Therefore as illustrated in the recovering operation after the SET applies a pulse of a predetermined time for example by setting a voltage of the selected global bit line to 0.8 V a voltage of the unselected global bit line to 3 V a voltage of the sheet selector gate voltage to 0 V and voltages of all word lines of the word line group to 4.1 V. In this manner the recovering processing can be simultaneously executed to all of the select elements connected to the bit lines belonging to the selected word line comb on the selected global bit line.

An enlarged schematic diagram of the state of the select element at this time is illustrated in the right diagram of . However in the schematic diagram for convenience the source voltage is set to be 0 V by lowering all voltages of the left diagram of by 0.8 V.

In this case the gate voltage of the select element is low but since the drain voltage is increased to 2.6 V a sufficient punch through current flows to the select element by impact ionization. As a result hot carrier is generated at the drain terminal Note .

However in the recovering operation the gate voltage of the select element is low as opposed to the SET operation. Therefore not electrons but holes are attracted to the gate by a gate electric field. Therefore holes are easily taken into the gate oxide film near the drain. Therefore deterioration of reliability can be avoided by adjusting the pulse time of the recovering processing such that electrons accumulated in the SET operation and holes accumulated in the recovering operation are neutralized annihilated .

Also in the recovering processing setting the potentials of all word lines of the word line group as well as a specific word line to 4.1 V can prevent erroneous writing and erroneous erasing to the memory cell by dispersing a current flowing in the recovering processing to parallel cells and can increase the source drain voltage of the select element FET and obtain a sufficient punch through current even at a low gate voltage by reducing a voltage drop in the cell and the word line Note .

In the present example an example of the RESET operation in which the direction of the current is reversed from the case of the SET in correspondence to the bipolar operation of the resistance change element will be described.

Also as illustrated in when the selected cell is reset a pulse of a predetermined RESET time length is applied for example by setting a voltage of the selected global bit line to 3.4 V a voltage of the unselected global bit line to 1 V a voltage of the selected word line to 0 V a voltage of the unselected word line to 1 V and a voltage of the sheet selector gate voltage to 4.5 V.

An enlarged schematic diagram of the state of the select element at this time is illustrated in the right diagram of . However in the schematic diagram for convenience the source voltage is set to be 0 V by lowering all voltages of the left diagram of by 2.0 V.

In this case since a necessary current of the resistance change material is larger in the RESET operation than in the SET operation the drain voltage is 1.4 V which is slightly larger than in the SET. Therefore as in the SET impact ionized hot carriers are generated by an electric field at the drain terminal Note and since electrons generated by this are attracted to the gate having a large voltage electrons are easily taken into the gate oxide film near the drain Note . Therefore if electrons are accumulated in the gate oxide film by the long term use there occur phenomenon such as a remarkable reduction of an ON current.

Also holes are moved to the source of the select element by the electric field at the drain terminal and then disappeared in a grain boundary or the like Note .

Therefore as illustrated in the recovering operation after the RESET applies a pulse of a predetermined time for example by setting a voltage of the selected global bit line to 3.4 V a voltage of the unselected global bit line to 1 V a voltage of the sheet selector gate voltage to 0 V and voltages of all word lines of the word line group to 0.1 V. In this manner the recovering processing can be simultaneously executed to all of the select elements connected to the bit lines belonging to the selected word line comb on the selected global bit line.

An enlarged schematic diagram of the state of the select element at this time is illustrated in the right diagram of . However in the schematic diagram for convenience the source voltage is set to be 0 V by lowering all voltages of the left diagram of by 0.8 V.

In this case the gate voltage of the select element is low but since the drain voltage is increased to 2.6 V a sufficient punch through current flows to the select element by impact ionization. As a result hot carrier is generated at the drain terminal Note .

However in the recovering operation the gate voltage of the select element is low as opposed to the RESET operation. Therefore not electrons but holes are attracted to the gate by a gate electric field. Therefore holes are easily taken into the gate oxide film near the drain. Therefore deterioration of reliability can be avoided by adjusting the pulse time of the recovering processing such that electrons accumulated in the RESET operation and holes accumulated in the recovering operation are neutralized annihilated .

Also in the recovering operation setting the potentials of all word lines of the word line group as well as a specific word line to 0.1 V can prevent erroneous writing and erroneous erasing to the memory cell by dispersing a current flowing in the recovering operation to parallel cells and can increase the source drain voltage of the select element FET and obtain a sufficient punch through current even at a low gate voltage by reducing a voltage drop in the cell and the word line Note .

Herein in the case of the SET operation of a location where hot carriers are easily accumulated is an edge of the gate oxide film of the bit line side of the select element FET . On the other hand in the case of the RESET operation of the location is an edge of the gate oxide film of the global bit line side of the select element FET . In this regard the use of different recovering processing in the case of the SET operation and the case of the RESET operation is one of characteristics of the present example.

The examples of are characterized in that the electrons cause of the threshold value shift are neutralized by holes generated by the impact ionization that is the punch through current flows to the select element in the recovering operation and the direction of the punch through current is equal to the direction of the current flowing to the select element in the SET RESET.

In the present example the recovering operation of pulling out the electrons trapped in the gate oxide film of the select element by a high electric field will be described.

As illustrated in the recovering operation after the SET RESET for example sets a voltage of the selected global bit line to 6.0 V a voltage of the unselected global bit line to 4 V a voltage of the sheet selector gate voltage to 0 V and voltages of all word lines of the word line group to 6.0 V. In this manner the recovering processing can be simultaneously executed to all of the select elements connected to the bit lines belonging to the selected word line comb on the selected global bit line.

An enlarged schematic diagram of the state of the select element at this time is illustrated in the right diagram of . However in the schematic diagram for convenience the source drain voltage is set to be 0 V by lowering all voltages of the left diagram of by 6.0 V.

In this case the gate voltage of the select element is negative but since the source drain voltage is 0 V the electrons in the gate oxide film are discharged to the source drain by a strong gate electric field. Therefore deterioration of reliability can be avoided by adjusting the recovering processing time such that electrons accumulated in the SET RESET operations and electrons discharged in the recovering operation become substantially equal in amount.

Also in the recovering processing setting the potentials of all word lines of the word line group as well as a specific word line to 6.0 V reduces a voltage drop in the cell and the word line so that the source drain voltage of the select element FET is equalized.

The present example is characterized in that the application of the compensation pulse for the recovering processing the neutralization of the threshold value shift and the application of the SET RESET pulses are reverse to the first embodiment.

The control circuit is set to a standby state by applying an un select voltage for example 3.0 V to all of the global word lines GWL and the global bit lines GBL. Subsequently the control circuit sets a GWL address which selects a word line group. The control circuit for example sets the selected global word line to a global word line select voltage for example 6.5 V step ST . Also global word lines other than the selected global word line maintain the un select voltage.

Subsequently the control circuit sets a GBL address which is to be a selected global bit line. The control circuit for example sets the selected global bit line to a global bit line select voltage for example 0.8 V step ST . High speed can be achieved by simultaneously selecting a plurality of selected global bit lines and executing a parallel operation.

Subsequently the control circuit performs characteristic variation for example threshold value shift recovering operation of the select element SS which is generated by the SET RESET operations.

First while setting the sheet selector gate of the selected word line group GWL address to the un select voltage the control circuit sets all word lines of the group to a SET recovery voltage when SET processing is in progress sets all word lines of the group to a RESET recovery voltage when RESET processing is in progress and applies a compensation pulse for example 4.1 V of a predetermined time step ST .

A processing time can be shortened because potentials of the global word line and the global bit line whose line delay is long can be maintained between the application of the Set pulse and the application of the compensation pulse.

Subsequently the control circuit sets a WL address which is to be a selected word line. The control circuit for example sets the selected word line to a word line select voltage for example 4.0 V and sets unselected word lines except for the selected word line to 3.0 V as an example of an un select voltage unselected word line voltage step ST .

Subsequently the control circuit sets a gate voltage of the select element SS according to an address of a bit line to be selected step ST . In the present example the select element SS is selected and the control circuit applies for example the select voltage of 3.0 V to gate electrodes SSG  and SSG  of both sides of the select element SS. Also the control circuit applies 0 V to gate electrodes of the unselected select elements SS. Also since 3.0 V is applied to one gate electrode of the select element SS sharing the gate electrode with the select element SS the control circuit applies 0 V to only the other gate electrode.

Also the control circuit executes SET RESET of the select element by applying a voltage of a pulse length corresponding to SET REST time to the gate electrode of the select element SS step ST . Also the control circuit repeats steps ST to ST within a sheet selector loop and completes the SET RESET of the selected word line step ST .

As a result the memory cells c c . . . cn 1 of the left diagram of are sequentially selected and the operation of one sheet selector loop is completed. Also the gate electrode SSG  or the like need not maintain the select voltage between steps ST to ST and may change according to the SET RESET operation.

A series of such processing is repeated in the other sheet selector loop WL layer loop and global bit line loop in a page steps ST and ST . Also after checking whether data of the page is equal to desired data the SET RESET operation is completed steps ST and ST . For example when read data is different from planned write data the control circuit repeats the loop of steps ST to ST again with respect to the different data.

Also although the SET RESET of page unit data as the file memory has been described in the present embodiment other data units such as segment unit or bit unit may also be used herein.

Since the set values of the voltages and the principle of recovering the characteristic variation of the select element SS have already been described in detail with reference to the illustrative drawings of a description thereof will be omitted herein. In the second embodiment the recovering operation of the select element SS is executed before the set reset operations. As a result since the set reset operations are executed after the characteristic of the select element SS is recovered the set reset operation can be accurately executed.

The present example is characterized in that the application of the compensation pulse for performing the recovering processing is arranged outside the loop of checking whether the SET RESET of the word line group is completed. This is effective when the recovering operation need not be frequently executed because it is less likely that the characteristic variation of the select FET will occur or the write margin of the SET RESET operation is large even when the characteristic of the select FET is varied. As a result necessary time of SET RESET can be reduced by reducing the recovering processing time.

The control circuit is set to a standby state by applying an un select voltage for example 3.0 V to all of the global word lines GWL and the global bit lines GBL. Subsequently the control circuit sets a GWL address which selects a word line group. The control circuit for example sets the selected global word line to a global word line select voltage for example 6.5 V step ST . Also global word lines other than the selected global word line maintain the un select voltage.

Subsequently the control circuit sets a GBL address which is to be a selected global bit line. The control circuit for example sets the selected global bit line to a global bit line select voltage for example 0.8 V step ST . High speed can be achieved by simultaneously selecting a plurality of selected global bit lines and executing a parallel operation.

Subsequently the control circuit sets a WL address which is to be a selected word line. The control circuit for example sets the selected word line to a word line select voltage for example 4.0 V and sets unselected word lines except for the selected word line to 3.0 V as an example of an un select voltage unselected word line voltage step ST .

Subsequently the control circuit sets a gate voltage of the select element SS according to an address of a bit line to be selected step ST . In the present example the select element SS is selected and the control circuit applies for example the select voltage of 3.0 V to gate electrodes SSG  and SSG  of both sides of the select element SS. Also the control circuit applies 0 V to gate electrodes of the unselected select elements SS. Also since 3.0 V is applied to one gate electrode of the select element SS sharing the gate electrode with the select element SS the control circuit applies 0 V to only the other gate electrode.

Also the control circuit executes SET RESET of the select element by applying a voltage of a pulse length corresponding to SET REST time to the gate electrode of the select element SS step ST . Also the control circuit repeats steps ST to ST within a sheet selector loop and completes the SET RESET of the selected word line step ST .

As a result the memory cells c c . . . cn 1 of the left diagram of are sequentially selected and the operation of one sheet selector loop is completed. Also the gate electrode SSG  or the like need not maintain the select voltage between steps ST to ST and may change according to the SET RESET operation.

Since the above steps may cause a variation in the characteristic of the select element SS for example threshold value shift a recovering operation of the select element SS is executed.

First while setting the sheet selector of the selected word line group GWL address to the un select voltage the control circuit sets all word lines of the group to a SET recovery voltage when SET processing is in progress sets all word lines of the group to a RESET recovery voltage when RESET processing is in progress and applies a compensation pulse for example 4.1 V of a predetermined time step ST .

A processing time can be shortened because potentials of the global word line and the global bit line whose line delay is long can be maintained between the application of the Set pulse and the application of the compensation pulse.

Also a series of such processing is repeated in the global bit line loop in a page step ST . After checking whether data of the page is equal to desired data step ST the SET RESET operation is completed step ST . For example when read data is different from planned write data the control circuit repeats the loop of steps ST to ST again with respect to the different data.

Also although the SET RESET of page unit data as the file memory has been described in the present embodiment other data units such as segment unit or bit unit may also be used herein.

Since the set values of the voltages and the principle of recovering the characteristic variation of the select element SS have already been described in detail with reference to the illustrative drawings of a description thereof will be omitted herein.

In the present example after the SET RESET operations of the word line group is completed the adjustment of the characteristic variation for example threshold value shift of the select element SS is executed in batch with respect to all word lines WL of the group. As a result the processing time can be shortened.

The present example is characterized in that the application of the compensation pulse for performing the recovering processing is provided independently of the global bit line loop SET RESET loop .

The control circuit is set to a standby state by applying an un select voltage for example 3.0 V to all of the global word lines GWL and the global bit lines GBL. Subsequently the control circuit sets a GWL address which selects a word line group. The control circuit for example sets the selected global word line to a global word line select voltage for example 6.5 V step ST . Also global word lines other than the selected global word line maintain the un select voltage.

Subsequently the control circuit sets a GBL address which is to be a selected global bit line. The control circuit for example sets the selected global bit line to a global bit line select voltage for example 0.8 V step ST . High speed can be achieved by simultaneously selecting a plurality of selected global bit lines and executing a parallel operation.

Subsequently the control circuit sets a WL address which is to be a selected word line. The control circuit for example sets the selected word line to a word line select voltage for example 4.0 V and sets unselected word lines except for the selected word line to 3.0 V as an example of an un select voltage unselected word line voltage step ST .

Subsequently the control circuit sets a gate voltage of the select element SS according to an address of a bit line to be selected step ST . In the present example the select element SS is selected and the control circuit applies for example the select voltage of 3.0 V to gate electrodes SSG  and SSG  of both sides of the select element SS. Also the control circuit applies 0 V to gate electrodes of the unselected select elements SS. Also since 3.0 V is applied to one gate electrode of the select element SS sharing the gate electrode with the select element SS the control circuit applies 0 V to only the other gate electrode.

Also the control circuit executes SET RESET of the select element by applying a voltage of a pulse length corresponding to SET REST time to the gate electrode of the select element SS step ST . Also the control circuit repeats steps ST to ST within a sheet selector loop and completes the SET RESET of the selected word line step ST .

As a result the memory cells c c . . . cn 1 of the left diagram of are sequentially selected and the operation of one sheet selector loop is completed. Also the gate electrode SSG  or the like need not maintain the select voltage between steps ST to ST and may change according to the SET RESET operation.

A series of such processing is repeated in the other sheet selector loop WL layer loop and global bit line loop in a page steps ST and ST .

Since a variation in the characteristic of the select element SS for example threshold value shift may occur after the above steps a recovering operation of the select element SS is executed.

First while setting the sheet selector of the selected word line group GWL address to the un select voltage the control circuit sets all word lines of the group to a SET recovery voltage when SET processing is in progress sets all word lines of the group to a RESET recovery voltage when RESET processing is in progress and applies a compensation pulse for example 4.1 V of a predetermined time step ST .

Also before a read operation for checking data inside the page step ST whether the recovering processing has been completed is checked by monitoring a current flowing through the global bit line for example by using a current detection circuit connected to the global bit line step ST . When the recovering processing neutralization of threshold value shift is insufficient the application of the compensation pulse is executed again and the characteristic variation of the select FET is fully recovered. A series of such processing is repeated in a global bit line loop in a page step ST .

Also after checking whether data of the page is equal to desired data the SET RESET operation is completed steps ST and ST . For example when read data is different from planned write data the control circuit repeats the loop of steps ST to ST again with respect to the different data.

Since the set values of the voltages and the recovering principle of neutralizing the characteristic variation of the select element SS have already been described in detail with reference to the illustrative drawings of a description thereof will be omitted herein.

In the present example since the adjustment of the characteristic variation of the select element SS for example threshold value shift is executed immediately before the read processing check data in the page step ST there are no application of the SET RESET pulse between the application of the last compensation pulse and the read processing the influence of the characteristic variation can be further reduced.

Next a method of manufacturing the storage device according to the above mentioned embodiment will be described.

First for example a general CMOS circuit which controls an operation of a ReRAM is formed on a silicon substrate. Subsequently an interlayer insulating layer is formed on the silicon substrate to cover the CMOS circuit. The following manufacturing method relates to a structure over the interlayer insulating layer.

First as illustrated in a global bit line film is formed on the interlayer insulating layer. The global bit line film corresponds to the global bit line GBL described with reference to . As an example the global bit line film is formed using tungsten W and a TiN film as a barrier metal.

Subsequently an ntype silicon layer a ptype silicon layer and an ntype silicon layer are sequentially formed on the global bit line film . The silicon layers to correspond to the source region the channel region and the drain region respectively which have been described with reference to .

The silicon layers and have a dopant concentration of for example about 1 10cm and a film thickness of for example about 40 nm. The silicon layer has a dopant concentration of for example about 1 10cm and a film thickness of for example about 120 nm. Subsequently an annealing is performed under the condition of for example about 750 C. and 60 seconds to crystallize the silicon layers to .

Subsequently as illustrated in the silicon layers to and the global bit line film are patterned by a photolithography technique and an RIE technique. In this manner a global bit line GBL having a stripe shape extending in a first direction is formed. Also a line width and an adjacent spacing of the global bit line GBL are for example about 20 nm a film thickness thereof is for example about 150 nm and a sheet resistance thereof is for example about 1.5 ohm.

Subsequently as illustrated in an interlayer insulating layer is formed on an entire surface. Subsequently the interlayer insulating layer is polished by a CMP method or the like and an upper surface of the silicon layer is exposed. By the present process a recess portion formed in the process of is filled with the interlayer insulating layer . Also the silicon layers and and the interlayer insulating layer are patterned in a stripe shape extending a second direction by using a photolithography technique and an RIE technique.

As a result of the present process the silicon layers and are separated from each select element SS. Also the patterning process is performed for example under the condition that a line width is about 16 nm and an adjacent spacing is about 24 nm a half pitch is 20 nm . At a bottom of the recess formed by the present process the global bit line and the interlayer insulating layer are exposed.

Subsequently as illustrated in an insulating layer for example a silicon oxide film is formed on an entire surface. Subsequently the insulating layer is etched backed so that the insulating layer remains only at the bottom of the recess . A film thickness of the remaining insulating layer is for example about 30 nm. Therefore a part of the silicon layer and side surfaces of the silicon layers and are exposed in the inside of the recess .

Subsequently as illustrated in an insulating layer is formed on an entire surface. The insulating layer corresponds to the gate insulating layer described with reference to . Subsequently the upper surface of the silicon layer and the insulating layer on the insulating layer are removed so that the insulating layer remains only at the side surface of the recess .

Subsequently as illustrated in the inside of the recess is filled with a conductive film . The conductive film is for example an ntype polycrystalline silicon layer and corresponds to the select gate line SSG described with reference to . Subsequently an upper surface of the conductive film is etched back so that a film thickness of the conductive film becomes for example about 140 nm.

By the present process a lower surface of the conductive film becomes lower than an interface of the silicon layers and and an upper surface of the conductive film becomes higher than an interface of the silicon layers and .

Subsequently as illustrated in an insulating layer for example a silicon oxide film is formed on an entire surface. Subsequently the insulating layer is polished by for example a CMP method so that the insulating layer remains only within the recess . As a result the upper surface of the silicon layer is exposed.

Subsequently as illustrated in an insulating layer for example a silicon oxide film having a film thickness of for example 20 nm is formed on the silicon layer and the insulating layers and . Subsequently word line films of sixteen layers are formed on the insulating layer . The word line film corresponds to the word line WL described with reference to .

Also the word line film is formed using for example TiN as a material and a film thickness thereof is for example about 10 nm. Also an insulating layer for example silicon oxide film having a film thickness of for example 7 nm is formed between the stacked word line films . Subsequently an insulating layer for example silicon oxide film having a film thickness of for example 13 nm is formed on the word line film of the uppermost layer sixteenth layer in the present example .

Subsequently as illustrated in the insulating layers and and the word line film are patterned in a stripe shape along a second direction by a photolithography technique and an RIE technique. The present patterning process is performed for example under the condition that a line width is about 15 nm and an adjacent spacing is about 25 nm a half pitch is 20 nm .

Also the present process is performed such that the insulating layers and and the word line film remain on the underlying insulating layer . As a result of the present process the word line WL is formed and simultaneously the upper surfaces of the silicon layer and the insulating layers and are exposed at the bottom of the recess formed by the patterning.

Subsequently as illustrated in a resistance change material is formed on the lower surface and side surface of the recess and the upper surface of the insulating layer . The resistance change material corresponds to the resistance change material described with reference to . The resistance change material is formed to a film thickness of for example about 4 nm and is formed not to bury the recess . Subsequently an etching back is performed to remove the resistance change material at the bottom of the recess and on the upper surface of the insulating layer . As a result the upper surfaces of the silicon layer and the insulating layers and are exposed again at the bottom of the recess .

Subsequently as illustrated in a bit line film is formed on an entire surface and is polished by a CMP method so that the bit line film remains only within the recess . The bit line film corresponds to the bit line BL described with reference to and is formed using for example ntype polycrystalline silicon as a material.

Subsequently as illustrated in the bit line film is patterned in a pillar shape by using a photolithography technique and an RIE technique.

The present patterning process is performed for example under the condition that a line width and an adjacent spacing are all about 20 nm. Also the present process is performed such that the bit line film remains on the underlying silicon layer . As a result of the present process a bit line BL is completed.

Subsequently a recess between adjacent bit lines BL is filled with an interlayer insulating layer and a memory cell region R1 is completed. Subsequently as in a typical semiconductor device a passivation process is performed and an interconnection connecting portion which will be an input output unit is further formed. Finally the above described storage device is completed by performing a so called post process such as an inspection a dicing or the like.

According to the present embodiment in the three dimensional storage device which is easy to manufacture and can be highly integrated high performance can be achieved by suppressing the threshold value shift of the select transistor.

While certain embodiments have been described these embodiments have been presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel embodiments described herein may be embodied in a variety of other forms furthermore various omissions substitutions and changes in the form of the embodiments described herein may be made without departing from the spirit of the inventions. The accompanying claims and their equivalents are intended to cover such forms or modifications as would fall within the scope and spirit of the inventions.


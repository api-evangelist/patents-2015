---

title: Method and technical equipment for short range data transmission
abstract: A method, an apparatus and a computer program product are used for device filtering. A packet is received from a device, after which it is determined whether the device is allowed to be responded to, wherein the determination comprises at least one of the following: determining a received signal strength indication from the packet; or determining a time from previous connection of the device; or determining the data in a payload of the packet.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09609464&OS=09609464&RS=09609464
owner: Silicon Laboratories Finland Oy
number: 09609464
owner_city: Espoo
owner_country: FI
publication_date: 20150317
---
This application claims priority to co pending Finnish patent application serial number 20145251 filed on Mar. 18 2014 the disclosure of which is incorporated herein by reference in its entirety for all purposes.

The present application relates to Bluetooth modules. In particular the present application relates to Bluetooth low energy.

Bluetooth Low Energy BLE relates to Bluetooth wireless radio technology. It has been designed for low power and low latency applications for wireless devices within short range. Today BLE applications can be found from healthcare fitness security smart energy industrial automation and home entertainment. However BLE is not limited only those but increasingly more new application utilizing BLE technology are designed.

The difference between BLE and classic Bluetooth is that the BLE devices consume remarkably less power for communication than classic Bluetooth devices. In addition the BLE is able to start the data transmission much quicker than the classic Bluetooth. This makes it possible to have BLE devices constantly on and to communicate intermittently with other devices.

Now there has been invented an improved method and technical equipment implementing the method by which the above problems are alleviated. Various aspects of the invention include a method an apparatus a computer program product which are characterized by what is stated in the independent claims. Various embodiments of the invention are disclosed in the dependent claims.

According to a first aspect there is provided a method comprising receiving a packet from a device determining whether the device is allowed to be responded to wherein the determination comprises at least one of the following determining a received signal strength indication from the packet or determining a time from previous connection of the device or determining the data in a payload of the packet.

According to a second aspect there is provided an apparatus comprising at least processing means and memory means wherein the apparatus is configured to receive a packet from a device determine whether the device is allowed to be responded to wherein the determination comprises at least one of the following determining a received signal strength indication from the packet or determining a time from previous connection of the device or determining the data in a payload of the packet.

According to a first aspect there is provided a computer program product embodied on a computer readable medium comprising computer program code configured to when executed on at least one processor cause an apparatus to receive a packet from a device determine whether the device is allowed to be responded to wherein the determination comprises at least one of the following determining a received signal strength indication from the packet or determining a time from previous connection of the device or determining the data in a payload of the packet.

According to an embodiment the determined received signal strength indication is used for determining a distance.

In the following several embodiments of the invention will be described in the context of device filtering in BLE. It is to be noted however that the invention is not limited to only this radio transmission technology. In fact the different embodiments have applications in different environments.

The link layer provides ultra low power idle mode operation and device discovery i.e. connection mode and advertising mode handling . The link layer also is in charge for packet transmission and responding.

In BLE technology one or more slave devices can be connected to a master device. The master is able to communicate with one or more slave devices also simultaneously. To let the master know about the slave devices the slave devices or at that point advertisers periodically at pseudo random intervals pass advertisement packets which a master device also known as scanner device i.e. scanner is scanning.

When an advertising device receives SCAN REQ packet from a scanning device the advertising device may give more information to the scanning device by SCAN RSP packet. SCAN RSP packet may contain information on the name of the advertising device and on the services the advertising device is able to provide. However SCAN RSP packet is not limited to carry only this information but may contain other data as well or instead.

Scanning device wishing to connect with the advertising device sends a CONNECT REQ packet that contains data on e.g. transmit window size defining timing window for first data packet transmit window offset that is off when the transmit window starts connection interval is the time between connection events slave latency defines number of times the slave can ignore connection events from the master connection timeout is maximum time between two correctly received packets in the connection before link is considered to be lost hop sequence is a random number appointing the starting point for a hop channel map CRC Cyclic Redundancy Check initialization value.

When a scanner is connected to an advertiser the advertiser is called a slave and the scanner is called a master . The state for passing advertisement packets is called advertising state and the state for connection is called connected state . In both states data transfer occurs. Slave device may be a sensor or an actuator such as a temperature sensor heart rate sensor light bulb proximity sensor etc. Master device can be any electronic device capable of collecting data e.g. mobile phone smart phone personal digital assistant personal computer laptop computer tablet computer etc.

Packets sent from a slave device in advertising mode may contain approximately 27 bytes of data and a slave address. Packets from master device in advertisement channel may contain only a master address.

When an advertisement packet is successfully received by the master device the master device can send a SCAN REQ packet to the slave device. This SCAN REQ packet indicates that the master device has received the advertisement data successfully. The SCAN REQ packet is transmitted from the master device to the slave device in order to request more data.

Connection between the master device and the slave device can be formed by the master device sending CONNECT REQ packet after the slave advertisement packet. When the connection is opened the slave device becomes aware with which device the connection is formed.

The BLE devices are capable of filter scanning devices to which scan responses are sent and or connections are formed. Prior to the invention the device filtering is implemented by using white listing and or black listing only. White listing defines which devices are allowed to have connection with and to send response to. Black listing defines devices which are not to be connected with or responded to. Black and white lists are updated by an upper layer application. The process of updating the white black lists should be done before receiving a packet which means that address in the received packet cannot be used to update the list.

The present embodiments provide a solution where device filtering is implemented by using extraneous information. According to an embodiment the extraneous information used for filtering is used together with the Bluetooth address or packet. However according to another embodiment only the extraneous information is used for filtering. The extraneous information can relate to a received signal strength or interval between requests or data in payload of the packet.

BLE devices are capable of determining RSSI Received Signal Strength Indication to measure a power of the received radio signal. The RSSI can be calculated from packets in advertisement state or connected state. The determined RSSI can be utilized e.g. for determining the distance between two devices according to known algorithms. The determined received signal strength can be used for filtering devices in such a manner that if according to the received signal strength one of the scanning device or the advertising device is too far from the other of the scanning device or the advertising device such a device may be filtered out.

As another example if the time phase from the previous connection of the one of the scanning device or the advertising device to the other of the scanning device or the advertising device is too short i.e. the device was just connected such a device may be filtered out.

According to an embodiment the distance being determined according to the received signal strength can be used to define whether a device should be filtered out. For example if the distance indicates that the scanning device is too far it is appreciated that far depends on a situation. Examples of far are 0.5 meters 2 meters 5 meters etc. according to an embodiment the advertising device filters the scanning device out. According to another embodiment if the distance indicates that the advertising device is too far the scanning device may filter the advertising device out. If the scanning device advertising device on the other hand is closer than far then scan responses or connection requests advertising packets can be send to received from such device.

According to another embodiment the advertising or scanning device may comprise a timer that measures the time from a previous connection of a certain device. The timer can be remote device specific or it can be generic to the device. If the timer is generic to the device it means it is shared with all remote devices. If the timer indicates that the scanning device has just been connected then such scanning device can be filtered out and no scan responses are sent to that device or no connection requests are accepted from that device. Another embodiment is from the scanning device s point of view if the advertising device has just been connected then such advertising device can be filtered out and no connection requests or scan requests are sent to that device. The timings are defined by upper layer application requirements. As examples of the preset timing are 1 minute 5 minutes 10 minutes etc.

Yet according to an embodiment the data in the payload of the packet is determined. For example the sending device is filtered out if the data does not have information which the device is interested in. As another example the sending device is filtered out if the data has a certain information which is not interesting or important to the device.

An embodiment is disclosed next with respect to . A link layer of an advertising device is advertising by sending an advertising packet . A scanning device detects the advertising packet and responds to it by sending either a scan request SCAN REQ or connection request CONN REQ . Before sending scan response SCAN RSP or connection response CONN RSP packet back to the scanning device the advertising device determines whether the scanning device is an allowed device. For determining whether the scanning device is an allowed device the advertising device may use the white black list. In addition to or instead of the black white list the advertising device further determines a received signal strength RSSI which can be used for determining a distance to the scanning device . If the RSSI indicates that the distance to the scanning device is too long then no scan response SCAN RSP is sent to the scanning device or connection response CONN RSP are accepted from the scanning device .

According to another embodiment a link layer of an advertising device is advertising by sending advertising packets. A scanning device may determine whether the advertising device is an allowed device according to white black list. In addition to or instead of the white black list the scanning device determines a received signal strength RSSI which can be used for determining a distance to the advertising device . If the RSSI indicates that the distance to advertising device is too long then the scanning device sends no scan request SCAN REQ nor connection request CONN REQ to the advertising device .

It is appreciated that the embodiments disclosed with reference to are also applicable in situations where the scanning device determines whether the advertising device is too far or whether the time from a previous connection of the advertising device is less than preset time value. Such embodiments are disclosed next with reference to .

It is to be noticed that in the previous embodiments shown in the use of black white listing for predetermining the allowance of the device is optional. In the previous embodiments the RSSI or time is used after it was determined whether the device was allowed according to black white listing. However black white lists may not be used at all. In such embodiments only RSSI or time is used for determining the allowed device. In addition the previous embodiments can also be combined. In such an embodiment at first a device being close enough is determined after which the temporal factor is also defined .

In addition the previous embodiment discloses determining either RSSI or time after the white black listing is read. However according to an embodiment white black listing is not used at all. In such an embodiment the filtering is based only on RSSI on time or on their combination. Yet according to an embodiment the filtering may also be based on a data in the packet payload. For example if the data contains advertising information of which the scanning device is interested in.

The various embodiments may provide advantages. When using extraneous information for device filtering power can be saved. In addition multiple devices in crowded environment can be easily filtered in or out.

The various embodiments of the invention can be implemented with the help of computer program code that resides in a memory and causes the relevant apparatuses to carry out the invention.

It is obvious that the present invention is not limited solely to the above presented embodiments but it can be modified within the scope of the appended claims.


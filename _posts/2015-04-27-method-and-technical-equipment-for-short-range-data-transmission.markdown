---

title: Method and technical equipment for short range data transmission
abstract: Disclosed herein are apparatus and methods capable in one example of transmitting a first advertisement packet indicating that an advertising device is scannable; receiving a scan request from at least one scanning device; determining, based on the received one or more scan requests, whether a corresponding one or more scanning device is an allowed for connection; transmitting a second advertisement packet indicating that said advertising device is connectable; and receiving connection requests from the allowed at least one scanning device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09414217&OS=09414217&RS=09414217
owner: Silicon Laboratories Finland Oy
number: 09414217
owner_city: Espoo
owner_country: FI
publication_date: 20150427
---
This application claims priority to co pending Finnish patent application serial number 20145404 filed on May 5 2014 the disclosure of which is incorporated herein by reference in its entirety for all purposes.

The present application relates to Bluetooth modules. In particular the present application relates to Bluetooth low energy.

Bluetooth Low Energy BLE relates to Bluetooth wireless radio technology. It has been designed for low power and low latency applications for wireless devices within short range. Today BLE applications can be found from healthcare fitness security smart energy industrial automation and home entertainment. However BLE is not limited only those but increasingly more new application utilizing BLE technology are designed.

The difference between BLE and classic Bluetooth is that the BLE devices consume remarkably less power for communication than classic Bluetooth devices. In addition the BLE is able to start the data transmission much quicker than the classic Bluetooth. This makes it possible to have BLE devices constantly on and to communicate intermittently with other devices.

Now there has been invented an improved method and technical equipment implementing the method by which a connection procedure between a master and a slave can be accelerated.

According to a first aspect there is provided a method that comprises transmitting a first advertisement packet indicating that an advertising device is scannable receiving a scan request from at least one scanning device determining based on the received one or more scan requests whether a corresponding one or more scanning device is an allowed for connection transmitting a second advertisement packet indicating that said advertising device is connectable receiving connection requests from the allowed at least one scanning device.

According to a second aspect there is provided an apparatus comprising processing means and memory means wherein the apparatus is configured to transmit a first advertisement packet indicating that an advertising device is scannable receive a scan request from at least one scanning device determine based on the received scan requests whether a corresponding scanning device is an allowed for connection transmit a second advertisement packet indicating that said advertising device is connectable receive connection requests from the allowed at least one scanning device.

According to a third aspect there is provided a computer program product embodied on a computer readable medium comprising computer program code configured to when executed on at least one processor cause an apparatus or a system to transmit a first advertisement packet indicating that an advertising device is scannable receive a scan request from at least one scanning device determine based on the received scan requests whether a corresponding scanning device is an allowed for connection transmit a second advertisement packet indicating that said advertising device is connectable receive connection requests from the allowed at least one scanning device.

According to an embodiment a list of allowed devices is generated which list is transmitted to a link layer.

According to an embodiment the determination on the allowed scanning device is based on at least one of the following data received signal strength indication an existing bond between devices time period from previous connection a manufacturer of the scanning device.

According to an embodiment the second advertising packet is ADV DIRECT IND packet comprising an indication of the allowed scanning device.

In the following several embodiments of the invention will be described in the context of device filtering in BLE. It is to be noted however that the invention is not limited to only this radio transmission technology. In fact the different embodiments have applications in different environments.

The link layer provides ultra low power idle mode operation and device discovery i.e. connection mode and advertising mode handling . The link layer is also in charge for packet transmission and responding.

In BLE technology one or more so called slave devices can be connected to a master device. The master is able to communicate with one or more slave devices also simultaneously. To let the master know about the slave devices the slave devices or at that point advertisers periodically at pseudo random intervals pass advertisement packets which a master device also known as scanner device i.e. scanner is scanning.

If the advertiser sends either the ADV IND or ADV DIRECT IND packets a scanner desiring to exchange data with the advertiser can send a CONNECT REQ packet. If the advertiser accepts the CONNECT REQ packet the devices become connected and the communication may be started. At this point the advertiser becomes a slave and the scanner becomes a master. After connected the master device can request bonding with the slave device. This means that the devices exchange keys or other encryption info to be stored for future connections.

Instead of the CONNECT REQ the scanner device may also respond with SCAN REQ which is a request for further information from the advertiser. This can be send as a response to ADV IND or ADV SCAN IND advertising packets.

When an advertising receives SCAN REQ packet from a scanning device the advertising device may give more information to the scanning device by SCAN RSP packet. SCAN RSP packet may contain information on the name of the advertising device and on the services the advertising device is able to provide. However SCAN RSP packet is not limited to carry only this information but may contain other data as well or instead.

As said scanning device wishing to connect with the advertising device sends a CONNECT REQ packet that contains data on one or more of the following transmit window size defining timing window for first data packet transmit window offset that is off when the transmit window starts connection interval which is the time between connection events slave latency defines number of times the slave can ignore connection events from the master connection timeout is maximum time between two correctly received packets in the connection before link is considered to be lost hop sequence is a random number appointing the starting point for a hop channel map CRC Cyclic Redundancy Check initialization value. The CONNECT REQ packet initiates the connection i.e. creates a point to point connection between the devices.

The state for passing advertising packets is called advertising state and the state for connection is called connected state . In both states data transfer occurs. Slave device may be a sensor or an actuator such as a temperature sensor heart rate sensor light bulb proximity sensor etc. Master device can be any electronic device capable of collecting data e.g. mobile phone smart phone personal digital assistant personal computer laptop computer tablet computer etc.

Packets sent from a slave device in advertising mode may contain approximately 28 bytes of data and a slave address. Packets from a master device in advertisement channel may contain scanner and advertiser addresses. According to an embodiment the packets from a master device in advertisement channel contains only a master address.

Connection between the master device and the slave device can be formed by the master device sending CONNECT REQ packet after the slave s advertisement packet. When the connection is opened the slave device becomes aware with which device the connection is formed.

The BLE devices are capable of filtering scanning devices to which scan response are sent. Prior to the present embodiments the device filtering is implemented by using white listing and or black listing. White listing defines which devices are allowed to have connection with and to send response to. Black listing defines which are not to be connected with or responded to. Black and white lists are updated by an upper layer application. The process of updating the white black lists should be done before receiving a packet which means that address in the received packet cannot be used to update the list.

At present if there are multiple master devices trying to connect by sending CONNECT REQ packets to single slave the master device that is connected to the slave device is the one whose CONNECT REQ packet was received first by the slave device i.e. advertiser . Therefore not necessarily the optimal master is selected for connection.

According to an embodiment the advertisement procedure is modified so that at first the advertising device advertises with ADV SCAN IND packet which indicates that the advertiser is scannable but not connectable. The scanners send SCAN REQ packets which the advertiser uses for generating a list of allowed master devices for connection. The generated list is used as a whitelist for connections. After having generated the white list the advertiser device advertises with a new advertisement packet this time with ADV IND packet indicating that the advertiser is connectable.

The embodiments are useful e.g. when generating whitelists for e.g. master devices using random addresses master devices in an environment containing multiple master devices such as key which unlocks computer and or master devices being previously defined. In a mesh type of setting where multiple master devices exist the slave device can select the optimal master for connection using RSSI Received Signal Strength Indication .

The present embodiment is illustrates in . illustrates an advertising device and scanner devices . The advertising device advertises using ADV SCAN IND packet to gather information on scanner device . After enough data has been gathered a list of allowed master devices is generated by the advertiser device. A scanner device is entered to the list of allowed master devices if e.g. RSSI is high enough there exists a bond between the scanner device and the advertiser device i.e. encryption info has been stored for the devices if enough time is passed from previous connection or if a device is from certain manufacturer 3 upper bytes of the address .

The generated list is fed to a link layer of the advertising device where it is used as a white list for filtering the CONNECT REQ packets.

The advertising device then changes the advertisement type to ADV IND or ADV DIRECT IND packet which indicates that the advertising device is connectable. In an ADV DIRECT IND packet may comprises an address of the allowed connecting device. Now the received CONNECT REQ packets are filtered according to the white list that was generated of the list of allowed devices. The advertising device accepts only those CONNECT REQ packets that are originated from a scanner device belonging to the list of allowed device. According to an embodiment the advertising device accepts only such CONNECT REQ packet that is received from a scanner device indicated in the ADV DIRECT IND packet.

According to an embodiment the second advertising packet is ADV IND packet and according to another embodiment the second advertising packet is ADV DIRECT IND packet.

It is appreciated that in the previous examples a list of allowed master devices is generated. However it is also possible that a list of rejected master device is generated instead by using the information in the SCAN REQ packets.

The present embodiments provide a solution where an advertising device first advertises with a packet indicating that the device is scannable and later switches the advertising mode and advertises with a packet indicating that the device is connectable. With such an embodiment a master device for connection can be selected.

The various embodiments may provide advantages. For example connection procedure is accelerated because there is no need to form the connection at first and then to validate the master address and if it is noticed that the master device is not an optimal master device to disconnect.

The various embodiments of the invention can be implemented with the help of computer program code that resides in a memory and causes the relevant apparatuses to carry out the invention.

It is obvious that the present invention is not limited solely to the above presented embodiments but it can be modified within the scope of the appended claims.


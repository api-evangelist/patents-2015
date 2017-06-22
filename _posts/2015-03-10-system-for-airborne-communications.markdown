---

title: System for airborne communications
abstract: The invention achieves high Multiple Input, Multiple Output (MIMO) data rates over long wireless links by employing large ground relay MIMO antenna arrays and conformal airborne MIMO antenna arrays. Antenna transceiving element layouts and polarizations are optimized for enhanced channel capacity.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09419330&OS=09419330&RS=09419330
owner: The United States of America as represented by the Secretary of the Air Force
number: 09419330
owner_city: Washington
owner_country: US
publication_date: 20150310
---
The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates generally to enabling aircraft wireless links to achieve the high data rates provided by MIMO Multiple Input Multiple Output communications over longer distances than usually provided with limited size aircrafts. The invention described herein employs a large size ground array MIMO relay.

The wireless link between aircraft at elevated altitudes is typically free of electromagnetic reflections termed free space communications . MIMO links rely on the ability to distinguish between the transmitting array elements by the receiving array. Without electromagnetic scattering the transmitting array element spacing must be resolved by the receiving array free space beamwidth. The beamwidth of the receiving array is limited by its size which is limited by the size of the aircraft. For typical size aircraft and typical radio frequencies link distances greater than 1 km do not provide the MIMO data rates expected for spectrum efficiency. It is desirable to provide MIMO capacity for aircraft links longer than 100 km. A way of overcoming the limitations imposed by aircraft size is desired.

The distance limitation for a wireless aircraft to aircraft MIMO link is highlighted in the reference M. J. Gans Aircraft Free Space MIMO Communications Nov. 1 4 2009 Paper MP7a 1.

One method of increasing the possible communications link length using MIMO on a fixed aircraft size is to increase the radio frequency. The beamwidth of a fixed width array is inversely proportional to the radio frequency. A much narrower beamwidth can allow transmitting antenna element resolution by the receiving array at larger distances. However using a many times higher frequency can be subject to high propagation loss and expensive hardware.

In U.S. Pat. No. 6 097 771 to G. J. Foschini Wireless Communications System Having a Layered Space Time Architecture Employing Multi Element Antennas it is taught that wireless link data rates can be increased roughly in proportion to the number of antenna elements at the link terminals without increasing the total transmitted power or bandwidth. This allows for enormous data rates e.g. hundreds of bits per second per Hz for a system employing 30 antennas at both transmitter and receiver and experiencing an average signal to noise ratio of 24 dB in a so called Rayleigh fading environment. This is the high data rate MIMO capacity sought after in the free space aircraft environment referred to above.

It is therefore an object of the present invention to provide maximized channel capacity in communications with airborne platforms.

It is a further object of the present invention to provide a ground array relay to overcome the prior art s link length capacity limitation of aircraft to aircraft communications.

It is a further object of the present invention to provide antenna array layouts which provide coverage flexibility and compactness while maintaining high MIMO data rate capacity.

Briefly stated the present invention achieves high Multiple Input Multiple Output MIMO data rates over long wireless links by employing large ground relay MIMO antenna arrays and conformal airborne MIMO antenna arrays. Antenna transceiving element layouts and polarizations are optimized for enhanced channel capacity.

According to an embodiment of the present invention a system for airborne communications comprises a ground based multiple input multiple output antenna and at least one aircraft based multiple input multiple output antenna where the ground based multiple input multiple output antenna further comprises a first plurality of transceiving elements and where the first plurality of transceiving elements are arranged in a plurality of concentric rings so as to provide any concentric ring a collective polarization coverage range of 0 degrees to 360 degrees and where the aircraft based multiple input multiple output antenna further comprises a second plurality of transceiving elements and where the second plurality of transceiving elements are arranged on an airframe of an aircraft so as to provide the second plurality of transceiving elements a collective polarization coverage range of 0 degrees to 360 degrees.

According to another embodiment of the present invention a system for airborne communications relay comprises a ground based multiple input multiple output antenna and at least two aircraft each having an aircraft based multiple input multiple output antenna where the ground based multiple input multiple output antenna further comprises a first plurality of transceiving elements where the first plurality of transceiving elements are arranged in a plurality of concentric rings so as to provide any concentric ring a collective polarization coverage range of 0 degrees to 360 degrees and where each aircraft based multiple input multiple output antenna further comprises a second plurality of transceiving elements where the second plurality of transceiving elements are arranged on an airframe of an aircraft so as to provide the second plurality of transceiving elements a collective polarization coverage range of 0 degrees to 360 degree and where communications is relayed from the aircraft based multiple input multiple output antenna of one of the at least two aircraft through the ground based multiple input multiple output antenna to the aircraft based multiple input multiple output antenna of one or more of the other at least two aircraft.

By employing an earth based relay of size much larger than the aircraft the ground MIMO array of the present invention can resolve the aircraft array elements and the aircraft array can resolve the widely spaced elements on the ground array. Thus the link from aircraft to ground array can provide high MIMO capacity for much larger link lengths than that provided by aircraft to aircraft links. By using the large ground array as a relay high MIMO capacity can be provided from aircraft A to the ground array to aircraft B even though the distance from aircraft A to aircraft B is on the order of 200 km.

An important aspect of the layout of the MIMO antenna elements in the aircraft and the ground arrays is the choice of their polarizations locations and orientations. Choices which maximize the channel capacity and coverage should be selected. By considering all likely scenarios of aircraft attitudes and locations better strategies for antenna layout are determined.

Referring to is a depiction of a typical application of a ground array relay. A MIMO array on an aircraft transmits to a large area ground based MIMO array relay. The ground based MIMO array then relays its received data through a MIMO link to another aircraft.

Referring to is a typical layout of transceiving antenna elements on a C 5 aircraft. At each antenna location a dual polarization patch antenna element is mounted a dipole moment parallel with the surface of the aircraft termed horizontal and one perpendicular to the aircraft surface termed vertical . Only the horizontal dipole is shown. The array represents a 64 element MIMO array. The antenna layout uses many polarizations and wide spacing to assist resolution of antenna elements for MIMO communication.

Referring to is a typical layout of antenna elements on 1 km diameter ground array. At each antenna location a dual polarized dipole antenna element is mounted a dipole parallel with the surface of the earth termed horizontal and one perpendicular to the earth termed vertical . Only the horizontal dipole is shown. The array represents a 64 element MIMO array. The antenna layout uses many polarizations and wide spacing to assist resolution of antenna elements for MIMO communication.

Referring to and displays the channel capacity computed at 10 dB signal to noise ratio for free space propagation which neglects scattering. The antenna layouts assumed in and are assumed.

Referring to the symmetry axis of the ground array is aligned with the circumflex over x axis and the azimuth direction of the aircraft from the line between the aircraft origin to the origin of the ground array is at an angle relative to circumflex over x denoted by alpha . The symmetry axis of the aircraft is an angle of relative to the azimuth direction from the origin of the aircraft to the origin of the ground array denoted by beta . The distance from the ground array center to the aircraft is d 50 km.

Referring again to and it is evident that the channel capacity is high and stable for variations in frequency see azimuth angle see and orientation of the aircraft see . The ergodic channel capacity in a Rayleigh scattering propagation channel for the same arrays on a 64 by 64 MIMO link is 174 bits second Hz. Thus the ground relay can provide a major portion of full MIMO capacity even without scattering.

Referring again to the key components of a Large Aperture MIMO Relay include a MIMO transceiver array on an aircraft a MIMO transceiver array on the ground . A typical antenna element of the aircraft MIMO array is shown with polarization circumflex over p the carat represents a unit vector at angular location relative to its symmetry axis in the aircraft array. A typical antenna element of the ground MIMO array is shown with polarization circumflex over q at angular location relative to its symmetry axis in the ground array.

The channel capacity was computed for the various antenna array layouts. Consider a short relative to free space wavelength dipole of length h and polarization circumflex over p on the aircraft and a similar dipole of polarization circumflex over q in the ground array. Given the distance r between the two dipoles the free space propagation constant k 2 and the free space impedance the transmission coefficient open circuit received voltage divided by dipole radiating current is 3 

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.


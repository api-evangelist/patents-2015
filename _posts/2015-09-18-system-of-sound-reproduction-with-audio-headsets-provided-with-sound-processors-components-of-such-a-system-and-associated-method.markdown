---

title: System of sound reproduction with audio headsets provided with sound processors, components of such a system and associated method
abstract: The system comprises audio headsets able to apply audio processing operations in response to presets that are common to all the headsets, smart terminals provided with audio flow generation means, and communication means to transmit to the headsets an audio flow and presets to be applied to this flow. A preset server memorises the presets associated with works. Certain terminals can generate presets and transmit them to the server, whereas other terminals collect these presets to apply them to the corresponding works at the time of reproducing these latter.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09485564&OS=09485564&RS=09485564
owner: PARROT
number: 09485564
owner_city: Paris
owner_country: FR
publication_date: 20150918
---
The present invention generally relates to the audio head sets and more particularly the customization of the sound reproduction with such headsets.

Such headsets include a rechargeable battery and a wireless receiving circuit for example radio typically according to the Bluetooth specifications registered trademark of Bluetooth SIG or infrared adapted to receive the audio signals conveyed by such a channel in order to decode and transform them into analog sound signals applied to the transducers. The most recent audio headsets also contain audio processing electronic circuits intended to perform an equalization to apply sound effects to dynamically control the volume of reproduction to neutralize the ambient noises etc.

Generally the equalization and sound effect presets are applied at the user s choice through a control by means of an interface located on a remote device such as a smartphone communicating with the audio head set typically through a wireless link according to the Bluetooth communication protocol. The headset marketed by the applicant company under the commercial name Zik registered trademark has such a functionality. In a similar domain the US 2014 0073429 A1 describes a headset inter faced through a wireless link with a videogame console and provided with a signal processor integrating several presets kept in memory. These pre sets may possibly be presets downloaded from a remote site via the game console. They can be selected at the user s will by means of a select button and a menu shown on a screen integrated to an earphone of the headset.

The present invention aims to enrich the possibilities of creation sharing and use of sound presets of an audio headset provided with switchable equalization presets.

In particular the invention aims to allow that a given artist or referent can suggest or impose that a given work typically the work of the artist song writer composer performer arranger etc. is listened to by the public in conditions of reproduction as desired by the artist.

The invention also aims to allow the reproduction of the work faithfully to the artist s spirit or to select reproduction presets chosen among a group of presets suggested by one or several artists or other referents in the field.

The invention hence proposes according to a first aspect a system of sound reproduction by means of audio headsets comprising in a manner known per se as disclosed by the above mentioned US 2014 0073429 A1 

Advantageously the characteristic markers are markers of identification of at least one among a track an album an artist a style.

The invention proposes according to a second aspect a set formed of an audio headset and a smart terminal the smart terminal being adapted to transmit an audio flow to the audio headset through a link. The audio headset comprises a processor adapted to apply a sound processing to the audio flow to be reproduced in response to a characteristic marker associated with the audio flow a memory adapted to store presets and means for reading in the memory and applying to said processor a preset chosen as a function of the characteristic marker received.

Characteristically of the invention the smart terminal is also adapted to transmit to the audio headset characteristic markers associated with said audio flow and the audio headset comprises means for reading in the memory and applying to the processor a preset chosen in the memory as a function of the characteristic marker received from the smart terminal.

In a preferred but optional implementation said characteristic markers are metadata associated with an audio file adapted to be played in the smart terminal.

It is moreover advantageous that the smart terminal comprises means for updating the reproduction presets memorized in the audio headset from recent reproduction presets received via a network from a preset server.

The invention also aims at an audio headset comprising means for receiving an audio flow from a source a memory adapted to store reproduction presets and a processor adapted to apply a sound processing to the audio flow to be reproduced in response to a preset.

Characteristically of the invention this headset further comprises means for receiving in association with the audio flow a marker characteristic of said flow and means for reading in the memory and applying to said processor a preset chosen as a function of the characteristic marker received.

According to an advantageous but optional additional characteristic the headset further comprises means for updating said presets from a smart terminal.

Another aspect of the invention consists in a smart terminal comprising an audio player adapted to generate an audio flow connection means for applying thereto the audio flow with a sound reproduction device liable to store reproduction presets and network communication means.

Characteristically of the invention this smart terminal further comprises means for creating and or selecting a reproduction preset during the generation of an audio flow and means for transmitting to a server the created and or selected preset in association with a characteristic marker of the audio flow for which said reproduction preset has been created and or selected.

Finally the invention proposes a method of reproduction of an audio flow by an audio headset characterized in that it comprises the following steps 

With reference to the drawings it has been shown a system that comprises an audio preset sharing server an artist audio headset an artist smart terminal or smartphone a user audio headset and a user smart terminal or smartphone .

As will be described hereinafter the smart terminal communicates with the artist headset through a wireless link for example according to the Bluetooth protocol. Likewise the smart terminal communicates with the user headset through a wireless link according to the same type of protocol.

The terminals and are moreover provided with a functionality of communication through a network R such as the Internet to establish communication sessions with the server for example according to the TCP IP protocol.

By means of the headset and the smartphone an artist or another referent listens to a work by choosing different audio reproduction presets implemented by a specialized processor integrated in the headset.

The reproduction presets can comprise with no limitation equalization presets bass medium treble etc. and sound effect presets spatialization reverberation delays compression accentuation etc. these different effects being known per se.

This creation of presets is performed by means of a user interface preferably with a touch screen where virtual cursors rotary knobs etc. are actuated by the user to obtain the desired presets.

As a variant rather than creating himself the presets the artist may apply successively pre existing presets memorized in his smart terminal or in his audio headset after having possibly downloaded them from the server and choose the preset that he finds the most appropriate.

Another variant may be a mixed approach where basic presets are proposed to the artist and the latter retouches them.

After having listened to the work or parts of the latter with different reproduction presets either among pre selections or with presets performed by himself by acting of the reproduction parameters the artist uses the user interface of his terminal so that the presets obtained by creation or selection are transmitted to the server in association with data characteristic of the work preferentially all or part of the metadata of the work for being made available by the users.

It will be noted herein that a given preset created or chosen by an artist may be applied to a single work or track or to a set of works for example the tracks of an album or of the works of the artist or to a musical style to which the work belongs etc.

Moreover the system of the invention allows an artist or referent to allocate presets to works of other artists.

The presets created and memorized in the server as described herein above may then be downloaded towards user smart terminals such as the terminal and transferred as will be seen in detail hereinafter in the following towards a preset memory provided in the associated audio head set .

At the time of selection of an audio file by a user for the playing thereof by the smart terminal this user can 

This mode of automatic selection according to the invention of a preset may typically be implemented during the listening of the music via a Blue tooth link between the terminal and the audio headset by exploiting herein the Advanced Audio Distribution Bluetooth Profile A2DP . For that purpose the system uses the Audio Video Remote Control Profile AVRCP to collect and communicate to the audio headset the tag information or markers metadata relating to the track whose reproduction is in progress title artist album style etc. allowing to perform the selection of an associated preset.

As a variant other means for collecting and transmitting such metadata for example via an integrated purchase function such as the In App Purchase function proposed by Apple Inc. may be used.

With reference now to an electronic architecture on the smart terminal side and on the audio headset side allowing the implementation of the present invention will now be described.

The smart terminal is the user terminal of . It comprises in a manner known per se a player for playing audio files for example in MP3 AAC WMA format etc. which cooperate with a pile of media of the terminal.

A Bluetooth pile is in communication with the pile of media and exchanges data with a Bluetooth component or chip provided on the electronic card of the terminal.

An audio preset management program run by the processor of the terminal comprises a user interface a communication protocol and an Application Programming Interface API in communication with the Bluetooth pile .

The audio headset comprises for its part a hardware part provided in particular with a Bluetooth chip or component a digital signal processor or DSP intended to process the audio flow to be reproduced including the digital analog conversion and the amplification and transducers .

The processor is piloted from an audio core or kernel through an equalization core or kernel a spatialization core or kernel and a player management core or kernel .

An audio preset core or kernel communicates with a communication protocol with a Bluetooth pile exchanging data with the Bluetooth chip .

This core cooperates with a database for example in the SQLite registered trademark format containing a data processing core and preset files .

The core comprises a sub program for inserting presets in the database and a sub program for collecting presets from the database.

The Bluetooth chips of the smart terminal and of the audio head set communicate with each other through an Advanced Audio Distribution Bluetooth Profile A2DP an Audio Video Remote Control Bluetooth Profile AVRCP in its release 1.3 or subsequent and finally by the RFCOMM Radio Frequency COMMunication service.

The cooperation between the smart terminal and the headset for the transmission of a sound reproduction preset to the headset comprises the following aspects 

It is understood that this architecture allows to select presets allocated to sound tracks via the metadata or tag markers by means of the database .

It will be observed herein that the memorization of the presets inside the audio headset allows to ensure an optimum reactivity in case of pre set change at the time of the transition between the playing of a work and the playing of the following work no transmission of presets being necessary between the smart terminal and the headset because this is the latter that memorizes the presets and ensures automatically their smart selection only the metadata or tag markers of the audio file being transmitted.

The invention can however be implemented with a dynamic transmission of presets before the playing of a work via the RFCOMM service. It may also be provided as a variant to encapsulate the presets in the metadata of an audio file.

The creation of presets at an artist terminal is performed with a preset management program that can be identical to that of the user terminal or consists in a dedicated program. Hence an artist can create specific pre sets in association with given data and the program comprises means for sending these presets in association with the metadata of the works for which these presets have been chosen to the preset server .

The presets hence proposed by the artists can be recovered by the users either at a later time or dynamically previously to the playing of a work.

In the first case the user smart terminal opens a session via the Internet with the preset server and scans the metadata of the auto files memorized in the terminal to download the new data of the pre sets made available by artists from the last session and in the implementation with an integrated preset database described hereinabove to transmit these new presets to the database .

In the second case the terminal checks the preset server before each playing to download the preset corresponding to the metadata of the work chosen for the playing in case of problem of communication a default preset is applied .

As a variant the server is able to send notifications to the users of smart terminals implementing in a push way the system of the invention in order to signal them the existence of new presets available for audio files that are stored in their terminal.

The present invention finds an application as soon as a community is equipped with identical or similar audio headsets in that they are able to respond to common presets to reproduce the sound in the same manner. The reproduction chain is hence fully controlled.

Of course the present invention is not limited to the embodiment and the variants described hereinabove but the one skilled in the art will be able to make many adaptations thanks to his general knowledges. In particular 


---

title: Providing access to message headers
abstract: Method and system are provided for providing access to string-based message headers in network protocol messages. The method includes: converting header names into canonical form, wherein a canonical key represents at least one equivalent header name, and wherein a canonical key has a string and an integer value; providing a mapping between the header names and the canonical keys; and searching for a header name using the canonical key by sequential search using integer comparison.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09356990&OS=09356990&RS=09356990
owner: International Business Machines Corporation
number: 09356990
owner_city: Armonk
owner_country: US
publication_date: 20151015
---
This invention relates to the field of access to message headers. In particular the invention relates to providing fast access to string based message headers in network protocol messages.

Access to header fields of messages based on HTTP Hypertext Transfer Protocol format in particular SIP Session Initiation Protocol is processor intensive as the header names are case insensitive multi valued ordered and possibly accessed with aliases. Processing of messages themselves may take an important part of processor usage because these headers are heavily used for low level routing purposes.

In a conventional implementation message headers are stored as an ordered table of key value pairs. Searching a header is generally done with a sequential search in the headers list with an ignoring case string comparison. In the case of a possible alias the search is done again with the alias value. However performance is not very good due to different header name representations.

According to a first aspect of the present invention there is provided a method for providing fast access to string based message headers in network protocol messages comprising converting header names into canonical form wherein a canonical key represents at least one equivalent header name and wherein a canonical key has a string and an integer value providing a mapping between the header names and the canonical keys and enabling searching for a header name using the canonical key by sequential search using integer comparison.

In embodiments the present invention further provides a method wherein providing a mapping between the header names and the canonical keys comprises mapping the header names of the following forms to the canonical key a standard representation of the header name which is its canonical string a lower case representation of the header name and a lower case representation of any alias versions of the header name.

In embodiments the present invention further provides a method comprising initializing a converter by converting predefined header names for a protocol to canonical keys and building the mapping.

In embodiments the present invention further provides a method comprising associating an integer value with a canonical key by using a memory address for a canonical header string as the integer value.

In embodiments the present invention further provides a method comprising associating an integer value with a canonical key by using a table to store all canonical header strings and using the index of the table as the integer value.

In embodiments the present invention further provides a method comprising storing the canonical key and its lower case representation as map keys and the canonical key as a map value.

In embodiments the present invention further provides a method comprising updating the mapping of canonical keys to include new representations of existing predefined header names.

In embodiments the present invention further provides a method comprising updating the mapping of canonical keys to include new header names received which are not in the initialized predefined header names of the protocol.

In embodiments the present invention further provides a method comprising receiving a message having a message header of header names and converting the header names to canonical keys and building a message header list for the message of the canonical keys.

In embodiments the present invention further provides a method wherein converting header names further comprises searching the header name directly in the mapping and if found getting the associated value if not found converting the header name to lower case and searching the mapping if found adding the new representation to the mapping for subsequent searches if not found adding the header name to the mapping with the new header name as a new canonical key.

In embodiments the present invention further provides a method comprising receiving a header name to be searched and searching for the canonical key in the message header list of a message using integer comparison.

In embodiments the present invention further provides a method comprising receiving a header name to be searched converting the header name to its canonical key using the mapping and searching for the canonical key in the message header list of a message using integer comparison.

According to a second aspect of the present invention there is provided a system for providing fast access to string based message headers in network protocol messages comprising a converter for converting header names into canonical form wherein a canonical key represents at least one equivalent header name and wherein a canonical key has a string and an integer value a map for providing a mapping between the header names and the canonical keys and a header search component for searching for a header name using the canonical key by sequential search using integer comparison.

In embodiments the present invention further provides a system wherein the map for providing a mapping between the header names and the canonical keys comprises a standard representation of the header name which is its canonical string and a lower case representation of the header name a lower case representation of any alias versions of the header name.

In embodiments the present invention further provides a system comprising an initializing component for initializing the converter by converting predefined header names for a protocol to canonical keys and building the map.

In embodiments the present invention further provides a system wherein the map stores the canonical key and its lower case representation as map keys and the canonical key as a map value.

In embodiments the present invention further provides a system comprising an updating component for updating canonical keys to include new representations of existing predefined header names.

In embodiments the present invention further provides a system comprising an updating component for updating canonical keys to include new header names received which are not in the initialized predefined header names of the protocol.

In embodiments the present invention further provides a system further comprising a message header converting component for receiving a message having a message header of header names and including a look up component for converting the header names to canonical keys and a list building component for building a message header list for the message of the canonical keys with integer values.

In embodiments the present invention further provides a system comprising a header search component comprising a key receiving component for receiving a header name to be searched a converting component for converting the header name to its canonical key using the mapping and a sequential search component for searching for the canonical key in the message header list of a message using integer comparison.

According to a third aspect of the present invention there is provided a computer program product for providing fast access to string based message headers in network protocol messages the computer program product comprising a computer readable storage medium having computer readable program code embodied therewith the computer readable program code configured to convert header names into canonical form wherein a canonical key represents at least one equivalent header name and wherein a canonical key has a string and an integer value provide a mapping between the header names and the canonical keys and enable search for a header name using the canonical key by sequential search using integer comparison.

According to a fourth aspect of the present invention there is provided a method substantially as described with reference to the figures.

According to an fifth aspect of the present invention there is provided a system substantially as described with reference to the figures.

The described aspects of the invention provide advantages including a reduced memory footprint a header name comparison reduced to integer comparison and an automatic normalization of header names.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

Methods and systems are provided for a front end key converter that quickly transforms any header key into a canonical form. A canonical form represents equivalence classes only once with a canonical key representing a class of one or multiple equivalent header keys.

When a message is read from an input stream the header key or name is read and transformed into a unique canonical key by a front end converter. This canonical key may be accessed as a string or as an integer. A simple implementation is to have this key as an address that points to the string and use this address as an integer for comparison. Another implementation may be to use an integer that is an index in a table of strings to retrieve the sting form of the header name.

To search for a known predefined header key for example Content Length a sequential search is made over headers using directly the canonical keys that are stored as a program constant. This allows an integer comparison instead of string comparison.

To search for a dynamic private header first the header key is converted into its canonical key then the search is carried out as for known predefined header keys.

Referring to a schematic diagram shows the transformation from received message header keys to integer keys to a canonical form in the form of a unique set of canonical keys which are reused for all messages. From a header key expressed as a string the transformation returns a canonical key in two representations as a string and as an integer. The integer keys may be an index in a canonical form table or more simply directly the address of the canonical key strings.

For example using the message headers shown in the three equivalent header keys of Via v via all transform the same integer key which refers to the unique canonical form key Via .

Referring to a schematic diagram shows message header processing as known in the prior art. A message received from a network is read from an input stream generally attached to the network. A message header may include headers as shown in . Three of the header names have been highlighted together with their values to illustrate the processing.

An internal logical representation of the message is built including a message header list with a list of key value pairs to represent the headers. The header names or keys of the message header list point to the header names on a duplicate copy of the message in memory which means that each header name is in a different memory area even if the text content is identical. The header values of the message header list point to the values in the message .

In the internal message representation when a particular header name is required to be searched then the required string must be compared with all the strings. Additionally any alias names must also be checked.

In the example of if a search is required for the header name Via this string should match each of the headers Via the same representation via the lower case representation and v the alias . A header name being searched for must be compared to all the headers in the list as it could be at the end of the list.

A converter is provided to quickly convert all the header names which are physically different but semantically identical to a unique canonical key always located a the same memory area with the same address. The message header list C which is built for a message is then always using the same key C C for all header names that are semantically identical. Moreover as the same converter is used for all messages the same canonical key may be used for all messages that are processed with it.

To increase the speed of comparison of header keys an integer key value is associated to each canonical header name. Two possible ways to do this include 

1 Using directly the memory address of the canonical header string as the integer. In this case the integer value is something random that depends on where the string has been placed in memory by the program but it is enough to allow a fast key comparison. An advantage of this embodiment is that if it is considered as the address of the string then the string is provided or if it is considered as an integer it allows efficient comparisons.

2 Using an intermediate table or array that stores all canonical header strings and uses the index in this table or array as the canonical key integer. In such case the header keys will be integers from zero to the total number of header names. An advantage of this embodiment is that the format of the integer can be short however there is an indirection to access the string associated to the integer.

The selection of the method of association of the integer value depends on the implementation context.

A front end key converter may be provided as a hash map that links the different forms of a message header key to its canonical key. To speed up the access an integer key value may be associated to each canonical header name which is used for header searches. From a header name expressed as a string the converter may return a canonical key in two representations as a string and as an integer. The integer key may be an index in the canonical form table or may simply be the address of the canonical key.

The front end converter is initialized for all predefined message headers of the protocol. The canonical form of the message header key and its lower case representation are used as map keys and the canonical form as map value. If there is an alias the alias in lower case is also added to the map.

Referring to a flow diagram shows an example embodiment the described method for message header conversion to provide fast access to message headers as carried out by a front end converter

An input stream may be received at a front end converter. A message header key may be read by the front end converter and each message header key may be converted into a canonical key identified by an integer value.

A message header list for the message may be built using the canonical keys of the dual form of integer and string.

Referring to a flow diagram shows an example embodiment of an aspect of the described method of message header conversion to provide fast access to message headers as carried out by a front end converter.

A header key may be received and input for conversion. A search may be carried out for the header key directly in the map. It may be determined if the key is found and if so the associated value may be retrieved from the map val map.get key . This means that the key is directly in the map and the canonical form is the value .

If the key is not found the header key may be converted to lower case nkey key.toLowerCase It may be determined if the lower case key is found and if so the associated value may be retrieved from the map val map.get key . A new representation of an existing key may then be added map.put nkey val and the canonical form is the value.

If they key is not found in the lower case it is a new key. The key may be added to the map as for predefined keys map.put key key map.put nkey key . The first form becomes the canonical form canonical form key.

The converter map is self adaptive and quickly converges to a fix point. All conversions are then done in a single step using a low cost hash code function.

Referring to a flow diagram an example embodiment of an aspect of the described method of searching for a header key. A message may be received and access required to its header. A conversion of the message s header keys to canonical keys referenced by integer values will have been carried out on the message to provide a message header list for the message.

A header key may be received for a search. It may be determined by the front end converter if the header key is a known predefined header key for example Content Length . If so a sequential search may be made over the message header list of the message using directly the canonical keys that are stored. This allows an integer comparison instead of string comparison.

If a header key is not a predefined header key for example it may be a dynamic private header the header key may be converted by the front end converter into its canonical key and then the search may be carried out of the message header list as for known predefined header keys.

When a message is received all its header names are converted to integer keys corresponding to canonical keys before being delivered to the application. When the application wants to retrieve header values from this message there are several possibilities 

1 The application uses a predefined method for example msg.getContentLength that directly uses the canonical key of the header to search for. In such case which may be the default usage the front end key converter is not involved because the header key is already converted.

2 The application uses a generic method that retrieves a header using its name as a string for example msg.getHeader COntENt LengTH . In this case the front end key converter must be used first to convert the string into header key prior to search for the header.

3 The application is searching for a non standard header that is not predefined by the protocol. This case is similar to Case 2 because only the string representation must be used at least the first time. The front end key converter is updated to increase the speed of subsequent searches.

In the described system a client server may include a converter for converting message header keys to a canonical form in order to provide fast access to the message headers when searching.

The converter may be implemented in a library dedicated to the protocol that is to be handled for example HTTP or SIP . This library is a piece of software that may be directly linked to an application or provided by some middleware called container in which the application resides.

For example web applications are deployed inside web servers that provide such libraries to applications. This allows applications to be simplified and also multiple applications to share the same libraries.

The converter may include an initializing component for initializing the converter for all predefined header keys of the protocol.

The converter includes a map which includes for each header name string 1 The canonical form of the header name with a referenced integer value 2 The lower case representation of the header name or other generalized representation which is used to retrieve the canonical form in case the header name is given in any mix of upper and lower case. For example ViA will be converted in via and then found in the map and 3 If the header has an alias the lower case representation of this alias .

The converter may include a message header converting component for converting an incoming message header to canonical form and building a message header list using the canonical keys with integer values. The message header converting component may include a look up component for looking up header names read from the message header in the map . The look up component may use the canonical form or the lower case form to find the header name in the map . A list building component may build the message header list for the message formed of the retrieved canonical keys and integer values obtained from the map .

The converter may also include an updating component for updating the map to include a new header name discovered in a message and additional mappings and canonical keys which were not input during initialization of the converter .

The updating component may be triggered by the look up component if a message header name is not found in the map . A new representation adding component may be provided for adding a new representation to the map if the lower case search matched but the actual representation was not previously mapped to the canonical key . A new key adding component may be provided for adding a new canonical key to the map if the search did not locate a match.

The header search component may include a key receiving component for receiving a header key to search for in a message header . A converting component may convert the header key to its canonical form and a sequential search component may carry out a search using the canonical form of the message header list .

Referring to an exemplary system for implementing aspects of the invention includes a data processing system suitable for storing and or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements may include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also include a primary storage means such as a magnetic hard disk drive and secondary storage means such as a magnetic disc drive and an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices may be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

Referring to a schematic diagram illustrates the mapping of header keys to canonical keys . During initialization of a converter predefined header keys for example Content Length in the standard form are converted to a canonical key for example Content Length . The lower case form of the canonical key is also stored for searching purposes. Any aliases for example I are also stored in lower case form .

If a new representation of a header key comes in for example CONTENT LENGTH it is converted into lower case form to find the canonical form in this case Content Length . The new representation is added to the map to increase the speed of a future search with this representation.

When a new header key comes in for example NewHeaderKey the new format is used as the new canonical key in this case NewHeaderKey and its lower case representation in this case newheaderkey is added to allow future search of other representations of the same key.

This invention proposes a method allowing access to header fields of messages based on HTTP format in particular SIP where header names are case insensitive multi valued ordered and possibly accessed with aliases.

The solution is based on a front end key normalization map allowing quick retrieval of a normalized form of the header name from any other of its variants including alias . Then the header search is based on a simple integer comparison instead of string comparison.

The described solution is particularly valuable in SIP engines such as an IMS CSCF IP Multimedia Subsystem Call Session Control Function where thousands of messages have to be processed every second each one with several dozens of headers.

The described method may also be self adaptive for possible private keys not in the list of keys defined by the protocol.

The solution is applicable to all data structures that use a such case insensitive attribute naming convention such as Internet mail.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.


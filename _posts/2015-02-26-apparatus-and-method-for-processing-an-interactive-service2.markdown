---

title: Apparatus and method for processing an interactive service
abstract: A method of processing an interactive service and an apparatus thereof are disclosed. The present invention includes receiving uncompressed audio contents or uncompressed video contents from an external decoding unit, extracting an identifier of a frame from the received content, sending a request containing the identifier to a server and receiving a trigger for the content from the server based on the request, wherein the trigger indicates the current time of the contents and references a particular interactive event in an application parameter table or signals that the event is to be executed now or at a specified future time and the application parameter table includes information about at least one of applications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09596494&OS=09596494&RS=09596494
owner: LG ELECTRONICS INC.
number: 09596494
owner_city: Seoul
owner_country: KR
publication_date: 20150226
---
This application is a Continuation of application Ser. No. 13 972 673 filed Aug. 21 2013 which claims the benefit under 35 U.S.C. 119 e of U.S. Provisional Application Nos. 61 691 805 filed on Aug. 22 2012 and 61 703 749 filed on Sep. 20 2012 all of which are hereby expressly incorporated by reference into the present application.

The present invention relates to a method and apparatus for providing receiving and processing a broadcast service and more particularly to a method and apparatus for providing a supplementary service related to broadcast content.

TVs first appeared at the end of the 19th century and have become the most popular information delivery apparatus since the end of the 20th century as a screen display method or design thereof has been continuously developed. However TVs generally enable viewers to receive unidirectional information from a broadcast station. Such TV limitations have become problematic as personal computers PCs and the Internet have come into widespread use since the 1990s. Therefore TVs have been developed to be able to provide an interactive service.

However currently there is no system for providing an interactive service between a content provider and a viewer. In particular in order to provide such an interactive service there is a need for a method of executing an application related to broadcast content which is currently being broadcast at a specific time and providing related information to a viewer through special information processing.

Accordingly the present invention is directed to a method and apparatus for processing an interactive service that substantially obviates one or more problems due to limitations and disadvantages of the related art.

An object of the present invention is to provide supplementary information related to broadcast content at an appropriate time during a period when the broadcast content is played back.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein a method of processing an interactive service at a receiver n includes receiving uncompressed audio contents or uncompressed video contents from an external decoding unit extracting an identifier of a frame from the received content sending a request containing the identifier to a server and receiving a trigger for the content from the server based on the request wherein the trigger indicates the current time of the contents and references a particular interactive event in an application parameter table or signals that the event is to be executed now or at a specified future time wherein the application parameter table includes information about at least one of applications.

Preferably the trigger is a time base trigger when no event activation is scheduled to take place before sending a next request and the time base trigger is used to maintain a time of a segment.

Preferably the trigger is an activation trigger when an activation is due to take place wherein the activation trigger sets an activation time for the event and the activation time is indicated by an timing value term in the activation trigger.

Preferably the method further comprises downloading a new application parameter table immediately unless the receiver has already retrieved the new application parameter table using URL information delivered with the application parameter table when the trigger includes an application parameter table identifier which identifies the new application parameter table.

Preferably the method further comprises obtaining an application URL for a new application associated with the trigger from the application parameter table or the new application parameter table when the receiver does not have the new application and downloading the new application using the application URL.

Preferably the activation trigger is applied once when the receiver receives more than one activation trigger for same event activation.

Preferably the activation trigger is applied as soon as the activation trigger arrives when the activation trigger is received after the activation time.

Preferably the time is a media time and the media time is a parameter referencing a point in the playout of a content item.

Preferably the application is a Declarative Object a Triggered Declarative Object a Non Real Time Declarative Object or an Unbound Declarative Object.

In another aspect of the present invention an apparatus for processing an interactive service includes a receiving module configured to receive uncompressed audio contents or uncompressed video contents from an external decoding unit an identifier extracting module configured to extract an identifier of a frame from the received content and a network interface configured to send a request containing the identifier to a server and receive a trigger for the content from the server based on the request wherein the trigger indicates the current time of the contents and references a particular interactive event in an application parameter table or signals that the event is to be executed now or at a specified future time and the application parameter table includes information about at least one of applications.

Preferably the trigger is a time base trigger when no event activation is scheduled to take place before sending a next request and the time base trigger is used to maintain a time of a segment. Preferably the trigger is an activation trigger when an activation is due to take place wherein the activation trigger sets an activation time for the event and the activation time is indicated by an timing value term in the activation trigger.

Preferably the network interface further configured to download a new application parameter table immediately unless the apparatus has already retrieved the new application parameter table using URL information delivered with the application parameter table when the trigger includes an application parameter table identifier which identifies the new application parameter table.

Preferably the apparatus further comprises a trigger module configured to obtain an application URL for a new application associated with the trigger from the application parameter table or the new application parameter table when the apparatus does not have the new application wherein the network interface further configured to download the new application using the application URL.

Preferably the activation trigger is applied once when the apparatus receives more than one activation trigger for same event activation.

Preferably the activation trigger is applied as soon as the activation trigger arrives when the activation trigger is received after the activation time.

Preferably the time is a media time and the media time is a parameter referencing a point in the playout of a content item.

Preferably the application is a Declarative Object a Triggered Declarative Object a Non Real Time Declarative Object or an Unbound Declarative Object.

It is to be understood that both the foregoing general description and the following detailed description of the present invention are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Although the terms used in the present invention are selected from generally known and used terms terms used herein may be variable depending on operator s intention or customs in the art appearance of a new technology or the like. In addition some of the terms mentioned in the description of the present invention have been selected by the applicant at his or her discretion the detailed meanings of which are described in relevant parts of the description herein. Furthermore it is required that the present invention is understood not simply by the actual terms used but by the meanings of each term lying within.

In the present specification the term media time stands for a parameter referencing a point in the playout of an audio video or audio content item. ACR stands for Automatic Content Recognition. AMT stands for Activation Messages Table. API stands for Application Programming Interface. DAE stands for Declarative Application Environment. DO stands for Declarative Object. FLUTE stands for File Delivery over Unidirectional Transport. GPS stands for Global Positioning System. HTTP stands for Hypertext Transfer Protocol. IP stands for Internet Protocol. IPTV stands for Internet Protocol Television. iTV stands for Interactive Television. MIME stands for Internet Media Type. NDO stands for NRT Declarative Object. NRT stands for Non Real Time. SMT stands for Service Map Table. SSC stands for Service Signaling Channel. TDO stands for Triggered Declarative Object. TPT stands for TDO Parameters Table. UDO stands for Unbound Declarative Object. UPnP stands for User Plug and Play. URI stands for Uniform Resource Identifier. URL stands for Uniform Resource Locator. XML stands for eXtensible Markup Language. TFT stands for Text Fragment Table. Details thereof will be described below.

DO Declarative Object can be a collection constituting an interactive application. For example HTML JavaScript CSS XML and multimedia files .

The term Triggered Declarative Object TDO is used to designate a Declarative Object that has been launched by a Trigger in a Triggered interactive adjunct data service or a DO that has been launched by a DO that has been launched by a Trigger and so on iteratively.

The term NRT Declarative Object NDO is used to designate a Declarative Object that has been launched as part of an NRT service that is not a Triggered interactive data service.

The term Unbound Declarative Object UDO is used to designate a Declarative Object that is not bound to a service such as a Packaged App or a DO launched by a Link or a DO that has been launched by such a DO and so on iteratively.

The Link is a broadcaster provided URL that points to a web site which provides on line information or functionality related to the current TV programming or NRT service.

The Packaged App is a broadcaster provided Declarative Object DO that provides information or functionality which the broadcaster wants to offer viewers and that is packaged up into a single file for viewers to download and install.

In this specification a time base message includes a time base trigger and an equivalent thereof. Accordingly the term time base message may be used interchangeably with the term time base trigger .

In this specification an activation message includes all information delivery causing activation such as an activation element in an AMT and or an activation trigger.

A typical broadcast stream consists of a sequence of TV programs. Each TV program consists of an underlying show which is typically broken up into blocks separated by ads and or other interstitial material.

In Segment of Show A Ad Ad Segment of Show B etc. are sequentially included in the broadcast stream. Segments configuring each show may be referred to as show content and Ads may be referred to as interstitial content.

Each show or piece of interstitial material might or might not have an interactive adjunct data service associated with it.

The term interactive service segment or just segment will be used in this specification to refer to a portion of an interactive adjunct service that is treated by the broadcaster as an integrated unit. An interactive service segment is typically but not necessarily associated with a single show or a single piece of interstitial material.

In order to execute such an interactive adjunct data service there are two models Direct execution model and triggered declarative object TDO model.

In the direct execution model a declarative object DO can be launched automatically as soon as the virtual channel is selected. It can communicate over the Internet with a backend server to get detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

In the TDO model signals can be delivered in the broadcast stream or via the Internet in order to initiate TDO events such as launching a TDO terminating a TDO or prompting some task by a TDO. These events can be initiated at specific times typically synchronized with the audio video program. When a TDO is launched it can provide the interactive features it is programmed to provide.

A basic concept behind the TDO model is that the files that make up a TDO and the data files to be used by a TDO to take some action all need some amount of time to be delivered to a receiver given their size. While the user experience of the interactive elements can be authored prior to the broadcast of the content certain behaviors must be carefully timed to coincide with events in the program itself for example the occurrence of a commercial advertising segment.

The TDO model separates the delivery of declarative objects and associated data scripts text and graphics from the signaling of the specific timing of the playout of interactive events.

The information about the TDOs used in a segment and the associated TDO events that are initiated by Triggers is provided by a data structure called the TDO Parameters Table TPT .

Trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events.

The trigger includes a time base trigger which serves to indicate a media time of a segment related to an interactive service and an activation trigger which serves to indicate an event occurrence time of an application related to an interactive service.

Triggers can perform various timing related signaling functions in support of interactive services. Triggers can be multi functional depending on their structure a particular Trigger instance can perform one or more of the following functions 

As shown a short time prior to the occurrence of programming segment a pre load Trigger can be delivered to allow receivers an opportunity to acquire the TPT and interactive content associated with programming segment . If a pre load Trigger is not transmitted receivers can be expected to use the first Trigger they see within the segment to acquire the content.

Triggers can be sent throughout segment as shown to indicate the current Media Time labeled m in the figure relative to the segment. Periodic delivery of Media Time Triggers can be necessary to allow receivers who are just encountering the channel to synchronize and acquire the interactive content.

In the case of pre produced content non live the TPT that the receiver can acquire after processing the first Trigger can define the timing of all elements of the interactive experience for that segment. All that is needed for the receiver and TDO to play out the interactive elements can be the knowledge of the media timing the TPT can describe interactive events relative to Media Time.

For the case of live content the TPT still contains data and information pertinent to different interactive events however the timing of playout of those events cannot be known until the action in the program unfolds during the broadcast. For the live case the event timing function of the Trigger is utilized. In this mode the Trigger can signal that a specified interactive event is to be re timed to a specified new value of Media Time. Alternatively the Trigger can indicate that a certain event is to be executed immediately.

A third trigger is an event re timing trigger and indicates that the event with eventID 2 in the TPT is to be re timed to occur at Media Time . The hatched area indicates the time interval prior to over which Trigger 3 may be delivered to receivers.

A fifth trigger is an event re timing trigger and indicates that the event with eventID 5 in the TPT is to be re timed to occur at Media Time .

An eighth trigger is an event Trigger and indicates that the event with eventID 12 in the TPT is to be executed immediately.

A ninth trigger is an event re timing Trigger and indicates that the event with eventID 89 in the TPT is to be re timed to occur at Media Time .

A TDO can exist in four different states Released Ready Active and Suspended. A number of different factors can cause a transition from one state to another trigger user action changing channels etc. .

The TDO may include the following four states. The four states are Ready Active Suspended and Released. Ready state means that TDO is downloaded and prepared for execution but not yet executing. Active state means that TDO is executing. Suspended state means that TDO is temporarily suspended from execution with its state saved. Released state means that TDO is not Ready Active or Suspended.

Both Activation messages and Time Base messages can have the general Trigger format under certain delivery circumstances.

The syntactic definition here is described using the Augmented Backus Naur Form ABNF grammar except that the vertical bar symbol is used to designate alternatives. Rules are separated from definitions by an equal indentation is used to continue a rule definition over more than one line literals are quoted with parentheses and are used to group elements optional elements are enclosed in and brackets and elements may be preceded with to designate n or more repetitions of the following element n defaults to 0. And elements may be preceded with designate n or more repetitions and m or less repetitions of the following element.

This Trigger syntax is based on the Uniform Resource Identifier URI Generic Syntax excluding the and portion with additional restrictions.

The trigger may include locator part and terms. Terms may be omitted. If terms are present locator part and terms may be connected by .

The hostname may include domainlabel and toplabel and domainlabel may be repeated 0 times or more along with . . That is hostname may include repeated domainlabel connected with toplabel or include only toplabel.

domainlabel may include one alphanum or include alphanum or repeatedly inserted between alphanum and alphanum 0 times or more.

toplabel includes one alpha or include alphanum or repeatedly inserted between alpha and alphanum 0 times or more.

path segments includes one segment which is followed by segment repeated 0 times or more. At this time segments may be connected by .

Terms may include one of event time or media time which may be followed by spread or others. Spread and others may be omitted. If spread and others are present may be placed ahead of spread and others and spread and others may be placed after event time or media time.

Event time may include digit repeated once or more after e or include hexdigit repeated once or more or seven times or less after zt . zt and the back part thereof may be omitted.

The length of the trigger may not exceed 52 bytes. In addition the hostname portion of the Trigger can be a registered Internet domain name.

The can reference a registered Internet domain name. The can be an arbitrary character string identifying a directory path under the control and management of the entity who owns rights to the identified domain name.

In the TDO model the combination of and can uniquely identify a TPT that can be processed by a receiver to add interactivity to the associated content.

The combination of and can be the URL of an Internet location where the TPT for the current segment can be obtained.

That is the trigger may identify the TPT using and . Through and it is possible to confirm the TPT to which the trigger applies. The role performed by applying the trigger to the TPT depends on .

The event time term can be used in an Activation trigger to identify the targeted event e term and the time the event should be activated t term . When the t term is absent that means the event should be activated at the time the trigger arrives.

That is e which is an interactive event ID term can reference the appID in the associated TPT of the TDO targeted by the event the eventID of the specific event and the dataID of the Data element to be used for this event activation.

 t which is an optional timing value term can indicate a new media timing for the designated event. If the t part is not present that can mean the timing for the designated event is the arrival time of the Trigger.

The media time term m term can be used in a Time base trigger to identify the current time relative to the time base represented by the Time base trigger. Content identifier information c term for identifying currently displayed content may be further included in media time. For c term the direct execution model will be described below.

That is m which is a media timestamp term followed by a character string of 1 to 8 characters in length representing a hexadecimal number can indicate the current Media Time.

The spread term can be used to indicate that any action taken in response to a Time base trigger such as retrieving a TPT from a server or an Activation trigger such as causing a TDO to access a server should be delayed a random amount of time to spread out the workload on the server.

 s term can indicate the number of seconds of time over which all receivers should attempt to access the Internet server identified in the Trigger. Each individual receiver can be expected to derive a random time within the designated interval and delay the access request by that amount thereby spreading in time the peak in demand that might otherwise occur at the first appearance of a Trigger at the receiver.

A Trigger containing a parameter can be called a Time base trigger since it is used to establish a time base for event times.

A Trigger containing an parameter can be called an Activation Trigger since it sets an activation time for an event.

A TDO Parameters Table TPT contains metadata about the TDOs of a segment and the Events targeted to them.

Hereinafter fields included in the table will be described. The sizes of the fields and the types of the fields included in the table may be added or changed according to designer s intention.

TDO parameter table TPT may include majorProtocolVersion minorProtocolVersion id tptVersion expireDate updatingTime serviceID baseURL attributes Capabilities LiveTrigger and or TDO element.

TPT is the root element of the TPT. One TPT element describes all or a portion in time of one programming segment.

 MajorProtocolVersion which can be 4 bit attribute can indicate the major version number of the table definition. The major version number can be set to 1. Receivers are expected to discard instances of the TPT indicating major version values they are not equipped to support.

When present MinorProtocolVersion which can be 4 bit attribute can indicate the minor version number of the table definition. When not present the value defaults to 0. The minor version number can be set to 0. Receivers are expected to not discard instances of the TPT indicating minor version values they are not equipped to support. In this case they are expected to ignore any individual elements or attributes they do not support.

 id which is URI can uniquely identify the interactive programming segment which This TPT element pertains to. id serves as an identifier of a segment. Accordingly after a receiver parses the TPT a trigger an AMT etc. related to one segment may match the TPT having id for identifying the segment using id information. Accordingly a segment to which the trigger and the AMT will apply may be found. The details of the AMT will be described below.

 tptVersion which can be 8 bit integer can indicate the version number of the TPT element identified by the id attribute. The tptVersion can be incremented whenever any change is made to the TPT.

When present expireDate attribute of the TPT element can indicate the date and time of the expiration of the information included in this TPT instance. If the receiver caches the TPT it can be re used until the expireDate.

When present updatingTime which can be 16 bit element can indicate that the TPT is subject to revision and it gives the recommended interval in seconds to download the TPT again and check whether the newly downloaded TPT is a new version.

When present serviceID which can be 16 bit integer can indicate the NRT service id associated with the interactive service described in this TPT instance. This is needed for receivers to get FLUTE parameters from the Service Map Table when files for this interactive service are delivered in the broadcast stream.

When present baseURL attribute can give a base URL which when concatenated onto the front of any relative URLs that appear in this TPT. It can give the absolute URLs of the files.

When present Capabilities element can indicate capabilities that are essential for a meaningful presentation of the interactive service associated with this TPT. Receivers that do not have one or more of the required capabilities are expected not to attempt to present the service.

LiveTrigger element presents if and only if delivery of Activation Triggers via Internet is available. When present it can provide information needed by a receiver to obtain the Activation Triggers. The child element and attribute of LiveTrigger will be described below.

TDO which is a child element of the TPT element can represent an application for example a TDO that provides part of the interactive service during the segment described by this TPT instance. The child element and attribute of TDO will be described below.

As described above LiveTrigger element presents if and only if delivery of Activation Triggers via Internet is available. When present it can provide information needed by a receiver to obtain the Activation Triggers.

 URL which is an attribute of the LiveTrigger element can indicate the URL of a server that can deliver Activation Triggers via Internet. Activation Triggers can be delivered via Internet using HTTP short polling HTTP long polling or HTTP streaming at the option of the interactive service provider.

When present pollPeriod which is an attribute of the LiveTrigger element can indicate that short polling is being used to deliver Activation Triggers and the value of the pollPeriod attribute can indicate the recommended time in seconds for the receiver to use as a polling period.

If LiveTrigger element is present the receiver may parse the TPT and obtain information used to deliver the activation trigger using the Internet. The URL of the server which may receive the activation trigger may be used using URL information. Through pollPeriod information or information indicating that pollPeriod attribute is not present a method of delivering the activation trigger via the Internet and information about the polling period may be obtained. pollPeriod will be described in detail below.

TDO element may include appID appType appName globalID appVersion cookieSpace frequencyOfUse expireDate testTDO availInternet availBroadcast attribute URL Capabilities Contentitem and or Event element.

As described above TDO which is a child element of the TPT element can represent an application for example a TDO that provides part of the interactive service during the segment described by this TPT instance.

 appID which can be 16 bit integer can identify the application uniquely within the scope of the TPT. An Activation Trigger identifies the target application for the Trigger by means of a reference to the appID. appID is an identifier of an application. One TPT may include several applications such as TDO . Accordingly after parsing the TPT the application may be identified using appID information. The trigger AMT etc. which will apply to one application may match an application having appID for identifying the application. Accordingly the application to which the trigger and the AMT will apply may be found. The AMT will be described in detail below.

 appType which can be 8 bit integer can indicate the application format type. The default value can be 1 which can represent a TDO. Other values can represent other formats.

 appName which is attribute of the TDO element can be a human readable name which can be displayed to a viewer when a viewer s permission is sought to launch the application.

 globalID which is attribute of the TDO element can be a globally unique identifier of the application. In many cases a receiver will cache an app that is going to be used again before too long. In order for this to be useful the receiver must be able to recognize the app the next time it appears. A globalID is needed for the receiver to be able to recognize the app when it appears again in a new segment.

 appVersion which is attribute of the TDO element can be the version number of the application. The appVersion value can be incremented whenever the application as identified by the globalID changes. The appVersion attribute cannot be present if the globalID attribute is not present.

 cookieSpace which can be 8 bit integer can indicate how much space the application needs to store persistent data between invocations.

 frequencyOfUse which can be 4 bit integer can indicate approximately how frequently the application will be used in the broadcast to provide guidance to receivers on managing their application code cache space. frequencyOfUse will be described in detail below.

 expireDate which is attribute of the TDO element can indicate a date and time after which the receiver can safely delete the application and any related resources.

When present with value true testTDO which is Boolean attribute can indicate that the application is for testing purposes only and that it can be ignored by ordinary receivers.

The value true for availInternet attribute can indicate that the application is available for downloading over the Internet. The value false can indicate that the application is not available for downloading over the Internet. When the attribute is not present the default value can be true .

The value true for availBroadcast attribute can indicate that the application is available for extraction from the broadcast. The value false can indicate that the application is not available for extraction from the broadcast. When the attribute is not present the default value can be true .

Each instance of URL a child element of the TDO element can identify a file which is part of the application. URL element may include entry attribute. entry an attribute of the URL element has value true that can indicate that the URL is an entry point for the application i.e. a file that can be launched in order to launch the application. When it has value false that can indicate that the URL is not an entry point for the application. The default value when the attribute does not appear can be false . The URL element which is the child element of the TDO element identifies a file configuring the application as described above. The receiver parses the TPT to obtain URL information accesses the server using the URL information and downloads an application indicated by the URL information.

When present Capabilities which is child element of the TDO element can indicate capabilities that are essential for a meaningful presentation of this application. Receivers that do not have one or more of the required capabilities are expected not to attempt to present launch the application.

ContentItem a child element of the TDO element can indicate a content item consisting of one or more data files that are needed by the application. ContentItem element has information about data files required by an application indicated by the TDO element to which this element belongs. The receiver may download data files required by the application using URL information etc. of ContentItem if the ContentItem element is present after parsing. The child element and attribute of ContentItem will be described below.

Event a child element of the TDO element can represent an event for the application. Event element indicates an event of an application to which this element belongs. The event element contains information indicating which events are present which data is present which action is present etc. The receiver may parse the event element to obtain information about the event of the application. The child element and attribute of the event will be described below.

The receiver may receive and parse the TPT to obtain the child element of the TDO and the information about attributes.

ContentItem element which is the child element of the TDO element may include updateAvail pollPeriod size availInternet availBroadcast attribute and or URL element.

Here URL element may include entry attribute. Each instance of URL a child element of the ContentItem element can identify a file which is part of the content item. URL element may include entry attribute. entry an attribute of the URL element has value true that can indicate that the URL is an entry point for the content item i.e. a file that can be launched in order to launch the content item. When it has value false that can indicate that the URL is not an entry point for the content item. The default value when the attribute does not appear can be false . The receiver may download data files required by the application using URL information of ContentItem after parsing. In this process the information such as the above described other attributes may be used.

 updatesAvail which is a boolean attribute of the ContentItem element can indicate whether or not the content item will be updated from time to time i.e. whether the content item consists of static files or whether it is a real time data feed. When the value is true the content item will be updated from time to time when the value is false the content item will not be updated. The default value when this attribute does not appear can be false.

 pollPeriod which is an attribute of the ContentItem element may be present only when the value of the updatesAvail attribute is true . The presence of the pollPeriod attribute can indicate that short polling is being used to deliver Activation Triggers and the value of the pollPeriod attribute can indicate the recommended time in seconds for the receiver to use as a polling period.

The value true for availInternet attribute can indicate that the content item is available for downloading over the Internet. The value false can indicate that the content item is not available for downloading over the Internet. When this attribute is not present the default value can be true. 

The value true for availBroadcast attribute can indicate that the content item is available for extraction from the broadcast. The value false can indicate that the content item is not available for extraction from the broadcast. When this attribute is not present the default value can be true. 

The event element contains information about the event of the application indicated by the TDO element to which the event element belongs. The receiver may parse the event element to obtain information about the event.

The event element which is the child element of the TDO element may include eventID action destination diffusion attribute and or Data element. Here the data element may include dataID attribute.

 eventID which can be a 16 bit integer attribute of the Event element can identify the event uniquely within the scope of the TDO element containing it. An Activation Trigger or activation element in AMT can identify the target application and event for the Trigger by the combination of appID and eventID. When an event is activated receivers pass the event in to the application. eventID serves as an identifier of an event. Using eventID information a trigger AMT etc. for activating the event may match an application having eventID for identifying the event. That is an Activation Trigger or activation element in AMT can identify the target application and event for the Trigger by the combination of appID and eventID. When an event is activated receivers pass the event in to the application. The AMT will be described in detail below.

 action which is an attribute of the Event element can indicate the type of action to be applied when the event is activated. Allowed values can be prep exec susp and kill .

 prep can correspond to the Trig prep action. If the state of the targeted application is Released this action can cause a state change to Ready. 

 exec can correspond to the Trig exec action. The state of the targeted application can become Active upon reception of this trigger.

 susp can correspond to the Trig susp action. If the state of the targeted application is Active the state can change to Suspended upon reception of this trigger otherwise there is no change.

 kill can correspond to the Trig kill action. The state of the targeted application can become Released upon reception of this trigger.

 destination which is an attribute of the Event element can indicate the target device for the event. destination will be described in detail below.

When present diffusion which can be an 8 bit integer attribute of the Event element can represent a period T of time in seconds. The purpose of the diffusion parameter is to smooth peaks in server loading. The receiver can be expected to compute a random time in the range 0 T in increments of 10 milliseconds and delay this amount before accessing an Internet server to retrieve content referenced by URLs in the TPT.

When present Data which is a child element of the Event element can provide data related to the event. Different activations of the Event can have different Data elements associated with them. The data element may include dataID attribute. dataID which is a 16 bit integer attribute can identify the Data element uniquely within the scope of the Event element containing it. When an activation of an event has data associated with it the Activation Trigger can identify the Data element by the combination of AppID EventID and DataID. The data element indicates data used for the event. One event element may have several data elements. Data is identified using dataID attribute of the data element. In the receiver if the event related to the data is activated the Activation Trigger or activation element in AMT can identify the Data element by the combination of AppID EventID and DataID. AMT will be described in detail below.

The Meaning column indicates the frequency of occurrence of segments that contain this application. An attribute can appear multiple times within a single segment of course. The frequencyOfUse attribute cannot be present if the globalID attribute is not present. If the app is going to be cached and used again later the receiver needs to recognize that it is the same app when it appears again. This requires the globalId attribute.

As shown in the destination attribute value of 0 indicates reserved the destination attribute value of 1 indicates primary device only the destination attribute value of 2 indicates one or more secondary devices only 2 and the destination attribute value of 3 indicates Primary device and or one or more secondary devices.

This is the binary format of the above described TPT structure. This structure is a format necessary when the TPT is transmitted in NRT and is made such that the XML structure of the TPT is suitably transmitted in NRT.

The following elements and or attributes contained in the XML version of the TPT can be omitted from the binary version since they can be provided by the encapsulation header for delivering the binary table in the broadcast stream protocolVersion major minor serviceID and tptVersion.

The semantics of the fields are as follows. Fields of the binary format of TDO parameter table of and will be sequentially described.

expire date included which can be 1 bit field can indicate whether the expire date field is included. The value 1 can mean it is included the value 0 can mean it is not included.

segment id length which can be a 5 bit field can indicate the length in bytes of the segment id field.

segment id which is a variable length field can contain the bytes of the segment id which can have the same semantics as the id attribute of the TPT XML format.

base URL which is a variable length field can contain the bytes of the base URL which can have the same semantics as the baseURL attribute of the TPT XML format.

When present expire date which can be a 32 bit field can indicate the date and time of the expiration of the information included in this TPT instance. If the receiver caches the TPT it can be re used until the expireDate. The unsigned integer can be interpreted as the number of GPS seconds since 00 00 00 UTC 6 Jan. 1980 minus the GPS UTC offset. The GPS UTC offset can be an 8 bit unsigned integer that defines the current offset in whole seconds between GPS and UTC time standards.

trigger server URL length which can be an 8 bit field can indicate the length in bytes of the trigger server URL field. When the value of this field is 0 it can indicate that internet delivery of individual Activation Triggers is not available.

trigger server URL when the value of the trigger server URL length field is not 0 can contain the bytes of the Trigger Server URL which can have the same semantics as the URL attribute of the LiveTrigger element of the TPT XML format.

trigger delivery type which can be a 1 bit field can indicate the delivery mode of individual Activation Triggers over the Internet. The value 0 can indicate that HTTP short polling is being used the value 1 can indicate that either HTTP long polling or HTTP streaming is being used.

poll period which can be an 8 bit integer can indicate the recommended number of seconds between polls when HTTP short polling is being used.

num apps in table which can be an 8 bit field can indicate the number of applications TDOs described in this TPT instance.

app id which can be a 16 bit field can contain an identifier for this application the application described in this iteration of the num apps in table loop . It can be unique within this TPT instance.

app type included which can be a 1 bit field can indicate whether the app type field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

app name included which can be a 1 bit field can indicate whether the app name field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

global id included which can be a 1 bit field can indicate whether the global id field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

app version included which can be a 1 bit field can indicate whether the app version field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

cookie space included which can be a 1 bit field can indicate whether the cookie space field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

frequency of use included which can be a 1 bit field can indicate whether the frequency of use field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

expire date included which can be a 1 bit field can indicate whether the expire date field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

When present app type which can be an 8 bit field can indicate the format type of this application. The value 0 can indicate that the application is a TDO. If this field is not present the value can default to 0. Other values can represent other formats.

When present app name  which can be an 8 bit field can indicate the length in bytes of the app name field immediately following it. The value 0 for this field can indicate that no app name field is present for this application.

When present app name which is a variable length field can have the same semantics as the appName attribute of the TDO element in the TPT XML format.

When present global id length which can be an 8 bit field can indicate the length in bytes of the global id field immediately following it. The value 0 for this field can indicate that no global id field is present for this application.

When present global id which is a variable length field can have the same semantics as the globalId attribute of the TDO element in the TPT XML format.

When present app version which can be an 8 bit field has the same semantics as the appVersion attribute of the TDO element in the TPT XML format.

When present cookie space which can be an 8 bit field can have the same semantics as the cookieSpace attribute of the TDO element in the TPT XML format.

When present frequency of use which can be an 8 bit field can have the same semantics as the frequencyOfUse attribute of the TDO element in the TPT XML format.

When present expire date which can be an 8 bit field can have the same semantics as the expireDate attribute of the TDO element in the TPT XML format.

test app which can be a 1 bit field can indicate whether or not this application is a test application intended to be ignored by ordinary receivers. The value 1 can mean it is a test application the value 0 can mean it is not a test application.

available on internet which can be a 1 bit field can indicate whether or not this application is available via the Internet or not. The value 1 can mean it is available via the Internet the value 0 can mean it is not available via the Internet.

available in broadcast which can be a 1 bit field can indicate whether or not this application is available via the broadcast or not. The value 1 can mean it is available via the broadcast the value 0 can mean it is not available via the broadcast. number URLs which can be a 4 bit field can indicate the number of files that comprise this application.

URL which is a variable length field can have the same semantics as the URL attribute of the TDO element in the TPT XML format.

number content items which can be an 8 bit field can indicate the number of content items that are to be downloaded for use by this application.

updates avail which can be a 1 bit field can indicate whether this content item will be updated from time to time i.e. whether it a set of static files or a real time data feed. The value 1 can indicate that it will be updated the value 0 can indicate that it will not be updated.

avail internet which can be a 1 bit field can indicate whether the file s that comprise this content item can be downloaded via the Internet or not. The value 1 can mean that they are available for downloading via the Internet the value 0 can mean they are not available.

avail broadcast which can be a 1 bit field can indicate whether the file s that comprise this content item can be downloaded via the broadcast or not. The value 1 can mean that they are available for downloading via the broadcast the value 0 can mean they are not available.

content size included which can be a 1 bit field can indicate whether or not the content size field is included or not for this application. The value 1 can mean it is included the value 0 can mean it is not included.

number URLs which can be a 4 bit field can indicate the number of files that comprise this content item.

URL which is a variable length field can have the same semantics as the URL attribute of the ContentItem child element of the TDO element in the TPT XML format.

content size which can be a 24 bit field can have the same semantics as the contentSize attribute of the ContentItem child element of the TDO element in the TPT XML format.

num content descriptors which can be an 8 bit field can indicate the number of content descriptors in the descriptor loop immediately following it.

content descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this content item. Among the descriptors that may be included in this descriptor loop can be the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of this content item.

event id which can be a 16 bit field can contain an identifier for this event the event described in this iteration of the number events loop . It can be unique within the scope of this application. The event can be referenced within Activation Triggers by the combination of app id and event id.

action which can be a 5 bit field can have the same semantics as the action attribute of the Event child element of the TDO element in the TPT XML format.

destination included which can be a 1 bit field can indicate whether or not the destination field is included for this event. The value 1 can indicate that it is included the value 0 can indicate that it is not included.

diffusion included which can be a 1 bit field can indicate whether or not the diffusion field is included for this event. The value can indicate that it is included the value 0 can indicate that it is not included.

data included which can be a 1 bit field can indicate whether or not the data size and data bytes fields are included for this event. The value 1 can indicate that they are included the value 0 can indicate that they are not included.

When present the semantics of destination field can be the same as the semantics of the destination attribute of the Event child element of the TDO element in the TPT XML format.

When present the semantics of diffusion field can be the same as the semantics of the diffusion attribute of the Event child element of the TDO element in the TPT XML format.

When present the data size field can indicate the size of the data bytes field immediately following it.

When present the data bytes field can provide data related to this event. Whenever the event is activated the target application will be able to read the data and use it to help carry out the desired action. The content of this field can be identical to the content of the corresponding Data child element of the corresponding Event child element of the corresponding TDO element in the TPT XML format except that this field can contain the raw binary value and the Data element in the TPT XML format can contain a base64 encoding of the binary value.

num app descriptors which can be an 8 bit field can indicate the number of descriptors in the descriptor loop immediately following it.

app descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this application TDO . Among the descriptors that may be included in this descriptor loop is the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of this application.

num TPT descriptors which can be an 8 bit field can indicate the number of descriptors in the descriptor loop immediately following it.

TPT descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this TPT. Among the descriptors that may be included in this descriptor loop is the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of the interactive service represented by this TPT.

An Activation Messages Table AMT can contain the equivalent of the Activation Triggers for a segment. Under certain circumstances it can be delivered to receivers in lieu of Activation Triggers. A trigger can be delivered in the closed caption stream by ACR servers by a live trigger server and via AMT.

An Activation Messages Table AMT may include majorProtocolVersion minorProtocolVersion segmentId beginMT attribute and or Activation element.

 majorProtocolVersion which can be a 4 bit attribute of the AMT element can indicate the major version number of the AMT definition. The major version number can be set to 1. Receivers can be expected to discard instances of the AMT indicating major version values they are not equipped to support.

When present minorProtocolVersion which can be a 4 bit attribute of the AMT element can indicate the minor version number of the AMT definition. When not present the value can default to 0. The minor version number can be set to 0. Receivers can be expected to not discard instances of the AMT indicating minor version values they are not equipped to support. In this case they can be expected to ignore any individual elements or attributes they do not support.

 segmentID which is an identifier of the AMT matches the identifier of the TPT which contains the applications and events to which the Activations in this AMT apply. segmentId may serve as an identifier of the AMT. Accordingly the receiver may receive and parse the AMT to identify the AMT via segmentId information. segmentId contains information indicating to which segment the AMT applies matches id of the TPT related to the segment and serves to connect the AMT and the TPT. Further the segment may be identified to provide basic information necessary to identify the target TDO and the event of the activation element of the AMT.

When present beginMT which is an attribute of the AMT element can indicate the beginning Media Time of the segment for which this AMT instance provides activation times. beginMT may indicate beginning of the media time with respect to a segment to which the AMT will apply. Therefore it is possible to decide a criterion of a time when activation indicated by the activation element occurs. Accordingly if beginMT is present startTime attribute in the activation element may be influenced by the beginning of the media time indicated by beginMT.

Each instance of Activation element of the AMT can represent a command to activate a certain event at a certain time with certain data associated with the event. A plurality of activation elements may be present in the AMT. Each activation element performs a role similar to that of the activation trigger. The activation element may apply to the segment indicated by segmentId in the AMT. Attributes of the activation element may contain information about in which application activation occurs in which event activation occurs when activation occurs etc. Attributes of the activation element will be described in detail below.

 targetTDO which is an attribute of the Activation element can match the appID attribute of a TDO element in the TPT with which the AMT is associated thereby identifying the target application for the activation command. targetTDO may contain information to which application the activation element of the AMT applies. The receiver may receive and parse the AMT to obtain targetTDO and find appID in the TDO element of the matching TPT to identify the application to which the activation element will apply.

 targetEvent which is an attribute of the Activation element can match the eventID attribute of an Event element contained in the TDO element identified by the targetTDO attribute thereby identifying the target event for the activation command. targetEvent may contain information to which event of which application the activation element of the AMT applies. The receiver may receive and parse the AMT to obtain targetEvent and find eventID in the TDO element of the matching TPT to identify the event to which the activation element will apply.

 targetData which is an attribute of the Activation element can match the dataID attribute of a Data element contained in the Event element identified by the targetTDO and targetEvent attributes thereby identifying the Data that is to be associated with the target event when the activation command applies. targetData may identify data related to the target event when the activation command applies. The receiver may receive and parse the AMT to obtain targetData and find dataID in the event element of the TPT.

 startTime which is an attribute of the event element can indicate the start of the valid time period for the event relative to Media Time. Receivers can be expected to execute the command when Media Time reaches the value in startTime or as soon thereafter as possible. startTime may indicate a start time when the event occurs. This start time is based on the media time. The receiver may parse the AMT to obtain startTime information and confirm the time when the event occurs using startTime. The receiver may activate the event if the media time reaches the startTime based on the media time of the segment identified by segmentId. If startTime has been already elapsed the event may be activated as soon as possible.

When present endTime which is an attribute of the event element can indicate the end of the valid time period for the event relative to Media Time. The receiver can be expected to not execute the command when Media Time is past the value in endTime. endTime may indicate the end time of the event. If the media time reaches the endTime the receiver may not perform the event.

When a receiver is activating events according to the Activations in an AMT it can be expected to apply each activation at its startTime or as soon thereafter as possible for example in the case when a receiver joins the service and receives the AMT at some time after the startTime and before the endTime . If the action attribute of the event element in TPT is exec then the receiver can be expected to pass a TriggerEvent in to the target application. TriggerEvent will be described below in the part related to the API.

A URL List can contain certain URLs of potential use to a receiver. The URL list may include the following URLs etc.

Among others the URL list may be made with respect to the UrsUrl element so as to further indicate the URL of the server for usage reporting in order to use preferred data and the type of content viewed and consumed currently through the receiver in business. The UrsUrl element included in the URL list may be variously interpreted as follows.

First in case of a usage reporting server the receiver may perform the usage reporting function of the receiver by a predetermined protocol e.g. data structure XML file etc. with the URL of the usage reporting server.

Second there may be a TDO executed on the web browser of the receiver. In this case this indicates the location of the Usage Reporting TDO. In this case the TDO may directly collect and report information about content stored in the receiver or consumed currently using the API e.g. file APIs or usage reporting APIs of the web browser of the receiver. The TDO may transmit the collected data using Javascript API called XMLHttpRequest.

URLlist may include UrlList TptUrl UrsUrl and or PdiUrl. The semantics of these elements is as follows.

TptUrl which is an element of the UrlList element can contain the URL of a TPT for a future segment in the current interactive adjunct service. When multiple TptUrl elements are included they can be arranged in order of the appearance of the segments in the broadcast.

NrtSignalingUrl which is an element of the UrlList element can contain the URL of a server from which receivers can obtain NRT signaling tables for all the virtual channels in the current transport stream.

UrsUrl which is an element of the UrlList element can contain the URL of a server to which receivers can send usage audience measurement reports for the current virtual channel.

PdiUrl which is an element of the UrlList element can contain the URL of the PDI Q table for the current virtual channel.

Hereinafter Output from Interactive Service Creation Delivery of Triggers in the Broadcast Stream Delivery of Time base triggers via the Internet Delivery of Activation Triggers via Internet ACR Scenario Delivery of TPTs in Broadcast Stream Delivery of TPTs via Internet Moving TDOs and Content Items Combining Multiple Segments into One Segment will be sequentially described.

Among others Output from Interactive Service Creation Delivery of Triggers in the Broadcast Stream Delivery of Time Base Triggers via the Internet Delivery of Activation Triggers via Internet ACR Scenario Moving TDOs and Content Items Combining Multiple Segments into One Segment are not limited to this specification and may be changed according to designer s intention although not shown.

The process of service creation for a segment can result in folder containing all TDOs and other content items TPT file in XML format and AMT file in XML format. The other results may be created.

When delivered in the broadcast stream Triggers can be delivered in the DTV Closed Caption channel in Service 6 in the URLString command.

If the Trigger is less than or equal to 26 characters in length it can be sent non segmented Type 11 . If the Trigger is 27 to 52 characters in length it can be sent in two segments the first segment in a Type 00 segment and the second segment in a Type 10 segment .

For interactive services using the TDO model the URI type of the URI data structure can be set to 0 Interactive TV Trigger for TDO model . This delivery mechanism includes both Time base triggers and Activation Triggers.

In the case in which the time base trigger is delivered via a broadcast stream in closed caption service 6. if m term is absent Time base triggers can simply deliver URL of Signaling Server. And if m term is absent then t term must be absent from Activation triggers.

In the case in which the activation trigger is delivered via a broadcast stream in closed caption service 6. that is in the case of Trigger format with e term with or without t term if t term is present activation time can be the timestamp relative to a time base. And if t term is absent activation time can be the arrival time of the message.

In the case in which the time base trigger and the activation trigger are delivered via CC service 6 there can be three possible ways for broadcasters to handle Time Base and Activation triggers. The three ways are Segment mode without explicit time base Segment mode with explicit time base and Service mode with explicit time base .

In segment mode without explicit time base Activation messages include no time stamp so that the activation time of each message can be the delivery time of the message and Time Base messages also include no time stamp so that their only purpose can be to provide the URL of the Signaling Server that can deliver TPT files. Time Base messages can even be omitted entirely in this mode relying on the URL in the Activation messages to provide the URL of the Signaling Server but then receivers will not be able to retrieve a TPT and start downloading TDOs until after the first Activation message appears delaying the response to the first Activation message by quite a bit.

In this case Time Base messages that can appear in CC service 6 can contain the locator part of the Trigger format and possibly the spread term but no media time term and Activation messages that can appear in CC service 6 can contain the locator part of the Trigger format the event time term and possibly the spread term but with no t part in the event time term. The locator part of both Time Base and Activation messages can be the current segmentId. This URL can also be used to retrieve the TPT for the segment via the Internet.

In segment mode with explicit time base Time Base messages include a time stamp to define a time base and Activation messages might include a time stamp to define the activation time relative to the time base or they might include no time stamp indicating that the activation time is the arrival time of the message.

In this case Time Base messages that can appear in CC service 6 can contain the locator part of the Trigger format the media time term and possibly the spread term and Activation messages that can appear in CC service 6 can contain the locator part of the Trigger format the event time term and possibly the spread term with or without the t part in the event time term. The locator part of both Time Base and Activation messages can be the current segmentId and the time base is specific to the segment. This URL can also be used to retrieve the TPT for the segment via the Internet.

In service mode with explicit time base Time Base messages include a time stamp to define a time base and Activation messages might or might not include a time stamp. The time base can extend across multiple segments rather than being specific to a single segment. The locator part of the Time Base messages can be an identifier of the time base and also a URL that can be used to retrieve TPTs for the service via the Internet.

In any case the Trigger Insertion Server that inserts the triggers into CC service 6 should work from the AMT translating the Activation messages from the XML format in the AMT into the trigger format specified for delivery in CC service 6. In the case of an Activation element with no endTime attribute a single trigger can be inserted with activation time equal to the startTime attribute. In the case of an Activation element with both startTime and endTime elements a sequence of triggers can be inserted with same target. The first trigger in the sequence can have activation time equal to the startTime attribute the last trigger in the sequence can have activation time equal to the endTime attribute and there can be a fixed time interval between the activation times of the triggers in the sequence except that the interval between the next to last and last trigger in the sequence can be shorter . The length of this fixed time interval can be configurable.

When the Time Base and Activation messages are in segment mode the time base can be specific to the segment. It can start with the beginMT value at the beginning of the segment and run through the segment. The startTime and endTime values of individual Activations can be relative to the beginMT value. When the Time Base and Activation messages are in service mode the time base can span segments and the beginMT value for each segment can be adjusted to take account of the service time base and the broadcast schedule.

Internet delivery of Time base triggers can be useful in so called Automatic Content Recognition ACR situations where the recipient of the Time base triggers has no access to Closed Caption service 6. In these situations the receiver needs to use ACR in order to recognize video frames and synchronize the time base with them. In ACR situations Time Base messages can be obtained from watermarks or from ACR servers. In case of reception from the ACR server the Time Base messages are delivered as responses from an ACR server.

Activation messages can be delivered via short polling long polling or streaming but all of these can impose a lot of overhead on the receivers and the server. Activation messages can also be delivered in the form of an AMT but this can provide a good deal of information about the length of segments facilitating ad killers. There might be other alternatives.

In the case in which the activation message is delivered in the form of the activation trigger that is in case of Trigger format with e term with or without t term this may be delivered via HTTP short polling long polling or streaming.

When delivered via Internet Activation messages can be delivered using either or both of the mechanisms Individual Activation Trigger Delivery mechanism and Bulk Activation Trigger Delivery mechanism.

As described above when individual Activation Triggers are delivered via the Internet they can be delivered using HTTP short polling long polling or streaming. The format of the Activation Trigger can be exactly the same as when they are delivered via DTVCC service 6.

In case of short polling the polling period must be specified. In this period a short polling operation may be set using pollPeriod included in the TPT as described below.

When Internet delivery of Activation Triggers is available the URL attribute of the LiveTrigger element in the TPT can indicate the Activation Trigger Server which can deliver activation trigger. If the pollPeriod attribute of the LiveTrigger element is present in the TPT this can indicate that HTTP short polling is being used and it can indicate the polling period a receiver should use. If the pollPeriod attribute of the LiveTrigger element is not present in the TPT this can indicate that either HTTP long polling or HTTP streaming is being used.

Regardless of which protocol is being used the receiver can be expected to issue an HTTP request to the Activation Trigger Server with the query term 

If short polling is being used the response from the Activation Trigger Server can contain all the Triggers that have been issued within the time interval of length pollPeriod ending at . If more than one Activation Trigger is returned they can be separated by one or more white space characters. If no Activation Triggers are returned the response can be empty.

If HTTP long polling or HTTP streaming is being used the Activation Trigger Server can wait to return a response until the media time when an Activation Trigger would be delivered in the broadcast stream. At this time it can return the Activation Trigger.

If HTTP long polling is being used the Activation Trigger Server can close the session after returning an Activation Trigger. The receiver can be expected to immediately issue another request with an updated media time.

If HTTP streaming is being used the Activation Trigger Server can keep the session open after returning each Activation Trigger and it can deliver additional Activation Triggers over the session as the time arrives for them to be delivered.

In all cases the HTTP response can contain an HTTP Response Header Field of one of the following forms to signal the delivery mode 

The parameter can indicate the recommended interval between polls for the succeeding polls. The can be omitted.

When Activation Triggers are delivered via the Internet in bulk the Activation Triggers for a segment can be delivered via HTTP along with the TPT for the segment in the form of a multi part MIME message with the TPT as the first part of the message and an Activation Messages Table AMT as the second part of the message.

When delivered in the broadcast stream TPTs can be translated from their XML format into an equivalent binary NRT style signaling table format and encapsulated in NRT style private sections one TPT per table instance. The TPT for the current segment is always present. TPTs for one or more future segments may also be present. The TPT instance is defined by the value of its segment id field. For reference the binary format of the TDO parameter table was described above.

In summary in order to transmit the binary structure of the TPT in NRT the TPT may have a section structure suitable for NRT transmission. Hereinafter this process will be described in detail.

Each TPT can be encapsulated in NRT style private sections by dividing each TPT into blocks and inserting the blocks into the tpt bytes fields of sections that have a common value of table id protocol version TPT data version and sequence number fields. The blocks can be inserted into the sections in order of ascending section number field values. The private sections can be carried in the Service Signaling Channel SSC of the IP subnet of the virtual channel to which the TPT pertains. Here Service Signaling Channel is defined in the ATSC NRT standard and means a channel having a specific IP address and a port number. The sequence number fields in the sections can be used to distinguish different TPT instances carried in the same SSC.

The private section tpt section may include table id protocol version sequence number TPT data version current next indicator section number last section number and or service id and tpt bytes information.

table id which can be an 8 bit field can identify this table section as belonging to a TDO Parameters Table instance.

protocol version may be divided into two parts. The high order 4 bits of this 8 bit unsigned integer field can indicate the major version number of the definition of this table and the TPT instance carried in it and the low order 4 bits can indicate the minor version number. The major version number can be set to 1. Receivers can be expected to discard instances of the AMT indicating major version values they are not equipped to support. The minor version number can be set to 0. Receivers can be expected to not discard instances of the AMT indicating minor version values they are not equipped to support. In this case they can be expected to ignore any descriptors they do not recognize and to ignore any fields that they do not support.

sequence number can be an 8 bit field. The value of sequence number can be the same as the sequence number of all other sections of this TPT instance and different from the sequence number of all sections of any other TPT instance in this Service Signaling Channel. Accordingly this field may perform a role different from that of the other TPT instance. sequence number field may indicate an IP subnet associated with a service signaling channel in this section. The values of the sequence number fields of the different TPT instances can reflect the order in which the segments appear in the broadcast stream.

TPT data version which can be a 5 bit field can indicate the version number of this TPT instance where the TPT instance can be defined by its segment id. Since the TPT version is known in advance in order to determine whether the received TPT section data is a new version TPT the TPT data version field may be present in the section table. The version number can be incremented by 1 modulo 32 when any field in the TPT instance changes.

current next indicator which can be a 1 bit indicator can always be set to 1 for TPT sections indicating that the TPT sent is always the current TPT for the segment identified by its segment id.

section number which can be an 8 bit field can give the section number of this TPT instance section where the TPT instance can be identified by its segment id. The section number of the first section in an TPT instance can be 0x00. The section number can be incremented by 1 with each additional section in the TPT instance.

last section number which can be an 8 bit field can give the number of the last section i.e. the section with the highest section number of the TPT instance of which this section is a part.

service id which can be a 16 bit field can specify the service id associated with the interactive service offering the content items described in this table instance.

tpt bytes which is a variable length field can consist of a block of the TPT instance carried in part by this section. When the tpt bytes fields of all the sections of this table instance are concatenated in order of their section number fields the result can be the complete TPT instance.

That is after the binary format of the TPT is used or the XML format is changed to a binary format the TPT may be divided to be suitable for NRT transmission included in tpt bytes field of the private section and transmitted in NRT. At this time if one TPT is divided into several private sections the private section may have the same table id protocol version TPT data version and sequence number value. The divided TPT blocks may be inserted in order of section number field values.

The receiver may parse the received private sections. In order to combine the private sections into one TPT again the private sections having the same table id protocol version TPT data version and sequence number values may be used. At this time order information capable of being obtained from section number and last section number information may be used. If tpt bytes of all private sections having the same table id protocol version TPT data version and sequence number values are sequentially connected one TPT may be created.

When delivered over the Internet TPTs can be delivered via HTTP. The URL of the TPT for the current segment can be the in Time Base messages. The response to a request for a TPT can consist of just the TPT or it can consist of a 2 part MIME message with the requested TPT in the first part and a list of URLs in the second part encoded as an XML document. The response to a request will always include the TPT for the current segment. It may include TPTs for one or more future segments as well. 

 TptUrl can contain the URL of a TPT for a future segment. When multiple TptUrl elements are included they can be arranged in order of the appearance of the segments in the broadcast.

 NrtSignalingUrl can contain the URL of a server where receivers can obtain NRT signaling tables for all the virtual channels in the current broadcast stream.

Networks and stations will often need to provide their own HTTP servers for delivering TDOs and content items files used by TDOs. When this is done the baseURL in the TPT can be adjusted to reflect the location of the server.

In order to thoroughly obfuscate boundaries between segments the TPTs and AMTs for multiple segments can be combined into a single TPT and AMT. The following steps may be performed.

In order to support synchronization of Declarative Object actions to broadcast programming additional methods can be supported for the video broadcast object.

If the TPT is received via the DTVCC or the Internet several events for executing the TDO may be present in the TPT and these events may be activated by the activation trigger.

In order to process this event a Listener function may be registered on a per eventID basis. Accordingly as the above described additional methods the two functions addTriggerEventListener and removeTriggerEventListener for registering the Listener function may be present.

addTriggerEventListener function can register a callback function listener function for processing an event generated on a per eventId basis.

removeTriggerEventListener function can cancel registration of a callback function listener function for processing an event generated on a per eventId basis.

The addTriggerEventListener function may receive the listener of EventListener type and eventId of Number type as argument. EventListener type will be described below. The addTriggerEventListener function may not have a return value void .

The trigger processing module of the receiver may register the listener function on a per eventId basis using the addTriggerEventListener function as soon as the activation message is received. If the event is activated the registered listener function may be called. At this time the object of TriggerEvent type may be delivered to the listener function. TriggerEvent type will be described below.

The removeTriggerEventListener function may receive the listener of EventListener type and eventId of Number type as argument. EventListener type will be described below. The removeTriggerEventListener function may not have a return value void .

Here the eventide argument may be eventide in the event element of the TPT. Here the listener argument may be a listener for the event.

In the javascript program if the event which may be generated on a per eventId basis is desired to be no longer received or if the program DestroyWindow is finished the listener function registered using removeTriggerEventListener may be cancelled.

EventListener type may have an event TriggerEvent type as argument. EventListener may be an interface.

TriggerEvent type may have eventId data and status as properties. Here eventId may be eventID in the event element of the TPT. Here data may be data for this activation of the event. Here data may be hexadecimal. Here status may mean the status of the event. Here if the status value is trigger this means a status in which the event is activated by the activation trigger. If the status value is error this means a status in which error occurs.

In the Direct Execution model a Declarative Object DO can be launched automatically as soon as the virtual channel is selected. It can communicate over the Internet with a backend server to get detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

In the direct execution model an application is launched automatically as soon as the virtual channel is selected. Application can communicate over the Internet with a backend server via a Synchronized Content Protocol . The server can give detailed instructions for providing interactive feature which is all synchronized with the audio video program.

In case of the direct execution model since an application is immediately executed information may be delivered to the currently executed application as a time base trigger is delivered. In this model the application needs to continuously deliver information about currently broadcast content to the server for synchronization. To this end the time base trigger may further include special information different from that of the TDO model. This special information may be an identifier of currently broadcast content.

Similarly the content identifier may be present in the parameter part of the trigger in the form of a parameter.

Similarly the content identifier may be present in media time of the trigger in the form of one term. The content identifier term which can be called content id which can be designated by c followed by a character string can represent an identifier for the content currently being viewed.

The content id term can be intended to support the Direct Execution model of interactive service implementation.

As described above in this model Time base triggers with content id term can be passed in to the application after it is launched and the application can deliver the content id to the backend server in order to identify the context for the interaction. Detailed operation thereof will be described below.

The delivery mechanism of the trigger in the direct execution module is equal to that described above.

However in case of Delivery of Triggers in the Broadcast Stream Triggers can be delivered in the DTV Closed Caption channel in Service 6 in the URLString command And for interactive services using the Direct Execution model the URI type field can be set to 2 Interactive TV Trigger for Direct Execution model .

As one model for executing interactive service in the direct execution model an application can be launched automatically as soon as the virtual channel is selected. The application can communicate over the Internet with a backend server via a Synchronized Content Protocol. The server can give detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

First of all an application can be launched. Then a time base trigger is received. The time base trigger is delivered to the application after the application has been executed. The content id term of the time base trigger may include content identification information of currently displayed content. The application can deliver the content id to the backend server in order to identify the context for the interaction and in order to identify the content currently being viewed.

In an environment in which only uncompressed video and audio can be accessed for example as received from a cable or satellite set top box architecture and protocols capable of acquiring an interactive service are defined. The architecture and protocols can be designed to be used by receivers that have Internet connections and that only have access to the uncompressed audio and video from the broadcast stream. Of course the architecture and protocols can be used successfully if the interactive service provider chooses to support them.

The architecture can be designed to support two basic approaches to identifying the content being viewed so that any associated interactive service data enhancements can be delivered via Internet. Two basic approaches may be Watermarking or Fingerprinting.

In both the watermarking and fingerprinting approaches the intent can be to allow receivers to find out what programming is currently being watched and obtain a URL that can be used as the starting point to get additional information about interactive services for the programming.

In Architecture for WM Approach the architecture may include a broadcaster a watermark inserter an MVPD an STB a receiver a WM client a TPT server and a content server .

The broadcaster may be a source for providing an audio video stream and an interactive service related thereto. Examples of the broadcaster may include a TV station etc. The broadcaster may be a producer or distributor of broadcast content. The broadcaster may deliver broadcast streams audio video contents interactive data broadcast schedule AMT etc.

The watermark inserter may inert watermarks into broadcast audio video frames. The watermark inserter may be combined with or separated from the broadcaster . The watermark may be information necessary for the receiver. The watermark may be information such as URL. The watermark will be in detail below.

The MVPD may be an abbreviation for Multiprogram Video Program Distributor. The MVPD may be a cable operator a satellite operator or an IPTV operator. The MVPD can receive the broadcast stream from the Broadcaster Watermark Inserter with the watermarks inserted by the watermark inserter in the case of a watermarking ACR system. MVPD often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs in customer premises.

The STB typically decodes decompresses the audio and video and sends them to a TV set for presentation to viewers. The STB may send uncompressed audio video content to the receiver . The STB may be an external decoding unit according to one embodiment of the present invention.

The receiver may include a WM client . The WM Client may be located outside the receiver . Here the receiver is a watermarking capable receiver. The structure of the receiver will be described below.

The WM Client can get Activation Triggers from the ACR server not shown and passes them in to the main receiver code using an API provided for that purpose. Normally the WM Client would be built into the receiver but other configurations are possible. The WM Client may extract the inserted watermarks from the uncompressed audio video content. The watermarks may be information such as URL.

The TPT server may download an application such as a TPT. After the extracted watermark is transmitted to the ACR server if the watermark matches a watermark stored in a database not shown the receiver may receive a trigger or triggers as a response. If the received trigger may have the above described new locator part or a TPT or if an application parameter table of a new version number is found the receiver may request and download the TPT or application parameter table from the TPT server .

The content server may provide an application TDO etc. necessary to provide an interactive service. If a new application or TDO is necessary the new application etc. may be downloaded using the URL of the TPT or application parameter table.

In the watermarking WM approach the broadcaster watermark inserter can insert watermarks into the broadcast audio or video frames. These watermarks can be designed to carry a modest amount of information to receivers while being imperceptible or at least minimally intrusive to viewers. Such watermarks might provide directly the information that receivers need or they might only provide a code value that receivers can send via an Internet connection to a remote server in order to get the information they need.

In Architecture for FP Approach the architecture may include a broadcaster an MVPD an STB a receiver a FP Client a TPT server a content server a signature extractor and a FP server .

The broadcaster may be a source for providing an audio video stream and an interactive service related thereto. Examples of the broadcaster may include a TV station etc. The broadcaster may be a producer or distributer of broadcast content. The broadcaster may deliver broadcast streams audio video contents interactive data broadcast schedule AMT etc.

The MVPD may be an abbreviation for Multiprogram Video Program Distributor. The MVPD may be a cable operator a satellite operator or an IPTV operator. The MVPD often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs in customer premises.

The STB typically decodes decompresses the audio and video and sends them to a TV set for presentation to viewers. The STB may send uncompressed audio video contents to the receiver . The STB may be an external decoding unit according to one embodiment of the present invention.

The receiver may include a FP client . The FP Client may be located outside the receiver . Here the receiver is a fingerprinting capable receiver. The structure of the receiver will be described below.

The FP Client can get Activation Triggers from the FP Server and passes them in to the main receiver code using an API provided for that purpose. Normally the FP Client would be built into the receiver but other configurations are possible. FP Client may extract a fingerprint from uncompressed audio video contents. The fingerprint will be described below.

The TPT server may download an application such as a TPT. After the extracted fingerprint is transmitted to the FP server if the fingerprint matches a signature of the signature extractor the receiver may receive a trigger or triggers as a response. If the received trigger may have the above described new locator part or a if TPT or an application parameter table of a new version number is found the receiver may request and download the TPT or application parameter table from the TPT server .

The content server may provide an application TDO etc. necessary to provide an interactive service. If a new application or TDO is necessary the new application etc. may be downloaded using the URL of the TPT or application parameter table.

The signature extractor may receive metadata from the broadcaster . The signature extractor may extract a signature of a frame from the received metadata. If the fingerprint received by the FP server matches the signature of the signature extractor the signature extractor may send metadata related thereto to the FP server .

The FP server may perform a signature matching process with the signature extractor . The FP server may perform a matching process between the signature and the fingerprint received from the receiver . If the signature matches the fingerprint the FP server may receive the metadata related thereto from the signature extractor . The FP server may transmit the received metadata to the receiver .

In the fingerprinting FP approach FP Client can extract fingerprints also can be called signatures from audio or video frames and check the fingerprints against a database of fingerprints of broadcast frames from multiple broadcasters in the area to find the information the receivers need. Such checks can be done by signatures to a remote server and getting back a record with the desired information or in some cases they can be done by checking against a database of signatures that has been downloaded into the receiver . Here the remote server may be the FP server .

Although watermarking and fingerprinting can be distinct technologies they are not necessarily exclusive of one another. Using a combination of the two technologies is quite conceivable. The term automatic content recognition ACR can be used to refer to either of these technologies separately or to any combination of the two of them.

An environment in which a receiver only has access to the uncompressed audio and video from the broadcast stream is called an ACR environment. 

In both WM and FP cases receivers can use the URL as a starting point to get interactive service content including triggers.

In both WM and FP cases the timing information can be in the form of a timestamp relative to a broadcast side clock that is used for specification of the timing of time critical events for the channel such as activation timestamps in triggers delivered over the Internet.

It is assumed that broadcasters can typically support delivery of interactive services directly in the broadcast stream for the benefit of receivers that get TV signals from antennas and also support delivery of interactive services over the Internet as described above for the benefit of receivers that get uncompressed audio and video but have an Internet connection. However broadcasters can support either one of these two delivery mechanisms without the other.

A typical architecture for the watermarking approach in the case when the watermark provides only a code value would look something like a combination of the two architectures in and . There would be a Watermark Inserter as in but it would insert a code rather than the information needed by receivers. There would also be a WM Server playing much the same role as the FP Server in . Receivers would send it codes rather than signatures and they would get back the information they need.

The accessing interactive services may include Direct Execution Model TDO Model with Activations Independent of ACR Server TDO Model with Activations Received from ACR Server which is not limited to this specification and may be changed according to designer s intention although not shown.

There are a number of different ways for a receiver in an ACR environment to access interactive services depending on broadcaster choices and the nature of the ACR system. The interactive service model can be the Direct Execution model or the TDO model and Activation In the case of the TDO model Triggers can be delivered independently of the ACR Server or they can be delivered by the ACR Server.

An ACR process for a virtual channel that contains an interactive service which has the Direct Execution Model can provide to receivers viewing that channel the equivalent of Time Base Triggers that include the media time m term and the content id c term. These Triggers can be identified as Triggers for an interactive service with the Direct Execution model.

When a receiver first receives such a Trigger with a new locator part it can be expected to load into its browser the Declarative Object DO pointed to by the locator part of the Trigger. Typically the DO will have been pre installed or previously downloaded and cached. Otherwise the receiver can be expected to download it using an HTTP GET request.

Then the DO can contact the appropriate back end server and provide the interactive service as directed by the back end server.

The receiver can be expected to make that initial Trigger and subsequent Triggers available to the DO as they are obtained until such time as it gets a Trigger from the ACR server that has a new locator part and or that is identified as a Trigger for an interactive service with the TDO model either of which typically indicates a channel change .

An ACR process for a virtual channel that can contain an interactive service which has the TDO model and which provide event activations independently of the ACR Server can provide to receivers viewing that channel the equivalent of Time Base Triggers that can include the media time m term. These Triggers can be identified as Triggers for an interactive service with the TDO model.

When a receiver first receives such a Trigger with a new locator part it can be expected to retrieve the current TDO Parameters Table TPT from the TPT Server can be pointed to by the locator part of the Trigger and to use the media time in that Trigger and subsequent Triggers to establish a reference time base for event activations relative to the audio or video frames can be identified by the ACR process.

If an Activation Messages Table AMT is delivered along with the TPT the receiver can be expected to use the individual Activation elements in the table to activate events at the correct times relative to the time base established by the media time terms in the Triggers. These events can include loading and executing a TDO causing a TDO to take a particular synchronized action suspend a TDO etc. 

If a LiveTrigger element is included in the TPT the receiver can be expected to retrieve Activation Triggers from the Live Trigger Server identified by the URL in the LiveTrigger element using the polling method signaled in the LiveTrigger element and to use these Activation Triggers to activate events at the correct times relative to the time base established by the media time terms in the Triggers.

Both an AMT and a Live Trigger Server can be used for the same service typically with the former providing static activations and the latter providing dynamic activations. Alternatively an AMT can be used alone when all activations for the segment are static or a Live Trigger Server can be used alone to deliver both static and dynamic activations.

How the Activation Triggers for a TDO interactive service model is delivered without a separate trigger server in the ACR environment will be described.

Fingerprinting ACR systems can include an ACR server. Receivers can send frame signatures to an ACR server and the ACR server can identify the frame represented by the signature and send back the information needed by the receivers. Watermarking ACR systems can include an ACR server in the case when the watermarks consist of no more that codes that can be sent to an ACR server to get the information needed by receivers. Watermarking ACR systems may not include an ACR server in the case when the watermarks themselves contain the information needed by receivers. In those ACR systems that include an ACR server two different models can be used for communication between the ACR servers and receivers a request response model and an event driven model.

Three cases such as ACR Server using request response model ACR Server using event driven model and Watermarking ACR system inserting information directly will be assumed.

In the cases with an ACR server the ACR method could be fingerprinting in which case receivers compute some sort of signature or fingerprint of audio or video frames and submit them to an ACR server for identification or it could be watermarking in which case receivers extract codes in the form of watermarks from the audio or video frames and submit the codes to an ACR server for identification.

Hereinafter for convenience of description a description will be given using the terms of fingerprinting signatures. However the system equally operates even in case of watermarking codes and the present invention is not limited to a fingerprinting method.

In the request response ACR model the receiver can be expected to generate signatures of the content periodically e.g. every 5 seconds this is only exemplary and may be changed according to designer s intention and send requests containing the signatures to the ACR server. When the ACR server gets a request from a receiver it can return a response. The communications session may not kept open between request response instances. In this model it may be not feasible for the ACR server to initiate messages to the client.

For an ACR server that is using this request response model and is delivering Activation Triggers to receivers each response from the ACR server can be one of Null Time Base Trigger and Activation Trigger.

A Null response can indicate that the signature is not recognized or if the ACR Ingest Module includes signatures for frames in program segments with no interactive service that the signature represents a frame which belongs to a segment that does not have an interactive service associated with it. The ACR ingest module will be described below.

A Time Base Trigger response can indicate that no event activation is scheduled to take place before the client s next request. The client can be expected to use the Time Base Triggers to maintain a media time clock.

An Activation Trigger response can indicate that an activation is due to take place soon with the time of the activation indicated by the t term in the Trigger.

Whenever a receiver gets a Trigger with a new locator part it can be expected to download the new TPT immediately unless it has already retrieved it using a URLList delivered with a previous TPT.

Whenever a receiver gets an Activation Trigger it can be expected to activate the event at the time indicated by the t term in the Trigger relative to the media time clock.

In the receiver can be sending signatures for frames which the ACR server determines to have media times MT MT and MT. For the frame with media time MT the receiver just gets a response that contains a Time Base Trigger. For the frame with media time MT a static activation is due at media time MTa so the receiver gets a response that contains an Activation Trigger which has a t MTa term. For the frame with media time MT the receiver just gets a response that contains a Time Base Trigger.

It can happen that a receiver receives more than one Activation Trigger for the same event activation. However the media times for each of them will be the same so the receiver can identify them as duplicates and only apply one of them.

Hereinafter the case in which the ACR server uses a request response model will be described. This is similar to the description of .

In the receiver can be sending signatures for frames viewed at local clock times LC LC LC etc. The media time for the frame viewed at local clock time LC can be determined by the ACR server to be MT and the receiver just gets a response that contains a Trigger with no media time or event time. The media time for the frame viewed at local clock time LC can be determined by the ACR server to be MT and the ACR server knows that a static activation is due at media time MTa so the ACR server sends a response that contains an Activation Trigger which has a d term meaning that the media time MTa for the activation is time units after MT. The receiver then adds the to time LC and gets LCa as the local time it should activate the event.

Hereinafter the case in which dynamic activation occurs in Request Response ACR Case will be described.

For dynamic activations in situations when the ACR System does not learn of the event activation until it is too late to send the Trigger to the receiver ahead of time the ACR Server needs to wait until the next request and then sends an Activation Trigger. illustrates this case. The effect of this is that dynamic activations can be delayed by as much as one request interval.

In the receiver can be sending signatures for frames that the ACR server determines to have media times MT MT and MT. For the frames with media times MT and MT the receiver just gets a response that contains a Time Base Trigger. When a dynamic activation with activation time MTa shows up at or shortly before media time MTa the ACR server cannot notify the receiver about it until the next request from the receiver which occurs for the frame with media time MT. At that time the ACR server response contains an Activation Trigger with activation time MTa which is a little in the past . In this situation the receiver can be expected to apply the Activation Trigger as soon as it arrives.

Here again it is possible that a receiver receive more than one Activation Trigger for the same event activation. However the media time for each of them will be the same so the receiver can identify them as duplicates and only apply one of them.

Hereinafter the case in which dynamic activation occurs in Request Response ACR Case will be described. This is similar to the description of .

In the receiver can be sending signatures for frames viewed at local clock times LC LC LC etc. The media time for the frame viewed at local clock time LC can be determined by the ACR server to be MT and the receiver just gets a response that contains a Trigger with no media time or event time. The media time for the frame viewed at local clock time LC can be determined by the ACR server to be MT and the ACR server does not know that a dynamic activation will show up at media time MTa so the receiver just gets a response that contains a Trigger with no media time or event time. When a dynamic activation shows up at media time MTa the ACR server cannot notify the receiver about it until the next request from the receiver which occurs at local time LC. At that time the ACR server response can contain an Activation Trigger with a negative value or contains a do it now activation trigger.

Hereinafter Watermarking ACR System Inserting Information Directly will be described. Although this is not shown details of the present invention are not limited to the following and may be changed according to designer s intention.

In the case of a watermarking system that inserts the information receivers need directly the watermark associated with a frame can follow the same rules as stated above for what a request response ACR server would return for that frame as follows. The request response ACR server can return one of Null Time Base Trigger and Activation Trigger.

A Null response can indicate that the signature is not recognized or if the ACR Ingest Module includes signatures for frames in program segments with no interactive service that the signature represents a frame which belongs to a segment that does not have an interactive service associated with it.

A Time Base Trigger response can indicate that no event activation is scheduled to take place before the client s next request. The client can be expected to use the Time Base Triggers to maintain a media time clock.

An Activation Trigger response can indicate that an activation is due to take place soon with the time of the activation indicated by the t term in the Trigger.

In the case of a watermarking ACR system that is delivering the information receivers need by including it directly in the watermarks so that no ACR server is needed an Ingest Module can follow the same rules as described for the request response server model above to determine the Trigger to associate with each frame but then include the Trigger in the watermark for the frame rather than associate the Trigger with the frame in a Database. The ingest module and database will be described.

Hereinafter support for stand alone NRT services will be described. Although this is not shown details of the present invention are not limited to the following and may be changed according to designer s intention.

In order for a receiver in an ACR environment to get access to stand alone NRT services the broadcaster may need to support Internet access to the NRT services and the receiver may need to obtain the SMT and the NRT IT instances for the services

If a broadcaster supports this protocol for a particular broadcast stream then a receiver that knows the URL of the broadcaster s Signaling Server for that broadcast stream can take the following steps.

First the receiver can issue a query for the Basic NRT Set of tables for the broadcast stream for a specified future time interval for example the next 12 hours .

Second this will produce the SMT and ILT for each of the stand alone NRT virtual channels and the NRT IT and TFT instances covering the specified time interval.

One way a receiver can discover the URL of the Signaling Server for a broadcast stream can be that the provider of an interactive service segment in the broadcast stream can choose to provide the Signaling Server URL in a URLList element delivered along with the TPT.

Another way a receiver can discover URLs of Signaling Servers can be by pre configuration. In the same way that a DTV receiver manufacturer can pre configure a DTV receiver to know how to find an ACR Server covering any particular broadcast area a DTV receiver manufacturer can pre configure a DTV receiver to know how to find an NRT Discovery Server covering any particular broadcast area. Such an NRT Discovery Server would be able to give the receiver a list of the broadcast streams that contain stand alone NRT services along with the Signaling Server URL for each one.

Some ACR systems include an ACR server and some ACR systems do not. In fingerprinting ACR systems receivers can compute and send frame signatures to an ACR server and the ACR server can send back the information needed by the receivers. Thus fingerprinting ACR systems include an ACR server. In watermarking ACR systems the watermarks may contain only codes that uniquely identify the frames or the watermarks may contain the full information needed by receivers. When the watermarks contain only codes receivers can extract the codes and send them to an ACR server and the ACR server sends back the information needed by the receivers. In the case when the watermarks include the full information receivers can just extract the information they need directly from the watermarks and no ACR server is needed.

In those ACR systems that include an ACR server two different models can be commonly used for communication between the ACR servers and receivers a request response model and an event driven model.

In the request response ACR server model the receiver can be expected to compute signatures of or extract codes from the content periodically e.g. every 5 seconds and send requests containing the signatures or codes to an ACR server. When an ACR server gets a request from a receiver it can return a response. The communications session is not kept open between request response instances. In this model it may not feasible for an ACR server to initiate messages to a receiver.

It is assumed that the broadcaster of the channel being processed is supporting the TDO interaction model.

There can be two general type of event activations static activations in which the activation time is known before the broadcast of the segment begins and dynamic activations in which the activation time in determined dynamically as the segment is being broadcast. In pre recorded segments all of the event activations can be static. In segments that are broadcasting live shows some or all of the event activations can be dynamic. Static activations are typically listed in the Activation Messages Table AMT although they might be delivered to receivers in the form of Activation Triggers. Dynamic activations can be delivered in the form of Activation Triggers since their timing is not known at the time the AMT is generated.

In the architecture to support ACR systems that use an ACR server the architecture may include a broadcast source an ACR Ingest Module an MVPD an STB a receiver an ACR Client an ACR Config Server an ACR Server and a Database .

The Broadcast Source can be a point where the A V stream and associated interactive service is emitted for example a network distribution point or a TV station.

An ACR Ingest Module can compute signatures fingerprints of frames in the case of a fingerprinting ACR system or insert watermarks consisting of codes into frames in the case of a watermarking ACR system that is based on codes. It can store in the database the media time of each frame associated with a signature or code together with other metadata. An ACR Ingest Module could handle a single channel in a broadcast stream or an entire broadcast stream or multiple broadcast streams or any combination thereof. For the purposes it is assumed that the ACR Ingest Module processes frames for program segments that contain an interactive service. However it is possible to have ACR systems in which all frames are processed but those that are not part of a segment with an interactive service have an indication in their database entry that they are not part of a segment with an interactive service.

A Multiprogram Video Program Distributor MVPD is typically a cable operator satellite operator or IPTV operator. It can receive the broadcast stream from the Broadcast Source in some way with the watermarks inserted by the ACR Ingest Module in the case of a watermarking ACR system Such a system often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs in customer premises.

A STB typically decodes decompresses the audio and video and sends them to a TV set for presentation to viewers. We are assuming that DTV Closed Caption service 6 which contains interactive service Triggers is not available to the TV Set.

The receiver may include the ACR Client . The ACR Client may be located outside the receiver . The structure of the receiver will be described below.

The ACR Client in an receiver can get Activation Triggers from the ACR Server and pass them in to the main receiver code using an API provided for that purpose. Normally the ACR client would be built into the receiver but other configurations are possible.

The ACR Config Server can provide a way for ACR clients to determine the location of a suitable ACR Server . This discovery process could be achieved in other ways.

An ACR Server can get signatures or codes from receivers and return Activation Triggers at appropriate times.

The Database can be a data store of some kind not necessarily a database in the strict sense of the term in which information about audio or video frames or both is stored for the use of ACR Servers .

The architecture of an ACR system that uses direct delivery of information in watermarks could have no Database and no ACR Server. The ACR Ingest Module could insert information directly into the frames in the broadcast stream in the form of watermarks instead of inserting into a Database records that contain identifiers of frames and the information associated with them. Receivers could then extract this information from the frames in the broadcast instead of getting it from an ACR server.

Hereinafter delivery of Activation Triggers via request response ACR servers will be described stepwise.

An efficient way to implement this ACR Server behavior is to follow the process described below where the numbers of the actions in the process correspond to the numbers in the architecture diagram above .

1 The broadcast schedule for the interactive service segments and the AMTs or their equivalents for each segment can be delivered to the ACR Ingest Module ahead of the time the segments are broadcast. The broadcast schedule can contain the segment ID GPS start time and GPS end time of each segment that can contain an interactive service associated with it. If there are any last minute changes to the broadcast schedule the ACR Ingest Module can be notified of these changes immediately. The broadcast schedule could also contain the version number of the TPT for each segment and the ACR Ingest Module could get notification in real time of any unscheduled changes in a TPT version so that it can insert version v terms into Triggers when needed. The Ingest Module could also be configured to insert spread s terms into Triggers at suitable times such as during a specified interval at the beginning of each segment when many receivers are likely to be requesting new TPTs at the same time .

2 If there are any dynamic activations links can be set up from sources of dynamic activations to the ACR Ingest Module.

4 The ACR Ingest Module can extract signatures from the frames in the case of a fingerprint ACR system or insert codes into the frames in the case of a watermark ACR system for all frames contained in segments that have an interactive service associated with them. The ACR Ingest Module can determine whether a frame is in such a segment by using a GPS clock and the start times and end times of segments in the broadcast schedule. For each such frame the ACR Ingest Module can insert a record in the Database that can include a Trigger and the signature or code associated with the frame. The rules for what Trigger gets inserted are described at the end of this list of actions in the process.

6 MVPD can route the Broadcast Stream to the STB at a subscriber s location typically stripping out all of the interactive content first .

8 When the receiver is first turned on it can send its location to an ACR Configuration Server. The URL of the ACR Configuration Server can be built into the receiver. 

10 The ACR Client in the receiver can start extracting fingerprint signatures or watermark codes and sending them to the ACR Server.

12 If the signature or code does not match any signature or code in the Database then the ACR Server can get back a no match indicator. If the signature or code does match a signature or code in the Database then the ACR Server can get back the record for the frame that has the matching signature or code. In the latter case the record in the Database can contain a Time Base Trigger and or it can contain one or more Activation Triggers depending on what was inserted into the record for the frame by the ACR Ingest Module.

13 If the ACR Server gets back a no match indicator from the Database it can return a NULL response to the ACR Client. Otherwise the ACR Server can return to the ACR Client the Trigger or Triggers it obtained.

The following rules can be used to determine what Trigger or Triggers the ACR Ingest Module inserts into each frame record in the Database 

It can be assumed that there is some upper bound L on the length of the request intervals used by individual ACR clients in receivers. It is not important whether the ACR clients know what this bound is as long as they operate within it in practice. Let L be the length of time it takes a typical ACR client to compute the signature or extract the watermark associated with a frame counting from the time the frame arrives at the receiver. Let L be the typical round trip time for a message to go from an ACR client to an ACR server and back. Let M L L L. A slightly larger value of M could also be used the advantage of a slightly larger value is that receivers get a little extra time to react to Activation Triggers the disadvantage is that receivers are a little more likely to get multiple Activation Triggers for the same Event activation which is not much of a problem since they will be able to detect that they are duplicates as explained below and only apply the activation once. 

The ACR Ingest Module can insert only a Time Base Trigger in the record associated with a frame unless at least one of the following three conditions holds 

 a There is an Activation element in the AMT such that the media time of the frame is in the time interval beginning at time span M before the startTime of the Activation element and ending at the endTime of the Activation element. If an Activation has no endTime the endTime is considered equal to the startTime. 

 b A dynamic Activation Trigger was received by the Ingest Module before the time interval of time span M immediately preceding the activation time of the Trigger t and the frame lies within that interval.

 c A dynamic Activation Trigger was received by the Ingest Module later than the beginning of the interval of time span M immediately preceding the activation time of the Trigger and the media time of the frame is in the interval of time span L immediately following the receipt of the Trigger.

If any of the conditions a b or c holds then an Activation Trigger can be included in the record with an e term to identify the Event to be activated and a t term to indicate the startTime of the Activation element in the AMT for condition a or the event time of the dynamic Trigger for condition b . The Trigger can also contain a version v term.

The reason for continuing to associate Activation Triggers with frames throughout the interval from the startTime to the endTime in case a of course is to accommodate receivers that join the channel partway through the interval.

Note that this approach requires no extra intelligence on the part of the ACR Server. It simply returns to the ACR Client the information it finds in the Database. All the intelligence can reside in the ACR Ingest Module. Moreover the computations the ACR Ingest Module needs to do can be very simple.

With this scheme it is possible that a receiver can get more than one Activation Trigger associated with different frames for the same event activation. However a receiver can easily see from the t values that they all have the same activation time so the receiver can determine that they are duplicates and activate the event only once.

In two of the situations above the t term in the Activation Trigger can have an event time earlier than the media time of the frame with which it is associated. In situation a if the endTime of the Activation element is significantly later than the startTime then a receiver can typically get multiple Activation Triggers throughout the interval between the startTime and the endTime and they can all have the startTime as activation times. In situation c the Activation Triggers for the activation can get inserted into frame records so late that the Activation Trigger a receiver gets can come in response to a request with a signature for a frame that has media time after the activation time. When a receiver gets an Activation Trigger with an event time earlier than the media time of the frame with which it is associated it can be expected to activate the event immediately unless it recognizes it as a duplicate of an Activation Trigger it has already seen and used to activate the event.

The purpose of using event time values in the past rather than do it now Triggers for the situation when the frame media time is later than the event activation time is because a receiver can get more than one of these after the fact Activation Triggers. The t values allow the receiver to determine that they all have the same activation time and to activate the event only once.

Circled four vertical arrows may denote an example in which a typical receiver sends a request. In this example the receiver would get two Activation Triggers for the same event activation but they would have the same event activation times so the receiver would recognize them as duplicates and only apply the first one. Because the interval between receiver requests is less than L the receiver is guaranteed to make at least one request with a signature for a frame in the L interval shown in the diagram. This gives it time to compute the signature send the request to the ACR server and get the Activation Trigger back in response all before the activation time. In this example the first Activation Trigger the receiver gets would be delivered well ahead of time the second Activation Trigger the receiver gets would barely arrive in time it is a duplicate .

Hereinafter Activation Triggers in Case b and Case a without EndTime will be described. This is similar to the description of .

Circled four vertical arrows may denote an example in which a typical receiver sends a request. In this example the receiver would get two Activation Triggers for the same event activation but the activation times computed by adding the value to the receiver s local time for frame f or adding the value to the receiver s local time of frame f both give the same result so the receiver would recognize them as duplicates and only apply the first one. Because the interval between receiver requests is less than L the receiver is guaranteed to make at least one request with a signature for a frame in the L interval shown in the diagram. This gives it time to compute the signature send the request to the ACR server and get the Activation Trigger in response all before the activation time. In this example the second Activation Trigger received by the receiver would arrive after the activation time.

The figure shows an event activation startTime and endTime above the time line with an interval of length M preceding the startTime. The arrows below the time line show the times of individual frames. Each frame preceding the beginning of the interval of length M or following the event activation endTime would have associated with it in the Database a Time Base Trigger. Each frame inside the interval of length M or between the startTime and endTime of the event activation would have an Activation Trigger associated with it in the Database in the form shown by the three examples at the bottom of the figure. The t term for each frame would indicate the event activation time relative to the media time line. denoted by circled f f and f .

Circled three vertical arrows may denote an example in which a typical receiver sends a request. In this case the receiver would get three Activation Triggers for the same event activation but the activation times would all be the same so the receiver would recognize them as duplicates and only apply the first one.

Of course the first two Activation Triggers shown in the diagram would not be seen at all by a receiver that joins the channel after the startTime and sends the signature of frame f with its first request.

Hereinafter Activation Triggers in Case a with EndTime will be described. This is similar to the description of .

The figure shows an event activation startTime and endTime above the time line with an interval of length M preceding the startTime. The arrows below the time line show the times of individual frames. Each frame preceding the beginning of the interval of length M or following the event activation endTime would have associated with it in the Database a Trigger with no or terms. Each frame inside the interval of length M would have an Activation Trigger in the Database in the form shown by the two examples at the bottom of the figure. The d term for each frame would indicate the length of time between that frame and the event activation time. denoted by circled vertical arrows .

The circled vertical arrows may be an example in which a typical receiver sends a request. In this case the receiver would get three Activation Triggers for the same event activation but the activation times computed by adding the value to the receiver s local time for frame f or adding the value to the receiver s local time of frame f or adding the negative value to the receiver s local time of frame f all give the same result so the receiver would recognize them as duplicates and only apply the first one.

Of course the first two Activation Triggers shown in the diagram would not be seen at all by a receiver that joins the channel after the startTime and sends the signature of frame f with its first request.

Hereinafter Activation Triggers for Case c will be described. This is similar to the description of .

Hereinafter an example of operation of a request response model will be described in order of request response.

The sequence diagram between ACR client and other servers in Request Response ACR Case may include an ACR request s an ACR response s an ACR request s an ACR response s a HTTP request s a HTTP response s a HTTP request s a HTTP response s an ACR request s an ACR response s an ACR request s and an ACR response s.

The ACR request s is a step of at a receiver transmitting a signature of a currently viewed program to a server. The server may be the above described ACR server. The signature may be a fingerprint signature or a watermarking code.

The ACR response s is a step of at the ACR server returning NULL if the signature is not recognized or if a related interactive service is not present. This may be equal to the case of returning the above described NULL response.

The ACR request s is a step of at the receiver transmitting a signature of a changed program to the ACR server after a channel or program has been changed.

The ACR response s is a step of at the ACR server returning a trigger e.g. xbc.com tpt504 including an address capable of acquiring an interactive service related to the program. In this case unlike the ACR response s the signature may be recognized and the related interactive service may be present. That is the trigger may be available. In this case the returned trigger may be a time base trigger without information about a media time.

The HTTP request s may be a step of at the receiver requesting a TPT from a TPT server e.g. http xbc.com tpt504 etc. using the address received in the ACR response s using the http protocol.

The HTTP response s is a step of at the TPT server transmitting a TPT expressed in XML according to the request of the receiver.

The HTTP request s is a step of at the receiver requesting an application such as TDO from a content server using the http protocol. The receiver may parse TDO related information included in the TPT. The TDO related information may be an address of the content server from which the TDO can be downloaded. The request may be sent using the address of the content server.

The HTTP response s is a step of at the content server transmitting the TDO according to the receiver.

The ACR request s is a step of at the receiver transmitting the signature of the frame of a currently viewed program to the ACR server.

The ACR response s is a step of at the ACR server returning a trigger e.g. xbc.com tpt504 including an address capable of acquiring an interactive service related to the program. In this case unlike the above described ACR response s the signature may be recognized and the related interactive service may be present. That is the trigger may be available.

The ACR request s is a step of at the receiver transmitting the signature of the frame of the currently viewed program to the ACR server.

The ACR response s is a step of at the ACR server transmitting the signature received from the receiver and an activation trigger related to the related interactive service. According to the activation trigger a specific event may be activated at a specific time.

In the request response model of the present invention a method of processing an interactive service at a receiver of one embodiment includes receiving uncompressed audio content or uncompressed video content s extracting an identifier s sending a request containing the identifier s and receiving a trigger for the content s .

Receiving uncompressed audio content or uncompressed video content s is a step of at the receiver receiving uncompressed audio content or uncompressed video content from an external decoding unit.

Here an external decoding unit may be the above described STB. The STB will be described in detail below.

Here the uncompressed audio content or uncompressed video content may be audio video content transmitted from the above described STB external decoding unit to the receiver.

The external decoding unit may decode decompress A V content received from the MVPD and transmit the decoded A V content to the receiver. The receiver may receive and display the uncompressed audio content or uncompressed video content from the external decoding unit to the viewer. The uncompressed audio content or uncompressed video content may be processed according to operation of the above described ACR ingest module. That is an ACR Ingest Module can compute signatures fingerprints of frames in the case of a fingerprinting ACR system or insert watermarks consisting of codes into frames in the case of a watermarking ACR system that is based on codes. Here the frames may relate to audio video content before being decoded decompressed by the STB. The ACR Ingest Module can store in the database the media time of each frame associated with a signature or code together with other metadata.

Extracting an identifier s is a step of at the receiver extracting an identifier from one frame of the received uncompressed audio content or uncompressed video content.

Here the identifier may identify the frame of the received content. This identifier may be fingerprint signatures or watermark codes among the above described concepts. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

Here extracting means extracting the identifier from one frame of the received uncompressed audio content or uncompressed video content and may correspond to the above described computing the signature extracting the watermark or generating the signature .

 extracting may be operation performed in the above described ACR client. This is only exemplary and the present invention is not limited thereto and a designer may design extracting performed in another module. The ACR client may be located in the receiver.

In extracting an identifier s an identifier corresponding to one frame is extracted. The extracted identifier may be sent to the ACR server etc. as described above. Similarly to the above described operation the ACR server may perform a process of matching the received identifier with the records stored in the database. Here the ACR server and the database may be the above described ACR server and database respectively. The records stored in the database may be stored by the ACR ingest module in advance.

In one embodiment of the present invention identifiers may be periodically extracted generated from the frames of the received content.

In one embodiment of the present invention a period for extracting the identifiers may be 5 seconds. This may be changed according to designer s intension.

In sending a request containing the identifier s a request including the extracted identifier is sent to the server.

The extracted identifier may be fingerprint signatures or watermark codes. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

Here the request may include the identifier. Here the receiver may periodically send the request to the server. One request may include one identifier. The length of the period may be changed according to designer s intention.

Here the server may be the above described ACR server. The server may receive the request and perform a matching process with the database. Here the ACR server and the database may be the above described ACR server and database respectively. The records stored in the database may be stored by the ACR ingest module in advance.

In receiving a trigger for the content s the trigger is received from the server depending on whether the request and identifier sent to the server matches the records stored in the database or depending on whether the trigger matching the records is present.

Here the trigger can indicate the current time of the contents and reference a particular interactive event in an application parameter table or signal that the event is to be executed now or at a specified future time.

Here the server may be the above described ACR server. The database may be the above described database. Here the identifier may be fingerprint signatures or watermark codes. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

The server may perform a matching process with the database using the received request identifier. The matching process may be performed between the ACR ingest module and the records stored in the database. If the identifier matches the identifier of the database the server may receive a record related thereto from the database. In this case the record may include a time base trigger or an activation trigger. The included trigger may be changed depending on which is previously inserted into the record by the ACR ingest module. When the server receives the record from the database the server may send the acquired trigger or triggers to the receiver.

In one embodiment of the present invention the trigger is a time base trigger when no event activation is scheduled to take place before sending a next request. Here the time base trigger is used to maintain a time of a segment. The time base trigger may follow the above described operation of the time base trigger.

In one embodiment of the present invention the trigger is an activation trigger when an activation is due to take place. Here the activation trigger sets an activation time for the event. Here the activation time is indicated by a timing value term in the activation trigger. The activation trigger may follow the above described operation of the activation trigger. The activation trigger is applied to the event of the application to cause activation at a specific time. Via activation of the event a viewer may receive an interactive service. In case of activation trigger delivery according to the embodiment of the present invention in the above described ACR environment that is only if the receiver has Internet connections and accesses the uncompressed audio and video via the broadcast stream the receiver may receive the interactive service.

In one embodiment of the present invention the activation trigger is applied once when the receiver receives more than one activation trigger for same event activation. As described above with respect to the same event activation the receiver may receive a plurality of activation triggers. In one embodiment of the present invention the identifiers may be periodically extracted and sent to the server. At this time as responses to the periodic requests a plurality of activation triggers may be received. As described above in this case since the activation triggers have the same t term the receiver may confirm that the activation triggers are duplicates and apply only one activation trigger.

In one embodiment of the present invention the activation trigger is applied as soon as the activation trigger arrives when the activation trigger is received after the activation time. This embodiment is equal to the above described dynamic activation case. If the activation is recognized late such that the server can not send an activation trigger to the receiver earlier than an activation time the server may wait for a next request of the receiver and then send the activation trigger as a response to the next request. In this case the activation trigger may indicate a past activation time. In this case the receiver may apply the activation trigger as soon as the activation trigger arrives.

In one embodiment of the present invention the method of processing the interactive service may further include immediately downloading a new application parameter table. The receiver immediately download the new application parameter table unless the receiver has already retrieved the new application parameter table using URL information delivered with the application parameter table when the trigger includes an application parameter table identifier which identifies the new application parameter table. As described above if a trigger having the new application parameter table identifier is received the receiver may download the new application parameter table e.g. a TPT to obtain new information for providing the interactive service of the related segment. In one embodiment of the present invention a new application parameter table may be requested and downloaded from an application parameter table server using an http protocol. In one embodiment of the present invention the application parameter table may be in an XML or binary format. Here the application parameter table identifier may be the above described locator part. Here URL information may be the above described URLList.

In one embodiment of the present invention the method of processing the interactive service may further include obtaining an application URL and downloading a new application. The receiver can obtain an application URL for a new application associated with the trigger from the application parameter table or the new application parameter table when the receiver does not have the new application. The receiver can download the new application using the application URL. The receiver may parse application e.g. TDO related information included in the application parameter table e.g. a TPT and request the application from the server. The request may use an http protocol. Here the server may be a content server. The server may transmit the application according to the receiver s request.

In one embodiment of the present invention the time can be a media time and the media time can be a parameter referencing a point in the playout of a content item.

In one embodiment of the present invention the application is a Declarative Object a Triggered Declarative Object a Non Real Time Declarative Object or an Unbound Declarative Object.

In one embodiment of the present invention a communication session may be closed except for when the request and the response are exchanged. The communications session is not kept open between request response instances.

In one embodiment of the present invention the server may not transmit a message earlier than the receiver. It might not be feasible for the server e.g. the ACR server to initiate messages to the client e.g. the receiver .

In one embodiment of the present invention the receiver may receive a NULL response which is not a trigger. If the identifier received by the server does not match the identifier of the database the server may receive a no match indicator from the database. If the server receives the no match indicator the server may return the NULL response to the receiver.

One embodiment of the present invention requires no extra intelligence on the server. The server may only send information retrieved from the database to the receiver e.g. the ACR client . The ACR ingest module may serve all intelligence of the operation of the present invention.

In the embodiment of the present invention the receiver may include an antenna rcvr a tuner rcvr a VSB or DVB demodulator rcvr an MPEG 2TS System Decoder rcvr a caption module rcvr a trigger module rcvr a web browser rcvr a network protocol stack rcvr a network interface rcvr a UI module rcvr an audio decoder rcvr a video decoder rcvr a speaker rcvr a display module rcvr a graphic processor rcvr a remote controller receiver rcvr and or a remote controller rcvr.

The antenna rcvr may receive a broadcast signal according to a broadcast stream. Here the antenna rcvr may be one generally used in the technical field.

The tuner rcvr may seek or tune to a channel of the receiver and may include a radio frequency amplifier a local oscillator a frequency conversion and input circuit a seeker etc. The tuner rcvr may be one generally used in the technical field.

The VSB or DVB demodulator rcvr may modulate a VSB signal or a DVB signal. The VSB or DVB demodulator rcvr may restore the modulated VSB or DVB e.g. OFDM modulated signal to an original signal. The demodulation process of the VSB or DVB demodulator rcvr may be one generally used in the technical field.

The MPEG 2TS System Decoder rcvr decodes the transport stream TS of the demodulated signal. The MPEG 2TS System Decoder rcvr may obtain and deliver a caption stream from the transport stream to the caption module rcvr. The MPEG 2TS System Decoder rcvr may send the decoded audio and video signal to the audio video decoder rcvr.

The caption module rcvr may receive the caption stream. The caption module rcvr may monitor service 6 or other services and determine whether service 6 or services for transmitting the trigger is selected and sent to the trigger module rcvr or whether caption text is processed and displayed on a screen. Trigger data may be delivered to the trigger module rcvr. Other caption services may be subjected to caption text processing and sent to the graphic processor rcvr.

The trigger module rcvr may parse trigger TPT and or AMT information and process the parsed data. The trigger module rcvr may access the network via the network protocol stack rcvr using the URI information value of the trigger. The URI information value may be the address of the HTTP server. The trigger module rcvr may analyze the TPT file content to obtain the TDO URL. In addition the trigger module rcvr may parse the AMT to process data. Other information may be obtained through parsing. After the AMT message has been received the TDO URL corresponding to the web browser is delivered according to a predetermined time and operation or the currently operating TDO may be stopped at a predetermined time. This corresponds to a TDO action and the trigger module rcvr may send a command to the web browser to operate. The operation of the trigger module rcvr related to the present invention will be described in detail below.

The web browser rcvr may receive the command from the trigger module rcvr a browser key code from the UI module rcvr and a browser key code from the remote controller receiver rcvr and communicate with the network protocol stack rcvr.

The network protocol stack rcvr may communicate with the trigger module rcvr and the web browser to access the server via the network interface rcvr.

The network interface rcvr performs common connection of several other apparatuses or connection of a network computer and an external network. The network interface may be connected to the server to download a TDO a TPT an AMT etc. Here operation of the network interface rcvr may be operation of the network interface rcvr one generally used in the technical field. Operation of the network interface rcvr related to the present invention will be described in detail below.

The UI module rcvr may receive information input by a viewer using the remote controller rcvr through the remote controller receiver rcvr. If the received information is related to a service using the network the browser key code may be delivered to the web browser. If the received information is related to currently displayed video the signal may be delivered to the display module rcvr via the graphic processor rcvr.

The audio decoder rcvr may decode the audio signal received from the MPEG 2TS System Decoder rcvr. Thereafter the decoded audio signal may be sent to the speaker and output to the viewer. Here the audio decoder rcvr may be one generally used in the technical field.

The video decoder rcvr may decode the video signal received from the MPEG 2TS System Decoder rcvr. Thereafter the decoded video signal may be sent to the display module rcvr to be output to the viewer. Here the video decoder rcvr may be one generally used in the technical field.

The speakers rcvr may output the audio signal to the viewer. The speaker may be one generally used in the technical field.

The display module rcvr may output the video signal to the viewer. The display module rcvr may be one generally used in the technical field. Operation of the display module rcvr related to the present invention will be described in detail below.

The graphic processor rcvr may perform graphic processing with respect to the caption text received from the caption module rcvr and the viewer input information received from the UI module rcvr. The processed information may be delivered to the display module rcvr. The graphic processor rcvr may be one generally used in the technical field.

The remote controller receiver rcvr may receive information from the remote controller rcvr. At this time the key code may be delivered to the UI module rcvr and the browser key code may be delivered to the web browser.

The remote controller rcvr delivers the signal input by the viewer to the remote controller receiver rcvr. The remote controller rcvr may receive viewer input for changing a virtual channel. In addition the remote controller may receive information selected by the viewer with respect to the application. The remote controller rcvr may deliver the received information to the remote controller receiver rcvr. At this time the information may be remotely delivered using infrared IR light at a distance out of a predetermined range.

In the embodiment of the present invention shown in the receiver may include an antenna rcvr a tuner rcvr a Set Top Box rcvr a VSB or DVB demodulator rcvr a HDMI RCVR a MPEG 2 TS system decoder rcvr a caption module rcvr a trigger module rcvr a web browser rcvr a network protocol stack rcvr a network interface rcvr a UI module rcvr an ACR module rcvr an audio decoder rcvr a video decoder rcvr a speaker rcvr a display module rcvr a graphic processor rcvr a remote controller receiver rcvr and a remote controller rcvr.

In this case since video and audio of a broadcast stream is raw data a trigger included in a caption stream may not be received. Details of the present invention will be described below.

Here the modules excluding the Set Top Box rcvr the HDMI rcvr and the ACR module rcvr are similar to the modules described in the embodiment of in terms of the role.

The Set Top Box rcvr may restore a compressed signal received from the video server through a digital network to an original video and audio signal. The TV may be an Internet user interface.

The HDMI rcvr may be a high definition multimedia interface which is a non compression digital video audio interface standard. The HDMI rcvr may provide an interface between the Set Top Box rcvr and an AV apparatus that is the audio decoder rcvr and the video decoder rcvr.

The ACR module rcvr may automatically recognize broadcast content from the audio decoder rcvr and the video decoder rcvr. Based on the currently recognized content a query may be sent to the ACR server via the trigger module rcvr and the network interface rcvr to receive the TPT AMT for the trigger.

In the request response model according to the present invention an embodiment of an apparatus for processing an interactive service may include a receiving module an identifier extracting module and a network interface .

The receiving module may receive uncompressed audio content or uncompressed video content from an external decoding unit.

Here the uncompressed audio content or uncompressed video content may be audio video content sent from the above described STB external decoding unit to the receiver.

The receiving module may be another module which is not shown in or . This may be changed according to designer s intention.

The external decoding unit may decode decompress the A V content received from the MVPD and send the decoded A V content to the receiving module . The uncompressed audio content or uncompressed video content may be processed by the above described ACR ingest module. That is an ACR Ingest Module can compute signatures fingerprints of frames in the case of a fingerprinting ACR system or insert watermarks consisting of codes into frames in the case of a watermarking ACR system that is based on codes. Here the frames may relate to the audio video content before being decoded decompressed by the STB. The ACR Ingest Module can store in the database the media time of each frame associated with a signature or code together with other metadata.

The identifier extracting module extracts the identifier from one frame of uncompressed audio content or uncompressed video content received by the receiving module .

Here the identifier may identify the frame of the received content. This identifier may be fingerprint signatures or watermark codes. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

Here extracting means that the identifier is extracted from one frame of the received uncompressed audio content or uncompressed video content and may correspond to the above described computing the signature extracting the watermark or generating the signature .

The identifier extracting module extracts an identifier corresponding to one frame. The extracted identifier may be sent to the ACR server as described above. Similarly to the above described operation the ACR server may match the received identifier with the records of the database. Here the ACR server and the database may be the above described ACR server and database respectively. The records stored in the database may be stored by the ACR Ingest Module in advance.

Here the identifier extracting module may correspond to the ACR module of . The identifier extracting module may be another module which is not shown in or . This may be changed according to designer s intention.

In one embodiment of the present invention identifiers may be periodically extracted generated from the frames of the received content.

In one embodiment of the present invention a period for extracting the identifiers may be 5 seconds. This may be changed according to designer s intension.

The network interface may send a request including the extracted identifier to the server and receive a trigger related to content from the server. Here the trigger may be received based on the request.

Here the network interface may correspond to the network interface of . Alternatively the network interface may be another module which is not shown in or . This may be changed according to designer s intention.

Here the extracted identifier may be fingerprint signatures or watermark codes among the above described concepts. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

Here the request may include the identifier. Here the network interface may periodically send the request to the server. One request may include one identifier. The length of the period may be changed according to designer s intention.

Here the server may be the above described ACR server. The server may receive the request and perform a matching process with the database. Here the ACR server and the database may be the above described ACR server and database respectively. The records stored in the database may be stored by the ACR ingest module in advance.

Here the trigger can indicate the current time of the contents and reference a particular interactive event in an application parameter table or signal that the event is to be executed now or at a specified future time.

Here the server may be the above described ACR server. The database may be the above described database. Here the identifier may be fingerprint signatures or watermark codes. The present embodiment is not limited to any one of the fingerprinting or watermarking method.

The server may perform a matching process with the database using the received request identifier. The matching process may be performed between the ACR ingest module and the records stored in the database. If the identifier matches the identifier of the database the server may receive a record related thereto from the database. In this case the record may include a time base trigger or an activation trigger. The included trigger may be changed depending on which is previously inserted into the record by the ACR ingest module. When the server receives the record from the database the server may send the acquired trigger or triggers to the network interface .

In one embodiment of the present invention the trigger is a time base trigger when no event activation is scheduled to take place before sending a next request. Here the time base trigger is used to maintain a time of a segment. The time base trigger may follow the above described operation of the time base trigger.

In one embodiment of the present invention the trigger is an activation trigger when an activation is due to take place. Here the activation trigger sets an activation time for the event. Here the activation time is indicated by an timing value term in the activation trigger. The activation trigger may follow the above described operation of the activation trigger. The activation trigger is applied to the event of the application to cause activation at a specific time. Via activation of the event a viewer may receive an interactive service. In case of activation trigger delivery according to the embodiment of the present invention in the above described ACR environment that is only if the receiver has Internet connections and access the uncompressed audio and video via the broadcast stream the receiver may receive the interactive service.

In one embodiment of the present invention the activation trigger is applied once when the receiver receives more than one activation trigger for same event activation. As described above with respect to the same event activation the apparatus may receive a plurality of activation triggers. In one embodiment of the present invention the identifier may be periodically extracted and sent to the server. At this time as responses to the periodic requests a plurality of activation triggers may be received. As described above in this case since the activation triggers have the same t term the apparatus may confirm that the activation triggers are duplicates and apply only one activation trigger.

In one embodiment of the present invention the activation trigger is applied as soon as the activation trigger arrives when the activation trigger is received after the activation time. This embodiment is equal to the above described dynamic activation case. If the activation is recognized late such that the server can not send an activation trigger to the apparatus earlier than an activation time the server may wait for a next request of the apparatus and then send the activation trigger as a response to the next request. In this case the activation trigger may indicate a past activation time. In this case the apparatus may apply the activation trigger as soon as the activation trigger arrives.

In one embodiment of the present invention the network interface is further configured to download a new application parameter table immediately unless the apparatus has already retrieved the new application parameter table using URL information delivered with the application parameter table when the trigger includes an application parameter table identifier which identifies the new application parameter table. As described above if a trigger having the new application parameter table identifier is received the apparatus may download the new application parameter table e.g. a TPT to obtain new information for providing the interactive service of the related segment. In one embodiment of the present invention a new application parameter table may be requested and downloaded from an application parameter table server using an http protocol. In one embodiment of the present invention the application parameter table may be in an XML or binary format. Here the application parameter table identifier may be the above described locator part. Here URL information may be the above described URLList.

In one embodiment of the present invention the apparatus further comprises a trigger module which is configured to obtain an application URL for a new application associated with the trigger from the application parameter table or the new application parameter table when the apparatus does not have the new application wherein the network interface further configured to download the new application using the application URL.

Here the apparatus may parse application e.g. TDO related information included in the application parameter table e.g. a TPT and request the application from the server. The request may use an http protocol. Here the server may be a content server. The server may transmit the application according to the apparatus s request.

In one embodiment of the present invention the time can be a media time and the media time can be a parameter referencing a point in the playout of a content item.

In one embodiment of the present invention the application is a Declarative Object a Triggered Declarative Object a Non Real Time Declarative Object or an Unbound Declarative Object.

In one embodiment of the present invention a communication session may be closed except for when the request and the response are exchanged. The communications session is not kept open between request response instances.

In one embodiment of the present invention the server may not transmit a message earlier than the receiver. It might not be feasible for the server e.g. the ACR server to initiate messages to the client e.g. the apparatus .

In one embodiment of the present invention the network interface may receive a NULL response which is not a trigger. If the identifier received by the server does not match the identifier of the database the server may receive a no match indicator from the database. If the server receives the no match indicator the server may return the NULL response to the network interface .

One embodiment of the present invention requires no extra intelligence on the server. The server may only send information of the database to the network interface . The ACR ingest module may serve all intelligence of the operation of the present invention.

According to the present invention it is possible to provide supplementary information related to broadcast content using an existing broadcast system.

According to the present invention it is possible to accurately confirm when supplementary information related to broadcast content is displayed and to provide the supplementary information to a user at an appropriately time.

According to the present invention it is possible to provide supplementary information related to broadcast content to a receiver which has an Internet connection and can access uncompressed audio and video via a broadcast stream.

Although the description of the present invention is explained with reference to each of the accompanying drawings for clarity it is possible to design new embodiment s by merging the embodiments shown in the accompanying drawings with each other. In addition if a recording medium readable by a computer in which programs for executing the embodiments mentioned in the foregoing description are recorded is designed in necessity of those skilled in the art it may belong to the scope of the appended claims and their equivalents.

An apparatus and method according to the present invention may be non limited by the configurations and methods of the embodiments mentioned in the foregoing description. And the embodiments mentioned in the foregoing description can be configured in a manner of being selectively combined with one another entirely or in part to enable various modifications.

In addition a method for processing an interactive service related to a broadcast program according to the present invention can be implemented with processor readable codes in a processor readable recording medium provided to a network device. The processor readable medium may include all kinds of recording devices capable of storing data readable by a processor. The processor readable medium may include one of ROM RAM CD ROM magnetic tapes floppy discs optical data storage devices and the like for example and also include such a carrier wave type implementation as a transmission via Internet. Furthermore as the processor readable recording medium is distributed to a computer system connected via network processor readable codes can be saved and executed according to a distributive system.

It will be appreciated by those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the inventions. Thus it is intended that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

Both apparatus and method inventions are mentioned in this specification and descriptions of both of the apparatus and method inventions may be complementarily applicable to each other.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.


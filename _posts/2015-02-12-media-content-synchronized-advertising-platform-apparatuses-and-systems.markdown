---

title: Media content synchronized advertising platform apparatuses and systems
abstract: The MEDIA CONTENT SYNCHRONIZED ADVERTISING PLATFORM APPARATUSES AND SYSTEMS (“AD-SURVEY”) transforms user advertisement exposure data via AD-SURVEY components, into ad effects data including user responses to survey questions. A system is disclosed, comprising: a memory; a processor disposed in communication with said memory, and configured to issue a plurality of processing instructions stored in the memory, wherein the processor issues instructions for obtaining TV program schedule listing data including a plurality of ad tags at a server: providing the obtained TV program schedule listing data to a user mobile device, receiving a user media program selection message from the user mobile device; retrieving an ad tag associated with the user selected media program from the TV program schedule listing data; extracting key terms from the ad tags based by parsing ad contents; querying a survey question list based on the extracted key terms; generating and sending a survey question from the query to the user mobile device; and obtaining a user reaction to the survey question.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432713&OS=09432713&RS=09432713
owner: Symphony Advanced Media
number: 09432713
owner_city: San Francisco
owner_country: US
publication_date: 20150212
---
This application is a continuation of and claims priority under 35 U.S.C. 120 from U.S. application Ser. No. 13 341 076 titled Media Content Based Advertising Survey Platform Apparatuses And Systems filed on Dec. 30 2011 which in turn claims priority under 35 U.S.C. 119 for U.S. provisional patent application Ser. No. 61 504 913 filed Jul. 6 2011 entitled Mobile Remote Media Control Platform Apparatuses methods and systems. 

The instant application is related to PCT international application no. PCT IL2010 000918 publication no. WO 2011 055365 filed Nov. 7 2010 entitled System And Method For Mobile Computing Transmission On A Network Of Data Associated With A Television Display. 

The instant application is further related to U.S. application Ser. No. 13 341 400 filed Dec. 30 2011 entitled Mobile Remote Media Control Platform Methods U.S. application Ser. No. 13 341 857 filed Dec. 30 2011 entitled Mobile Remote Media Control Platform Apparatuses and Methods U.S. application Ser. No. 13 340 933 filed Dec. 30 2011 entitled Audience Atmospherics Monitoring Platform Methods U.S. application Ser. No. 13 340 953 filed Dec. 30 2011 entitled Audience Atmospherics Monitoring Platform Apparatuses and Systems U.S. application Ser. No. 13 341 036 filed Dec. 30 2011 entitled Media Content Based Advertising Survey Platform Methods U.S. application Ser. No. 13 341 076 filed Dec. 30 2011 entitled Media Content Based Advertising Survey Platform Apparatuses and a Systems U.S. application Ser. No. 13 341 096 filed Dec. 30 2011 entitled Media Content Synchronized Advertising Platform Methods U.S. application Ser. No. 13 341 118 filed Dec. 30 2011 entitled Media Content Synchronized Advertising Platform Apparatuses and Systems U.S. application Ser. No. 13 341 137 filed Dec. 30 2011 entitled Social Content Monitoring Platform Methods U.S. application Ser. No. 13 341 165 filed Dec. 30 2011 entitled Social Content Monitoring Platform Apparatuses and Systems U.S. application Ser. No. 13 341 183 filed Dec. 30 2011 entitled User Impression Media Analytics Platform Methods U.S. application Ser. No. 13 341 199 filed Dec. 30 2011 entitled User Impression Media Analytics Platform Apparatuses and Systems U.S. application Ser. No. 13 341 217 filed Dec. 30 2011 entitled Mobile Content Tracking Platform Methods and U.S. application Ser. No. 13 341 254 filed Dec. 30 2011 entitled Mobile Content Tracking Platform Apparatuses and Systems. 

The entire contents of the aforementioned applications are herein expressly incorporated by reference.

This application for letters patent disclosure document describes inventive aspects directed at various novel innovations hereinafter disclosure and contains material that is subject to copyright mask work and or other intellectual property protection. The respective owners of such intellectual property have no objection to the facsimile reproduction of the disclosure by anyone as it appears in published Patent Office file records but otherwise reserve all rights.

The present innovations are directed generally to media control and more particularly to MEDIA CONTENT SYNCHRONIZED ADVERTISING PLATFORM APPARATUSES AND SYSTEMS.

A home TV user may view TV programs from a plurality of channels. The user may operate a handheld remote TV controller sold with the TV set to select TV channels. For example the user may push buttons on the remote controller to switch channels turn up down audio volume power on off the TV. Merchants advertise their products to attract consumers. Thus the TV audiences may interact with the TV and select a desired channel without physically touching it via operating the remote TV controller.

The leading number of each reference number within the drawings indicates the figure in which that reference number is introduced and or detailed. As such a detailed discussion of reference number would be found and or introduced in . Reference number is introduced in etc.

The MEDIA CONTENT SYNCHRONIZED ADVERTISING PLATFORM APPARATUSES AND SYSTEMS provides a client server interactive platform whereby a user may operate a general purpose personal mobile device e.g. a smart phone etc. to receive a list of TV programs schedules and submit a selection of TV channel via the personal mobile device. In one implementation the user may operate the personal mobile device as a TV remote controller. In one implementation the AD SURVEY may receive the user s selection of a channel and determine what media contents the user has elected to watch. In one implementation the user s channel selection and viewing status may be populated to a social media platform and the AD SURVEY may obtain user response with regard to a TV program from the social media to perform analytics for TV program feedback review.

For example in one implementation a user may plug a AD SURVEY accessory e.g. in into his mobile device such as a smartphone e.g. an Apple iPhone BlackBerry Google Android Palm HTC Evo Samsung Galaxy etc. laptop personal digital assistant PDA tablet computer e.g. Apple iTouch iPad etc. and or the like to facilitate communication between the mobile device and a home TV set. In an alternative implementations the AD SURVEY accessory may be a standalone table top unit which may not need to be attached to user mobile device. For example the table top unit communicated with a desktop computer a laptop computer a cell phone or mobile device and or the like via wired or wireless connection e.g. Bluetooth WiFi etc. . In further implementations the table top unit may monitor audience activities as further illustrated in . Further implementations of the table top unit are illustrated in . Within implementations a AD SURVEY server may obtain real time TV program listing including the TV program schedule advertisement schedule and or the like from a TV network. The user ma then obtain the list of TV program schedules from the AD SURVEY e.g. as shown at in . The user may then submit a channel selection e.g. tap on the touch screen of the mobile device as shown at in . In one implementation upon receiving the user channel selection the AD SURVEY server may retrieve data record from a media content database and check program table to determine what s the TV program on air. For example if the user selects the channel CBS the AD SURVEY may ascertain CBS has The Big Bang Theory on air based on the timestamp when the user submits the selection. In one implementation the AD SURVEY may further retrieve a program table to obtain information with regard to the advertisement streamed during the intervals of the TV play The Big Bang Theory and or the product placement advertisements tagged in the TV play The Big Bang Theory on CBS. 

In another implementation the AD SURVEY may parse commercial ad information retrieved at and generate prompt questions surveys and or the like . For example if the AD SURVEY determines the user is supposed to watch a series of Audi commercial during the show The Big Bang Theory the AD SURVEY may prompt a survey including questions with regard to automobile purchasing. In another implementation the AD SURVEY may keep a record of advertisements that has played on channels the user has recently selected e.g. for a period of past 2 weeks etc. and generate prompt questions based on such advertisements. In one implementation the user may submit responses to such questions.

In a further implementation when a user is provided a question with regard to an embedded advertisement in the TV show e.g. are you interested in the red bag the character is carrying etc. the user may submit a request to learn more and or purchase the product. In that case the AD SURVEY may provide a merchant URL to the user and or redirect the user to the merchant site.

In one implementation AD SURVEY may monitor whether the user is actually attending and watching the selected TV channel. For example the user s mobile device may capture aggregate and packetize atmospherics data e.g. taking photos of the user recoding audio clips obtaining GPS information etc. and submit to the AD SURVEY which may in turn decode the atmospherics data to analyze ad effect and audience perception as further illustrated in .

Within implementations the AD SURVEY platform may interact with user mobile devices e.g. PDAs Smartphones etc. for targeted mobile advertisement delivery . For example in one implementation AD SURVEY platform may obtain a TV viewing status information from a user s mobile device and determine the TV program content the user is has been watching based on TV schedules as further discussed in . When AD SURVEY determines the user selected channel contains a TV ad of Geico AD SURVEY may deliver promotions rewards coupons questionnaires etc. related to Geico as a targeted ad to the user mobile device.

In one implementation AD SURVEY platform may obtain data related to user interactive activities with regard to mobile ads TV viewing Internet including online browsing purchasing etc. social media and or the like to analyze ad effects TV rating so that to determine delivery and performance of an advertisement campaign. Within implementations the ad campaign planning ad performance and ad delivery may be separately executed by the AD SURVEY platform for each media type e.g. TV print Internet social media etc.

In one implementation upon instantiating the downloaded AD SURVEY client component the user may receive a schedule listing of TV programs and may select a channel that the user is interested. For example the user may tap on the listed item to select CH2 CBS The Big Bang Theory . In one implementation the AD SURVEY plug in accessory may receive the indication of user channel selection and transmit such indication to the home TV set and the TV may switch to the channel CBS accordingly.

In a further implementation the user s selection of channel CBS may be transmitted to a AD SURVEY which may in turn automatically populate a message on social media e.g. a Facebook status update showing the user is watching The Big Bang Theory on CBS . In an alternative implementation the user may elect to manually enter and populate the social media feeds via the AD SURVEY client component instantiated on his personal mobile device.

For another example the social message e.g. a Tweet message may contextually tag the text on key terms to indicate what the user is watching e.g. the Tweet hashtags The Big Bang Theory CBS etc. In one implementation the hashtags may link to profile information of a TV show including its scheduled airing time crew information description and or the like. In further implementations the Tweet hashtags may be employed for social content data taxonomy engine as further illustrated in .

As shown in one example in the personal mobile device may automatically snap a photo and or a video clip of the audience scene including the audience watching the TV program . For example the AD SURVEY may be configured to snap a photo or video clip periodically e.g. every 10 minutes etc. . The AD SURVEY may then packetize the obtained photo video clip as audience atmospherics data for audience attendance analysis.

In further implementations AD SURVEY may include various data into the atmospherics data packets. For example AD SURVEY may listen and record an audio clip of the audience scene. For another example AD SURVEY may prompt the user to indicate how many audience are present to watch the on going TV program. For another example AD SURVEY may monitor whether the user is engaging in other application activities on the personal mobile device e.g. email s Facebook browser activities gaming applications etc. For another example AD SURVEY may include GPS information of the personal mobile device into the atmospherics data.

In one implementation AD SURVEY may be configured to automatically create photo video audio captures. In another implementation AD SURVEY may prompt the user to manually enter desired information such as how many individuals are present to watch the TV program and or request the user position the built in camera of the mobile device to snap photos video clips. In one implementation AD SURVEY may provide promotion incentives for the user to cooperate with such requests e.g. lottery opportunities etc.

In one implementation AD SURVEY may analyze the obtained audience atmospherics data . For example as shown in AD SURVEY may identify the number of audience at an associated timestamp from an audience scene photo video via face recognition software e.g. Apple iPhoto face recognition etc.

In one implementation AD SURVEY may generate a media analytics report based on the obtained social media user comments to reflect audience reaction to the show The Big Bang Theory. For example in one implementation the report may comprise statistical data with regard to audience age demographics occupation etc. Further examples of media analytics report are discussed in .

In one embodiment the AD SURVEY may receive a list of real time TV program . For example in one implementation the TV program data may comprise information such as channel information media program information of each channel program schedule information and or the like. For example the TV network may provide a Secure Hypertext Transfer Protocol HTTP S PUT message including the TV schedule data in the form of data formatted according to the eXtensible Markup Language XML . Below is an example HTTP S PUT message including an XML formatted TV schedule for the AD SURVEY server 

The media program may further comprise information such as media air time media length advertisement tag timestamp ad name ad product information and or the like. The media program may further comprise a sub table comprising embedded advertisement tags e.g. see in .

In further implementations the TV schedule may comprise sub tables including information with regard to the media programs. For example an exemplary XML formatted TV program table takes a form similar to the following 

In one embodiment the user may operate a client mobile device which may receive a list of real time TV programs . In one embodiment upon reviewing the received channel schedule the user may submit a channel selection by tapping on a selected channel e.g. see in . In one implementation the user mobile device may be enabled with an infrared remote control component e.g. a plug in accessory in and may send the channel submission indication to a client TV e.g. a home TV set via an infrared communication channel which may result in a channel switch on TV. In another embodiment when the user selects the channel from his mobile device e.g. an Apple iPhone etc. the channel selection message may be transmitted to the AD SURVEY server in real time.

In another implementation the AD SURVEY server may provide the TV program schedule data to a TV set top box STB e.g. via a cable network wherein the STB may receive user TV event messages and forward such information to the AD SURVEY server . In another implementation the STB may directly communicate with a AD SURVEY infrared component e.g. in a table unit and or the like. In one implementation the TV event may comprise a variety of TV events such as but not limited to TV on off STB on off channel switch and or the like. In further implementations when the user has registered non live media facility e.g. DVD TiVo etc. with the AD SURVEY the TV event may comprise DVD player on off TiVo on off TiVo channel change and or the like. In one implementation to operate and exchange data with the STB the presentation layer on the user mobile device may adopt development tools such as but not limited to Android iOS app development tools and or the like. In one implementation the TV set up top box may similarly employ a presentation layer development tool compatible with that of the user mobile device and may additionally employ HTML5 and web 2.0 presentation layers.

In one implementation a TV channel selection event may be logged by the AD SURVEY server and stored as a real time data record in a AD SURVEY database . For example in one implementation the user device may provide a HTTPS POST message including the TV channel selection message in the form of data formatted according to the XML. Below is an example HTTP S POST message including an XML formatted user trigger for the AD SURVEY server 

In further implementation the user s mobile device may send event messages. Such event messages may include channel selection message user checkin checkout action e.g. user signing in out to a AD SURVEY mobile web based client portal etc. and or the like. In one implementation the events may be sent to the AD SURVEY server via Https Post web based API which may comprise a type identifier and a set of parameters of the event data e.g. channel selection user response etc. In one implementation AD SURVEY server may save such event data at CSV format. For example the following Tables I and II provide an exemplary data structure of an event message 

In one embodiment upon submitting a channel selection the user may populate social media feeds of his viewing status to the social media network wherein the user s friends may view his status knowing what the user is watching electing to like dislike and or comment on his status and or the like. For example in one implementation a AD SURVEY client app may comprise a social feature e.g. see in so that a user may input a social media message e.g. in . In another implementation the AD SURVEY may automatically generate a social message based on a pre populated message format e.g. a Tweet format with hashtags etc. send a message indicating the user s viewing status to the social media which may automatically populate a social media status update. In such cases the social media platform may request user authorization for AD SURVEY server to access e.g. download social data or send social data to social media etc. The AD SURVEY may obtain a user token for authorization to access the user s social media profile content and or the like. The user authorization may be further discussed in .

For example in one implementation the AD SURVEY may provide a HTTPS POST message including a social message in the form of data formatted according to the XML. Below is an example HTTP S POST message including an XML formatted user viewing status for the AD SURVEY server 

In the above example the AD SURVEY server may automatically populate a social message to the user s Facebook page showing a status update John Doe is watching The Big Bang Theory on CBS. 

In a further implementation the user may receive friends recommendations of TV programs from the social media e.g. see in . For example the user may view a scroll down list of friends recommendations from a user interface via the user s mobile device.

In further embodiments AD SURVEY may load data from the social media platform e.g. user profile information user comments activity data related to an advertisement a TV program and or the like. Further implementations and example data structures of the social media data are discussed in .

For another example in one implementation the user device may generate an atmospherics data package as a HTTPS POST message in the form of data formatted according to the XML. Below is an example HTTP S POST message including an XML formatted atmospherics data to provide to the AD SURVEY server 

The user device may perform ambient listening and generate atmospherics data package constantly intermittently and or periodically e.g. every hour etc. to listen in user s watching status e.g. whether the user is paying attention to the selected TV program. In the above example the generated atmospherics data package may comprise a variety of data segments such as a MyRecord.mp3 audio clip which may indicate whether the played audio matches a selected channel program whether the user is chatting with friends e.g. see at a MyPic.JPEG photo taken by an iPhone camera which may indicate whether the user is present with the TV set and or one or more individuals are present e.g. see at GPS information of the user mobile device which may indicate whether the user is present at his residential address where the home TV is located e.g. see at user mobile device application status information including an actively running gaming application e.g. Angry Bird which may indicate the user is playing the video game instead of paying attention to the TV program e.g. see at . In one implementation the atmospherics data and or analytics may be incorporated into a data record and stored in the database .

In another implementation the user mobile device may send a device application event indicating user device application status to the AD SURVEY server . For example the device application event may comprise an actively engaged application information on the device e.g. application ID application name application category push email heart beat pulse etc which may suggest audience activities while watching TV e.g. video gaming texting calling checking email browsing playing music editing photos and or the like. For example in one implementation the user device may generate a mobile application event as a HTTPS POST message in the form of data formatted according to the XML. Below is an example HTTP S POST message including an XML formatted device application status to provide to the AD SURVEY server 

In one implementation the device application status may comprise a list of application names that have been open and active for a minimum amount of time e.g. 10 seconds etc. . In another implementation the device application status may be periodically harvested to the AD SURVEY serer.

In one implementation the user may submit a session request to the AD SURVEY server via the mobile application e.g. as shown in Table 1 the session request may comprise a user ID and an event session ID to indicate the AD SURVEY application has stared. Upon receiving a user request the AD SURVEY server may determine whether the user has registered with AD SURVEY . For example in one implementation the user may be a new user to the AD SURVEY application service who may just download and install the mobile application but has not registered. If the user is not registered the user may be requested to submit registration information such as user name phone number email address residential address and or the like for registration . The AD SURVEY may also obtain a physical address a hardware ID of the user mobile device etc. for registration purposes.

In one implementation upon registration the AD SURVEY server may obtain and store a user application ID and or a session ID to start the AD SURVEY service session. In one implementation the AD SURVEY server may obtain a real time TV program listing e.g. from a TV network a TV broadcasting service etc. In one implementation the AD SURVEY server may obtain the TV schedule updates on a periodical basis e.g. daily etc. and store the TV schedule information at a TV schedule database. In one implementation the user may receive a list of TV programs via the AD SURVEY application e.g. see in .

In one implementation the user mobile device may send a user event message to the AD SURVEY server and the AD SURVEY server may monitor user event messages from the user device. As discussed in and will be further discussed in the received user event at may comprise a variety of events messages such as but not limited to user TV event e.g. in user device application event e.g. in atmospherics data e.g. in social content e.g. in response to ads surveys e.g. in and or the like. In one implementation upon receiving the message the AD SURVEY may determine a type of the message . In one implementation the user event message may comprise user channel submission event check in out messages and or the like e.g. see in . For another example the user event message may comprise atmospherics data as further illustrated in ad survey response as further illustrated in social data as further illustrated in non live TV consumption message as illustrated in . For example in one implementation the AD SURVEY may determine the message types based on the data structure e.g. a field value of a field message type as shown in Table 2 message type code in the header information of a received data packet and or the like.

Within implementations the AD SURVEY may determine whether each received TV event message indicates a stable TV channel program selection or a channel surfing. In one implementation the AD SURVEY retrieve a list of unprocessed TV message records e.g. grouped per user profile from the raw data store . For every two consecutively received messages the AD SURVEY may calculate the elapsed time in between and determine whether the elapse time is greater than a pre determined surfing threshold e.g. 5 seconds 10 seconds etc. . For example when the elapsed time is shorter than the surfing threshold indicating the user may be frequently switching channels to browse the program the AD SURVEY may not consider the channel selection message as effective TV viewing and may filter such message records from TV viewing analysis .

In another implementation when the elapsed time is greater than the surfing threshold suggesting the user may at least spend an amount of time staying on the selected channel the AD SURVEY may further determine whether the elapsed time is greater than a capping threshold . For example when the elapsed time is too long greater than the capping threshold e.g. 2 hours 3 hours etc. it may suggest a user may just let the TV on without watching. In such cases AD SURVEY may apply capping edit rules to compute a real watching time . For example if the elapsed time between a first TV channel switch and a second channel switch is 5 hours the AD SURVEY may not log 5 hours as the watching time for the first selected channel as the capping threshold is 2 hours. The AD SURVEY may in turn determine the watching time of the first selected channel as capped by a STB TV off event e.g. when a STB TV off event is received during the elapsed time the watching time may not exceed the timestamp of the STB TV off event TV program end time e.g. when the playing TV program on the first selected channel ends during the elapsed time the watching time is calculated as the time elapse between the first TV channel event and the TV program end time and or the like e.g. at . In further implementations the AD SURVEY may apply cutoff thresholds based on historical heuristics via statistical analysis . For example the AD SURVEY may determine the watching time based on individual habits e.g. a user has been observed to stay on the same channel for at most 1 hour etc. For another example the cut off threshold may be analyzed by channel e.g. 1 hour on CBS 2 hours on ABC family and or the like.

In one implementation when the elapsed time does not exceed a capping threshold at and or when the watching time has been re calculated based on capping rules at the AD SURVEY may retrieve TV program information on the user selected channel and generate a user channel selection log file . For example the log file may comprise fields such as user ID channel ID channel selection time user watching time channel program name channel program ID and or the like. Such generated log files may be fed to a user TV viewing data engine for audience analytics . For example the audience analytics database may be utilized to analyze TV viewing rates of a TV program product brand impression of advertised products during the user watching time and or the like. Exemplary audience analytics reports are discussed at .

the AD SURVEY server may retrieve TV program information to determine the TV program played on the user selected channel . For example the AD SURVEY may query on a TV program table e.g. obtained at at based on an instant timestamp and the user selected channel. The AD SURVEY may log the user channel selection with the timestamp in a database e.g. at in .

In one implementation AD SURVEY may generate TV viewing data for the retrieve TV program . In one implementation AD SURVEY may associate the user selection to the TV viewing rate of the retrieved TV program and may refine the TV viewing rate with atmospherics analytics at . For example in one implementation the AD SURVEY may monitor groups of audience s channel selection wherein the audience groups may be defined based on age geography and or the like. In one implementation the AD SURVEY may generate an audience summary via a dashboard e.g. see .

In another implementation the AD SURVEY may incorporate the received device application status e.g. for user activity analytics. For example the AD SURVEY may capture active application s running on the device from the received device application data and determine user activities when viewing e.g. emailing browsing Internet content texting video gaming and or the like. Such indicated user activity data may be incorporated into audience attendance estimation .

In one implementation the artifact may comprise a visual data file such as a video file e.g. wmv mp4 avi rm etc. an image file e.g. JPEG bmp tiff gif etc. and or the like. In one implementation the AD SURVEY may determine graphical content of the visual file. For example the AD SURVEY may perform image analysis to determine whether the photo image and or video frames comprise a scene of audience and or a TV screen. In one implementation a mobile application at the user mobile device e.g. iPhone etc. may perform face recognition at a photo taken at an iPhone and integrate such data in the atmospherics data package e.g. an iPhoto including two faces etc. In another implementation the AD SURVEY server may perform facial recognition to determine audience presence . In other implementations the AD SURVEY server may perform image analysis to determine user activities in the photo image e.g. reading a book doing housework and or the like. In further implementations a AD SURVEY panelist may review the photo image and determine audience status.

In another implementation the AD SURVEY may determine whether a TV screen image matches the TV program associated with the user channel selection e.g. the user may switch to watch recorded program e.g. TiVo DVD player etc. instead of live TV program on the channel and in such cases the AD SURVEY may not receive an indication of such change. For example in one implementation AD SURVEY may perform image analysis to determine whether the received image photo and or a video frame grab contains a TV screen shot e.g. by detecting edges of a rectangular shaped object on the image etc. For another example the AD SURVEY may store a plurality of sample screen shots from the TV program played at the user submitted channel and may compare the received image photo with each of the stored sample screen shots. In further implementations a AD SURVEY panelist may assist in reviewing and determining whether the user TV screen matches the played TV program. In one implementation if the AD SURVEY determines the user is absent from a TV set or engaging in other activities from the graphic analysis AD SURVEY may generate negative heuristics with regard to TV viewing data of the TV program on air.

In another implementation if the received atmospherics data comprises an audio artifact e.g. with a file extension of wav mp3 ape m4a etc. the AD SURVEY may perform audio analysis to determine a content of the audio . For example the AD SURVEY may analyze the frequency range of the audio content to determine the sound source e.g. whether it is human voice ambient noise media broadcasting and or the like.

In one implementation if the audio content comprises human voice e.g. within the frequency range 60 7000 Hz the AD SURVEY may determine whether the human voice is from the audience or broadcasting media. For example the AD SURVEY may perform voice recognition to determine whether the human voice matches with any of the characters in the TV program on air on the user submitted channel e.g. at .. If not the AD SURVEY may determine such human voices may indicate audience presence e.g. whether more than one user is present with the TV set.

In further implementations if the audio file comprises human voice the AD SURVEY may extract verbal content from the audio file to determine whether an audience conversation or a human conversation from media playing is related to the TV program on air on the user submitted channel .. For example the AD SURVEY may adopt speech recognition software e.g. Nuance IBM WebSphere Voice etc. to extract key terms from the conversation and compare whether the key terms are related to key words stored with the TV program in the database. For example if AD SURVEY extracts key terms quantum mechanics physics big bang etc. from the human conversation in the received atmospherics audio artifact and the user submitted channel CBS is playing The Big Bang Theory AD SURVEY may determine the audience is watching the show on air. In such cases the AD SURVEY may not need to distinguish whether the human conversation in the audio file is from the audience or TV but focus on mining the content of the conversation.

In another implementation if the AD SURVEY determines the audio artifact comprises ambient noise AD SURVEY may determine an environment of the audience . For example if the background is overly noisy the user may not be watching the TV program.

In another implementation if the AD SURVEY determines the audio artifact comprises media sound e.g. music etc. the AD SURVEY may determine whether the audio media content matches the TV program on air on the user submitted channel via a media recognition software e.g. a Shazam alike music recognition kit etc. . For example if the user selected channel CBS has The Big Bang Theory scheduled at the moment but the AD SURVEY determines a Lady Gaga song in the received audio atmospherics this may indicate the user is not watching the TV program. In one implementation if the AD SURVEY determines the user is distracted from the TV program based on the audio content AD SURVEY may generate negative heuristics with regard to TV viewing data of the TV program on air.

In an alternative implementation the AD SURVEY client component which may be instantiated on a user mobile device e.g. a downloadable application such as but mot limited to an iphone application an Android application etc. and or a table top standalone unit may obtain atmospherics data to determine the program the user us watching without user indication of the channel. For example the AD SURVEY component may obtain audio recording video recording signatures image captures and or the like of the audience watching environment and submit the obtained data to AD SURVEY server. In one implementation the AD SURVEY server may analyze the obtained data to determine what the audience is watching in a similar manner as illustrated at in but without the user s channel selection indication.

In one implementation the AD SURVEY may perform an audio video recognition procedure to identify a TV program e.g. via digital signatures embedded in the program and or the like. In another implementation the AD SURVEY may extract key terms from the audio video captures and form a query on a database of TV programs to find a match. For example in one implementation the AD SURVEY may extract textual terms from the obtained audio media program excerpts such as big bang quantum physics Sheldon etc. and may form a query in a database of TV programs which may return a result indicating the obtained audio media program excerpt may be related to the TV show Big Bang Theory. 

In an alternative implementation rather than uploading sampling and or the entirety of the captured audio video median content the AD SURVEY may analyze the recorded audio video content to generate a unique signature and or a unique hash which may be used for further matching. For example the unique signature hash may take a form similar to a sequence of 0 1 representation of a sampling of the recorded media content. In one implementation the signature hash generation may be performed at a user device e.g. the user s mobile phone the table top unit etc. which may upload the generated signature hash sequence to the AD SURVEY server. In another implementation the user device may upload media content sampling clips or the captured entirety to the AD SURVEY server which may then perform the signature generation. Within implementations software tools components such as but not limited to i brainz and or the like may be adopted to generate audio signature hash.

In further implementations such listen in activities may be performed on a standalone table unit which may communicate with a user computer via a wireless network and or transmit the listen in results to the AD SURVEY server.

In further implementations lighting sensor data may indicate the lighting condition of the user environment to determine the viewing status. GPS information contained in the atmospherics data may indicate whether the user is located with the home TV e.g. by comparing the instant GPS location with a registered user residential address etc.

In one implementation AD SURVEY may analyze the variety of atmospherics data to determine whether the user should be accorded as a viewer of the real time TV program on air. In one implementation as shown in the AD SURVEY server may adopt a procedure to generate a progressive weighted sum of atmospherics scores to determine whether the user is watching or not watching. When the weighted sum of different atmospherics scores exceeds a predetermined threshold the user may be considered not watching and the AD SURVEY may not need to proceed with further atmospherics analysis to improve efficiency of the atmospherics analystics.

For example at in e.g. comparing received user GPS information with the user s registered residential address in the AD SURVEY may determine an address type and may assign a weight to the GPS atmospherics factor based on the address type from an atmospherics GPS weight table . For example the atmospherics GPS weight table may assign 0.1 to a residential address 0.2 to a Starbucks store 1.0 to an outdoor address e.g. a national park etc. and or the like. In one example the AD SURVEY may assign a GPS factor weighing score similar to the following table 

In one implementation the AD SURVEY may calculate the atmospherics score which may be the assigned GPS weight at this stage and determine whether the score is greater than a predetermined threshold e.g. etc. . If so the AD SURVEY may conclude the user is not watching the TV and quit scoring . Otherwise the AD SURVEY may proceed with analyzing device app analytics data at and repeat the process of updating atmospherics score to determine whether a threshold has been met to suggest the user is not watching.

At the AD SURVEY may determine an active application type and assign a weight based on the application type . For example an active gaming application may be accorded 0.7 an active email application may be accorded 0.5 an active internet browser may be accorded 0.5 and or the like 

In one implementation the AD SURVEY may calculate an updated atmospherics score and determine whether it exceeds the threshold . If it has not exceeded the threshold the AD SURVEY may proceed with audio analytics results from provided such audio analytics is available from the atmospherics data. In one implementation the AD SURVEY may retrieve and or determine audio analytics indications e.g. ambient noise level media music which does not match the TV program on air human voice chatting on irrelevant topics etc. In one example the AD SURVEY may assign a weight based on audio analytics indications similar to the following table 

In one implementation the AD SURVEY may update the atmospherics score by adding the audio scores to determine whether it exceeds the threshold . Otherwise AD SURVEY may proceed to perform graphical analytics at given such visual data is available. In one implementation the AD SURVEY may retrieve and or determine visual analytics indications e.g. user activity user presence number of individuals TV screenshot etc. In one example the AD SURVEY may assign a weight based on visual analytics indications similar to the following table 

In one implementation if the updated score does not exceed the threshold the AD SURVEY may conclude the user is watching the TV program and feed such indication to for studying TV viewing rates. Otherwise the AD SURVEY may conclude the user is not watching and may not count the user as a viewer of the TV program.

In one implementation the AD SURVEY may process the decoded atmospherics data based on a progressive mechanism to reduce processing complexity. For example as shown in the AD SURVEY may start with a less complicated analysis of GPS information device application status and progressively proceed with visual data processing with a higher complexity.

Within embodiments the user s mobile device may capture image audio data video data GPS coordinates and or the like . In one implementation the AD SURVEY client component may automatically configure the user device to capture atmospherics data e.g. obtaining GPS coordinates capturing audio data capturing device application status data etc. In another implementation the AD SURVEY client component may prompt a request for the user to hold up the mobile device to position the camera for image video capturing of the TV screen the audience scene and or the like.

In one implementation the AD SURVEY may extract identifying information from the captured monitoring data such as a hardware ID MAC address and or the like. The AD SURVEY may determine whether there is any external event e.g. the user is sending a response to survey question submitting a channel selection etc. If there is such external event the AD SURVEY may launch the event and embed the atmospherics information into the user responses for transmission. For example in one implementation the embedded atmospherics data may have the same timestamp as the original user response data payload.

In another implementation the AD SURVEY may aggregate and packetize different atmospherics data in a compliant data format for transmission to the AD SURVEY server e.g. see in .

In one implementation upon receiving a message from the user device the AD SURVEY server may determine the message type . In one implementation if the message is an atmospherics data packet the AD SURVEY server may decode and analyze the atmospherics data packet to extract information as to the user s viewing status. For example the AD SURVEY server may perform an optical character recognition OCR procedure on a photographic frame extracted from the received atmospherics data to determine whether the TV program played on TV matches the program schedule associated with the user s selected channel e.g. whether the program is correct . For example if the user has submitted a selection of channel CBS the AD SURVEY may query on a program table to determine that The Big Bang Theory shall be on air at the timestamp when the atmospherics data is received. The AD SURVEY may then ascertain whether the received photo of the user s TV set indicates the show on TV is The Big Bang Theory. 

In a further implementation the AD SURVEY may determine whether the user is watching . For example the AD SURVEY may perform OCR on the received graphic data e.g. photos video clips etc. to determine whether the user is present in front of the TV. For another example the AD SURVEY may determine how many users are watching the TV program by being present. For another example the AD SURVEY may determine whether the user is present in front of his home TV by analyzing the received GPS coordinates e.g. when the user s GPS coordinates reflects he has migrated from his home address to a second address it may indicate the user is no longer watching the TV program after submitting channel selection.

In a further implementation the AD SURVEY may generate viewing data to determine audience rating of a TV program wherein analysis of the atmospherics data may contribute to the viewing statistics.

In one implementation AD SURVEY may register the user s non live media facility and may establish a secure communication channel with the non live media facility. In one implementation the AD SURVEY may receive a non live media schedule which may be automatically downloaded from the user s non live media e.g. media on demand Internet TV streaming service such as ABC episodes Hulu.com etc. and or provided by the user e.g. a list of recorded programs for replay .

In one implementation upon receiving an indication of non live media selection the AD SURVEY platform may check the program table to determine the TV program on the non live media and log the user channel selection of an associated TV program with a timestamp . The AD SURVEY may also obtain and analyze atmospherics data e.g. in a similar manner as discussed in to generate TV viewing data for the selected TV program .

Upon establishing communication with a TV DVD set the user device may monitor on user s channel submission . When a channel selection is obtained the user device may transmit a channel selection indication to the logged TV DVD address via the infrared plug in accessory . In this manner the user may operate a general purpose mobile device as a TV DVD remote.

For example in one implementation the TV media program table e.g. see also in may comprise a sub table comprising embedded advertisement tags. For example in one implementation an exemplary XML record of a media program data structure with ad tags may take a form similar to the following 

The above XML example shows a media program The Big Bang Theory season 3 episode 2 which is scheduled to be on air on CBS at 9 pm on Sep. 9 2000. The example media program comprise an ad tag which may be a regular advertisement e.g. non product placement or embedded in the scene of Audi automobile and another ad tag which may be an embedded product placement e.g. a pair of XYZ designer sunglasses as shown in a scene during the TV program e.g. see . In a further implementation the AD SURVEY may redirect the user to a URL www.buybags.com XYZ spring2000 if the user clicks to learn more about the product. In one implementation the AD SURVEY may generate synchronized advertisement to a user based on the ad tag by providing a pop up static ad e.g. Do you like Penny s sunglasses e.g. see in . In another implementation the AD SURVEY may generate an interactive ad including a tagged screenshot of the TV program containing the placed product e.g. see in .

In another embodiment the AD SURVEY server may generate questions synchronized and or related to the TV program ads which may be devised by the AD SURVEY based on the media content the user has viewed the advertisement the user has viewed and or the like. For example if the channel the user has been watching recently has played advertisement of Audi the AD SURVEY may prompt a question to the user such as which brand automobile would you prefer to determine the advertisement effects. In another example the user may receive real time information synchronized with a product placement embedded in the TV program. For example when a user is watching a TV show he may receive a prompt question related to an embedded advertisement in a scene of the TV show e.g. Do you want to learn more about Penny s sunglasses In a further implementation the AD SURVEY may redirect the user to a URL www.buythings.com XYZ designer spring2000 if the user clicks to learn more about the product.

For example in one implementation the AD SURVEY server may provide a HTTPS PUT message including the questionnaire in the form of data formatted according to the XML. Below is an example HTTP S PUT message including an XML formatted questions to provide to the user 

In one embodiment upon receiving questions and or ads at the mobile device the user may submit a response to the AD SURVEY server e.g. an answer to the question a click on the provided ad URL and or the like. In another implementation upon viewing an embedded advertisement while watching a TV program the user may desire to learn more or purchase the product and submit a request of purchase e.g. by clicking on Buy it Now C in to the AD SURVEY server . The AD SURVEY may forward the purchase request to a merchant website and redirect the user to view the merchant site to obtain more information of the interested product. In one implementation the AD SURVEY may log the user question responses indication of interests purchase transaction and or the like at the database to indicate ad effects.

For example in one implementation the AD SURVEY server may provide a HTTPS PUT message including the questionnaire response purchase request in the form of data formatted according to the XML. Below is an example HTTP S PUT message including an XML formatted questions responses purchasing request to provide to the database 

In further implementations the AD SURVEY may populate social media feeds of the user s questionnaire responses purchase information to a social media platform . In another implementation the user may share purchase information to the social media . For example the user s Facebook news feeds may comprise a message XXX participated in a survey. See her response e.g. see in . The user may also obtain his friends AD SURVEY activities including participation in surveys purchases etc. from social media news feed.

In one implementation the AD SURVEY may parse commercial ad information on the selected channel to extract key terms. For example in one implementation the AD SURVEY may retrieve the advertised product brand name product name category etc. In one implementation the AD SURVEY may query on a questionnaire database based on the parsed ad key terms . For example for an Audi commercial the AD SURVEY may parse key terms as Audi car automobile and select and generate pop up questions related to such key terms to the user .

In another implementation the AD SURVEY may incorporate a variety of user media content exposure data to generate media content based survey questions . For example AD SURVEY may incorporate mobile ads exposure data e.g. user web visits AD SURVEY generated mobile ads etc. user application status e.g. browsing history Internet gaming content etc. social content e.g. social pages social ads friends recommendations user likes etc. and or the like. In one implementation the AD SURVEY may receive the various user content exposure data from a AD SURVEY client component instantiated on the user mobile device e.g. an iPhone app etc. In another implementation the AD SURVEY may receive mobile data from a mobile meter a proxy server a TV metering system and or the like.

In one implementation the AD SURVEY may generate synchronized pop up survey questions to the user. For example in one implementation the AD SURVEY may analyze the ad tags prior to the TV program on air and prepare pop up questions associated with each ad tag. The generated pop up questions may be sent to the user according to the timetable of the ad tags. In another implementation the AD SURVEY may retrieve the user s viewing history e.g. the TV programs the user has recently watched etc. and determine the ads associated with the TV programs the user has watched to generate non synchronized pop up survey questions.

Upon receiving the pop up survey question the user may elect to submit a response which may indicate ad effects. In further implementations the survey questions may be generated based on advertisement the user has exposed to e.g. via cross channel ad measurement as further illustrated in social media contents and the like.

In one implementation if the TV program at the user submitted channel contains no synchronized ad tags the AD SURVEY may elect not to send ads questions to the user. In another implementation the AD SURVEY may retrieve user s recent viewing history e.g. the past week etc. and generate a non synchronized ad survey question to the user based on the user s recently viewed TV programs. In further implementations the AD SURVEY may re send ads that were synchronized with one of user s recently viewed TV programs to the user.

In further implementations the synchronized product placement ads may be applied to in game ads in a similar manner. For example the AD SURVEY may determine a user is engaging in a gaming application via the received device application event e.g. in and deliver an interactive advertisement of related virtual goods e.g. gaming points widget etc. to the user mobile device.

In another implementation if the received message comprises responses to prompt questions the AD SURVEY may determine a classification of the question e.g. a response to survey a response to embedded advertisement and or the like. In another implementation the question responses may be classified by the products e.g. automobiles apparels electronics and or the like. In one implementation the AD SURVEY may extract a questionnaire ID and or a survey ID from the received user response and store the questionnaire results associated matched with the questionnaire based on an ID query.

In a further implementation the user who responds to questionnaires may be credited for a reward. For example after obtaining and storing questionnaire results the AD SURVEY may determine rewards for the user e.g. five AD SURVEY points for each question answered etc. and credit the points to the user s AD SURVEY account . In another implementations the rewards may comprise virtual currency e.g. store points gaming points etc. coupons discounts and or the like sponsored by an advertising merchant.

In another implementation when the AD SURVEY determines the response does not comprise a response to a survey question at the AD SURVEY may determine whether it comprises an interactive activity indication . For example a user may submit a rating of the product with the interactive ad click on the interactive ad and or the like. In one implementation if the user submits a purchase request the AD SURVEY may provide a merchant URL and or direct the user to a merchant page to proceed with purchase transaction . The AD SURVEY may log user activities associated with the product placement advertisement e.g. with an ad ID etc.

In one implementation the AD SURVEY may aggregate data analysis results from all different types of messages received from the user and run aggregate analytics for ad effects. provides a logic flow diagram illustrating ad delivery effects analysis within embodiments of the AD SURVEY. For example in one implementation AD SURVEY may obtain a correlation of an advertisement and user perception of the product based on responses to the survey question e.g. if a user selects Audi in an automobile survey after viewing an Audi advertisement etc. . In further implementation AD SURVEY may generate an ad effect score for each advertisement.

In one implementation AD SURVEY may retrieve an advertisement and determine an ad classification e.g. a category of the advertised product e.g. apparel accessories automobile electronics etc. . For example for an Audi advertisement the AD SURVEY may query for stored questions e.g. in results with the ad classification automobile . If such survey responses are available the AD SURVEY may query the retrieved survey responses for mentions of the product e.g. on a brand name Audi on a make and model of the Audi automobile etc. For each response the AD SURVEY may determine a relevance of the question and question results . For example the AD SURVEY may retrieve the corresponding question with the question results based on a question ID e.g. stored at in and perform text analytics to determine a relevance level of the question to the brand name product Audi automobile e.g. based on whether the question contains key terms such as preference car purchase etc. . In one implementation the AD SURVEY may determine an ad effect weight value for the response . For example the AD SURVEY may perform text analytics of the question and questions results and if the textual question question results contain key terms such as car purchase and Audi such response may be accorded with a high weight value. In one implementation the weighting value determination at may be based on a pre stored weight evaluation table e.g. 0.5 for submitting a response of Audi 0.8 for clicking on a merchant site 50.0 for transacting a sale on an Audi automobile etc. and calculate an impact score of the advertisement based on a group of users e.g. see I at . The AD SURVEY may generate an ad effect sub score based on analytics of user survey responses e.g. taking a weighted sum etc.

In another implementation the AD SURVEY may query for stored user activities e.g. stored at in in response to an ad e.g. purchasing request click for more information etc. base on an ad ID . If such activities are available the AD SURVEY may determine a type of the activity e.g. clicks on the ad for more information clicks on a provided merchant URL user rating of the advertised product clicks on Buy It Now closing the ad without browsing and or the like. Based on the activity type the AD SURVEY may associate a weight value for the activity and generate an ad effect sub score based on analytics of user activities e.g. taking a weighted sum etc. For example a click on a merchant URL may be accorded with a high positive weight value and a prompt window close of the ad may be accorded with a low or zero weight value and or the like. In one implementation the AD SURVEY may generate an indication of ad effects based on an integrated ad effects score e.g. taking a sum of the subscores from and etc. .

In one implementation AD SURVEY may compare the ad effects score of the same ad on different media channel to determine efficiency of the ad placement. For example if the same Audi ad has a higher impact score on channel ESPN than Disney it may provide heuristics to the merchant that such advertisement is more efficient on ESPN. In further implementations AD SURVEY may determine efficiency of the time and the TV program to place the advertisement based on the ad effects score.

In one embodiment the AD SURVEY controller and or the different components may be instantiated on a user mobile device e.g. an Apple iPhone etc. In an alternative embodiment the controller may be housed separately from other components and or databases within the AD SURVEY system while in another embodiment some or all of the other modules and or databases may be housed within and or configured as part of the AD SURVEY controller. Further detail regarding implementations of AD SURVEY controller operations modules and databases is provided below.

In one embodiment the AD SURVEY controller may be coupled to one or more interface components and or modules. In one embodiment the AD SURVEY Controller may be coupled to a user interface UI . The user interface may be configured to receive user inputs and display application states and or other outputs. The UI may for example allow a user to adjust AD SURVEY system settings select communication methods and or protocols manually enter texts engage mobile device application features and or the like. In one implementation the user interface may include but not limited to devices such as keyboard s mouse stylus es touch screen s digital display s and or the like. In another implementation the user questionnaire component may provide user survey questions and receive user responses via the user interface .

In one implementation the AD SURVEY Controller may further be coupled to a sensor module configured to interface with and or process signals from sensor input output I O components . The sensor I O components may be configured to obtain information of environmental conditions and or the like to generate atmospherics data that may be received and or processed by other AD SURVEY components. A wide variety of different sensors may be compatible with AD SURVEY operation and may be integrated with sensor I O components such as but not limited to a camera an audio recorder a GPS component and or the like configured to capture video clips photos of what is playing on the TV and or whether the user is watching the program audio recording clips indicative of what is playing on the TV GPS information indicative of the user s location and or the like. In one implementation the Media Listen In Component may configure aggregate and packetize atmospherics data captured by the sensor module component in a data format suitable for data transmission via the sensor I O . In a further implementation the Media Listen In Component may process and analyze the obtained atmospherics data e.g. a photo captured by the mobile device etc. to identify whether the user is watching and or how many individuals are watching from the photo via image processing. For example in one embodiment the iPhone SDK toolkit and or runtime libraries may be installed and or used to perform such image processing.

In one embodiment the AD SURVEY Controller may further be coupled to a communications module configured to interface with and or process data transmission from communications I O components . The communications I O components may comprise components facilitating transmission of electronic communications via a variety of different communication protocols and or formats as coordinated with and or by the communications module . Communication I O components may for example contain ports slots antennas amplifiers and or the like to facilitate transmission of TV program listing information user submission of channel selection user responses to survey questions and or the like via any of the aforementioned methods. Communication protocols and or formats for which the communications module and or communications IO components may be compatible may include but are not limited to GSM GPRS W CDMA CDMA CDMA2000 HSDPA Ethernet WiFi Bluetooth USB and or the like. In various implementations the communication I O may for example serve to configure data into application transport network media access control and or physical layer formats in accordance with a network transmission protocol such as but not limited to FTP TCP IP SMTP Short Message Peer to Peer SMPP and or the like. The communications module and communications I O may further be configurable to implement and or translate Wireless Application Protocol WAP VoIP and or the like data formats and or protocols. The communications I O may further house one or more ports jacks antennas and or the like to facilitate wired and or wireless communications with and or within the AD SURVEY system. For example the communication I O may be extended by a plug in accessory as shown at in .

Numerous data transfer protocols may also be employed as AD SURVEY connections for example TCP IP and or higher protocols such as HTTP post FTP put commands and or the like. In one implementation the communications module may comprise web server software equipped to configure application state data for publication on the World Wide Web. Published application state data may in one implementation be represented as an integrated video animation rich internet application and or the like configured in accordance with a multimedia plug in such as Adobe Flash. In another implementation the communications module may comprise remote access software such as Citrix Virtual Network Computing VNC and or the like equipped to configure user application e.g. a user mobile device . In another implementation the communications module may transmit TV program listing information to the real time TV remote control component which may in turn receives user channel selection form the user interface .

In further implementations the AD SURVEY may be configured to communicate with a content based embedded advertising component media content questionnaire synchronization component and or the like as further discussed in .

In one implementation the generated ad synchronization questions may be received and provided to the user via a user interface generated by the user questionnaire component on the user s mobile device which may in turn provide user s response events to an Ad effect engine component at the MR PLATFORM server to analyze advertisement effects.

In one embodiment the media listen in component may collect and aggregate atmospherics data e.g. video recording clips audio recording clips photo streams GPS information and or the like to a media viewing statistics analysis component which may analyze the media viewing data and determine the audience reception rate of a TV program and or advertisement.

In a further implementation the social media connection component may generate and transmit social media post indicating the user s viewing status to a social media database and may optionally send the social media post to the AD SURVEY as well. In one implementation the AD SURVEY server may obtain the user s social media status updates information including friends recommendations comments and or the like via an API call to the social media database . In another implementation the AD SURVEY server may redirect a user to the social media website from the user s instantiated AD SURVEY client component to engage in social media activities. For example the user may click on a social media link via the AD SURVEY client component user interface and be redirected to the social media page.

The table top device may facilitate mobile remote control to operate in a similar manner as the AD SURVEY accessory in . Instead of being plugged into a user mobile device the table top device may communicate with a user device running the remote mobile application via wireless connections. For example the table top device may be operated for remote TV channel control collecting atmospherics data for audience monitoring and or the like. In further implementations the table top device may be positioned so that the table top device may capture images from the screen of the TV set.

In one implementation the table top device may be configured to periodically monitor audio contents video contents etc. in the atmosphere with or without having user input of a channel selection. For example the table top device may record an audio video clip of media program being played and send such audio video clip or generate a signature hash based on sampling of the recorded audio video media content to the AD SURVEY server which may in turn determine what the user is watching. Further implementations are discussed in .

In a further implementation the AD SURVEY may track social media content e.g. Facebook and Twitter etc. of AD SURVEY consumers e.g. users who has authorized AD SURVEY to access their social media content. In one implementation the AD SURVEY may link demographic behavioral and attitudinal data from the user s profile information with social media behavior. The social media data downloading may be obtained via API calls as discussed in .

In a further implementation the AD SURVEY may recruit consumers e.g. Facebook Twitter users who have allow AD SURVEY to access their social content as AD SURVEY panelists e.g. by providing incentive rewards to the users etc. In one implementation the AD SURVEY may track how social media messages propagate throughout a network of social media users e.g. the recruited panelists etc. based on the profiles of the individuals. Such measures of connectivity may be analyzed to measure propagation of marketing communications.

In another implementation each panelist may be associated with a social media specific profile so that their social media activities may be tracked to determine whether they are influencers in certain categories disseminators of information information consumers and or the like. For example in one implementation a panelist may be labeled as a The Big Bang Theory Fan Wiki so that users interested in the show The Big Bang Theory may follow the panelist to obtain information of the show via the panelist s posts comments and or the like related to The Big Bang Theory. 

In one implementation individual social media profiles may be incorporated to assess advertising targeting performance enable advertisers to plan social media campaigns by targeting product influencers and or the like.

As shown in AD SURVEY server may send an access request to a social media platform e.g. Facebook Twitter Google etc. for access to a user s profile information and social media content e.g. news feeds posted photos Tweets comments activities Likes Dislikes etc. .

In one implementation upon receiving the access request the social media may generate and send a user authorization request to the user . For example Facebook and or Twitter may send an email to the user wherein the email may comprise an authorization link directing the user to a AD SURVEY authorization page e.g. as included in the access request . In one implementation the user may be access the included authorization link via a mobile application UI e.g. see and or a web based application UI e.g. see . As shown in the user may click Allow to grant permission of AD SURVEY to access the user s social media content. In further implementation as shown at in the user may configure a scope of information the AD SURVEY may be allowed to access.

For example in one implementation the user s mobile application and or a web based application may generate a Secure HTTPS PUT authorization message including an application ID and permission indication for the social media platform in the form of data formatted according to the XML. Below is an example HTTP S PUT message including the XML formatted access authorization message provide to Facebook 

In the above example the authorization message to Facebook may comprise information as to the scope of information access e.g. the user may permit AD SURVEY to access the user JDOE s Facebook profile including his name age date of birth work an education information interested pages network and or the like a number of friends of JDOE but may not access an exact friends list. The user may allow AD SURVEY to obtain JDOE s posts on his own wall but may not permit access to his posts on his friends wall or friends comments on his wall and or the like.

In one implementation the social media may pass on the application ID from the user s mobile or web application and generate a user token to AD SURVEY for confirmation of access permission. In one implementation the AD SURVEY may determine when data update is needed e.g. the data update from social media may be performed on a periodic basis e.g. daily weekly etc. . The AD SURVEY server may generate a data request together with the received user authorization token e.g. and transmit to the social media platform.

In one implementation the data request may be sent to the social media platform via a user oAuth protocol and comprise a AD SURVEY application ID and or a user social media ID and or the like. For example in one implementation the AD SURVEY server may provide a Secure HTTPS PUT message including a data request for Facebook in the form of data formatted according to the XML. Below is an example HTTP S PUT message including the XML formatted access request provide to Facebook 

In the above example the data request generated by AD SURVEY to Facebook may comprise a user ID JDOE indicating the request is directed to Facebook information of the user JDOE a client ID indicating the application e.g. the AD SURVEY mobile application ID etc. indicating a source of the request and a URL link which may be provided to the user for authorization e.g. a link that requests the user to click a OK or Cancel button on the page to authorize or deny AD SURVEY to gain access to the user s Facebook content. The access request may further comprise information as to the scope of information access e.g. AD SURVEY may request to access the user JDOE s Facebook profile including his name age date of birth work an education information interested pages network and or the like. The AD SURVEY may also request to obtain information of a number of friends of JDOE but may not request to access an exact friends list. The AD SURVEY may further request to obtain JDOE s posts on his own wall but may not request to obtain his posts on his friends wall or friends comments on his wall and or the like.

For another example in one implementation the AD SURVEY server may provide a Secure HTTPS PUT message including a data request for Twitter server in the form of data formatted according to the XML. Below is an example HTTP S PUT message including the XML formatted access request provide to Twitter 

In the above example of data request to Twitter the request may comprise a user signature request. For example a user may provide electronic signature by clicking on a link e.g. at etc. noting I hereby provide my signature by pressing this button to allow AD SURVEY access my Twitter content etc.

In one implementation upon verification of the data request by Facebook Twitter other social media platform AD SURVEY server may download social media structured data and unstructured data e.g. see in for media analytics.

In one embodiment the AD SURVEY media measurement portal may load data from social networks via a HTTP network via API calls e.g. Facebook APPI Twitter API Google API and other social data providers . The media measurement portal may process the loaded data within different analytics platforms based on loaded data types e.g. structured data or unstructured data

For example in one implementation structured data may be already stored in a structured format when loaded from the data source such as but not limited to user TV channel selection indication with timestamp web displaying content with timestamp social media user profile information a number of user s social connections time stamped a posted photo on social media platform with timestamp and or the like. For example an exemplary XML record of structured Facebook user profile data downloaded from Facebook may take a form similar to the following 

In one implementation the analytics platform for processing structured data may store the structured data such as TV channel selection mobile web content data social network user profile data etc. in a database

For another example unstructured data may comprise raw text downloaded from social media platform e.g. friends comments from Facebook original Tweets etc. In one implementation AD SURVEY social analytics platform may perform data mining on unstructured data to measure user feedbacks of a brand name product TV program etc. For example a query may be performed on the unstructured data to determine how many mentions of The Big Bang Theory are posted by Facebook users.

For example in one implementation an exemplary XML record of unstructured Facebook user message downloaded from Facebook may take a form similar to the following 

For further implementations the unstructured data may comprise a social post a social media check in status social mentions and or the like.

In one implementation the AD SURVEY structured data analytics platform comprises a variety of processing components such as but not limited to user permission component for social media access TV mobile web measurement reports component media analytics engine organization user account management component single source data extraction transformation and load ETL component and or the like. Within implementations the user permission component may present panel users with a set of user interface screens requesting them to provide permission for AD SURVEY to access their social content. For example AD SURVEY may provide incentives of promotional rewards points coupons and or the like to users during questionnaire distribution e.g. AD SURVEY mobile questionnaires etc to allow AD SURVEY access to their social content.

In one implementation if the user agrees to provide the access to their social content the permission component may get the authorization token from the respective social platforms Facebook twitter etc as per the authorization protocol and persist the token in a repository . The user permission component may pass the user token and other application authorization details to social analytics platform so that the user s social content can be extracted at a scheduled frequency. For example AD SURVEY may periodically constantly and or intermittently load social content data from the social media platforms via API calls once authentication is established. Further implementations of user permission flows are discussed in .

In one implementation the media analytics engine may analyze the loaded structured data e.g. per user profile per media type etc. In one implementation the organization user management may create and manage user accounts with the AD SURVEY. In further implementations the TV mobile web measurement reports component may generate media measurement reports e.g. including audience ratings ad effectiveness etc. based on structured media data such as audience TV channel selections mobile web browsing activities etc.

In one implementation the AD SURVEY unstructured data analytics platform may have a rule to define the specific fields for which the content needs to be extracted for a given user e.g. user demographics no of friends no of messages in a given duration actual text for message and comments etc . Based on the authentication token the social media analytics platform may query the social platform for the content. In one implementation the social analytics platform may schedule the query tasks and persist structured and unstructured content that is extracted.

In one implementation the AD SURVEY social analytics platform may comprise a variety of processing components such as but not limited to social media measurement reports component taxonomy management console text analytics engine social media adapters social analytics platform API and or the like. The social analytics platform API may exchange data via API calls with the single source ETL process component such as user authorization tokens and or the like.

In one implementation the taxonomy management console may define taxonomy tags and taxonomy logic rules. For example the taxonomy may be defined at three different levels a standard taxonomy specific to an industry and business function as provided by the platform vendor e.g. tagging a unstructured data record by industry etc. taxonomy defined by analyst and subject matter experts e.g. AD SURVEY analytics defined taxonomy rules etc. and or taxonomy defined by clients and or the like. For example for a Tweet Good adaption of the Southern Vampire series. Love the CBS actors actresses. Expecting the new season e.g. in the text analytics engine may apply a taxonomy rule to tag it by a hierarchy of tags TV show CBS The Big Bang Theory Positive Feedback. For another example the client e.g. CBS etc. may desire to categorize the commented target of the Tweet and therefore the taxonomy rule may comprise an additional sub category actor actresses and or the like. In one implementations such taxonomy rules may be stored in a repository and the original social text data and social graph tagged social data may be stored at . Further implementations and applications of the taxonomy rules are discussed in .

In one implementation the social media measurement reports may provide a user feedback measurement report to a user via UI integration and data visualization. Within implementations the reporting portal may leverage the web based visual components e.g. word cloud traffic light components etc provided by the social media analytics platform for analysis that deliver insights purely on social media data. In further implementations for insights generated on combined data set from social and other data sources e.g. via data mesh up between the structured data analytics platform and unstructured data analytics platform etc. the taxonomy management console may be integrated to an integrated reporting portal to ensure the clients have the self service capability of defining the taxonomy and building the reports. For example single sign on and UI widget meshup may be adopted between the two platforms and for integration of the two.

In one implementation the AD SURVEY media measurement portal may combine structured social media data with other data sources to generate cross media insights. The social media analytics platform may have the API to extract data for predefined metrics and attributes e.g. taxonomy logics data tags etc. . The metrics and attributes may be predefined in the social media analytics tool to compute from the structured and unstructured content extracted from the social media platforms.

In one implementation the AD SURVEY media measurement portal may use different platforms for social media reporting and structured data reporting and have a tight integration at the data and UI layers of both the platforms. Additional implementations of the AD SURVEY media measurement portal may comprise out of the box connectors for social media platforms like Facebook Twitter Google etc e.g. at etc. web based taxonomy creation and management user interfaces industry specific prebuilt taxonomies e.g. at etc. text analytics engine with sentiment analysis with learning algorithms e.g. at etc. ability to define fields for which social content needs to be extracted e.g. at etc. data API calls to extract large data set in and out of the platform in real time and or in batch mode e.g. at etc. data API calls for UI widget integration to create mesh up e.g. at etc. multiple tenant support to ensure taxonomies defined at organization and department level e.g. at etc. single sign on support with active directory service interfaces ADSI and other light weight directory access protocol LDAP providers e.g. at etc. components to generate insights from large historical data e.g. over two terabytes of data components to schedule data extraction jobs from social media sites e.g. at etc. components to support to host the service on a cloud and or the like.

In one implementation the user may allow AD SURVEY platform to access to their social network. For example in one implementation the user may sign up for AD SURVEY permission via a AD SURVEY mobile application from a mobile device e.g. an Apple iPhone an Android etc. . For another example the user may visit a AD SURVEY social data panel management website e.g. as illustrated in one example in . In each case AD SURVEY may provide a sign up link to a social media platform to the user. Upon user clicking the link the AD SURVEY may verify whether the user previously authorized AD SURVEY to access their Facebook or Twitter information on their behalf and their previous authorization token e.g. in is not expired.

In another implementation the AD SURVEY may receive user attempts to log in and determine whether the user is authorized to grant social media data access permission for AD SURVEY. For example when a user has received an email from a social media platform e.g. Facebook Twitter etc. comprising a AD SURVEY link for authentication and the user clicks the link to proceed to grant permissions for AD SURVEY the user may deemed authorized to configure social media permissions via AD SURVEY. In another implementation when AD SURVEY determines the user is not authorized AD SURVEY may redirect the user to a social media page with a AD SURVEY application ID and a permission attribute request e.g. as discussed at in .

In one implementation the AD SURVEY may determine whether access is approved by the user e.g. the user may select Yes or Cancel to indicate permission decision for AD SURVEY to access the user s social media content when the social media platform sent an email notification indicating the access request from AD SURVEY e.g. at in .

For example if the previous authorization is not valid or if it is a first time access then the AD SURVEY application may use oAuth protocol to request Facebook or Twitter to provide access to user profile and messages e.g. sending an access request as shown in . In such cases the user may be redirected to Facebook or Twitter web site with request to log in and provide access parameters e.g. see in in . Facebook or Twitter web site may present a login and permission screen with option to allow or deny requested access to AD SURVEY e.g. see at .

In one implementation if the user approves the access request then in the response Facebook or Twitter may provide an authentication token associated with permission to the data elements e.g. at . In one implementation the authentication tokens may be requested with constant permission to allow user data access even when the user is neither logged into AD SURVEY user portal e.g. the mobile app or the web based app nor any social media platform. In alternative implementations the authentication token may request timely update and re authentication from user on a periodic basis e.g. weekly monthly etc. In further implementations the user may revoke access of AD SURVEY from to their social media account if they wish to opt out.

If the user granted the permission AD SURVEY may save the authorization response token provided by the social media platform in a user repository . The authentication token may be used in all subsequent requests to social networking sites to access user s data elements. In another implementation if the user did not grant permission the user may continue with the mobile application or the web based panel management website

Upon establishing and or confirm user authorization for social media access AD SURVEY server may generate social messages to populate to social media platforms via AD SURVEY e.g. see in in etc.

For example if the data record is obtained from Facebook the data format analytics may determine whether it is structured user profile information a user posted photo unstructured user posting on the wall others comments and or the like. For another example if the data record is obtained from Twitter the AD SURVEY may determine whether it comprises raw text of a Tweet and or the like.

In one implementation if the received data is structured AD SURVEY may parsing the structured data to extract information . For example a structured user profile data record may be parsed per data field e.g. user id user name user DOB user interests and or the like. The AD SURVEY may generate a data record including user ID timestamp geo source etc. and store the data record for the structured data at a database e.g. see in .

In another implementation if the received data is unstructured e.g. raw texts of Facebook comments Tweets etc. AD SURVEY may feed the data to a Taxonomy engine for data tagging as further illustrated in .

Within implementations a AD SURVEY analytics platform e.g. at may extract and use different sets of data elements from a user social media profile. For example in one implementation as shown in a data record of a Facebook user profile may comprise data fields such as user work information user education information television viewing history interested music interested books data feeds likes status message comments on status message wall posted comments check in history and or the like.

In one implementation data elements are categorized based upon how frequently they are updated and AD SURVEY may accordingly determine the fetch and refresh schedules. For example the categorization may comprise users static descriptors such as user demographic attributes like date of birth gender etc. which may be relatively constant and static and thus may be determined to scheduled to update every 6 months. For another example the categorization may comprise dynamic descriptors such as number of friends Likes television viewing books and other preferences which may be updated by a Facebook user more frequently and may be scheduled for updates monthly. For another example the categorization may comprise text messages status comment messages posts etc. and may be scheduled to update daily and or on demand. In one implementation AD SURVEY may specify the requested content in a data request accordingly e.g. for user descriptors only for dynamic descriptor only for text messages only and or any combination of the above. e.g. see the RequestedContent field in the example Facebook data request in .

In one implementation AD SURVEY server may download social media data updates e.g. as discussed in and form a query based on the retrieved social media data based on the user inquiry. For example when the producer CBS would like to know audience feedbacks of the show The Big Bang Theory e.g. see AD SURVEY may search for data related to The Big Bang Theory on the retrieved updated social media data.

For example in one implementation AD SURVEY may form a query on the structured data based on key word The Big Bang Theory and or any character names and or actors actress names for the associated profiles e.g. a Facebook pages Twitter profiles and obtain a number of followers from the structured data. In another example AD SURVEY may form a query based on the key term The Big Bang Theory and obtain raw text comments containing the key term. In one implementation AD SURVEY may perform a progressive search over the raw text e.g. unstructured data etc. . For example AD SURVEY may search for The Big Bang Theory and then refine the search results by The Big Bang Theory AND CBS and refine the search results by The Big Bang Theory AND CBS AND Show and or the like. In one implementation AD SURVEY may search the unstructured data based on data tags associated therewith as further discussed in .

In one implementation AD SURVEY may obtain query results which may comprise a number of followers on the social media platform a series of raw text comments from the social media and or the like. The AD SURVEY may then determine a presentation format to provide the results to the user. For example when the user elects to choose raw texts e.g. see in the user may view a list of raw text comments e.g. see in . In another implementation AD SURVEY may select an output visualization format and present the visualization of query results to the user and the user may view visualized results e.g. see in .

In one implementation AD SURVEY may apply taxonomy model logics which may comprise any of a first logical section associated with the semantic categorization of keywords and a second logical section associated with the sentiment keywords. In one implementation the taxonomy may assign weighted scores to the logical tagging in conjunction with the semantic text.

For example in one implementation the semantic categorization logic may be hierarchical and specific to a domain to maintain simplicity of in model management and run time executions e.g. a specific taxonomy model for TV shows a specific taxonomy model for advertisement and brand mentions a taxonomy model for any combination of the above and or the like.

The AD SURVEY may extract sample text for a TV show from social media by a text miner e.g. the text analytics engine in to identify most commonly used key words by the social media users. For example user comments posted on the Facebook page of The Big Bang Theory e.g. see in may be sampled to extract key words if words such as Werewolf characters Bontemp fictional town in the story etc. are frequently used in the comments the taxonomy engine may adopt these words for taxonomy tags e.g. the key word text in descriptor see in . This process may enrich the dictionary and provide inputs to defining taxonomy rules. The AD SURVEY may be associated with the identified key words with a level for the tagging . For example in one implementation the keywords identified from sampled social media raw texts e.g. Tweets Facebook posts etc. may be associated with appropriate nodes e.g. level 0 1 2 5 etc.

In a further implementation AD SURVEY may identify keywords set for each TV show topic including words spelled differently but meant to refer the same entity to expand the query scope e.g. COCA COLA COCA COLA S COKE COKE S COCA COLA COCACOLA etc. Within implementations a variety of logical combination of such key words may be coded as a logical rule with AND OR Not operator e.g.

wherein the is an AND operator and is an OR operator. The AD SURVEY may establish a taxonomy tree combining the rules and store the generated logic taxonomy tree in a taxonomy database e.g. see in .

In one implementation AD SURVEY may follow the taxonomy tree for Coke forming a query on a second category e.g. brand name and positive mentions . In the above example the taxonomy tree may apply a query on Coke Good etc. If such text is found AD SURVEY may generate a sub tag associated with the unstructured data with Coke good . If not the AD SURVEY may apply the taxonomy for an alternative query key terms e.g. Coke Excellent and or the like. Similarly if that is found AD SURVEY may generate a sub tag Coke Excellent with the unstructured data .

Continuing on with the taxonomy engine may progressively query on Coke and key word texts e.g. too much taste etc. If such key words are found the AD SURVEY may generate s sub tag e.g. level 2 with the unstructured data . If not the AD SURVEY may move on with the next taxonomy rule.

Within implementations during the taxonomy rule execution process each taxonomy rule may be executed at a leaf node and then the next higher level may be computed. Upon finishing with a taxonomy tree the AD SURVEY may generate a matching score of the applied taxonomy logics . For example the score may be based on a similarity percentage of the key terms in each node of the taxonomy tree and the compared unstructured data segment. To maintain efficiency taxonomy execution models may be logically partitioned. For example for a segment of raw text the same unstructured text segment may be executed through different models and scores generated may be merged and aggregated. When the similarity score is greater than a threshold e.g. 80 etc. the current tagging generated from may be saved . Otherwise the AD SURVEY may proceed with a different taxonomy model e.g. at in .

In one implementations AD SURVEY may apply one or more taxonomy logics to an unstructured data segment as the data segment e.g. a Tweet a Facebook post etc. may be related to one or more brand products etc.

In further implementations the taxonomy tagging mechanism may be associated with a weighting score at each node of the taxonomy hierarchy. For example in the above example for Coke if the AD SURVEY receives a client request to analyze consumer impression about a new product of Coca Cola on social media analytics the AD SURVEY may perform taxonomy mining upon unstructured data from the social media e.g. consumer comments . Each node may be progressively associated with a weight score to determine consumer impression. For example when the data comprises Coke a level 0 weight score may be assigned e.g. 0.1 etc. when the data comprises Coke good or Coke excellent a level 1 weight score may be assigned e.g. 0.5 etc. but when the data comprises Coke horrible or Coke with other negatively indicative adjectives a negative level 1 weight score may be assigned e.g. 0.5 etc. . In one implementation the taxonomy engine may calculate an overall score of an unstructured data record when progressively querying upon taxonomy key terms and generate statistical results of a group of unstructured data to determine the consumer impression. For example the AD SURVEY may generate statistical report as to how many consumers are positive neutral or negative towards Coke based on their calculated scores as illustrated in one example in . For another example the AD SURVEY may generate popular brands TV shows that are the mostly mentioned or positively commented from social media users e.g. see . In further implementations the AD SURVEY may determine a social group to analyze their social content. For example within the social group the AD SURVEY may determine user s influence over.

over other members of the population e.g. whether a user is an influencer. For example when a user posts comments to the CBS show The Big Bang Theory on Facebook and his Facebook friends have liked his comments and subsequently watch the show the user may be considered as a Facebook influencer. In one implementation the notion of influencer may be specific to a social media platform a person who is an influencer on one platform may not be an influencer on another.

In one implementation the social influencer may be determined by social media indices. For example the AD SURVEY may analyze prerequisites for consideration as a social media influencer such as whether a user has an account on a social web platform whether the user has generated content on that platform within the past 30 days and or the like.

In one implementation the AD SURVEY may calculate social media index of a user to determine an influencer. For each member that meets the prerequisites a social media index is calculated using various measures. For example the AD SURVEY may calculate a reach measure e.g. over the past 30 days the maximum size of the network which may be measured through friends followers or other similar measures. For another example the AD SURVEY may calculate a frequency measure e.g. over the past 30 days the total number of posts to the platform which may be measured through things like status updates tweets or comments depending on the relevant content generation opportunities for the particular platform. For another example the AD SURVEY may calculate a resonance measure e.g. over the past 30 days the total number of responses to the individual s content. Depending on the platform these responses may take the form of retweets comments on posts or status updates or direct messages responses to the individual. The responses may or may not need to come from individuals within the population being measured.

In one implementation the calculated measures are then ranked against the same measure from other individuals in his or her demographic group. The demographic measures may include but are not limited to age gender race education and income. The specific groupings used for age education and income can vary based on the population being analyzed. An individual is considered an influencer if he or she ranks in the top 20 of at least two of the variables.

In further implementation the influencer determination may be refined by product category. Each post made by an individual may be classified as mentioning a product or not mentioning a product based on text analysis against a standard taxonomy of products and brands. The volume of posts in each category can be tabulated and an individual classified as an influencer in any product category which represents at least 20 of his or her product classified posts. In further implementation a social influencer may be specified and or classified with regard to a TV show category a category of products a category of brands and or the like.

In one implementation AD SURVEY may track audience activities to content planning and competitive analysis and advertising post analysis ad effectiveness . In one implementation the AD SURVEY may create digital footprints on usage as a bi product of delivering content and advertising e.g. via application session ID cookie etc. to create dataset that is used for tactical content and advertising decisions. For example the MR PLATFORM may set up a group of users e.g. 100 000 users etc. to track their TV viewing Mobile usage Online surfing history advertising exposure demographic information product ownership info for auto location financial services product usage information for CPG Pharma and or the like to provide survey research for ad effectiveness. In one implementation AD SURVEY may recruit users with incentive rewards e.g. the participants may be required to allow AD SURVEY to access their social media content as illustrated in e.g. Credit in iTunes or Google App Store account e.g. 10 quarter 40 a year local coupons offers based on zip code etc.

As shown in the AD SURVEY may automatically collect data from various source e.g. online advertising usage mobile device usage TV viewing data social media data e.g. Facebook posts conversations etc. via API calls e.g. see . In another implementation the AD SURVEY may employ panelists to configure data downloads parameters system maintenance and or the like. For example the panelist may comprise social media users that allow AD SURVEY to access their social profile and content for analytics.

In a further implementation the AD SURVEY may utilize the AD SURVEY client component installed at a user mobile device to capture TV viewing in the home survey responses and or the like. In a further implementation the AD SURVEY may adopt a mobile meter to measure mobile usage. In another implementation the AD SURVEY may provide a client component which may provide history information from a user s personal computer when user connects his mobile device to his computer to sync up so that the AD SURVEY may track online Internet usage of the user e.g. browsing history clicks on ads etc. In a further implementation the AD SURVEY may track TV ad exposure from a variety of meter data e.g. TNS M AceMetrix and or the like. In further implementations data may be collected passively via mobile phones in almost real time and or when phone is being charged.

Within implementations TV distribution may be driven by an over the air broadcast and a one to many cable infrastructure. Unlike other media and industries like the Internet and the CPG retail environment the TV infrastructure may not create footprints on usage with content or product distribution. In such cases the industry may have a panel based research to understand the size and composition of TV audiences. All decisions related to programming ad sales and carriage deals between multiple system operator and cable networks may be based upon panel data which may enable research providers to realize outsized rewards for providing insights.

In one embodiment the AD SURVEY may obtain TV viewing data via Return Path Data RPD from Digital Set Top Boxes RDTB which may facilitate analysis of TV viewing to provide insights on viewing to small networks and small geographies e.g. local market measurement reflecting a local TV station or cable MSO zone. For another example metered data from RPD may be applied to analyze a group of categorized audience e.g. heavy Coke drinkers with targeted ad content e.g. a 30 second commercial on a niche targeted network .

In further implementations the AD SURVEY may study ad effects by collecting data with regard to user purchasing activities of the advertised products. For example the AD SURVEY may track user clicks on a Buy it Now button e.g. see in . In another implementation the AD SURVEY may obtain data form retailers manufactures Internet players and or the like wherein real store data frequent shopper cards usage and log files Internet shopping may be analyzed to study placement decisions increase traffic and sales ad visits use the granular traffic click stream data to design customized products content advertising to shoppers viewers and real time analytics to better manage ad campaigns and or the like. In one implementation a weighing scoring mechanism similar to that illustrated in may be employed but expanded to a variety of cross channel tracking data to analyze ad effects within a cross channel dataset.

In further implementations the MR PLATFORM may access to non live media such as Charter TiVo Rentrak Internet TV e.g. Google TV Apple TV and or the like and incorporate viewing data for analysis e.g. see .

In further implementation Internet measurement data e.g. from ISP data etc. may be collected e.g. HTTP cookies click stream data with demographic to information and or the like.

In further implementations mobile usage may be tracked via specific applications e.g. in a similar manner to log file analysis anonymous location based tracking of cell users and or the like.

In one implementation a client e.g. a user a merchant for analytics report etc. may access the AD SURVEY analytics server via a website which may in turn operate with a text analytics platform to analyze social content cross channel data and or the like.

In further implementations the Ad SURVEY may identity an advertisement comprised in a URL link via advertisement image recognition. For example the AD SURVEY may identify graphical contents contained in a URL link based on empirical pattern of web content format. Such empirical patterns may be classified per URL link type e.g. a shopping site ink such as Amazon.com may have an advertisement placed at the center frame of the web page a news link such as New York Times page may have an advertisement placed at the side bottom bar of the web page and or the like . For another example the AD SURVEY may identify dynamic contents on the web page such as but not limited to flash contents banners applets and or the like as displayed advertisements.

Within implementations upon obtaining an image capture of an advertisement the AD SURVEY may adopt software packages to identify contents of the advertisement e.g. a featured product name a brand name etc. so that it can be associated with a user s ad exposure. In one implementation the AD SURVEY may generate a unique identifier indicative of visual characteristics of the captured ad graphical contents e.g. a matrix representation of sampling of the captured ad image etc. and form a query on an ad database based on the unique identifier. In another implementation the AD SURVEY may adopt software packages similar to but not limited to Google image search and or the like. Further details of advertisement image match may be similar to that described in U.S. Pat. No. 7 565 139 entitled Image Based Search Engine for Mobile Phone with Camera which is herein expressly incorporated by reference.

In one implementation the AD SURVEY may dissect an advertisement identification from the advertisement embedded in the web content e.g. the URL link to determine a product name a brand name and or the like which the user has been exposed to. In further implementations the captured graphical advertisement contents may be tagged with metadata in compliance with formats associated with an advertisement e.g. exif data tags which may include unique advertising identifiers in the software tags in the inter operability tags in the extension name ID extension

In further implementations the AD SURVEY may determine whether a user clicked a URL link comprising media program content e.g. a Youtube link etc. The AD SURVEY may extract an identifier e.g. a web ID etc. to determine the name of the media program. In another implementation the AD SURVEY may obtain excerpts of the media program and determine a name of the media program via an embedded digital signature. In further implementation the AD SURVEY may set time stamp on the user s click on the URL link comprising a media program to record how long the user has been exposed to the media program. Further implementations of the ad identification are discussed in .

In further implementations the AD SURVEY may track a user s browsing history by monitoring a stream of clicks the user has submitted on his mobile device. For example the AD SURVEY may monitor user s clicks to determine a type of the click e.g. usage of media playing visits of a different URL link posting of social media contents usage of an application and or the like. Using an app. The AD SURVEY may then determine advertisement exposure associated with each click e.g. via ad image identification illustrated in .

In another implementation the received data may comprise application information from the user device . The proxy server may ascertain an application inventory list of the user device and or application group sharing information . For example one or more users who are Facebook friends may form a group to share their interested TV watch list and viewing status via AD SURVEY and such information may be captured by the proxy server.

In another implementation the received data may comprise indication of media usage e.g. channel selection atmospherics data etc. the AD SURVEY may determine whether the TV program on the selected channel has been listened watched and or streamed . The AD SURVEY may determine a title of the media program and retrieve ad tags embedded in the media program from a media table to determine user ad exposure information e.g. as discussed in . In further implementations the received data may comprise survey responses social messages sent to the AD SURVEY as further discussed in .

In one implementation the AD SURVEY may generate media analytics report based on the obtained media data including information as to user impressions to a brand name product TV shows etc. e.g. as shown in .

In one implementation the AD SURVEY may provide advertisers solutions to design advertising campaigns as to which type of media to place an ad developing media plans with the optimal mix across media determine the impact of advertising on brand awareness favorability measures intent to buy and actual purchase across media ROI . In another implementation the AD SURVEY may provide advertising measurement solutions using emerging sources of data e.g. media consumption data TV online mobile social etc. shopper data for key categories and or the like.

In one implementation the AD SURVEY may provide clients with insights on campaign effectiveness and recommendations on optimal media allocation using survey questionnaires e.g. as further discussed in based on statistical modeling and regression analysis. In further implementations the impact of each media may be separately analyzed to make recommendation on optimal spend and predict sales based upon survey responses.

In further implementations the AD SURVEY may link different type of data for cross channel analysis. In one implementation the AD SURVEY may create a unified dataset that profiles audiences for TV and online media consumption wherein each viewing source e.g. individual TV set household TV set etc. with viewing and ad exposure information for TV and online is associated with a unique identifier. For example AD SURVEY may adopt direct linkage by getting TV and online data for the same household e.g. via ISP cable provider etc. . For another example the AD SURVEY may segment TV and online data and link using segments e.g. segmented by program category zip code air time etc. . For another example the AD SURVEY may devise and distribute survey questions about TV viewing and linking with the respondents online surfing data.

For digital advertising online and mobile AD SURVEY may classify the advertisements via a hybrid manual automatic process. For example AD SURVEY may adopt a mobile or PC based system using a software meter VPN and or Proxy Server among other technologies to pass along to a staging server the URL of the ad along with the actual file typically a .gif .jpg or .png . For example upon receiving ad data including URLs and associated digital files e.g. media program excerpt files etc. via a network connection the AD SURVEY server may compare the received advertisement data with ad profiles in a database . The filename file size and other data may be compared against an ad database and if the ad already been classified then the new ad exposure event is transmitted to a classification engine classified based on classification rules in the database. Classification rules may include brand and product mentions as well as ad size and other descriptions. If a match is not found then the ad is put in a queue for manual classification by a AD SURVEY representative. For example the AD SURVEY representative may identify the object e.g. a product a brand name etc. that is advertised within the ad.

In one implementation the advertisement may be identified via graphical content match as discussed in . In an alternative implementation the ad identification may be performed via an automated system by which ads that do not match any items in the ad database may be examined automatically by a computer program for clues as to the proper classification. For example when an ad that mentions Acura in the ad image the AD SURVEY may automatically classify the ad as an Acura advertisement. Within implementations the AD SURVEY may perform character recognition procedures e.g. optical character recognition etc. to obtain key terms from advertisement images for advertising exposure identification. Such ad identification may be used for advertising effectiveness measurement. Numerous OCR engines may be adopted such as GOCR Java OCR OmniPage SimpleOCR and or the like.

In one implementation the user may view a list of channel program schedules and may elect to tap on the screen to choose one of the listed channels. In a further implementation the user may select to allow ambient monitoring so that the AD SURVEY may listen in and submit atmospherics data to the AD SURVEY server as discussed at in .

In further implementations the user may click on the Prompts button and view a drop down list of survey questions e.g. as shown in . The survey question may be generated based on the media content the user has been watching as discussed in . Upon the user submitting a response as shown in the user response may be populated as a social media message . In one implementation the user s friends may view the user s activity and likes the user s response commented on the response and or follow the link of the survey and participate in the survey

In further implementations as shown in the user may tap on the Social button and launch a drop down panel for social media inputs . In one implementation the AD SURVEY may generate an automatic message template for the user based on the media ad tags e.g. the user likes an embedded product placement . For another example the user may manually type texts to update his social media status

In further implementations as shown in if the user elects to submit a message on social media indicating he likes the embedded product placement the user s friends may be aware of the product. For example the user s friends may like the post comment on the product . For another example the AD SURVEY may feed a link directing to a merchant site comprising the placed product along with the social media message and the user s friend may follow the link to learn more about the placed product via the social media

In a further implementation the interactive ad may comprise a user rating of the featured product showing beneath the product. In one implementation the user rating may be obtained from historical user rating data social media rating and or the like. In one implementation the user may enter his own rating by tapping on the box

In a further implementation the user may browse the interactive ads e.g. including screen shots from the TV program comprising product placement tags etc. by going to a previous page and or a next page . In further implementations the user may elect to browse interactive ads associated with the TV program in a variety ways. For example the user may elect to view a list of all ads may elect to view by season episode may elect to view by character e.g. products carried by or associated with the character names in the show may elect to view by item category e.g. apparel accessories furniture hair products etc. and or the like. In further implementations the user may initiate a search on desired products . For example if the user is interested in a red hat the character Penny wore in one of the scenes the user may form a query on the embedded ads table based on key terms Penny red hat etc.

When the user tap on the live section the user may view a list of most viewed programs e.g. ranked by registered AD SURVEY users. The user may also see a list of program that the user s social friends are watching and a list of programs the user has selected .

In another implementation the user may configure DVDs via the AD SURVEY. The AD SURVEY may initiate an automatic scan upon user selection and or receive an indication from the user of the DVD brand. Upon indicating the DVD brand the user may test connection with the DVD set to select a DVD type.

In another implementation the user may enter a zip code to configure the TV provider so that the AD SURVEY may provide a list of TV providers for the user to choose.

In one implementation the user may view a social rating of the TV program The Big Bang Theory under its profile. For example the rating may be given by social users of AD SURVEY who has viewed the program and the user may elects to submit his own rating . In a further implementation the user may obtain a list of social watching to see a list of social users e.g. social media users who has allowed AD SURVEY to access their social profiles etc. who is watching the selected TV program.

In another implementation as shown in a user may configure social network connection settings under the settings e.g. see at of AD SURVEY client mobile application. In one implementation the AD SURVEY may send an access request so that a user may view a prompt from his mobile device and may elect allow or disallow the AD SURVEY access attempt . The user may be directed to a Facebook login page wherein Facebook may request user to provide login credentials to verify the permission authorization. For example the user may enter his email address and password to login to Facebook. For another example if the user does not have a Facebook account yet upon tapping on Yes the user may be directed to create a new account. In another implementation if the user s mobile application e.g. an iPhone Facebook app a mobile browser etc. stores user previously entered login credentials the user mobile device may send the login credentials to the social media to proceed with access authorization so that the user may not need to view the login page to manually provide user credentials.

Upon providing Facebook login credentials and verification of Facebook the user may receive a request for permission screen to select to Allow AD SURVEY to access the user s Facebook profile. In further implementations the user may configure access parameters in a similar manner as illustrated in .

In one implementation upon submitting the request the social media platform may request login confirmation . For example the user may be redirected to the social media homepage to login. For another example the user may be presented a pop up window for the social analytics to connect with Facebook e.g. the user may need to provide email and password to login to Facebook.

As shown in upon providing user Facebook credentials the user may configure access scope for Facebook content. For example the user may elect to allow AD SURVEY to access his user profile e.g. the user may select among a list of checkboxes for user name user address user email user phone number work information education information date of birth pages groups networks and or the like. For another example the user may configure the AD SURVEY may access his friends information e.g. the user may allow the AD SURVEY to obtain a number o friends but may not allow the AD SURVEY to access details of the friends list. For another example the user may allow the AD SURVEY to access his wall posts e.g. the user may allow the AD SURVEY to access his post on his own wall including sharing links posted photos status update messages etc. . The user may conditionally allow AD SURVEY to access his post on his friend s wall when the friend allows access to his wall . Similarly the user may conditionally allow AD SURVEY to access the user s likes dislikes when the liked or disliked item owner allows AD SURVEY access as well.

In one implementation as shown in if the user selects TV shows the user may provide information of the TV show by selecting a TV network e.g. CBS at genre e.g. Comedy at show name e.g. The Big Bang Theory at from a drop down list. In another implementation the user may manually enter a name of the TV show to query on a TV show database at AD SURVEY.

In one implementation the user may configure analytics parameters such as social content source e.g. check on Facebook and Twitter time range e.g. between a specified time and present . The user may further select a presentation format e.g. whether to view raw textual comments or a visualized summary e.g. plain format chart plots or table . For example if raw text is selected the user may view a list of Facebook comments and Tweets related to the show The Big Bang Theory. 

In another implementation as shown in if the user elects to view analytics report in a visualized format the summary may be presented in a plain textual format e.g. showing statistical results of the positive neutral and or negative comments. For another example charts plots and a table summary may be presented. In one implementation the analytics summary may be broken down to different categories e.g. the comments for each category CBS The Big Bang Theory Characters Music of the show and or the like.

For example the AD SURVEY may provide a welcome login screen to a user wherein the user may be a AD SURVEY client such as a TV producer an advertiser a merchant and or the like who may be interested to learn their TV audience statistics brand product impressions and or the like.

Upon user login at the AD SURVEY may provide a customized dashboard page e.g. as further illustrated in one implementation at H. The dashboard page may provide an overview of the media analytics results such as generated report types available statistics charts plots and or the like. For example the AD SURVEY may perform analytics to generate advertising reports e.g. advertisement delivery reports etc. audience reports e.g. an audience summary report audience reports by gender reach by age reach reports per day of week reports per hour during a day part etc. .

In one implementation the media analytics dashboard page may provide a plot of total AD SURVEY user sessions based on the user configured AD SURVEY social user group. For example the personal trending data statistics may further comprise plots of number of users number of sessions number of new users median mean session length geographic regions of users and or the like. In another implementation AD SURVEY may provide analysis of AD SURVEY application usage statistics such as a total number of sessions a total number of registered users a median session length per user and or the like. In another implementation the AD SURVEY may provide a summary table showing the study of user selected reporting application Foursquare including audience active reach total visits visits per person total web page views page view per person duration time per person web user gender age and or the like. For example a report on the number of users may summarize the number of users an application e.g. Foursquare has had over period of tracking to indicate whether the number is growing or declining. The report may also analyze user sessions in different scenarios e.g. whether by a single user . For example when a mobile site has been visited for 50 times but 30 of those times it was from the same user versus another month the number visits from different users was 25 the number of users may not be considered as increased.

For another example a report on number of sessions may include number of sessions by all users within the last calendar month which may be tracked on a monthly trending basis to indicate how often an application site was seen by all users. For another example a report on number of new users may show the number of new users for the last calendar month using the application or mobile site. For another example the median mean session length may indicate the time spent on application site. For another example the geo graphic region of users may show a geographical distribution of users engaging or visiting the application advertisement

For example in one implementation for a specified TV show e.g. Big Bang Theory at CBS the profile measure may provide social data metrics with regard to social groups such as percentage of influencers in a social group e.g. social users whose watching recommendations have been followed by other social users etc. percentage of users who engage in watching the show percentage of users who is distracted from watching the show e.g. via atmospherics analysis as illustrated in number of friends who have engaged in the TV watching number of posts per week a number of brand pages the social group has followed number of photos the social group has posted and or the like. In further implementations the AD SURVEY may analyze the social media content to provide liking measures such as the most positively commented to brand pages music pages TV show pages and or the like brand measures such as the top to brands top 5 products mentioned within a social group and or the like the top TV shows watched and or the like.

Typically users which may be people and or other systems may engage information technology systems e.g. computers to facilitate information processing. In turn computers employ processors to process information such processors may be referred to as central processing units CPU . One form of processor is referred to as a microprocessor. CPUs use communicative circuits to carry and pass encoded e.g. binary signals acting as instructions to bring about various operations. These instructions may be operational and or data instructions containing and or referencing other instructions and data in various processor accessible and operable areas of memory e.g. registers cache memory random access memory etc. . Such communicative instructions may be stored and or transmitted in batches e.g. batches of instructions as programs and or data components to facilitate desired operations. These stored instruction codes e.g. programs may engage the CPU circuit components and other motherboard and or system components to perform desired operations. One type of program is a computer operating system which may be executed by CPU on a computer the operating system enables and facilitates users to access and operate computer information technology and resources. Some resources that may be employed in information technology systems include input and output mechanisms through which data may pass into and out of a computer memory storage into which data may be saved and processors by which information may be processed. These information technology systems may be used to collect data for later retrieval analysis and manipulation which may be facilitated through a database program. These information technology systems provide interfaces that allow users to access and operate various system components.

In one embodiment the AD SURVEY controller may be connected to and or communicate with entities such as but not limited to one or more users from user input devices peripheral devices an optional cryptographic processor device and or a communications network .

Networks are commonly thought to comprise the interconnection and interoperation of clients servers and intermediary nodes in a graph topology. It should be noted that the term server as used throughout this application refers generally to a computer other device program or combination thereof that processes and responds to the requests of remote users across a communications network. Servers serve their information to requesting clients. The term client as used herein refers generally to a computer program other device user and or combination thereof that is capable of processing and making requests and obtaining and processing any responses from servers across a communications network. A computer other device program or combination thereof that facilitates processes information and requests and or furthers the passage of information from a source user to a destination user is commonly referred to as a node. Networks are generally thought to facilitate the transfer of information from source points to destinations. A node specifically tasked with furthering the passage of information from a source to a destination is commonly called a router. There are many forms of networks such as Local Area Networks LANs Pico networks Wide Area Networks WANs Wireless Networks WLANs etc. For example the Internet is generally accepted as being an interconnection of a multitude of networks whereby remote clients and servers may access and interoperate with one another.

The AD SURVEY controller may be based on computer systems that may comprise but are not limited to components such as a computer systemization connected to memory .

A computer systemization may comprise a clock central processing unit CPU s and or processor s these terms are used interchangeable throughout the disclosure unless noted to the contrary a memory e.g. a read only memory ROM a random access memory RAM etc. and or an interface bus and most frequently although not necessarily are all interconnected and or communicating through a system bus on one or more mother board s having conductive and or otherwise transportive circuit pathways through which instructions e.g. binary encoded signals may travel to effectuate communications operations storage etc. The computer systemization may be connected to a power source e.g. optionally the power source may be internal. Optionally a cryptographic processor and or transceivers e.g. ICs may be connected to the system bus. In another embodiment the cryptographic processor and or transceivers may be connected as either internal and or external peripheral devices via the interface bus I O. In turn the transceivers may be connected to antenna s thereby effectuating wireless transmission and reception of various communication and or sensor protocols for example the antenna s may connect to a Texas Instruments WiLink WL1283 transceiver chip e.g. providing 802.11n Bluetooth 5.0 FM global positioning system GPS thereby allowing AD SURVEY controller to determine its location Broadcom BCM4329FKUBG transceiver chip e.g. providing 802.11n Bluetooth 2.1 EDR FM etc. a Broadcom BCM4750IUB8 receiver chip e.g. GPS an Infineon Technologies X Gold 618 PMB9800 e.g. providing 2G 3G HSDPA HSUPA communications and or the like. The system clock typically has a crystal oscillator and generates a base signal through the computer systemization s circuit pathways. The clock is typically coupled to the system bus and various clock multipliers that may increase or decrease the base operating frequency for other components interconnected in the computer systemization. The clock and various components in a computer systemization drive signals embodying information throughout the system. Such transmission and reception of instructions embodying information throughout a computer systemization may be commonly referred to as communications. These communicative instructions may further be transmitted received and the cause of return and or reply communications beyond the instant computer systemization to communications networks input devices other computer systemizations peripheral devices and or the like. It should be understood that in alternative embodiments any of the above components may be connected directly to one another connected to the CPU and or organized in numerous variations employed as exemplified by various computer systems.

The CPU comprises at least one high speed data processor adequate to execute program components for executing user and or system generated requests. Often the processors themselves may incorporate various specialized processing units such as but not limited to integrated system bus controllers memory management control units floating point units and even specialized processing sub units like graphics processing units digital signal processing units and or the like. Additionally processors may include internal fast access addressable memory and be capable of mapping and addressing memory beyond the processor itself internal memory may include but is not limited to fast registers various levels of cache memory e.g. level 1 2 5 etc. RAM etc. The processor may access this memory through the use of a memory address space that is accessible via instruction address which the processor can construct and decode allowing it to access a circuit path to a specific memory address space having a memory state. The CPU may be a microprocessor such as AMD s Athlon Duron and or Opteron ARM s application embedded and secure processors IBM and or Motorola s DragonBall and PowerPC IBM s and Sony s Cell processor Intel s Celeron Core 2 Duo Itanium Pentium Xeon and or XScale and or the like processor s . The CPU interacts with memory through instruction passing through conductive and or transportive conduits e.g. printed electronic and or optic circuits to execute stored instructions i.e. program code according to conventional data processing techniques. Such instruction passing facilitates communication within the AD SURVEY controller and beyond through various interfaces. Should processing requirements dictate a greater amount speed and or capacity distributed processors e.g. Distributed AD SURVEY mainframe multi core parallel and or super computer architectures may similarly be employed. Alternatively should deployment requirements dictate greater portability smaller Personal Digital Assistants PDAs may be employed.

Depending on the particular implementation features of the AD SURVEY may be achieved by implementing a microcontroller such as CAST s R8051XC2 microcontroller Intel s MCS 51 i.e. 8051 microcontroller and or the like. Also to implement certain features of the AD SURVEY some feature implementations may rely on embedded components such as Application Specific Integrated Circuit ASIC Digital Signal Processing DSP Field Programmable Gate Array FPGA and or the like embedded technology. For example any of the AD SURVEY component collection distributed or otherwise and or features may be implemented via the microprocessor and or via embedded components e.g. via ASIC coprocessor DSP FPGA and or the like. Alternately some implementations of the AD SURVEY may be implemented with embedded components that are configured and used to achieve a variety of features or signal processing.

Depending on the particular implementation the embedded components may include software solutions hardware solutions and or some combination of both hardware software solutions. For example AD SURVEY features discussed herein may be achieved through implementing FPGAs which are a semiconductor devices containing programmable logic components called logic blocks and programmable interconnects such as the high performance FPGA Virtex series and or the low cost Spartan series manufactured by Xilinx. Logic blocks and interconnects can be programmed by the customer or designer after the FPGA is manufactured to implement any of the AD SURVEY features. A hierarchy of programmable interconnects allow logic blocks to be interconnected as needed by the AD SURVEY system designer administrator somewhat like a one chip programmable breadboard. An FPGA s logic blocks can be programmed to perform the operation of basic logic gates such as AND and XOR or more complex combinational operators such as decoders or mathematical operations. In most FPGAs the logic blocks also include memory elements which may be circuit flip flops or more complete blocks of memory. In some circumstances the AD SURVEY may be developed on regular FPGAs and then migrated into a fixed version that more resembles ASIC implementations. Alternate or coordinating implementations may migrate AD SURVEY controller features to a final ASIC instead of or in addition to FPGAs. Depending on the implementation all of the aforementioned embedded components and microprocessors may be considered the CPU and or processor for the AD SURVEY.

The power source may be of any standard form for powering small electronic circuit board devices such as the following power cells alkaline lithium hydride lithium ion lithium polymer nickel cadmium solar cells and or the like. Other types of AC or DC power sources may be used as well. In the case of solar cells in one embodiment the case provides an aperture through which the solar cell may capture photonic energy. The power cell is connected to at least one of the interconnected subsequent components of the AD SURVEY thereby providing an electric current to all subsequent components. In one example the power source is connected to the system bus component . In an alternative embodiment an outside power source is provided through a connection across the I O interface. For example a USB and or IEEE 1394 connection carries both data and power across the connection and is therefore a suitable source of power.

Interface bus ses may accept connect and or communicate to a number of interface adapters conventionally although not necessarily in the form of adapter cards such as but not limited to input output interfaces I O storage interfaces network interfaces and or the like. Optionally cryptographic processor interfaces similarly may be connected to the interface bus. The interface bus provides for the communications of interface adapters with one another as well as with other components of the computer systemization. Interface adapters are adapted for a compatible interface bus. Interface adapters conventionally connect to the interface bus via a slot architecture. Conventional slot architectures may be employed such as but not limited to Accelerated Graphics Port AGP Card Bus Extended Industry Standard Architecture E ISA Micro Channel Architecture MCA NuBus Peripheral Component Interconnect Extended PCI X PCI Express Personal Computer Memory Card International Association PCMCIA and or the like.

Storage interfaces may accept communicate and or connect to a number of storage devices such as but not limited to storage devices removable disc devices and or the like. Storage interfaces may employ connection protocols such as but not limited to Ultra Serial Advanced Technology Attachment Packet Interface Ultra Serial ATA PI Enhanced Integrated Drive Electronics E IDE Institute of Electrical and Electronics Engineers IEEE 1394 fiber channel Small Computer Systems Interface SCSI Universal Serial Bus USB and or the like.

Network interfaces may accept communicate and or connect to a communications network . Through a communications network the AD SURVEY controller is accessible through remote clients e.g. computers with web browsers by users . Network interfaces may employ connection protocols such as but not limited to direct connect Ethernet thick thin twisted pair 10 100 1000 Base T and or the like Token Ring wireless connection such as IEEE 802.11a x and or the like. Should processing requirements dictate a greater amount speed and or capacity distributed network controllers e.g. Distributed AD SURVEY architectures may similarly be employed to pool load balance and or otherwise increase the communicative bandwidth required by the AD SURVEY controller. A communications network may be any one and or the combination of the following a direct interconnection the Internet a Local Area Network LAN a Metropolitan Area Network MAN an Operating Missions as Nodes on the Internet OMNI a secured custom connection a Wide Area Network WAN a wireless network e.g. employing protocols such as but not limited to a Wireless Application Protocol WAP I mode and or the like and or the like. A network interface may be regarded as a specialized form of an input output interface. Further multiple network interfaces may be used to engage with various communications network types . For example multiple network interfaces may be employed to allow for the communication over broadcast multicast and or unicast networks.

Input Output interfaces I O may accept communicate and or connect to user input devices peripheral devices cryptographic processor devices and or the like. I O may employ connection protocols such as but not limited to audio analog digital monaural RCA stereo and or the like data Apple Desktop Bus ADB IEEE 1394a b serial universal serial bus USB infrared joystick keyboard midi optical PC AT PS 2 parallel radio video interface Apple Desktop Connector ADC BNC coaxial component composite digital Digital Visual Interface DVI high definition multimedia interface HDMI RCA RF antennae S Video VGA and or the like wireless transceivers 802.11a b g n x Bluetooth cellular e.g. code division multiple access CDMA high speed packet access HSPA high speed downlink packet access HSDPA global system for mobile communications GSM long term evolution LTE WiMax etc. and or the like. One typical output device may include a video display which typically comprises a Cathode Ray Tube CRT or Liquid Crystal Display LCD based monitor with an interface e.g. DVI circuitry and cable that accepts signals from a video interface may be used. The video interface composites information generated by a computer systemization and generates video signals based on the composited information in a video memory frame. Another output device is a TV set which accepts signals from a video interface. Typically the video interface provides the composited video information through a video connection interface that accepts a video display interface e.g. an RCA composite video connector accepting an RCA composite video cable a DVI connector accepting a DVI display cable etc. .

User input devices often are a type of peripheral device see below and may include card readers dongles finger print readers gloves graphics tablets joysticks keyboards microphones mouse mice remote controls retina readers touch screens e.g. capacitive resistive etc. trackballs trackpads sensors e.g. accelerometers ambient light GPS gyroscopes proximity etc. styluses and or the like.

Peripheral devices may be connected and or communicate to I O and or other facilities of the like such as network interfaces storage interfaces directly to the interface bus system bus the CPU and or the like. Peripheral devices may be external internal and or part of the AD SURVEY controller. Peripheral devices may include antenna audio devices e.g. line in line out microphone input speakers etc. cameras e.g. still video webcam etc. dongles e.g. for copy protection ensuring secure transactions with a digital signature and or the like external processors for added capabilities e.g. crypto devices force feedback devices e.g. vibrating motors network interfaces printers scanners storage devices transceivers e.g. cellular GPS etc. video devices e.g. goggles monitors etc. video sources visors and or the like. Peripheral devices often include types of input devices e.g. cameras .

It should be noted that although user input devices and peripheral devices may be employed the AD SURVEY controller may be embodied as an embedded dedicated and or monitor less i.e. headless device wherein access would be provided over a network interface connection.

Cryptographic units such as but not limited to microcontrollers processors interfaces and or devices may be attached and or communicate with the AD SURVEY controller. A MC68HC16 microcontroller manufactured by Motorola Inc. may be used for and or within cryptographic units. The MC68HC16 microcontroller utilizes a 16 bit multiply and accumulate instruction in the MHz configuration and requires less than one second to perform a 512 bit RSA private key operation. Cryptographic units support the authentication of communications from interacting agents as well as allowing for anonymous transactions. Cryptographic units may also be configured as part of the CPU. Equivalent microcontrollers and or processors may also be used. Other commercially available specialized cryptographic processors include Broadcom s CryptoNetX and other Security Processors nCipher s nShield SafeNet s Luna PCI e.g. 7100 series Semaphore Communications 40 MHz Roadrunner 184 Sun s Cryptographic Accelerators e.g. Accelerator 6000 PCIe Board Accelerator 500 Daughtercard Via Nano Processor e.g. L2100 L2200 U2400 line which is capable of performing 500 MB s of cryptographic instructions VLSI Technology s 53 MHz 6868 and or the like.

Generally any mechanization and or embodiment allowing a processor to affect the storage and or retrieval of information is regarded as memory . However memory is a fungible technology and resource thus any number of memory embodiments may be employed in lieu of or in concert with one another. It is to be understood that the AD SURVEY controller and or a computer systemization may employ various forms of memory . For example a computer systemization may be configured wherein the operation of on chip CPU memory e.g. registers RAM ROM and any other storage devices are provided by a paper punch tape or paper punch card mechanism however such an embodiment would result in an extremely slow rate of operation. In a typical configuration memory may include ROM RAM and a storage device . A storage device may be any conventional computer system storage. Storage devices may include a drum a fixed and or removable magnetic disk drive a magneto optical drive an optical drive i.e. Blueray CD ROM RAM Recordable R ReWritable RW DVD R RW HD DVD R RW etc. an array of devices e.g. Redundant Array of Independent Disks RAID solid state memory devices USB memory solid state drives SSD etc. other processor readable storage mediums and or other devices of the like. Thus a computer systemization generally requires and makes use of memory.

The memory may contain a collection of program and or database components and or data such as but not limited to operating system component s operating system information server component s information server user interface component s user interface Web browser component s Web browser database s mail server component s mail client component s cryptographic server component s cryptographic server the AD SURVEY component s and or the like i.e. collectively a component collection . These components may be stored and accessed from the storage devices and or from storage devices accessible through an interface bus. Although non conventional program components such as those in the component collection typically are stored in a local storage device they may also be loaded and or stored in memory such as peripheral devices RAM remote storage facilities through a communications network ROM various forms of memory and or the like.

The operating system component is an executable program component facilitating the operation of the AD SURVEY controller. Typically the operating system facilitates access of I O network interfaces peripheral devices storage devices and or the like. The operating system may be a highly fault tolerant scalable and secure system such as Apple Macintosh OS X Server AT T Plan 7 Be OS Unix and Unix like system distributions such as AT T s UNIX Berkley Software Distribution BSD variations such as FreeBSD NetBSD OpenBSD and or the like Linux distributions such as Red Hat Ubuntu and or the like and or the like operating systems. However more limited and or less secure operating systems also may be employed such as Apple Macintosh OS IBM OS 2 Microsoft DOS Microsoft Windows 2000 2003 3.1 95 98 CE Millennium NT Vista XP Server Palm OS and or the like. An operating system may communicate to and or with other components in a component collection including itself and or the like. Most frequently the operating system communicates with other program components user interfaces and or the like. For example the operating system may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses. The operating system once executed by the CPU may facilitate the interaction with communications networks data I O peripheral devices program components memory user input devices and or the like. The operating system may provide communications protocols that allow the AD SURVEY controller to communicate with other entities through a communications network . Various communication protocols may be used by the AD SURVEY controller as a subcarrier transport mechanism for interaction such as but not limited to multicast TCP IP UDP unicast and or the like.

An information server component is a stored program component that is executed by a CPU. The information server may be a conventional Internet information server such as but not limited to Apache Software Foundation s Apache Microsoft s Internet Information Server and or the like. The information server may allow for the execution of program components through facilities such as Active Server Page ASP ActiveX ANSI Objective C C and or .NET Common Gateway Interface CGI scripts dynamic D hypertext markup language HTML FLASH Java JavaScript Practical Extraction Report Language PERL Hypertext Pre Processor PHP pipes Python wireless application protocol WAP WebObjects and or the like. The information server may support secure communications protocols such as but not limited to File Transfer Protocol FTP HyperText Transfer Protocol HTTP Secure Hypertext Transfer Protocol HTTPS Secure Socket Layer SSL messaging protocols e.g. America Online AOL Instant Messenger AIM Application Exchange APEX ICQ Internet Relay Chat IRC Microsoft Network MSN Messenger Service Presence and Instant Messaging Protocol PRIM Internet Engineering Task Force s IETF s Session Initiation Protocol SIP SIP for Instant Messaging and Presence Leveraging Extensions SIMPLE open XML based Extensible Messaging and Presence Protocol XMPP i.e. Jabber or Open Mobile Alliance s OMA s Instant Messaging and Presence Service IMPS Yahoo Instant Messenger Service and or the like. The information server provides results in the form of Web pages to Web browsers and allows for the manipulated generation of the Web pages through interaction with other program components. After a Domain Name System DNS resolution portion of an HTTP request is resolved to a particular information server the information server resolves requests for information at specified locations on the AD SURVEY controller based on the remainder of the HTTP request. For example a request such as http 123.124.125.126 myInformation.html might have the IP portion of the request 123.124.125.126 resolved by a DNS server to an information server at that IP address that information server might in turn further parse the http request for the myInformation.html portion of the request and resolve it to a location in memory containing the information myInformation.html. Additionally other information serving protocols may be employed across various ports e.g. FTP communications across port and or the like. An information server may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the information server communicates with the AD SURVEY database operating systems other program components user interfaces Web browsers and or the like.

Access to the AD SURVEY database may be achieved through a number of database bridge mechanisms such as through scripting languages as enumerated below e.g. CGI and through inter application communication channels as enumerated below e.g. CORBA WebObjects etc. . Any data requests through a Web browser are parsed through the bridge mechanism into appropriate grammars as required by the AD SURVEY. In one embodiment the information server would provide a Web form accessible by a Web browser. Entries made into supplied fields in the Web form are tagged as having been entered into the particular fields and parsed as such. The entered terms are then passed along with the field tags which act to instruct the parser to generate queries directed to appropriate tables and or fields. In one embodiment the parser may generate queries in standard SQL by instantiating a search string with the proper join select commands based on the tagged text entries wherein the resulting command is provided over the bridge mechanism to the AD SURVEY as a query. Upon generating query results from the query the results are passed over the bridge mechanism and may be parsed for formatting and generation of a new results Web page by the bridge mechanism. Such a new results Web page is then provided to the information server which may supply it to the requesting Web browser.

Also an information server may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses.

Computer interfaces in some respects are similar to automobile operation interfaces. Automobile operation interface elements such as steering wheels gearshifts and speedometers facilitate the access operation and display of automobile resources and status. Computer interaction interface elements such as check boxes cursors menus scrollers and windows collectively and commonly referred to as widgets similarly facilitate the access capabilities operation and display of data and computer hardware and operating system resources and status. Operation interfaces are commonly called user interfaces. Graphical user interfaces GUIs such as the Apple Macintosh Operating System s Aqua IBM s OS 2 Microsoft s Windows 2000 2003 3.1 95 98 CE Millennium NT XP Vista 7 i.e. Aero Unix s X Windows e.g. which may include additional Unix graphic interface libraries and layers such as K Desktop Environment KDE mythTV and GNU Network Object Model Environment GNOME web interface libraries e.g. ActiveX AJAX D HTML FLASH Java JavaScript etc. interface libraries such as but not limited to Dojo jQuery UI MooTools Prototype script.aculo.us SWFObject Yahoo User Interface any of which may be used and provide a baseline and means of accessing and displaying information graphically to users.

A user interface component is a stored program component that is executed by a CPU. The user interface may be a conventional graphic user interface as provided by with and or atop operating systems and or operating environments such as already discussed. The user interface may allow for the display execution interaction manipulation and or operation of program components and or system facilities through textual and or graphical facilities. The user interface provides a facility through which users may affect interact and or operate a computer system. A user interface may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the user interface communicates with operating systems other program components and or the like. The user interface may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses.

A Web browser component is a stored program component that is executed by a CPU. The Web browser may be a conventional hypertext viewing application such as Microsoft Internet Explorer or Netscape Navigator. Secure Web browsing may be supplied with 128 bit or greater encryption by way of HTTPS SSL and or the like. Web browsers allowing for the execution of program components through facilities such as ActiveX AJAX D HTML FLASH Java JavaScript web browser plug in APIs e.g. FireFox Safari Plug in and or the like APIs and or the like. Web browsers and like information access tools may be integrated into PDAs cellular telephones and or other mobile devices. A Web browser may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the Web browser communicates with information servers operating systems integrated program components e.g. plug ins and or the like e.g. it may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses. Also in place of a Web browser and information server a combined application may be developed to perform similar operations of both. The combined application would similarly affect the obtaining and the provision of information to users user agents and or the like from the AD SURVEY enabled nodes. The combined application may be nugatory on systems employing standard Web browsers.

A mail server component is a stored program component that is executed by a CPU . The mail server may be a conventional Internet mail server such as but not limited to sendmail Microsoft Exchange and or the like. The mail server may allow for the execution of program components through facilities such as ASP ActiveX ANSI Objective C C and or .NET CGI scripts Java JavaScript PERL PHP pipes Python WebObjects and or the like. The mail server may support communications protocols such as but not limited to Internet message access protocol IMAP Messaging Application Programming Interface MAPI Microsoft Exchange post office protocol POP3 simple mail transfer protocol SMTP and or the like. The mail server can route forward and process incoming and outgoing mail messages that have been sent relayed and or otherwise traversing through and or to the AD SURVEY.

Access to the AD SURVEY mail may be achieved through a number of APIs offered by the individual Web server components and or the operating system.

Also a mail server may contain communicate generate obtain and or provide program component system user and or data communications requests information and or responses.

A mail client component is a stored program component that is executed by a CPU . The mail client may be a conventional mail viewing application such as Apple Mail Microsoft Entourage Microsoft Outlook Microsoft Outlook Express Mozilla Thunderbird and or the like. Mail clients may support a number of transfer protocols such as IMAP Microsoft Exchange POP3 SMTP and or the like. A mail client may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the mail client communicates with mail servers operating systems other mail clients and or the like e.g. it may contain communicate generate obtain and or provide program component system user and or data communications requests information and or responses. Generally the mail client provides a facility to compose and transmit electronic mail messages.

A cryptographic server component is a stored program component that is executed by a CPU cryptographic processor cryptographic processor interface cryptographic processor device and or the like. Cryptographic processor interfaces may allow for expedition of encryption and or decryption requests by the cryptographic component however the cryptographic component alternatively may run on a conventional CPU. The cryptographic component allows for the encryption and or decryption of provided data. The cryptographic component allows for both symmetric and asymmetric e.g. Pretty Good Protection PGP encryption and or decryption. The cryptographic component may employ cryptographic techniques such as but not limited to digital certificates e.g. X.509 authentication framework digital signatures dual signatures enveloping password access protection public key management and or the like. The cryptographic component may facilitate numerous encryption and or decryption security protocols such as but not limited to checksum Data Encryption Standard DES Elliptical Curve Encryption ECC International Data Encryption Algorithm IDEA Message Digest 5 MD5 which is a one way hash operation passwords Rivest Cipher RC5 Rijndael RSA which is an Internet encryption and authentication system that uses an algorithm developed in 1977 by Ron Rivest Adi Shamir and Leonard Adleman Secure Hash Algorithm SHA Secure Socket Layer SSL Secure Hypertext Transfer Protocol HTTPS and or the like. Employing such encryption security protocols the AD SURVEY may encrypt all incoming and or outgoing communications and may serve as node within a virtual private network VPN with a wider communications network. The cryptographic component facilitates the process of security authorization whereby access to a resource is inhibited by a security protocol wherein the cryptographic component effects authorized access to the secured resource. In addition the cryptographic component may provide unique identifiers of content e.g. employing and MD5 hash to obtain a unique signature for an digital audio file. A cryptographic component may communicate to and or with other components in a component collection including itself and or facilities of the like. The cryptographic component supports encryption schemes allowing for the secure transmission of information across a communications network to enable the AD SURVEY component to engage in secure transactions if so desired. The cryptographic component facilitates the secure accessing of resources on the AD SURVEY and facilitates the access of secured resources on remote systems i.e. it may act as a client and or server of secured resources. Most frequently the cryptographic component communicates with information servers operating systems other program components and or the like. The cryptographic component may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses.

The AD SURVEY database component may be embodied in a database and its stored data. The database is a stored program component which is executed by the CPU the stored program component portion configuring the CPU to process the stored data. The database may be a conventional fault tolerant relational scalable secure database such as Oracle or Sybase. Relational databases are an extension of a flat file. Relational databases consist of a series of related tables. The tables are interconnected via a key field. Use of the key field allows the combination of the tables by indexing against the key field i.e. the key fields act as dimensional pivot points for combining information from various tables. Relationships generally identify links maintained between tables by matching primary keys. Primary keys represent fields that uniquely identify the rows of a table in a relational database. More precisely they uniquely identify rows of a table on the one side of a one to many relationship.

Alternatively the AD SURVEY database may be implemented using various standard data structures such as an array hash linked list struct structured text file e.g. XML table and or the like. Such data structures may be stored in memory and or in structured files. In another alternative an object oriented database may be used such as Frontier ObjectStore Poet Zope and or the like. Object databases can include a number of object collections that are grouped and or linked together by common attributes they may be related to other object collections by some common attributes. Object oriented databases perform similarly to relational databases with the exception that objects are not just pieces of data but may have other types of capabilities encapsulated within a given object. If the AD SURVEY database is implemented as a data structure the use of the AD SURVEY database may be integrated into another component such as the AD SURVEY component . Also the database may be implemented as a mix of data structures objects and relational structures. Databases may be consolidated and or distributed in countless variations through standard data processing techniques. Portions of databases e.g. tables may be exported and or imported and thus decentralized and or integrated.

In one embodiment the database component includes several tables . A user accounts table includes fields such as but not limited to a UserID UserName UserPassword UserAddress UserDeviceID UserViewingHistory UserRating UserPreference and or the like. The User table may support and or track multiple entity accounts on a AD SURVEY. A Real Time TV table includes fields such as but not limited to TVChannelID TVChannelName TVChannelLogo TVChannelAirTime TVChannelProgram TVChannelAd and or the like. A Media Program table includes fields such as MediaID MediaName MediaLength MediaBrand MediaTimeTag MediaAd MediaAdSponsor MediaAirTime MediaChannelID and or the like. A Survey Question table includes fields such as QuestionID QuestionCategory QuestionAdID QuestionDescription QuestionResponse QuestionMediaID QuestionMediaTimeTag QuestionUserID and or the like. An Ad table includes fields such as but not limited to AdID AdMerchant AdFormat AdProduct AdText AdTimeTag AdMediaID AdChannelID adAudiosignature and or the like. An Atmospherics table includes fields such as but not limited to AtmosID AtmosType AtmosTimestamp AtmosUserID AtmosDeviceID AtmosPhotoID AtmosGPS AtmosMediaID AtmosChannelID and or the like. A User Device table includes fields such as but not limited to DeviceID DeviceType DeviceHardwareID DeviceMAC DeviceAppInventory and or the like. A Reports table includes fields such as but not limited to ReportID ReportTimePeriod ReportMediaID ReportChannelID ReportAdID ReportType ReportUserRating ReportAdEffect and or the like. A social content table includes fields such as but not limited to SocialID SocialName SocialUserID SocialTokenID SocialUserID SocialSource SocialContent SocialTimeStamp and or the like. A Taxonomy table includes fields such as but not limited to TaxpID TaxoName TaxoProducType TaxoKeyWords TaxoTreeNode TaxoLevel TaxoLabels and or the like. A User Toaken table includes fields such as but not limited to TokenID TokenUserID TokenSociaID TokenSocialSource TokenNumber TokenFile and or the like. An Analytics Weight Scores table includes fields such as but not limited to ScoreID ScoreName ScoreFactorAttribute ScoreWeight ScoreDescription ScoreIndication and or the like.

In one embodiment the AD SURVEY database may interact with other database systems. For example employing a distributed database system queries and data access by search AD SURVEY component may treat the combination of the AD SURVEY database an integrated data security layer database as a single database entity.

In one embodiment user programs may contain various user interface primitives which may serve to update the AD SURVEY. Also various accounts may require custom database tables depending upon the environments and the types of clients the AD SURVEY may need to serve. It should be noted that any unique fields may be designated as a key field throughout. In an alternative embodiment these tables have been decentralized into their own databases and their respective database controllers i.e. individual database controllers for each of the above tables . Employing standard data processing techniques one may further distribute the databases over several computer systemizations and or storage devices. Similarly configurations of the decentralized database controllers may be varied by consolidating and or distributing the various database components . The AD SURVEY may be configured to keep track of various settings inputs and parameters via database controllers.

The AD SURVEY database may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the AD SURVEY database communicates with the AD SURVEY component other program components and or the like. The database may contain retain and provide information regarding other nodes and data.

The AD SURVEY component is a stored program component that is executed by a CPU. In one embodiment the AD SURVEY component incorporates any and or all combinations of the aspects of the AD SURVEY that was discussed in the previous figures. As such the AD SURVEY affects accessing obtaining and the provision of information services transactions and or the like across various communications networks.

The AD SURVEY transforms TV program schedule listing information and user channel selection via AD SURVEY components such as real time TV ad survey synchronization atmospherics analysis audience statistics analysis social media connection media analytics and or the like into TV audience viewing data and ad effects data.

The AD SURVEY component facilitates access of information between nodes may be developed by employing standard development tools and languages such as but not limited to Apache components Assembly ActiveX binary executables ANSI Objective C C and or .NET database adapters CGI scripts Java JavaScript mapping tools procedural and object oriented development tools PERL PHP Python shell scripts SQL commands web application server extensions web development environments and libraries e.g. Microsoft s ActiveX Adobe AIR FLEX FLASH AJAX D HTML Dojo Java JavaScript jQuery UI MooTools Prototype script.aculo.us Simple Object Access Protocol SOAP SWFObject Yahoo User Interface and or the like WebObjects and or the like. In one embodiment the AD SURVEY server employs a cryptographic server to encrypt and decrypt communications. The AD SURVEY component may communicate to and or with other components in a component collection including itself and or facilities of the like. Most frequently the AD SURVEY component communicates with the AD SURVEY database operating systems other program components and or the like. The AD SURVEY may contain communicate generate obtain and or provide program component system user and or data communications requests and or responses.

The structure and or operation of any of the AD SURVEY node controller components may be combined consolidated and or distributed in any number of ways to facilitate development and or deployment. Similarly the component collection may be combined in any number of ways to facilitate deployment and or development. To accomplish this one may integrate the components into a common code base or in a facility that can dynamically load the components on demand in an integrated fashion.

The component collection may be consolidated and or distributed in countless variations through standard data processing and or development techniques. Multiple instances of any one of the program components in the program component collection may be instantiated on a single node and or across numerous nodes to improve performance through load balancing and or data processing techniques. Furthermore single instances may also be distributed across multiple controllers and or storage devices e.g. databases. All program component instances and controllers working in concert may do so through standard data processing communication techniques.

The configuration of the AD SURVEY controller may depend on the context of system deployment. Factors such as but not limited to the budget capacity location and or use of the underlying hardware resources may affect deployment requirements and configuration. Regardless of if the configuration results in more consolidated and or integrated program components results in a more distributed series of program components and or results in some combination between a consolidated and distributed configuration data may be communicated obtained and or provided. Instances of components consolidated into a common code base from the program component collection may communicate obtain and or provide data. This may be accomplished through intra application data processing communication techniques such as but not limited to data referencing e.g. pointers internal messaging object instance variable communication shared memory space variable passing and or the like.

If component collection components are discrete separate and or external to one another then communicating obtaining and or providing data with and or to other component components may be accomplished through inter application data processing communication techniques such as but not limited to Application Program Interfaces API information passage distributed Component Object Model D COM Distributed Object Linking and Embedding D OLE and or the like Common Object Request Broker Architecture CORBA Jini local and remote application program interfaces JavaScript Object Notation JSON Remote Method Invocation RMI SOAP process pipes shared files and or the like. Messages sent between discrete component components for inter application communication or within memory spaces of a singular component for intra application communication may be facilitated through the creation and parsing of a grammar. A grammar may be developed by using development tools such as lex yacc XML and or the like which allow for grammar generation and parsing capabilities which in turn may form the basis of communication messages within and between components.

where Value1 is discerned as being a parameter because http is part of the grammar syntax and what follows is considered part of the post value. Similarly with such a grammar a variable Value1 may be inserted into an http post command and then sent. The grammar syntax itself may be presented as structured data that is interpreted and or otherwise used to generate the parsing mechanism e.g. a syntax description text file as processed by lex yacc etc. . Also once the parsing mechanism is generated and or instantiated it itself may process and or parse structured data such as but not limited to character e.g. tab delineated text HTML structured text streams XML and or the like structured data. In another embodiment inter application data processing protocols themselves may have integrated and or readily available parsers e.g. JSON SOAP and or like parsers that may be employed to parse e.g. communications data. Further the parsing grammar may be used beyond message parsing but may also be used to parse databases data collections data stores structured data and or the like. Again the desired configuration may depend upon the context environment and requirements of system deployment.

For example in some implementations the AD SURVEY controller may be executing a PHP script implementing a Secure Sockets Layer SSL socket server via the information server which listens to incoming communications on a server port to which a client may send data e.g. data encoded in JSON format. Upon identifying an incoming communication the PHP script may read the incoming message from the client device parse the received JSON encoded text data to extract information from the JSON encoded text data into PHP script variables and store the data e.g. client identifying information etc. and or extracted information in a relational database accessible using the Structured Query Language SQL . An exemplary listing written substantially in the form of PHP SQL commands to accept JSON encoded input data from a client device via a SSL connection parse the data to extract variables and store the data to a database is provided below 

Also the following resources may be used to provide example embodiments regarding SOAP parser implementation 

providing the obtained TV program schedule listing data to a general purpose user mobile device communicatively coupled to an infrared communication component 

determining whether the received user media program selection message indicates a user watching event 

determining a user watching time length associated with the user selected channel when the received user media program selection message is determined to indicate the user watching event and

generating and storing a user watching event log file including the user selected channel and the determined user watching time length.

filtering the received user media program selection message when the received user media program selection message is determined not to indicate a user watching event.

3. The method of embodiment 1 wherein the general purpose user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer

4. The method of embodiment 1 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

5. The method of embodiment 1 wherein the general purpose user mobile device transmits a TV remote channel selection indication to a TV set top box via the infrared plug in component.

6. The method of embodiment 1 wherein the TV remote channel selection message comprises a non live media program selection message.

7. The method of embodiment 1 wherein the non live media program selection message comprises any of a DVD control message a TiVo control message and an on demand media control message.

8. The method of embodiment 1 wherein the determining whether the received user media program selection message indicates a user watching event comprises 

9. The method of embodiment 1 wherein the determining a user watching time length comprises determining whether a time lapse between two consecutively received program selection messages exceeds a capping threshold.

10. The method of embodiment 1 wherein the determining a user watching time length comprises applying watching time caps based on any of TV on off events set top box on off events and heuristics.

11. The method of embodiment 1 further comprising feeding the user watching event log file for user viewing data record associated with the selected media program.

12. The method of embodiment 1 wherein the general purpose user mobile device is configured to automatically scan on a communication stack for a physical address of a TV set.

13. The method of embodiment 1 wherein the general purpose user mobile device receives user submitted TV parameters to scan for a TV set.

14. The method of embodiment 1 further comprising obtaining an atmospherics data artifact from the atmospherics data package.

incorporating the user viewing status indication into viewer measurement data of the user selected channel

17. The method of embodiment 1 wherein the received TV program schedule listing data comprises a plurality of ad tags.

a processor disposed in communication with said memory and configured to issue a plurality of processing instructions stored in the memory wherein the processor issues instructions to 

filter the received user media program selection message when the received user media program selection message is determined not to indicate a user watching event.

23. The system of embodiment 21 wherein the general purpose user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer

24. The system of embodiment 21 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

25. The system of embodiment 21 wherein the general purpose user mobile device transmits a TV remote channel selection indication to a TV set top box via the infrared plug in component.

26. The system of embodiment 21 wherein the TV remote channel selection message comprises a non live media program selection message.

27. The system of embodiment 21 wherein the non live media program selection message comprises any of a DVD control message a TiVo control message and an on demand media control message.

28. The system of embodiment 21 wherein the determining whether the received user media program selection message indicates a user watching event comprises 

29. The system of embodiment 21 wherein the determining a user watching time length comprises determining whether a time lapse between two consecutively received program selection messages exceeds a capping threshold.

30. The system of embodiment 21 wherein the determining a user watching time length comprises applying watching time caps based on any of TV on off events set top box on off events and heuristics.

31. The system of embodiment 21 wherein the processor issues instructions to feed the user watching event log file for user viewing data record associated with the selected media program.

32. The system of embodiment 21 wherein the general purpose user mobile device is configured to automatically scan on a communication stack for a physical address of a TV set.

33. The system of embodiment 21 wherein the general purpose user mobile device receives user submitted TV parameters to scan for a TV set.

incorporate the user viewing status indication into viewer measurement data of the user selected channel

37. The system of embodiment 21 wherein the received TV program schedule listing data comprises a plurality of ad tags.

41. A TV mobile control processor readable storage medium storing processor executable instructions to 

filter the received user media program selection message when the received user media program selection message is determined not to indicate a user watching event.

43. The medium of embodiment 41 wherein the general purpose user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer

44. The medium of embodiment 41 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

45. The medium of embodiment 41 wherein the general purpose user mobile device transmits a TV remote channel selection indication to a TV set top box via the infrared plug in component.

46. The medium of embodiment 41 wherein the TV remote channel selection message comprises a non live media program selection message.

47. The medium of embodiment 41 wherein the non live media program selection message comprises any of a DVD control message a TiVo control message and an on demand media control message.

48. The medium of embodiment 41 wherein the determining whether the received user media program selection message indicates a user watching event comprises 

49. The medium of embodiment 41 wherein the determining a user watching time length comprises determining whether a time lapse between two consecutively received program selection messages exceeds a capping threshold.

50. The medium of embodiment 41 wherein the determining a user watching time length comprises applying watching time caps based on any of TV on off events set top box on off events and heuristics.

51. The medium of embodiment 41 further storing instructions to feed the user watching event log file for user viewing data record associated with the selected media program.

52. The medium of embodiment 41 wherein the general purpose user mobile device is configured to automatically scan on a communication stack for a physical address of a TV set.

53. The medium of embodiment 41 wherein the general purpose user mobile device receives user submitted TV parameters to scan for a TV set.

incorporate the user viewing status indication into viewer measurement data of the user selected channel

57. The medium of embodiment 41 wherein the received TV program schedule listing data comprises a plurality of ad tags.

2. The method of embodiment 1 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

3. The method of embodiment 1 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

4. The method of embodiment 1 wherein the same user channel selection is transmitted to a TV set via an infrared communication channel.

5. The method of embodiment 1 wherein the atmospherics data package is captured and aggregated by the user mobile device to monitor whether the user is watching the selected channel.

6. The method of embodiment 1 further comprising determining a type of the atmospherics data artifact.

when the graphic content comprises audience presence performing facial recognition to determine a number of presented audiences.

when the graphic content comprises a TV screen determining whether the TV screen is related to a TV show scheduled on the user selected channel.

19. The method of embodiment 1 wherein the atmospherics data artifact comprises a lighting sensing data file.

20. The method of embodiment 19 further comprising determining whether audience environment is suitable for viewing based on the lighting sensing data.

21. The method of embodiment 1 wherein the atmospherics data artifact comprises a device application activity log file.

23. The method of embodiment 1 wherein the generating a user viewing status indication is performed based on a threshold based progressive procedure.

repeating analysis of atmospherics data artifacts when an accumulated atmospherics score does not exceed the threshold.

determining the user is not watching the selected channel and exit the threshold based progressive procedure when the accumulated atmospherics score exceeds the threshold.

27. The method of embodiment 23 wherein the threshold based progressive procedure analyzes atmospherics data artifacts based on complexity from low to high.

28. The method of embodiment 24 wherein the first atmospherics data artifact comprises any of GPS information and device application activity status.

29. The method of embodiment 24 wherein the first and second weight score values are retrieved from the pre stored data table.

when the threshold based progressive procedure determines the user is not watching the selected channel 

32. The system of embodiment 31 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

33. The system of embodiment 31 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

34. The system of embodiment 31 wherein the same user channel selection is transmitted to a TV set via an infrared communication channel.

35. The system of embodiment 31 wherein the atmospherics data package is captured and aggregated by the user mobile device to monitor whether the user is watching the selected channel.

36. The system of embodiment 31 further comprising determining a type of the atmospherics data artifact.

means to when the graphic content comprises audience presence perform facial recognition to determine a number of presented audiences.

means to when the graphic content comprises a TV screen determine whether the TV screen is related to a TV show scheduled on the user selected channel.

49. The system of embodiment 31 wherein the atmospherics data artifact comprises a lighting sensing data file.

50. The system of embodiment 49 further comprising means to determine whether audience environment is suitable for viewing based on the lighting sensing data.

51. The system of embodiment 31 wherein the atmospherics data artifact comprises a device application activity log file.

53. The system of embodiment 31 wherein the generating a user viewing status indication is performed based on a threshold based progressive procedure.

means to repeat analysis of atmospherics data artifacts when an accumulated atmospherics score does not exceed the threshold.

means to determine the user is not watching the selected channel and exit the threshold based progressive procedure when the accumulated atmospherics score exceeds the threshold.

57. The system of embodiment 53 wherein the threshold based progressive procedure analyzes atmospherics data artifacts based on complexity from low to high.

58. The system of embodiment 54 wherein the first atmospherics data artifact comprises any of GPS information and device application activity status.

59. The system of embodiment 54 wherein the first and second weight score values are retrieved from the pre stored data table.

when the threshold based progressive procedure determines the user is not watching the selected channel 

61. A TV audience monitoring processor readable non transitory medium storing processor executable instructions said instructions issuable by a processor to 

62. The medium of embodiment 61 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

63. The medium of embodiment 61 wherein the TV program schedule listing data is transmitted via any of a cellar network a 3G network and a Wifi network.

64. The medium of embodiment 61 wherein the same user channel selection is transmitted to a TV set via an infrared communication channel.

65. The medium of embodiment 61 wherein the atmospherics data package is captured and aggregated by the user mobile device to monitor whether the user is watching the selected channel.

66. The medium of embodiment 61 wherein the processor executable instructions are further issuable by the processor to determining a type of the atmospherics data artifact.

68. The medium of embodiment 67 wherein the processor executable instructions are further issuable by the processor to 

69. The medium of embodiment 68 wherein the processor executable instructions are further issuable by the processor to 

70. The medium of embodiment 68 wherein the processor executable instructions are further issuable by the processor to 

71. The medium of 68 wherein the processor executable instructions are further issuable by the processor to 

72. The medium of embodiment 68 wherein the processor executable instructions are further issuable by the processor to 

74. The medium of embodiment 61 wherein the processor executable instructions are further issuable by the processor to 

75. The medium of embodiment 64 wherein the processor executable instructions are further issuable by the processor to 

when the graphic content comprises audience presence perform facial recognition to determine a number of presented audiences.

76. The medium of embodiment 75 wherein the processor executable instructions are further issuable by the processor to 

when the graphic content comprises a TV screen determine whether the TV screen is related to a TV show scheduled on the user selected channel.

78. The medium of embodiment 61 wherein the processor executable instructions are further issuable by the processor to 

79. The medium of embodiment 61 wherein the atmospherics data artifact comprises a lighting sensing data file.

80. The medium of embodiment 79 wherein the processor executable instructions are further issuable by the processor to determine whether audience environment is suitable for viewing based on the lighting sensing data.

81. The medium of embodiment 61 wherein the atmospherics data artifact comprises a device application activity log file.

82. The medium of embodiment 71 wherein the processor executable instructions are further issuable by the processor to 

83. The medium of embodiment 61 wherein the generating a user viewing status indication is performed based on a threshold based progressive procedure.

85. The medium of embodiment 83 wherein the processor executable instructions are further issuable by the processor to 

repeat analysis of atmospherics data artifacts when an accumulated atmospherics score does not exceed the threshold.

86. The medium of embodiment 83 wherein the processor executable instructions are further issuable by the processor to 

determine the user is not watching the selected channel and exit the threshold based progressive procedure when the accumulated atmospherics score exceeds the threshold.

87. The medium of embodiment 83 wherein the threshold based progressive procedure analyzes atmospherics data artifacts based on complexity from low to high.

88. The medium of embodiment 84 wherein the first atmospherics data artifact comprises any of GPS information and device application activity status.

89. The medium of embodiment 84 wherein the first and second weight score values are retrieved from the pre stored data table.

90. The medium of embodiment 84 wherein the processor executable instructions are further issuable by the processor to 

when the threshold based progressive procedure determines the user is not watching the selected channel 

Further embodiments of capturing audience atmospherics data at a user mobile device may comprise the following 

receiving TV program schedule listing data at the general purpose user mobile device via a communication channel 

obtaining a user selection of TV program via a user interface of the instantiated TV mobile control component 

generating an atmospherics data package comprising one or more atmospherics data artifact from the captured atmospherics data and

2. The method of embodiment 1 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

3. The method of embodiment 1 wherein the communication network comprises any of a cellar network a 3G network and a Wifi network.

4. The method of embodiment 1 wherein the capturing atmospherics data is automatically performed by the TV mobile control component on a periodic basis.

6. The method of embodiment 1 wherein the capturing atmospherics data comprises snapping a photo by an image capturing component connected to the user mobile device.

7. The method of embodiment 1 wherein the capturing atmospherics data comprises obtaining a video clip by an image capturing component connected to the user mobile device.

8. The method of embodiment 1 wherein the capturing atmospherics data comprises recording an audio clip by the user mobile device.

9. The method of embodiment 1 wherein the capturing atmospherics data comprises obtaining GPS information of the user mobile device.

10. The method of embodiment 1 wherein the capturing atmospherics data comprises obtaining lighting sensing data by the user mobile device.

11. The method of embodiment 1 wherein the capturing atmospherics data comprises obtaining device application activity status on the user mobile device.

12. The method of embodiment 1 wherein the atmospherics data artifact comprises any of an image a video clip an audio clip GPS information device application data and lighting data.

13. The method of embodiment 1 further comprising prompting a request to a user to position the user mobile device so that an image capture component is focused on a TV screen.

19. The method of embodiment 7 wherein the GPS information indicates whether a user is located with a TV set.

20. The method of embodiment to wherein the lighting data indicates whether amble light is provided to watch TV.

a processor disposed in communication with said memory and configured to issue a plurality of processing instructions stored in the memory wherein the processor issues instructions to 

receive TV program schedule listing data at the general purpose user mobile device via a communication channel 

obtain a user selection of TV program via a user interface of the instantiated TV mobile control component 

generate an atmospherics data package comprising one or more atmospherics data artifact from the captured atmospherics data and

22. The apparatus of embodiment 1 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

23. The apparatus of embodiment 21 wherein the communication network comprises any of a cellar network a 3G network and a Wifi network.

24. The apparatus of embodiment 21 wherein the capturing atmospherics data is automatically performed by the TV mobile control component on a periodic basis.

26. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises snapping a photo by an image capturing component connected to the user mobile device.

27. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises obtaining a video clip by an image capturing component connected to the user mobile device.

28. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises recording an audio clip by the user mobile device.

29. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises obtaining GPS information of the user mobile device.

30. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises obtaining lighting sensing data by the user mobile device.

31. The apparatus of embodiment 21 wherein the capturing atmospherics data comprises obtaining device application activity status on the user mobile device.

32. The apparatus of embodiment 21 wherein the atmospherics data artifact comprises any of an image a video clip an audio clip GPS information device application data and lighting data.

33. The apparatus of embodiment 21 wherein the processor further issues instructions to prompt a request to a user to position the user mobile device so that an image capture component is focused on a TV screen.

39. The apparatus of embodiment 29 wherein the GPS information indicates whether a user is located with a TV set.

40. The apparatus of embodiment 30 wherein the lighting data indicates whether amble light is provided to watch TV.

receive TV program schedule listing data at the general purpose user mobile device via a communication channel 

obtain a user selection of TV program via a user interface of the instantiated TV mobile control component 

generate an atmospherics data package comprising one or more atmospherics data artifact from the captured atmospherics data and

42. The medium of embodiment 41 wherein the user mobile device comprises any of a smartphone a personal data assistant a cellular phone a laptop and a tablet computer.

43. The medium of embodiment 41 wherein the communication network comprises any of a cellar network a 3G network and a Wifi network.

44. The medium of embodiment 41 wherein the capturing atmospherics data is automatically performed by the TV mobile control component on a periodic basis.

46. The medium of embodiment 41 wherein the capturing atmospherics data comprises snapping a photo by an image capturing component connected to the user mobile device.

47. The medium of embodiment 41 wherein the capturing atmospherics data comprises obtaining a video clip by an image capturing component connected to the user mobile device.

48. The medium of embodiment 41 wherein the capturing atmospherics data comprises recording an audio clip by the user mobile device.

49. The medium of embodiment 41 wherein the capturing atmospherics data comprises obtaining GPS information of the user mobile device.

50. The medium of embodiment 41 wherein the capturing atmospherics data comprises obtaining lighting sensing data by the user mobile device.

61. The medium of embodiment 41 wherein the capturing atmospherics data comprises obtaining device application activity status on the user mobile device.

62. The medium of embodiment 41 wherein the atmospherics data artifact comprises any of an image a video clip an audio clip GPS information device application data and lighting data.

63. The medium of embodiment 41 further storing processor executable instructions to prompt a request to a user to position the user mobile device so that an image capture component is focused on a TV screen.

69. The medium of embodiment 59 wherein the GPS information indicates whether a user is located with a TV set.

60. The medium of embodiment 50 wherein the lighting data indicates whether amble light is provided to watch TV.

Further embodiments of generating media content based survey questionnaires may comprise the following 

providing the obtained TV program schedule listing data including a plurality of ad tags to a user mobile device 

retrieving an ad tag associated with the user selected media program from the TV program schedule listing data 

2. The method of embodiment 1 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

3. The method of embodiment 1 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

4. The method of embodiment 1 wherein the ad tag further comprises a timestamp of an ad and information related to the advertised item.

7. The method of embodiment 1 wherein the generated survey question is sent to the user mobile device shortly after a timestamp of the ad tag.

10. The method of embodiment 1 wherein the survey question comprises a URL to a merchant shopping site.

11. The method of embodiment 1 wherein the user reaction to the survey question comprises a submission of answer to the survey question.

12. The method of embodiment 1 wherein the user reaction to the survey question comprises a click on a URL provided in the survey question.

13. The method of embodiment 1 wherein the survey question is generated based on ad tags in a user s recent viewing history.

14. The method of embodiment 1 further comprising providing incentive rewards to a user after receiving an answer to the survey question.

17. The method of embodiment 16 wherein the weighing score is determined based on a type of the user reaction.

18. The method of embodiment 16 wherein the weighing score is determined based on a user s answer to the survey question.

19. The method of embodiment 15 further comprising aggregating weighing scores from a plurality of user reactions to determine ad effects.

20. The method of embodiment 15 further comprising periodically update the analysis by combining newly received user reactions to survey questions.

means for providing the obtained TV program schedule listing data including a plurality of ad tags to a user mobile device 

means for retrieving an ad tag associated with the user selected media program from the TV program schedule listing data 

22. The system of embodiment 21 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

23. The system of embodiment 21 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

24. The system of embodiment 21 wherein the ad tag further comprises a timestamp of an ad and information related to the advertised item.

means for retrieving survey questions from the survey question list based on the determined category.

27. The system of embodiment 21 wherein the generated survey question is sent to the user mobile device shortly after a timestamp of the ad tag.

30. The system of embodiment 21 wherein the survey question comprises a URL to a merchant shopping site.

31. The system of embodiment 21 wherein the user reaction to the survey question comprises a submission of answer to the survey question.

32. The system of embodiment 21 wherein the user reaction to the survey question comprises a click on a URL provided in the survey question.

33. The system of embodiment 21 wherein the survey question is generated based on ad tags in a user s recent viewing history.

34. The system of embodiment 21 further comprising means for providing incentive rewards to a user after receiving an answer to the survey question.

37. The system of embodiment 36 wherein the weighing score is determined based on a type of the user reaction.

38. The system of embodiment 36 wherein the weighing score is determined based on a user s answer to the survey question.

39. The system of embodiment 35 further comprising means for aggregating weighing scores from a plurality of user reactions to determine ad effects.

40. The system of embodiment 35 further comprising means for periodically updating the analysis by combining newly received user reactions to survey questions.

41. A media content based survey distribution and collection processor readable non transitory medium storing processor executable instructions to 

provide the obtained TV program schedule listing data including a plurality of ad tags to a user mobile device 

retrieve an ad tag associated with the user selected media program from the TV program schedule listing data 

42. The medium of embodiment 21 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

43. The medium of embodiment 21 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

44. The medium of embodiment 21 wherein the ad tag further comprises a timestamp of an ad and information related to the advertised item.

46. The medium of embodiment 45 further storing processor executable instructions to retrieve survey questions from the survey question list based on the determined category.

47. The medium of embodiment 41 wherein the generated survey question is sent to the user mobile device shortly after a timestamp of the ad tag.

50. The medium of embodiment 41 wherein the survey question comprises a URL to a merchant shopping site.

51. The medium of embodiment 41 wherein the user reaction to the survey question comprises a submission of answer to the survey question.

52. The medium of embodiment 41 wherein the user reaction to the survey question comprises a click on a URL provided in the survey question.

53. The medium of embodiment 41 wherein the survey question is generated based on ad tags in a user s recent viewing history.

54. The medium of embodiment 41 further storing processor executable instructions to provide incentive rewards to a user after receiving an answer to the survey question.

55. The medium of embodiment 41 further storing processor executable instructions to analyze ad delivery and effects.

56. The medium of embodiment 55 further storing processor executable instructions to assign a weighing score to the user reaction to the survey question.

57. The medium of embodiment 56 wherein the weighing score is determined based on a type of the user reaction.

58. The medium of embodiment 56 wherein the weighing score is determined based on a user s answer to the survey question.

59. The medium of embodiment 55 further storing processor executable instructions to aggregate weighing scores from a plurality of user reactions to determine ad effects.

60. The medium of embodiment 55 further storing processor executable instructions to periodically update the analysis by combining newly received user reactions to survey questions.

Further embodiments of generating synchronized media content based product placement ads may comprise the following 

retrieving an ad tag associated with the user selected media program from the TV program schedule listing data 

2. The method of embodiment 1 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

3. The method of embodiment 1 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

4. The method of embodiment 1 wherein the ad tag further comprises the timestamp of an ad and information related to the advertised item.

6. The method of embodiment 5 further comprising populating information of the identified advertised item into the static ad template.

7. The method of embodiment 1 wherein the available ad template comprises an image captured from the media program and said image comprises the identified advertised item.

8. The method of embodiment 7 further comprising generating an interactive ad using the available ad template.

9. The method of embodiment 7 wherein the image comprises an indicia box indicating the identified advertised item.

10. The method of embodiment 8 wherein the interactive ad comprises a rating of the identified advertised item.

11. The method of embodiment 8 wherein the interactive ad comprises an immediate purchasing option including a URL to a merchant shopping site.

12. The method of embodiment 1 wherein the interactive ad comprises an option for a user to enter a rating for the identified advertised item.

13. The method of embodiment 1 further comprising providing options to a user to browse interactive ads.

14. The method of embodiment 13 wherein the options comprises browsing interactive ads by any of character item category season episode.

17. The method of embodiment 16 wherein the weighing score is determined based on a type of the user interaction.

18. The method of embodiment 16 wherein the user interaction comprises any of entry of product rating click to view more and click to purchase.

19. The method of embodiment 15 further comprising aggregating weighing scores from a plurality of user reactions to determine ad effects.

20. The method of embodiment 15 further comprising periodically update the analysis by combining newly received user interactions.

means for providing TV program schedule listing data including a plurality of ad tags to a user mobile device 

means for retrieving an ad tag associated with the user selected media program from the TV program schedule listing data 

means for identifying an advertised item embedded in the media program based on the retrieved ad tag 

22. The system of embodiment 21 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

23. The system of embodiment 21 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

24. The system of embodiment 21 wherein the ad tag further comprises the timestamp of an ad and information related to the advertised item.

26. The system of embodiment 25 further comprising populating information of the identified advertised item into the static ad template.

27. The system of embodiment 21 wherein the available ad template comprises an image captured from the media program and said image comprises the identified advertised item.

28. The system of embodiment 27 further comprising means for generating an interactive ad using the available ad template.

29. The system of embodiment 27 wherein the image comprises an indicia box indicating the identified advertised item.

30. The system of embodiment 28 wherein the interactive ad comprises a rating of the identified advertised item.

31. The system of embodiment 28 wherein the interactive ad comprises an immediate purchasing option including a URL to a merchant shopping site.

32. The system of embodiment 21 wherein the interactive ad comprises an option for a user to enter a rating for the identified advertised item.

33. The system of embodiment 21 further comprising providing options to a user to browse interactive ads.

34. The system of embodiment 33 wherein the options comprises browsing interactive ads by any of character item category season episode.

37. The system of embodiment 36 wherein the weighing score is determined based on a type of the user interaction.

38. The system of embodiment 36 wherein the user interaction comprises any of entry of product rating click to view more and click to purchase.

39. The system of embodiment 35 further comprising means for aggregating weighing scores from a plurality of user reactions to determine ad effects.

40. The system of embodiment 35 further comprising means for periodically updating the analysis by combining newly received user interactions.

41. A media content based advertising processor readable non transitory medium storing processor executable instructions to 

retrieve an ad tag associated with the user selected media program from the TV program schedule listing data 

42. The medium of embodiment 41 wherein the ad tag is related to an advertisement played during a commercial break associated with the user selected media program.

43. The medium of embodiment 41 wherein the ad tag is related to an embedded ad placed in a scene of the user selected media program.

44. The medium of embodiment 41 wherein the ad tag further comprises the timestamp of an ad and information related to the advertised item.

46. The medium of embodiment 45 further storing instructions to populate information of the identified advertised item into the static ad template.

47. The medium of embodiment 41 wherein the available ad template comprises an image captured from the media program and said image comprises the identified advertised item.

48. The medium of embodiment 47 further storing instructions to generate an interactive ad using the available ad template.

49. The medium of embodiment 47 wherein the image comprises an indicia box indicating the identified advertised item.

50. The medium of embodiment 48 wherein the interactive ad comprises a rating of the identified advertised item.

51. The medium of embodiment 48 wherein the interactive ad comprises an immediate purchasing option including a URL to a merchant shopping site.

52. The medium of embodiment 41 wherein the interactive ad comprises an option for a user to enter a rating for the identified advertised item.

53. The medium of embodiment 41 further storing instructions to provide options to a user to browse interactive ads.

54. The medium of embodiment 43 wherein the options comprises browsing interactive ads by any of character item category season episode.

57. The medium of embodiment 56 wherein the weighing score is determined based on a type of the user interaction.

58. The medium of embodiment 57 wherein the user interaction comprises any of entry of product rating click to view more and click to purchase.

59. The medium of embodiment 55 further comprising aggregating weighing scores from a plurality of user reactions to determine ad effects.

60. The medium of embodiment 55 further comprising periodically update the analysis by combining newly received user interactions.

sending an access request with the obtained user authorization credentials to a social media platform 

tagging the received media content data based on the type according to a progressive taxonomy mechanism 

2. The method of embodiment 1 wherein the request to access social media content comprises a request received from a user to populate a social watching event status to a social media platform.

3. The method of embodiment 1 wherein the request to access social media content comprises a periodic social media content update.

4. The method of embodiment 1 wherein the request to access social media content is triggered by an obtained request for social media analytics.

6. The method of embodiment 1 wherein the obtaining user authorization credentials comprises redirecting a user to a social media login page.

7. The method of embodiment 1 wherein the social media platform obtains a user application ID and user permission.

8. The method of embodiment 1 wherein the user authorization credentials comprise a user token received from the social media platform.

9. The method of embodiment 1 wherein the receiving social media content data from the social media platform is scheduled on a periodic basis.

10. The method of embodiment 1 wherein the receiving social media content data from the social media platform is performed on demand.

11. The method of embodiment 1 wherein the type of the received media content data comprises any of structured data and unstructured data.

12. The method of embodiment 11 wherein the structured data comprises any of a number of user social media connections and a user profile.

13. The method of embodiment 11 wherein the unstructured data comprises raw texts of social media comments.

14. The method of embodiment 11 wherein the tagging the received media content data comprises tagging unstructured data based on category of data content.

15. The method of embodiment 1 wherein progressive taxonomy mechanism comprises a set of pre determined key terms.

18. The method of embodiment 1 wherein the social media analytics request comprises an impression request of the item.

22. The method of embodiment 19 further comprising determining whether tags of unstructured data includes the key word.

23. The method of embodiment 1 wherein the determining impression heuristics comprises assigning a weight value to the social media content based on the progressive mechanism.

24. The method of embodiment 1 wherein the determining impression heuristics of the item based on query results comprises calculating an impression score.

25. The method of embodiment 1 wherein the impression heuristics is determined based on statistical analysis of social media content.

means for sending an access request with the obtained user authorization credentials to a social media platform 

means for tagging the received media content data based on the type according to a progressive taxonomy mechanism 

27. The system of embodiment 26 wherein the request to access social media content comprises a request received from a user to populate a social watching event status to a social media platform.

28. The system of embodiment 26 wherein the request to access social media content comprises a periodic social media content update.

29. The system of embodiment 26 wherein the request to access social media content is triggered by an obtained request for social media analytics.

31. The system of embodiment 26 wherein the obtaining user authorization credentials comprises redirecting a user to a social media login page.

32. The system of embodiment 26 wherein the social media platform obtains a user application ID and user permission.

33. The system of embodiment 26 wherein the user authorization credentials comprise a user token received from the social media platform.

34. The system of embodiment 26 wherein the receiving social media content data from the social media platform is scheduled on a periodic basis.

35. The system of embodiment 26 wherein the receiving social media content data from the social media platform is performed on demand.

36. The system of embodiment 26 wherein the type of the received media content data comprises any of structured data and unstructured data.

37. The system of embodiment 36 wherein the structured data comprises any of a number of user social media connections and a user profile.

38. The system of embodiment 36 wherein the unstructured data comprises raw texts of social media comments.

39. The system of embodiment 36 wherein the tagging the received media content data comprises tagging unstructured data based on category of data content.

40. The system of embodiment 26 wherein progressive taxonomy mechanism comprises a set of pre determined key terms.

43. The system of embodiment 26 wherein the social media analytics request comprises an impression request of the item.

47. The system of embodiment 26 further comprising means for determining whether tags of unstructured data includes the key word.

48. The system of embodiment 26 wherein the determining impression heuristics comprises assigning a weight value to the social media content based on the progressive mechanism.

49. The system of embodiment 26 wherein the determining impression heuristics of the item based on query results comprises calculating an impression score.

50. The system of embodiment 26 wherein the impression heuristics is determined based on statistical analysis of social media content.

51. A social media content access processor readable non transitory medium storing processor executable instructions to 

52. The medium of embodiment 51 wherein the request to access social media content comprises a request received from a user to populate a social watching event status to a social media platform.

53. The medium of embodiment 51 wherein the request to access social media content comprises a periodic social media content update.

54. The medium of embodiment 51 wherein the request to access social media content is triggered by an obtained request for social media analytics.

56. The medium of embodiment 51 wherein the obtaining user authorization credentials comprises redirecting a user to a social media login page.

57. The medium of embodiment 51 wherein the social media platform obtains a user application ID and user permission.

58. The medium of embodiment 51 wherein the user authorization credentials comprise a user token received from the social media platform.

59. The medium of embodiment 51 wherein the receiving social media content data from the social media platform is scheduled on a periodic basis.

60. The medium of embodiment 51 wherein the receiving social media content data from the social media platform is performed on demand.

61. The medium of embodiment 51 wherein the type of the received media content data comprises any of structured data and unstructured data.

62. The medium of embodiment 61 wherein the structured data comprises any of a number of user social media connections and a user profile.

63. The medium of embodiment 61 wherein the unstructured data comprises raw texts of social media comments.

64. The medium of embodiment 61 wherein the tagging the received media content data comprises tagging unstructured data based on category of data content.

65. The medium of embodiment 51 wherein progressive taxonomy mechanism comprises a set of pre determined key terms.

68. The medium of embodiment 51 wherein the social media analytics request comprises an impression request of the item.

72. The medium of embodiment 69 further comprising determining whether tags of unstructured data includes the key word.

73. The medium of embodiment 51 wherein the determining impression heuristics comprises assigning a weight value to the social media content based on the progressive mechanism.

74. The medium of embodiment 51 wherein the determining impression heuristics of the item based on query results comprises calculating an impression score.

75. The medium of embodiment 51 wherein the impression heuristics is determined based on statistical analysis of social media content.

obtaining user media exposure data from a variety of data channels upon verification of the obtained user authorization credentials 

querying for user impression data related to the identified object from the obtained user media exposure data 

classifying the queried user impression data related to the identified object based on different classification measures and

4. The method of embodiment 1 wherein the media analytics parameters comprise any of a TV network a TV show genre a TV show name.

5. The method of embodiment 1 wherein the media analytics parameters further comprise user gender age group user interface types user phone type day part time range and user location.

6. The method of embodiment 1 wherein the media analytics parameters further comprise types of social media platform.

7. The method of embodiment 1 wherein the obtaining user authorization credentials comprises recruiting social media users to share social content.

8. The method of embodiment 1 wherein the obtaining user authorization credentials further comprises prompting a user to provide social media login credentials.

9. The method of embodiment 1 wherein the obtaining user authorization credentials further comprises redirecting a user to a social media login page.

10. The method of embodiment 1 wherein the user media exposure data comprises any of user website visits social media content and TV viewing data.

12. The method of embodiment 1 wherein the variety of data channels comprise a mobile application instantiated on a user mobile device.

15. The method of embodiment 1 wherein the user media exposure data further comprises user responses to survey questions GPS locations user application usage and mobile search behavior.

16. The method of embodiment 1 wherein the querying for user impression data comprises a progressive search based on the identified object related key terms.

17. The method of embodiment 1 wherein the classification measures comprise any of user gender user age group day of week and day part time range.

18. The method of embodiment 1 wherein the user impression reports are classified by the classification measures.

19. The method of embodiment 1 wherein the user impression reports comprise application data statistics as to any of number of total application sessions media session length number of total users.

20. The method of embodiment 1 wherein the user impression reports further comprise any of unique users percent active reach time per person number of visits number of pages viewed visits person user gender and age groups.

a processor disposed in communication with said memory and configured to issue a plurality of processing instructions stored in the memory wherein the processor issues instructions to 

obtain user media exposure data from a variety of data channels upon verification of the obtained user authorization credentials 

query for user impression data related to the identified object from the obtained user media exposure data 

classify the queried user impression data related to the identified object based on different classification measures and

24. The system of embodiment 21 wherein the media analytics parameters comprise any of a TV network a TV show genre a TV show name.

25. The system of embodiment 21 wherein the media analytics parameters further comprise user gender age group user interface types user phone type day part time range and user location.

26. The system of embodiment 21 wherein the media analytics parameters further comprise types of social media platform.

27. The system of embodiment 21 wherein the obtaining user authorization credentials comprises recruiting social media users to share social content.

28. The system of embodiment 21 wherein the obtaining user authorization credentials further comprises prompting a user to provide social media login credentials.

29. The system of embodiment 21 wherein the obtaining user authorization credentials further comprises redirecting a user to a social media login page.

30. The system of embodiment 21 wherein the user media exposure data comprises any of user website visits social media content and TV viewing data.

32. The system of embodiment 21 wherein the variety of data channels comprise a mobile application instantiated on a user mobile device.

35. The system of embodiment 21 wherein the user media exposure data further comprises user responses to survey questions GPS locations user application usage and mobile search behavior.

36. The system of embodiment 21 wherein the querying for user impression data comprises a progressive search based on the identified object related key terms.

37. The system of embodiment 21 wherein the classification measures comprise any of user gender user age group day of week and day part time range.

38. The system of embodiment 21 wherein the user impression reports are classified by the classification measures.

39. The system of embodiment 21 wherein the user impression reports comprise application data statistics as to any of number of total application sessions media session length number of total users.

40. The system of embodiment 21 wherein the user impression reports further comprise any of unique users percent active reach time per person number of visits number of pages viewed visits person user gender and age groups.

41. A media analytics processor readable storage medium storing processor executable instructions to 

obtain user media exposure data from a variety of data channels upon verification of the obtained user authorization credentials 

query for user impression data related to the identified object from the obtained user media exposure data 

classify the queried user impression data related to the identified object based on different classification measures and

44. The medium of embodiment 41 wherein the media analytics parameters comprise any of a TV network a TV show genre a TV show name.

45. The medium of embodiment 41 wherein the media analytics parameters further comprise user gender age group user interface types user phone type day part time range and user location.

46. The medium of embodiment 41 wherein the media analytics parameters further comprise types of social media platform.

47. The medium of embodiment 41 wherein the obtaining user authorization credentials comprises recruiting social media users to share social content.

48. The medium of embodiment 41 wherein the obtaining user authorization credentials further comprises prompting a user to provide social media login credentials.

49. The medium of embodiment 41 wherein the obtaining user authorization credentials further comprises redirecting a user to a social media login page.

40. The medium of embodiment 41 wherein the user media exposure data comprises any of user website visits social media content and TV viewing data.

52. The medium of embodiment 41 wherein the variety of data channels comprise a mobile application instantiated on a user mobile device.

55. The medium of embodiment 41 wherein the user media exposure data further comprises user responses to survey questions GPS locations user application usage and mobile search behavior.

56. The medium of embodiment 41 wherein the querying for user impression data comprises a progressive search based on the identified object related key terms.

57. The medium of embodiment 41 wherein the classification measures comprise any of user gender user age group day of week and day part time range.

58. The medium of embodiment 41 wherein the user impression reports are classified by the classification measures.

59. The medium of embodiment 41 wherein the user impression reports comprise application data statistics as to any of number of total application sessions media session length number of total users.

60. The medium of embodiment 41 wherein the user impression reports further comprise any of unique users percent active reach time per person number of visits number of pages viewed visits person user gender and age groups.

monitoring data traffic coming in and out of the user mobile device based on the obtained user mobile device identifier via a mobile usage tracking entity 

determining user media content exposure information from the parsed monitored data traffic based on the data content type and

2. The method of embodiment 1 wherein the user mobile device identifier comprises a hardware identifier.

3. The method of embodiment 1 wherein the user mobile device identifier comprises a physical address.

4. The method of embodiment 1 wherein the data traffic is obtained via a mobile application instantiated on the user mobile device.

6. The method of embodiment 1 wherein the determine a data content type of the data traffic comprises extracting a data type filed value from a data event message.

8. The method of embodiment 1 wherein the determining user media content exposure information comprises 

9. The method of embodiment 8 wherein the determining user media content exposure information further comprises 

10. The method of embodiment 1 wherein the determining user media content exposure information comprises 

11. The method of embodiment to wherein the application group sharing information comprises a list of social connections.

12. The method of embodiment 1 wherein the determining user media content exposure information comprises 

13. The method of embodiment 1 wherein the determining user media content exposure information comprises 

TV channel changing events mobile advertising data mobile application usage data social media profile social media comments and website visits.

17. The method of embodiment 1 wherein the user media content exposure statistics data comprises any of user brand impression measures.

18. The method of embodiment 17 wherein the user brand impression measures comprises a list of top mentioned brands.

providing and generating individualized ad contents to the user mobile device based on the generated user media content exposure statistics data.

generating individualized survey questions to the user mobile device based on the generated user media content exposure statistics data.

a processor disposed in communication with said memory and configured to issue a plurality of processing instructions stored in the memory wherein the processor issues instructions to 

monitor data traffic coming in and out of the user mobile device based on the obtained user mobile device identifier via a mobile usage tracking entity 

determine user media content exposure information from the parsed monitored data traffic based on the data content type and

22. The system of embodiment 21 wherein the user mobile device identifier comprises a hardware identifier.

23. The system of embodiment 21 wherein the user mobile device identifier comprises a physical address.

24. The system of embodiment 21 wherein the data traffic is obtained via a mobile application instantiated on the user mobile device.

26. The system of embodiment 21 wherein the determine a data content type of the data traffic comprises extracting a data type filed value from a data event message.

28. The system of embodiment 21 wherein the determining user media content exposure information comprises 

29. The system of embodiment 28 wherein the determining user media content exposure information further comprises 

30. The system of embodiment 21 wherein the determining user media content exposure information comprises 

31. The system of embodiment 30 wherein the application group sharing information comprises a list of social connections.

32. The system of embodiment 21 wherein the determining user media content exposure information comprises 

33. The system of embodiment 21 wherein the determining user media content exposure information comprises 

TV channel changing events mobile advertising data mobile application usage data social media profile social media comments and website visits.

37. The system of embodiment 21 wherein the user media content exposure statistics data comprises any of user brand impression measures.

38. The system of embodiment 37 wherein the user brand impression measures comprises a list of top mentioned brands.

providing and generating individualized ad contents to the user mobile device based on the generated user media content exposure statistics data.

generating individualized survey questions to the user mobile device based on the generated user media content exposure statistics data.

41. A mobile content tracking and analyzing processor implemented storage medium storing processor executable instructions to 

monitor data traffic coming in and out of the user mobile device based on the obtained user mobile device identifier via a mobile usage tracking entity 

determine user media content exposure information from the parsed monitored data traffic based on the data content type and

42. The medium of embodiment 41 wherein the user mobile device identifier comprises a hardware identifier.

43. The medium of embodiment 41 wherein the user mobile device identifier comprises a physical address.

44. The medium of embodiment 41 wherein the data traffic is obtained via a mobile application instantiated on the user mobile device.

46. The medium of embodiment 41 wherein the determine a data content type of the data traffic comprises extracting a data type filed value from a data event message.

48. The medium of embodiment 41 wherein the determining user media content exposure information comprises 

49. The medium of embodiment 28 wherein the determining user media content exposure information further comprises 

50. The medium of embodiment 41 wherein the determining user media content exposure information comprises 

51. The medium of embodiment 30 wherein the application group sharing information comprises a list of social connections.

52. The medium of embodiment 41 wherein the determining user media content exposure information comprises 

53. The medium of embodiment 41 wherein the determining user media content exposure information comprises 

TV channel changing events mobile advertising data mobile application usage data social media profile social media comments and website visits.

57. The medium of embodiment 41 wherein the user media content exposure statistics data comprises any of user brand impression measures.

58. The medium of embodiment 57 wherein the user brand impression measures comprises a list of top mentioned brands.

providing and generating individualized ad contents to the user mobile device based on the generated user media content exposure statistics data.

generating individualized survey questions to the user mobile device based on the generated user media content exposure statistics data.

In order to address various issues and advance the art the entirety of this application for MEDIA CONTENT SYNCHRONIZED ADVERTISING PLATFORM APPARATUSES AND SYSTEMS including the Cover Page Title Headings Field Background Summary Brief Description of the Drawings Detailed Description Embodiments Abstract Figures Appendices and otherwise shows by way of illustration various embodiments in which the claimed innovations may be practiced. The advantages and features of the application are of a representative sample of embodiments only and are not exhaustive and or exclusive. They are presented only to assist in understanding and teach the claimed principles. It should be understood that they are not representative of all claimed innovations. As such certain aspects of the disclosure have not been discussed herein. That alternate embodiments may not have been presented for a specific portion of the innovations or that further undescribed alternate embodiments may be available for a portion is not to be considered a disclaimer of those alternate embodiments. It may be appreciated that many of those undescribed embodiments incorporate the same principles of the innovations and others are equivalent. Thus it is to be understood that other embodiments may be utilized and functional logical operational organizational structural and or topological modifications may be made without departing from the scope and or spirit of the disclosure. As such all examples and or embodiments are deemed to be non limiting throughout this disclosure. Also no inference should be drawn regarding those embodiments discussed herein relative to those not discussed herein other than it is as such for purposes of reducing space and repetition. For instance it is to be understood that the logical and or topological structure of any combination of any program components a component collection other components and or any present feature sets as described in the figures and or throughout are not limited to a fixed operating order and or arrangement but rather any disclosed order is exemplary and all equivalents regardless of order are contemplated by the disclosure. Furthermore it is to be understood that such features are not limited to serial execution but rather any number of threads processes services servers and or the like that may execute asynchronously concurrently in parallel simultaneously synchronously and or the like are contemplated by the disclosure. As such some of these features may be mutually contradictory in that they cannot be simultaneously present in a single embodiment. Similarly some features are applicable to one aspect of the innovations and inapplicable to others. In addition the disclosure includes other innovations not presently claimed. Applicant reserves all rights in those presently unclaimed innovations including the right to embodiment such innovations file additional applications continuations continuations in part divisions and or the like thereof. As such it should be understood that advantages embodiments examples functional features logical operational organizational structural topological and or other aspects of the disclosure are not to be considered limitations on the disclosure as defined by the embodiments or limitations on equivalents to the embodiments. It is to be understood that depending on the particular needs and or characteristics of a AD SURVEY individual and or enterprise user database configuration and or relational model data type data transmission and or network framework syntax structure and or the like various embodiments of the AD SURVEY may be implemented that facilitates a great deal of flexibility and customization. While various embodiments and discussions of the AD SURVEY have been directed to social networks however it is to be understood that the embodiments described herein may be readily configured and or customized for a wide variety of other applications and or implementations.


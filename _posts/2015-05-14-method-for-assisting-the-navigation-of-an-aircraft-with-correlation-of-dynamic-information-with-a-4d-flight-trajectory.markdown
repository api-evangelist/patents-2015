---

title: Method for assisting the navigation of an aircraft with correlation of dynamic information with a 4D flight trajectory
abstract: A method for assisting the navigation of an aircraft comprises: assembly by families of data by a processing unit of predetermined data and acquired data, including meteorological data, the families being predefined, each data value being associated with a time window of validity; formatting the data of the families to associate with each data value a type of graphical representation as text or a scalar, vector, surface, or volume; selection of families of data to be displayed; choice of a display time window for each family of data to be displayed; spatio-temporal discretization of the trajectory; spatio-temporal correlation of the discretized trajectory with each family of data as a function of the time windows of validity, in the display time windows of the family, to extract a sub-assembly from each family of data, by the processing unit; display of the sub-assemblies in a single representation on the same display screen.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09524571&OS=09524571&RS=09524571
owner: THALES
number: 09524571
owner_city: Courbevoie
owner_country: FR
publication_date: 20150514
---
This application claims priority to foreign French patent application No. FR 1401105 filed on May 16 2014 the disclosure of which is incorporated by reference in its entirety.

The field of the invention is that of navigation aids for aircraft and more precisely of a dynamic information correlation aid with a 4D flight trajectory.

Aeronautical information is commonly supplied to the crew. This of course relates to weather information but also to the other dynamic information likely to be encountered during the flight 

This aeronautical information is supplied to the crew in hardcopy form manual logs charts flight dossiers or in electronic form by displaying on screens in the cockpit. This dynamic information is more difficult to manage than static information since it is necessary to extrapolate and to correlate disparate pieces of information. Similarly some of this information depends on the intended altitude of the aircraft throughout the flight and here again requires a correlation. For example the temperature wind or cloud charts are provided by ranges of altitude the predicted altitude of the aircraft at a location in its flight plan has to be estimated in order to be able to find the correct chart to be displayed.

In the current operations the crew filters the information that does not apply and manages the applicable information manually. For example they correlate the lateral and vertical flight plan information with the weather charts by calculating at what time the aircraft is likely to enter into a weather area. This work is complex because several weather charts need to be crossed and the predicted 3D position of the aircraft mentally visualized on these charts together with the time dependent aspect.

Moreover dynamic information such as the weather is subject to frequent updates it needs to each time be mentally re determined what the predicted weather will be at a given future time.

Similarly the flight plan may be subject to modifications here again requiring the calculations to be re done.

A few initiatives are starting to emerge for managing these problems either in the CDS acronym for Cockpit Display System the FMS acronym for Flight Management System or the EFB acronym for Electronic Flight Bag 

The document US2012 0232785 Methods and Systems for dynamically providing contextual weather information discloses a method allowing the aircraft icon to be virtually moved via a marker along the flight plan i.e. to run the film of the flight in advance. The system determines the corresponding time it is displayed on the screens according to the method. The rest of the dynamic aeronautical information displayed on the chart corresponds to the information valid at the time in question. This allows coherent information to be displayed but only in the neighbourhood of the icon being virtually displaced as illustrated in . It can be seen in the figure that the information presented is only exact in the neighbourhood of the aircraft icon which is on the WPT since the static chart shown is that corresponding to the time closest to the time predicted for the aircraft icon. Thus for example the region Z which can in fact be traversed before 23 00 and after 06 00 is declared as accessible whereas it will no longer be so at the time when the aircraft will arrive there. Similarly it cannot be seen in the figure that a strong turbulent side wind will occur at the point WPT. This method does not allow 

The document U.S. Pat. No. 8 332 084 Four dimensional weather predictor based on aircraft trajectory discloses a method for merging spatio temporal weather information used to predict the weather along a 3D time trajectory the time being predetermined. The system determines the weather in the vicinity of a 4D 3D time trajectory. Then it allows either this trajectory to be refined by taking into account the correct wind at each point at the predicted time or a more optimized trajectory to be found in the neighbourhood of the initial trajectory using the predicted wind in a volume around the initial trajectory. This method does not allow a developing situation around the 4D trajectory to be presented in an effective manner since it does not display anything indeed the display on the current screens in 2D of a weather volume is not possible. It is just a method for calculating the FMS predictions. Moreover it only takes into account the weather wind temperature humidity pressure .

The document US2011 0102192 Displaying weather forecast for own air vehicle provides a method for displaying the weather forecast on a screen on board the aircraft. The system allows a time period or a time to be selected via a input HMI. The display screen then displays the predicted position of the aircraft at the time in question and the weather situation corresponding to the time interval in which this time is situated. This does not allows the changes in dynamic aeronautical information with time to be seen at a given time if this information changes and impacts the progress of the flight the crew have to estimate at what time this will occur to manually input the time in question in order to see both the predicted aircraft icon and the weather around this aircraft icon. There is no coherent display all along the flight path on a single screen.

The document US2011 098871 Method and apparatus for updating winds aloft display as aircraft altitude changes describes a method for displaying charts of winds as a function of the altitude by selection of a rotary switch on the aircraft altitude. This allows the crew to choose altitudes on a display screen the winds corresponding to the chosen level are then displayed. The time parameter is not integrated into this method. Moreover the display takes place around the current aircraft and does not take into account the flight plan.

The document by the applicant US2009 0204277 Method of estimating atmospheric data at any point of a path of an aircraft discloses a method for calculating the most likely weather model wind pressure temperature humidity at a given point of the flight path by using a grid of winds and atmospheric models. This allows discrete wind data values to be plotted against atmospheric models section by section along the flight plan in order to determine the most probable wind at any point. However this does not solve the problem consisting in displaying in an effective manner a developing situation around the 4D trajectory since it calculates the wind at a given point of the trajectory and does not display it elsewhere. It is just a method for calculating FMS predictions.

The document by the applicant US2007 179703 Process taking into account a local and favourable situation not conforming to a general meteorological forecast discloses a method for warning of predicted unfavourable wind along a flight plan. The wind is calculated in 4D on a 3D flight path including the time parameter in other words the spatio temporal variation of the wind allowing the weather vent pressure temperature to be determined and forecast at any point of a flight plan. This therefore allows the segments of the flight plan to be determined where an unfavourable wind will exist and a diversion to be proposed at these points. However as before this does not solve the problem consisting in displaying in an effective manner a developing situation around the 4D trajectory since it predicts the wind at a given 3D point of the trajectory and does not display it elsewhere. It is just a method for calculating FMS or ground predictions.

Other types of information are not shown with a range of time variation correlated with the predictions along the flight path. The extrapolations of data concerning the flight and their correlation with the predicted flight path are carried out manually.

The methods described in the aforementioned documents allow a correlation to be performed manually and at a given time the crew chooses a geographical region on their flight plan and the predicted weather information at this location at this time is displayed. However this does not give an overall view of the trajectory and makes the crew perform trial and error operations in order to estimate if a potential problem could exist at a given point.

One subject of the invention is a method for correlation of spatio temporal information with a 3D time trajectory incorporating mechanisms for automatic and manual filtering of the level of information and of the desired time range around the trajectory and including an improved representation of the time variation of geographical information.

More precisely the subject of the invention is a method for assisting the navigation of an aircraft equipped with

It allows spatio temporal data to be determined that is coherent with the 3D trajectory displayed by taking into account the time axis over forward time scales allowing the crew to capture on a single representation the predicted time variation of the situation without however cluttering the displays in order to preserve an optimum readability and appreciation of the situation.

The choice of the families to be displayed may be predetermined or determined by the crew or automatically.

According to one feature of the invention a degree of reliability being associated with data the formatting step is furthermore carried out by degree of reliability.

The families of data are typically a family of meteorological data and or a family of geographical data and or a family of navigational data and or a family of data supplied by the crew.

Sub families may be associated with data the assembly step is then furthermore carried out by sub families.

Another subject of the invention is a system for assisting the navigation of an aircraft which comprises 

The various steps of the method according to the invention are described with reference to the flow diagram in .

Step A extraction of the data insertion into a database BDD by families of data and potentially sub families of data.

This first step consists in acquiring the relevant data to be displayed via the various sensors and systems available. The lists provided hereinbelow are not exhaustive but allow the operation of the method to be understood. This data will form a database BDD within which they are assembled by families.

The following geographical data are extracted in the same way via digital data uplinks and by using on board charts 

The navigational data is extracted in the same way via digital data uplinks and by using on board Notams 

This step also allows data to be displayed to be manually defined either for replacing data that have not been digitized and are not therefore extractable for the other systems or available via datalink or for inserting proprietary data which do not belong to the list of data types expressed hereinabove.

In order to be exploitable by the following steps and as illustrated in the proprietary data are characterized by 

The set of these data values is integrated into a database BDD in which they are assembled by families examples of which are given in the step C.

Furthermore for data of the same type for example the wind data coming at the same time from the radar weather from the on board charts and from updates via digital data uplinks a tag ex WINDS and a degree of reliability in time or distance is associated with these data in order to allow the following steps to operate on this set of mutually coherent data and the data of different types to be well separated.

During this step the data values are formatted as a function of their type events scalars vectors surfaces and volumes all associated with a time window of validity. For an one off event the time window is reduced to a date of occurrence.

In order to guarantee the correct understanding of the operational situation by the crew and in order to allow them concentrate where necessary on the important parameters for the flight a selection step or filtering step for the data to be displayed is carried out so as not to clutter the overall display. A parameter presetting may be provided or defined by the policy of the airline via a software configuration.

A selection of the information to be displayed is made by family then by sub family and where appropriate by type of representation and or by priority of the information.

For each family and for each sub family examples of which are cited in the following part a priority not to be confused with the priority associated with each data value may be chosen by the crew so as to only display the required information. An selection HMI allows the priorities to be chosen for example P P P. In the example of choice of priority shown in it has been chosen to only show the selected data SEL is enabled and with a priority P i.e. strictly with a higher priority than P from amongst the 3 families selected in the preceding HMI in . As shown in this example in a geographical region at 10 NM and or a time window 20 min 40 min can also be selected.

For the data to be displayed around the trajectory or ALOFT AREA which is the display option indicated with and not in the latter the method according to the invention allows the spatial corridor around the trajectory within which the data will be displayed to be chosen. This may be a corridor of the lateral band type around the trajectory or a corridor of the circle around the trajectory type. By default only one corridor is provided but a different corridor by sub family could be provided. The corridor is lateral for lateral data a vertical corridor could also be defined for the displays on the vertical display screen.

The method also allows filtering of the data to be displayed according to the time window in which they occur with respect to the predicted times along the trajectory. Thus in the example hereinabove it may be choen to only extract the data occurring 20 min before and 40 min after the predicted time at each point of the trajectory. A choice of 0 min before and 0 min after allows the data to be displayed that is exactly temporally correlated with the trajectory. This functionality is illustrated in . In the example in the time window chosen is situated between 30 min and 30 min as indicated on the bottom right. However two cloud banks are overlapping 

Thus a bank of clouds intersecting the WPT may be masked by the bank of clouds intersecting the WPT. In the display time windows situated between 5 min and 5 min have been limited. The overlapping is thus avoided the visibility is improved.

According to one variant this selection of the time window for each family may also be carried out during the step E for correlation of the data with the trajectory.

The family METEO one example of which is shown in comprises the display mode and the following sub families 

The family CLOUDS one example of which is shown in comprises the display mode and the following sub families 

The family NAVAIDS GNSS one example of which is shown in comprises the display mode and the following sub families 

The category AREAS one example of which is shown in comprises the display mode and the following sub families 

The family CUSTOMS one example of which is shown in comprises the display mode and the sub families defined by the pilot 

In the example in the figure there are for example a contact reminder from the airline the service hours of the PNC flight personnel for the main cabin meals and a change of crew.

The family DAY NIGHT does not have any sub family. With a knowledge of the ephemerides and hence for a country traversed the sunset and sunrise times local time the UTC time is calculated with the local time offset of the geographical region. For example in a country where the time offset is 6 hrs i.e. it is 18 00 hrs when it is noon UTC and where the local sunrise time is equal to 07 45 the UTC time stored for sunrise will be 01 45.

In order to assist with the trajectory spatio temporal correlation and data for the following step an intermediate step for processing of the predicted trajectory is carried out. From the trajectory points en route straight segments and bends vertical profile in altitude and in speed predicted times of passage at the various points a characteristic point TRAJ i is saved given by 

For segments that are too long more than 3 minutes in length for example but the value may be chosen to be different the trajectory is discretized and characteristic points are added.

A succession of 3D geometrical elements characterized by a start time and an end time are therefore obtained.

Step E Trajectory spatio temporal correlation and data for determining the objects that intersect the trajectory the goal is to determine around each element TRAJ i of the trajectory the data geographically present according to a given spatial window and within a given time window with respect to the predicted time at the said element window X minutes Y minutes . The data to be displayed is sorted by verification of their distance with respect to the trajectory and by verifying their time of occurrence with respect to the predicted times along the trajectory.

Thus for the event sunrise or DAY a point DAY lat long alt time speed dist to dest tag DAY will have been created.

Its coordinates and parameters are interpolated. For example for the Dist to Dest Dist to Dest DAY Dist to Dest Dist to Dest Dist to Dest 1 time sunrise time time time 1 

Take for example the surface defined by the atmospheric layer at 0 where the risk of icing may arise in the case of traversing this layer within a wet region of the cloud type. This surface is composed of points called SURF lat long alt time for the icing for example. The surface is composed of contiguous facets each facet being a triplet of points SURF as shown in functions of the prior art are used such as Delaunay triangulation http en.wikipedia.org. wiki Delaunay triangulation used for digitizing mountainous areas by creation of a mesh which determines a matrix of facets approximating a surface.

In the example in the idea is to determine if the facet defined by the triplet SURF lat long Alt SURF lat long Alt SURF lat long Alt intersects the point TRAJ i in the red corridor with a radius R determined in the step C and in the time window determined by Time TRAJ i Start Time Time TRAJ i End Time .

The Euclidian distances are therefore calculated for example between each of the 3 points of each facet and the point TRAJ i .

If at least one of the points of the facet is located at a distance from the point TRAJ i that is less than the limit of the corridor here the radius of the ball of radius R centred on TRAJ i then the candidate surface is retained if the time of occurrence of the candidate points is in the time segment defined by Time TRAJ i Start Time Time TRAJ i End Time .

If the data is of the volume fields type the same operations are performed as for the surface fields by considering once again an approximation of the volume using polyhedra.

The representation of the important data is customized such as the priority data P intersecting the trajectory with a particular scheme such as a colour for example.

A display scheme is also provided for the data varying over time allowing its geographic displacement to be judged. For example an arrow between the centres of gravity of the objects.

In the examples in the trajectory traverses Iran IR Pakistan PK and India IN and information on various families are correlated over time. The figures respectively show 

The cloud development is highlighted with a coloured edge red for example at the moment where the storm cloud intersects the trajectory between WPT and WPT. Curved arrows allow the representations of the same cloud to be connected at different times the time is also displayed in the shape of the cloud.

Similarly the non availability of the whole GNSS constellation between 19 00 hrs and 19 38 when the aircraft will be at the point WPT is for example represented by a red pictogramme.

The same goes for the closing of the region Z when the aircraft will be at WPT and the maintenance of the beacon between 23 40 and 01 00 hrs for landing.

As indicated on the flow diagram in adjustments are subsequently made when there is a modification of the lateral or vertical trajectory by the crew or modification of the predicted data when the real conditions encountered by the aircraft result in a deviation from the predicted trajectory for example a slower real speed will modify the predicted times of passage at the points and will require updating a modification of the choice of the data to be displayed or a modification of the data to be displayed reception of a new chart manual modification of a customized input etc. .

The method according to the invention allows a representation to be made of the data connected with the 4D trajectory displayed by taking into account the time axis on time scales allowing the crew to capture on a single display the development of the predicted situation without however cluttering the displays in order to keep an optimum readability and appreciation of the situation.

It may furthermore be applied to any type of trajectory whether this be the trajectory followed by the flight or alternative trajectories for example work around alternative trajectories What if scenario with a presentation of the time correlated information for 

The method can be implemented in a computer of the FMS type or in an FM Flight Management function of a computer. shows an FMS disposing of the following modules described in the standard ARINC 702 Advanced Flight Management Computer System December 1996 . The provide all or part of the following functions 

Based on the flight plan defined by the pilot in the form of a list of passing points known as waypoints WPT the lateral trajectory is calculated as a function of the geometry between the waypoints commonly referred to as LEG and or the altitude and speed condition which are used for the calculation of the turning radius.

On this lateral trajectory the FMS optimizes a vertical trajectory in altitude and speed including potential constraints of altitude of speed or of time.

All of the information input or calculated by the FMS is assembled on display screens MFD acronym for Multi Function Display pages ND acronym for Navigation Display screens and PFD acronym for Primary Flight Display HUD acronym for Head Up Display or other .

According to a first embodiment described with reference to the BDD is hosted in the FMS as a new database in which the data from the equipment sensors etc. other than the FMS are stored.

Based on the selections carried out by the pilot the correlation of the time data is carried out by the module PRED together with the conditioning and the transmission of the data to the display screens the trajectory and the data being transmitted to the display screens in the cockpit Navigation Display and or Vertical Display .

Certain functions may be provided by modules integrated into an EFB Electronic Flight Bag an ANS Airport Navigation System i.e. ground taxiing system or a portable PC or tablet or lastly onto screens of ground tools with for example a dedicated correlation system.

According to a second embodiment described with reference to the FMS or EFB or ANS supplies the trajectory to the BDD. The other equipment ground or on board sends the data to be displayed in the BDD. A correlator is responsible for the exploitation of the data from the various pieces of equipment on the basis of pilot selections via the selection HMI. The correlator formats the trajectory and the data and sends them to the CDS for displaying.

According to a third embodiment described with reference to the correlation of the data with the trajectory is carried out by the CDS on the basis of pilot selections made via the selection HMI. According to this embodiment the FMS or EFB or ANS supplies the trajectory in the BDD. The other equipment ground or on board sends the data to be displayed in the BDD.

Other embodiments are possible in which the BDD is no longer a centralized database but each piece of equipment stores its data and during the correlation step the data from each piece of equipment is read.


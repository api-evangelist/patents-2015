---

title: System, method, and software application for displaying data from a web service in a visual map
abstract: The present invention provides a system, method, and software application for enabling a user to view data from an external data source in a visual map, wherein the external data source has a web services interface. Visual mapping software on a computer provides a visual mapping interface in which a user can create, edit, and/or view a visual map. Within the visual mapping interface, the visual mapping software provides the user with an option to obtain data from one or more data sources associated with a web service. In response to the user selecting a data source associated with a web service, the visual mapping software builds a web service request for the web service associated with the selected data source. The visual mapping application makes a call to the applicable web service with the web service request. The visual mapping application subsequently receives data from the web service and transforms the data into a format that can be used to generate visual map data. The visual mapping software then displays the data in a visual map.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09396282&OS=09396282&RS=09396282
owner: Mindjet LLC
number: 09396282
owner_city: San Francisco
owner_country: US
publication_date: 20150601
---
This application is a continuation of U.S. patent application Ser. No. 12 291 495 titled System Method and Software Application for Displaying Data from a Web Service in a Visual Map and filed on Nov. 10 2008 which is a continuation in part of U.S. patent application Ser. No. 10 882 556 titled System and Method for Graphically Illustrating External Data Source Information in the Form of a Visual Hierarchy in an Electronic Workspace which was filed on Jul. 1 2004. All of the foregoing parent applications are incorporated by reference as if fully disclosed herein.

This invention relates generally to visual mapping systems and more particularly to displaying data from a web service in a visual map.

Visual maps such as mind maps and topic maps provide an excellent way for users to view large amounts information in an organized graphical format. A visual map is a diagram that represents ideas and or information in topics. Examples of visual maps are mind maps topic maps semantic networks and concept maps. Visual maps are increasingly used to help people generate classify and or organize ideas and information and to see such ideas and information in a hierarchical visual layout. Visual maps are used for project management work flow analysis organizational charts and other purposes.

Users typically create visual maps using proprietary visual mapping software. Mindjet LLC s MINDMANGER and MINDJET CONNECT are examples of such software.

The Internet and the World Wide Web the Web have made a wealth of information available to Internet users. Many companies and other entities have made data available via Web Services web services . Web services are a web based interface to a data source. A computer can make a call to a web service based on the web service s published API application programming interface . For example a company with a CRM system may have a web service interface to the CRM system. This means that the CRM data can be obtained by a program that makes a call to the web service associated with the CRM system.

It would be desirable to enable a user to view web service data within a visual map. Therefore there is a need for a visual map interface from which a user can initiate a web service call.

The present invention provides a system method and software application for enabling a user to view data from an external data source in a visual map wherein the external data source has a web services interface. A web service is a service made available from an entity s web server and accessible on the World Wide Web via the Internet.

Visual mapping software on a computer provides a visual mapping interface in which a user can create edit and or view a visual map. Within the visual mapping interface the visual mapping software provides the user with an option to obtain data from one or more data sources associated with a web service.

In response to the user selecting a data source associated with a web service the visual mapping software determines whether or not the web service is associated with any user configurable parameters. If so the visual mapping software enables the user to enter user configurable parameters.

After a user has entered any user configurable parameters the visual mapping software builds a web service request for the web service associated with the selected data source. The visual mapping application makes a call to the applicable web service with the web service request. The visual mapping application subsequently receives data from the web service and transforms the data into a format that can be used to generate visual map data. The visual mapping software then displays the data in a visual map.

In an alternate embodiment of the invention the user need not initiate the web service request. In such alternate embodiment the visual mapping software automatically makes a web service call for example upon launch of a visual map and display the data from the web service in a visual map.

The present invention provides a system method and software application for enabling a user to view data from an external data source in a visual map wherein the external data source has a web services interface.

A web service is a service made available from an entity s web server and accessible on the World Wide Web via the Internet. A web service is a way to obtain data from an entity via a web interface. A computer can make a call to a web service based on the web service s published API application programming interface . For example a company with a CRM system may have a web service interface to the CRM system. This means that the CRM data can be obtained by a program that makes a call to the web service associated with the CRM system.

Referring to visual mapping software on a computer provides a visual mapping interface in which a user can create edit and or view a visual map step .

Within the visual mapping interface the visual mapping software provides the user with an option to obtain data from one or more data sources associated with a web service . Examples of the type of data that can be obtained from a web service include 

There are multiple ways in which a user can initiate a web service request within the visual mapping interface. For example the visual mapping interface may include icons representing data sources associated with a web service and a user may click on one of the icons to import data from such data source.

In response to the user selecting a data source associated with a web service step the visual mapping software determines whether or not the web service is associated with any user configurable parameters step . If so the visual mapping software enables the user to enter user configurable parameters step . In one embodiment the visual mapping software provides a dialog box or form into which user can enter user configurable parameters.

After a user has entered any user configurable parameters the visual mapping software builds a web service request for the web service associated with the selected data source step . The web service request is built in accordance with the API for the web service. If the user has entered user configurable parameters for the search the web service request includes the user configurable parameters as well as any default parameters associated with the selected search domain. If there are no user configurable parameters then the web service request includes default parameters if any .

After building a web service request the visual mapping application makes a call via the Internet to the applicable web service with the web service request step . The visual mapping application subsequently receives data from the web service step . The visual mapping software transforms the data obtained from the web service into a format applicable to visual maps step . For example it is common for web service results to be in the form of XML. In such case the visual mapping application may perform an XSLT transformation on the received data to transform it into an XML format from which a visual map can be generated. The visual mapping software then displays the data in a visual map step .

In the method of a user initiates the web service request from a visual mapping interface. However in an alternate embodiment of the invention the user need not initiate the web service request. In such alternate embodiment the visual mapping software automatically makes a web service call for example upon launch of a visual map and display the data from the web service in a visual map.

In one embodiment when a user selects a data source associated with a web service the visual mapping software retrieves a web service definition for the data source. A web services definition specifies i the parameters associated with the web service request ii the requirements for building a web service request and iii instructions on how to handle and transform the data returned from the web service request.

In the present example the user selects a search domain by either i dragging an icon representing a search domain to a topic with search terms or ii selecting a topic with search terms and clicking on an icon representing the search domain.

In a user has selected topic in visual map interface and clicked on the GOOGLE icon to initiate a GOOGLE search for Lung Cancer. 

In the example of the number of search results displayed is a user configurable parameter. When a user selects the GOOGLE search domain a dialog box appears . The dialog box includes a Results field into which a user can specify the number of search results he she wants to see in the visual map. A default parameter may initially be displayed in field . The dialog box also includes a search terms field i.e. the Look for field . In this example the default entry for search terms field is Lung Cancer as these are the terms entered into topic . Dialog box gives the user the opportunity to change the search terms.

After the user selects the OK button in dialog box the visual mapping software builds a web services request for GOOGLE where the request specifies that the search terms are Lung Cancer and the number of search results desired is ten. The GOOGLE web service then returns the top ten search results for Lung Cancer on the GOOGLE search engine. illustrates the results from a Google search of Lung Cancer displayed in a visual map.

The visual map in includes a topic that indicates that GOOGLE was the search domain associated with the search results displayed. In this example topic was added as a subtopic to topic in response to the user selecting GOOGLE as the search domain. Topic is referred to herein as a web services map part the Google icon is also considered a map part that became topic . By displaying data from a web service as subtopics to a web service map parts in the map a user viewing the map can see the web service that was used to obtain data. This can be helpful if the user viewing the map was not the user who created the map.

Web service map parts can be added at any level of the map. For example in a search web services map part can be added as a subtopic to i the central topic Cancer Research ii the Lung Cancer topic or iii any of the search results displayed in . In addition a web services map part can be the central topic of a map. In one embodiment a web services map part is a type of content specific topic where one of the properties of the topics is that is able to make a call to a web service e.g. software code capable of performing the method of is compiled into the topic . A content specific topic is designed specifically for a type of content. One implementation of content specific topics are described in U.S. patent application Ser. No. 11 478 220 titled System and Method for Providing Content Specific Topics in a Mind Mapping System and filed on Jun. 29 2006 the contents of which are incorporated by reference as if fully described herein.

In system a user can create visual map from a visual mapping desktop client or a visual mapping web client . These visual mapping clients are served by a visual mapping server . Mindjet LLC s MINDJET CONNECT is an example of a visual mapping server application. After a user creates or edits a visual map the visual mapping client or sends the map data to the visual mapping server which stores the data in a file system or a database . Visual maps with web service data can be saved and shared with other users. In one embodiment web services data is refreshed when a map with a web services map part is opened i.e. a web service call is made each time the map is opened .

A visual map can be stored as a file or the topics in a map can be stored in individually in a database as described in U.S. patent application Ser. No. 12 001 533 titled System and Method for Enabling a User to Search and Retrieve Individual Topics in a Visual Mapping System which was filed on Dec. 12 2007 and which is incorporated by reference as if fully disclosed herein.

The method of can be implemented by the visual mapping client or in conjunction with the visual mapping server . The method of can also be implemented by visual mapping software running in an external application such as the visual mapping software with the network module described in the U.S. patent application titled System Method and Software Application for Enabling a User to View and Interact with a Visual Map in a Non Visual Mapping Application filed on Nov. 10 2008 and having inventors Neil S. Mendelson William J. Creekbaum and Andriy O. Mochalskyy the content of which are incorporated by reference herein.

As will be understood by those familiar with the art the invention may be embodied in other specific forms without departing from the spirit or essential characteristics thereof. Accordingly the above disclosure of the present invention is intended to be illustrative and not limiting of the invention.


---

title: Isolation of objects representng server resources in browser using iframes
abstract: Method for web-based management of resources. On a cloud computing system, for groups of user resources, defining commonly managed subgroups. Accessing cloud-based control procedures of one subgroup using a dedicated communication channel. Control procedures reside on a server, and are visible with a single specified domain ID unique for the subgroup. Multiple domain IDs are used in one communication session. On the client, isolated windows for each domain ID contain graphical representation of local applications, and where applications of one window share local data and are connected to control procedures using the same domain ID. Managing user resources through control procedures that are controlled by the applications. Only one of the isolated windows is activated at any one time on the user's computer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09398017&OS=09398017&RS=09398017
owner: Parallels IP Holdings GmbH
number: 09398017
owner_city: Schaffhausen
owner_country: CH
publication_date: 20150501
---
This invention relates to a method for a universal interface for controlling Virtual Machines VMs Containers Virtual Private Servers VPSs server based applications and other isolated objects controlled by network users through a browser displaying multiple sub windows.

Providers have multiple applications running in different environments such as VMs Virtual Servers server based application and other isolated objects. Currently there is no interface that can securely control and separate these applications from a central location. For example VM resources antivirus AV resources for the email AV resources for the VM or container separate from email backup payment store interface e.g. to collect credit card data and permit purchase Office 365 or similar resources and mailbox resources appear on the same browser page the user can affect and modify these resources using any of the code of this page even if they are encapsulated into different subwindows. In other words any browser user and any code running in that browser has random access to all resources within any browser window and sub window. This can result in loss of security for the objects and resources that interface to an iframe that should not be affected.

Accordingly a method for secure operations with objects which require isolation and also with services and resources controlled by network is desired.

Accordingly the present invention is related to a method for a universal interface for controlling of services and resources over network through browser that substantially obviates one or more of the disadvantages of the related art.

A generic universal interface description according to the invention is encapsulated or insulated into a code container. The container stores a special code e.g. HTML used by a browser with supporting code isolation technology. The browser can have several windows or code representation with established borders on one page or it can use window placeholders that overlap each other. Such a windows have control elements or active iframe content defined in a generic form but related to connected control entities. One example of such a container for generating such windows is an iframe. In spite of the fact that conventional iframes have limited functionality the following text will use the term iframe for both isolated windows on the user hardware display and for code that insulates certain interfaces in an isolated pool which produces a required level of security according to the invention.

The applications iframe and panel are placed on different domains. This provides for code isolation at a browser level. In other words the code written inside the iframe does not interfere with the code of the main window. Thus the user feels as if he were working in one window i.e. viewing one page . The user simply sees a web page and does not even know that this page is a sub page or a portion of a larger iframe. This provides a desired level of security i.e. the resources are isolated from services and the application does not have a direct access to the resources.

In another embodiment a method for universal interface for isolation of services and resources. On a computer executing code for downloading a webpage in a browser the webpage interfacing to a server through a unified interface for managing browser objects and server resources the webpage including a plurality of iframes such that each iframe is associated with an application running on a server the application having a corresponding browser object. One of the browser objects is a control panel for managing the server resources the server resources including server applications. One of the server applications includes at least one virtual environment. Displaying on the webpage a control panel for managing the server applications and for allocating the server resources. The iframes are isolated from each on a domain name level such that code in one iframe cannot affect code in another iframe without permission. Each application is associated with its own domain or sub domain.

In another embodiment a method for web based management of user s resources. On a cloud computing system for a plurality of groups of user resources placed in the cloud defining subgroups of resources whose settings are commonly managed. From a user s computer accessing cloud based control procedures of one subgroup using a dedicated communication channel. The control procedures reside on a server and are visible with specified domain ID single and unique for the subgroup on a cloud side. Multiple domain IDs are used in one communication session between the server and the user s computer.

On the user s computer starting isolated windows for each domain ID that contain graphical representation of local computer applications placed on the user s computer and where applications of one window share local data and are connected to the control procedures using the same domain ID. Managing user resources through the control procedures that are controlled by the applications. Only one of the isolated windows is activated at any one time on the user s computer. When a control procedure is controlled by several applications belonging to separate windows a separate communication channels with a separate domain ID is established for each window.

A security token is given the rights to control resources of a particular application only for a certain account. Trusted relationships are established among the applications installed by a provider. The isolation in accordance with the exemplary embodiment takes place on the client.

Additional features and advantages of the invention will be set forth in the description that follows and in part will be apparent from the description or may be learned by practice of the invention. The advantages of the invention will be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Reference will now be made in detail to the preferred embodiments of the present invention examples of which are illustrated in the accompanying drawings.

Virtual Machine VM a type of an isolated Virtual Environment running on the same physical machine simultaneously such as for example available from Microsoft Corp. VMware Inc. or Parallels Software International Inc. Each Virtual Machine instance executes its own OS kernel. Support of the VMs is implemented using a Virtual Machine Monitor and or a Hypervisor.

Container Virtual Private Server one type of a Virtual Environment running on the same hardware node with a single shared OS kernel and most of the system resources where isolation of the Container is implemented on the namespace level. A container acts as an isolated virtual server within a single machine where multiple sets of application services are organized on a single hardware node by placing each into an isolated virtual container.

The present invention is directed to a method for universal interface for isolation of services and resources controlled by network users through browser iframes. For example mailbox application can control mail boxes or an application can control anti virus settings and operations but it cannot modify or delete VMs or containers and it should not be able to modify other iframes and their corresponding applications objects and corresponding resources and services without permission.

This isolation is provided across the board from a server code to the client code. This is implemented by separation at the iframe level. Each application runs on its own sub domain of the domain specified in the address bar. This guarantees that the application cannot access anything in another iframe from a different domain. The domain address specifies the application access rights on the server as well. All requests are encapsulated within the iframe located at a certain address.

Each iframe does not have access to other iframes or to the control panel except when explicitly permitted. According to the exemplary embodiment a generic universal interface description is encapsulated into a virtual environment container VPS or VM . The virtual environment stores a special code e.g. HTML used by a browser supporting iframe technology. The browser can have windows on one page or it can use window placeholders that overlap each other. The windows have control elements or active iframe content defined in a generic form but related to connected control entities.

For example one application can create VMs and another application can create payment tokens. These applications need to be isolated so the application that controls the VMs or the mail does not interact with the application controlling the payment methods. Accordingly the iframes can be called billing and service. Particular control elements are defined by a user and the environment. In one embodiment when a browser or an application is unpacked a semantic analysis of control elements built into the environment i.e. container VM or hosting system is performed and the elements are grouped based on the semantic analysis.

If the placeholder does not have at least one corresponding element the placeholder is not activated. According to the exemplary embodiment each placeholder has to correlate to a certain security policy. For example a resource visibility placeholder can reflect all resources of environments available to the user. The user authorizes himself to the system using centralized authorization e.g. Facebook authorization provides access to all his system resources . Note that when the resources are displayed the iframe prohibits resources from controlling each other control other system elements and request data from other resources.

In case if the requested by user information requires interaction of the resources for read operations the iframe is created at domain level i.e. the window reflects elements belonging to one domain. Resources interaction is possible when domain resource performs calculations or other processing of data. This approach provides for isolation of groups of resources of one user. However domain association can be somewhat abstract including broadcasting of domain association. For example resources of Apache servers can be isolated artificially.

Another authorization method is assigning to all resources a window of secure token. Display of the resources in the window is possible only after validation of the token. If the resources in the window have different tokens some resources are deactivated or the entire window is deactivated. After the validation the data exchange can be implemented over the ifame only using a secure protocol such as SSH.

When the application is unpacked the resources corresponding to the iframes are requested and the resources are grouped according to their domains. The security certificates of authorization centers are used. A starting page of the application is generated for the user and label is created. The user opens the placeholders sequentially acquires the information and controls the execution environments. In case when the interaction between the control elements for different placeholders is required a new placeholder with corresponding rights is created.

According to the exemplary embodiment applications iframe and control panel are placed on different domains in order to provide code isolation at a browser level. The rights for controlling the resources of a given application are added to the security token for the given account. Trusted relationships between the applications are set by a provider.

According to the exemplary embodiment APS Application Provisioning Standard allows creating custom user interface UI that can be plugged into different types of control panels CPs such as provider CP and customer CP. Each type of CP has its own placeholder socket to which the APS custom UI navigation tree can be plugged. In the example depicted in the navigation tree VPS Management is plugged into the customer CP.

Navigation serves as a switch between placeholders corresponding to browser sessions. Note that each tab in a browser can correspond to its own session with its own set of security rules. The set of security rules for each iframe is a subset of the session security rules and the session security rules are a superset of all the security rules for all the iframes that make up a browser tab. The security rule set may be different for different tabs.

All services are combined within one control panel but the user should not experience any differences when working with different services i.e. the tables are rendered in the same way and the navigation has to be the same making operating with the different applications through the different iframes completely seamless. The navigation provides switching between views of different applications residing in different iframes rendered to the user. The menu elements are drawn by the control panel and displayed as placeholders. Note that navigation between menu items is separated from the contents displayed in the iframes. In one embodiment this means that any action performed inside any iframe does not affect content outside the iframe border. And vice versa the content of the iframe may be affected by only elements located inside the iframe. To protect a user against erroneous or malicious actions the inactive or similar sign may be placed in a visible part of the iframe shown in the background in process of switching between iframes for example. The control panel can draw these elements in a different manner at a later time. A user can switch between these elements while the iframe code is not affected. In other words the navigation between the iframes is isolated from the content of the iframes. This makes the user interface very smooth seamless in terms of navigation.

Metadata in the APP META.xml file must define one or more navigation trees that can be plugged into specified placeholders placeholders of different control panels 

Each navigation tree contains one or more navigation items that together make up the skeleton of the navigation tree 

Each navigation item may contain one or more visibility components. Visibility refers to displaying or hiding of navigation elements. For example a screen can have several elements but some of them are not shown. Each visibility is mapped to a screen in a CP. For example AV elements placeholder and mailbox elements placeholder can be combined and shown on the same navigation map. However if the user did not buy an AV component the corresponding placeholder is made invisible. In a CP screen the contents of a visibility is presented by an HTML file. The CP places a visibility marker inside an HTML iframe.

Normally an HTML file contains HTML and JavaScript code that provide all necessary widgets to a user for managing application resources.

The entire simplified high level APS UI architecture can be represented as shown in . The exemplary architecture has the following key features 

A typical view may be built from several groups of control elements controls . Visual controls are defined and processed by HTML and javascript code 

Model controls are used for effective management of data in the user browser and for interacting with the APS controller 

The Store control manages the asynchronous communication with the APS controller. It implements the REST operations POST GET UPDATE and DELETE.

The Model control if bound to a widget establishes the 2 way synchronization with the widget. If the widget value is changed it will be synced with the Model. Usually when navigating to another view the javascript code takes care of syncing the Model with the Store control and saving the data in the APS database.

A navigation tree tells a CP where a certain visibility must be embedded. APS UI can be represented by a navigation tree similar to the example depicted in . It contains a number of navigation items Servers Network IP Addresses and Firewall. The diagram also specifies visibilities in some navigation items and the HTML files implementing the visibilities. For example the Servers item contains several visibilities 

The visibility HTML files and all auxiliary files are collected in the UI folder of the APS package as presented in the example depicted in .

In a CP an APS UI visibility is embedded into an HTML iframe through a special object called visibility context which structure is presented in the example provided in the Appendix i.

The objects defined in the visibility context are available for the JavaScript code in the visibility file. For example the varName1 variable is available as aps.context.vars.varName1. Note that the aps.context object is available in a visibility file if the aps.ready object from the APS JS SDK is required in the file.

A system control panel embeds an APS navigation tree and renders a selected visibility using several steps outlined below 

3. In the response get the JSON representation of the current screen menu items visibility and representations of resources declared by variables in the navigation section 

4. Render item elements as menu elements. For example in the PA Customer CP a navigation item is presented by a tab 

5. Initialize the aps.context JS object with the security token navigation variables locale etc. This object will be passed to the target iframe and parsed by the aps ready plugin.

The use of APS permits backend and UI integration of different distributed services semantically bound with the following capabilities 

 1 unified lookup engine using multiple inheritance and unified sockets containing security descriptors and description or indication of interface on the client browser side 

 2 automatic provision unprovision flow e.g. a user can create a VM and physical server will be created automatically using depend resolving mechanism . If a separate object had been created during session the iframe was opened with isolated content inside it 

 3 common data cache database with runtime generated schema used by different services apps. A new table or emulation of a new table in a database is created for each iframe or isolated window. This is different from Relational Database Management Systems where a schema is defined at compile time and NoSQL databases where schemas are not defined at all.

 i Common and consistent user experience. A limited set of control representations can be used. Each set of controls works with an isolated database table.

 ii security isolation each application is isolated inside its own sandbox iframe and different domains leveraging same origin policy security tokens that allow to isolate data . One security token works inside only one frame. If the server side contains the application used in different frames then several instances are created or several sessions with one application are established.

According to the exemplary embodiment development of the APS custom UI for an application requires the following three steps depicted in 

According to the exemplary embodiment a control panel CP allows a user to navigate to any visibility specified in the navigation tree as shown in . There are two navigation approaches 

 a Navigation is the root element in the tree. The element declares it. Different types of CP can visualize this element differently. For example in a Parallels Automation CP when using an APS predefined placeholder it is represented by a top level tab.

 b Item creates a tree branch by means of the element. An item is bound to the element or to another item its parent. The element and several elements create the tree skeleton. There are no loops in the tree. In a CP an item is visualized as a tab.

 c Visibility corresponds to a screen in a CP. A element defines a navigation visibility and it is bound to an item or to another visibility. The one that is bound to an item will be activated when the item tab is selected in a CP.

 d Group is similar to an item. The only difference is that it is not visualized. One can use it to group some items in order to assign the same variable for them or plug them to a certain placeholder.

 e Placeholder reserves a place where navigation elements of other applications can plug to. It must have a unique ID in the form of URI. To plug a navigation element to it the element must refer to the placeholder ID.

Dynamic navigation is important as it implies navigation from a visibility to another visibility by calling a navigation method and specifying the destination visibility ID. It is possible to use two different types of dynamic navigation 

According to the exemplary embodiment navigation can present several problems that are solved by a proprietary RESTful API navigation 

The purpose of the API is to implement a simple logic of navigation of APS2 in the panels. Only the navigation primitives that a panel can draw based on context are returned. The context can represent a selected screen plus a stack of selected resources. A set of such primitives produces a cross section of the navigation. The attributes item visibility wizard in the navigation primitives will be already calculated. The panel performs the rendering function e.g. item tab visibility iframe wizard group of screens with a corresponding header .

A basic URL navigation is used. This URL contains the entire navigation tree available to the user according to subscription.

According to the exemplary embodiment a controller navigation API is implemented on node.js a server that allows for writing write a navigation code in JAVA script for emulation. The API monitors system resources detects new resources and resource quotas being exceeded. The API also refreshes or hides a control element in a new control panel. Note that only visible control elements can be used by the user. All the client side traffic can go through the same bus so the Navigation API can control all resources. The provider can disconnect an application from all other applications if it finds out about a bug or critical vulnerability.

According to the exemplary embodiment the size of the browser page is automatically adjusted based on the content of the iframe. The content of the iframe is constantly monitored in order to adjust the size of the browser page. Scrolling can appear on the page if necessary but the user does not see any scrolling in the iframe window it just changes its size for better user experience.

In order for the application to work it is necessary that APP META.xml aps2 of the application has a navigation section. All declared in the navigation variables has to be accessible. APP META.xml of the application is located in directory usr local pem APS packages . In order to find the packet id a size of a zip file with application name can be compared against other zip file. If the sizes match it means that this is a copy of the application and the id can be determined.

A first request has to be placeholder http www.parallels.com pa ccp 1 top APS Token. In order to check the requests the plugin PostMan for Chrome can be used. The headers are APS Token 1 Content Type application json. The application parameters are port port used for listening by the application default 9998 base URL base URL for controller default http localhost 8080 aps 2.

After the navigation merge an ambiguity can arise. According to the exemplary embodiment the application is isolated at variable level as well in order to resolve ambiguity. Thus the variables only work in the context of a given application navigation tree. Note that read is performed over the navigation channel as well as over a direct access to APS bus channel while write is performed only over the APS channel. Thus the common channel can be used for all tabs used for reading.

Each navigation element implicitly points to its own visibility field. In the visibility field all variables of this field are visible along with all variables in all parent visibility fields only within a corresponding navigation element of navigation. The values of variables are global for a given request and are defined by the context provided with the request. In case the resource cannot be found in the context a search of resource of the given type is performed in the user account i.e. a corresponding APS Token . If more than one resource is present an error is generated.

A navigation model is depicted in . All navigation elements are inherited from a base type NavItem Navigation Item Visibility . The navigation is represented in the memory as a tree. Two types of references parent children are needed for convenience of using the tree. All NavItems are related to each other as 1 n. Each NavItem can contain several variables. Each item represents variable scope. The scope a visibility field defines a set of available variables. The variables within the scope are combined with the parent ones.

When a model is calculated the variables available to the given navigation element are used. Only the variables of a type that corresponds to or inherits the type within the visibility field of the navigation element are available. Names of the variables in the expressions sent in JavaScript correspond to the name of variable in the visibility field of the navigation element.

2. Receive representation of a navigation model of each of the received applications in the memory i.e. representation of navigation of application 

3. If available in cache take it from the cache. Otherwise disassemble the navigation section in APP META if necessary disassemble the entire APP META 

4. Index all navigation elements dictionaries maps from the section by key id. The index must be global e.g. placeholder and plugs to 

a. Find all representations of navigation having plugs to elements with the same ID as in the received placeholder id request 

b. Unite the above into a common list by creating a tree of references to the model elements parent children src a reference for presenting a navigation built in the previous step 

h. If the operation in plugs to is omitted or operation insert insert parent plugs to as a child of the placeholder with the same id of corresponding navigation element a deep copying of the elements except for variable scope is performed 

j. In case of insert or replacement it is necessary to begin a pass through inserted navigation elements. Thus initial data is mutable 

6. Build a dynamic model consisting of static elements dynamic navigation elements and screens visibility .

7. If the visibilityID is provided find in the static model corresponding navigation element by index 

If required and resources to which it is mapped loaded in step the process adds element to the navigation results. Otherwise the process moves back to step . In step the process drops all into navigation element Stores breadcrumb a navigation element for VPS management see Returns result.

Objects managed by APS controller may be split into the collections each with its own base path. Here UI navigation collection aps 2 navigation may contain custom navigation tree for remote control panel and collection of data required for establishing the iframe. Another collection aps 2 ui runtime may contain data and procedures related to communication between applications which are protected from communication directly. An application is available for the APS controller usually through a single APS application HTTPS REST endpoint. In some cases more endpoints can be used.

Each application service that is a factory of resources within a specific type is presented as a separate URI. In certain embodiments APS controller can operate an application instance as a resource through procedures similar to usual procedures with other resources however there are also several operations affecting the entire selected application instance.

As shown in the APS applications can request the APS controller to operate resources in accordance with granted permissions. In the examples the requester may be a user however an application instance can initiate similar operations as well.

An APS application can initiate operations over its own resources through the APS controller using application alias. The APS controller as the service bus authority interacts with other APS participants application instances and users through UI . These three types of actors authenticate identify themselves in the following way 

Each application instance uses own application client certificate when interacting with the APS controller.

The UI when interacting with the APS controller authenticates the active user by means of the user or account token. The received token allows the APS controller to further identify the actor whether it is the provider or a reseller or a customer or an end user.

A token is generated for an account e.g. a staff member or an end user for a limited period of time and may be optionally refreshed while the owner of the token shows activity. In an exemplary embodiment the token for the iframe has been invalidated after the iframe is closed. Here the iframe may be active while refreshing or reloading web pages containing the iframes. An application certificate is generated by the APS controller and passed to the application instance.

With reference to an exemplary system for implementing the invention includes a general purpose computing device in the form of a computer system or the like including a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit .

The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. The system memory includes read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help transfer information between elements within the computer such as during start up is stored in ROM .

The computer may further include a hard disk drive for reading from and writing to a hard disk not shown a magnetic disk drive for reading from or writing to a removable magnetic disk and an optical disk drive for reading from or writing to a removable optical disk such as a CD ROM DVD ROM or other optical media. The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The drives and their associated computer readable media provide non volatile storage of computer readable instructions data structures program modules and other data for the computer .

Although the exemplary environment described herein employs a hard disk a removable magnetic disk and a removable optical disk it should be appreciated by those skilled in the art that other types of computer readable media that can store data that is accessible by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges random access memories RAMs read only memories ROMs and the like may also be used in the exemplary operating environment.

A number of program modules may be stored on the hard disk magnetic disk optical disk ROM or RAM including an operating system . The computer includes a file system associated with or included within the operating system one or more application programs other program modules and program data . A user may enter commands and information into the computer through input devices such as a keyboard and pointing device . Other input devices not shown may include a microphone joystick game pad satellite dish scanner or the like.

These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but may be connected by other interfaces such as a parallel port game port or universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor personal computers typically include other peripheral output devices not shown such as speakers and printers.

The computer may operate in a networked environment using logical connections to one or more remote computers . The remote computer or computers may be another computer a server a router a network PC a peer device or other common network node and typically includes many or all of the elements described above relative to the computer although only a memory storage device has been illustrated. The logical connections include a local area network LAN and a wide area network WAN . Such networking environments are commonplace in offices enterprise wide computer networks Intranets and the Internet.

When used in a LAN networking environment the computer is connected to the local network through a network interface or adapter . When used in a WAN networking environment the computer typically includes a modem or other means for establishing communications over the wide area network such as the Internet.

The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

Having thus described a preferred embodiment it should be apparent to those skilled in the art that certain advantages of the described method and apparatus have been achieved.

It should also be appreciated that various modifications adaptations and alternative embodiments thereof may be made within the scope and spirit of the present invention. The invention is further defined by the following claims.


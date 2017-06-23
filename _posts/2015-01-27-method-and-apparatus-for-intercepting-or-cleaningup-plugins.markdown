---

title: Method and apparatus for intercepting or cleaning-up plugins
abstract: The present invention discloses a method and apparatus for intercepting or cleaning-up plugins. The methods may include: obtaining performance attributes of a plugin; determining if the plugin meets a performance criterion based on the obtained performance attributes and empirical data; and intercepting or cleaning-up the plugin if the plugin does not meet the performance criterion. In accordance with embodiments of the present invention, the performance attributes of a plugin can be evaluated to determine whether the plugin meets a preset performance criterion, and the plugin can then be processed according to the result of the determination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09531734&OS=09531734&RS=09531734
owner: TENCENT TECHNOLOGY (SHENZHEN) COMPANY LIMITED
number: 09531734
owner_city: Shenzhen
owner_country: CN
publication_date: 20150127
---
This application is a continuation of International Patent Application No. PCT CN2013 079482 entitled Method and Apparatus for Intercepting or Cleaning up Plugins filed on Jul. 16 2013 which claims the benefit and priority of Chinese Patent Application No. 201210264230.X entitled Method and Apparatus for Intercepting or Cleaning up Plugins filed on Jul. 27 2012. The entire disclosures of each of the above applications are incorporated herein by reference.

The present invention relates to plugin detection technologies and more particularly to a method and apparatus for intercepting or cleaning up plugins.

In the prior art plugin interception or cleanup is generally based on the malicious acts or reputations of the plugins. For example malicious plugin like Adware or Spyware monitors the internet activities of user terminals and sends the recorded data to a remote monitoring center for the purposes of advertising or stealing game or bank account passwords which causes severe adverse effects on user terminals.

However some plugins are not malicious have some useful functions but may consume large amount of resources at the user terminal when they are running Such plugins are usually not blocked or cleaned up by security software and are not easily found by the user terminal.

Since the current security software only blocks or cleans up plugin based on maliciousness it may miss some plugins which could affect the stability of the user terminal system.

The present invention aims to provide a method for intercepting or cleaning up plugins to ensure a more complete interception and cleanup of the plugins and enhances the stability of the system.

In accordance with embodiments of the present invention a method for intercepting or cleaning up a plugin is provided the method comprising obtaining performance attributes of a plugin determining whether the plugin meets a performance criterion based on the performance attributes and empirical data and intercepting or cleaning up the plugin if the plugin does not meet the performance criterion.

Preferably the method further comprises monitoring activity of the plugin in a user terminal wherein the activity is selected from a group comprising installing loading and running of the plugin identifying the plugin based on the monitored activity and obtaining performance attributes of the plugin when the plugin is identified.

Preferably the method further comprises after identifying the plugin based on the monitored activity evaluating performance attributes of the plugin when the plugin is not identified determining whether the plugin meets a performance criterion based on the performance attributes and empirical data and intercepting or cleaning up the plugin if the plugin does not meet the performance criterion.

Preferably the method further comprises prior to obtaining performance attributes of the plugin obtaining empirical data of the plugin wherein the empirical data comprises plugin importance data plugin performance data and or end user review data and determining whether the plugin meets the performance criterion based on the empirical data.

Preferably the empirical data obtained through plugin testing backend collection and or web crawling backend collection comprises frontend collection and end user review frontend collection comprises hook mode and notification mode plug testing comprises testing the plugin in an automatic module to obtain information on the plugin s CPU usage load time and or memory usage hook mode comprises using a hook to obtain a start time and an end time for loading the plugin a start time and an end time for running the plugin and information on the plug s CPU usage and or memory usage while the plugin is loading and running reception mode comprises a client directly notifying starting and ending of loading and running of the plugin end user review comprises collecting reviews of end users on the performance of the plugin web crawling comprises crawling search engine data and or website review data to evaluate the performance of the plugin and the empirical data is stored in a remote cloud database or a local database.

Preferably determining if the plugin meets the performance criterion based on the performance attributes and empirical data comprises matching the performance attributes with empirical data stored on a cloud database obtaining a preset determination result after a successful match and determining whether the plugin meets the performance criterion based on the preset determination result.

In accordance with embodiments of the present invention an apparatus for intercepting or cleaning up a plugin is provided the apparatus comprising a performance acquisition module for obtaining performance attributes of a plugin a first performance determination module for determining whether the plugin meets a performance criterion based on the performance attributes and empirical data and a plugin processing module for intercepting or cleaning up the plugin if the plugin does not meet the performance criterion.

Preferably the apparatus further comprises a plugin monitoring module for monitoring activity of the plugin in a user terminal wherein the activity is selected from a group comprising installing loading and running of the plugin identifying the plugin based on the monitored activity and obtaining performance attributes of the plugin when the plugin is identified.

Preferably the apparatus further comprises a performance evaluation module for after identifying the plugin based on the monitored activity evaluating performance attributes of the plugin when the plugin is not identified wherein the first performance determination module is configured for determining whether the plugin meets a performance criterion based on the performance attributes and empirical data and the plugin processing module is configured for intercepting or cleaning up the plugin if the plugin does not meet the performance criterion.

Preferably the apparatus further comprises an empirical data acquisition module for obtaining empirical data of the plugin wherein the empirical data comprises plugin importance data plugin performance data and or end user review data and a second performance determination module for determining whether the plugin meets a performance criterion based on the empirical data.

Preferably the empirical data obtained through plugin testing backend collection and or web crawling wherein backend collection comprises frontend collection and end user review frontend collection comprises hook mode and notification mode plug testing comprises testing the plugin in an automatic module to obtain information on the plugin s CPU usage load time and or memory usage hook mode comprises using a hook to obtain a start time and an end time for loading the plugin a start time and an end time for running the plugin and information on the plug s CPU usage and or memory usage while the plugin is loading and running reception mode comprises a client directly notifying starting and ending of loading and running of the plugin end user review comprises collecting reviews of end users on the performance of the plugin web crawling comprises crawling search engine data and or website review data to evaluate the performance of the plugin and the empirical data is stored in a remote cloud database or a local database.

Preferably the first performance determination module is further configured for matching the performance attributes with empirical data stored on a cloud database obtaining a preset determination result after a successful match and determining whether the plugin meets the performance criterion based on the preset determination result.

In accordance with embodiments of the present invention the performance attributes of a plugin can be evaluated to determine whether the plugin meets a preset performance criterion and the plugin can then be processed according to the result of the determination. The embodiments of the present invention are primarily directed to evaluate and process plugins that are being installed loaded or running if the plugin does meet the performance criterion it will be intercepted if being installed and cleaned up if being loaded or running.

To better illustrate the technical features of the embodiments of the present invention various embodiments of the present invention will be briefly described in conjunction with the accompanying drawings.

It should be noted that the various embodiments are merely provided to illustrate the present invention and are not intended to limit the scope of the present invention.

Plugins are common in computer software and are supported by many types of software. For example text editor software Ultra Edit and software development tool Visual Studio both support plugins. There are also plugins for browsers which comes in different forms such as browser helper object BHO ActiveX Url SearchHook and ToolBar.

BHO Browser Helper Objects BHOs are applets that automatically run whenever an Internet browser such as IE starts. Usually a BHO file is installed into the user terminal systems by some other software. For example some Adware with downloading capability may install a BHO file to track the various advertisements while the user terminal surfs the web. BHO usually makes it easier for user terminals to browse the Internet or use various accessory functions but some BHOs are Adware or Spyware as which monitor the online behavior of user terminals and transmit recorded data to the creator of the BHO. BHO may also create conflicts with other programs that are running and causes various display and running time errors that may prevents the normal browsing.

ActiveX ActiveX plugins also known as OLE controls or OCX controls are software components or objects that can be inserted into a webpage or other applications. Typical software needs to be separately downloaded by a user terminal before being installed while ActiveX plugins will be automatically downloaded by the browser when the user navigates to a particular webpage and the user will be prompted to install them. ActiveX plug ins must be downloaded first authenticated and eventually confirmed by the user terminal before they can be installed. A webpage embedded with ActiveX scripts may become very slow or may even freeze the browser.

Url SearchHook when a user terminal enters a non standard Web address in the address bar such as English characters or Chinese characters that cannot be successfully interpreted by the address bar the browser will automatically open a page containing the search result where the string entered by the user is used as the search term which may help the user to find the needed contents. Url SearchHook object is the plugin that completes such search usually developed by a third party company or individual and installed on the browser as a plugin to help the user to better use the Internet. For example if the user terminal enters mobile phone in the address bar the search results for mobile phone will directly appear. Some companies or individuals may modify a browser s Url SearchHook without the knowledge of the user terminal in order to direct traffic to a particular website or for other commercial purposes.

Toolbar usually refers to accessory tools loaded in a browser located below the standard browser toolbar. In Internet Explorer one can right click the blank space in the toolbar to check the installed toolbars and to display or hide the installed toolbars by making the corresponding selections.

The plugins in accordance with embodiments of the present invention are programs written accordance to certain standard application programming interfaces. For example after being installed browser plugins can be called directly by the browser. The plugin can also be a component for certain software features which can facilitate or impede the user s use of the software. Performance refers to the specification parameters of a computer such as speed which is an important indicator of computer performance. The performance of a computer can typically be evaluated by the CPU usage and the time it takes to complete a task. Inception refers to stopping the installation or loading of a plugin. Clean up refers to the removal of the plugin from the computer.

Windows NT family Host Intrusion Prevention System WinHIPS is a kernel driver which uses techniques such as filtering and system call hooking to implement intelligence interception and safeguard computer systems.

As shown in in accordance with an embodiment of the present invention a method for intercepting or cleaning up a plugin is provided the method comprising 

Step determining whether the plugin meets a performance criterion based on the performance attributes and empirical data. If the plugin does not meet the performance criterion proceed to Step if the plugin meets the performance criterion proceed to Step .

In accordance with the method for intercepting or cleaning up a plugin the performance attributes of a plugin can be evaluated to determine whether the plugin meets a preset performance criterion and the plugin can then be processed according to the result of the determination. This embodiment of the present invention is primarily directed to evaluating and processing plugins that are being installed loaded or running if the plugin does meet the performance criterion it will be intercepted if being installed and cleaned up if being loaded or running if the plugin meets the performance criterion no action is taken.

As shown in in accordance with another embodiment of the present invention the method further comprises prior to the above method 

Step monitoring activity of the plugin in a user terminal wherein the activity is selected from a group comprising installing loading and running of the plugin identifying the plugin based on the monitored activity if the plugin is identified proceeds to step if the plug is not identified proceeds to step .

Step determining whether the plugin meets a performance criterion based on the performance attributes and empirical data. If the plugin does not meet the performance criterion proceed to Step if the plugin meets the performance criterion proceed to Step .

As shown in in accordance with another embodiment of the present invention the method further comprises prior to Step 

Step obtaining empirical data of the plugin wherein the empirical data comprises plugin importance data plugin performance data and or end user review data and

As shown in the empirical data can be obtained through plugin testing backend collection and or web crawling backend collection comprises frontend collection and end user review frontend collection comprises hook mode and notification mode the empirical data is stored in a remote cloud database or a local database. The cloud database is located at the server and can be used to store empirical data and can communicate with the client over the network. The local database is located locally at the client and can be used to store empirical data.

Further plug testing comprises testing the plugin in an automatic module to obtain information on the plugin s CPU usage load time and or memory usage.

Frontend collection can be implemented through a client and includes hook mode and notification mode.

1. Hook mode using a hook to obtain a start time and an end time for loading the plugin a start time and an end time for running the plugin and information on the plug s CPU usage and or memory usage while the plugin is loading and running 

2. Reception mode a client directly notifying starting and ending of loading and running of the plugin.

Frontend collection includes collection hardware and software environment to further evaluate performance data.

End user review includes collecting reviews of end users on the performance of the plugin which can be placed in the plugin cleanup module of security software or plugin monitoring modules or any other places.

Web crawling includes crawling search engine data and or website review data to evaluate the performance of the plugin.

In constructing the cloud database for empirical data one factor that should be considered is the necessity of the plugin. For example plugins like the Flash are highly necessary and should be loaded even if its performance is poorer than other plugins and the performance attributes of such plugins should be directly set as meeting the criterion. The factors to be considered regarding whether or not a plugin meets the performance criterion include but are not limited to plugins necessity or importance data end user plugin performance review data plugin performance testing data frontend collected performance data and relevant performance data on the Internet. For example a plugin with long loading time poor end user review and not particularly important can be set as not meeting the performance criterion.

The method for intercepting or cleaning up a plugin can be implemented in a client and a server and the client can include a performance acquisition module an evalution determination module and a plugin processing module . The method can also be implemented in a plugin signature database and a local empirical database . The server can include backend module . The method can also be implemented in cloud empirical data database as shown in . The performance acquisition module evaluation determination module and plugin processing module generally can be one or several independent installation files based on the needs and whose functionalities can be implemented as either Dynamic Link Library DLL or Label Information Base LIB .

The evaluating and processing of a plugin being installed at the user terminal will be described in reference to . The process includes 

Step matching the performance attributes with empirical data stored on a cloud database obtaining a preset determination result after a successful match and determining whether the plugin meets the performance criterion based on the preset determination result. If the plugin does not meet the performance criterion proceed to Step if the plugin meets the performance criterion proceed to Step .

The plugin monitoring module monitors various activities at the user terminal such as addition deletion or modification of entries in the registry files and services. The plugin monitoring module generally runs in the driver layer. The plugin signature database can record identifying characteristics of plugins such as those written to specific locations of the registry which can be used to identify the plugin. When the plugin is being installed at the user terminal the plugin monitoring module can catch such activity and compares such activity with plugin signature database to identify the plugin and obtain other information on the plugin. As a result it can be confirmed that the monitored activity is the installation of the specific plugin.

The plugin monitoring module then sends information regarding the plugin such as the identification ID of the plugin to the evaluation determination module . The evaluation determination module is mainly used to obtain performance attributes of the plugin. The evaluation determination module can visit cloud empirical database or local empirical database to obtain performance attributes of the plugin. The evaluation determination module visits cloud empirical database first to obtain performance attributes of the plugin from the server then determines whether the plugin meets the performance criterion or directly obtains a preset result on whether the plugin meets the performance criterion. The result can be pre obtained by backend module . The local empirical database is a backup when there is no network connection or when the network connection is poor and the cloud empirical database cannot be connected. In accordance with this embodiment the present result on whether the plugin meets the performance criterion can be located on the server and be updated when data on the server data is being updated. The present result can also be located at the client and be updated through replacement of the relevant files.

Whether the plugin meets the performance criterion is determined not only based on the loading time of the plugin or any other individual data but can also be based on a variety of factors such as combining the loading time with end user review.

Plugin can be installed as regular software such as through a plugin installation package or can be installed while other software is being installed. When a plugin is being installed if it is determined that the plugin does not meet the performance criterion the plugin can be intercepted by the plugin processing module as shown in . The interception user interface can be a popup window shown in . If the plugin meets the performance criterion no action will be taken.

The evaluation and processing of plugin being loaded at the user terminal will be described in reference to . The process includes 

Step matching the performance attributes with empirical data stored on a cloud database obtaining a preset determination result after a successful match and determining whether the plugin meets the performance criterion based on the preset determination result. If the plugin does not meet the performance criterion proceed to Step if the plugin meets the performance criterion proceed to Step .

For plugin that has already been installed the plugin monitoring module can catch the plugin when it is being loaded at the user terminal and sends to evaluation determination module . The evaluation determination module can visit cloud empirical database or local empirical database to obtain performance attributes of the plugin. The data in the cloud empirical database is acquired through the backend module . The performance attributes will be matched with empirical data. If a match is successfully found a preset determination result is obtained and whether the plugin meets the performance criterion is determined based on the preset determination result. If the plugin does not meet the performance criterion prohibit the loading of the plugin if permitted by the user terminal and process the plugin using plugin processing module if permitted by the user terminal. If the plugin meets the performance criterion no action will be taken. During the removal of the plugin identifying characteristics of the plugin should be obtained from the plugin signature database .

The evaluation and processing of plugin running at the user terminal will be described in reference to . The process includes 

Step monitoring the running of a plugin at a user terminal obtaining performance attributes of the plugin 

Step determining whether the plugin meets the performance criterion based on the performance attributes. If the plugin does not meet the performance criterion proceed to Step if the plugin meets the performance criterion proceed to Step .

A running plugin may have passed the testing during its loading or its performance attributes might not been collected by the cloud empirical database to local empirical database through the backend module . Thus the plugin monitor module can be used to catch the plugin and send it to the evaluation determination module to obtain the performance attribute of the plugin. It can also test the performance of the plugin in real time if needed and derive a determination result. If the plugin does not meet the performance criterion clean up the plugin using plugin processing module if permitted by the user terminal. If the plugin meets the performance criterion no action will be taken. During the cleanup of the plugin identifying characteristics of the plugin should be obtained from the plugin signature database . If the performance attributes of the plugin has already be collected the plugin can be processed in similar fashion discussed above when it is being installed or loaded.

In accordance with the apparatus for intercepting or cleaning up a plugin the performance attributes of a plugin can be evaluated to determine whether the plugin meets a preset performance criterion and the plugin can then be processed according to the result of the determination. This embodiment of the present invention is primarily directed to evaluating and processing plugins that are being installed loaded or running if the plugin does meet the performance criterion it will be intercepted if being installed and cleaned up if being loaded or running if the plugin meets the performance criterion no action is taken.

As shown in the empirical data can be obtained through plugin testing backend collection and or web crawling backend collection comprises frontend collection and end user review frontend collection comprises hook mode and notification mode the empirical data is stored in a remote cloud database or a local database.

As shown in the apparatus for intercepting or cleaning up a plugin can be implemented in a client and a server and the client can include a performance acquisition module a evaluation determination module and a plugin processing module . The apparatus can also be implemented in a plugin signature database and a local empirical database . The server can include backend module . The method can also be implemented in cloud empirical data database . The performance acquisition module evaluation determination module and plugin processing module generally can be one or several independent installation files based on the needs and whose functionalities can be implemented as either Dynamic Link Library DLL or Label Information Base LIB .

In this embodiment the performance acquisition module is equivalent to the performance acquisition module in the performance acquisition module the first performance determination module and performance evaluation module are equivalent to evaluation determination module in the plugin processing module is equivalent to plugin processing module the empirical data acquisition module and the second performance determination module are equivalent to backend module in .

The various embodiments of the present invention are merely preferred embodiments and are not intended to limit the scope of the present invention which includes any modification equivalent or improvement that does not depart from the spirit and principles of the present invention.


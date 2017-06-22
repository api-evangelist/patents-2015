---

title: Information processing apparatus capable of controlling installation of application, method of controlling the same, and storage medium
abstract: An information processing apparatus capable of performing application installation control while taking into account amounts of resources to be changed by installation of an extension application to be attached to an associated application. When a fragment bundle is installed, total values of amounts of the resources used by installed applications including a host bundle assumed to have been extended in function by the fragment bundle are calculated. It is determined whether the total values are within allowable upper limit values allowed by the apparatus. If it is determined that the total values are within their allowable upper limit values, the fragment bundle is installed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09588755&OS=09588755&RS=09588755
owner: CANON KABUSHIKI KAISHA
number: 09588755
owner_city: Tokyo
owner_country: JP
publication_date: 20150401
---
The present invention relates to an information processing apparatus capable of controlling installation of an application a method of controlling the same and a storage medium.

In recent years in an information processing apparatus such as an image forming apparatus an application operating environment notably a Java environment has come to be provided. Further a technique is proposed which provides an extensible application by making use of the portability of a program provided in an application operating environment such as Java . Java is a registered trademark of Oracle and or its affiliates.

To improve the functions and usability of the image forming apparatus an application that operates under an application operating environment such as the Java environment is created and installed in the image forming apparatus whereby it is possible to realize desired functions in the image forming apparatus.

As an application platform there has been proposed an OSGi Open Services Gateway initiative Service Platform hereinafter simply referred to as the OSGi which is an application platform for built in devices operating under an application operating environment such as Java .

The OSGi defines a bundle as a management unit of a software module and defines specifications for managing a life cycle of install start stop update and uninstall.

The bundle refers to a module operating in an application operating environment such as Java . Further the OSGi can provide the application with built in functions such as a copy function a scan function and a print function.

Further the specifications of the OSGi include a host bundle and a fragment bundle. The fragment bundle is a bundle in a form which does not operate singly but attaches the bundle itself to a class loader space of the host bundle.

To correct or extend the application the function of the host bundle is corrected or extended using the fragment bundle whereby it is possible to reduce the size of a file to be installed which contributes to efficient module distribution.

Under the above described technical background many of image forming apparatuses are not provided with a wealth of system resources in view of cost reduction. For this reason to install or start an application there has been proposed a technique that checks whether or not system resources required for proper operation of the application can be secured to thereby prevent occurrence of a failure or an erroneous operation of the apparatus see e.g. Japanese Patent Laid Open Publication No. 2011 243232 .

However in a case where a fragment bundle is installed for example amounts of resources required by an installed host bundle are sometimes increased. In this case it is impossible for the amounts of the resources checked during installation or execution of the host bundle to guarantee the securing of the system resources required for proper operation of the application.

Further some host bundles provided on the precondition of using a fragment bundle perform a function equipped in the fragment bundle instead of using a corresponding standard function of the host bundle.

In such a case the required amounts of resources are sometimes reduced by the use of the fragment bundle. Therefore uninstallation of the fragment bundle increases the amounts of resources required by the application and hence depending on the amounts of the resources it is impossible to uninstall the fragment bundle alone.

As described above in the conventional technique when installing or uninstalling an application for extension amounts of resources changed by installation or uninstallation of the application for extension are not taken into account.

The present invention provides an information processing apparatus that is capable of performing application installation control while taking into account amounts of resources to be changed by installation of an extension application for extending a function of an application associated therewith a method of controlling the information processing apparatus and a storage medium.

In a first aspect of the present invention there is provided an information processing apparatus that is capable of installing an extension application which operates using resources of the information processing apparatus and extends a function of an application installed in the information processing apparatus comprising a calculation unit configured to calculate in a case where the extension application is to be installed respective total values of amounts of resources that are used by installed applications including an extension target application which is assumed to have been extended in function by the extension application a determination unit configured to determine whether or not the total values calculated by the calculation unit are within allowable upper limit values allowed by the information processing apparatus and an installation unit configured to install the extension application in a case where it is determined by the determination unit that the total values are within the allowable upper limit values.

In a second aspect of the present invention there is provided a method of controlling an information processing apparatus that is capable of installing an extension application which operates using resources of the information processing apparatus and extends a function of an application installed in the information processing apparatus comprising calculating in a case where the extension application is to be installed respective total values of amounts of resources that are used by installed applications including an extension target application which is assumed to have been extended in function by the extension application determining whether or not the total values calculated by said calculating are within allowable upper limit values allowed by the information processing apparatus and installing the extension application in a case where it is determined by said determining that the total values are within the allowable upper limit values.

In a third aspect of the present invention there is provided a non transitory computer readable storage medium storing a computer executable program for executing a method of controlling an information processing apparatus that is capable of installing an extension application which operates using resources of the information processing apparatus and extends a function of an application installed in the information processing apparatus wherein the method comprises calculating in a case where the extension application is to be installed respective total values of amounts of resources that are used by installed applications including an extension target application which is assumed to have been extended in function by the extension application determining whether or not the total values calculated by said calculating are within allowable upper limit values allowed by the information processing apparatus and installing the extension application in a case where it is determined by said determining that the total values are within the allowable upper limit values.

According to the present invention there are calculated respective total values of amounts of resources used by installed applications including the extension target application which is assumed to have been extended in function by the extension application and in a case where the calculated total values are within the allowable upper limit values allowed by the information processing apparatus the extension application is installed. Therefore it is possible to perform application installation control while taking into account amounts of resources to be changed by installation of an extension application for extending a function of an application associated therewith.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings .

The present invention will now be described in detail below with reference to the accompanying drawings showing embodiments thereof.

Referring to the image forming apparatus includes a controller . The controller is comprised of a CPU a ROM a RAM an HDD Hard Disk Drive a console section interface a network interface a scanner interface an image processor a printer interface a scanner section a printer section and a console section which are connected to each other by a system bus .

The CPU performs centralized control of access to various types of hardware connected to the system bus based on a control program and the like stored in the ROM . Further the CPU also performs centralized control of various processes performed by the controller .

The ROM is a read only nonvolatile storage device and stores a boot program and the like for the image forming apparatus .

The RAM serves as a system work memory for the operation of the CPU and also serves as a memory for temporarily storing various programs and data. The RAM is implemented by either of an FRAM Ferroelectric Random Access Memory registered trademark and an SRAM Static RAM which are capable of storing data even after the image forming apparatus is powered off or a DRAM Dynamic RAM from which data is deleted when the image forming apparatus is powered off.

The HDD is a nonvolatile storage device and stores various programs such as a system application and various types of data. Applications installed in the present embodiment are stored in the HDD .

More specifically the console section interface receives data from the system bus and displays the data on the console section . Further the console section interface outputs information input from the console section to the system bus . The user provides instructions and information to the image forming apparatus via the console section .

The network interface is connected to a LAN Local Area Network and a WAN Wide Area Network and transmits and receives information to and from external apparatuses. The scanner interface outputs image data received from the scanner section to the system bus .

The image processor performs turning compression expansion and so forth on image data. The printer interface receives image data sent from the image processor and output the image data to the printer section . The printer section prints image data output from the printer interface on a recording medium such as a sheet.

As described above similar to a general information processing apparatus the image forming apparatus is comprised of a computing device volatile storage devices nonvolatile storage devices and so forth.

Although a PC for communicating with the image forming apparatus configured as above is a general personal computer capable of executing a web browser the PC may be replaced by a smart phone or a tablet terminal which is capable of executing a web browser.

Software shown in is stored in the ROM or the HDD and is executed by the CPU . Further various information used during execution of the software is stored in the RAM or the HDD and is exchanged between the functions of the software.

The software includes an OS Operating System platform . A software platform is built on the OS platform .

The software platform is formed as a run time environment of a JVM Java Virtual Machine which operates under JAVA application operating environment and includes the JVM as an interpreter a library and a frame work group .

The library includes a standard API Application Programming Interface library. Further the frame work group includes an OSGi Open Services Gateway initiative and an OSGi extension section .

The OSGi causes a plurality of applications to operate on the JVM which is single. Further the OSGi provides functions for life cycle management of applications and communication between the applications. Furthermore a plurality of system services are preinstalled on the OSGi . The OSGi extension section is capable of extending the functions of the OSGi on an as needed basis.

Further when the image forming apparatus is started up the OSGi starts the services of an installation controller an application management section a host bundle and a fragment bundle attached to the host bundle according to a service start order list stored in the HDD .

Out of the above components the host bundle is an application body and is a bundle to which the fragment bundle is attached. Further the fragment bundle is an extension application and is a bundle which does not operate singly but attaches itself to the class loader space of the host bundle .

Here the term class loader refers to an object which is in charge of loading classes and searching resources. All the classes are loaded into the JVM by the class loader and become usable from the application. That is after installation of the fragment bundle all the classes become usable as part of the host bundle . Therefore when the fragment bundle is installed to attach itself to the host bundle or uninstalled in general the amounts of resources used by the host bundle are changed.

The extension application includes e.g. a class of Java which is an application operating environment which provides an extension for resource data such as image data and language data.

Further the host bundle provides to the user various processes performed by the image forming apparatus singly or together with the fragment bundle under the control of the application management section . Examples of the various processes include processes by applications for manipulating and compressing images and processes by an application for performing department management such as restrictions on printing and like other applications. The above described host bundle corresponds to an extension target application and the fragment bundle corresponds to an extension application for extending the function of the application to be extended. Further the host bundle and the fragment bundle operate using resources of the image forming apparatus . Further as described above the image forming apparatus is configured to be capable of installing a fragment bundle for extending the function of a host bundle installed on the image forming apparatus .

The application management section manages a plurality of application groups and performs installation and uninstallation of applications and so forth using the installation controller .

Further the application management section stores application information and license information including versions of the host bundle and the fragment bundle which are installed under the control thereof.

Furthermore in response to an uninstallation instruction to an application in the image forming apparatus the application management section removes the host bundle or the fragment bundle from objects to be managed via the installation controller .

Note that in the example of the present embodiment the application mentioned in is intended to mean the host bundle or the fragment bundle .

Referring to the PC displays an application installation UI user interface formed by a web page displayed on an installation screen described hereinafter on a web browser not shown . When the user designates an application that the user desires to install from the install UI the PC installs the application.

Upon receipt of an application file designated from the install UI the application management section passes the application file to the installation controller . Upon receipt of the application file the installation controller requests the OSGi to install the application file and the OSGi installs the application file. The installed application is managed by the application management section .

Note that attaching of the fragment bundle to the host bundle is sometimes referred to as installation.

As shown in Bundle ManifestVersion of a manifest of the host bundle is specified as 2. Bundle SymbolicName in the manifest is given a unique name within a frame work.

Fragment Host in the manifest is specified by which refers to a bundle symbolic name described in the manifest of the host bundle. When the respective values of Bundle SymbolicName in the manifest and Fragment Host in the manifest are equal to each other it indicates that the host bundle and the fragment bundle are component parts of the same application.

When installing the fragment bundle with the information described in the above described manifests the OSGi identifies the host bundle based on the manifest information of the fragment bundle and adds a class path of the fragment bundle itself to a class path of the host bundle.

Here the term class path specifies a location from where the JVM is required to read a class file when performing a Java which is an application operating environment application.

Further classes and resources within the fragment bundle are all loaded by the class loader of the host bundle.

In the fragment bundle it is possible to extend resources including resources for country specific languages so as to enable switching between display languages of the host bundle and extend standard functions of the application.

Further to uninstall a fragment bundle attached to the host bundle it is required to delete a class path of the fragment bundle itself from class paths of the host bundle and further load a class necessary for the host bundle again using the class loader of the host bundle.

In the manifests appearing in MaximumMemoryUsage indicates the maximum amount of memory to be used MaximumThreadUsage indicates the maximum number of threads to be used MaximumSocketUsage indicates the maximum number of sockets to be used MaximumFiledescriptorUsage indicates the maximum number of file descriptors to be used and MaximumFilespaceUsage indicates the maximum amount of disk space to be used. On the other hands in association with these items there are separately defined beforehand respective allowable upper limit values of the amount of memory the number of threads the number of sockets the number of file descriptors and the amount of disk space that are usable in the image forming apparatus .

Further shows a manifest of the fragment bundle in a case where some of the resource consumptions are increased by the installation of the fragment bundle .

Descriptions in the manifest indicate the amounts of respective resources increased or reduced by the fragment bundle when the fragment bundle is installed to attach itself to the host bundle and is operated in a case where attention is paid to the totals of resource consumptions by the host bundle and the fragment bundle i.e. the whole application. In the case of there are entries of positive values but there are no entries of negative values which means that the amounts of resources to be used are increased. For example the maximum thread usage MaximumThreadUsage of the fragment bundle appearing in is 2 and hence the associated resource consumption by the application is increased by 2 by the installation of the fragment bundle .

Note that when the maximum consumption of a resource by the application is not changed in spite of the installation of the fragment bundle is entered as a value of the maximum resource consumption associated with the resource.

Descriptions in the manifest indicate similarly to those in the manifest the amounts of respective resources increased or reduced by the fragment bundle when the fragment bundle is installed to attach itself to the host bundle and is operated in a case where attention is paid to the totals of resource consumptions by the host bundle and the fragment bundle i.e. the whole application. However in this case there are entries of negative values which means that the amounts of resources are reduced. For example MaximumThreadUsage of the fragment bundle appearing in is 1 and hence the associated resource consumption by the application is reduced by 1 by the installation of the fragment bundle .

Thus in the case of when the fragment bundle of the manifest is installed the maximum number of used threads and the maximum amount of used disk space are reduced compared with when the host bundle is operated singly.

Note that it is also possible to employ a method in which total resource consumptions obtained by combining the amounts of resources to be used by the host bundle and the fragment bundle are entered e.g. in the manifest of the fragment bundle .

In this method however when any of the maximum resource consumptions in the host bundle itself are changed by addition of a function to the host bundle it is required to also change the values of resource consumptions entered in the manifest of the fragment bundle .

Therefore to reduce influence of a change in resource consumptions in a specific host bundle it is desirable to enter only differences in resource consumption from the host bundle in the manifests and of the fragment bundle .

Referring to a field of Application A displays the resource consumptions by the application when the host bundle having the manifest operates singly. Values appearing in the manifest are directly entered as total resource consumptions in the application A.

A field of Application A and Fragment A displays the total resource consumptions by the application when the fragment bundle having the manifest is attached to the host bundle having the manifest and is operated. Values obtained by adding values of the resource consumptions in the manifest and values of the resource consumptions in the manifest to each other are entered as the total resource consumptions by the application.

Further a field of Application A and Fragment B displays the total resource consumptions by the application when the fragment bundle having the manifest is attached to the host bundle having the manifest and is operated. Values obtained by adding values of the resource consumptions in the manifests and values of the resource consumptions in the manifest to each other are entered as the total resource consumptions by the application.

Although this field of Application A and Fragment B is the same as the field of Application A and Fragment A in that values obtained by adding values of the resource consumptions in both the manifests are entered as the total resource consumptions by the application the field shows that the total resource consumptions shown in MaximumThreadUsage and MaximumFilespaceUsage become smaller than when the host bundle is operated singly.

In the present embodiment the installation and uninstallation of the fragment bundle are achieved by also taking into account cases where any of the total resource consumptions become smaller.

Note that resource consumptions declared by an application are amounts of resources mainly consumed during execution of the application and hence it is not necessarily required to check all the resource consumptions during the installation of a fragment bundle. A resource consumption to be checked during the installation is an amount of disk space to be used including an amount of disk space to be occupied by a file itself of the application and in general the remaining resource consumptions are checked during operation of the application.

As described above in the present embodiment there are used amounts of resources used by the host bundle without a fragment bundle installed therein and respective differences amounts of decrease or increase between the mentioned amounts of resources used by the host bundle and amounts of resources used by the host bundle with the fragment bundle installed therein whereby the total resource consumptions are indicated by respective total values of the amounts of resources and the differences amounts of decrease or increase .

The name of an application under management is displayed at an application name . In the illustrated example two applications i.e. an application A and an application B are under management.

Further a fragment bundle A and a fragment bundle B are managed by setting the application A as a host bundle. The fragment bundles A and B are displayed on the application management screen in association with the application A .

An installation date is a date on which an associated application was installed. An installation ID indicates an ID identifier uniquely assigned to an associated application.

A status indicates a status of an associated application. When an application has been started the status thereof is displayed as started whereas when the application has been stopped the status thereof is displayed as stopped .

A switch button switches between the start and stop of an associated application. In a case where an application is in a started state the switch button functions as a stop button whereas in a case where the application is in a stopped state the switch button functions as a start button.

For example when the switch button associated with the application A which is in the started state is depressed the status of the application A is changed to stopped .

On the other hand when the switch button associated with the application B which is in the stopped state is depressed the status of the application B is changed to started .

An uninstall button is used for uninstalling each application. In the uninstallation of a fragment bundle only the fragment bundle is uninstalled.

For example when an uninstall button associated with the fragment bundle A is depressed only the fragment bundle A is uninstalled.

Referring to a reference button is used for displaying a screen for use in selecting a file path. When an application file is designated on the screen a path to the application file is input to an application file path .

Some applications each sometimes require a license file for decoding a file of an application during an installation process from the viewpoint of security and business.

In such a case when the user depresses a reference button a screen for selecting a file path is displayed. When a license file is designated on the screen a path to the license file is input to a license file path .

When an install button is depressed installation of an application designated by the application file path is started.

Next a description will be given of a general process performed during the installation of the application. As mentioned hereinabove in general the resource consumption to be checked during the installation is an amount of disk space to be used and the remaining resource consumptions are checked during operation of the application.

Referring to when the installation controller starts installation of an application the installation controller calculates a total value of respective MaximumFilespaceUsage values of installed applications and a MaximumFilespaceUsage value of the application to be installed step S .

Then the installation controller determines whether or not the total value calculated in the step S is within the allowable upper limit value step S . Here it is determined whether or not the calculated amount of disk space to be used is within the allowable upper limit value allowed by the image forming apparatus .

If it is determined in the step S that the total value is within the allowable upper limit value YES to the step S the installation controller requests the OSGi to install the application step S followed by terminating the present process.

On the other hand if the total value is not within the allowable upper limit value NO to the step S the installation controller terminates the present process without installing the application.

Referring to the installation controller calculates respective total values of MaximumMemoryUsage values MaximumThreadUsage values MaximumSocketUsage values and MaximumFiledescriptorUsage values of applications in operation and an application to be started step S .

Next the installation controller determines whether or not respective total values of resource amounts calculated in the step S are within their allowable upper limit values step S .

If it is determined in the step S that the total values are within the respective allowable upper limit values YES to the step S the installation controller requests the OSGi to start the application step S followed by terminating the present process.

On the other hand if it is determined in the step S that any of the total values are not within the respective allowable upper limit values NO to the step S the installation controller terminates the present process without starting the application.

As described above in general when an application is installed a checking process concerning the resource consumptions is performed and when the application is operated another checking process concerning the resource consumptions is performed. A host bundle is installed through the processes described with reference to .

Next a description will be given of a fragment bundle installation process and a fragment bundle uninstallation process.

Referring to upon depression of the install button appearing in by the user it is determined whether or not a host bundle associated with the fragment bundle to be installed has been installed step S .

If it is determined in the step S that the host bundle has not been installed NO to the step S the present process is terminated without installing the fragment bundle.

On the other hand if it is determined in the step S that the host bundle has been installed YES to the step S a total value of MaximumFilespaceUsage values of the installed applications and the fragment bundle to be installed is calculated step S .

Then it is determined whether or not the total value calculated in the step S is within the allowable upper limit value of the amount of disk space to be used step S .

If it is determined in the step S that the total value is not within the allowable upper limit value NO to the step S the present process is terminated without installing the fragment bundle.

On the other hand if it is determined in the step S that the total value is within the allowable upper limit value YES to the step S it is determined whether or not the host bundle is in operation step S .

If it is determined in the step S that the host bundle is not in operation NO to the step S the OSGi is requested to install the application step S followed by terminating the present process.

When the host bundle is not in operation if only a resource consumption of disk space is checked it is possible to allow installation of the application and checking of the remaining resource consumptions is newly performed in the operation time checking process described with reference to .

On the other hand if it is determined in the step S that the host bundle is in operation YES to the step S the respective total values of the values of the resource consumptions MaximumMemoryUsage MaximumThreadUsage MaximumSocketUsage and MaximumFiledescriptorUsage of the applications in operation and the fragment bundle to be installed are calculated step S . This step S and the above described step S correspond to an operation of a calculation unit configured to calculate in a case where the extension application is to be installed respective total values of amounts of resources that are used by installed applications including the extension target application which is assumed to have been extended in function by the extension application.

Then it is determined whether or not all the total values of the respective resource amounts calculated in the step S are within their allowable upper limit values step S . This step S and the above described step S correspond to an operation of a determination unit configured to determine whether or not the calculated total values are within allowable upper limit values allowed by the information processing apparatus.

If it is determined in the step S that not all the total values are within their allowable upper limit values NO to the step S the present process is terminated without installing the fragment bundle.

On the other hand if it is determined in the step S that all the total values are within their allowable upper limit values YES to the step S the host bundle is stopped step S .

Then the OSGi is requested to install the application to be installed step S . Subsequently the host bundle having the fragment bundle installed therein is started step S followed by terminating the present process. This step S and the above described step S correspond to an operation of an installation unit configured to install the extension application in a case where it is determined that all the total values are within their allowable upper limit values.

Referring to upon depression of the uninstall button appearing in by the user it is determined whether or not the host bundle is in operation step S .

If it is determined in the step S that the host bundle is not in operation NO to the step S a total value of MaximumFilespaceUsage values of the installed applications from which a MaximumFilespaceUsage value of the fragment bundle to be uninstalled is subtracted is calculated step S .

Then it is determined whether or not the total value calculated in the step S is within the allowable upper limit value of the amount of disk space to be used step S . If it is determined in the step S that the total value is not within the allowable upper limit value NO to the step S the present process is terminated without uninstalling the fragment bundle.

On the other hand if it is determined in the step S that the total value is within the allowable upper limit value YES to the step S the fragment bundle is uninstalled step S followed by terminating the present process.

Referring again to the step S if it is determined in the step S that the host bundle is in operation YES to the step S total values of the values of the resource consumptions MaximumMemoryUsage MaximumThreadUsage MaximumSocketUsage and MaximumFiledescriptorUsage of the applications in operation from which values of the resource consumptions of the fragment bundle to be uninstalled are subtracted are calculated step S .

This step S and the above described step S correspond to an operation of another calculation unit configured to calculate in a case where the extension application attached to the extension target application is to be uninstalled respective total values of amounts of resources that are used by the installed applications including the extension target application to which the extension application is not attached.

Further as shown in the step S and the above described step S the total values of the respective resource consumptions are calculated by subtracting the amounts of the resources used by the fragment bundle from the resources used by the installed applications including the host bundle having the fragment bundle installed therein.

Next it is determined whether or not the total values of the respective resource consumptions calculated in the step S are within their allowable upper limit values step S . This step S and the above described step S correspond to an operation of another determination unit configured to determine whether or not the calculated total values are within the allowable upper limit values allowed by the information processing apparatus.

If it is determined in the step S that any of the total values are not within their allowable upper limit values NO to the step S the present process is terminated without uninstalling the fragment bundle.

On the other hand if it is determined in the step S that the total values are within their allowable upper limit values YES to the step S the total value of MaximumFilespaceUsage values of the installed applications from which the MaximumFilespaceUsage value of the fragment bundle to be uninstalled is subtracted is calculated step S .

Then it is determined whether or not the total value calculated in the step S is within its allowable upper limit value step S . If it is determined in the step that the total value is not within its allowable upper limit value NO to the step S the present process is terminated without uninstalling the fragment bundle.

On the other hand if it is determined in the step S that the total value is within its allowable upper limit value YES to the step S the host bundle is stopped step S .

Then the fragment bundle is uninstalled step S and the host bundle is started step S followed by terminating the present process. The step S and the above described step S correspond to an operation of an uninstallation unit configured to uninstall the extension application when it is determined that the total values are within the allowable upper limit values.

The deletion candidate screen presents to the user a fragment bundle which consumes large amounts of resources as an uninstallation candidate when it is impossible to install a fragment bundle because any of the resource consumptions of the fragment bundle exceeds their allowable upper limit values.

When the user is thus prompted to uninstall a fragment bundle consuming large amounts of resources and the fragment bundle is uninstalled a possibility increases that the amounts of resources consumed by the fragment bundle to be installed can be secured.

Referring to an application name is a field for displaying installed host bundles. Note that an application having no fragment bundle installed therein is not displayed on the deletion candidate screen .

In the case of it is shown that an application A and an application B have been installed. Further it is also shown that a fragment bundle A has been attached to the application A which is a host bundle.

Further it is also shown that a fragment bundle B and a fragment bundle C have been attached to the application B which is a host bundle.

Note that the fragment bundles are displayed in a decreasing order of the memory usage on the deletion candidate screen .

An installation date indicates a date on which each fragment bundle was installed. An application ID indicates an ID identifier uniquely assigned to each fragment bundle.

A status indicates a status of a host bundle of each application. When the host bundle has been started the status is displayed as started and when the host bundle has been stopped the status is displayed as stopped .

Resource consumption indicates amounts of resource consumptions by which the maximum resource consumptions are increased or reduced by uninstallation of a fragment bundle.

In the field of the resource consumption MEM indicates the amount of memory to be used TH indicates the number of threads to be used SOC indicates the number of sockets to be used FD indicates the number of file descriptors to be used and HDD indicates the amount of disk space to be used.

When the user checks a check box associated with a fragment bundle to be uninstalled the fragment bundle becomes an object to be uninstalled.

Further when the user depresses an uninstall button a fragment bundle associated with the checked check box is uninstalled. On the other hand when the user depresses a cancel button display of the deletion candidate screen is terminated.

Referring to when it is determined in the step S or S in the installation process in that the total value s is are not within the allowable upper limit value s No to the step S or S the deletion candidate screen is displayed S .

Next on the deletion candidate screen it is determined whether or not the check box is checked and the uninstall button is depressed by the user S .

If it is determined in the step S that the cancel button is depressed by the user NO to the S the present process is terminated.

On the other hand if it is determined in the step S that the check box is checked and the uninstall button is depressed by the user YES to the S the uninstallation process in is performed step S and the process returns to the step S in the installation process in again.

According to the process shown in if it is impossible to install a fragment bundle because any of the resource consumptions of the fragment bundle exceed their allowable upper limit values installation of the fragment bundle can be performed by displaying the deletion candidate screen for uninstalling a fragment bundle that has already been installed.

As described hereinabove in the present embodiment if it is determined that total values of respective resource consumptions are not within their allowable upper limit values an installed fragment bundle is uninstalled which is checked and designated by the user on the deletion candidate screen displayed for uninstalling the installed fragment bundle.

Next a description will be given of an installation process for simultaneously installing a host bundle and a fragment bundle.

As described above the amounts of resources used when a fragment bundle is attached to a host bundle sometimes becomes smaller than when host bundle operates singly.

In this case even when the host bundle cannot be installed singly because the resource consumptions thereof exceed allowable upper limit values thereof it is possible to simultaneously install the host bundle and the fragment bundle.

Therefore in the present embodiment by enabling simultaneous installation of the host bundle and the fragment bundle it is made possible to check resource consumptions during installation of the host and fragment bundles using total values of consumptions of respective resources by the two bundles as application resource consumptions.

Referring to a reference button is a button for displaying a screen for selecting a file path of the host bundle. When a host bundle file is designated on the screen a path to the host bundle is input to a path of the host bundle.

A reference button is a button for displaying a screen for selecting a file path. When a host bundle license file is designated on the screen a path to the license file is input to a path of the license file of the host bundle.

A reference button is a button for displaying a screen for selecting a file path. When a fragment bundle file is designated on the screen a path to the fragment bundle file is input to a path of the fragment bundle.

A reference button is a button for displaying a screen for selecting a file path. When a fragment bundle license file is designated on the screen a path to the license file is input to a path of the fragment bundle license file.

An install button is a button for starting installation of an application designated by the path of an application file.

At this time resource consumptions by an application are represented by total values of resource consumptions declared in the manifest of the host bundle and resource consumptions declared in the manifest of the fragment bundle.

The host bundle and the fragment bundle are simultaneously installed by the installation time checking process in using the total values.

Note that although one fragment bundle is shown on the simultaneous installation screen in a plurality of fragment bundles may be installed at the same time using a user interface via which a plurality of fragment bundles can be designated.

As described above in the present embodiment when a host bundle and a fragment bundle which are not installed in the image forming apparatus are to be installed they are installed regarding the amounts of resources used by the host bundle and the fragment bundle as the amounts of resources used by the host bundle in a case where the fragment bundle is attached to the host bundle.

As described heretofore according to the present embodiment first respective total values of the amounts of resources which are used by installed applications including a host bundle assumed to have been extended in function by a fragment bundle are calculated steps S and .

Next when the calculated total values are within allowable upper limit values allowed by the image forming apparatus YES to the step S or S the fragment bundle extension application is installed steps S and S .

Through the above described process it is possible to perform installation control by taking into account resource consumptions changed by installation of an application for extending a function.

Further according to the above described embodiment first when a fragment bundle attached to a host bundle is to be uninstalled respective total values of the amounts of resources which are used by installed applications including the host bundle from which the fragment bundle is uninstalled are calculated.

Then when the calculated total values are within allowable upper limit values allowed by the image forming apparatus YES to the step S or YES to the step S the fragment bundle is uninstalled steps S and S .

Through the above described process it is possible to perform installation control by taking into account resource consumptions changed by uninstallation of an application for extending a function.

Embodiment s of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions e.g. one or more programs recorded on a storage medium which may also be referred to more fully as a non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s and or that includes one or more circuits e.g. application specific integrated circuit ASIC for performing the functions of one or more of the above described embodiment s and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s and or controlling the one or more circuits to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more processors e.g. central processing unit CPU micro processing unit MPU and may include a network of separate computers or separate processors to read out and execute the computer executable instructions. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2014 076176 filed Apr. 2 2014 which is hereby incorporated by reference herein in its entirety.


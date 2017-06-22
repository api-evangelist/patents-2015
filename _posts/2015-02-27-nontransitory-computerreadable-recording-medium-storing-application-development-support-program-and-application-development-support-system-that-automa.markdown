---

title: Non-transitory computer-readable recording medium storing application development support program and application development support system that automatically support platform version
abstract: In an application development support system, a file extractor searches platforms for target files supporting the version of an application developer's project, identifying any library not common to the platform but necessary to the project version. Based on manifest files, an interface reference unit queries open-source application programming interfaces for any libraries remaining as not having been extracted by the file extractor, such library files being version-dependent interface difference files for the project build. A manifest file creation unit generates manifest files for the difference files found by the interface reference unit, and merges the difference files with existing manifest files, replacing only the version-dependent portions required by the target platform.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09298451&OS=09298451&RS=09298451
owner: Kyocera Document Solutions Inc.
number: 09298451
owner_city: Osaka
owner_country: JP
publication_date: 20150227
---
This application is based upon and claims the benefit of priority from corresponding Japanese Patent Application No. 2014 036604 filed in the Japan Patent Office on Feb. 27 2014 the entire contents of which are incorporated herein by reference.

Unless otherwise indicated herein the description in this section is not prior art to the claims in this application and is not admitted to be prior art by inclusion in this section.

Application creation necessitates a development environment. Use of the development environment creates an application as a target. The application as the target is configured and managed in a unit referred to as a project.

The project is closely related to a version of the development environment. The version of the development environment is closely related to a version of a platform of an operating system OS where the application is operated.

Files or libraries required for the application are different depending on the platforms. When a developer attempts to develop the application for various versions of the platform each of the projects are often modified for each of the versions of the platforms.

Under this circumstance various kinds of techniques for supporting developers have been proposed. For example for a library management method in a development environment and an execution environment of software there is provided a technique of a library management method especially for adding changing and deleting rules regarding a library structure.

An application development support system according to an aspect of the disclosure is for creating an application by building build resources that contain libraries and manifest files. The application development support system includes a project version confirmation circuit an updating circuit and a manifest file creation circuit. The project version confirmation circuit searches all projects existing in a resources holding region to confirm the version in situations where a platform of an operation target for the application is in a plurality of versions. The updating circuit updates version dependent files by replacing files that differ by version stored in a development environment with files appropriate to the project version. The manifest file creation circuit creates manifest files for what is different from an open source interface and merging the files with existing manifest files.

These as well as other aspects advantages and alternatives will become apparent to those of ordinary skill in the art by reading the following detailed description with reference where appropriate to the accompanying drawings. Further it should be understood that the description provided in this summary section and elsewhere in this document is intended to illustrate the claimed subject matter by way of example and not by way of limitation.

Example apparatuses are described herein. Other example embodiments or features may further be utilized and other changes may be made without departing from the spirit or scope of the subject matter presented herein. In the following detailed description reference is made to the accompanying drawings which form a part thereof.

The example embodiments described herein are not meant to be limiting. It will be readily understood that the aspects of the present disclosure as generally described herein and illustrated in the drawings can be arranged substituted combined separated and designed in a wide variety of different configurations all of which are explicitly contemplated herein.

The application development support system includes a development tool unit a resources for building holding unit and a building unit that are achieved by operations of the control circuit.

The development tool unit which is software providing an application development environment provides an integrated environment for supporting designing coding debugging and testing the application using so called Graphical User Interface GUI . The development tool unit controls development environments for the application to be created in units referred to as Project. Specifically when creating application a user uses the development tool unit to define a project and edit a source code in the defined project. The project is constituted with files libraries and folders and components of the project are stored in the folders.

The resources for building holding unit holds various files libraries and similar matter required when building the application to be created in the project.

The building unit uses the files libraries and similar matter held in the resources for building holding unit to execute building to create desired application. The building herein means generating execution codes for the application based on the files in the resources for building holding unit . Generally it is a processing including steps such as compile and link.

The building unit includes a building execution unit a file extractor an interface reference unit and a manifest file creation unit .

The building execution unit is a program tool that actually builds application according to the resources for building holding unit such as a compiler.

When a platform of an operating system OS is present in a plurality version the file extractor extracts libraries commonly required for all of these platforms. The extracting herein means an action of searching all the platforms and arranging the library commonly required for all the platforms to the necessary locations for the project. This does not especially limit the location of the arrangement insofar as the path for the link upon building is open. Furthermore library commonly required is the common file in versions of all the platforms. This common file is fixed.

Following the extraction processing of the libraries commonly required the file extractor performs processing of searching the platform to be the target that is the file supporting the version of the project. It is necessary to distinct the files and the libraries for searching however an extension may be used for distinction. In this processing the file extractor identifies the libraries that are not common but in necessity.

The interface reference unit performs processing of querying the open interfaces for the remaining libraries that have not been extracted. Querying the open interface is a process in order that other applications search an Application Programming Interface API available by the other applications on the libraries. A process of querying the open interface which is stated in order to determine which API the application for the building uses or not use is dynamically created. The files which have described information on querying the open interface are manifest files and are necessary in the development environment when building.

The manifest file creation unit generates manifest files for difference searched by the interface reference unit and merges the files with the existing manifest files.

The processing by the above described configuration will be described. is a flowchart illustrating a project update processing by the application development support system .

When the user initiates the development environment the user operates the development tool unit and displays GUI for development on the display apparatus to start processing the creation of the application. First the file extractor refers to the resources for building holding unit searches all the projects existing in the object folders and confirms the version Step S . Specifically the file extractor searches all the projects existing in the object folders and lists up the target platform versions of the all projects. It should be noted that the target platform version is a version of the platform to be the target for example OS when the project is built to create the application. Thus the file extractor functions as a project version confirmation unit.

The file extractor determines whether or not the searched project is the same version as a version of the own environment Step S . When they are the same version Yes in Step S it is not necessary to update the project thus the processing for the update is terminated.

When they are different versions N in Step S the file extractor updates the version dependent files and performs processing of replacing the files that are different per version stored in the development environment for example the libraries Step S . Naturally the development environment holds the version dependent files of the own platform version. Thus the file extractor also functions as an updating unit.

Next the manifest file creation unit creates manifest files for difference from the open interface Step S and merges these files with the existing manifest files Step S . Specifically the manifest file creation unit creates the manifest file for difference searched by the interface reference unit and merges these files with the existing manifest files.

The application uses APIs of the platforms where the application operates. Relatively numerous platforms are required to describe which APIs or API groups are published and which APIs or API groups are used among them on the manifest files. For example it includes an OSGi environment or similar environment used for an embedded system. In this case the manifest file created by the project creators includes a portion where the project creators have described and a portion which is required by the platforms in one file. No simple replacement is accordingly available. As described above therefore creating the manifest file for difference from the open interface and merging this file with the existing manifest files will replace only the version depending portions required by the platforms.

As described the application development support system of the embodiment supports the target platforms of the development environment automatically when a plurality of the projects with various platforms to be the target exists. According to the result a table associating the platforms with the projects will be unnecessary. The conventional application development environment often manages the table which associates the files libraries manifest files and the platform version selects the version when building the application and specifies the necessary libraries to build. This is one factor by which the development environment becomes bloated and complicated. However for the application development support system of the embodiment switching a version of a platform which is a target is not performed by the selection method and the application development support system includes the own version file only.

Particularly the versions of the platforms are so often updated in open source OS such as Android registered trademark used in portable terminal for example and Linux registered trademark used in image forming apparatus for example that it is very effective to use the application development support system of the embodiment. It is advantageous in that no special resources and processing capacity are unnecessary and other existing functions are rarely affected. Furthermore the application development support system of the embodiment is effective for instance to generate application relating to an image forming apparatus such as a printer and a MFP. In other words some of the printer and the MFP are often used for a longer period than personal computers and portable terminals and thus require to support many versions of OSes. In this respect for the application of the image forming apparatus use of the application development support system of the embodiment ensures the facilitated creation of the application supporting various platforms.

While various aspects and embodiments have been disclosed herein other aspects and embodiments will be apparent to those skilled in the art. The various aspects and embodiments disclosed herein are for purposes of illustration and are not intended to be limiting with the true scope and spirit being indicated by the following claims.


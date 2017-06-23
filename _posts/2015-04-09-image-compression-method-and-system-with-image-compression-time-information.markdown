---

title: Image compression method and system with image compression time information
abstract: The present disclosure provides an image compression method and system. The method includes: receiving, by an access server, an image compression request submitted by a terminal; selecting, by the access server according to the image compression request's time information, an image compression server whose load is lower than a preset threshold, and sending the image compression request to the selected image compression server; compressing, by the selected image compression server, the images according to the image compression request, saving the compressed images, and forwarding URL addresses of the compressed images to the access server; and forwarding, by the access server, the URL addresses to the terminal. In the present disclosure, an image compression system processes an image compression request of a terminal, and performs load balancing automatically according to the load of various image compression servers in the system, thereby implementing automatic processing of mass images of the terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432672&OS=09432672&RS=09432672
owner: TENCENT TECHNOLOGY (SHENZHEN) COMPANY LIMITED
number: 09432672
owner_city: Shenzhen, Guangdong Province
owner_country: CN
publication_date: 20150409
---
This application is a continuation application of PCT Patent Application No. PCT CN2013 000889 entitled IMAGE COMPRESSION METHOD AND SYSTEM filed on Jul. 25 2013 which claims priority to Chinese Patent Application No. 201210384676.6 IMAGE COMPRESSION METHOD AND SYSTEM filed on Oct. 11 2012 both of which are hereby incorporated by reference in their entirety.

The present disclosure relates to the field of computer technologies and in particular to an image compression method and system.

Along with the development of image capturing devices images shot or created by the devices have increasingly higher quality and capacity. Moreover as the number of images increases increasingly more space is occupied by image data and accordingly an image compression technology emerges. Currently a commonly used compression method is to reorganize and encode image data by using technical means so as to obtain an image occupying less file space.

In the existing technology a user can perform compression processing on images by using an image processing application in a terminal and a professional developer can perform compression processing on images by calling an application programming interface API function provided by a third party code library and calling a development kit provided by the third party code library.

During implementation of the present application the inventor finds that the existing technology has at least the following problems 

When a user performs image compression processing by using an image processing application the user can only perform a compression operation on each image manually but cannot process the images in batches and the efficiency is low when a development kit provided by a third party code library is used to perform compression processing on images because the compression process is a compute intensive operation the user needs to deploy a load balancing process by himself herself when there are mass images which affects user experience.

The present disclosure takes into consideration the problems in the existing technology that a user terminal cannot compress images in batches and a professional need to deploy load balancing by himself herself when compressing images by using a development kit provided by a third party code library and provides an image compression method and system through multiple embodiments.

receiving by an access server an image compression request submitted by a terminal the image compression request including multiple to be compressed images or uniform resource locator URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images 

selecting by the access server according to the image compression time information a size of the to be compressed images and a target compression ratio an image compression server whose load is lower than a preset threshold and sending the image compression request to the selected image compression server so that the selected image compression server can compress the images according to the image compression request and save the compressed images 

receiving by the access server URL addresses of the compressed images from the selected image compression server and

The step of selecting by the access server according to the image compression time information an image compression server whose load is lower than a preset threshold and sending the image compression request to the selected image compression server may include 

selecting by the access server according to real time image compression time information an image compression server whose current load is lower than the preset threshold and sending the image compression request to the selected image compression server or 

dividing by the access server according to delayed image compression time information a period of time from a current time point to the delayed image compression time information into equal image compression intervals selecting in each of the image compression intervals an image compression server whose load is lower than the preset threshold and sending the image compression request to the selected image compression server.

The step of compressing by the selected image compression server the images according to the image compression request and saving the compressed images may include 

compressing by the selected image compression server the images according to the to be compressed images carried in the image compression request or 

acquiring by the selected image compression server the to be compressed images according to the URL addresses of the images carried in the image compression request and compressing the images.

After the step of receiving by an access server an image compression request submitted by a terminal the method may further include 

sending by the access server the to be compressed images to a fault tolerant backup server for backup or 

acquiring by the access server the to be compressed images according to the URL addresses and sending the to be compressed images to a fault tolerant backup server for backup.

sending by a compression algorithm control server a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

After forwarding by the access server the URL addresses of the compressed images to the terminal the method may further include 

extracting at least one of the URL addresses of the compressed images from the image download request 

deleting the corresponding compressed images after receiving from the terminal an acknowledgement of receiving the corresponding compressed images.

In another aspect an image compression system is provided which includes an access server having one or more processors memory and one or more program modules stored in the memory and to be executed by the one or more processors the one or more program modules further including a receiving module a processing module and a sending module 

the receiving module being configured to receive an image compression request submitted by a terminal the image compression request including multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images 

the processing module being configured to select according to the image compression time information a size of the to be compressed images and a target compression ratio an image compression server whose load is lower than a preset threshold and send the image compression request to the selected image compression server so that the selected image compression server can compress the images according to the image compression request and save the compressed images and

the sending module being configured to receive URL addresses of the compressed images and forward the URL addresses of the compressed images to the terminal.

The processing module includes at least one of a first processing unit and a second processing unit where

the first processing unit is configured for the access server to select according to real time image compression time information an image compression server whose current load is lower than the preset threshold and send the image compression request to the selected image compression server and

the second processing unit is configured for the access server to divide according to delayed image compression time information a period of time from a current time point to the delayed image compression time information into equal image compression intervals select in each of the image compression intervals an image compression server whose load is lower than the preset threshold and send the image compression request to the selected image compression server.

The image compression server may further include a compression module the compression module including at least one of a first compression unit and a second compression unit where

the first compression unit is configured to compress the images according to the to be compressed images carried in the image compression request save the compressed images and return URL addresses of the compressed images to the access server and

the second compression unit is configured to acquire the to be compressed images according to the URL addresses of the images carried in the image compression request compress the images save the compressed images and return URL addresses of the compressed images to the access server.

The access server may further include at least one of a first backup module and a second backup module where

the first backup module is configured to send the to be compressed images to a fault tolerant backup server for backup and

the second backup module is configured to acquire the to be compressed images according to the URL addresses and send the to be compressed images to a fault tolerant backup server for backup.

The system may further include a compression algorithm control server where the compression algorithm control server is configured to send a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

The technical solutions provided by the embodiments of the present application has the following beneficial effects 

An image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

In order make the objectives technical solutions and advantages of the present application more comprehensible the embodiments of the present application are described in further detail with reference to the accompanying drawings.

An embodiment of the present application provides an image compression method as shown in . The process of the method at least includes steps and that are performed by an access server.

Step An access server receives an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images. The image compression request may further optionally include compression related parameter information selected by a user at a website such as a size of the to be compressed images a target image compression ratio lossy or lossless processing manner and information about image resolution adjustment. In some embodiments the user of the terminal specifies his her preference for the compressed image by prioritizing the different compression related parameters. For example the user may assign a higher priority to the image compression time information if he she wants to receive the compressed images as quickly as possible or within a predefined time period. Alternatively if the user cares more about the compression quality he she may assign a higher priority to the target image compression ratio even if this means that he she may not receive the compressed images within the predefined time period dictated by the image compression time information.

Step The access server selects according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and sends the image compression request to the selected image compression server so that the selected image compression server can perform processing in step .

Step The selected image compression server compresses the images according to the image compression request saves the compressed images and returns URL addresses of the compressed images to the access server.

Step The access server receives the URL addresses of the compressed images from the selected image compression server and forwards the URL addresses of the compressed images to the terminal. This step enables the terminal to acquire the compressed images according to the URL addresses of the compressed images.

In some embodiments after forwarding the URL addresses of the compressed images to the terminal the access server detects an image download request from the terminal which may be triggered by a user selection of at least one of the URL addresses on the terminal. In response the access server extracts the user selected one of the URL addresses of the compressed images from the image download request identifies the corresponding compressed images associated with the URL address and returns the identified compressed images to the terminal. In some embodiments the access server then receives from the terminal an acknowledgement of receiving the corresponding compressed images. After that the access server deletes the corresponding compressed images.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

An embodiment of the present application provides an image compression method as shown in . It should be noted that in this embodiment of the present application real time compression processing is performed on images and the images are returned to a terminal after the real time compression processing. Further a server involved in this embodiment of the present application may be a single server or may also be a server cluster which is not limited herein.

The process of the method at least includes steps and that are performed by an access server and may further include optional steps and .

Step An access server receives an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images. In some embodiments the image compression request includes a size of the to be compressed images and a target compression ratio.

Specifically after a terminal chooses to perform image compression processing in real time the sent image compression request includes one or more to be compressed images or URL addresses corresponding to the to be compressed images uploaded by the terminal and at the same time the image compression request further includes image compression time information corresponding to each of the to be compressed images. Correspondingly in this embodiment of the present application the image compression time information is real time image compression time information. Further the image compression request may further optionally include compression related parameter information selected by the user at a website such as a size of the to be compressed images a target image compression ratio lossy or lossless processing manner and information about image resolution adjustment.

Preferably in this embodiment of the present application to be compressed images uploaded by the user are received in the process of requesting real time image compression.

Optional step The access server sends the to be compressed images to a fault tolerant backup server for backup or acquires the to be compressed images according to the URL addresses of the to be compressed images and sends the to be compressed images to a fault tolerant backup server for backup.

Preferably the access server may back up in advance the to be compressed images carried in the image compression request submitted by the terminal and send the to be compressed images to the fault tolerant backup server before compression. This prevents the failure of the image compression service due to loss of original images that is caused by an error occurring during the compression process of the image compression server.

When the image compression server fails in implementing the image compression process the image compression server sends to the access server a request for acquiring backup images the access server sends according to the request message a request for searching for the backup images to the fault tolerant backup server after finding the backup images the fault tolerant backup server returns the backup images to the access server and the access server further returns the images to the image compression server for recompression.

Step The access server selects according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and sends the image compression request to the selected image compression server so that the selected image compression server can perform processing in step .

Specifically after the terminal chooses to perform the image compression service in real time the time information in the image compression request is real time image compression time information and therefore the access server needs to respond to the request in real time to compress the images.

The image compression service is a compute intensive operation and the computing capability of a server is used to process the function of image compression therefore for purpose of load balancing the access server first checks the load situation of each image compression server in a current image compression server cluster so as to obtain the load of each image compression server and then an image compression server whose load is lower than a preset threshold that is an image compression server having a low load is selected as a target image compression server to which an image compression request of the terminal is allocated. Then the received image compression request is sent to the target image compression server by using a message for distributing compression tasks.

Step The access server selects according to the real time image compression time information an image compression server whose current load is lower than the preset threshold and sends the image compression request to the selected image compression server.

Step The selected image compression server compresses the images according to the image compression request saves the compressed images and returns URL addresses of the compressed images to the access server.

After the image carried in the image compression request is compressed according to a compression mode selected by the user the compressed image is sent to an image storage server and the image storage server saves the compressed image and returns to the image compression server a URL address at which the image is saved. The image compression server returns a result of the image compression and the URL address saved after the image compression to the access server.

Step The selected image compression server compresses the images according to the to be compressed images carried in the image compression request saves the compressed images and returns URL addresses of the compressed images to the access server.

Step The access server receives the URL addresses of the compressed images from the selected image compression server and forwards the URL addresses of the compressed images to the terminal. This step enables the terminal to acquire the compressed images according to the URL addresses of the compressed images.

Optional step The compression algorithm control server sends a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

Preferably in the whole system a compression algorithm control server may further be additionally deployed in the whole system. The compression algorithm control server performs two way data interaction with the image compression computing server. The compression algorithm control server may control by transmitting an updated parameter such as an updated compression algorithm and or kernel data the image compression server to perform a corresponding operation.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

An embodiment of the present application provides an image compression method as shown in . It should be noted that in this embodiment of the present application delayed compression processing is performed on images and the images are returned to a terminal after the delayed compression processing. Further a server involved in this embodiment of the present application may be a single server or may also be a server cluster which is not limited herein.

The process of the method at least includes steps and that are performed by an access server and may further include optional steps and .

Step An access server receives an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images.

Specifically the functions of the access server in this embodiment of the present application may be managed and implemented by using two different servers and correspondingly the two servers are an offline compression service control server and an offline compression scheduling server.

The offline compression service control server in the access server is responsible for managing a registration service after a terminal selects delayed image compression. First after the terminal selects a service for performing delayed image compression the sent image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images uploaded by the terminal and at the same time the image compression request further includes image compression time information corresponding to each of the to be compressed images. Correspondingly in this embodiment of the present application the image compression time information is delayed image compression time information that is currently the images are not compressed in real time. Further the image compression request further includes compression related parameter information selected by the user at a website such as a target image compression ratio lossy or lossless processing manner and information about image resolution adjustment.

The image compression request is sent to the offline compression service control server and registration is performed in the server according to an agreed format protocol so as to register the URL addresses of the to be processed images a temporal frequency of processing that is delayed image processing time information and related compression parameters.

The delayed image processing time information selected by the user may be for example one day one week or the like and the user receives the compressed images when the time expires. Therefore the image compression system does not need to perform compression processing on the images in real time and can make full use of the period of time from the current time point to the expiration time to properly allocate time and image compression servers for processing so that the amount of computation required for centralized compression of images of the user is distributed to multiple time periods to complete the compression task thereby greatly reducing dependence on the amount of computation.

Optional step The access server sends the to be compressed images to a fault tolerant backup server for backup or acquires the to be compressed images according to the URL addresses of the to be compressed images and sends the to be compressed images to a fault tolerant backup server for backup.

Preferably the offline compression scheduling server in the access server may back up in advance the to be compressed images or the images corresponding to the URL addresses of the to be compressed images that are carried in the image compression request submitted by the terminal or may send the URL addresses of the to be compressed images to a fault tolerant backup server before compression and the fault tolerant backup server acquires the images according to the URL addresses and saves the images for backup. This prevents the failure of the image compression service due to loss of original images that is caused by an error occurring during the compression process of the image compression server.

When the image compression server fails in implementing the image compression process the image compression server sends to the offline compression scheduling server in the access server a request for acquiring backup images the offline compression scheduling server in the access server sends according to the request message a request for searching for the backup images to the fault tolerant backup server after finding the backup images the fault tolerant backup server returns the backup images to the offline compression scheduling server in the access server and the offline compression scheduling server in the access server further returns the images to the image compression server for recompression.

Step The access server selects according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and sends the image compression request to the selected image compression server so that the selected image compression server can perform processing in step .

Specifically the offline compression scheduling server in the access server is responsible for balancing overall scheduling tasks. After receiving the image compression request submitted by the terminal and completing the registration process the offline compression service control server sends the image compression request to the offline compression scheduling server and the offline compression scheduling server schedules the compression tasks according to queuing tasks and delayed image compression time information in the image compression request of the current task.

In this case the offline compression scheduling server in the access server divides a period of time from a current time point to the delayed image compression time information into equal image compression intervals according to the delayed image compression time information in the image compression request of the current task. The load situation of each image compression server in the current image compression server cluster is checked in each of the image compression intervals so as to obtain the load of each image compression server and then an image compression server whose load is lower than a preset threshold that is an image compression server having a low load is selected as a target image compression server to which the image compression request of the terminal is allocated. Then the received image compression request is sent to the target image compression server by using a message for distributing compression tasks. Once all images corresponding to the image compression request are compressed the task corresponding to the image compression request is finished.

Step The access server divides according to the delayed image compression time information a period of time from a current time point to the delayed image compression time information into equal image compression intervals selects in each of the image compression intervals an image compression server whose load is lower than the preset threshold and sends the image compression request to the selected image compression server.

Step The selected image compression server compresses the images according to the image compression request saves the compressed images and returns URL addresses of the compressed images to the access server.

After receiving an image compression request corresponding to a distributed compression task the image compression server first acquires an image according to a URL address in the image compression request and then compresses the image.

After the image carried in the image compression request is compressed according to a compression mode selected by the user the compressed image is sent to an image storage server and the image storage server saves the compressed image and returns to the image compression server a URL address at which the image is saved. The image compression server returns a result of the image compression and the URL address saved after the image compression to the access server.

Step The selected image compression server acquires the to be compressed images according to the URL addresses of the images carried in the image compression request compresses the images saves the compressed images and returns URL addresses of the compressed images to the access server.

Specifically the URL addresses of the compressed images are returned to the offline compression scheduling server in the access server.

Step The access server receives the URL addresses of the compressed images from the selected image compression server and forwards the URL addresses of the compressed images to the terminal. This step enables the terminal to acquire the compressed images according to the URL addresses of the compressed images.

The offline compression scheduling server in the access server returns the URL addresses of the compressed images to the terminal according to an interface agreed with the terminal.

Optional step The compression algorithm control server sends a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

Preferably a compression algorithm control server may further be additionally deployed in the whole system. The compression algorithm control server performs two way data interaction with the image compression computation server. The compression algorithm control server may control by transmitting an updated parameter such as an updated compression algorithm and or kernel data the image compression server to perform a corresponding operation.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

The system includes an access server and the access server is connected to an image compression server . One or more terminals are connected to the access server via a network e.g. the Internet . A user of the terminal may send an image compression request to the access server so as to compress one or more images identified in the request. For example the user may have a user account at the access server for uploading and sharing images with others through the Internet. At some point the user may want to download some of the pictures from the access server. Instead of performing the download operation once for each picture the user may specify a set of parameters for a set of pictures to be downloaded to the terminal. In order to make the download of multiple pictures more efficiently the terminal then generates an image compression request based on the set of parameters. In some embodiments the image compression request specifies not only which picture s need to be compressed but also when e.g. using the image compression time information and how e.g. using the target compression ratio . Upon receipt of the image compression request the access server performs necessary operations accordingly and returns one or more URL addresses pointing to the user desired compressed images to the terminal so that the user can download a large number of compressed images through a user selection of the one of the URL addresses.

In some embodiments the access server has one or more processors memory and one or more program modules stored in the memory and to be executed by the one or more processors. For example the one or more program modules further includes a receiving module a processing module and a sending module .

The receiving module is configured to receive an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images.

The processing module is configured to select according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and send the image compression request to the selected image compression server so that the selected image compression server compresses the images according to the image compression request and saves the compressed images.

The sending module is configured to receive URL addresses of the compressed images and forward the URL addresses of the compressed images to the terminal so that the terminal can acquire the compressed images according to the URL addresses of the compressed images.

The image compression server includes a compression module where the compression module is configured to compress the images according to the image compression request save the compressed images and return URL addresses of the compressed images to the access server.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

The system includes an access server and the access server is connected to an image compression server .

The receiving module is configured to receive an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images.

The processing module is configured to select according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and send the image compression request to the selected image compression server so that the selected image compression server compresses the images according to the image compression request and saves the compressed images.

The sending module is configured to receive URL addresses of the compressed images and forward the URL addresses of the compressed images to the terminal so that the terminal can acquire the compressed images according to the URL addresses of the compressed images.

a first processing unit not shown configured for the access server to select according to real time image compression time information an image compression server whose load is lower than the preset threshold and send the image compression request to the selected image compression server.

a first backup module configured to send the to be compressed images to a fault tolerant backup server for backup.

The compression module is configured to compress the images according to the image compression request save the compressed images and return URL addresses of the compressed images to the access server.

a first compression unit not shown configured to compress the images according to the to be compressed images carried in the image compression request save the compressed images and return URL addresses of the compressed images to the access server.

the compression algorithm control server is configured to send a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

The system includes an access server and the access server is connected to an image compression server .

The receiving module is configured to receive an image compression request submitted by a terminal where the image compression request includes multiple to be compressed images or URL addresses corresponding to the to be compressed images and image compression time information corresponding to each of the to be compressed images.

The processing module is configured to select according to the image compression time information the size of the to be compressed images and the target compression ratio an image compression server whose load is lower than a preset threshold and send the image compression request to the selected image compression server so that the selected image compression server compresses the images according to the image compression request and saves the compressed images.

The sending module is configured to receive URL addresses of the compressed images and forward the URL addresses of the compressed images to the terminal so that the terminal can acquire the compressed images according to the URL addresses of the compressed images.

a second processing unit not shown configured for the access server to divide according to delayed image compression time information a period of time from a current time point to the delayed image compression time information into equal image compression intervals select in each of the image compression intervals an image compression server whose load is lower than the preset threshold and send the image compression request to the selected image compression server.

a second backup module configured to acquire the to be compressed images according to the URL addresses and send the to be compressed images to a fault tolerant backup server for backup.

The compression module is configured to compress the images according to the image compression request save the compressed images and return URL addresses of the compressed images to the access server.

a second compression unit not shown configured to acquire the to be compressed images according to the URL addresses of the images carried in the image compression request compress the images save the compressed images and return URL addresses of the compressed images to the access server.

The compression algorithm control server is configured to send a compression algorithm and or kernel data updating command to the image compression server so that the image compression server adjusts its own image compression manner according to the updated compression algorithm and or kernel data.

In this embodiment of the present application an image compression system processes an image compression request of a terminal and performs load balancing automatically according to the load of various image compression servers in the system thereby implementing processing of mass images of the terminal while achieving the objective of automatic adjustment of load balancing.

The sequence numbers of the foregoing embodiments of the present application are merely for the convenience of description and do not imply the preference among the embodiments. The technical features in one embodiment may be applied to other embodiments as long as no technical conflict is generated.

A person of ordinary skill in the art may understand that all or some of the steps of the foregoing embodiments may be implemented by using hardware or may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium. The storage medium may be a read only memory a magnetic disk an optical disc or the like.

The foregoing descriptions are merely preferred embodiments of the present application but are not intended to limit the present disclosure. Any modification equivalent replacement or improvement made within the spirit and principle of the present disclosure shall fall within the protection scope of the present disclosure.


---

title: Information processing method, information processing device, and program that facilitates image processing operations on a mobile device
abstract: An information processing method for causing a computer to process an image, wherein the image processing method causes the computer to execute an acquisition step of acquiring the image, and an output step of outputting an output image by separating between an editing area that is a predetermined area where the image is editable on the image and a changing area other than the predetermined area on the image, wherein, in a case where an operation is done on the changing area, the editing area is moved, and in a case where an operation is done on the editing area, the editing area is not moved.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09646404&OS=09646404&RS=09646404
owner: Ricoh Company, Ltd.
number: 09646404
owner_city: Tokyo
owner_country: JP
publication_date: 20151028
---
This application is a continuation application filed under 35 U.S.C. 111 a claiming the benefit under 35 U.S.C. 120 and 365 c of a PCT International Application No. PCT JP2015 057610 filed on Mar. 10 2015 which is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2014 054783 filed on Mar. 18 2014 the entire contents of which are incorporated herein by reference.

The present invention relates to at least one of an information processing method an information processing device and a program.

A user interface that will be referred to as a UI below has been known for accepting an instruction from a user with respect to display of a panoramic image in a panoramic image display see for example Japanese Patent Application Publication No. 2011 076249 .

However a conventional UI assigns a function for scrolling an image to so called dragging at a time of image display on a smartphone or the like and hence it may be difficult for a user to execute an image operation for example editing of an image or the like.

According to one aspect of the present invention there is provided an information processing method for causing a computer to process an image wherein the image processing method causes the computer to execute an acquisition step of acquiring the image and an output step of outputting an output image by separating between an editing area that is a predetermined area where the image is editable on the image and a changing area other than the predetermined area on the image wherein in a case where an operation is done on the changing area the editing area is moved and in a case where an operation is done on the editing area the editing area is not moved.

The image taking device has a plurality of optical systems and produces and outputs to the smartphone for example a taken image of a wide range such as all directions around the image taking device that will be referred to as an all celestial sphere image below . Details of the image taking device and an all celestial sphere image will be described below. An image that is processed by the image taking system is for example an all celestial sphere image. A panoramic image is for example an all celestial sphere image. An example of an all celestial sphere image will be described below.

An information processing device is for example the smartphone . The smartphone will be described as an example below. The smartphone is a device for causing a user to operate an all celestial sphere image acquired from the image taking device . The smartphone is a device for causing a user to output an acquired all celestial sphere image. A detail of the smartphone will be described below.

The image taking device and the smartphone are subjected to wired or wireless connection. For example the smartphone downloads from the image taking device and inputs to the smartphone data such an all celestial sphere image output from the image taking device . Here connection may be executed through a network.

Here an entire configuration is not limited to a configuration illustrated in . For example the image taking device and the smartphone may be an integrated device. Furthermore another computer other than the image taking device and the smartphone may be connected to be composed of three or more devices.

The image taking device has a front side image taking element H a back side image taking element H and a switch H. A hardware that is provided in an interior of the image taking device will be described below.

The image taking device produces an all celestial sphere image by using images taken by the front side image taking element H and the back side image taking element H.

The switch H is a so called shutter button and is an input device for causing a user to execute an instruction of image taking for the image taking device .

The image taking device is held by hand of a user for example as illustrated in and the switch H is pushed to execute image taking.

As illustrated in a user holds the image taking device by hand and pushes the switch H in and to execute image taking. As illustrated in it is possible for the image taking device to take an image in all directions around the image taking device by the front side image taking element H in and and the back side image taking element H in and .

An image taken by the front side image taking element H in and is an image with an image taking range that is a wide range in a front direction of the image taking device for example a range of 180 as an angle of view as illustrated in . An image taken by the front side image taking element H in and has a distortion aberration as illustrated in in a case where the front side image taking element H in and uses an optical system for taking an image with a wide range for example a so called fisheye lens . An image in taken by the front side image taking element H in and is a so called hemispherical image that has a wide range in one side of the image taking device and a distortion aberration that will be referred to as a hemispherical image below .

Here it is desirable for an angle of view to be within a range greater than or equal to 180 and less than or equal to 200 . In particular as a hemispherical image in and a hemispherical image in that will be described below are synthesized in a case where an angle of view is greater than 180 there is an overlapping image area and hence synthesis is facilitated.

An image taken by the back side image taking element H in and is an image with an image taking range that is a wide range in a back direction of the image taking device for example a range of 180 as an angle of view as illustrated in .

An image in taken by the back side image taking element H in and is a hemispherical image similar to that of .

The image taking device executes processes such as a distortion correction process and a synthesis process and thereby produces an image illustrated in from a front side hemispherical image in and a back side hemispherical image in . is an image produced by for example Mercator s projection equidistant cylindrical projection or the like namely an all celestial sphere image.

Here an all celestial sphere image is not limited to an image produced by the image taking device . An all celestial sphere image may be for example an image taken by another camera or the like or an image produced based on an image taken by another camera. It is desirable for an all celestial sphere image to be an image with a view angle in a wide range taken by a so called all direction camera a so called wide angle lens camera or the like.

Furthermore an all celestial sphere image will be described as an example and an image is not limited to such an all celestial sphere image. An image may be for example an image or the like taken by a compact camera a single lens reflex camera a smartphone or the like. An image may be a panoramic image that extends horizontally or vertically or the like.

The image taking device has an image taking unit H an image processing unit H an image control unit H a Central Processing Unit CPU H and a Read Only Memory ROM H. Furthermore the image taking device has a Static Random Access Memory SRAM H a Dynamic Random Access Memory DRAM H and an operation interface I F H. Moreover the image taking device has a network I F H a wireless I F H and an antenna H. Each component of the image taking device is connected through a bus H and executes input or output of data or a signal.

The image taking unit H has the front side image taking element H and the back side image taking element H. A lens H that corresponds to the front side image taking element H and a lens H that corresponds to the back side image taking element H are placed. The front side image taking element H and the back side image taking element H are so called camera units . The front side image taking element H and the back side image taking element H have optical sensors such as a Complementary Metal Oxide semiconductor CMOS or a Charge Coupled Device CCD . The front side image taking element H executes a process for converting light incident on the lens H to produce image data. The back side image taking element H executes a process for converting light incident on the lens H to produce image data. The image taking unit H outputs image data produced by the front side image taking element H and the back side image taking element H to the image processing unit H. For example image data are the front side hemispherical image in and the back side hemispherical image in or the like.

Here the front side image taking element H and the back side image taking element H may have an optical element other than a lens such as a stop or a low pass filter in order to execute image taking with a high image quality. Furthermore the front side image taking element H and the back side image taking element H may execute a process such as a so called defective pixel correction or a so called hand movement correction in order to execute image taking with a high image quality.

The image processing unit H executes a process for producing an all celestial sphere image in from image data that are input from the image taking unit H. A detail of a process for producing an all celestial sphere image will be described below. Here a process that is executed by the image processing unit H may be such that a part or an entirety of a process is executed in parallel and redundantly by another computer.

The image taking control unit H is a control device that controls each component of the image taking device .

The CPU H executes an operation or a control for each process that is executed by the image taking device . For example the CPU H executes each kind of program. Here the CPU H may be composed of a plurality of CPUs or devices or a plurality of cores in order to attain speeding up due to parallel processing. Furthermore a process of the CPU H may be such that another hardware resource is provided inside or outside the image taking device and caused to execute a part or an entirety of a process for the image taking device .

The ROM H the SRAM H and the DRAM H are examples of a storage device. The ROM H stores for example a program data or a parameter to that is executed by the CPU H. The SRAM H and the DRAM H store for example a program data to be used in a program data to be produced by a program a parameter or the like in a case where the CPU H executes a program. Here the image taking device may have an auxiliary storage device such as a hard disk.

The operation I F H is an interface that executes a process for inputting an operation of a user to the image taking device such as the switch H. The operation I F H is an operation device such as a switch a connector or cable for connecting an operation device a circuit for processing a signal input from an operation device a driver a control device or the like. Here the operation I F H may have an output device such as a display. Furthermore the operation I F H may be a so called touch panel wherein an input device and an output device are integrated or the like. Moreover the operation I F H may have an interface such as a Universal Serial Bus USB connect a storage medium such as Flash Memory Flash Memory is a registered trademark and input from and output to the image taking device data.

Here the switch H may have an electric power source switch for executing an operation other than a shutter operation a parameter input switch or the like.

The network I F H the wireless I F H and the antenna H are devices for connecting the image taking device with another computer through a wireless or wired network and a peripheral circuit or the like. For example the image taking device is connected to a network through the network I F H and transmits data to the smartphone . Here the network I F H the wireless I F H and the antenna H may be configured to be connected by using a connector such as a USB a cable or the like.

The bus H is used for an input or an output of data or the like between respective components of the image taking device . The bus H is a so called internal bus . The bus H is for example a Peripheral Component Interconnect Bus Express PCI Express .

Here the image taking device is not limited to a case of two image taking elements. For example it may have three or more image taking elements. Moreover the image taking device may change an image taking angle of one image taking element to take a plurality of partial images. Furthermore the image taking device is not limited to an optical system that uses a fisheye lens. For example a wide angle lens may be used.

Here a process that is executed by the image taking device is not limited to that is executed by the image taking device . A part or an entirety of a process that is executed by the image taking device may be executed by the smartphone or another computer connected through a network while the image taking device may transmit data or a parameter.

An information processing device is a computer. An information processing device may be for example a notebook Personal Computer PC a Personal Digital Assistance PDA a tablet a mobile phone or the like other than a smartphone.

The smartphone that is one example of an information processing device has an auxiliary storage device H a main storage device H an input output device H a state sensor H a CPU H and a network I F H. Each component of the smartphone is connected to a bus H and executes an input or an output of data or a signal.

The auxiliary storage device H stores information such as each kind of data that includes an intermediate result of a process executed by the CPU H due to a control of the CPU H a control device or the like a parameter or a program. The auxiliary storage device H is for example a hard disk a flash Solid State Drive SSD or the like. Here information stored in the auxiliary storage device H is such that a part or an entirety of such information may be stored in a file server connected to the network I F H or the like instead of the auxiliary storage device H.

The main storage device H is a main storage device such as a storage area to be used by a program that is executed by the CPU H that is a so called Memory . The main storage device H stores information such as data a program or a parameter. The main storage device H is for example a Static Random Access Memory SRAM a DRAM or the like. The main storage device H may have a control device for executing storage in or acquisition from a memory.

The input output device H is a device that has functions of an output device for executing display and an input device for inputting an operation of a user.

The input output device H executes a process for displaying to a user an image input in for example a predetermined Graphical User Interface GUI or the smartphone .

The input output device H executes a process for inputting an operation of a user for example in a case where a GUI with a display or an image is operated by such a user.

The state sensor H is a sensor for detecting a state of the smartphone . The state sensor H is a gyro sensor an angle sensor or the like. The state sensor H determines for example whether or not one side that is possessed by the smartphone is provided at a predetermined or greater angle with respect to a horizon. That is the state sensor H executes a detection as to whether the smartphone is provided at a state of a longitudinally directional attitude or a state of a laterally directional attitude.

The CPU H executes a calculation in each process that is executed by the smartphone and a control of a device that is provided in the smartphone . For example the CPU H executes each kind of program. Here the CPU H may be composed of a plurality of CPUs or devices or a plurality of cores in order to execute a process in parallel redundantly or dispersedly. Furthermore a process for the CPU H is such that another hardware resource may be provided inside or outside the smartphone to execute a part or an entirety of a process for the smartphone . For example the smartphone may have a Graphics Processing Unit GPU for executing image processing or the like.

The network I F H is a device such as an antenna a peripheral circuit a driver or the like for inputting or outputting data or the like that is connected to another computer through a wireless or wired network. For example the smartphone executes a process for inputting image data from the image taking device due to the CPU H and the network I F H. The smartphone executes a process for outputting a predetermined parameter or the like to the image taking device due to the CPU H and the network I F H.

Similarly to is a diagram illustrated in such a manner that positions in a hemispherical image in where incidence angles are equal in a horizontal direction or a vertical direction with respect to an optical axis are connected by a line.

As illustrated in a synthesis process is to produce an image by using a plurality of images for example in a state illustrated in . Here a synthesis process is not limited to a process for simply arranging pre processed images successively. For example in a case where a center of an all celestial sphere image in a horizontal direction is not provided at 180 a synthesis process may be a process for executing a synthesis process in such a manner that a pre processed image in is arranged at a center of an all celestial sphere image and a pre processed image in is divided and arranged at left and right sides thereof so as to produce an all celestial sphere image illustrated in .

Here a process for producing an all celestial sphere image is not limited to a process in accordance with equidistant cylindrical projection. For example a so called upside down case is provided in such a manner that like an alignment of pixels in a direction of is upside down with respect to an alignment in and an alignment of pixels in a direction of is left right reversal with respect to an alignment in . In an upside down case the image taking device may execute a process for rolling or rotating a pre processed image in a state of by 180 so as to align with an alignment of pixels in a direction of and a direction of in .

Furthermore a process for producing an all celestial sphere image may execute a correction process for correcting distortion aberration that is provided in an image in a state of or . Moreover a process for producing an all celestial sphere image may execute a process for improving an image quality for example shading correction gamma correction white balance hand movement correction an optical black correction process a defective pixel correction process an edge enhancement process a linear correction process or the like.

Here for example in a case where an image taking range of a hemispherical image overlaps with an image taking range of another hemispherical image a synthesis process may execute correction by utilizing an overlapping range to execute such a synthesis process at high precision.

Due to a process for producing an all celestial sphere image the image taking device produces an all celestial sphere image from a hemispherical image that is taken by the image taking device .

At step S the smartphone executes a process for acquiring an all celestial sphere image produced at step S. A case where the smartphone acquires an all celestial sphere image in will be described as an example below.

At step S the smartphone produces an all celestial sphere panoramic image from an all celestial sphere image acquired at step S. An all celestial sphere panoramic image is an image provided in such a manner that an all celestial sphere image is applied onto a spherical shape.

At step S the smartphone executes a process for producing an all celestial sphere panoramic image in from an all celestial sphere image in .

A process for producing an all celestial sphere panoramic image is realized by for example an Application Programming Interface API such as Open GL Open GL is a registered trademark for Embedded Systems Open GL ES .

An all celestial sphere panoramic image is produced by dividing an image into triangles joining vertices P of triangles that will be referred to as vertices P below and applying a polygon thereof.

At step S the smartphone executes a process for causing a user to input an operation for starting an output of an image. At step S the smartphone for example reduces and outputs an all celestial sphere panoramic image produced at step S that is displays a so called thumbnail image . In a case where a plurality of all celestial sphere panoramic images are stored in the smartphone the smartphone outputs a list of thumbnail images for example to cause a user to select an image to be output. At step S the smartphone executes for example a process for inputting an operation for causing a user to select one image from a list of thumbnail images.

At step S the smartphone executes a process for producing an initial image based on an all celestial sphere panoramic image selected at step S.

As illustrated in a three dimensional coordinate system with XYZ axes will be described below. The smartphone places a virtual camera at a position of an origin and produces each kind of image at a viewpoint of the virtual camera . In a case of a coordinate system in an all celestial sphere panoramic image is represented by for example a sphere CS. The virtual camera corresponds to a viewpoint of a user that views an all celestial sphere panoramic image wherein such an all celestial sphere panoramic image is a sphere CS at a placed position thereof.

A predetermined area T is an area where a view angle of the virtual camera is projected onto a sphere CS. The smartphone produces an image based on a predetermined area T.

A view angle is an angle that indicates an angle of the virtual camera as illustrated in . In a case of a diagonal angle of view L of a predetermined area T that is represented by a view angle coordinates of a center point CP of such a predetermined area T are represented by x y in predetermined area information.

Here a distance from the virtual camera to a center point CP is represented by Formula 1 described below tan 2 Formula 1 

An initial image is an image provided by determining a predetermined area T based on a preliminarily set initial setting and being produced based on such a determined predetermined area T. An initial setting is for example x y 0 0 34 or the like.

At step S the smartphone causes a user to execute an operation for switching to an image editing mode. Here in a case where a user does not execute an operation for switching to an image editing mode the smartphone outputs for example an initial image.

An output image is for example an output image at an initial state. An output image has an editing image at an initial state and a changing image at an initial state.

An output image displays a button for a Graphical User Interface GUI for accepting an operation of a user. A GUI is for example a blur editing button a cancellation editing button or the like. Here an output image may have another GUI.

An editing area at an initial state and a changing area at an initial state are combined into an output identical to an initial image produced at step S. An output image has a separation line for separating and outputting the editing area and the changing area . Here the separation line is not limited to a solid line. The separation line may be for example a broken line a pattern or the like. Furthermore the smartphone may change a pattern of the separation line such as a color or a kind of line of the separation line in such a manner that the separation line is readily viewed by a user with respect to a peripheral pixel to be output. For example in a case of an output image with many white objects such as a snow scene the smartphone outputs the separation line as a solid line with a blue color. For example in a case of an output image with many reflective objects such as a cluster of high rise buildings the smartphone outputs the separation line as a thick solid line with a red color. For example in a case of an output image with many objects such as a graph or a design drawing the smartphone outputs the separation line as a thick broken line with a green color.

A pattern of a separation line is changed depending on an object or a background and thereby it is possible for the smartphone to cause a user to readily view a separation between areas.

Here although a separation line is clearly indicated to cause a user to readily view a separation between areas a separation line may not be displayed. For example a separation line disturbs a user that has gotten familiar with an operation and hence the smartphone may control display non display of such a separation line. Moreover the smartphone may change a contrast of an editing area or a contrast of a changing area instead of displaying a separation line so that it is possible to identify a separation between areas. In this case an embodiment is realized by a configuration provided in such a manner that the smartphone controls a contrast for an area in an output image by using coordinates of an editing area and coordinates of a changing area.

A user edits an image in an image editing mode and hence applies an operation to an editing area or a changing area that is displayed in an output image.

At step S the smartphone executes a process for causing a user to input an operation for editing an image.

At step S the smartphone acquires coordinates where a user inputs an operation for the input output device H. At step S the smartphone executes a process for determining whether an operation is executed for an area in the editing area at an initial state in or an operation is executed for an area in the changing area at an initial state in based on acquired coordinates.

Image editing is editing that is executed based on an operation of a user. Editing of an area to be output is editing for changing an area to be output in an image based on a changing area or editing executed for a predetermined area based on an editing area.

Editing for changing an area to be output is executed in a case where an operation is applied to an area of a changing area at step S.

Editing to be executed for a predetermined area based on an editing area is executed in a case where an operation is applied to an area in an editing area at step S.

In a case where a user operates a changing area an area in a changing area is determined at step S the smartphone goes to step S. In a case where a user operates an editing area an area in an editing area is determined at step S the smartphone goes to step S.

An output image is for example an output image after editing an area to be output. The output image after editing an area to be output has an editing area after editing an area to be output and a changing area after editing an area to be output. The output image after editing an area to be output has a separation line for separating and outputting the editing area after editing an area to be output and the changing area after editing an area to be output similarly to the output image at an initial state.

The output image after editing an area to be output is an image produced by changing a predetermined area T as illustrated in and in the output image at an initial state in . The output image after editing an area to be output is to output an image that corresponds to a predetermined area T changed by the editing area after editing an area to be output and the changing area after editing an area to be output similarly to the output image at an initial state.

The output image after editing an area to be output is provided at for example a viewpoint of a case where the virtual camera at a state of is pan rotated as illustrated in .

Editing of an area to be output is executed in such a manner that a user operates a screen area where a changing image is output.

An operation to be input at step S is for example an operation for changing an area to be output with respect to left and right directions of an image or the like.

In a case of and an operation that is input by a user is such that a screen where the changing area at an initial state in is traced with a finger in left and right directions of such a screen as illustrated in that is a so called swipe operation or the like.

A relation between a polar coordinate system of an all celestial sphere in and and an input amount dx dy is represented by Formula 2 described below Formula 2 

An output image is changed based on an input amount input for a swipe operation and hence it is possible for a user to operate an image with a feeling that a sphere such as a terrestrial globe is rotated.

Here for simplifying a process what position of a screen a swipe operation is input at may not be taken into consideration. That is similar values may be input for an input amount dx dy in Formula 2 even though a swipe operation is executed at any position of a screen where the changing area at an initial state is output.

The changing area after editing an area to be output executes perspective projection transformation of coordinates Px Py Pz of a vertex P in a three dimensional space based on calculated in accordance with Formula 2 .

In a case where a user executes a swipe operation with an input amount dx dy in a case of a polar coordinate system of an all celestial sphere is represented by Formula 3 described below 2 2 Formula 3 

As illustrated in 3 described above a polar coordinate system of an all celestial sphere is calculated based on a total value of input amounts for respective swipe operations. Even in a case where a plurality of swipe operations are executed or the like calculation of a polar coordinate system of an all celestial sphere is executed and thereby it is possible to keep constant operability.

Here editing of an area to be output is not limited to pan rotation. For example tilt rotation of the virtual camera in upper and lower directions of an image may be realized.

An operation that is input at step S is for example an operation for enlarging or reducing an area to be output or the like.

In a case where enlargement of an area to be output is executed an operation that is input by a user is such that two fingers are spread on a screen where the changing area at an initial state in is output as illustrated in that is a so called pinch out operation or the like.

In a case where reduction of an area to be output is executed an operation that is input by a user is such that two fingers are moved closer to each other on a screen where the changing area at an initial state in is output as illustrated in that is a so called pinch in operation or the like.

Here a pinch out or pinch in operation is sufficient as long as a position where a finger of a user first contacts is provided in an area with a changing image displayed thereon and may be an operation that subsequently uses an area with an editing area displayed thereon. Furthermore an operation may be executed by a so called stylus pen that is a tool for operating a touch panel or the like.

In a case where an operation illustrated in and is input the smartphone executes a so called zoom process .

A zoom process is a process for producing an image with a predetermined area enlarged or reduced based on an operation that is input by a user.

In a case where an operation illustrated in and is input the smartphone acquires an amount of change dz based on an operation that is input by a user.

A zoom process is a process for executing calculation in accordance with Formula 4 described below 0 Formula 4 based on an amount of change dz.

 indicated in Formula 4 described above is a view angle of the virtual camera as illustrated in and . m indicated in Formula 4 is a coefficient for adjusting an amount of zoom. 0 indicated in Formula 4 is a view angle at an initial state that is a view angle in a case where an initial image is produced at step S.

In a case where an operation illustrated in and is input the smartphone determines a range of a predetermined area T in and by using a view angle calculated in accordance with Formula 4 for a projection matrix.

In a case where calculation is executed in accordance with Formula 4 and a user executes an operation for providing an amount of change dz the smartphone executes calculation in accordance with Formula 5 described below 0 2 Formula 5 

As indicated in 5 described above a view angle is calculated based on a total value of amounts of change due to operations as illustrated in and . Even in a case where a plurality of operations as illustrated in and are executed or the like calculation of a view angle of a celestial sphere is executed and thereby it is possible to keep constant operability.

A zoom process may be realized by combining a view angle of the virtual camera and a change in a position of a viewpoint.

An origin in is provided at an initial position of the virtual camera . A position of the virtual camera is changed on an optical axis that is a z axis in . It is possible to represent an amount of movement d of the virtual camera by a distance from an origin. For example in a case where the virtual camera is positioned at an origin that is a case of an initial state an amount of movement d is 0 .

A range of a predetermined area T in and is represented by an angle of view based on an amount of movement d and a view angle of the virtual camera . An angle of view as illustrated in is an angle of view in a case where the virtual camera is positioned at an origin namely a case of d 0.

In a case where the virtual camera is positioned at an origin namely a case of d 0 an angle of view is identical to a view angle . In a case where the virtual camera is displaced from an origin that is a case where a value of d is increased an angle of view and a view angle exhibit different ranges.

As illustrated in illustrative table the smartphone determines which of a view angle and an amount of movement d of the virtual camera is preferentially changed based on a zoom specification value ZP.

 OUTPUT MAGNIFICATION is an output magnification of an image calculated based on an image parameter determined by another zoom process.

 ZOOM SPECIFICATION VALUE ZP is a value that corresponds to an angle of view to be output. Another zoom process changes a process for determining an amount of movement d and a view angle based on a zoom specification value ZP. For a process to be executed in another zoom process one of four methods is determined based on a zoom specification value ZP as illustrated in illustrative table . A range of a zoom specification value ZP is divided into four ranges that are a range of A B a range of B C a range of C D and a range of D E.

 ANGLE OF VIEW is an angle of view a that corresponds to an image parameter determined by another zoom process.

 CHANGING PARAMETER is a description that illustrates a parameter that is changed by each of four methods based on a zoom specification value ZP. REMARKS are remarks for CHANGING PARAMETER .

 viewWH in illustrative table is a value that represents a width or a height of an output area. In a case where an output area is laterally long viewWH is a value of a width. In a case where an output area is longitudinally long viewWH is a value of a height. That is viewWH is a value that represents a size of an output area in longitudinal direction.

 imgWH in illustrative table is a value that represents a width or a height of an output image. In a case where an output area is laterally long imgWH is a value of a width of an output image. In a case where an output area is longitudinally long imgWH is a value of a height of an output image. That is imgWH is a value that represents a size of an output image in longitudinal direction.

 imageDeg in illustrative table is a value that represents an angle of a display range of an output image. In a case where a width of an output image is represented imageDeg is 360 . In a case where a height of an output image is represented imageDeg is 180 .

A case of a so called zoom out in and will be described as an example below. Here a left figure in each figure of and illustrates one example of an image to be output. A right figure in each figure of and is a diagram that illustrates one example of a state of the virtual camera at a time of an output in a model diagram illustrated in .

In a case of A B or B C an angle of view is identical to a zoom specification value ZP. In a case of A B or B C a value of an angle of view is increased.

A maximum display distance dmax is a distance where a sphere CS is displayed so as to be maximum in an output area of the smartphone . An output area is for example a size of a screen where the smartphone outputs an image or the like or the like. A maximum display distance dmax is for example a case of . A maximum display distance dmax is calculated in accordance with Formula 6 described below 

 viewW in Formula 6 described above is a value that represents a width of an output area of the smartphone . viewH in Formula 6 described above is a value that represents a height of an output area of the smartphone . A similar matter will be described below.

A maximum display distance dmax is calculated based on values of viewW and viewH that are output areas of the smartphone .

A limit display distance dmax is calculated based on values of viewW and viewH that are output areas of the smartphone . A limit display distance dmax represents a maximum range that is able to be output by the smartphone that is a limit value of an amount of movement d of the virtual camera . An embodiment may be limited in such a manner that a zoom specification value ZP is included in a range illustrated in illustrative table in that is a value of an amount of movement d of the virtual camera is less than or equal to a limit display distance dmax. Due to such limitation the smartphone is provided on a condition that an output image is fitted to a screen that is an output area or a condition that an image with a predetermined output magnification is output to a user so that it is possible to realize zoom out.

Due to a process for D E it is possible for the smartphone to cause a user to recognize that an output image is all celestial sphere panorama.

Here in a case of C D or D E an angle of view is not identical to a zoom specification value ZP. Furthermore as illustrated in illustrative table in and and an angle of view is continuous in each range but such an angle of view is not uniformly increased by zoom out toward a wide angle side. That is in a case of C D where an amount of movement d of the virtual camera is changed an angle of view is increased with such an amount of movement d of the virtual camera . In a case of D E where an amount of movement d of the virtual camera is changed an angle of view is decreased with such an amount of movement d of the virtual camera . A decrease in an amount of movement d of the virtual camera in D E is caused by reflecting an outer area of a sphere CS. In a case where a wide field of view greater than or equal to 240 is specified by a zoom specification value ZP the smartphone changes an amount of movement d of the virtual camera and thereby it is possible to output an image with a less feeling of strangeness to a user and change an angle of view .

In a case where a zoom specification value ZP is changed toward a wide angle direction an angle of view is frequently increased. In a case where an angle of view is increased the smartphone fixes a view angle of the virtual camera and increases an amount of movement d of the virtual camera . The smartphone fixes a view angle of the virtual camera and thereby it is possible to reduce an increase in such a view angle of the virtual camera . The smartphone reduces an increase in a view angle of the virtual camera and thereby it is possible to output an image with less distortion to a user. In a case where a view angle of the virtual camera is fixed the smartphone increases an amount of movement d of the virtual camera that is moves the virtual camera to be distant and thereby it is possible to provide a user with an open feeling of a wide angle display. Furthermore movement for moving the virtual camera to be distant is similar to movement at a time when a human being confirms a wide range and hence it is possible for the smartphone to realize zoom out with a less feeling of strangeness due to movement for moving the virtual camera to be distant.

In a case of D E an angle of view is decreased with changing a zoom specification value ZP toward a wide angle direction. In a case of D E the smartphone decreases an angle of view and thereby it is possible to provide a user with a feeling of being distant from a sphere CS. The smartphone provides a user with a feeling of being distant from a sphere CS and thereby it is possible to output an image with a less feeling of strangeness to a user.

Hence it is possible for the smartphone to output an image with a less feeling of strangeness to a user due to another zoom process illustrated in illustrative table in .

Here an embodiment is not limited to a case where only an amount of movement d or a view angle of the virtual camera illustrated in illustrative table in is changed. It is sufficient for an embodiment to be a mode for preferentially changing an amount of movement d or a view angle of the virtual camera on a condition illustrated in illustrative table in and a fixed value may be changed to a sufficiently small value for example for adjustment.

Here a case where an area to be output is edited is not limited to a case where an operation is executed for a changing area. The smartphone may edit an area to be output for example in a case where an operation is executed for an editing area.

Editing to be executed for a predetermined area based on an editing image is blur editing that blurs a predetermined pixel. Herein for another editing it is possible to provide erasing of a specified range of an image changing of a color tone or a color depth of an image or the like a color change of a specified range of an image or the like.

A case where a user executes blur editing for the output image after editing of an area to be output in and will be described as an example below.

In a case where a user executes an operation that pushes a blur editing button the smartphone causes a user to input a so called tap operation for an area where an editing area for the output image after editing of an area to be output in and is displayed.

The smartphone executes a process for blurring a predetermined range centered at a point tapped by a user.

The output image after blur editing is produced by applying blur editing to an output image after editing of an area to be output in and . Blur editing is realized by for example a Gauss function an average of peripheral pixels a low pass filter or the like. Blur editing is illustrated like for example a blur editing area .

Editing that is applied to a predetermined area based on an editing area is editing that cancels blur editing for a blur editing area blurred by such blur editing.

In a case where a user executes an operation that pushes the cancellation editing button the smartphone outputs an output image for cancellation editing that displays a filling area on the blur editing area with applied blur editing. As illustrated in the output image for cancellation editing is an image that displays the filling area on the blur editing area in the editing area after blur editing in . A user executes a tap operation for a displayed filling area that is an area with applied blurring. The smartphone executes a process for cancelling blur editing in a predetermined range centered at a point tapped by a user. That is in editing for cancelling blur editing the smartphone provides a predetermined range centered at a point tapped by a user in the editing image after blur editing on a state of the output image after editing of an area to be output in and .

Once a taken image of a face of a person or a photography prohibited building is released or shared on the internet trouble may be caused. In particular in a case where a panoramic image with a broad range is taken an image of many objects in a broad range may frequently be taken. Therefore it is possible for a user to reduce trouble due to a process for blurring an object that is possibly problematic at a time of release or sharing. It is possible for the smartphone to facilitate an operation for blurring a face of a person taken in an image due to editing to be applied to a predetermined area based on an editing area. Hence it is possible for the smartphone to cause a user to readily execute an image operation due to editing to be applied to a predetermined area based on an editing area.

Here in a case where editing of an area to be output is executed the smartphone may change a range of editing applied to a predetermined area based on an editing area or the like in accordance with a magnification.

At step S the smartphone calculates amounts of movement of coordinates to be output. That is at step S the smartphone calculates a position of a predetermined area T in and that corresponds to a swipe operation of a user based on for example Formula 2 described above.

At step S the smartphone updates a position of a predetermined area T in FIG. B and at a position calculated at step S.

At step S the smartphone calculates coordinates of a point that is an editing object. That is at step S the smartphone calculates coordinates that correspond to a tap operation of a user and executes calculation for projection onto three dimensional coordinates.

At step S the smartphone calculates a predetermined area that is edited centered at coordinates calculated at step S and based on an editing area. That is at step S the smartphone calculates a pixel that is a point specified by a tap operation of a user or a periphery of such a point and is an object for blur editing or the like.

At step S the smartphone produces an editing area. In a case where a user executes an operation for a changing area at step S the smartphone produces a changing area based on a predetermined area T updated at step S. In a case where a user executes an operation for an editing area at step S the smartphone produces an editing area wherein a blurring process is reflected on a pixel calculated at step S.

At step S the smartphone produces a changing area. In a case where a user executes an operation for a changing area at step S the smartphone produces a changing area based on a predetermined area T updated at step S. In a case where a user executes an operation for an editing area at step S the smartphone produces an changing area that indicates a location that is a blurring object at step S.

At step S the smartphone executes a process for acquiring an image from the image taking device in or the like. A process at step S corresponds to a process at step S in .

At step S the smartphone executes a process for producing a panoramic image. A process at step S is executed based on an image acquired at step S. A process at step S corresponds to a process at step S in .

At step S the smartphone executes a process for causing a user to select an image to be output. A process at step S corresponds to a process at step S in . Specifically a process for causing a user to select an image to be output is a process for outputting a thumbnail image or providing a UI for causing a user to execute an operation for a thumbnail image or the like.

At step S the smartphone executes a process for producing an initial image. A process at step S corresponds to a process at step S in . At step S the smartphone produces and outputs an image selected by a user at step S as an initial image.

At step S the smartphone executes determination as to whether or not switching to a mode for editing an image is executed. A process at step S executes determination based on whether or not an operation of a user at step S in is provided. In a case where determination is provided at step S in such a manner that switching to a mode for editing an image is provided YES at step S the smartphone goes to step S. In a case where determination is provided at step S in such a manner that switching to a mode for editing an image is not provided NO at step S the smartphone returns to step S.

A case where determination is provided at step S in such a manner that switching to a mode for editing an image is provided is a case where an input to start editing of an image is provided by a user. A case where determination is provided at step S in such a manner that switching to a mode for editing an image is not provided is a case where a user does not execute an operation. Therefore in a case where a user does not execute an operation the smartphone continues to output an initial image and waits for an input of an user to start editing of an image.

At step S the smartphone executes a process for outputting an output image for editing an image. A process at step S corresponds to a process at step S in . Furthermore the smartphone outputs an output image and thereby accepts an operation of a user at step S in .

At step S the smartphone executes determination as to whether an operation of a user is executed for an editing area or a changing area. A process at step S corresponds to a process at step S in . The smartphone executes determination as to whether an operation of a user at step S in is executed for an editing area or a changing area.

In a case where determination is provided in such a manner that an operation of a user is executed for a changing area a changing area at step S the smartphone goes to step S. In a case where determination is provided in such a manner that an operation of a user is executed for an editing area an editing area at step S the smartphone goes to step S.

At step S the smartphone executes a process for calculating an amount of movement of a predetermined area due to an operation. A process at step S corresponds to a process at step S in . At step S the smartphone calculates an amount of movement for moving a predetermined area based on a swipe operation that is executed by a user and changes such a predetermined area.

At step S the smartphone executes a process for updating a predetermined area. A process at step S corresponds to a process at step S in . At step S the smartphone moves a predetermined area T in and to a position that corresponds to an amount of movement calculated at step S and updates such a predetermined area T from a position of an initial image to a position that corresponds to a swipe operation of a user.

At step S the smartphone executes a process for calculating and three dimensionally projecting coordinates that are objects for an operation. A process at step S corresponds to a process at step S in . At step S the smartphone calculates coordinates on an all celestial sphere image that corresponds to a point specified by a tap operation of a user.

At step S the smartphone executes a process for calculating a pixel that is an object for blurring. For example the smartphone has an editing state table that causes flag data as to whether or not an object for blurring is provided to correspond to each pixel. An editing state table represents whether or not each pixel is output in a blur state. The smartphone refers to an editing state table determines whether or not each pixel in an output image is output in a blur state and outputs an image. That is a process at step S is a process for updating an editing state table. In a case where an operation for either blurring as illustrated in or cancellation as illustrated in is provided in a tap operation of a user the smartphone updates an editing state table based on such an operation.

At step S the smartphone executes a process for producing an editing image. A process at step S corresponds to a process at step S in .

At step S the smartphone executes a process for producing a changing area. A process at step S corresponds to a process at step S in .

Due to processes at step S and step S the smartphone produces an output image and executes an output to a user.

In a case where an object for blurring is provided based on an editing state table at processes at step S and step S the smartphone executes for example a blurring process as illustrated in and an output.

An image that is output to a user by the smartphone is output at 30 or more frames per 1 second in such a manner that such a user feels smooth reproduction of an animation. It is desirable for the smartphone to execute an output at 60 or more frames per 1 second in such a manner that a user feels particularly smooth reproduction. Here a frame rate of an output may be such that 60 frames per 1 second is changed to for example 59.94 frames per 1 second.

Here processes at step S and step S are not limited to processes for causing the smartphone to execute a blurring process and an output.

For example the smartphone has an image provided by preliminarily applying a blurring process to all of pixels of an image to be output and an image provided by applying no blurring process. The smartphone outputs each pixel by simultaneously selecting an image provided by executing a blurring process based on an editing state table or an image provided by executing no blurring process. It is possible for the smartphone to reduce an amount of calculation for outputting an image by preliminarily executing a blurring process. That is it is possible for the smartphone to realize a high speed image output such as 60 frames per 1 second by executing selection and a simultaneous output of each pixel.

Furthermore for example in a case where each pixel is selected and simultaneously output the smartphone may store an output image. In a case where a user does not execute an editing operation the smartphone outputs a stored image. Due to storage a process for selecting and producing each pixel of an image to be output is not required and hence it is possible for the smartphone to reduce an amount of calculation. Therefore the smartphone stores an output image and thereby it is possible to realize a high speed image output such as 60 frames per 1 second.

Here an output image is not limited to an image illustrated in or the like. For example a shape a position a size or a range of an editing area or a changing area may be changed.

For example the smartphone causes a user to push the separation line for a longer period of time or input a so called long tap operation . In a case of pushing for a longer period of time or a long tap is an operation of a user that continues to push a screen at a position with an output separation line by a finger thereof for a predetermined or more period of time.

In a case where a long tap operation is input the smartphone executes a process for changing a position a size or a range of the separation line .

A pre changing separation line A illustrates a position of a separation line before changing. That us the pre changing separation line A is provided in a state of .

A post changing separation line B illustrates a position of a separation line after changing. As illustrated in the smartphone changes a separation line depending on movement of a finger of a user that traces a screen. The smartphone changes and outputs a position a size or a range of an editing area or a changing area to be output depending on changing in a separation line.

Changing in a separation between areas is executed and thereby it is possible for a user to provide a position a size or a range of an editing area or a changing area so as to facilitate an operation. Changing in a separation between areas is executed and thereby it is possible for the smartphone to output an output image in such a manner that an operation of a screen is facilitated for a user.

The image taking system has the image taking device and the smartphone . The image taking system has a first image taking part F a second image taking part F and an all celestial sphere image production part F. The image taking system has an image acquisition part F a production part F an input output part F a storage part F and a control part F.

The first image talking part F and the second image taking part F take and produce images that are materials of an all celestial sphere image. The first image taking part F is realized by for example the front side image taking element H in and or the like. The second image taking part F is realized by for example the back side image taking element H in and or the like. An image that is a material of an all celestial sphere image is for example a hemispherical image as illustrated in or .

The all celestial sphere image production part F produces an image that is output to the smartphone such as an all celestial sphere image. The all celestial sphere image production part F is realized by for example the image processing unit H in or the like. The all celestial sphere image production part F produces an all celestial sphere image from hemispherical images that are taken by the first image taking part F and the second image taking part F.

The image acquisition part F acquires image data such as an all celestial sphere image from the image taking device . The image acquisition part F is realized by for example the network I F H in or the like. The image acquisition part F executes a process for causing the smartphone to acquire image data such as an all celestial sphere image.

The production part F executes a process for producing each kind of image and a line and each kind of calculation necessary for production of an image. The production part F has a changing area production part F an editing area production part F and a separation line production part F. The production part F is realized by the CPU H in or the like.

The changing area production part F executes a process for executing production of a changing area. The changing area production part F acquires for example image data and an editing state table from the storage part F. The changing area production part F produces a changing area based on an acquired editing state table and image data.

The editing area production part F executes a process for executing production of an editing area. The editing area production part F acquires for example image data and an editing state table from the storage part F. The editing area production part F produces an editing area based on an acquired editing state table and image data.

Furthermore in a case where an operation as illustrated in and is provided the changing area production part F and the editing area production part F change a position a size a range or the like of each area to be output and produces an image to be output in each area.

The separation line production part F produces a separation line such as the separation line in . For example in a case where an operation as illustrated in and is provided the separation line production part F executes a process necessary for changing an output of a separation line.

The production part F calculates and stores as an editing state table coordinates associated with an operation in a case where a user executes a tap or swipe operation. Furthermore an image produced by the production part F may be stored in the storage part F and taken according to a process.

The input output part F executes a process for inputting an operation of a user. The input output part F causes a user to execute a process for outputting an image produced by the production part F. The input output part F is realized by for example the input output device H in or the like.

The storage part F stores each kind of information acquired or produced by the smartphone . The storage part F has for example an editing state table storage part F and an image storage part F. The storage part F is realized by for example the auxiliary storage device H or the main storage device H in or the like.

The editing state table storage part F stores data of a table that represents a pixel where a blurring process is executed.

The image storage part F stores an all celestial sphere image acquired by the image acquisition part F an output image produced by the production part F and the like.

The control part F controls each kind of a component that is provided in the smartphone . The control part F controls each kind of component and thereby realizes each kind of process a process for assisting each kind of process and the like. The control part F is realized by for example the CPU H in or the like.

Here an entire process is not limited to a case as illustrated in . For example a part or an entirety of each process may be processed by a device other than a device as illustrated in .

Here an embodiment is not limited to an output with a separation between an editing area and a changing area by a separation line. For example an embodiment may be an embodiment provided in such a manner that the smartphone blurs decorates for example colors with a predetermined color and outputs a changing area thereby causing a user to perceive different areas and separates between and outputs an editing area and such a changing area.

The smartphone produces an editing area and a changing area based on an all celestial sphere image acquired from the image taking device or the like. An editing area is an area for outputting a predetermined area that is determined by a predetermined area T and causes a user to execute an editing operation such as blurring or cancellation of blurring. A changing area is an area for outputting an image for causing a user to execute an operation for changing a position a size or a range of a predetermined area T or the like. The smartphone outputs an output image that has at least an editing area and a changing area. An output image has an editing area and a changing area and thereby it is possible for the smartphone to cause a user to execute editing such as blurring and simultaneously change an area output in such an editing area by such a changing area. Therefore in a case where a user executes a blurring operation for an all celestial sphere image or the like it is possible for the smartphone to output an image for facilitating an operation. Hence the smartphone outputs an output image that has an editing area and a changing area and thereby it is possible for a user to readily execute an operation of an image.

Here the smartphone may be realized by a computer executable program described in a legacy programming language such as Assembler C C C or Java Java is a registered trademark an object oriented programming language or the like. It is possible for a program to be stored in and distributed by a recording medium such as a ROM or an Electrically Erasable Programmable ROM EEPROM . It is possible for a program to be stored in and distributed by a recording medium such as an Erasable Programmable ROM EPROM . It is possible for a program to be stored in and distributed by a recording medium such as a flash memory a flexible disk a CD ROM a CD RW a DVD ROM a DVD RAM a DVD RW or the like. It is possible for a program to be stored in a device readable recording medium such as a Blu Ray disk Blu Ray disk is a registered trademark SD SD is a registered trademark card or an MO or distributed through a telecommunication line.

Here an image in an embodiment is not limited to a still image. For example an image may be an animation.

Furthermore a part or an entirety of each process in an embodiment may be realized by for example a programmable device PD such as a field programmable gate array FPGA . Moreover a part or an entirety of each process in an embodiment may be realized by an Application Specific Integrated Circuit ASIC .

Although preferable practical examples of the present invention have been described in detail above the present invention is not limited to such particular embodiments and a variety of alterations and modifications are possible within a scope of an essence of the present invention as recited in what is claimed.

At least one illustrative embodiment of the present invention may relate to an information processing method an information processing device and a program.

At least one illustrative embodiment of the present invention may aim at facilitating execution of an image operation for a user.

According to at least one illustrative embodiment of the present invention there may be provided an information processing method that causes a computer to process an image characterized by causing the computer to execute an acquisition step for acquiring the image and an output step for outputting an output image by separating between an editing area for editing a predetermined area of the image and a changing area for changing the predetermined area to be output.

Illustrative embodiment 1 is an information processing method for causing a computer to process an image wherein the image processing method causes the computer to execute an acquisition step for acquiring the image and an output step for outputting an output image by separating between an editing area for editing a predetermined area of the image and a changing area for changing the predetermined area to be output.

Illustrative embodiment 2 is the information processing method as described in illustrative embodiment 1 wherein an editing position input step for acquiring an editing position that is a target area of the editing by using the editing area and an editing step for editing the editing position are executed.

Illustrative embodiment 3 is the image processing method as described in illustrative embodiment 2 wherein the editing step is a step for blurring the editing position.

Illustrative embodiment 4 is the information processing method as described in illustrative embodiment 3 wherein an acquisition image that has just been acquired in the acquisition step and a blurred image produced by a blurring process are produced and the output image is output by selecting a pixel of the blurred image for the editing area and a pixel of the acquisition image for that other than the editing area.

Illustrative embodiment 5 is the information processing method as described in illustrative embodiment 3 or 4 wherein a specified position input step for acquiring a specifying position for specifying an area of a part or an entirety of an image output with the editing area and a cancellation step for canceling the blurring process executed for the specifying position are executed.

Illustrative embodiment 6 is the information processing method as described in any one of illustrative embodiments 1 to 5 wherein an operation input step for acquiring an operation for changing enlarging or reducing the predetermined area that is output with the editing area by using the changing area is executed.

Illustrative embodiment 7 is the information processing method as described in illustrative embodiment 6 wherein a determination step for determining a view point position and a view angle is executed based on the operation and the determination changes one of the view point position and the view angle based on an area indicated by the operation.

Illustrative embodiment 8 is the information processing method as described in any one of illustrative embodiments 1 to 7 wherein a changing step for changing a position a size or a range of the editing area or the changing area to be output based on an operation for changing a separation between the editing area and the changing area is executed.

Illustrative embodiment 9 is an information processing device that processes an image wherein the image processing device has an acquisition means for acquiring the image and an output means for outputting an output image by separating between an editing area for editing a predetermined area of the image and a changing area for changing the predetermined area to be output.

Illustrative embodiment 10 is a program for causing a computer to process an image wherein the program causes the computer to execute an acquisition step for acquiring the image and an output step for outputting an output image by separating between an editing area for editing a predetermined area of the image and a changing area for changing the predetermined area to be output.

According to at least an illustrative embodiment of the present invention it may be possible to facilitate execution of an image operation for a user.

Although the illustrative embodiment s and specific example s of the present invention have been described with reference to the accompanying drawings the present invention is not limited to any of the illustrative embodiment s and specific example s and the illustrative embodiment s and specific example s may be altered modified or combined without departing from the scope of the present invention.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the principles of the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority or inferiority of the invention. Although an information processing method has been described in detail it should be understood that various changes substitutions and alterations could be made thereto without departing from the spirit and scope of the invention.


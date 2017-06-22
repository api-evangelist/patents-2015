---

title: Virtual machine control method, apparatus, and medium
abstract: A method includes monitoring a load of a management target system on which a plurality of virtual machines are executed, cancelling an instruction to activate a virtual machine according to the monitored load and a status of the virtual machine for which the instruction to activate the virtual machine is previously given to the system and which is still under the activation process; and issuing an instruction to the system to stop the virtual machine which is still under an activation process according to the monitored load and the status of the virtual machine.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09594585&OS=09594585&RS=09594585
owner: FUJITSU LIMITED
number: 09594585
owner_city: Kawasaki
owner_country: JP
publication_date: 20150304
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2014 073233 filed on Mar. 31 2014 the entire contents of which are incorporated herein by reference.

In recent years cloud services in which computer processing or the like are used via networks using the Internet have been provided.

In cloud environments in which cloud services are provided a plurality of servers are prepared in large sized data centers and systems are constructed so that virtual machines software data storage areas and the like are available via networks.

Such systems can have an autoscale function of increasing and decreasing virtual machines. The autoscale function is a function of performing scale out to add a server to a system and performing scale in to remove a server from the system according to a processing amount of the system. By performing scale control called the scale out and scale in server resources are set according to a service request.

Japanese Laid open Patent Publication Nos. 2008 015958 and 2005 141605 are examples of the related art.

According to an aspect of the invention a method includes monitoring a load of a management target system on which a plurality of virtual machines are executed cancelling an instruction to activate a virtual machine according to the monitored load and a status of the virtual machine for which the instruction to activate the virtual machine is previously given to the system and which is still under the activation process and issuing an instruction to the system to stop the virtual machine which is still under an activation process according to the monitored load and the status of the virtual machine.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

First an examination of the inventors will be described. In cloud environments users are charged according to an amount of resources that have been used. Therefore changes in allocation amounts of resources are not typically performed until a situation in which resources are actually used.

On the other hand there are cases in which proper allocation of resources is desired in response to prediction of future values e.g. a steep increase in the number of accesses. However when the resources are actually allocated charging occurs in spite of the fact that the resources are not used in actual processes.

There is a desire to respond to an increase or decrease in the amount of a request by changing the allocation of the resources according to a sign indicating a change in the request for services. However when it takes a time to activate a calculator requested for the allocation of the resources it takes a certain time until the instruction to activate or stop the calculator for the purpose of changing the allocation of resources which is performed in the past is carried out as a resource of a service. Further it is difficult to perform an immediate response for the purpose of relating to charging.

In an embodiment to be described below it is possible to shorten a period in which virtual machines are deficient or excessive. Hereinafter an embodiment will be described with reference to the drawings.

In the embodiment there is provided an information processing apparatus managing the number of virtual machines in an information processing system performing a service using the virtual machine. The information processing apparatus monitors a load of a management target system and gives an instruction to stop a virtual machine which is under an activation process according to a load monitoring result and a status of the virtual machine for which the instruction to activate the virtual machine is previously given to the system and which is under the activation process.

The information processing apparatus performs scale out or scale in of a virtual machine according to a change in a load per unit time. At the time of the scale in a virtual machine to be stopped is selected based on an activation start time. Thus it is possible to shorten a period in which the virtual machines are deficient or excessive.

The monitoring unit monitors a load of an information processing system. The load is determined based on for example a response time or a usage rate of a central processing unit CPU . The response time is a time which is taken until return of a response when a client makes a service request to the system. When the response time is lengthened it means that the load is increased. When the response time is shortened it means that the load is decreased. Hereinafter the load is assumed to be monitored using the response time. In this case the monitoring unit recognizes the response time until a virtual machine receives a service request and then transmits its response.

When a change amount of the load per unit time exceeds a threshold value the control unit gives a scale out instruction to newly activate a virtual machine or a scale in instruction to stop a virtual machine selected based on an activation start time among existing virtual machines. For example the control unit compares the change amount of the response time to the threshold value. When the change amount of the response time exceeds the threshold value the control unit performs scale out to increase the number of virtual machines or performs scale in to decrease the number of virtual machines. The control unit also manages an operation state of the virtual machine. The storage unit stores information regarding the scale control.

The control unit detects the change amount of the response time. In this case when an increasing change amount of the response time is recognized to exceed a first threshold value at a time t the control unit performs the scale out and increases the number of running virtual machines from N to N for example.

When a decreasing change amount of the response time is recognized to exceed a second threshold value at a time t the control unit performs the scale in and decreases the number of running virtual machines from N to N for example.

Here in autoscale of the related art the scale out is performed when the response time reaches an upper limit. The scale in is performed when the response time reaches a lower limit. Therefore for a period of time taken to complete the activation of the virtual machines or to complete the stop of the virtual machines a deficient state or an excessive state of the virtual machines occurs.

In contrast the information processing apparatus performs the scale out and the scale in according to an increase rate or a decrease rate of the response time. Thus the scale out is performed in an earlier stage before the response time reaches the upper limit and an activation instruction can be given to a scale out target virtual machine. Therefore it is possible to suppress the deficient state of the virtual machines. Alternatively it is possible to shorten a period of time in which the virtual machines are deficient.

The scale in is performed in an earlier stage before the response time reaches the lower limit and a stopping instruction can be given to a scale in target virtual machine. Therefore it is possible to suppress the excessive state of the virtual machines. Alternatively it is possible to shorten a period of time in which the virtual machines are excessive. The details of the operations will be described after .

Next problems to be solved will be described in detail before detailed description of the present technology. First ideal scale control will be described. Hereinafter a virtual machine is referred to as an instance.

A graph g thin solid line indicates the number of instances and indicates the number of running instances. A graph g thick solid line indicates the average response time. A diagonal line portion area of a region surrounded by the graph g and the horizontal axis indicates a cost which increases or decreases according to the number of instances.

In the average response time an allowable range H is set. The allowable range H has a lower limit L which is a lower limit time and an upper limit U which is an upper limit time. The scale control is performed such that the average response time falls from the lower limit L to the upper limit U. Hereinafter an operation at a time t will be described.

 t ta The number of running instances is equal to N. The average response time reaches the upper limit U of the allowable range H. For the number of instances in the current state the processing performance is deficient. Therefore the scale out is performed and the number of instances increases from N to N.

 t tb The number of running instances is equal to N. The average response time reaches the lower limit L of the allowable range H. For the number of instances in the current state the processing performance is excessive. Therefore the scale in is performed and the number of instances decreases from N to N.

Here when the number of instances is small the cost is lowered. However there is a probability of the average response time exceeding the upper limit. In contrast when the number of instances is larger the average response time is shortened. However the cost is raised and there is a probability of the average response time exceeding the lower limit.

As illustrated in described above the scale control of changing the number of instances is performed by performing the scale out in so that the average response time satisfies the allowable range H. Thus necessary and sufficient resources to satisfy a service request can be used at an appropriate cost.

However the foregoing scale control is performed in an ideal scale control state when a time taken to activate and stop the instances is not considered.

That is in order to activate a scale out target instance it takes a processing time to activate the instance. Further in order to stop a scale in target instance it takes a processing time to stop the instance. However in the scale control of such times are not considered.

In actual scale control an instance activation processing time has influence on the scale out and an instance stop processing time has influence on the scale in.

Next problems of the scale control of the related art will be described. is a diagram illustrating transition of the number of instances and an average response time. The horizontal axis represents a system running time the left vertical axis represents an average response time and the right vertical axis represents the number of running instances. A graph g indicates the number of instances and a graph g indicates the average response time.

An area surrounded by the graph g and the horizontal axis indicates a cost as in . However diagonal lines are not illustrated in the following description to simplify the drawing. Hereinafter an operation at a time t of the scale control of the related art will be described.

 t t The number of running instances is equal to N. The average response time reaches the upper limit U. At this time since the scale out is performed an instance increased through the scale out starts an activation process.

 t t The number of running instances is equal to N. The activation of the scale out target instance is completed the number of instances is changed from N to N and the scale out is thus completed. The increase in the average response time is stopped.

 t t The number of running instances is equal to N. The average response time reaches the lower limit L. At this time since the scale in is performed a stopping process for the instance to be decreased through the scale in starts.

 t t The number of running instances is equal to N. The stopping process for the instance is completed the number of instances is changed from N to N and the scale in is thus completed. The decrease in the average response time is stopped.

Thus in the scale control of the related art the scale out is performed when the average response time reaches the upper limit U. The scale in is performed when the average response time reaches the lower limit L.

However when the average response time reaches the upper limit U the activation of the scale out target instance is not completed at the time at which the scale out is performed in spite of the fact that the scale out is performed. It takes a given activation processing time until the activation is completed.

Therefore since the instance resources are deficient for a service request in the period of time to from the start of the activation to the completion of the activation a state in which a processing load is high continues and thus the processing performance may deteriorate.

Further when the average response time reaches the lower limit L the stop of the scale in target instance is not completed at the time in which the scale in is performed in spite of the fact that the scale in is performed. It takes a given stop processing time until the stop is completed.

Therefore even when the service request is satisfied in the period of time tB from the start of the stop to the completion of the stop the instance resources are excessive. Therefore an unnecessary cost occurs.

Thus in the related art the upper lower limit of the average response time is provided the average response time is compared to the upper lower limit and the scale out in is performed. Therefore the deficient state of the resources continues and the processing performance may deteriorate or the excessive state of the resources continues and an unnecessary cost may occur.

The present technology is devised in view of the above mentioned circumstances and is designed to realize efficient scale control so that the deficient excessive state of the instance resources is suppressed and a cost is suppressed while a service request is satisfied.

Next the scale control according to the present technology will be described in detail below. is a diagram illustrating transition of the number of instances and the average response time. The horizontal axis represents a system running time the left vertical axis represents an average response time and the right vertical axis represents the number of running instances. A graph g indicates the number of instances and a graph g indicates the average response time.

The instance ID is an identification number of an instance. The state indicates an operation state of an instance. The state transition time indicates a time which may include a year a month and a date when an operation state of an instance transitions. illustrates the instance information at each time of the horizontal axis of . Hereinafter an operation at each time of will be described.

 time 12 00 The number of running instances is 1 and an instance I1 with the instance ID I1. is running. The activation of the instance I1 is assumed to be completed at time 11 00 00 and the instance I1 is assumed to be currently running.

In this case as a table generation process the control unit generates an instance information table Ta 12 00 in which the instance ID I1 a state running state and a state transition time 11 00 00 are registered.

 time 12 10 The number of running instances is 1 and the instance I1 is running. It is assumed that the average response time increases and the increasing change amount a slope of the increase degree exceeds a first threshold value referred to as a threshold value th .

At this time since the control unit performs the scale out the control unit activates the instance to be increased through the scale out. It is assumed that an ID I2 of the activated instance is set and an activation starting instruction time is 12 10 00.

As a table generation process the control unit generates the instance information table Ta 12 10 in which a record including the instance ID I2 a state under the activation process and a state transition time 12 10 00 is registered.

 time 12 20 The number of running instances is 2 and the instances I1 and I2 are running. The activation of the instance I2 is completed at a time 12 20 00 and the instance I2 is running.

As a table generation process the control unit generates the instance information table Ta 12 20 in which the state of the record of the instance ID I2 is changed to a running state and the state transition time is changed to 12 20 00.

 time 12 30 The number of instances running is 2 and the instances I1 and I2 are running. It is assumed that the average response time decreases and the decreasing change amount a slope of the decrease degree exceeds a second threshold value referred to as a threshold value th .

At this time the control unit performs the scale in an instance to be decreased through the scale in is stopped. An ID I2 of the stopped instance is assumed to be set and a stop starting instruction time is assumed to be 12 30 00.

As a table generation process the control unit generates the instance information table Ta 12 30 in which the state of the record of the instance ID I2 is changed to a state under the stopping process and the state transition time is changed to 12 30 00.

 time 12 40 The number of instances running is 1 the instance I1 is running and the running of the instance I2 is stopped.

When the control unit recognizes that the stop of the instance I2 is completed the control unit generates the instance information table Ta 12 40 from which the record of the instance ID I2 is deleted as a table generation process.

As described above in the scale control according to the present technology the scale out is performed when the increasing change amount of the average response time exceeds the threshold value th of the increasing change amount. Thus it is possible to forecast a time taken from the start of the activation to the completion of the activation of the instance and give an activation starting instruction to the scale out target instance.

Therefore even before the average response time exceeds the upper limit or even when the average response time exceeds the upper limit it is possible to perform the scale out while minimizing a period of time at which the average response time exceeds the upper limit. Accordingly it is possible to reduce a period of time in which the instance resources are deficient and suppress deterioration in the processing performance.

In the scale control according to the present technology the scale in is performed when the decreasing change amount of the average response time is less than the threshold value th. Thus it is possible to forecast a time taken from the start of the stop and the completion of the stop of the instance and give a stop starting instruction to the scale in target instance.

Therefore even before the average response time is less than the lower limit or even when the average response time is less than the lower limit it is possible to perform the scale in while minimizing a period of time in which the average response time is less than the lower limit. Accordingly it is possible to reduce a period of time in which the instance resources are excessive and suppress unnecessary occurrence of a cost.

When the scale out in is performed a number of instances calculation process of calculating how many instances are increased or decreased will be described with reference to .

Here in the present technology as described above the activation process for the scale out target instance starts when it is recognized that the increasing change amount of the average response time exceeds the threshold value th.

At this time after the activation process for the instance starts for example the increase in the change amount of the average response time is lessened for a short time and thus there is a probability of the resources of the instances starting to be activated being excessive.

Even in this case in the present technology when the decreasing change amount of the average response time exceeds a predetermined value the stopping process for the instance is performed and thus the excessive state of the resources is dissolved quickly.

 time 12 00 The number of running instances is 1 and the instance with the instance ID I1 is running. The activation of the instance I1 is assumed to be completed at time 11 00 00 and the instance I1 is assumed to be currently running.

As a table generation process the control unit generates an instance information table Ta 12 00 in which the instance ID I1. a state running state and a state transition time 11 00 00 are registered.

 time 12 10 The number of instances running is 1 and the instance I1 is running. It is assumed that the average response time increases and the increasing change amount exceeds the threshold value th. At this time since the control unit performs the scale out the control unit activates the instance to be increased through the scale out. It is assumed that the ID I2 of the activated instance is set and an activation starting instruction time is 12 10 00.

As a table generation process the control unit generates the instance information table Ta 12 10 in which a record including the instance ID I2 the state under the activation process and a state transition time 12 10 00 is registered.

 time 12 14 The number of running instances is 1 and the instance I1 is running. It is assumed that the control unit gives an instruction to activate the instance I2 to perform the scale out but the slope of the increase in the average response time is recognized to decrease before completion of the activation of the instance I2.

That is it is assumed that the decreasing change amount of the average response time exceeds the threshold value th before the completion of the activation of the instance I2.

In this case the control unit gives a stopping instruction to the instance I2 to which the activation instruction has been given once. The instance I2 receiving the stopping instruction performs the stopping process.

As a table generation process the control unit generates the instance information table Ta 12 14 in which the state of the record of the instance ID I2 is changed to a state under the stopping process and the time is changed to 12 14 00.

 time 12 20 The number of running instances is 1 and the instance I1 is running. It is assumed that the running of the instance I2 is stopped and the control unit recognizes that the stop of the instance I2 is completed at the time 12 20 00.

As a table generation process the control unit generates the instance information table Tat 12 20 from which the record of the instance ID I2 is deleted.

As described above even when the scale out target instance for which the activation process starts is an excessive resource the stopping process for the instance is performed based on the decreasing change amount of the average response time. Therefore it is possible to dissolve the excessive state of the resources quickly.

When the instance of which the activation is already completed is stopped in spite of the fact that the instance under the activation process is present the process performed with the instance may be stopped. Therefore at the time of the stopping process the stopping process is performed from the instance under the activation process.

Next an instance to which a stopping instruction is given among the instance resources will be described with reference to . is a diagram illustrating transition of the number of instances and the average response time. The horizontal axis represents a system running time the left vertical axis represents an average response time and the right vertical axis represents the number of running instances. A graph g indicates the number of instances and a graph g indicates the average response time.

 time 12 00 The number of running instances is 2 and the instance I1 with the instance ID I1 and the instance I2 with the instance ID I2 are running.

The activation of the instance I1 is completed at the time 10 00 00 and the instance I1 is currently running. The activation of the instance I2 is completed at the time 11 00 00 and the instance I2 is currently running.

As a table generation process the control unit generates the instance information table Ta 12 00 which has a record including the instance ID I1 the state running state and the state transition time 10 00 00 and a record including the instance ID I2 the state running state and the state transition time 11 00 00 

 time 12 10 The number of running instances is 2 and the instances I1 and I2 are running. It is assumed that the average response time increases and the increasing change amount exceeds the threshold value th.

At this time since the control unit performs the scale out the control unit activates the instance to be increased through the scale out. It is assumed that an ID I3 of the activated instance is set and an activation starting instruction time is 12 10 00.

As a table generation process the control unit generates the instance information table Ta 12 10 in which a record including the instance ID I3 a state under the activation process and a state transition time 12 10 00 is newly registered.

 time 12 14 The number of running instances is 2 and the instances I1 and I2 are running. At the time 12 14 the increasing change amount is assumed to exceed the threshold value th again.

At this time since the control unit performs the scale out to increase the instance the control unit activates the instance to be increased through the scale out. It is assumed that an ID I4 of the activated instance is set and an activation starting instruction time is 12 14 00.

As a table generation process the control unit generates the instance information table Ta 12 14 in which a record including the instance ID I4 a state under the activation process and a state transition time 12 14 00 is newly registered.

 time 12 20 The number of running instances is 2 and the instances I1 and I2 are running. The instances I3 and I4 are under the activation process.

 time 12 30 The number of instances running is 2 and the instances I1 and I2 are running. The instances I3 and I4 are under the activation process. It is assumed that the average response time decreases and the decreasing change amount exceeds the threshold value th. At this time since the control unit performs the scale in the control unit stops the instance to be decreased through the scale in. The instance to be stopped is set to the instance 14 of which an activation starting time is the latest and the stop starting instruction time is set to 12 30 00.

As a table generation process the control unit generates the instance information table Ta 12 30 in which the state of the record of the instance ID I4 is changed to a state under the stopping process and the state transition time is changed to 12 30 00.

 time 12 40 The number of running instances is 3 and the instances I1 12 and 13 are running. The activation of the instance I3 is assumed to be completed at the time 12 38 00. Further the stop of the instance I4 is assumed to be completed at the time 12 40 00.

As a table generation process the control unit generates the instance information table Ta 12 40 in which the state of the record of the instance ID I3 is changed to a running state and the state transition time is changed to 12 38 00 and from which the record of the instance ID I4 is deleted.

Thus the instance to which the stopping instruction is given is selected in consideration of an influence on a service. When the instance under the activation process is present the instance under the activation process is selected. When the plurality of instances under the activation process are present the instances are stopped in order from the instance of which the activation starting time is later i.e. the recently activated instance.

When the virtual machine under the activation process is not present the instances are stopped in order from the instance of which the running start time is later i.e. the recently running instance. Thus when the instances are stopped occurrence of interruption of the service can be inhibited.

Next a flow of the entire scale control will be described. is a diagram illustrating a flow of the scale control. An information processing system includes clients a load balancer a service supply instance group a response time information acquisition unit a response time information database DB an instance information DB instances A and B and a cloud environment application programming interface API .

The instance A includes a number of instances calculation unit and a scale control unit . The instance B includes an instance information acquisition unit . The number of instances calculation unit the scale control unit and the instance information acquisition unit may be included in one instance.

Here the number of instances calculation unit the scale control unit and the instance information acquisition unit are included in the functions of the control unit in . The response time information acquisition unit is included in the function of the monitoring unit in . The response time information DB and the instance information DB are included in the functions of the storage unit in .

 S The load balancer selects an instance that supplies a corresponding service in response to the service request from the service supply instance group including a plurality of instances. In this case the instance is selected so that a load is not biased to specific instances.

 S The instance selected by the load balancer performs a process by the service request and transmits a response to the client having transmitted the service request.

 S The response time information acquisition unit acquires response time information indicating how much time the instance uses and transmits the response.

 S The response time information acquisition unit stores the response time information in the response time information DB .

 S The instance information acquisition unit acquires instance information regarding the instances under the cloud environment via the cloud environment management API .

 S The number of instances calculation unit calculates the number of instances to be subjected to the scale control based on the response time information and the instance information.

 S The scale control unit performs the scale control based on a calculation result of the number of instances through the cloud environment management API .

Next the scale control will be described with reference to a flowchart. is a flowchart illustrating an operation of the scale control.

 S The scale control unit ends the scale control when the scale control unit does not perform the scale out in. When the scale out is performed the process proceeds to step S. When the scale in is performed the process proceeds to step S.

 S The scale control unit transmits an instruction to activate the scale out target instance to the cloud environment management API .

 S The cloud environment management API receives the instruction to activate the instance. The activation instruction transmitted from the scale control unit is transmitted to the scale out target instance via the cloud environment management API .

 S The scale control unit transmits an instruction to stop the scale in target instance to the cloud environment management API . As described above when the instance under the activation process is present the stopping instruction is given to the instance of which the activation start time is the latest and which is recently activated. When the instance under the activation process is not present the stopping instruction is given to the instance of which the activation start time is the latest and which is recently activated.

 S The cloud environment management API receives the instruction to stop the instance. The stopping instruction transmitted from the scale control unit is transmitted to the scale in target instance via the cloud environment management API .

 S The cloud environment management API collects the instance information from the instances under the cloud environment.

 S The instance information acquisition unit stores the instance information in the instance information DB .

Next data structures of the response time information DB and the instance information DB will be described. is a diagram illustrating the data structure of the response time information DB. The response time information DB has a response time information table Tb. The response time information table Tb has items an instance ID a response time measurement starting date a response time measurement ending date and an average response time .

The instance ID is an identification number of an instance. The response time measurement starting date indicates a date in which measurement of a response time starts. The response time measurement ending date indicates a date in which the measurement of the response time ends. The average response time indicates a value obtained by dividing a total number of average response times of accesses from the start to the end of the measurement by the number of accesses.

Next a number of instances calculation process will be described. are diagrams for describing the number of instances calculation process. In the horizontal axis represents a system running time the left vertical axis represents a response time ms and the right vertical axis represents the number of instances.

Here a target response time which is a target value of the response time is assumed to be 200 ms. Further a calculation expression for the number of instances is defined as follows number of instances unit number actual measurement response time at time target response time 1 actual measurement response time at time actual measurement response time at time 2 1 

In Expression 1 K1 and K2 are coefficients. Here K1 1 100 and K2 1 400 are set. The number of instances rounds off. When the number of instances is a positive number the scale out is performed. When the number of instances is a negative number the scale in is performed.

On the other hand actual measurement response time at time T target response time K1 of Expression 1 is a term referred to as term 1 for calculating the number of scales based on a difference between an actual measurement value and a target value of the response time.

Further actual measurement response time at time T actual measurement response time at time T K2 of Expression 1 is a term referred to as term 2 for calculating the number of scales based on a change in the actual measurement value of the response time. Hereinafter an operation at times T to T illustrated in will be described.

 T The actual measurement response time is equal to 200 ms and the number of running instances is equal to 1. The actual measurement response time is equal to the target response time the scale out in is not performed .

 T The actual measurement response time is equal to 600 ms and the number of running instances is equal to 1. The actual measurement response time exceeds the target response time. In this case at the time T the actual measurement response time is equal to 600 ms and the target response time is equal to 200 ms. At the previous time T the actual measurement response time is equal to 200 ms.

Accordingly term 1 of Expression 1 is 600 200 100 4 . Further term 2 of Expression 1 is 600 200 400 1 . Accordingly the number of instances is equal to 4 1 5 and it is determined that 5 instances are subjected to the scale out.

 T The actual measurement response time is equal to 300 ms and the number of running instances is equal to 6. The actual measurement response time exceeds the target response time. In this case at the time T the actual measurement response time is equal to 300 ms and the target response time is equal to 200 ms. At the previous time T the actual measurement response time is equal to 600 ms.

Accordingly term 1 of Expression 1 is 300 200 100 1 . Further term 2 of Expression 1 is 300 600 400 0.75 . Accordingly the number of instances is equal to 1 0.75 0.25 but rounds off to become 0. Therefore at the time T the scale control is not performed.

 T The actual measurement response time is equal to 100 ms and the number of running instances is equal to 6. The actual measurement response time is less than the target response time. In this case at the time T the actual measurement response time is equal to 100 ms and the target response time is equal to 200 ms. At the previous time T the actual measurement response time is equal to 300 ms.

Accordingly term 1 of Expression 1 is 100 200 100 1 . Further term 2 of Expression 1 is 100 300 400 0.5 . Accordingly the number of instances is equal to 1 0.5 1.5 and rounds off. Thus 2 instances are subjected to the scale in.

Thus by calculating the number of instances using Expression 1 it is possible to efficiently obtain the number of instances to be subjected to the scale out in. As a result a period in which the instance is deficient or excessive is shortened and thus operational efficiency of the system is improved.

A user using a service by cloud computing is charged according to the number of running instances in some cases. In this case when the period in which the instance is deficient or excessive is shortened excessive charging to the user is suppressed. When a running instance is determined not to be desired before activation completion the instance is stopped. Therefore when deficiency in performance can be predicted an instance can start to be activated before actual occurrence of the deficiency in performance. When the deficiency in performance is known not to occur the activation process can be stopped. As a result since there is no reason for delaying the start of the activation of an instance in order to suppress charging occurrence of shortage of an instance due to delay of the start of the activation of the instance is suppressed.

Next a case in which the present technology is realized by a computer will be described. The above described processing functions can be realized by a computer. For example the information processing system is configured to include one or more computers. The functions of the number of instances calculation unit and the scale control unit can be realized by one computer included in the information processing system . is a diagram illustrating a hardware example of a computer used in the information processing apparatus.

The entire device the computer in the information processing apparatus is controlled by a CPU . A random access memory RAM and a plurality of peripheral devices are connected to the CPU via a bus .

The RAM is used as a main storage device of the computer . At least a part of a program of an operating system OS or an application program executed by the CPU is temporarily stored in the RAM . Various kinds of data used in a process by the CPU are stored in the RAM .

As the peripheral devices connected to the bus there are a hard disk drive HDD a graphic processing device an input interface an optical drive device a communication interface and the like.

The HDD magnetically writes and reads data on and from a built in disk. The HDD is used as a secondary storage device of the computer . The HDD stores the program of the OS the application program and various kinds of data. A semiconductor storage device such as a flash memory can also be used as the secondary storage device.

A monitor is connected to the graphic processing device . The graphic processing device displays an image on the screen of the monitor according to a command from the CPU . As the monitor there is a display device using a cathode ray tube CRT a liquid crystal display device or the like.

A keyboard and a mouse are connected to the input interface . The input interface transmits a signal transmitted from the keyboard or the mouse to the CPU . The mouse is an example of a pointing device and other pointing devices can also be used. As the other pointing devices there are a touch panel a tablet a touch pad a track ball and the like.

The optical drive device reads data recorded on an optical disc using a laser beam or the like. The optical disc is a portable recording medium on which data readable by light reflection is recorded. As the optical disc there is a digital versatile disc DVD a DVD RAM a Compact Disc Read Only Memory CD ROM a CD R Recordable RW Rewritable or the like.

The communication interface is connected to a network . The communication interface transmits and receives data to and from another computer or a communication device via the network .

The functions of the information processing apparatus can be realized by the above described hardware configuration. When the functions of the embodiment are realized by a computer a program describing the processing contents of the functions of the information processing apparatus is provided.

By causing the computer to execute the program the foregoing processing functions are realized on the computer. The program describing the processing contents can be recorded on a computer readable recording medium.

As the computer readable recording medium there is a magnetic storage device an optical disc a magneto optical disc a semiconductor memory or the like. As the magnetic storage device there is a hard disk device HDD a flexible disc FD a magnetic tape or the like. As the optical disc there is a DVD a DVD RAM a CD ROM RW or the like. As the magneto optical medium there is a magneto optical disc MO or the like. The recording medium recording a program does not include a temporarily transmitted signal itself.

When a program is circulated for example a portable recording medium such as a DVD or a CD ROM on which the program is recorded is sold. Further a program can be stored in a storage device of a server computer and the program can also be transmitted from the server computer to another computer via a network.

For example a computer executing a program stores a program recorded on a portable recording medium or a program transmitted from a server computer in a storage device of the computer. Then the computer reads the program from the storage device of the computer and executes a process according to the program. The computer can also read the program directly from the portable recording medium and execute a process according to the program. Whenever a program is transmitted from the server computer the computer can also execute a process according to the received program in order.

At least some of the foregoing processing functions can also be realized by an electronic circuit such as a digital signal processor DSP an application specific integrated circuit ASIC or a programmable logic device PLD .

The embodiment has been exemplified above but the configuration of each unit described in the embodiment can be substituted with another configuration with the same function. Further other optional constituents or processes may be added.

All examples and conditional language provided herein are intended for the pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed as limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although one or more embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.


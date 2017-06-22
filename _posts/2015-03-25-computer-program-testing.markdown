---

title: Computer program testing
abstract: To centrally manage execution of tests of software in an event oriented manner, a test execution engine reads a first test case from a test case component, where the test case represents tasks that have to be run to test a first procedure of a software program under evaluation. Further, the test execution engine identifies a participant node configured for sending events to an event queue and obtains events from the event queue. With those obtained events, the test execution engine evaluates whether the first procedure of the software program executed successfully and indicates whether the first procedure executed properly. The participant node has a node agent transmits events about the procedure and the first test case to the event queue.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09329983&OS=09329983&RS=09329983
owner: INTERNATIONAL BUSINESS MACHINES CORPORATION
number: 09329983
owner_city: Armonk
owner_country: US
publication_date: 20150325
---
Various aspects of the present invention relate to testing a computer program in an event oriented manner.

Test automation frameworks usually provide tools integration legacy tools support ease of use data integration reporting features shell script support automatic environment setup remote command execution etc.

However the definition of the test flow is deficient as it is not very flexible. This definition regardless of whether it uses proprietary language for testing or general scripting language is a sequence of synchronous actions more or less complex that an engine has to execute to complete the test case. Each action is usually represented by the invocation of a method of a class or by the execution of a Command line Interface CLI command on a remote or local machine and the subsequent check of the related result code returned by that invocation. Then according to such result the next step is executed to continue with the test case or an error is thrown to report the failure. Complex testing scenarios cannot be implemented by such testing frameworks.

According to various aspects of the present invention approaches are provided to centrally manage the execution of tests of software in an event oriented manner. A test execution engine reads a first test case from a test case component where the first test case represents tasks that have to be run to test a first procedure of a software program under evaluation. Further the test execution engine identifies a participant node configured for sending events to an event queue. The test execution engine provides to the identified participant node a test case definition of the first test case. The test case definition corresponds to a first event which when detected indicates that the first test case should be evaluated. The test execution engine obtains events from the event queue. The test execution engine evaluates the obtained events to determine whether the first procedure of the software program under evaluation executed successfully and indicates whether the first procedure executed properly. The participant node has a node agent that registers a first event handler for detecting the occurrence of the first event detects the occurrence of the first event and evaluates a first logical function with the first event as input in response to the detection of the first event. Also the participant node decides whether the first condition is met the decision being a function of the evaluation of the first logical function and sends an event message to the event queue based upon whether the first condition is met.

According to a first aspect of the present invention there is provided a method for testing a procedure of a software program said procedure being suitable for annunciating whether it executed successfully or not said method comprising the steps of 

adapting said computer program with a first executable component for altering the execution of said computer program said first executable component being configured for generating a first event to announce the occurrence of said alteration 

a first event definition corresponding to said first event which when detected said first test case should be evaluated 

a first logical function representing a first condition which must be met for executing said second executable component 

evaluating said first logical function with said first event as input in response to said detection of said first event 

deciding whether said first condition is met said decision being a function of the evaluation of said first logical function 

in a case where it is decided that said first condition is met carrying out the further step of requesting the execution of said second executable component and

determining whether said procedure has executed successfully in response to the execution of said second executable component.

A first advantage of this aspect is that the procedure can be tested in an asynchronous manner so that other procedures can be tested at the same time by the same system implementing the method. A further advantage is that the definition of the test to be run is very flexible and can be modified at any time even while the test of the procedure is running After updating the test case or the test cases dependencies the system would be able to re evaluate the dependencies and decide if new steps have to be triggered by re processing both the already received events and the new incoming ones. Yet another advantage is that sequences of test cases can be arranged and modified in a flexible manner for example by changing the dependencies between them even when the test is running

In a first development of the first aspect the alteration occurs when a predefined instruction in said computer program is executed.

In a second development of the first aspect the predefined instruction is an exception or a time out.

Another advantage of this aspect is that situations which may not be anticipated by the normal program flow can also be controlled.

Yet another advantage of this aspect is that it is easy to correlate the received event with the corresponding test case.

In a fourth development of the first aspect the second executable component is synchronous or asynchronous.

A further advantage of this aspect is that the call to the second executable component can be tailored to the need of the test environment. In the case of an asynchronous call the call to the executable component would not wait for the execution to finish thus optimizing the test system resources.

In a fifth development of the first aspect the second executable component is the computer program comprising the procedure to be tested.

An additional advantage of this aspect is that it is possible to test in a flexible manner the reaction of the procedure to be tested to the alteration of the computer program by the first executable component.

A further advantage of this aspect is that the hook agent could modify how the computer program interacts with another program without any alteration to the computer program.

In a seventh development of the first aspect the alteration caused by said first executable component is a system exit during a file download.

An advantage of this aspect is that the simulated situation is a worst case scenario wherein the computer program cannot gather any information on why the file download failed.

In an eighth development of the first aspect the procedure to test is adapted for restarting the file download which failed.

Another advantage of this aspect is that the procedure which is tested does not need to be correlated to the executable component which made the file download to fail.

According to a second aspect of the present invention there is provided an apparatus comprising means adapted for carrying out each step of the method according to the first aspect of the invention.

An advantage is that this apparatus can be obtained very easily thus making the method easy to execute.

According to a third aspect of the present invention there is provided a computer program comprising instructions for carrying out the steps of the method according to a first aspect of the invention when said computer program is executed on a computer.

According to a fourth aspect of the present invention there is provided a computer readable medium having encoded thereon a computer program according to the third aspect of the invention.

Further advantages of the present invention will become clear to the skilled person upon examination of the drawings and detailed description. It is intended that any additional advantages be incorporating therein.

a test management system comprising a test execution engine adapted to process a test case and an event from an event queue 

a first node comprising a node agent a first computer program adapted with a first event shooter and optionally comprising one or more other programs adapted with another event shooter 

The test execution engine centrally manages the execution of the tests and coordinates the activities of all the actors of the system. It reads the definition of a provided test case and manages the execution of the tasks belonging to the test case according to the events retrieved from the event queue and to the outcome of the execution of each single step of the test case .

The test case component is a representation of the tasks that have to be run by the test execution engine to perform a specific test. A test case defines also the criteria to infer if a test completes successfully or not. The test case is described in more details with respect to .

The event queue is the receiver for the events sent by the participant nodes during the execution of a test case . The events in such queue are retrieved and processed by the test execution engine . The order in which the events are de queued from the event queue can be first in first out first in last out an order taking into account the priority of the event as set by the event shooter . Alternatively the test execution engine can search the event queue to find the next expected event as defined in the test case and retrieve the event in an order not linked at all to the order in which the events were received.

The node agent is an element which can be installed on each node participating to the execution of a test case that is managed by the test execution engine . It is used by the test execution engine to remotely perform several kinds of tasks such as remote command execution file transfer operations etc. The node agent allows remote method invocation from the test execution engine . Possible communication means between the test execution engine and the node agent include RMI IIOP JRMP JMS SMS emails REST requests SOAP messages etc.

The event shooter sends events to the event queue when a specific situation occurs. Typically this element is able to intercept the activities performed by a specific program under test. In a preferred embodiment if the program under test is an agent that has to communicate with a server the event shooter can be a hook that intercepts the communications between such agent and the server. When specific messages are sent by the agent to the server the hook can send to the event queue an event to indicate such situation. The event shooter can simulate many of the environmental conditions that usually occur in a typical production environment that are difficult to recreate in a development environment such as loss of network connectivity unavailability of a needed service provider abrupt crash of the application etc. Moreover leveraging capture and replay capabilities the event shooter can enable execution of several instances of a test case by enforcing the same generation of unexpected events during each run providing in this way the possibility to debug and analyze any potential problem more accurately. More generally the event shooter component could also be an independent process that under certain conditions generates and sends events to the test execution engine . It is not necessary that the event shooter be directly related to the program under test nor that it execute within the same thread or share the same process id.

a node called Step A which requires that a Condition A is fulfilled in order to execute the Condition A itself requiring the occurrence of an event called Event 

a node called Step B which requires that a Condition B is fulfilled in order to execute the Condition B itself requiring the occurrence of the events called Event Event and of the completion of the execution of Step A 

The events defined in the test case correspond to events which can be generated by an event shooter as described with respect to . The detection by the test engine during the execution of the test case of a predefined Event or Event Event in the event queue triggers the evaluation of the respective Condition A or Condition B as defined by the test case.

a result which corresponds to a predefined value in the form of a string or an integer for indicating if the event has occurred and in which way it occurred 

a time of occurrence for indicating when the event has occurred its time of occurrence can thus be compared to the time of occurrence of other events so that the test execution engine can check a particular order of occurrence of the events for a condition of the test case to be satisfied 

a test case ID for identifying the test case instance the event applies to. If it is not specified the event will be automatically dispatched to all the test cases currently running inside the test execution engine .

Each step has a condition associated with it for specifying if and when that step can be executed. A condition is a logical function with inputs defined in the test case and a Boolean as output. Optionally fuzzy logic can be implemented by the condition so as to more accurately represent the state of the system and take finer decisions. The following conditions can be specified 

On Completion which evaluates to true as soon as the conditioning step completes regardless of its result 

On Event Sequence which evaluates to true when a specific sequence of events is received. If the received sequence is different from the expected one the related condition is not satisfied and the step will not execute. The Condition B is conditioned in such a way. This kind of conditioning can be very useful as a synchronization mechanism to decide when a specific step of the test case has to be executed in response to well defined events.

As a simple example of an application of this kind of conditioning it would be possible to configure an event shooter so that each time an exception is thrown inside the application a specific event is fired in this way it would be possible to monitor track all the exceptions thrown by the application and evaluate the final status of the test case also according to this criteria.

More than one condition can be specified for each step and all the conditions can be composed through Boolean operators AND and OR . For example the Condition B is conditioned by the complete execution of Step A and by the occurrence of Event Event . The test case can also define in which order the events and of Event Event must occur and that Step A must complete for Condition B to evaluate to true.

When a specific step is executed the execution engine can optionally pass as one of the input parameters of the invocation the condition object or and its status associated with the step. In this way the execution of the step may leverage such parameter to modify its behavior accordingly.

Each step represents an operation to be executed in the context of the test case. The executable component associated with a step can be identified by an ID a URL a URI or any other resource or method locator. Each step has an associated outcome. According to the outcome of the execution of the action the next step can be executed or not.

Synchronous actions which are represented usually by the invocation of a command line interface CLI command or the execution of a Java method Java is a trademark of Sun Microsystems Inc. in the United States other countries or both . The outcome of such actions is the result returned by the corresponding invocation.

Asynchronous actions are operations that run asynchronously. Usually they are started by invoking a CLI command that returns immediately after the operation has been submitted. The final result is in general available in a future moment in time. An example of an asynchronous task is the submission of a software distribution installation through a configuration manager product. Each asynchronous action sends an event to the event queue to notify its completion. Upon detection of such an event in the event queue the corresponding node for example the Step A node will update its status and the depending conditions Condition B in this case will be re evaluated.

a Condition whose positive evaluation triggers the execution of the agent reconfiguration and restart step 

an Event corresponding to the crash of the agent whose occurrence must be detected by the test execution engine for Condition to evaluate positively 

an Event corresponding to the package distribution being complete whose occurrence must be detected by the test execution engine for Condition to evaluate positively 

The Condition requires that the set up environment step has executed successfully. Successful execution of this step is ensured by the sending of a corresponding event by the executable component associated with the set up environment step . The execution engine must thus check periodically the different events present in the event queue so as to determine which condition function must be evaluated. It may happen that the occurrence of a single event triggers the positive evaluation of several conditions which in turn triggers the simultaneous execution of several steps.

The Condition requires the detection of the Event and of the completion of the start package distribution step to evaluate to true.

Similarly the Condition requires the detection of the Event and of the completion of the agent reconfiguration and restart step to evaluate to true.

The test objective of this sample test case is to verify the recovery capability of a solution that furnishes a software distribution service when the target abnormally closes the package download.

The test scenario will be described in more details with respect to . From a high level perspective it starts with the general environment set up . In a preferred embodiment this mainly consists in target enabling hook code . The package distribution towards a target is then initiated . As soon as the target starts to receive software package the hook code causes it to crash and to shoot an event to the test execution engine . If the hook code executes in the same process as the target program the event is sent before the crash of the program is caused as the crash of the program also causes the crash of the hook code or event shooter . The test execution engine recognizes the event and makes the target to restart without the hook code enabled to cause the crash . Package distribution when finished causes the shooting of an event of completion to the event queue . After receiving the last event or a believable timeout in case of general test case failure test execution engine validates test result and test case ends .

The test execution engine drives the execution of the test based on the test case . The test execution engine starts the test in response to the detection of the start step in the test case described with respect to .

The set up environment step being the next step and being unconditional in the test case the test execution engine executes the step and the executable component identified by this step in the test case. In particular the agent is instructed to start by the test execution engine by means of the asynchronous invocation of a startInstrumentedAgent method. The agent then enables the event shooter . Without waiting for a status from the agent the test execution engine enqueues a message or event in the event queue to announce that the agent was started.

The component monitoring the queue detects that the set up environment step has been executed. The test execution engine then reads the queue and evaluates the Condition as defined in the test case described with respect to . As Condition is fulfilled the test execution engine executes the start package distribution step . The distribute package sequence will be described in more details with respect to .

Upon completion of this step an event is fired by the event shooter to announce a situation and more particularly that the agent crashed . This event is detected and read from the queue . Condition is evaluated to true. The failure recovery sequence is then started. This sequence corresponds to the execution of the agent reconfiguration and restart step . The failure recovery sequence will be described in more details with respect to .

Upon completion of this step an event is fired to announce that the package distribution is complete . The event can comprise the following information 

The test result validation step is then executed and the test case evaluation sequence is started to determine whether the component under test had the expected behavior. In particular the test execution engine can verify that the event generated during the failure recovery sequence has the expected values corresponding to a successful test and a failed test otherwise.

The test execution engine executes the package distribution step . It instructs the server to start the distribution of the package. The package download is then initiated. Alternatively the agent can request the download to start in response to a request from the test execution engine . The agent notifies the event shooter that the package download has started. If the download completes successfully the server will enqueue a message in the event queue corresponding to that situation. However here the event shooter is adapted to makes the agent crash during the download. The event shooter thus enqueues in the event queue a message comprising the following information 

The event shooter then kills the agent . In this example the agent killing occurs after the message is sent because the event shooter executes in the same process as the agent . If the kill cannot occur for some reason the event shooter can send another event describing this situation. It is thus easy to correlate in the test case the later message with the message announcing that the agent is going to be killed.

The test execution engine restarts the agent . The goal is to test whether the agent will be able to detect that a package download has crashed and to restart the download and optionally resuming the download thus avoiding transferring again the data already received by the agent .

Upon successful completion of the download the agent will notify the distribution result to the server . The server will then send an event to the event queue comprising 

Another embodiment comprises a method and system for testing a software component by instrumenting the software component under test with a component able to modify the execution of the component under test and able to generate an event corresponding to the performed modification and by verifying that the order and the content of the event received match a predefined sequence.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.


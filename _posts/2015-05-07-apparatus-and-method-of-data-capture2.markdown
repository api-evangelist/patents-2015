---

title: Apparatus and method of data capture
abstract: A method of capturing the state of a target program that is running within the environment of an operating system is provided. The method includes identifying threads associated with the target program, suspending threads associated with the target program, preserving data characterizing the threads, and preserving data accessible by the threads when in operation. A method of changing the state of a target program that is running within the environment of an operating system is also provided. This method includes identifying threads associated with the target program, suspending threads associated with the target program, replacing data characterizing the threads with previously preserved data, and replacing data accessible by the threads when in operation with previously preserved data. In either case, the threads are then resumed to allow the target program to continue operation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09552224&OS=09552224&RS=09552224
owner: Sony Computer Entertainment Europe Limited
number: 09552224
owner_city: 
owner_country: GB
publication_date: 20150507
---
The present application claims the benefit of and priority to GB Application No. 1408380.2 filed May 12 2014 the entire disclosure of which is incorporated by reference herein.

The background description provided herein is for the purpose of generally presenting the context of the disclosure. Work of the presently named inventors to the extent it is described in this background section as well as aspects of the description which may not otherwise qualify as prior art at the time of filing are neither expressly or impliedly admitted as prior art against the present invention.

Conventional methods exist to archive the complete state of a computer system. An early example of such a method was the hardware based transfer of the complete memory of a computer to a file. An example of this approach is the SNA snapshot format used for 8 bit computers such as the Sinclair Spectrum and Amstrad CPC . The hardware based duplication of the entire memory from such old machines is typically used to transfer their functionality to an emulated version of the machine on a modern computer.

A more recent example of this approach is the ability to run a virtual PC on a server. Again a snapshot of the state of such a virtual system can be taken by copying the system memory of the virtual machine to permanent storage. The virtual machine can then be shut down and resumed when needed using the stored system memory.

This in turn is essentially a virtualised implementation of the hibernation mode used for example by laptops running Microsoft Windows in which all current system memory is copied to the laptop hard disk and the laptop then shuts down. Upon being restarted the system memory is restored back from the hard disk so that the computer can resume from its previous state.

In each case the entire memory of the system is captured thereby including the states of the operating system OS and any applications running in the OS environment for the purposes of suspending the whole machine for an indefinite period before restoring it from scratch following a real or virtual power on action.

However there are circumstances in which rather than suspending the state of the whole system and restoring the whole system it would be preferable to copy a state without interrupting the system so that the OS and applications can continue to operate but it would be possible to restore the copied state later on.

Microsoft Windows provides the facility to set so called restore points which are archives of the settings and software for certain key functions of Windows . Restore points are typically created before new software is installed that directly interacts with the Windows system and or host hardware such as driver software and other system files. This allows the new software installation to be undone by restoring the previous software and its settings in Windows if there is a problem with the new software.

However it will be appreciated that while restore points allow for old programs to be recovered and re integrated into the operating system they are not intended to save the current running state of a program currently running on the OS.

Nevertheless there are circumstances in which it would be desirable to be able to save the current running state of a computer program for subsequent recovery such as when developing new software that may crash or behave unexpectedly.

The foregoing paragraphs have been provided by way of general introduction and are not intended to limit the scope of the following claims. The described embodiments together with further advantages will be best understood by reference to the following detailed description taken in conjunction with the accompanying drawings.

In a first aspect a method of capturing the state of a target program that is running within the environment of an OS is provided.

In another aspect a method of changing the state of a target program that is running within the environment of an OS is provided.

In another aspect a computing apparatus for capturing the state of a target program that is running within the environment of an OS is provided.

In another aspect a computing apparatus for changing the state of a target program that is running within the environment of an OS is provided.

Referring now to the drawings wherein like reference numerals designate identical or corresponding parts throughout the several views an apparatus and method of data capture are disclosed. In the following description a number of specific details are presented in order to provide a thorough understanding of the embodiments of the present invention. It will be apparent however to a person skilled in the art that these specific details need not be employed to practice the present invention. Conversely specific details known to the person skilled in the art are omitted for the purposes of clarity where appropriate.

Referring to a typical computer program is illustrated. Such a computer program runs within the environment provided by the host operating system. Typical host operating systems include various iterations of Windows and Linux and also operating systems such as Cell OS which runs on the PlayStation 3 and Orbis OS which runs on the Playstation 4 . Other operating systems will also be known to the skilled person.

The computer program comprises a process live app process that owns one or more threads . The process also has a virtual memory allocated to it by the operating system that it can use to store any data workings and results it needs in the form of a mapped address space . It is also possible that during the live running of a program the program affects the memory of the host computer in other areas that are not directly mapped to the process such as in a graphics co processor and its attendant video RAM. This is termed unmapped state information .

It is desirable to capture sufficient information about the process the threads the mapped space and unmapped state of the live running program to enable the program to be subsequently rewound back to that live running state whilst also allowing the program to continue operation after the capture process has occurred.

Hence it is desirable to provide a capture feature that can capture the state of a running program the program can then subsequently continue to run but at a user s discretion a rewind feature can substitute the existing state of the computer program with the captured state so that in effect the program rewinds to a previous time of operation.

Notably this occurs without suspending or archiving the underlying operating system and or the machine as a whole as in the above described prior art.

Also notably the facility preferably works without the need to modify the source code of the running program first so that the rewind function can work with any or at least with many third party programs running within the OS environment thus providing in operation a new general rewind function of the OS and by extension of the computer.

Such a facility would be of particular use to program developers who may wish to evaluate the behaviours of a program in response to different variables such as variations in user inputs or other factors. By capturing the state of a program at a given point the program can be replayed differently from a common start position to evaluate its behaviour in different circumstances either to assess faults in the program or to assess and adjust a user experience.

Referring now also to in an embodiment of the present invention a second computer program is run within the environment of the operating system. This second computer program hereafter the capture program comprises a capture process that owns one or more threads e.g. main thread . The capture process also has virtual address space allocated to it by the OS.

Hence the OS runs among any other processes that it is running two processes the first process of computer program which may be referred to as the target process and the second process of the capture program which may be referred to as the capture process .

The following description assumes throughout that Windows is the host operating system OS for consistency of explanation but it will be appreciated that any suitable OS may be used.

The capture process may support a user interface allowing a capture event to be initiated by a user of the system. Alternatively or in addition it may perform a capture event periodically. Alternatively or in addition it may perform a capture event in response to a change in the operating system environment such as a particular disc access or memory or processor utilisation reaching a predetermined threshold.

When a capture is to be performed the capture process obtains the target process ID and requests from Windows a list of all threads in the system. The capture process can then compare the thread owner ID with the target process ID to identify the threads owned by the target process. It will be appreciated that in an OS where it is possible to request a list of threads corresponding to a process ID this initial step can be simplified.

Once the capture process has a list of threads belonging to the target process the capture process can attempt to suspend each thread on the list at a time. How this is done may depend on the OS and or the permission level of the capture process examples include direct instruction by the capture process or a request to the OS. Once a thread is suspended it cannot resume by itself unless an external process requests it. An OS will also not spontaneously resume a suspended thread of a third party process.

As illustrated in as a result the threads of the target process can all be suspended in quick succession. However any hardware services or code outside the user mode environment of the target process will not be suspended by this process for example if a graphics command was sent to the GPU the instant before the threads of the target process were suspended then the GPU will continue to process this command.

The suspension requests can be issued one after the other without waiting for each suspension to complete and hence the suspensions can occur substantially in parallel. However where it is possible to monitor the memory use and or CPU utilisation of each thread in advance then optionally the thread requests can be issued in order of largest and or most CPU intensive threads first to last. This is most likely to result in the target process main thread being suspended first thereby limiting scope for the main thread to attempt to communicate with a suspended thread during the brief period in which threads are being suspended.

User mode is a non privileged mode that normal code runs in. When a thread stops in user mode it is possible for example to read its registers including single instruction multiple data registers program counter and condition flags.

By contrast kernel mode is a privileged mode that the OS code runs in. Threads of target process enter this mode when they request an operation from the OS such as reading the keyboard. Hence for example a thread in user mode that makes a system call will swap the processor into kernel mode once the relevant function is complete then it swaps back to user mode. However if the thread is in kernel mode when it is suspended then the capture process cannot properly inspect the thread all that is visible is the program counter of the system call instruction and undefined registers and flags. Hence it is impossible to capture or reconstruct the state of the thread when suspended in kernel mode.

Consequently once the capture process has suspended the treads of the target process some will stop in user mode and some in kernel mode. The capture process can readily store the registers program counter and flags of threads in user mode. However for threads in kernel mode a different approach is needed.

To a first approximation one can assume that a thread in kernel mode will exit that mode and return to user mode if it was resumed for a short period of time in other words if the relevant system call that caused the thread to enter kernel mode was allowed to complete its current operation.

However if the thread is allowed to resume it would be desirable to re suspend the thread as soon as it re entered user mode. Depending on the OS the status of the thread may be directly inspected by the capture process or by the OS which the capture process can interrogate enabling the thread to be suspended when its status changes from kernel mode to user mode. However where this is not possible then an alternative approach may be considered as follows 

Using Windows as an example the Windows debugging API debugger interface can be used to present the capture process as a debugger to the target process allowing it to be attached prior to the capture event commencing. When a capture is performed the capture process can then replace the instruction immediately following the system call instruction with a breakpoint instruction. The capture process can then resume the suspended thread and wait for the breakpoint event. The thread then runs until it exits kernel mode hits the breakpoint and is re suspended but now in user mode. The capture process re inserts the replaced instruction and then stores the state of the thread like any other thread in user mode as described previously. This process can be repeated for each thread that is suspended in kernel mode if necessary.

The above process is further complicated however by the fact that it is not correct to assume that all threads in kernel mode will exit that mode in a short period of time. Some threads remain in kernel mode indefinitely such as those waiting for a semaphore or mutex mutually exclusive semaphores or reading network traffic. Thus more generally any call that may cause a thread to sleep or block in kernel mode indefinitely needs to be dealt with.

In an embodiment of the present invention such calls are trapped and replaced with a modified call that is embedded in a while loop.

In order to achieve this without needing code of the target program to be written specifically to co operate with the capture process it is useful to appreciate that such kernel mode calls are to functions external to the target program.

Hence for example consider a function from Windows kernel32.dll called WaitForSingleObjectEx. This function can block in kernel mode indefinitely. However the capture process can replace this dll dynamic link library function by updating the function pointer table in the dll to point to a substitute function MyWaitForSingleObjectEx 

It will be appreciated that this replacement function calls the original WaitForSingleObjectEx function transparently unless it has an infinite allowed run period in which case it is replaced with a call having a maximum 100 milliseconds block that sits within a user mode while loop. It will be appreciated that the test for an infinite period could be replaced with any suitable threshold such as for example greater than 200 or 100 milliseconds . As the while loop itself exists in user mode the overall effect is function operation within the kernel mode but with regular brief returns to user mode.

Wrappers to substitute other potentially indefinitely running functions in the system dlls used by 3party programs then all follow this approach.

In this way the previously described approach for accessing threads suspended in kernel mode can be used as it makes correct the assumption that threads in kernel mode will exit within a brief period of time.

Hence as a preparatory step the capture process or indeed a companion process to the capture process supplies substitute system functions to the target process at least for those functions capable of indefinite blocking in kernel mode. When a capture takes place the capture process suspends all threads of the target process and either directly stores the state of those threads suspended in user mode or adds a breakpoint and temporarily releases threads in kernel mode until they re enter user mode at which point they are suspend and read like any other suspended thread in user mode. The substitute system functions described above ensure that a return to user mode will happen in every thread.

In addition however the capture process also captures the virtual memory system of the target process.

The capture process either by direct inspection if adequate privileges are available or via the OS or via a debug interface inspects each virtual memory area VMA in the target process virtual memory space starting at address zero.

A VMA is defined by a starting address and a size and typically also by a protection parameter and a flag indicating the physical form of the memory. The protection parameter defines the operations that the target process is allowed to perform within the memory such as read only read write execute only etc. The flag indicates whether the VMA actually has physical memory allocated to it as it could simply be a reserved area of virtual space that has no real memory allocated in which case an access attempt will typically call a trap handler.

For each VMA in the target process the capture process creates a new VMA of its own of the same size and sets it as read write no execute. The VMA memory from the target process is then copied to the new VMA of the capture process. The actual protection parameter of the target VMA is stored in association with the new VMA elsewhere by the capture process.

Threads can have dedicated VMAs for storing per thread data. Such VMAs are typically referenced by a table stored in the VMA of an owning process and hence can also be accessed and duplicated in the same way.

In this way all user visible memory of the target process and its threads can be copied to one or more VMAs of the capture process.

The capture process can capture mutexes and semaphores by enumerating all the synchronisation objects in the system and correlating these with the target process ID. The value of an object can also be read. The functions to do this may be included in the capture process or may be part of the OS.

For applications that have a significant audio video component such as games it would also be beneficial to capture the state of the GPU and local VRAM. This is because when the stored state of the target process is subsequently restored it will assume that any current texture and geometry data in VRAM is still present.

For some devices such as the PlayStation 4 which has a unified memory architecture this is relatively straightforward and the techniques above can be employed optionally in conjunction with some techniques described herein below.

For a Windows PC and similar architectures and or operating systems one may expect to encounter a discreet video card such as an NVidia or AMD video card and a graphics interface such as Direct3D.

Direct3D supplies resources such as buffers textures render targets etc. via a handle system hence for example if the target process requested a new texture Direct3D may set the texture up and return a texture ID such as 1234 . However the video card itself will use an internal representation of its real resources and a mapping between the Direct3D issued ID and the actual texture will be stored somewhere that is not directly accessible by the capture process.

However Direct3D presents itself as a single function call from the Direct3D dll. Hence it is possible to supply a modified function hereafter a D3D Wrapper to the target process that routes function calls though to Direct3D whilst logging all these function calls and their arguments for the benefit of the capture process.

The Direct3D function call gives a C virtual interface for a tree of classes. Hence the D3D Wrapper returns a modified tree of classes and associated virtual function calls to replacement functions from which ID handle and resource redirection can be monitored.

Hence it will be appreciated that Direct3D function calls can be replaced in a similar manner to the replacement function calls to system dlls discussed previously enabling routing of the calls to the real Direct3D whilst also monitoring and logging salient data.

When a capture is instigated the capture process and or the modified function walks through each logged function call and requests from Direct3D either directly or via the D3D Wrapper that the corresponding resource is copied from VRAM to a new user visible VMA of the target process. Once each resource has been copied in this fashion Direct3D is instructed again either directly or via the D3D Wrapper to shut down.

Typically this transfer and shut down of video assets and Direct3D occurs either just prior to or in parallel with the suspension of the threads in the target process. This limits the scope for unmonitored processes to be implemented by the GPU during the suspended period.

The new VMA containing the VRAM is copied to a VMA of the capture process in a similar manner to other VMAs of the target process.

In this manner the capture process acquires the resources in the VRAM in association with their logged Direct3D handles.

It will be appreciated that a similar approach can be used for other graphics APIs such as OpenGL indeed in the case of OpenGL it may optionally be adapted to provide these monitoring and logging functions natively.

Moreover this approach may be used for any API interfacing with a relevant but not directly accessible state such as an API for sound with attendant sound RAM OpenCL memory buffers any suitable interface to discreet or unified video RAM and indeed to memory holding mutex and semaphore states.

Referring now to using the above techniques it is possible to suspend and back up the data needed to characterise the current running state of a target process without any prior modification to that target process. In particular the thread data mapped memory and VRAM resources of a target process can be copied to a visible address space of a capture process. The result is a snapshot comprising thread data and mapped address space including VRAM data copied to the memory of the target process and then on to the memory of the capture process as described previously. The saved information may then be stored separately for example on a hard drive or network storage and or may be retained in the memory of the capture process.

As such the above techniques provide a computer with the generalised means to snapshot the state of a running and unmodified program without interrupting the overall operation of the wider OS or other programs. The target process can then be released to resume its current operations and subsequently can be rewound to the stored state as described herein below.

To get the target process running again after a capture has taken place the capture process arranges for the suspended threads of the target process to be released again optionally in the same order in which they were suspended. In addition the capture process or the D3D Wrapper instructs Direct3D to restart and transfers back all the VRAM resources from the VMA. Direct3D will assign new IDs to these resources and so the D3D Wrapper builds a lookup table between the old and new IDs so that it can translate between them when communicating with the target process which will still have the old IDs and Direct3D which will use the new IDs . Optionally suspended threads are released once Direct3D has restarted and the VRAM has been restored.

The target process is then able to resume with the D3D Wrapper maintaining communication with the new instance of Direct3D and continuing to translate resource IDs.

The rewind process implemented at a later time. The rewind process typically assumes that the target process is currently running indeed typically it will be the same instance of the target process from which the state was previously captured.

Many steps in the rewind technique are common to the capture technique and typically the capture process is also capable of implementing the rewind technique. However optionally a separate rewind process may be run for this purpose or a separate process may be used for supplementary steps of the technique. Hence hereafter where a rewind process is referred to it will be understood that this may refer to either the capture process or a separate rewind process implementing the rewind technique.

The first steps of the rewind process are similar to those of the capture process namely identifying and suspending the target process threads and getting them into user mode where needed. Direct 3D is also shut down. The methods for doing these have been described previously herein and are not repeated.

For each thread stored within the snapshot the rewind process copies the register program counter flags etc into the corresponding thread of the target process.

Similarly for each of the virtual memory areas in the snapshot the rewind process copies the contents into the corresponding VMA of the target process. If a VMA is now different then it can be deleted and a new one is requested with the desired permissions size etc. and then the contents from the stored snapshot are copied across as appropriate.

For saved semaphores and mutexes the rewind process can place these in the global system object pool and then lock signal and or release them until their internal values match what they did at capture.

The rewind process then repeats the release technique described previously to release the threads of the target process and re start Direct 3D with VRAM resources copied from the relevant snapshot VMA. Again the D3D Wrapper is used to maintain communication with the new instance of Direct3D.

In this way the target process is rewound back to the time that the snapshot was taken without interrupting overall operation of the operating system or other applications whilst allowing the target process to resume after the snapshot was taken and also without the requirement to modify the code of the target process in advance.

It was noted above that for each thread stored within the snapshot the rewind process copies the register program counter flags etc. into the corresponding thread of the target process. However it is possible that a particular thread may have been terminated in the time since the capture took place.

The rewind process can request the creation of a new thread for the target process but the new thread will have a different thread ID and this is typically read only.

Consequently in an embodiment of the present invention the capture process also traps all thread create destroy operations and instead replaces them with a persistent thread pool. All threads are allocated from a large pool and when a destroy operation is trapped the thread is simply returned to the pool. Consequently the rewind process can then still access all the threads with correct IDs of the target process as it was when its state was captured.

It will be appreciated that the snapshot process can potentially use significant amounts of memory if one allocates a new VMA in the capture process that is the same size as that in the target process backing it up with physical memory and then copying each byte from the target process to the capture process. Consequently in an embodiment of the present invention a memory efficient approach is not to allocate a new VMA in the capture process in this manner but instead create a new VMA in the capture process that has the same properties as that of the target process but inform the OS that both VMAs point to the same piece of physical memory. The OS is then also informed that this physical memory is to be treated as copy on write thereby preserving any data that is overwritten by subsequent operation of the target process. Typically in this case when the target process writes to a memory page the VMA the OS momentarily pauses the target process allocates a new physical memory page and copies the current content of the page to the new page maps that copied page within the VMA of B and then resumes A. In this way the operating system manages copying and only physically copies those memory contents that would be altered while the resumed target process runs. This significantly speeds up the snapshot process and also significantly reduces the size of the snapshot in memory.

A likely scenario for use of the capture rewind technique is for an application whose current state is the result of significant input either by a user or real world data and so is difficult or laborious to replicate but where it is anticipated that subsequent inputs or program operations could either diverge significantly or cause errors in which case it is desirable to create the snapshot before this occurs so that labour is saved when reviewing these outcomes.

Examples of such applications are videogames where the state of the game environment may be responsive to the player s actions and also possibly responsive to physics simulations non player character AI and also possibly random processes making the current state difficult to reproduce. Taking a snapshot at this point allows a game developer to explore alternative gameplay strategies or review the circumstances required to produce a particular undesired or desired outcome.

Another example is a learning machine such as a neural network hidden Markov model or Bayesian machine that may receive live data feeds but be periodically snapshot when the outputs of the machine and or the veracity of the inputs in a given period are confirmed. This allows machines to monitor live data stock market weather or social media data for example but provides for aberrant data to be excised.

Referring now to in a summary embodiment of the present invention as described previously herein a method of capturing the state of a target program that is running within the environment of an OS comprises 

It will be appreciated that the method is carried out by the capture process program optionally in combination with the operating system for example to identify threads in response to a request from the capture program . The third and fourth steps are described as preserving data because data may either be physically copied to the VMA of the capture process or the original data may be marked as copy on write as described previously herein following which depending on the subsequent operations of the target process it may not need to be copied at all unless the target process attempts to overwrite it. Hence in either case the code is preserved but may not necessarily be copied.

In an instance of this summary embodiment as described previously herein the method comprises the steps of detecting whether a thread has been suspended in a protected mode e.g. due to a call to a first function implemented in the protected mode and replacing an instruction immediately after the call to the first function in the suspended thread with a breakpoint the breakpoint operating outside the protected mode. The thread can then be released and allowed it to run until it reaches the break point and is re suspended the replaced instruction is then restored in the suspended thread before the various data is preserved as before.

In this case for situations where the first function may remain in protected mode indefinitely then as described previously herein the method may comprise substituting the first function implemented in the protected mode with a function that in turn is operable to implement a loop outside the protected mode and from within the loop call the first function to operate for a limited period of time.

In an instance of this summary embodiment as described previously herein the method comprises the steps of creating a thread pool trapping thread create commands relating to the target program and instead supplying a thread from the thread pool and trapping thread destroy commands relating to the target program and instead returning a thread to be destroyed to the thread pool this ensures that threads with the same thread IDs can be obtained when the target program is re wound as explained previously.

In an instance of this summary embodiment as described previously herein the method comprises the steps of intercepting communications between a thread associated with the target program and a graphics application programming interface such as Direct3D and recording identifiers associated with graphics resources stored in a video ram used by a graphics processor.

In an instance of this summary embodiment as described previously herein the method comprises the steps of duplicating content from a video ram used by a graphics processor to a virtual memory area created in association with the target program and then preserving the content.

In an instance of this summary embodiment as described previously herein the step of preserving data accessible by the threads when in operation in turn comprises the steps of creating a virtual memory area associated with a capturing program i.e. the capture process the created virtual memory area having similar properties to the virtual memory area to be preserved pointing the created virtual memory area at the same physical memory as the virtual memory area to be preserved and setting the virtual memory area to be preserved as copy on write memory.

Referring now to in a summary embodiment of the present invention as described previously herein a method of a method of changing rewinding the state of a target program that is running within the environment of an OS comprises 

In an instance of this summary embodiment as described previously herein any replaced or restored semaphore or mutex is locked signalled or released as appropriate until its state matches its state when preserved.

In a summary embodiment of the present invention as described previously herein after either capturing or rewinding the state of a target program all suspended threads are resumed.

In an instance of this summary embodiment as described previously herein the method comprises the steps of duplicating preserved content to a video ram used by a graphics processor intercepting communications between a thread associated with the target program and a graphics application programming interface detecting new identifiers associated with graphics resources stored in a video ram used by a graphics processor and translating between recorded identifiers used by the target program and new identifiers used by the graphics application programming interface that correspond to the same graphics resources.

In a summary embodiment of the present invention a computing apparatus comprises processing means operable to run an operating system and programs running within the environment of that operating system and memory means operable to store data related to said programs and is configured to identify threads associated with a target program suspend threads associated with the target program preserve data characterising the threads and preserve data accessible by the threads when in operation.

In a summary embodiment of the present invention a computing apparatus comprises processing means operable to run an operating system and programs running within the environment of that operating system and memory means operable to store data related to said programs and is configured to identify threads associated with a target program suspend threads associated with the target program replace data characterising the threads with previously preserved data and replace data accessible by the threads when in operation with previously preserved data.

It will be appreciated that the above methods may be carried by suitably configuring conventional hardware by software instruction. As described herein the software is a capture program process in conjunction with the operating system and a graphics API as required. The capture program itself may in turn comprise separate processes such as a capture process a trapping process for system calls an intercept process for communication between the target program and the graphics API and optionally a separate rewind process. It will be appreciated that the or each process is started at an appropriate time with respect to the target process. For example the intercept process or the part of the capture process that implements API intercepts may be started immediately prior to the target process itself.

The above described software may also be implemented in conventional hardware by the inclusion or substitution of dedicated hardware operable to implement equivalent functionality.

Thus the required adaptation to existing parts of a conventional equivalent device may be implemented in the form of a computer program product comprising processor implementable instructions stored on a tangible non transitory machine readable medium such as a floppy disk optical disk hard disk PROM RAM flash memory or any combination of these or other storage media or realised in hardware as an ASIC application specific integrated circuit or an FPGA field programmable gate array or other configurable circuit suitable to use in adapting the conventional equivalent device. Separately such a computer program may be transmitted via data signals on a network such as an Ethernet a wireless network the Internet or any combination of these of other networks.

The foregoing discussion discloses and describes merely exemplary embodiments of the present invention. As will be understood by those skilled in the art the present invention may be embodied in other specific forms without departing from the spirit or essential characteristics thereof. Accordingly the disclosure of the present invention is intended to be illustrative but not limiting of the scope of the invention as well as other claims. The disclosure including any readily discernible variants of the teachings herein defines in part the scope of the foregoing claim terminology such that no inventive subject matter is dedicated to the public.


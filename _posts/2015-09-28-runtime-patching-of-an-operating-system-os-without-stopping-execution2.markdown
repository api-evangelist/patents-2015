---

title: Runtime patching of an operating system (OS) without stopping execution
abstract: Techniques for runtime patching of an OS without stopping execution of the OS are presented. When a patch function is needed, it is loaded into the OS code. Threads of the OS that are in kernel mode have a flag set and a jump is inserted at a location of an old function. When the old function is accessed, the jump uses a trampoline to check the flag, if the flag is set, processing returns to the old function; otherwise processing jumps to a given location of the patch. Flags are unset when exiting or entering the kernel mode.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652221&OS=09652221&RS=09652221
owner: Micro Focus Software Inc.
number: 09652221
owner_city: Wilmington
owner_country: US
publication_date: 20150928
---
This application is a continuation of U.S. patent application Ser. No. 14 134 026 filed on Dec. 19 2013 which is incorporated herein by reference in its entirety.

Most processing devices have some form of an Operating System OS . A typical OS has two modes of operation a user mode of operation and a kernel mode of operation.

The kernel mode of operation has unrestricted access to the underlying hardware for the device on which it processes can access every available memory address with pretty much unrestricted access and can execute any processor instructions associated with the device on which the OS operates.

The user mode of operation is the primary mode where users access and perform operations via applications but these operations have limited ability to access memory or directly access underlying hardware. Operations in user mode use Application Programming Interface API system calls some of which can process in kernel mode using kernel operations to perform needed hardware operations and memory accesses where user access is restricted.

During operation of a processing device the user s processes will jump in and out of user mode and kernel mode based on API system calls.

So when an OS kernel is patched a reboot is typically required of the processing device such as a server having multiple processors . The reboot ensures consistency between processes jumping in an out of the kernel mode by stopping all processes. So a reboot can be a costly and disruptive operation which is hard to schedule particularly when many parties via independent devices depend on the server to be available. Moreover processors for devices being serviced by the server have to be stopped and usually for a non trivial extended period of time. Some other approaches can achieve a patch without a reboot these solutions typically stop all processors running the OS while the patch takes place to ensure consistency. So either approach necessitates stopping the processors of the OS to install a patch which makes the OS unavailable to users during the patching process.

It is noted the problem also exists with standalone devices and not just multi processors of a server. For example many users will attest to the frustration with updating their phone OS because during the update their phones are completely unusable. The same holds true for set top boxes tablets laptops computer desktops and the like.

Various embodiments of the invention provide techniques for runtime patching of an OS without stopping execution of the OS.

In an embodiment a method for runtime patching of an OS without stopping execution of the OS is presented.

Specifically a patch function for an existing function is loaded within a kernel of an Operating System OS . Next a flag is set for each kernel thread active within the Operating System OS . Then each flag is unset when any OS thread enters the kernel or when any OS thread exits the kernel. Finally each flag for each kernel thread that attempts to execute the existing function is inspected and when that flag is set pass that kernel thread to the existing function for execution but when that flag is unset pass that kernel thread to the patch function without halting the OS.

A resource includes a user service system device directory data store groups of users a Virtual Machine VM a cloud combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that at one time or another is an actor on another principal or another type of resource. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal. Resources can acquire and be associated with unique identities to identify unique resources during network transactions.

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X and be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment virtual environment virtual machine VM and the term cloud may be used interchangeably and synonymously herein.

A server refers to a network device that manages multiple client machines processing devices can be multiple VMs on a single client machine the server can have multiple processors and memory.

Various embodiments of this invention can be implemented in existing network architectures and devices having an OS.

Also the techniques presented herein are implemented in machines such as processor or processor enabled devices hardware processors . These machines are configured and the memories programmed to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within memory and or a non transitory computer readable storage media or machine readable storage medium and are processed on the machines configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

Finally although the techniques presented herein can be implemented in any OS in an embodiment the techniques are implemented within a Linux SUSE or Android OS.

It is within this context that embodiments of the invention are now discussed within the context of the .

As will be demonstrated more completely herein and below the runtime OS patch manager permits automatic patching of kernel functions in a kernel mode of operation within an OS without having to stop or halt the kernel and without having to check whether any code is executing within the patched address space.

The consistency of operations is maintained within the kernel for threads processes . Once a thread enters or exits kernel mode for or to user mode that thread is transitioned to the patched kernel function when it re enters kernel mode.

Initially a profiling infrastructure is used to have a compiler inject a counter instruction at the beginning of each function in the kernel. For example a mcount operation can be used. In addition the compiler produces a list of all counter instruction locations in the resulting binary for the kernel.

Then the kernel upon boot self patches and replaces these counter instructions with NOP no operation instructions using the compiler provided list of locations. This is done because the counters are not used and the mcount infrastructure is ab used to just provide space and a list of locations for the NOPs.

Then when a desired kernel patch for a desired function is loaded as a loadable module the kernel sets a flag on each process thread and each processor device the flag referred to as patching in progress. 

In a similar manner same sequence of steps same NOP patching and IPIs code gets added to kernel entry exit points such that the per process patching in progress flag then gets unset every time a process enters or exits the kernel when calling a system call. The kernel also schedules a task to run on all processing devices CPUs and clear per CPU patching in progress flags. The flag processing is done for consistency within interrupt handlers in some instances per CPU flags can be set and unset in addition to per process flags.

These flags ensure that from the point of view of each sequence of execution processes interrupts all the functions change from old to updated atomically and there cannot be a case when an old function calls a new function or vice versa which could lead to a system crash.

Once all the flags have cleared only new code for the patched function is being executed and a similar sequence of replacing instructions can be used to switch from a JMP to the trampoline functions with a JMP directly to the updated functions instead removing the performance overhead associated with the trampoline.

The processing of the is now discussed with respect to the runtime OS patch manager using and perhaps expanding on the detail provided above.

The processing of the runtime OS patch manager deals with loading a patch function to a kernel of an OS and then gradually migrating all kernel threads to use the patch function and not the old previous and existing function. Some details provided above illustrate how the OS code is initially prepped to make this happen and those details are elaborated upon in the that follows the discussion of the runtime OS patch manager. So the runtime OS patch manager assumes the OS code was previously prepped for its discussion.

At the runtime OS patch manager loads a patch function for an existing function within a kernel of an Operating System OS . Again in an embodiment the OS is Unix Linux SUSE or ANDROID . The patch function is a function that either has an update or completely replaces some existing function that is actively executing within the kernel of the OS.

According to an embodiment at the runtime OS patch manager installs the patch function as a loadable module within memory of the device that executes the runtime OS patch manager such as a multiprocessor server . This is done without stopping or halting the OS.

Continuing with and at the runtime OS patch manager injects a jump instruction as discussed above at a location for the existing function within the kernel. The jump instruction is initially configured to simply proceed to the next instruction in the kernel representing the start of the existing function.

In an embodiment at the runtime OS patch manager issues a flush operation to clear cache on all processors that are using the OS can be multiple devices each having multiple processors .

Continuing with and at the runtime OS patch manager inserts a trampoline function at every remaining reference to the existing function within the kernel. This trampoline function permits each flag discussed at below to be checked below at every time the existing function is called for execution by each kernel thread discussed at below .

Continuing with and at the runtime OS patch manager issues a second flush of cache. This is again for all processors and devices that are using the OS.

In an embodiment at A the runtime OS patch manager uses each trampoline function to send each kernel thread to the jump instruction when that kernel thread s is set. So this is an indication that there is a kernel thread that has not exited the kernel since the patch function was loaded into memory. As a result to ensure consistency of operation for this kernel thread it is sent to the existing function in the kernel to the jump instruction inserted at and that jump instruction is still configured to just pass the kernel thread to the existing function.

In another case at B the runtime OS patch manager uses each trampoline function to send each kernel thread to the location in memory that has the patch function. This is an indication that a kernel thread has either entered the kernel after the patch function was loaded or exited the kernel when the patch function was being loaded and since exited to user mode and is returning to the kernel mode see below .

Continuing with and at the runtime OS patch manager will eventually modify the jump instruction to jump to the patch function in memory when every existing kernel thread has its flag unset. This means that all kernel threads from this point forward will not have a set flag and are executing the patch function. Moreover this is done as a precaution since it is apparent at this point that the existing function should no longer be accessed if each kernel thread is executing the patch function.

Continuing with at the runtime OS patch manager replaces each trampoline function with a new jump instruction that jumps to the patch function when every kernel thread has its flag unset. This removes any processing overhead in the OS associated with continually checking flags for threads when there is no longer any need to do so so performance does not degrade.

Continuing with and at the runtime OS patch manager terminates the processing at discussed below when every kernel thread is unset. Essentially does not need any termination because the processing the processing at took care that will not happen but it is stated here for completeness since is discussed below.

In fact it is to be noted that the processing at A B and occur after the processing at and exists during the processing at as well. So the is not intended to impart a particular sequence of operations.

At occurring before A B and the runtime OS patch manager sets a flag for each kernel thread active in the OS. This was discussed above the flag helps maintain consistency of the kernel threads as the patch function is gradually updated to replace the existing function within the kernel without stopping of halting the OS.

According to an embodiment the runtime OS patch manager identifies each OS thread as being in kernel mode representing one of the kernel threads or user mode representing a particular OS thread that processes outside the kernel. Threads can move in and out between kernel mode and user mode and are regularly changing within the OS.

At the runtime OS patch manager unsets each flag for each OS thread when any OS thread enters the kernel or when any OS thread exits the kernel. So when an OS thread moves from kernel mode to user mode its flag is unset and at that point in time it becomes a kernel thread. Likewise when a kernel thread moves from kernel mode to user mode its flag is unset and at that point in time it is no longer a kernel thread.

In an embodiment at the OS patch manager may also set and unset an additional flag for each processing unit CPU processing device in a multi processor device environment while updating the OS with the patch function on a per processing unit basis.

At the runtime OS patch manager inspects each flag for each kernel thread that attempts to execute the existing function and when that flag is set that kernel thread is passed to the existing function. However when the flag is unset that kernel thread is passed to the patch function. This is done without halting the OS.

It is now apparent how a function can be dynamically added to a kernel of an OS without halting stopping and or rebooting the OS. The updated function gradually is updated and eventually becomes a complete replacement for an existing function within the kernel as was detailed above.

The OS patch controller describes the prep work done to the OS kernel to permit the techniques discussed with the processing depicted in the .

At the OS patch controller inserts labels before locations of references to functions within a kernel of an OS. This is done when the OS is compiled and can use existing features of the OS to perform this processing on its behalf.

For example at the runtime OS patch manager processes a counter instruction of a compiler that compiles the OS to insert counters.

Continuing with and at the runtime OS patch manager uses a list for the locations provided by the compiler to assist in the processing of discussed below where each label is replaced with a NOP.

Still continuing with and at the runtime OS patch manager maintains the list for use when updating any of the functions within the kernel of the OS.

At the runtime OS patch manager loads a patch function for a particular one of the functions. That is a new function patch function is replacing an existing function a particular one of the functions identified at .

In an embodiment at the runtime OS patch manager loads the PF as a loadable module within memory of the device executing the OS such as a multiprocessor server .

Finally at the runtime OS patch manager gradually migrates or updates all references to the patch function within the kernel to call the patch function by using the NOPs. Again this is done without halting or stopping the OS. The details on how the processing of is achieved were discussed at length above with reference to the . By gradually it is meant that the migration or update occurs over some period of time and not all at one time typical case until all kernel threads have been securely migrated to use the patch function as detailed in the above.

According to an embodiment the runtime patching OS system implements inter alia the features of the software module s that implement the methods and of the respectively.

The runtime patching OS system includes a server . In some cases the server may also include a compile software module and a patch software module .

The server has memory one or more processors and or non transitory computer readable storage media. The server is configured to update kernel functions of an OS without halting the OS by gradually over some extended period of time updating or migrating the kernel functions to ensure consistency of operation for threads of the OS that are passing between kernel mode and user mode within the OS.

The details of how the server achieves the gradual update or migration were presented above in the with the initial prep assistance of the .

The server may also include a compile software module that is programmed in memory and or a non transitory computer readable storage medium for execution on one or more processors of the server . The compile software module is configured to label locations for references to the kernel functions during compiles of the OS. Details of this were discussed above at the start of the and with the .

Additionally the server may also include a patch software module that is programmed in memory and or a non transitory computer readable storage medium for execution on one or more processors of the server . The patch software module is configured to use the label locations provided by the compiled OS via the compile software module when gradually updating particular ones of the kernel functions with patch functions. The details of this were discussed above with reference to the .

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.


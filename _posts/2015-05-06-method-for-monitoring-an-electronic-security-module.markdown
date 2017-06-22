---

title: Method for monitoring an electronic security module
abstract: A method and a computer program are provided for implementing memory accesses. A hypervisor is used for this purpose, via which the memory access takes place.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09483665&OS=09483665&RS=09483665
owner: ROBERT BOSCH GMBH
number: 09483665
owner_city: Stuttgart
owner_country: DE
publication_date: 20150506
---
The present application claims priority to Application No. DE 10 2014 208 848.8 filed in the Federal Republic of Germany on May 12 2014 which is incorporated herein in its entirety by reference thereto.

The present method relates to a method for monitoring an electronic security module and to a computer program for implementing the method which is also referred to as hypervisor.

Control units are electronic modules which for instance are used in motor vehicles for the control and regulation of functional sequences. For this purpose the control units are assigned to the particular components of the motor vehicle whose operation will be controlled with the aid of the assigned control unit. In order to do so the control unit reads in data acquired by sensors and influences the operation by controlling actuators.

The described method is used in conjunction with an electronic security module which is utilized in a control unit especially in the automotive field in security relevant areas. The manipulation proof or non monitorable storing of data is an essential requirement in most applications in the security relevant areas. Cryptographic keys which are utilized in symmetrical or asymmetrical encryption methods are used for this purpose.

The employed codes and encryption methods constitute secrets that need to be kept hidden from attackers. Other uses in security relevant areas for instance concern the protection against unauthorized modifications such as the storing of changed serial numbers or tachometer readings the prevention of unauthorized tuning measures etc.

Hence it is necessary to provide secure environments in control units in which functionalities that must have access to and or modify these secrets can be executed. These environments normally have a secure computer unit or CPU also referred to as secure CPU as well as a storage module. An environment of this type is called a hardware security module HSM in this context. It represents a high performance module which includes hardware and software components and improves the security and trustworthiness of embedded systems. The HSM in particular helps in protecting security critical applications and data. The security costs are also able to be reduced by an HSM while effective protection against attackers is offered at the same time. As far as the basic structure of an HSM is concerned reference is made to .

Against this background a method and a computer program having the features described herein are provided. Refinements of the method and the computer program can be gathered from the descriptions herein and the specification.

According to the presented method applications together with associated keys or data are strictly separated from the system resources including the basic software functionalities within the HSM the main computer cores or main cores or in a combination of both.

The introduced computer program which is also referred to as hypervisor in this text is executed on a computer unit especially a computer unit in an electronic hardware security module HSM .

A hypervisor is therefore utilized in the method. This hypervisor which is also known as a virtual machine monitor is a computer program which provides a virtual machine. This hypervisor constitutes a superposed instance which can control and possibly prevent applications. More specifically the hypervisor regulates access to resources and memories and the execution of software with regard to the duration instant and repetition rate.

All hardware resources in the HSM are exclusively administered by a hypervisor. This enables a clear separation of different applications that are executed in the HSM. Mutual interference either selective or random is impossible for instance by the use of the MPU memory protection unit among others.

The hypervisor functionality is based on the MPU in the HSM and the differentiation of the system user modes. In other words all applications are executed in the user mode and access to system and hardware resources is possible only via defined APIs. A user mode is a restricted operating mode for the applications for instance the application can use only an allocated memory allocated time slots as well as APIs. Another advantage is that the crypto or security functionalities implemented in the software are strictly separated or protected from the remaining application and can be called up only via a defined API.

The hypervisor in the main computer or main core s operates independently of the use in the HSM. This constitutes a mechanism for protecting the operating system.

The essential features of the hypervisor in the HSM apply here as well. In addition the hypervisor software is able to be secured via the secure boot feature in the control unit run up so that the application software is no longer able to be manipulated in the ongoing operation. The code basis of the hypervisor is rather small and can therefore be certified completely. As an alternative the hypervisor code is also storable in the HSM and can be loaded into and executed on the main core RAM during the control unit run up.

Another option consists of encrypting the hypervisor code and decoding it during the control unit run up via the HSM and allowing it to be executed from the RAM.

Additional advantages and developments of the present invention derive from the specification and the appended figures.

It is understood that the features mentioned above and the features yet to be described may be used not only in the individually given combination but in other combinations or in isolation as well without departing from the scope of the present invention.

The present invention is represented schematically in the drawing on the basis of specific embodiments and described in the following text with reference to the drawing.

To trust an IT system that it will always act as expected requires trust in all of the incorporated layers one after the other in order to create a trustworthy IT system.

Trust in the entire IT system requires that each layer be able to rely on the effective security of the layer situated underneath without having the ability to verify this fact independently. For example this means that it is possible that a perfect software and hardware security solution may turn out to be useless because of a weak security system configuration situated underneath. Moreover it may be the case that a potential weakness in the system configuration will not be detected or prevented by the upper hardware and software layers.

In contrast to typical back and IT systems the hardware layer of embedded systems is frequently exposed to physical attacks that influence hardware or software functionalities through a physical arrangement e.g. manipulate a flash memory or deactivate alarm functionalities. One particular approach for making such physical attacks more difficult is the use of manipulation proof hardware security modules HSM such as those shown in for instance. Such an HSM protects important information for example personal identification numbers PIN secure keys and critical operations such as a PIN verification data encryption e.g. by strong physical shielding.

The manner in which an HSM may be developed and the kind of functionalities it is able to perform in order to improve the security of an embedded system will be illustrated in the following text.

Software layer includes a number of applications of which three are illustrated here. An operating system is provided in addition. Hardware layer includes embedded standard hardware as well as a hardware security module HSM . A first block in this HSM is provided for interfaces and the control a second block is provided for secure encryption functionalities a third block is provided for secure functionalities and a secure memory is included.

Secure memory is a small non volatile data memory e.g. having a capacity of a few kB within manipulation proof HSM so that an unauthorized readout or a manipulation or deletion of critical information e.g. of cryptographic keys cryptographic certificates or authentication data such as PINs or passwords is prevented. In addition secure memory of HSM holds all HSM configuration information such as information pertaining to the owner of HSM or access authorizations to secure internal units.

Second block for secure encryption functionalities holds cryptographic algorithms used for data encryption and decoding such as AES or 3DES data integration strengthening such as MAC or HMAC or a data origin verification e.g. through the use of digital signature algorithms such as RSA or ECC as well as all associated cryptographic activities such as key generation and key verification for instance.

Secure functionalities in third block include all protected functionalities that are not directly assigned to a cryptographic method HSM serving as physically protected trust anchor . For example this may be a physically protected clock signal an internal random number generator a loading routine protection mechanism or some other critical application functionality such as for realizing a secure dongle.

First block for interfaces and the control includes the internal HSM logic which implements the HSM communication with the external world and administers the operation of all internal basic components such as the ones previously mentioned.

All functional basic components of hardware security module as described above are surrounded by an uninterrupted physical boundary which prevents internal data and processes from being monitored copied or cloned or manipulated. This could make it possible for an unauthorized user to use or compromise internal secrets. The cryptographic boundary is commonly implemented by algorithmic and physical time channel countermeasures with a dedicated access protection arrangement such as special shielding or coatings in order to enable side channel resistance access reporting access resistance or an access response for instance.

The manner in which HSM is able to improve the security of an embedded product solution will be elucidated in the following text.

HSM protects critical information e.g. identities cipher keys or keys with the aid of the physical shield that cannot be circumvented by software susceptibility.

HSM is able to assist in detecting weakening or deterring powerful POI attackers POI point of interest by implementing effective side channel resistance and access protection barriers which among other things have severe access restrictions that apply even to authorized users. For example some information is always held within HSM exclusively.

HSM is able to accelerate security mechanisms in which certain acceleration switching circuits are utilized.

The use of HSM makes it possible to reduce the security costs by adding highly optimized special switching circuits for instance for standardized cryptography.

One possible structure of the HSM is shown in . It shows HSM which is embedded in an environment. The figure depicts a main computer unit a system bus a RAM component having an area for joint use and a test program or debugger including associated hardware and interface the latter in turn including a register . Moreover the figure shows a memory component for flash code having a data area and a secure area in which secure core data are contained.

Provided in HSM are an interface with respect to test program a secure computer core a secure RAM component a random number generator e.g. a TRNG or PRNG and a key e.g. AES.

The hypervisor includes both the standard functionality of the operating system also known as scheduling memory access and access to the hardware or basic software functionalities via defined programming interfaces or APIs application programming interface . The hypervisor can be realized using the already existing memory protection unit MPU which makes it possible to specify access to defined memory areas for applications either in the system or user mode.

The configuration takes place in such a way that all system and hardware resources are located accordingly and are reachable only via the hypervisor. The applications themselves are configured into different address ranges and executed only in user mode with restricted access rights. System functionalities realized in software that are to be protected e.g. secure libraries or SecuLibs etc. are linked to the hypervisor similar to the hardware resources and operated in system mode. The separation of the resources of the individual applications includes both the program area and the associated data of the particular application. Access to data of the adjacent application is not possible. This applies in particular also to the keys. This structure allows new applications to be integrated into the system as well with little effort.

When the hypervisor is used in the main computer or main computer core as well the current security anchor is expanded to include the main computer. With the aid of the secure boot feature together with the hypervisor in the HSM the hypervisor code in the main computer is secured during the control unit run up.

In addition the figure shows a system bus by way of which HSM is connected to a main computer . There a first area is provided for application programs a second area is provided for the communication and a third area is provided for memory access. In addition an area is available as an interface to HSM .


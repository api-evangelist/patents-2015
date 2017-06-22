---

title: UICCs embedded in terminals or removable therefrom
abstract: The invention proposes several improvements related to the management of secure elements, like UICCs embedding Sim applications, these secure elements being installed, fixedly or not, in terminals, like for example mobile phones. In some cases, the terminals are constituted by machines that communicate with other machines for M2M (Machine to Machine) applications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09462475&OS=09462475&RS=09462475
owner: GEMALTO SA
number: 09462475
owner_city: Meudon
owner_country: FR
publication_date: 20150123
---
The present improvements concern different topics related to the management of secure elements like UICCs embedding Sim applications these secure elements being installed fixedly or not in terminals like for example mobile phones. In some cases the terminals are constituted by machines that communicate with other machines for M2M Machine to Machine applications.

A UICC Universal Integrated Circuit Card can be in the format of a smart card or may be in any other format such as for example but not limited to a packaged chip as described in PCT SE2008 050380 or any other format. It can be used in mobile terminals in GSM and UMTS networks for instance. The UICC ensures network authentication integrity and security of all kinds of personal data.

In a GSM network the UICC contains mainly a SIM application and in a UMTS network it is the USIM application. A UICC may contain several other applications making it possible for the same smart card to give access to both GSM and UMTS networks and also provide storage of a phone book and other applications. It is also possible to access a GSM network using an USIM application and it is possible to access UMTS networks using a SIM application with mobile terminals prepared for this. With the UMTS release and later stage network like LTE a new application the IP multimedia Services Identity Module ISIM is required for services in the IMS IP Multimedia Subsystem . The telephone book is a separate application and not part of either subscription information module.

In a CDMA network the UICC contains a CSIM application in addition to 3GPP USIM and SIM applications. A card with all three features is called a removable user identity card or R UIM. Thus the R UIM card can be inserted into CDMA GSM or UMTS handsets and will work in all three cases.

In 2G networks the SIM card and SIM application were bound together so that SIM card could mean the physical card or any physical card with the SIM application.

The UICC smart card consists of a CPU ROM RAM EEPROM and I O circuits. Early versions consisted of the whole full size 85 54 mm ISO IEC 7810 ID 1 smart card. Soon the race for smaller telephones called for a smaller version of the card.

Since the card slot is standardized a subscriber can easily move their wireless account and phone number from one handset to another. This will also transfer their phone book and text messages. Similarly usually a subscriber can change carriers by inserting a new carrier s UICC card into their existing handset. However it is not always possible because some carriers e.g. in U.S. SIM LOCK the phones that they sell thus preventing competitor carriers cards being used.

The integration of the ETSI framework and the Application management framework of Global Platform is standardized in the UICC configuration.

A UICC can normally be removed from a mobile terminal for example when the user wants to change his mobile terminal. After having inserted his UICC in his new terminal the user will still have access to his applications contacts and credentials network operator .

It is also known to solder or weld the UICC in a terminal in order to get it dependent of this terminal. This is done in M2M Machine to Machine applications. The same objective is reached when a chip a secure element containing the SIM or USIM applications and files is contained in the terminal. The chip is for example soldered to the mother board of the terminal or machine and constitutes an UICC.

Some of the further disclosed improvements apply to such soldered UICCs or to such chips containing the same applications than the chips comprised in UICCs. A parallel can be done for UICCs that are not totally linked to devices but that are removable with difficulty because they are not intended to be removed located in terminals that are distant or deeply integrated in machines. A special form factor of the UICC very small for example and therefore not easy to handle can also be a reason to consider it as in fact integrated in a terminal. The same applies when a UICC is integrated in a machine that is not intended to be opened.

In the next description welded UICCs or chips containing or designed to contain the same applications than UICCs will generally be called embedded UICCs or embedded secure elements in contrast to removable UICCs or removable secure elements . This will also apply to UICCs or secure elements that are removable with difficulty.

The first improvement concerns the authentication of the end user of a terminal during SIM application transfer. In a given context an entire Sim application meaning personal data file system Java applications like bank applications for example and secrets is stored in an embedded UICC comprised in a first terminal for example soldered in a first mobile phone and a user wishes to transfer this entire Sim application in another embedded UICC comprised in a second terminal for example constituted by a second mobile terminal . This can happen when a user changes his mobile phone but does not want to lose the applications contacts and personal data such as photographs videos or songs stored in the UICC of his first mobile phone.

Such a problem does not occur when the Sim application is stored in a Sim card that can be removed from a mobile phone and inserted in another one since when a secure element like a UICC is soldered onto the mobile phone it is not possible to physically change the secure element containing the SIM application from a mobile phone to another one.

The general process to achieve this operation of transfer of the Sim application could normally be the following 

The result is that the initial complete Sim has been transferred in another secure element with the whole user environment.

When initiating the initial transfer from initial secure element up to the secure vault we can imagine that the end user is entering a PIN code to authenticate himself and confirm the operation. But a problem occurs when it is desired to transfer the packaged SIM again from secure vault to the targeted secure element How to be sure that the request is coming from the same end user There is no possibility to enter again the PIN code as it is part of the SIM application and it is necessary to be sure of the identity of the end user before installing the SIM in the targeted new secure element. This problem could lead to the fact that the subscription carried with the SIM could be installed and reused by another user.

In order to avoid this problem it could be possible to first install the SIM in the targeted secure element and then to request for PIN authentication. However the drawback is that installation of the Sim has been made and the authentication is not strong since for a PIN code on 4 digits after maximum 10.000 trials a dishonest person could find the correct PIN code and use the Sim application of another user and consequently his subscription .

In this respect the present improvement proposes a method for transmitting a Sim application of a first terminal to a second terminal the Sim application being stored in a secure element included in the first terminal the access to the Sim application being locked by a Pin code. According to this improvement the method consists in 

i exporting the Sim application from the first terminal to a distant site by including the Pin code as well as a remote loading code 

iii in the event the remote loading code entered by the user matches the remote loading code that has been exported authorizing the installation of the Sim application in a secure element of the second terminal and otherwise do not install the Sim application in the secure element of the second terminal.

Advantageously the match of the remote loading codes is checked at the level of the distant site and the match launches the downloading of the Sim application to the secure element of the second terminal and the installation.

Alternatively the match of the remote loading codes is checked at the level of the second terminal after the Sim application has been downloaded to the secure element of the second terminal the match launching the installation of the Sim application in the secure element of the second terminal.

Other features of the improvement will emerge from a reading of the following description of a preferred embodiment given by way of non limiting illustrative example.

The present improvement proposes to request the end user to enter a remote loading code in addition to the PIN code to confirm the export of the SIM application to a distant site the secure vault . The remote loading code can for example be a pass phrase.

This pass phrase is ciphered and included in the secure packaged SIM that is uploaded to the secure vault on the cloud. Thus the secure vault stores the packaged Sim the subscription comprised in the secure element the PIN code the environment the authentication secrets the applicative keys Security Domain the different keys of the different applications the PKI keys the different applications NFC bank . . . the ISD Issuer Security Domain the file system . . . and the remote loading code in a unique package that can be later downloaded to a new secure element.

Before installing this package to the new secure element the user of the second terminal comprising the secure element is asked to enter the remote loading code in the second terminal.

If the remote loading code entered by said user matches the remote loading code that has been exported the installation of the Sim application in the secure element of the second terminal is authorized. Otherwise the installation is not done.

Two different ways of operating can be used the first one consists in checking the match of the remote loading codes at the level of the secure vault. If the codes match the Sim application is downloaded to the secure element and then executed.

The second one consists in checking the match of the remote loading codes at the level of the second terminal after having downloaded the Sim application in the secure element of the second terminal. If the codes match the Sim application is installed in the secure element of the second terminal.

After having been installed the Sim application can be launched by the user by entering his PIN code.

In a preferred embodiment the remote loading code is enciphered. In the first embodiment the secure vault un ciphers the pass phrase contained in the packaged SIM. In the second embodiment the secure element does this un ciphering.

The improvement permits to enhance the overall security of transfer of the Sim application since it ensures that the SIM application is exported and imported by the same end user.

The second improvement concerns the export of sensitive data out of a secure component UICC chip to be sent into a secure vault e.g. a secure server with no risk of cloning the data and no direct data link between the UICC and the secure server. More precisely the improvement concerns a method for exporting on a secure server data comprised on a UICC comprised in a terminal.

When changing terminals like mobile terminals for example mobile phones wireless terminals or connected terminals users want the facility to keep along the services that were enable in their old terminal. These services such as the cellular services or banking services are relying on keys and sensitive data loaded in a UICC of the terminal.

If the secure component UICC is removable such as a classic SIM card and if the new terminal supports such a removable component then the user can just remove the secure component from the old terminal and insert it in the new terminal.

But if the UICC is not removable embedded UICC or if the new terminal does not support this type of component then there are needs to be a way to move all the keys and data related to that service to the secure component of the new terminal.

Another problem that arises in the case of embedded UICCs is that the old and the new terminal are sometimes not available at the same time. The user wants to secure its sensitive personal data and keys before buying his new terminal.

The improvement provides a way to securely export the keys and data related to a service to a secure vault for further download into another or the same terminal in such a way that the keys and data cannot be cloned.

Furthermore the improvement addresses the problem that it may not be possible to establish a direct IP link between the secure vault and the secure component.

To this purpose the present inventive proposes a method for exporting on a secure server data comprised on a UICC comprised in a terminal. The method consists in 

The UICC is preferably embedded in the terminal and the export request is preceded by a selection of the data to be exported.

The improvement will be better understood by reading the following description of the figures representing preferred embodiments of the present improvement.

The improvement integrates an asynchronous connection between the secure component UICC and the secure vault constituted for example by a remote server.

In the end user of a terminal selects first the data to be exported. These data are for example phone numbers or private keys that the user wants to secure for being able to transfer them later on another or the same terminal.

This can be done by selecting an application id or a service id on the UICC. This can be done by the user through an application on the terminal or automatically through the terminal. This corresponds to an export request formulated by the end user. Such an export request could also be formulated by the remote server or by the terminal.

Optionally when selecting the data service to be exported from the UICC the user terminal may have to present a code or to authenticate towards the UICC or the service in order to get access to the data.

The terminal then initiates the export session on the secure component by sending him an INIT EXPORT SESSION order.

In response the UICC returns a Signed Export request to the terminal. This request is uniquely identified and signed by the UICC.

The Signed Export request is transmitted asynchronously to the server through a network like an IP cellular OTA or OTI network.

At reception the server verifies the signed export request by comparing the signature and the identity of the UICC. The improvement does not mandate any particular security scheme but requires that the server can verify the signature of the UICC.

The server generates then an Export Certificate . This certificate is uniquely signed by the server and uniquely identifies the UICC. With this certificate the server confirms that the UICC is genuine and that the export process can be initiated.

The UICC then verifies the Export Certificate . The improvement does not specify a particular security scheme but the UICC must have the ability to verify a signature from the server.

The UICC prepares an Export Package . This export package is encrypted and signed by the UICC. In addition the Export Package includes the Export Counter . The Export Package is sent to the terminal. If necessary as shown in the diagram due to I O limitation between the terminal and the UICC the Export Package can be sent through multiple commands. After having been sent to the terminal the image of the transmitted package kept at the level of the UICC is rendered inactive for avoiding a possible duplication of the package .

The Export Package is then transmitted asynchronously to the server. Since it is encrypted only the server can read it.

Once received the server decrypts and verifies the Export Package. For each UICC the server maintains a copy of the Export counter. The Export Counter in the Export Package must be higher than the copy of the export counter maintained by the server otherwise the export package is rejected. Once the export package has been accepted the server updates its copy of the Export Counter to match the value in the Export Package.

The server then generates a Signed Ack. This Ack is uniquely signed by the server and includes the value of the export counter. When having sent this command the received package is rendered inactive at the level of the server.

The UICC verifies the received Signed Ack and if it matches destroys its copy image of the data that have been exported.

The UICC then generates a Signed Destroy Ack which is uniquely signed by the UICC and includes the value of the export counter.

The server then verifies the Signed Destroy Ack. If it matches the exported data are available to be imported into another UICC in a new terminal or in the same one later.

The third improvement relates to the remote management of a secure element like a UICC located on or in a device that can be infected by a malware. This improvement applies to embedded UICCs and to removable UICCs. The term secure element will be used in the following description for designating such an UICC.

It is known that once issued the secure element needs to be maintained during their whole life. The maintenance usually consists in remote update of the secure element content. It could be a late stage personalization a code patch installation of a new functionality data update key renewal etc. . . . . These operations are performed by a remote administration platform that operates through a potentially unsecured network e.g. the Internet and a potentially unsecured device to which the secure element is attached.

In order to secure the process there is usually an end to end secure communication protocol between the administration platform and the secure element e.g. one Global Platform protocol . However in most cases neither the server nor the secure element has a direct connectivity to each other and there is some middleware on the device that initiate the secure administration session. It is well known that this first session between the middleware and the server has to be secured as well e.g. with TLS for multiple reasons authentication of remote management request confidentiality of the request avoiding denial of service etc. . . . .

However if some malware is located on a terminal it can be used by a hacker to perform some remote management on its secure element on behalf of the victim s device on which the malware is sitting as depicted in .

In this figure the malware is located in victim s terminal . Even if the channel between the terminal and the administrative platform is secured through TLS the malware can direct the content data and software to another secure element located in a hacker s terminal through the Internet . This redirection of the downloaded content can be very harmful for the owner of terminal . For example in the Telecom domain it can be foreseen to download an entire SIM application on an existing secure element like . For that the user of terminal connects to the administrative platform through the Internet and asks for a subscription to a given MNO the administrative platform can be connected to different MNOs as it will be seen later . Platform recognises user s terminal and after this identification prepares the content to be downloaded Sim application data credentials among them IMSI and Ki . If the content is loaded on the secure element of the hacker instead on the secure element the owner of terminal will not only not be able to connect to this MNO s network but he will pay for the hacker s communications.

Using the secure element as is to authenticate the device is also difficult for two reasons. Firstly the secure element is under management so it is difficult to use it especially if it is not personalized or if its personalization is not finished . Secondly the credential it contains may belong to another entity which is not the one operating the remote management platform.

In this respect the present improvement concerns a method for managing content on a secure element connected to a mobile equipment the content being managed on the secure element from a distant administrative platform the method consisting in 

The verification can consist in verifying that the private key used for establishing the secure channel corresponds to a certificate stored on the secure element that has generated the sessions keys.

In another embodiment the verification consists in verifying that an identifier corresponding to a symmetrical key used for establishing the secure channel corresponds to an identifier stored on the secure element that has generated the session keys.

The improvement proposes to insert in the secure element an independent application which is used to secure the session between the administrative platform and the terminal. After this step the server verifies the binding between the identity at the device session level and the identity at the secure element remote management.

As can be seen the secure element comprises an application foreseen to provide session keys to the administrative platform . These session keys are generated by the application and transmitted to the mobile equipment . The application transmits also an identifier or a certificate to the mobile equipment 

In both of the preceding cases a secure channel has been established between the platform and the equipment .

The main second step of the improvement consists in verifying the binding between the identity at the device session level and the identity at the secure element remote management.

A request to manage content of the secure element is sent to the administrative platform. This management consists for example in downloading content on the secure element deleting or exporting content stored on it or activating or deactivating content stored on it. The download of content can for example consist in downloading an entire Sim application on the secure element with the associated credentials IMSI Ki . It can also consist in downloading a phone book in the secure element from the platform .

In order to verify this binding the secure element sends through the established secure channel a fixed identifier like for example his ICCID or his serial number. The platform verifies that this request originates from the same secure element for example the session keys used for establishing the secure channel are compared to the fixed identifier . If the check is positive the management is authorized. On the contrary if the check is negative the management is forbidden.

The improvement thus ensures that the secure element that is managed is the correct one and not another secure element linked to the platform by a malware.

The fourth improvement concerns the personalization of a secure element by using another secure element in post issuance.

Secure personalization of secure elements is a heavy step in industrialization and distribution of services on secure elements.

This improvement proposes to not performing this step in factories but to let the user do it according to its needs.

Credentials porting from one secure element to the other one has not been possible so far. Until now it meant replacement of an old secure element by a new secure element already personalized with partial porting of the credentials.

The improvement also aims to allow to an end user to personalize an embedded secure element embedded UICC by transferring data to this embedded UICC after post issuance. This can for example consist in transferring to the embedded UICC a new application like a banking application for example.

In case of personalization of an embedded UICC the improvement proposes a method for personalizing a first secure element comprised in a first terminal said method consisting in 

In case of transfer of credentials comprised in the first secure element to the second secure element the first secure element being comprised in a first terminal the method for transferring credentials consists in 

The first and second secure elements can be removable or not embedded UICC . When the second secure element is removable its form factor can be a Sim card or a dongle for example. It can also be comprised in a so called smart badge having a wireless link with the first secure element. It can also be comprised in a mobile terminal under a non removable form embedded UICC .

The personalization can be done in a public area without any network access by anyone e.g. the end user anywhere e.g. at end user home and without any connectivity constraint.

This personalization can for example consist in a transfer of credentials Imsi Ki of a banking application from a mobile terminal for example a mobile phone to another one.

The improvement also applies to the personalization of a secure element embedded in a terminal for example in a PC. The second secure element is simply plugged in the PC and the personalization occurs.

For securing the point to point personalization certificate verification and asymmetric encryption are used. The security relies on the second secure element in any form factor and the use of a PKI scheme allowing an authentication between the two secure elements.

The personalization happens after the issuance of the secure element to be personalized. This is in particular useful when an end user already owns a secure element e.g. a smart card in its mobile phone a banking card a secure element in a PC or any other device. When the user needs wants to transfer its credentials to a brand new secure element the existing secure element can transfer the credentials contained therein subscription to a MNO entire Sim application with IMSI and KI content of an e purse . . . to the new secure element. This may happen securely in the field the user only needs to hold physically both secure elements.

This is also applicable when the end user wants to add a new service provided by any Service Provider on an existing secure element. He can be provided with a secure element able to personalize its first secure element without being required to connect to Internet nor to go in a shop.

The improvement allows also updating the personalization of a secure element post issuance. This is also true for an update of the secure element personalization.

The improvement permits to reduce personalization cost in factories and allows secure post issuance personalization. The end user does not need to go to the service provider shop nor to connect to Internet to personalize update its secure element. Moreover security is granted by point to point personalization relying on two secure elements. This is also simplified by the non connected process no virus threat .

The fifth improvement concerns the communication to an end user of personalization confidential data of its UICC.

Today when a UICC card is delivered to a customer some personalization confidential data such as the associated PIN and PUK codes are also delivered to the customer. As these data are confidential several communication schemes are used 

The problem with scratch codes is that the user generally keeps the codes at home and their access is not restricted.

According to this improvement for delivering confidential data to a user of a mobile terminal containing a UICC the confidential data being related to the UICC the confidential data are stored on a storage media that can be read by the mobile terminal access to the confidential data being enabled by the UICC and conditioned by a security policy implemented by the UICC.

The improvement enables the customer to access these confidential codes on a storage media securely. This storage media can be delivered through any non secured physical delivery mean since confidential data are encrypted and can only be read by using the customer UICC. The storage media in the form of a dongle for example or a SD card is given or sent to the customer by the MNO. End user is able to read securely the personalization confidential data stored in the storage media by using the UICC embedded or removable UICC located in his mobile phone.

The UICC comprises a software that is able to decrypt the personalization data and implement a security policy to access these data 

The pairing between the secure element and the user s data or UICC permits to guarantee that only this user will have access to the confidential data.

The deployment of the storage media can then be delivered through any means that does not need to be secured. The security of the solution relies on the secure element UICC located in the mobile phone.

The sixth improvement concerns embedded UICCs not removable . In a first embodiment the improvement is about a method using NFC to select and download an embedded U SIM application or generally speaking a complete UICC application to a terminal comprising such an embedded secure UICC. The terminal is for example a mobile phone.

In a second embodiment the improvement is about a method using a barcode for identifying a U SIM application or generally speaking a complete UICC application to be downloaded to a terminal able to take a photograph of this barcode.

As already explained in the introduction in the future when there are soft SIMs or embedded SIMs inside devices it will be necessary to select the appropriate subscription information to download to the device. The user experience could be improved by giving a single use NFC tag identifying the subscription for the device to download.

Said otherwise in a world where the subscription information is no longer stored in a secure removable format such as today s UICC and instead stored as a soft SIM or soldered secure element e.g. a VQFN8 DFN8 secure element then there is a need to select the correct subscription to download to the device.

The improvement proposes a method for downloading a subscription in an UICC embedded in a terminal this method consisting in 

The ICCID is preferably transferred along with a ICCID s secret activation code and the secure vault verifies the pairing of the ICCID and the secret activation code before transmitting the subscription to the terminal.

In a first embodiment the ICCID is contained in a token and the ICCID is transferred to the terminal via NFC.

The download of the subscription could be done through the user interface or in a push way. However for terminals that are unlocked a need is present for MNO processes with legacy flows to have a physical tag NFC card to distribute similar to today s physical SIM card. This tag would contain a reference to the ICCID with a security activation code known to the provisioning system and linked to an individual ICCID . Once the ICCID is submitted to the provisioning system with the correct activation code the remote provisioning service can begin the secure transfer of the correct software SIM profile subscription information for the embedded secure element.

If for example a user has a pre activated device X and want to buy a subscription from operator A the flow would be as follows 

If for example a user has a pre activated device X and want to buy a subscription from operator A the flow would be as follows 

In a second embodiment the ICCID is contained in a barcode to be photographed by the terminal. After having taken a picture of the barcode the terminal sends it to the secure vault. The secure vault then compares the received barcode with pre registered barcodes or decodes the barcode for retrieving the ICCID. The same process as mentioned above is then undertaken.

The improvement allows selection of subscription as well as profile variant remotely and makes the user experience very easy.

The seventh improvement relates to a method for transferring a subscription from an embedded secure element embedded UICC to a physical card removable UICC .

In the future when there are soft SIMs or embedded SIMs inside terminals it will be necessary to transfer the subscription information IMSI Ki Opc phonebook etc between a terminal with an embedded secure element and a terminal with a classical SIM slot in 2FF 3FF format.

In the state of the art to solve this problem it is unavoidable to buy a new SIM card that is re paired by the operator re pairing it. This leads frequently to a loss of user data.

The present improvement proposes a solution to this problem by proposing a method for transferring securely subscription and user data content between an embedded UICC and a removable UICC.

To this purpose the present improvement proposes a method for transferring securely a Sim profile comprising subscription and user data between a UICC embedded in a terminal and a removable UICC the method consisting in 

Alternatively the improvement proposes a method for transferring securely a Sim profile comprising subscription and user data between a UICC embedded in a terminal and a removable UICC the method consisting in 

At point of sale a mini personalisation station comprises blank cards belonging to a MNO. The station comprises a master key known to the personalisation system.

If the user of a terminal containing an embedded UICC wants to downgrade to a terminal having a Sim slot i.e. a terminal where a removable UICC can be inserted the flow would be as follows 

It is also possible to use a master key in the personalization station. Then all the UICCs in the personalization station have the same master key and it is used for the symmetric encryption of the profile as well as decryption of the profile within the removable UICC holding the corresponding master key inside the personalization station .

This improvement allows the transfer of subscriptions peer to peer between an embedded secure element and a classical SIM without passing by an OTA server.

The eighth improvement concerns a method for transferring a subscription between terminals with embedded secure elements embedded UICCs storing subscription information over NFC.

In the future when there will be soft SIMs or embedded SIMs inside terminals it will be necessary to transfer securely the subscription information IMSI Ki Opc user data like the phonebook etc from one terminal to another for example by touching them together in order to avoid reprovisioning the IMSI Ki Opc over the air into the new terminal using remote personalisation.

Today if a user wants to change his mobile terminal he can simply extract the UICC card from his old terminal to insert it in the new one. But this is not possible if the new one does not have a slot for inserting the Sim card i.e. has an embedded UICC or if the format of the UICC does not fit to the new terminal. The same problem occurs if the old terminal contains an embedded secure element the Sim application cannot be extracted manually.

The present improvement concerns a method for transferring securely the subscription information and user data from a first terminal to a second terminal the terminals respectively containing a first and a second UICC. According to the improvement the method consists in 

ii transmitting from the first terminal to a secure vault the identifier of the second terminal and an identifier of the first UICC 

iii transmitting from the secure vault to the first terminal a subscription installation public key of the second terminal 

iv in the first UICC packaging and encrypting the subscription information and user data with the subscription public installation key of the second terminal 

The following description is a use case where subscription information and user data are transmitted over NFC from a first to a second terminal.

If for example a user has a terminal X first terminal and wants to upgrade to a terminal Y second terminal the flow would be as follows 

It is also possible to establish a Bluetooth communication between the two terminals or any other channel. Using Bluetooth requires however pairing exchange of keys etc.

The improvement allows transfer of subscriptions remotely without passing by an OTA server only contact with network is needed for authorisation key exchange notification of completion of the subscriptions .

In another use case if Device Y does not have the same profile capabilities installed as Device X the secure vault can do a remote personalization of the UICC in Device Y. In this case it requests Device X to package its profile in its current state including profile subscription keys user data etc and upload it to the secure vault. In the case where the two secure elements are not compatible or are different versions the virtual profile would have to pass through the secure vault and then be transformed for Device Y s different embedded UICC and then repersonalized for the Device Y.

2 A smartcard Operating System executed on the chip providing standard services answer to ISO7816 3 reset answers to standardized APDUs sent by a reader . . . .

3 A set of applications executed on the chip providing answers to APDU defined by application provider

4 A set of personal data e.g. phonebook UICCID IMSI stored in the physical memory of the chip used by the smartcard OS

5 A set of secret data keys and PINs stored securely in a physical memory of the chip and used by the smartcard OS to provide secure services.

This Physical UICC can emulate several UICCs each one having the behaviour described in 2 and 3 storing sets described in 4 and 5 . This service is provided by embedding in the chip the 2 3 4 and 5 of each UICC emulated. An emulated UICC is hereinafter called Logical UICC. Because of physical memory constraints technology of the memory limited amount of volatile and persistent memory and Operating System constraints part of the volatile and persistent data of different Logical UICC are stored in the same location when they are executed. These parts of data are called overlapped volatile data and overlapped persistent data. This is the case for example for the volatile data of the Logical UICC they are stored in the limited amount of volatile memory of the physical UICC during the Logical UICC execution time.

The UICC card can be considered from the external world e.g. reader as anyone of the logical UICC that it emulates.

In the state of the art the basic behaviour to switch from a first logical UICC to another one is to reset the physical UICC and after the ISO7816 3 reset execute the Operating System of the newly selected logical UICC. During the reset the volatile memory of the physical UICC is cleared and all volatile data of the first logical UICC is lost. After this reset the software of the logical UICC is executed as today in a usual UICC from scratch a complete activation sequence shall be performed by the reader. It is requested by 2 and 3 to initialize its volatile data in order to set up the applicative and system contexts. The volatile data of the newly selected logical UICC are stored in the volatile memory of the physical UICC at the same location used by the previously selected logical UICC.

The volatile context of the logical UICC previously selected is however lost. If a service from this logical UICC is requested again the logical UICC shall be selected again and the complete activation sequence shall be performed again. This may take a while and limit the use cases to switch between two logical UICCs.

From the reader terminal for example mobile phone PDA or tablet point of view this solution is natural as the UICC is a removable device the UICC could have been removed and a new one could have been inserted. Modification of the UICC behaviour after the reset is normal. From the logical UICC point of the view the Operating System is executed started from a Reset and this is the normal behaviour.

The present improvement is a way to modify dynamically the contexts of 2 and 3 but avoid the initialization of volatile contexts.

The improvement proposes a method for switching between a first and a second logical UICCs comprised in a same physical UICC. In order to perform the switch specific areas are defined to manage the overlapped volatile data and overlapped persistent data. each logical UICC comprising an area for storing overlapped volatile data and an area for storing overlapped persistent data. The physical UICC comprises also an OS area comprising in operation during the logical UICC execution time the overlapped volatile data and overlapped persistent data.

According to this improvement the method consists in when a switch order is received to switch from the first logical UICC to the second logical UICC 

i backup overlapped volatile data from OS area of the physical UICC to the area for storing overlapped volatile data of the first logical UICC

ii backup overlapped persistent data from OS area of the physical UICC to the area for storing overlapped persistent data of the first logical UICC

iii restore volatile data from the area for storing overlapped volatile data from the second logical UICC to the OS area for storing overlapped volatile data of the physical UICC

iv restore persistent data from the area for storing overlapped persistent data from the second logical UICC to the OS area for storing overlapped persistent data of the physical UICC.

Thanks to this improvement from the reader terminal point of view there is no change of UICC card. There is also no need to perform the activation sequence after the switch between the logical UICCs.

The improvement will be better understood by reading the following description of the which represents a physical UICC comprising two logical UICCs between which a switch is performed.

The switch is performed thanks to a new design of 2 where the volatile contexts are backed up and restored from to persistent smartcard storage each time a warm switch is requested. Those persistent data are nevertheless cleared upon physical reset.

This switch operation can be performed each time an APDU is received. This APDU consists in a switch order to switch from the first logical UICC UICC 1 to the second logical UICC UICC 2 . The UICC can be asked to switch from one logical UICC to another by several mechanisms. It may be a specific APDU command an information set through the logical channel byte or any electric signal on the terminal UICC interface usage of a specific connector . The switch can also be automatic.

This mechanism can be entirely hidden from the reader reader has no knowledge of logical UICC switch .

Thanks to this improvement it is easy fast and transparent for end user and terminal to switch from one logical UICC providing some services to another one providing other services.

The physical UICC allows the end user to connect to two different radio networks e.g. UMTS or CDMA networks for example one network in France and the other one in USA. Usage of the improvement allows benefiting from the banking services whatever MNO is selected.

The method according to the present improvement proposes to switch between logical UICC 1 and logical UICC 2. This switch can be automatically done for example in view of the MNO used by a calling party. If the logical UICC currently used is UICC 1 and the calling party s MNO is the second operator it is advantageous for avoiding roaming costs to switch to UICC 2. For that an APDU is sent from the terminal enclosing the physical UICC removable or not to this physical UICC.

In this figure logical UICC 1 and logical UICC 2 are comprised on a physical UICC. Each logical UICC comprises an area for storing volatile data and an area for storing persistent data. The physical UICC comprises also an OS area comprising in operation volatile and persistent data. When a switch order is received to switch from the first logical UICC UICC 1 to the second logical UICC UICC 2 following steps are performed 

The tenth improvement concerns a way to notify an application executed on a UICC that it is going to be removed and exported out of the UICC for example to be installed in another UICC whether directly or through a host server .

The invention takes place in an environment where subscriptions and related applications can be downloaded on UICC cards with a remote provisioning system.

On these UICC cards different application could be installed and managed by the current MNO or by a third party e.g. Transport or Banking application .

There is a need to move all data from a UICC card to another UICC card and in particular the data of MNO and third party applications.

This invention concerns a method applicable to Javacard applications to be exported with the corresponding data from a UICC removable or embedded to a host this host being for example another UICC.

The invention proposes a method for exporting data of a Javacard application stored in a UICC to a host the method consisting in 

The host can be a remote server to which the pack is exported for being downloaded later for example on another UICC.

The host can also be another UICC. In this case the pack is directly transferred from a first UICC to a second UICC without intermediate.

The export can be managed by the host the host retrieves the pack of data or by the UICC the UICC sends the pack of data .

The invention also proposes a method for importing a pack of data of a Javacard application stored in a host to a UICC the method consisting in 

An application programming interface API is an interface implemented by a software program that enables it to interact with other software. It facilitates interaction between different software programs similar to the way the user interface facilitates interaction between humans and computers.

The invention proposes to define a new Export Import Javacard API that can be used by any applications based on the Javacard standards APIs. This new Export Import Javacard API comprises at least one entry point to inform an application it should export its data and one entry point to inform an application that data have to be imported and which data. These entry points are invoked by the Operating System of the UICC if they are implemented by an application. An application implementing this new API can be deployed on any Javacard compliant UICC providing this API independently of the card manufacturer ensuring an easy interoperability. The entry point for export corresponds to a function of exporting the data of an application stored in a UICC this UICC being for example embedded not removable in a terminal for example a mobile terminal or a machine. The mobile terminal is for example a mobile phone. It is then possible to transfer data of an application from a first UICC to a second UICC the second UICC comprising the same application than the first one. The second UICC will then be able to work with this application in the same environment than the first one i.e. with the same data. The first and second UICC do not need to be of same UICC manufacturer.

When triggered by this event the application takes necessary action to back up inform or what it need with a remote server to keep the portability of the confidential user data associated to the application. e.g. back up electronic purse credit .

When the data shall be moved from one UICC card to another all applications on UICC implementing this API are preferably notified that it is going to be deleted from this UICC card and exported for example on another one .

The method for exporting data of a Javacard application stored in a UICC to a host consists firstly in transmitting a transfer order to this application through a Javacard API. The transmission of this order can be done by the OS of the UICC for example after a user s action in a menu of the GUI of the terminal.

The application itself then formats a pack of the data linked to this application. The pack is then ready to be exported to a host for example to a remote server via an IP or link. The pack can also be directly transferred to another UICC for example via NFC or Bluetooth.

The host can take the initiative to retrieve the pack from the UICC or the UICC can itself decide to export the pack of data.

Once installed in the host the exported pack can be retrieved to be installed on another UICC. In this respect the invention proposes to transmit an import order of the data to the same application through an Export Import Javacard API the application being located on the UICC and to unpack the data the unpacking being realized by the application .

Since the application that has realized the formatting of the data pack in the first UICC is the same than the application in the second UICC that unpacks the data pack the same environment is obtained at the level of the second UICC.

Once exported the data and the application on the first UICC are deleted in order to avoid a duplication of the application and the data.

Thanks to the invention as notified an application or all the applications embedded in a UICC will be able to backup user confidential and portable data to a remote server.

The invention is preferably applied to embedded UICCs for example in order to transfer data of an application e.g. a banking application from a first UICC comprised in a first terminal to a second UICC comprised in a second terminal. The banking application is already installed in the second UICC when the transfer of data to this second UICC occurs or can be installed afterwards.

The eleventh improvement concerns a method for remotely delivering a full subscription profile to a UICC over IP. More precisely the improvement concerns the delivery of a full subscription profile including File System Security Domains Applications STK USIM ISM . . . unique data like Ki applicative keys . . . to a UICC embedded in a device using an HTTP transport OTI or OTA.

The improvement proposes to solve the following problem. Once a UICC is attached to a receiving device for instance soldered or simply not physically removable because of the device form factor or because not economically viable distance . . . or when the device has to be commercialized without any attachment to a particular subscription in order to give to the end user the possibility to choose separately the device and the subscription it is no longer possible to personalize the UICC at manufacturing stage with subscription profile.

The improvement proposes a way to perform the personalization of a UICC remotely in a very secure way when the UICC is already deployed on the market without low expectations regarding device functionalities IP connectivity only . The MNO profile has to be downloaded via OTA or OTI since the UICC is already in the field.

More precisely the improvement proposes a method for remotely delivering a full subscription profile to a UICC over IP the UICC being installed in a terminal able to provide an IP connectivity to a remote server and give access to the UICC. The UICC is pre personalised with a unique serial number and with a bootstrap application and bootstrap credentials allowing establishing a secure transport channel with the remote server. The remote server hosts a stock of subscription profiles and acts as a web server. According to the improvement the method consists in 

The present improvement will be better understood by reading the following description in relation to that describes the overall overflow of an embodiment of the improvement.

At the beginning of the sequence we assume that the subscription profile for the UICC has been determined and reserved in the Delivery server.

HTTP protocol is preferably used for communicating with the delivery server and BIP protocol for the communications between the UICC and the device.

The twelfth improvement concerns a centralized service that can notably be used for lost or stolen mobile devices.

This improvement aims to simplify procedures for a user that has lost his mobile phone and who has multiple subscriptions on the UICC it contains. The UICC can be removable or not.

Today it is more and more common for a user to have multiple telecommunications subscriptions available on his mobile. Several examples can be mentioned 

With several subscriptions in his UICC it is a burden for the user to call all hotlines from different operators to block all his subscriptions if his mobile device has been stolen or lost.

In addition as in the Brazilian case the user may not even know or have forgotten the activated subscriptions from all the pre loaded subscriptions on his device.

The improvement proposes to provide a unique centralized service for lost and stolen mobile phones that will be able to perform an action on mobile device on the user s behalf.

The improvement proposes a system for managing multiple subscriptions in a UICC the system comprising a central server able to manage subscriptions stored on a UICC comprised in a mobile terminal in the field at the request of a subscriber of one of these subscriptions.

The improvement proposes a system for managing multiple subscriptions in a UICC the system comprising a central server able to manage subscriptions stored on a UICC comprised in a mobile terminal in the field.

In a central server manages subscriptions stored in a UICC comprised in a terminal . The central server manages these subscriptions through a network for example Internet. Central server is connected to different telecommunication networks of operators MNO1 to MNO3.

In another configuration of the system represented in the central server is connected to a single operator s network MNO and communicates with the other networks MNO1 to MNO3 through this network MNO.

Central server can act as a manager of the subscriptions present on UICC . He can for example install a new subscription on the UICC at the request of the user of terminal .

The system according to this improvement allows a user that has lost his terminal to contact a single entity the central server in order to ask to this entity to manage its subscriptions. Such a management of subscriptions can for example consist in 

In order to contact the central server the user can contact directly the central server as shown in . He can contact the server by fax phone or over the Internet. Since the server knows which subscriptions have been installed on the lost stolen UICC it will be able to take the appropriate actions at the request of the user.

An alternative for the user is to contact one of his MNOs who will warn the central server . The latter will take the appropriate actions.

Alternatively as shown in the central server may try to send a short message to a specific application located in the UICC that will directly perform the action on the UICC instead of performing it in all the networks. As the central server may not be aware of the currently active subscription and the associated MSISDN it will try to reach the UICC with all the potential MSISDN

A third alternative depicted in would be to reach the UICC via another network than a 2G 3G one like Wi Fi or even a wired network. In this case the central server will try to reach an agent on the terminal that will forward the messages to the UICC and perform actions.

The main advantage of the improvement is that it provides a convenient and fast way to block all subscriptions related to lost or stolen mobile terminals.

The thirteenth improvement concerns simlock and applies to UICCs that are not removable from terminals embedded UICCs for example mobile terminals.

Mobile network operators MNOs often propose cheap mobile terminals to their subscribers and they do not want them to take subscriptions from other operators at least for a given period of time after they have bought a new terminal. Therefore operators lock new sold mobile terminals to their network to be sure that they will only work on their networks thanks to UICCs belonging to these operators.

It is however easy for an unfaithful user to desimlock his mobile terminal. Some shops propose for small amounts of money to desimlock recently bought mobile terminals. The desimlocked terminal can then be used on the network of another operator. This represents an important loss of money for the mobile operators since they have sold the terminals with an important discount price in exchange of the fidelity of their subscribers.

The present improvement is in particular applicable to mobile terminals comprising an embedded UICC not removable which can store at least two subscriptions one for a MNO 1 primary MNO who has sold the terminal and another one let s say for a MNO 2. MNO 1 who has locked the terminal on his network does not want that the user installs another subscription from another operator on his UICC. This would permit to the user to use his mobile terminal with this other subscription with MNO 2 instead with the subscription with MNO 1.

The present improvement proposes a method for downloading a subscription from an operator to a UICC embedded in a terminal the method consisting in 

The verification preferably consists in comparing the identifier with a list of subscriptions for which a download is authorized.

The present improvement will be better understood in reference to which represents a system according to the present invention.

The system of is similar to the system of already described in which a central server constituted by a platform manages subscriptions stored in a UICC comprised in a terminal . The central server manages these subscriptions through a network for example Internet. Central server is connected to different telecommunication networks not represented of operators or to a single operator s network and communicates with the other networks through this network.

Central server can act as a manager of the subscriptions present on UICC . He can for example install a new subscription on the UICC at the request of the user of terminal .

According to this improvement in order to download a subscription in the UICC the terminal sends a request for downloading the subscription to the central server this request comprising an identifier of the terminal or an identifier of the UICC . The central server comprises a list of all the identifiers of the terminals or UICC that can be managed by this server .

The list comprises for each identifier here the IMEI of the terminal corresponding rights R. To an identifier IMEI1 are associated rights R1. The server verifies that a terminal UICC making such a request for downloading a subscription has the right to download this subscription. If the rights are confirmed the subscription is downloaded to the UICC. If the rights are not allowed the subscription is not downloaded.

The UICC can comprise a bootstrap subscription allowing a first connexion to the server in order to download a real subscription afterwards.

Normally the sold UICC already comprises a subscription to a first MNO and is locked to this operator. The operator can inform the central server when locking is no more necessary and the list is then updated in order to allow the customer to download another subscription.

Instead of verifying the rights associated to a terminal the rights associated to a UICC can be checked.

Like described in regard to the UICC reference can be used for securing the channel between the terminal and the server .

The server can be managed by a unique entity like for example a card manufacturer who knows what is stored on each card.


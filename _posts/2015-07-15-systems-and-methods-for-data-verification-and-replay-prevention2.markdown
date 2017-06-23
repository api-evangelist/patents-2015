---

title: Systems and methods for data verification and replay prevention
abstract: A system and method are provided for the secure sharing of information stored using cloud storage services and for performing data verification and replay protection for information stored on an open network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09639711&OS=09639711&RS=09639711
owner: PKWARE, Inc.
number: 09639711
owner_city: Milwaukee
owner_country: US
publication_date: 20150715
---
The present application is a continuation of U.S. patent application Ser. No. 14 015 325 filed Aug. 30 2013 entitled Systems and Methods for Data Verification and Replay Prevention which claims the benefit of U.S. Provisional Patent Application No. 61 695 972 filed Aug. 31 2012 entitled System and Method for Data Verification and Replay Prevention on an Open Network both of which are hereby incorporated by reference in their entirety.

The present invention generally relates to computerized data security and verification systems and methods. More particularly the present invention relates to such systems and methods operating over a third party cloud based storage application.

The cloud is a new model for distributed computing. The National Institute of Standards and Technology NIST defines cloud computing in the document titled The NIST Definition of Cloud Computing NIST Special Publication 800 145 September 2011 as a model for enabling ubiquitous convenient on demand network access to a shared pool of configurable computing resources e.g. networks servers storage applications and services that may be rapidly provisioned and released with minimal management effort or service provider interaction. 

Increasingly electronic information that has been previously stored on local or network connected computing systems is moving to cloud storage systems. In addition to this movement of existing information to the cloud users are creating vast amounts of new information placed directly into cloud storage. These cloud storage systems include information storage that is provided by service or storage providers such as Dropbox Box SugarSync and the Microsoft Skydrive service. Other sources and providers of cloud storage exist.

Users of these services are provided authorized access to this storage after obtaining a subscription or membership offered to them by a storage provider. Alternatively membership may be obtained in other ways. Upon obtaining a membership a user becomes a member. Storage is then accessible to members through the internet. However the storage available through the internet is provided on an open network unprotected by the traditional perimeter defenses such as corporate firewalls SSL connections and access authentication mechanisms that may be used to protect local or network connected storage systems.

These open network storage systems provide only limited protections to users regarding the confidentiality or integrity of their information that they place onto these storage systems. For example some storage systems may provide no protections at all. Further this information is often shared between multiple users that have all been granted membership access to the same stored information giving rise to further security concerns.

Common methods in use today to protect access to information stored on open networks include basic authentication which relies on a user ID and password or methods such as Oauth as presented by the OAuth group www.oauth.net or OpenID as presented by the OpenID Foundation www.openid.net . These methods may authenticate user and application identities but they do not directly authenticate user data files.

Other methods for information protection available today may provide some limited protections for the information stored on open networks. Some examples of other methods currently deployed are digital timestamps digital signatures or file and folder access permissions as may be in use today. For example digital timestamps provide a way for determining the content of a file at a point in time. This method requires an available timestamping authority TSA or server to provide the digital timestamp. This method has a high degree of complexity and requires sufficient timestamp infrastructure to implement.

Digital signatures may provide a record of who applied a signature to a file but digital signatures do not provide a way for establishing a time sequence or chronology and therefore may not maintain integrity over a time interval. Additional ways of protecting information such as setting file and folder access permissions may prevent access to a file on an open network but today these methods may often be circumvented and they do not provide any way for data integrity or prevention of replay attacks.

Using these available methods users must place their information onto these cloud storage systems at their own risk with no certainty that their information will not be intercepted or altered by unauthorized users. In the event that this information is improperly accessed or altered in an unauthorized manner the authorized users of this information may never detect that this information has been improperly accessed or altered.

In some instances encryption may be available to these users from the storage provider by their own methods or through other methods available to them for protecting information. This encryption may be applied to the files and other information placed into the cloud. However the use of encryption which makes information unreadable without the use of an electronic key may not ensure that data has not been inappropriately accessed or altered. Electronic keys protecting encrypted information may be intercepted or in some cases even guessed allowing unauthorized users to access information they are not otherwise allowed to access.

Once this unauthorized access is obtained the information may be used inappropriately altered and even re encrypted by the unauthorized user without the knowledge of the authorized users. This may lead the authorized users to come to rely on this altered information as if it was correct when actually it is not.

Further the use of encryption does not prevent an unscrupulous member who is allowed access to information stored in the cloud from disregarding any rules established for accessing this stored information. The unscrupulous user may properly access this information but then improperly use or alter this information to harm or deceive the other authorized members using and relying on the information.

Members accessing information stored in the cloud may not all be granted the same level of access to the shared storage. Shared open network storage may be owned or managed by one or more members who are authorized to manage this information. A manager may also be referred to as a moderator. The moderator may accept approve or deny changes made to shared information by other members. The moderator may allow or deny other members access to shared information. Other members may be granted less or different access such as they may be able to read or copy information in or about the shared information storage but they may not be allowed to decrypt or alter it although they may copy and use that information in another private space that is separate from the shared access of the other members.

This type of access provides ways for an unscrupulous user to access appropriately validated information which they may copy to a private storage location that is not part of the shared member storage. The information may be considered valid for a defined period or interval of time after which the information is no longer to be considered valid. The unscrupulous user may attempt to present the data at a later time under the pretense that it is still valid data. Users unable to make a determination that the information should no longer be considered valid may mistakenly accept the data as still valid when in fact it should not be. This type of misrepresentation is referred to as a replay attack.

With regard to the operation of current cloud hosting or storage services we will use as an example Dropbox as provided by Dropbox Inc. Dropbox is a cloud file storage service offered to users through a membership service. A user becomes a member by joining the service. Membership levels are provided at no cost. Additional membership levels are available and may require payment.

Upon membership a new member is able to place files into the cloud storage provided to members. Members may create folders using familiar application programs such as the Microsoft Windows Explorer file manager. Files may be created and placed into these folders. These files and folders may then be accessible to a member from any device connected to the Dropbox storage for that member.

A capability of Dropbox storage is that file and folder access may be synchronized for almost immediate access from any of a members devices that may access Dropbox. A member may for example place a file into a folder within the Dropbox storage from the interface of a personal or laptop computer. That member may then access that file from a smart phone or tablet without having to perform a specific transfer operation using alternative methods including transfer programs such providing file transfer FTP or email Microsoft Outlook or that may require using physical media such as a USB or portable flash drive.

Using the Dropbox interface a member may designate that a folder be accessible to other members for purposes such as information exchange or collaboration. Making a folder accessible to other members provides a method for sharing information with members. A folder may be shared with many members. A limitation of products such as Dropbox is that any member may share a folder with any other member in such a way that not all members may know who has access to shared information. A member is unable to moderate access to shared information.

Sharing of information allows other members to receive access to folders to be shared. Sharing is initiated by a member by selecting or specifying other members who may access files or folders identified for sharing. Sharing selections may be made using the information displayed to a member within the user interface provided by Dropbox. A member may select that information not be shared.

A first user that shares a folder with a second member may not be aware that the second member is sharing that same folder with a third member. The first member may have intended for the information to be shared only with the second member. However the first member may not prevent the third member from accessing the folder once the second member has shared the folder.

Information placed within the Dropbox storage may be encrypted by the Dropbox system. Files placed within Dropbox folders transfer across the open network through a secure network channel established by the Dropbox environment. This secure channel is implemented using the SSL protocol. This protocol may protect the files only as they move across the network connection between a member device and the Dropbox storage.

Protection is also provided for files while they are stored within the Dropbox storage. They are encrypted within the Dropbox storage using an encryption key maintained by Dropbox. This encryption key may be known by a member. This encryption key is also known by Dropbox Inc.

A limitation of this protection is that a member no longer has sufficient control of their data even though it is encrypted within Dropbox storage. A breach of a Dropbox system that allows unauthorized access to encryption keys used to encrypt member information or a malicious act by a Dropbox staff member that gains access to an encryption key protecting a member file may place the information of a member at risk of unauthorized exposure.

One or more embodiments of the present invention provide systems and methods to improve upon the secure sharing of information stored using cloud storage services by providing a system and method of data verification and replay protection for information stored on an open network. An exemplary embodiment using the Dropbox cloud storage service is presented below but the present systems and methods may be performed on any cloud storage or hosting services such as Box SugarSync and the Microsoft Skydrive service for example.

As further discussed below one or more embodiments of the present invention provide benefits such as greater security and improved secure file sharing for information stored in the cloud security through data integrity and data replay prevention security for information stored in the cloud when none may otherwise be provided security for information shared in the cloud when none may otherwise be provided security for files on a device security for files used with cloud storage applications security for files using a method of secure folder replication secure sharing of files on an open network from user devices and secure sharing of files on local devices and file storage.

At the start of the User A setup section at step User A joins Dropbox. Next at step User A installs the SFRS on their computer. Next at step the SFRS creates a public key PID for User A. Then at step the SFRS creates a private key SID for User A. At step User A provides the SFRS with a password for User A. Next at step the SFRS encrypts User A s PID and SID using the User A password.

Then at step the SFRS creates cloud and local .SFRS folders for User A. In one embodiment the cloud folder may be created on the Dropbox. Additionally the file extension .SFRS is indicates a file formatted by the SFRS and with a file name suffix established by the SFRS. The actual file name suffix may be something other than .SFRS such as in one example .VIIVO for example.

Next at step the SFRS places User A s PID into a PIDFile and places User A s encrypted PID and SID into a SID File. Then at step the SFRS places the PIDFile and SIDFile into User A s local and cloud SFRS folders. User A has now been set up to use the SFRS and the SFRS is ready to receive and securely store files chosen by User A.

Turning now to the User B setup section the User B setup section proceeds generally similarly to the User A Setup section . First User B joins Dropbox at step . Next at step User B installs the SFRS on their computer. Next at step the SFRS creates a public key PID for User B. Then at step the SFRS creates a private key SID for User B. At step User B provides the SFRS with a password for User B. Next at step the SFRS encrypts User B s PID and SID using the User B password.

Then at step the SFRS creates cloud and local .SFRS folders for User B. In one embodiment the cloud folder may be created on the Dropbox. Additionally the file extension .SFRS is indicates a file formatted by the SFRS and with a file name suffix established by the SFRS. The actual file name suffix may be something other than .SFRS such as in one example .VIIVO for example.

Next at step the SFRS places User B s PID into a PIDFile and places User B s encrypted PID and SID into a SID File. Then at step the SFRS places the PIDFile and SIDFile into User B s local and cloud SFRS folders. User B has now been set up to use the SFRS and the SFRS is ready to receive and securely store files chosen by User B.

Turning now to the User A sharing section User A now wants to securely share a file with User B using the SFRS. First at step User A creates a folder using the SFRS. The folder is indicated as a shared folder because User A desires to share the contents of the folder with User B. At step the SFRS creates a Session Key SK for the shared folder. The SFRS also created a PIDList file with PID information for User A.

Then at step User A places an unencrypted file to share with User B into the shared folder. At step the SFRS encrypts the file from User A using the SK to form an encrypted file. Then at step then encrypted file is transferred to Dropbox and Dropbox copies the encrypted file to Dropbox cloud storage.

Next at step User A shares the shared folder with User B using the folder sharing controls provided by Dropbox. Additionally At step the SFRS sends a share invitation to User B.

Turning now to the User B sharing section at step User B accepts the invitation made by the SFRS in step . Then at step the SFRS retrieves User B s PID information for example from User B s PIDfile that was stored on the Dropbox application in step . The SFRS then places the User B PID information into a PIDList file for the shared folder.

Next at step the SFRS encrypts the SK for the folder using User B s PID and places a SK file for User B in User B s SFRS folders. Then at step the SFRS performs verify and replay prevention on metadata as further described below.

Then at step User B attempts to open the file placed into the shared folder by User A. In response the SFRS decrypts the SK using the SID of User B at step . Then at step the SFRS decrypts User A s file using the decrypted SK and places the decrypted file into the SFRS folder of User B. Finally at step User B accesses an unencrypted version of the file shared by User A.

As further discussed herein the SFRS may be implemented within an application app running on one or more computing devices of members using Dropbox. One example of such an application is a SFRS application that may alternatively be referenced using the product name VIIVO. The SFRS provides a system and method for at least one user to protect files on at least one device of the user. Users of SFRS are subscribers or members of the Dropbox cloud storage service.

A first user User A becomes a member of Dropbox. A second user User B is also a member of Dropbox. Both User A and User B install Dropbox onto each device in their possession that may be be used with the Dropbox service. Both User A and User then install the software for the SFRS application. The SFRS application during installation for each user creates an encryption and decryption key pair for the user. A key pair may be a public private key pair following the X.509 digital certificate standard. This standard defines a public key that is used during encryption operations on data and a private key that is used during decryption operations. A public key PID may also be used for authentication operations such as verifying a digital signature associated to a data file. A private key SID may also be used for operations of creating a digital signature associated to a data file.

Upon creation of a key pair for a user the SFRS places the key pair into metadata files. Metadata files holding user keys are used within the operations performed by SFRS on behalf of a user when data encryption and data decryption occurs.

The SFRS prompts a user using a dialog provided through a user interface. The prompt then asks the user for a password. The SFRS application uses this password from the user to encrypt the users PID and SID into an encrypted SID file that are placed into the users SFRS folder s .

The SFRS places the users PID into a PID file that are placed into the users SFRS folder. In addition to creating a user s key pair the SFRS application locates the user s dropbox software. Metadata files are copied by the SFRS to the user s dropbox folder. SFRS then monitors the user s dropbox. A user may repeat the above operations on additional devices in the user s possession that are to be protected by the SFRS.

In one embodiment a file to be placed into a user s dropbox folder may alternatively be placed by a user into their SFRS folder. Files may be placed using any methods available including copy move save or create a file. Files within a user s SFRS folder are detected by monitoring the SFRS folder. Upon detection the SFRS encrypts a copy of a file using a user s PID and place the encrypted copy into the users dropbox folder. Files within a user s dropbox folder are also detected using monitoring. Upon detection SFRS places a decrypted copy of the file into the users SFRS folder.

A user s files placed into the user s dropbox folder using SFRS are preferably encrypted within the dropbox cloud storage. Additionally as described herein files may be securely shared between one or more dropbox users. SFRS encrypts a file using a PID for each user allowed shared access. The SFRS uses a verification check workflow and replay prevention method to protect shared information from unauthorized use or access.

As an example the SFRS operates on a computing platform of at least one member using Dropbox. The SFRS application monitors the information files shared by a member and between members using Dropbox and encrypts and decrypts each file for a member using an encryption key for the member. Monitoring may occur using a method of polling which inspects the contents of a folder or other location at defined intervals of time. Other methods of monitoring may be used.

A user of the SFRS application may interact with files resources R using any of a number of workflows described below. These files contain data of at least one user of the system. A user may perform the verification workflow or the replay check workflow when interacting with the files resources R of this system. The SFRS may perform the verification workflow or the replay check workflow when interacting with the files resources R of this system on behalf of a user of the system. The order of the workflows and the steps within a workflow may be altered from those presented here.

One embodiment of the present invention preferably includes at least one configurable folder that is monitored by the application software SFRS . Such folder has a parallel folder maintained within the sharing service one example is Dropbox this is identified as a cloud replicated folder. A cloud replicated folder is a folder provided and maintained by Dropbox storage.

In one embodiment the SFRS software is such that the cloud replicated folder s contain at least one encrypted file and the monitored folder s managed by SFRS contain the decrypted copy or copies of the file s . This file encryption and decryption occurs within the SFRS software application and it appears to members as though the encryption and decryption occur automatically and they are inconvenienced as little as possible when attempting to use their files.

At least one example may be if a member may use a standard file operation such as drag and drop to drag a file into or alternatively directly writes a file into a monitored folder the SFRS software application of the current embodiment compresses and encrypts the file and places it in the corresponding cloud replicated Dropbox folder. This functionality operates differently from Dropbox in that Dropbox may encrypt and copy the file to the Dropbox cloud storage wherein one embodiment of the present invention may encrypt and copy to the user s local Dropbox folder. A benefit is the file is encrypted on the user s device using a key of the user before it is delivered to cloud storage and from there to other devices or to other users.

The encrypted format may be any encryption format. One example is the encrypted .ZIP format created using the SecureZIP software from the assignee of the present invention. Other encrypted formats may be used.

The SFRS extends the existing capabilities of Dropbox by offering transparent and secure access to encrypted shares using file tunnels.

Installing SFRS creates a new SFRS folder in the user s Dropbox and on the user s workstation thus building a tunnel. This SFRS folder may be named VIIVO. This SFRS folder may be a folder within a root of the users file view or it may be placed within another folder such as may be provided by the operating system on which SFRS is operating. For example on a device or computing platform using the Microsoft Windows operating system this folder may be located under the users AppData or AppData Roaming folder.

Adding files folders to the local end of SFRS tunnel automatically encrypts them with the user s unique encryption key and then uploads the secured data to the Dropbox storage at the same time the encrypted content from the cloud is automatically downloaded decrypted and instantly available in the local SFRS folder. The encryption decryption and data synchronization tasks are performed in the background making access to secure data nearly transparent for the users.

In addition to personal encryption the SFRS also allows the users to secure new and existing Dropbox shares by encrypting shared data so that it s only accessible by a selected subset of SFRS users or members.

Secure sharing with SFRS is easy and straightforward the users do not need to remember passwords or manage encryption certificates. Shared data is encrypted decrypted with a unique symmetric key session key for each share automatically generated by the SFRS copy of share owner and securely distributed to the SFRS instances of share participants. With the session key available all share members are able to access encrypted data transparently using the SFRS tunnel folder on their workstations.

The SFRS architecture is cloud based and encryption decryption tasks are performed by the client applications on a member device. The application metadata including but not limited to user account details keys PID SID SMOD OK ID .MOD SK JSON are stored in the hidden folders in one example .VIIVO within the user s Dropbox storage. Cross client communication is performed using the Dropbox shares. Metadata files may reside in or be replicated between any of the folders managed by Dropbox or the SFRS.

The SFRS application utilizes the Dropbox application for synchronization of encrypted data with cloud folder and may use the Dropbox API an application programming interface provided by Dropbox for metadata manipulations. Encryption or decryption operations of data and metadata may be performed using another API providing encryption such as the SecureZIP SDK by the assignee of the present invention or using the open source API such as is available from www.openssl.org.

SFRS Tunnel The SFRS tunnel may be pair of SFRS folders including a cloud end or outside of the tunnel and a local end or device side of the tunnel. The cloud end may be a SFRS folder in the root of a user s Dropbox and stores the encrypted files. The local end may be a SFRS folder on the user s device and contains the files already decrypted by SFRS. The SFRS provides secure storage and sharing for files and folders within the tunnel and folders outside of it are ignored. As a result the tunnel includes both the user s private content folders and any Dropbox shares secured by SFRS.

Session Key or SK The SK may be a symmetric or asymmetric key used to encrypt decrypt data. The SFRS may use two types of SKs the Private SK and the Folder SK. The Private SK is a key that may be used to encrypt unshared data in a SFRS tunnel and may be unique for each user. The Folder SK is a key used to encrypt the data within a shared folder and may be unique for each shared folder.

Shared folder The shared folder or the SFRS share may be a shared folder in Dropbox encrypted by SFRS. It may be read only subscribe only or read write. A share corresponds to a folder and sub folders it contains. The same settings and rules are applied to all sub folders within a share. Similar to Dropbox a share in SFRS maynot include other shares and may not be included in other shares.

Uninitialized share The uninitialized share may be a shared folder in Dropbox for which the sharing process is not yet complete and or for which folder metadata is not yet available.

Identity With regard to identity the SFRS identifies each user using a pair of keys unique to a user the PID the user s public key and the SID the user s private key. The SID PID key pair for a user is generated as the SFRS application is initialized on a user device. It is associated with the user s Dropbox account and may be stored in the user s cloud cache.

SID file The SID PID pair is stored in the cloud cache within an SID file. The SID file may be a password protected file containing the user s private and public key.

PID file The PID file may be the file containing the user s PID name e mail and other public information for the user.

Cloud cache The cloud cache may be a named folder with an extension unique to the SFRS application. One example is a folder having a in one example .VIIVO name extension located within the root of the user s Dropbox this folder is used to cache the user s account details including but not limited to SID PID SMOD SK OK ID .MOD and other information and metadata from the folders shared with the user in order to ensure synchronization of the metadata across the user s multiple client apps and prevent data loss during re installation.

Moderator The moderator is the user who has created the SFRS Share. The moderator s instance of SFRS generates the SK for the shared folder encrypts the data in the folder generates folder metadata required for sharing and then distributes the SK to the share participants. In one embodiment the moderator is the only person who may grant keys to the share and change share settings. In one embodiment the other share participants may only access the shared files read or read write depending on the folder s access level set by the moderator.

Folder Metadata Folder meta data may be at least one file of metadata generated by the moderator and used for secure sharing of the folder with SFRS. The folder metadata may include 

In one embodiment the folder metadata is located in a hidden in one example .VIIVO sub folder of the shared folder. This folder may also be a non hidden folder. In one embodiment folder metadata is created by SFRS and signed on behalf of the moderator. These metadata files are preferably not removed from the shared folder. If an event causes these files to be removed or damaged SFRS operation may block access to the folder until the metadata is restored by the actions of a moderator.

Share invitation The share action may be an action by or on behalf of the moderator of sharing a folder with at least one member. Shared information is secured by SFRS. A method of providing an invitation to a member to access the shared folder is provided. Sending an email is one example.

Unshare The unshared may be an action performed by or on behalf of a moderator of a share excluding all other users from the share. Unsharing may include re encrypting all data within the share using a private key.

Moderator lock The moderator lock may be a way for a moderator to prevent access to a shared folder thereby locking out other members for some duration. For example a moderator lock state may be achieved using a file designed as a lock file placed into a shared folder. The lock file may be placed by the moderator s SFRS application. A lock state may be placed by or on behalf of a moderator in order to eliminate synchronization conflicts during metadata updates or to limit access to shared folders during re encryption. A moderator lock may be used for other reasons when access to a shared folder may need to be prevented for some duration.

De verify PID Blacklisting The de verify PID blacklisting may be the act by any user of terminating all share relationship with any other user by adding the de verified user to the blacklist A blacklist may be established using a mechanism such as a file into which the name or other identity information of the de verified user is placed. Operations performed by the SFRS application check if a user is identified within the blacklist and if found the operation involving the blacklisted user is not performed.

The SFRS application folder includes one or more unencrypted files and a shared folder. The SFRS application folder communicates with the Dropbox application folder using a data tunnel .

The Dropbox application folder includes SFRS metadata including a SID for the user of the computer and the SK for non shared files which appear in the shared folder. Additionally the Dropbox application folder includes a Dropbox SFRS folder which contains one or more encrypted files.

The Dropbox application folder is preferably local to the user computer and operates as a pass through for the SFRS as described above. For example as described above the user may place a file in the SFRS application folder and the SFRS application automatically encrypts the file and passes it through the tunnel to the local Dropbox SFRS folder.

Additionally the contents of the Dropbox application folder are automatically passed through the standard Dropbox sync to the Dropbox computerized cloud based storage . The cloud based storage includes SFRS metadata folder including a SID for the folder and the SK for non shared filed. Additionally for the shared folder it includes the SK for the shared folder a PIDList and a SMOD file as described below. The SID may also be called a Secret Personal ID and may include the user s name e mail RSA public key and or RSA private key. Also the PIDList contains the PIDs of users who have access to the shared folder.

Also the cloud based storage includes a cloud SFRS folder . The cloud SFRS folder includes a shared folder . The shared folder includes a shared SFRS metadata folder . The cloud SFRS folder may include encrypted files. Additionally the shared folder may include a .dropbox file indicating that the folder is shared using Dropbox. Additionally the cloud SFRS folder may include encrypted files. The shared SFRS metadata folder includes a PIDList a SMOD file PIDs of the users having access to the encrypted files SKs for the users having access to the encrypted files an OK ID indicator and a .MOD file as described below.

The PIDs may be a personal ID that may include the user s name e mail and or RSA public key. Additionally the SK may be a symmetric key such a s PFX file for SecureZIP encryption. The SK may also be an asymmetric key 

As shown in and described further below the secure folder replication functions operate on the user s computer between the SFRS application folder and the Dropbox application folder .

User A s SFRS A receives decrypted files PID metadata SID and SK determined locally and provides the encrypted filed PID and metadata to the local dropbox folder which then passes them to the dropbox cloud storage . The Dropbox cloud storage includes the shared folder with the encrypted files.

User B operates similarly to User A. That is User B s SFRS B may receive decrypted files PID metadata SID and SK determined locally and provides the encrypted filed PID and metadata to the local dropbox folder which then passes them to the dropbox cloud storage .

Once User B has responded to User A s e mail preferably both User A s and User B s SFRSs may access the encrypted files stored at the dropbox cloud storage decrypt them and display the files for the respective user.

The GUI configuration manager in one embodiment is the component responsible for display of the configuration GUI components to the user. The GUI configuration manager communicates with the background process over named pipes to get set necessary data. Other types of inter process communication may be used including FIFO s. This component may not have direct access to metadata user data.

The synchronization daemon is responsible for handling encrypted user data and different encrypted metadata. The components of the synchronization daemon application are described in more detail below.

Logger The Logger may be accessed by other components of the background daemon and is responsible to output the logs of the user activities and SFRS activities not initiated by the user in the pre defined format. Several log levels are supported and in one embodiment logs are output unstructured in a plain text file.

Statistics Manager The statistics manager stores statistical data for different SFRS operations. It also implements API to enable queries for statistical data to be displayed in the SFRS UI.

Notification Storage The notification storage component is responsible for collection of notification information to be displayed to the user. Notifications stored in the notification manager may not be persistent and they may not survive daemon restart. After the daemon is restarted the necessary notifications may be regenerated based on the analysis of SFRS structures files for example.

Data Manager The data manager is a high level component for datafile operations performed by SFRS daemon. Using the data manager different user initiated operations may be started for example re encrypt or the status of background sync processes may be queried. The data manager may interact with the Metadata manager to perform its functions.

Folder Manager The folder manager is responsible for data file operations taking place within a particular folder. It interacts with the Folder Metadata manager to get access to the metadata related to a particular folder.

Sync Process The sync process implements logic of periodic sync between the inside and outside ends of SFRS tunnel.

Re encrypter The re encrypter is responsible for the initial encryption of the data in the SFRS folder and or on demand re encryption of the data.

Data Crypt with Temporary Storage The data crypt with temporary storage component is responsible for atomic encryption operations with the data saved in the temporary storage in the process of encryption. This component directly interacts with the SecureZIP SDK for data encryption.

Global User Manager The global user manager is a high level component for user management related operation and querying the global user related information. In one embodiment it has two subcomponents verification flow manager component responsible for the state machine logic of the PID verification workflow and the blacklist manager responsible for management of the folder unspecific PID blacklist .

Global Metadata Manager The global metadata manager is a high level component responsible for metadata modification operation and accessing data stored in the metadata files.

JSON serializer RSA Splitter Open SSL These are low level components responsible for storage of the metadata in the JSON format signing splitting of the metadata files into blocks corresponding to the used RSA key size and writing the encrypted data to the drive using openSSL. The reverse operations responsible for reading of encrypted metadata structures from drive are also implemented in these components.

Folder Metadata Manager The folder metadata manager is responsible for access and modifications of metadata associated with a particular folder including PIDLIST management.

Folder Initializer The folder initializer is responsible for initialization of the folder structures for the new folder.

Metadata Sync er with Access Locker and Dropbox API These components are responsible for metadata sync logic between cloud and local storages using the Dropbox API. This component also implements the logic for modification lock files.

Multiple members may have access to an open network resource over a given interval of time. A member may be a computer user or other entity using the open network resource. An example of an open network resource may be a file shared by members on a network such as the public internet. In one or more embodiments members introduce data into the resource at various subintervals and ensure that a the data presented is authentic and verifiable and that b it is not replayed from an earlier subinterval wherein the data from that interval is also verifiable.

This method is useful for instance in the case where time based directives are communicated to members over a shared resource and those directives while uniform may change over time. For example subsequent directives may overwrite directives from a previous subinterval although both directives are verifiable . Members may copy these directives out of the shared resource into a private space during any subinterval and replay them later.

An example of the use of directives may be but is not limited to encrypted data shared between some members of a network resource where the encrypted data indicates shared moderator events regarding the resource. All members of the resource may access the moderator packets at any time even non moderators but only moderators may decrypt the packet data. Any member may make copies of the moderator directives and could later replay the old directive in order to try and confuse moderation or perform an exploit. Using the method described below it may be ensured that no previous moderator event may be replayed in this manner.

The following example demonstrates one method in which arbitrary data is verified and protected against replay in a shared resource. In the example JSON is used for the data packet but this is only for convenience and illustrative purposes. This method may be applied to other data.

In addition to the data field a timestamp and signature field are added to the packet. The timestamp is based on epoch in this case but may be any valid date time format or even a simple incrementing counter. Other sequential values may be used. The signature field is preferably a Base64 encoded binary value but may be any valid binary authentication value.

The signature field is generated based on the data and timestamp fields using the member s private RSA key prior to placing the data into the shared resource. Receiving members may verify the data from signature using the sending member s public key.

Third using his private RSA key A generates the signature field based on data and t. For example signature RSA encrypt data t .

Fifth User B knows the public key for A and verifies data and t from the packet discovered in R. For example data t RSA decrypt signature .

The timestamp is used to employ a simple logic operation protecting against a replay attack. One example of a replay attack occurs when one user places old but still verifiable data into the shared resource. A second user may detect this attempt to reuse old data. After completing the verification step above the timestamp is compared against the second user s locally cached timestamp for that data. The timestamp must never be older than the locally cached timestamp.

First User B verifies data packet from user A in R and finds that it is authentic see Verification above 

Second B checks for a locally cached timestamp treferencing data. If tis not found B accepts the data from A and B writes timestamp t from the packet to locally cached t. Otherwise if tis found locally and is more recent than t from packet B rejects the data as a replay attack. That is tmust be 

Finally if verifies and most recent B accepts the data and writes t from data packet to locally cached t

The following workflow presents an alternate verification method using a password. This alternative method achieves the same result as that described above. For example this method may be used between a single member who has multiple devices accessing the shared resource and who does not care whether other members may verify against replay. An advantage of this method over the method above is that it just requires a one way hash function which may be more readily available than public private key encryption on some platforms. One example of a one way hash function that may be used is the Secure Hash Algorithm i.e. SHA 256 or SHA 512 published by the National Institute of Standards and Technology NIST .

Third using a one way hash A generates a signature based on t p and data. For example signature SHA256 t p data .

Fifth a receiving user knowing p may verify the data from the packet using the one way hash. For example signature from packet SHA256 t p data .

Sixth if the verification hash succeeds the receiving user may perform the replay check as described above.

More specifically illustrates the packet generation aspect of the verification workflow. As shown in a User A provides a packet such as a .JSON packet . The packet includes a data file a time value and a signature. The packet is then embedded in a resource for which verification is desired.

If tdoes exist tis then compared to the current time t. If tis less than earlier than the current time t then the data is again accepted at step . Conversely if the tis equal to or greater than the current time t then the data is rejected and access to the resource is not provided.

1. A user s identity in SFRS is linked to the user s Dropbox account only one SID key pair is stored in the user s Dropbox folder to add a new key the user first revokes the old one.

2. At first start up of SFRS the user creates a new identity a password protected SID file or imports the existing one e.g. from an existing file .

3. Once the identity is defined the application caches SID locally and does not require the user to import it again.

4. The SFRS may not cache SID password and may request the user to input it at every start up but the user is able to disable this check manually using the SFRS settings.

4. If the SID is not available in the local cache but found in the cloud Dropbox folder the application uses it from there see R1.4 .

5. If the SID is not available both in the local cache and in the cloud .SFRS in one example in one example. VIIVO root subfolder the app requests the user to either create a new SID key pair see R1.5 or to import SID key pair from a local file for example from a mounted USB drive see R1.6 .

2. The SFRS app asks the user to provide a SID password. The password may also be stored in the local secure key storage for the computing platform. On different platforms user may be requested to provide password to access the secure storage.

4. If the user fails to provide the correct password the application suggests the user to try again or login using a different Dropbox account.

3. User forgot SID password the user is asked to manually remove the SFRS folder from Dropbox leave all shared folders secured by SFRS and re install SFRS and generates a new SID.

4. Local SID does not match the shared encrypted metadata the SFRS app considers the remote SID to be invalid. The SFRS app re uploads the SID to the cloud.

1. After linking to a Dropbox account SFRS app notices the SID cached in the .SFRS in one example in one example .VIIVO folder in the user s Dropbox root folder.

2. The SFRS application welcomes the user back to SFRS downloads the SID key pair and asks the user to provide the password to access the SID file.

3. If the password is correct the SFRS application proceeds with its normal flow downloads the remaining metadata from SFRS cloud folder syncs the shares etc. 

4. If the password is invalid the SFRS application suggests the user to try again or log in under a different Dropbox account. Encrypted folders are not accessible.

3. SFRS gains access to the user s Dropbox folder and looks up the SFRS in one example in one example .VIIVO folder with cached metadata in it.

4. The existing SID is not found SFRS welcomes the new user to the SFRS app and suggests him her to generate the new key pair SID or import an existing one. The user decides to create a new key.

7. SFRS application creates the SFRS folder structure in the Dropbox uploads the SID to the .SFRS folder and displays the congratulations screen with basic instructions on how to use SFRS and on how to use and share files on the user s other devices.

1. During the first SFRS app run after fresh installation the user selects an option to import SID from the locally stored file.

3. The SFRS application loads the selected files and asks the user to provide a password for the decryption.

4. If password is correct the SFRS application accepts the key pair adds it to the local secure cache creates the SFRS folder structure in the Dropbox uploads the SID pair to the .SFRS in one example .VIIVO folder and may show a congratulations screen with basic instructions on how to use SFRS and how to extend the use of SFRS to the user s other devices.

1. Local copy of SID in the secure cache .SFRS in one example .VIIVO folder is linked to the user s Dropbox account and is removed when the user logs out of Dropbox or logs in again.

2. Disabling the SID password check at each start up requires the SID password. This is implemented by caching the password in the protected system storage keychain or similar . Logging in under a different dropbox account clears the cached SID password stored in the secure storage.

3. The SID key pair may not change except when revoked . The SFRS app may not track if local SID matches the copy in the cloud.

4. The user is able to export a SID file using a specific function from the UI of the desktop application.

6. SFRS monitors the SFRS tunnel if the folder becomes shared .dropbox file exists the application may stop encryption decryption and synchronization and may notify the user.

1. The SFRS may utilize one or more folders. As example three folders may be used to organize the user s data including metadata and may only work within these folders and their sub folders . Two of three folders create a pair which is called the tunnel and secure sharing may occur within this tunnel.

The SFRS may utilize a third folder to store the SFRS metadata. The SFRS in one example .VIIVO folder resides at the root of the user s dropbox account and contains only the metadata.

2. When the SFRS folder tunnel is initialized the content inside is private it is encrypted with one and the same private SK for all sub folders and may not be shared. Sharing any folder may require its re encryption with a new SK.

3. The user may be preventing from sharing the top most or root SFRS folder itself. It the application detects that a root SFRS VIIVO folder was shared the user may be warned and SFRS may not function.

4. Secure sharing of the SFRS subfolders occurs using Dropbox User Interface UI the SFRS provides the User Interface elements necessary to provide the secure sharing process for example to re encrypt the folder process access requests submitted PIDs etc.

5. The SFRS provides a UI to secure existing Dropbox shares shared folders located outside of the user s the SFRS folder .

3. The SFRS checks if it is possible to share the folder there are no shared parent or sub folders and places a .dropbox file in it.

4. The SFRS app notices that one of the sub folders in the SFRS folders becomes shared .dropbox exists and handles the share see below.

1. The SFRS starts and notices a new shared sub folder within the the SFRS tunnel. New uninitialized shared folders are identified according to the following conditions .dropbox file exists in the folder metadata PIDlist SMOD doesn t exist in the folder metadata PIDlist SMOD SK for this folder is not available in in one example .VIIVO cache.

NOTE the SFRS may choose to secure only the folders within the SFRS tunnel. Support may be provided to secure a Dropbox share folder which is outside the tunnel. The user may be required to move it inside the tunnel first see R2.5 .

2. The SFRS may assume that the user is a moderator and puts a tentative moderator lock in the new share see R2.8 below for details on the locking logic .

6. The SFRS creates public metadata for the folder the PIDlist SMOD and blacklist and stores them in the outside folder and in the .SFRS in one example. VIIVO folder.

7. Moderator or the SFRS app may apply verification check workflow and reply prevention method to files.

9. The SFRS proceeds with its normal workflow for example processes all submitted PID requests for this folder.

The SFRS UI allows the user to access the list of folders in the Dropbox and secure them with the SFRS.

1. When a the SFRS instance detects a new shared folder outside of the tunnel the SFRS may check if this folder has the SFRS metadata in it SMOD PIDLIST etc . If not the folder is ignored if yes it s treated as a new incoming share.

2. the SFRS submits its PID and obtains an SK file for the folder see also challenge response flow for additional details R6 .

3. the SFRS moves the shared folder from the user s Dropbox root to the SFRS folder and informs the user that sharing is complete and that decrypted files are now accessible from the tunnel.

1. Re encryption is performed over a temporary copy of original data. The original data both locally and in the cloud is replaced with the re encrypted data only after re encryption has been fully completed.

2. At re encryption start the SFRS uploads the specific marker of the re encryption operation to the folder being re encrypted to prevent data sync by other instances.

3. The application removes the marker file after re encrypted data is uploaded to the cloud or if the re encryption is cancelled.

4. In case if re encryption process gets interrupted app closed crashed lost connection etc the app may continue when it restores a working state and notices the marker file in the outside folder assuming no other moderators have stepped in. The app detects if another moderator device has taken over the process by detecting the presence of the expired moderator lock and the addition of newer moderator locks. If another moderator device has taken over the original moderator honors the new moderator and becomes a secondary moderator device monitoring the lock activity of the new moderator.

If the file exists the SFRS checks if the lock has expired. If it has not expired it may wait the predefined timeout then goes to Step . If the lock has expired the lock file is removed and then proceeds to Step .

If the file does not exist the SFRS tries uploading the lock file to the Dropbox folder using the Dropbox API. The lock file may have a pre defined name. Inside the lock file is stored the device ID.

When the file completes uploading the SFRS application on the device may re read the lock file information and confirm if its device ID has been stored. If not the lock is considered as not acquired. The suffixed lock files may then be removed.

3. Read only restriction may apply to all share participants but may not apply to the moderator. Moderators may continue to create update or delete files. Other users may be prevented from update or delete of files. Other users may still be allowed to create new files.

4. It is possible to change the folder s access level without the need to re encrypt the folder or re share it to users for example without generating new SK files .

5. Read only access level have effect within the SFRS share participants still retain full read write access to the folder using Dropbox and thus are able to delete any encrypted file from the cloud folder or update it.

2. Moderator changes the folder s access level from full or all allowed access to read only. Access may alternately be changed from read only to full or to another partial state of access.

3. Moderator s the SFRS app updates the SMOD file in the shared folder by changing the access level tag.

NOTE the moderator may also be able to set the folder s access level when creating a folder. This ability of a moderator may be set using an administrative setting such as a checkbox in a user interface such as provided by a sharing confirmation dialog.

1. Each time when accessing a shared folder during each meta data sync event the SFRS app reads its access level from the SMOD file.

2. If the folder s access level is read only the SFRS sets read only permissions for the folder s content in the local end of the tunnel the SFRS tunnel for the folder works one way the SFRS decrypts new file versions from the cloud and overwrite the local content but may not encrypt any changes to the local content and upload it to the cloud except for the new files .

Note 1 If the user creates a new file in a read only share it is copied to the cloud. The moderator may then choose to keep it or remove it. This feature allows users to submit edited or modified copies of documents and files for the moderator to determine whether to keep or remove the changes. The moderator or the SFRS app may apply the verification check workflow and reply prevention method to files to assist in the determination of whether to keep or remove user changes by establishing whether the files or documents were submitted using allowed procedures of the system or by circumvention by a malicious user.

3. If the folder s access level is read write the SFRS sets read write permissions for the folder s content in the local end of the tunnel the SFRS tunnel for the folder will work in normal two way mode.

2. Exclusion is implemented by removing the user s PID from the PIDlist and does not require re encryption.

5. The SFRS suggests the moderator to re encrypt the folder and proceeds with re encryption if confirmed.

6. The SFRS informs the moderator that the operation is complete and the moderator may now exclude or remove the user using Dropbox.

5. The SFRS suggests the moderator to re encrypt the folder and proceeds with re encryption if confirmed.

6. The SFRS informs the moderator that the operation is complete and the moderator may now unshare the folder using Dropbox.

2. The SFRS app automatically detected that one of the moderator s folders is no longer shared in Dropbox.

Note 1 when unsharing a folder the re encryption is performed with the user s private SK same as the one used for all other private content .

Note 2 after the folder is unshared using the SFRS but before it is unshared using Dropbox the user is not able to access the data in the folder.

Deleting a folder using the SFRS for example the folder is removed from the user s Dropbox cloud storage but each share member still has a copy of the folder. On mobile devices the user may not be able to remove the folder as a mobile device may provide only read only access.

A user may remove the folder from inside tunnel. the SFRS may detect this event and may warn the user that this may get the SFRS into inconsistent state. User has an option to restore the folder from outside tunnel or to unshare it before it is removed.

When the folder is removed from the outside tunnel the SFRS also detects that event but just warns the user about that event and with the instruction that other users having access to that folder should re share it again with the current user.

2. If the PID is not in the PID list the SFRS checks if the folder has been shared with it previously SK is available .

3. If the folder is a new one the SFRS proceeds with a standard flow for new shares. If the folder has been shared previously the SFRS understands that it has been excluded from it.

4. The SFRS informs the user that s he has been excluded from the folder and blocks access to it. The SFRS asks the user what s he would like to do a resend the PID invitation for that folder or b mark the folder as blocked 

1. The SFRS keeps track on the list of shared folders available to it compare the actual list of shared folders to the structure in the SFRS cloud cache .

2. In case if any of the shared folders are no longer accessible using Dropbox unshared or kicked out the SFRS removes all the metadata for such folders from both the local and cloud cache including the SKs and blocked markers . User is informed that if s he wants to restore access to that folder s he needs to request that folder to be re shared with her by the moderator.

1. Each the SFRS user is able to blacklist any other the SFRS user regardless of their roles moderator user .

2. When blacklisting a user the user is asked to repeat an identity verification first but this is done at the user s discretion. It is possible to blacklist a user without a check.

3. Blacklisting is global meaning that it applies to all the shares available to a user including future ones .

4. Blacklisting is reversible if user A mistakenly blacklisted user B there is an option to revert that.

5. In terms of this workflow user implies PID i.e. blacklisting is applied to a specific PID not all PIDs with a specific email or name.

6. There are two types of blacklist personal stored locally and in the user s the SFRS cloud cache and shared stored in the shared folder near the PIDlist . Having a PID in the personal blacklist causes the SFRS app to automatically reject share invitations and key requests from this PID. Having a PID in a shared folder s blacklist indicates that this PID is not able access this folder his the SFRS app does not let him even if he has SK.

7. The SFRS of the user A adds PID of the user B to the personal blacklist in the local cache and uploads it to the cloud cache .SFRS in one example .VIIVO folder.

1. Each time when a the SFRS app attempts accessing a shared folder during sync upon request when a new folder received etc. it looks up it s own PID in the blacklist.

2. If the PID is there the SFRS app shows a message to the user explaining that he got blacklisted and suggesting him to contact the moderator e mail provided .

3. The SFRS application blocks user s access to this folder stops syncing clears the local end of tunnel for this folder and removes all cached meta data for this folder both locally and from the cloud. Note Other folders than the SFRS folders remain accessible.

The SFRS app enables the user to see a list of blacklisted users and restore un blacklist them. When User A requests to un blacklist User B 

2. If confirmed the SFRS removes the PID of the user B from the A s personal blacklist both locally and in the cloud.

Note un blacklisting does not generate new SKs for the user or restore him in PIDlists or SMODs. The user preferably needs to request access to all shares again like for the first time.

1. In addition to the listed flows blacklisting is available as a part of the verification flow. It the counterpart fails verification the user is offered to blacklist it.

Every the SFRS application stores a users list of the known PIDs both locally and in the cloud cache folder.

If the PID is known no validation is required. Whenever any request is performed or when the operation requires collaboration with another user with the unknown PID the validation process preferably takes place.

Validation process represents the challenge response sequence with the communication carried through a shared Dropbox folder inside the SFRS tunnel in an encrypted form. Identity check is available.

3. User s the SFRS app notices a new shared folder the session keys for which are not yet available in the User s cache automatically uploads the user s PID file to the folder and waits for an SK or a challenge.

4. User s the SFRS app notices the new delegate with the unknown PID to be added to the earlier shared folder.

1. When moderator s delegate s the SFRS app finds a new PID file in the shared directory it retrieves the file and removes it from the shared folder.

2. The app checks if the PID owner is in the trusted list. If yes it automatically uploads an SK file for the PID to the folder and updates PIDlist. If not it displays a dialog with the PID owner details name email to the moderator delegate and asks if it should grant access block access or verify the identity.

3. If the moderator delegate requests an identity check the app asks him to fill in the challenge text and uploads this text to the shared folder. At this point the folder sharing process is suspended and may be automatically restarted when the challenge response authorization is completed.

4. The user s app finds a challenge request file retrieves it decrypts it and checks the signature. If signature is OK the app shows challenge text and sender details name email to the user.

6. The user fills in a response text for the challenge the app removes the challenge request file from the server and uploads a response file instead.

7. The moderator s delegate s app finds a challenge response file retrieves it removes it from the shared folder decrypts it and checks signature. If OK it displays the response text to the moderator delegate.

8. If the moderator delegate confirms the response as valid after an additional confirmation the PID owner should be added to the trusted list. At this stage the folder sharing process is resumed.

Note if challenge file signature is invalid or the answer is invalid the app shows a warning and removes the challenge file from the folder and suggests leaving unsharing the folder using Dropbox. Afterwards the sharing process may be repeated form the very beginning.

1. The user s SFRS app notices an SK file generated for it in the shared folder it retrieves it and removes it from the share.

Note The SFRS app may also notice the new moderator signature in the shared dropbox folder or notice a new delegate s PID in the smod file or notice the new user with whom the folder is shared in the pidlist. In this case the challenge response authorization will also be suggested to the user.

2. The app checks if the person who generated the SK file is in the trusted list or not. If yes the app accepts the key without any further user interaction. If not the app shows a dialog with information on the sharer name and email of the person who generated the SK file and the following options join the folder accepts the SK file discard the invitation removes the SK file requests the user to leave the folder using Dropbox check identity same request response sequence as described above . At the moment when the challenge is sent the process is suspended and resumed when the challenge is received.

3. Once the identity is confirmed the user s application accepts the SK file caches it and removes it from the shared folder and suggests the user to add SK file creator to the trusted list.

Note if the ID was taken not from the SK file after confirmation the PID is simply stored locally to the list of trusted PIDs.

1. While the SK is not yet retrieved and accepted by the user the new shared folder is specifically marked as temporary . An attempt to open this folder using the SFRS displays a message explaining the folder s state e.g. awaiting confirmation from share sender or waiting for share senders identity check .

2. The challenge request response file is a JSON file with a pre defined extension e.g. clg and a name uniquely identifying the file s intended recipient e.g. the recipient s PID . The file content includes the sender s PID and details name email and the request or response text. The file is asymmetrically encrypted with the recipients public key.

3. In case if the moderator s delegate s app finds several new PID files in the shared folder they are processed one by one.

4. The user is able to manage the list of trusted users using a specific section in the UI it is possible to remove the users from the trusted list and add any person listed in PIDlists of the accessible folders to it. Adding a new person to the trusted list does not require identity check but may require double confirmation from the user. The list of the trusted users is synchronized with the SFRS root subfolder.

3. PID revocation is the process to both inform the collaborators but also to prevent unauthorized access to the SFRS data in the private folders. PID is revoked from all the collaborators not only moderators.

User starts the PID revocation process. To User is displayed the double confirmation to start this process. The User is warned of the consequences.

The SFRS application then removes all the SK files from the local cache and the SK files from the hidden root .SFRS in one example .VIIVO folder removes the SID from the .SFRS in one example .VIIVO subfolder.

The SFRS application places the specific marker into the hidden .SFRS in one example .VIIVO root folder see the Subflow A below .

The SFRS application removes all the files in the Tunnel in the private user s the SFRS folders from Dropbox and locally . These files will typically need to be re encrypted in any case. If the user is a moderator the files are moved from all the shared folders that the user is a moderator.

The SFRS application uploads the specific revocation marker to all the shared folders Revoke PID file encrypted with the user s private key see Subflow B .

User is requested to leave all the folders in Dropbox inside the Tunnel when the user Leaves the folder the folder is no longer shared with him her and restart the SFRS.

Note After the revocation the user s Dropbox is free of any the SFRS metadata from the previous SID the user is able to generate a new SID after he starts the SFRS application next time.

When a blacklisted application starts again it checks all the files inside the tunnel for presence of shared folders. If it detects the shared marker in any folder the process proceeds to step 5.

If the app does not see the .dropbox marker of the shared folder inside any Tunnel subfolder the application removes all the remaining files inside the tunnel regenerates SID PID and the process of the initial SID PID sync between all the user s workstations will happen and removes the Revoke PID marker from the .SFRS in one example .VIIVO subfolder.

Here the SFRS application sees the marker of the PID revocation process in its cloud cache the .SFRS in one example .VIIVO root folder. The application then removes copies of the SK files stored locally disables syncs from to the SFRS tunnel denies user s access to the SFRS app and suggests the user to complete the PID revocation process and removes files from the local copies of files inside the the SFRS Tunnel both shared and private .

Here the SFRS application sees the Revoke PID marker in any shared folder. The SFRS adds the revoked PID to a list of revoked PIDs stored in the .SFRS in one example .VIIVO cloud cache the lists are personal .

For any folder the user is a moderator the PID file is removed from the PIDlist the SK is regenerated and the content is re encrypted while the content is being re encrypted the specific moderator signed marker is placed to the folder that prevents its modification using the SFRS by other users and new SK is distributed for all other users.

For any folder the user is a delegate and the revoked PID is NOT the moderator s PID the PID is removed from the PIDlist saved SKs are removed and new SKs are stored.

For any folder the user is a delegate and the revoked PID is the moderator s PID delegate status for the corresponding folder is cleared 

The lists of revoked users are personal for each user are stored in the SFRS cloud cache and are preferably not shared synced or merged between different the SFRS users.

One embodiment of the present invention includes a system including computer storage provided by a storage provider where users of the system store electronic information. This computer storage may use physical disk storage or virtual disk storage. Storage may be maintained by physical or virtual management server systems used to manage and access this storage by users. Storage may be contained within a single location or geographically dispersed. Storage may be implemented as a cloud architecture.

Access to this computer storage may occur through direct access through the management servers or by other methods. Access in the preferred implementation is provided using a network connection. The network connection may be implemented using a wired or wireless connection and would preferably be provided over the public internet. Other types of network connections may be used.

Users of the system access the computer storage from a range of computing devices having temporary or permanent connections to the network. Computing devices may include but are not limited to mainframe and midrange servers such as those operating under IBM z OS or UNIX and Linux operating systems personal computers workstations laptops mobile phones smartphones tablets optical or magnetic disk drives printing devices network storage devices or digital imaging devices.

A user of a computing device may use any of a number of available software tools to manually apply the verification and replay prevention method to their stored information. A user may determine a value for the current time combine data with the time value to produce a signature using a private key. Then store the signature and the information to the shared storage. It is preferable that the application software available on their computing device incorporates the verification and replay prevention method within the application operation to reduce the steps a user manually performs on their stored information.

This method of protecting information through verification and replay prevention is suitable for use within any type of software or hardware processing that desires a verification process for information. For example it may provide verification of information used within an operating system kernel process or within the input output subsystems or device drivers of an operating system that store and manage information.

This method may also be integrated into software applications that operate as a user level process or it may operate in software that provides internet access or that operates using the internet to access or share information. Examples may be file transfer or copy programs email or messaging applications productivity or workflow applications file management and file system management applications. Other types of software applications may be used.

Software may include this method on one or more computing platforms including mainframe and server platforms running operating systems including but not limited to IBM z OS Microsoft Windows or Linux. Other platforms on which this method may be enabled include personal computers servers physical or virtual server appliances virtual machines laptops mobile devices smart phones tablets optical or magnetic disk drives printing devices network storage devices SAN NAS or digital imaging devices. Other computing platforms may be used.

Information may be electronic files or resources R that contain documents spreadsheets presentations emails or messages calendars contact information database files compressed files encrypted files ZIP files OpenPGP files archive files graphical and binary image files pictures text files program files library files metadata and other information that may be stored on a computer. Metadata is information about files systems configurations settings or users that is used by the software and applications that process files created and used by the applications and their users. Metadata may include but is not limited to file names file sizes time and date information location allowed access compression information encryption information encryption keys known user or trust lists denied user or blacklists system state information PID SID SMOD OK ID .MOD JSON files. Collectively or individually this information may be referred to as data.

Data encryption may be applied to information in electronic files using encryption algorithms including but are not limited to RSA DES 3DES AES Blowfish Twofish. Other encryption algorithms may be used. Data encryption algorithms may symmetric or asymmetric keys. Data encryption algorithm may be used with any of a number of bit strengths. Data encryption algorithm bit lengths that define the strength of an algorithm such as 168 bits 192 bits or 256 bits 512 bits 1024 bits 2048 bits and 4096 bits may be used. Other data encryption algorithm bit lengths may be used.

Data authentication may be applied to information in electronic files using authentication methods including but not limited to digital signatures such as may be applied using a public private key pair cyclic redundancy checks such as CRC 32 secure hash functions such as MD5 RIPEMD SHA 1 SHA 256 SHA 384 or SHA 512 or HMAC.

Data compression may applied to information in electronic files using data compression algorithms including but not limited to Deflate PPMd Lempel Ziv based algorithms including LZMA. Other data compression algorithms may be used. Data compression reduces the bytes needed to store an electronic file making the compression copy of a file smaller than the original. When a file is compressed the original may be removed to reduce storage requirements.

Electronic information files compressed to reduce size using data compression may be placed within compressed archive formats before being placed into cloud storage. Compressed archive formats used to compress electronic information files include but are not limited to the .ZIP format by PKWARE Inc. RAR and others.

Encryption keys used within the data encryption processing of information in electronic files may be of any type commonly used. Types of encryptions keys used include but are not limited to passwords passphrases tokens one time pads public private key pairs and others. Public private key pairs may be of X.509 or OpenPGP. Other encryption key specifications may be used.

One way hash functions may include but are not limited to MD5 RIPEMD SHA 1 SHA 256 SHA 384 or SHA 512. Other one way hash functions may be used.

A user may be a member or an entity obtaining a membership or an entity that has not obtained a membership.

User A A may be a user a member a moderator a non moderator a delegate or have another role within a given workflow of one or more embodiments of the present invention.

User B B may be a user a member a moderator a non moderator a delegate or have another role within a given workflow of one or more embodiments of the present invention 

A delegate may be a member granted authority by a moderator to perform actions of or on behalf of a moderator.

A moderator is a member having authority to allow deny or revoke shared access abilities of other members.

The files and folders used within one or more embodiments of the present invention may operate on single device on cloud storage or on other storage method such as SAN or NAS. Files and folders used within the one or more embodiments of the present invention may reside on different devices or storage locations. For example data files may reside on user device and a cloud storage device and metadata may be placed onto separate storage from the data such as a server or other computer storage.

One or more embodiment of the present may include methods used to securely share information by integration within existing sharing systems available today including but not limited to Microsoft SharePoint or IBM Lotus Symphony. The one or more embodiments of the present invention also include methods used to securely share information by integration within other information sharing systems including but not limited to Facebook Google LinkedIn Twitter Skype Chatter or Apple FaceTime.

While particular elements embodiments and applications of the present invention have been shown and described it is understood that the invention is not limited thereto because modifications may be made by those skilled in the art particularly in light of the foregoing teaching. It is therefore contemplated by the appended claims to cover such modifications and incorporate those features which come within the spirit and scope of the invention.


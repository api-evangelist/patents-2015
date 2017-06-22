---

title: Method for providing application service
abstract: A method for providing application service is provided. The method discloses that a user is authenticated according to a received application service acquisition request from a user mobile phone, and when the user authentication is passed, the application service acquisition request is sent to an application server, so that the application server provides an application service to the user mobile phone according to the application service acquisition request. The application server does not need to authenticate the user mobile phone by performing an authentication operation on the user mobile phone through a wireless application protocol gateway, thus being capable of reducing the workload of the application server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09544769&OS=09544769&RS=09544769
owner: 
number: 09544769
owner_city: 
owner_country: 
publication_date: 20151019
---
This application is a continuation of U.S. patent application Ser. No. 14 142 946 filed on Dec. 30 2013 which is a continuation of International Application No. PCT CN2011 076634 filed on Jun. 30 2011 both of which are hereby incorporated by reference in its entirety.

The invention relates to the field of communication technologies and in particular to a method for providing application service wireless application protocol gateway and system.

With the development of wireless communication technology functions implemented by a wireless terminal such as a mobile phone are more and more powerful. A mobile phone application is application software running on the mobile phone. The application software implements various functions of the mobile phone through an API Application Programming Interface application programming interface extended from an underlayer of the mobile phone. Usually this mobile phone application has two ways off line application and online application. After application startup the offline application does not need network support any longer and runs independently at a mobile phone terminal. The online application requires network interaction and cannot run independently if departing from a network environment.

In the existing online applications a user mobile phone is connected with a WAPGW Wireless Application Protocol Gateway wireless application protocol gateway through a wireless network and then is accessed into Internet through the wireless application protocol gateway. The wireless application protocol gateway can only perform simple management operations for example target service shielding. Moreover some online applications can directly access the Internet through switching an access point and bypassing the wireless application protocol gateway.

The prior art at least has the following problems the wireless application protocol gateway only provides a network channel for accessing the application of the wireless terminal During access the security of an application server is very poor during accessing. The application server only uses a simple password authentication to authenticate the user mobile phone currently which does not have strong security. Moreover the user needs to enter a password for each access service which is inconvenient to use and causes poor user experience.

The embodiments of the present invention provide a method for providing application service wireless application protocol gateway and system which can reduce the workload of an application server improve security and experience of users.

An embodiment of the present invention provides a method for providing application service comprising 

According to the method for providing application service in the embodiments of the invention a user is authenticated according to a received application service acquisition request from a user mobile phone and when the user authentication is passed the application service acquisition request is sent to an application server so that the application server provides application service to the user mobile phone according to the application service acquisition request. The application server does not need to authenticate the user mobile phone by performing an authentication operation on the user mobile phone through a wireless application protocol gateway thus being capable of reducing the workload of the application server. In addition the user registers first fingerprint data to the wireless application protocol gateway. The wireless application protocol gateway acquires an encrypted fingerprint template of the user and an encryption key KEY corresponding to the encrypted fingerprint template. The wireless application protocol gateway generates security authentication data for the encryption key by using the first fingerprint data to conceal the encryption key so that the encryption key is protected more rigorously. During authentication the security authentication data is decrypted to obtain the encryption key by using second fingerprint data of the user and the encrypted fingerprint template is decrypted to obtain a fingerprint template by using the encryption key so that an authentication process is more secure and reliable. Moreover the user is only required to input fingerprints on a touch screen of the mobile phone which improves experience of the user.

To illustrate the advantages of the technical solutions of the invention more clearly the following introduces the invention in details with reference to the attached drawings and embodiments.

The embodiment provides a method for providing an application service. As shown in the method includes 

Step A user registers user fingerprint information to a wireless application protocol gateway which specifically includes 

The user mobile phone collects the user fingerprints to generate first fingerprint data of the user and sends the first fingerprint data to the wireless application protocol gateway through an encrypted channel.

The wireless application protocol gateway acquires an encrypted fingerprint template of the user and an encryption key KEY corresponding to the encrypted fingerprint template from an application server through the encrypted channel and saves the encrypted fingerprint template at the wireless application protocol gateway locally. The encryption key KEY is generated randomly by the application server. A length of the encryption key KEY is 128 bits. The encrypted fingerprint template is generated after the application server uses the encryption key KEY to encrypt a user fingerprint template.

The wireless application protocol gateway generates security authentication data according to the first fingerprint data and the encryption key which specifically includes 

The wireless application protocol gateway generates an encryption function of nine variables mod mod .

The encryption key KEY is split into eight non overlapping segments which are respectively s s . . . s. Each segment has 16 bits. Set a s a s . . . a s. Connect a ainto a 128 bit string KEYC aa. . . a calculate a cyclic redundancy check CRC 16 value C of the string KEYC. C is a 16 bit check value. Set a C mod p . P is a prime number 65537 that is proximate to 2 1 but larger than 2 1.

Acquire a set F x y x y . . . x y of minutiae plane coordinates in the first fingerprint data of the user where x y i 0 . . . N 1 are respectively minutiae plane coordinates and N is the total number of the minutiae. Each minutiae plane coordinate is respectively mapped into 0 255 and the mapped plane coordinates are connected in series together to constitute 16 bit data mand obtain a set H m m . . . m.

Take each m i 0 . . . N 1 as a 16 bit random number generator seed to generate eight random numbers r r . . . rin sequence and obtain a vector u u m uu. . . u mr. . . r .

Substitute each uinto the encryption function f u to calculate a corresponding encryption function value f u and obtain a set G wherein G is a set of the user encrypted fingerprint data constituted by the set H and the encryption function value corresponding to the elements thereinto and G m f u m m f u m . . . m f u m .

Generate an interference set C c d c d . . . c d where M is the number of elements of the set C cand d i 0 . . . M 1 are random numbers and a distance between cand mis larger than a preset threshold value. Moreover d f c .

Mix the elements in the set G and in the set C randomly to generate the security authentication data VL v w v w . . . v w where v w i 0 . . . M 1 represents the elements in the set G and in the set C.

The wireless application protocol gateway destroys the encryption key so as to ensure that the encryption key may not be disclosed.

Step The user inputs application service information to be acquired in a user mobile phone and inputs the fingerprints on a touch screen of the user mobile phone.

Step The user mobile phone collects the user fingerprints to generate second fingerprint data of the user carries the second fingerprint data in an application service acquisition request and sends the application service acquisition request to the wireless application protocol gateway through an encrypted channel.

Step The wireless application protocol gateway receives the application service acquisition request carrying the second fingerprint data from the user mobile phone and extracts the second fingerprint data from the application service acquisition request.

Step According to information of the user mobile phone for example a mobile phone number and the like the wireless application protocol gateway acquires the security authentication data saved locally.

Step The wireless application protocol gateway acquires the encryption key KEY according to the second fingerprint data and the security authentication data which specifically includes 

Extract a minutiae set Q x y x y . . . x y from the second fingerprint data where N is the total number of the minutiae in Q. N is not equal to the total number N of the minutiae in the first fingerprint data. Map minutiae plane coordinates xand y i 0 . . . N 1 into 0 255 .

Extract v v . . . vout from the security authentication data VL. Respectively split v v vinto two 8 bit numbers which are served as plane coordinates and a set R x y x y . . . x y may be obtained.

Use the elements in Q to locate elements belonging to true user fingerprint information in R. If a distance between a certain minutiae A in the set Q and a certain minutiae B in the set Ris smaller than a preset threshold value then it is determined that A and B are a pair of matching points and v w corresponding to B may be added into a matching point set R that is For all 0 i

If D x y x y T then v w belong to R. T is a threshold value. D x y x y represents a distance between the two points.

According to the foregoing algorithm a set of nine points R v w v w . . . v w may be obtained. Elements in Rare from true user fingerprints. Restore the encryption key KEY by using the elements in the set R. For each v R the 16 bit random number generator same with the random number generator is used to generate eight random numbers r r . . . rby using vas a seed. In this way a vector umay be obtained for each vi belongs to R 

Since v . . . vwhich serve as seeds are not the same each line of the random matrix U is irrelevant. That is a determinant U 0. In this way U may be guaranteed to be reversible thus solving afrom 3 mod 4 

Connect a a . . . ainto a string KEY in series wherein KEY KEY. In this way the encryption key KEY is restored.

Step The wireless application protocol gateway decrypts the encrypted fingerprint template according to the obtained encryption key KEY so as to obtain the fingerprint template of the user.

Step The wireless application protocol gateway compares the acquired second fingerprint data with the fingerprint template of the user determines that the user identity authentication is passed when a comparison result is that the two are matched and sends the application service acquisition request to the application server.

Step The application server sends a requested application service to the wireless application protocol gateway according to the application service acquisition request.

Step The wireless application protocol gateway provides the application service to the user mobile phone.

According to a method for providing application service in the embodiments of the invention the user is authenticated by the wireless application protocol gateway according to the received application service acquisition request from the user mobile phone and when the user authentication is passed the application service acquisition request is sent to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request. The application server does not need to authenticate the user mobile phone by performing an authentication operation on the user mobile phone through the wireless application protocol gateway thus being capable of reducing the workload of the application server. In addition the user registers the first fingerprint data to the wireless application protocol gateway. The wireless application protocol gateway acquires the encrypted fingerprint template of the user and the encryption key KEY corresponding to the encrypted fingerprint template. The wireless application protocol gateway generates security authentication data for the encryption key by using the first fingerprint data to conceal the encryption key so that the encryption key is protected more rigorously. During authentication the security authentication data is decrypted to obtain the encryption key by using the second fingerprint data of the user and the encrypted fingerprint template is decrypted to obtain a fingerprint template by using the encryption key so that an authentication process is more secure and reliable. Moreover the user only requires inputting fingerprints on the touch screen of the mobile phone which improves the user experiences.

The embodiment provides a method for providing an application service. As shown in the method includes the following steps 

S An application server releases applications on an application management platform. The application management platform forms the applications released by the application server into an application list so that a user may query and download conveniently. The application management platform is configured to perform management operations on the applications including application releasing updating and the like and perform management on information of a user mobile phone including such information as an account number and an account of the user mobile phone and the like.

S A wireless application protocol gateway receives an application query request sent by the user mobile phone through a software platform.

The software platform provides an operating environment for the applications of the user mobile phone and provides an interface between operating systems for example XML Extensible Markup Language Extensible Markup Language parsing JavaScript engine AJAX Asynchronous JavaScript and XML Asynchronous JavaScript and XML call engine cache graphics library underlayer device management multimedia management security management and the like provides necessary component support in an operating process and perform management on the operating environment of the applications of the user mobile phone performs management on the applications of the user mobile phone and is responsible for remotely loading deleting and updating the applications.

S The wireless application protocol gateway sends the application query request to the application management platform so as to acquire the application list.

Further when a message format of the application query request cannot be recognized by the application management platform the wireless application protocol gateway firstly converts the application query request into a format which can be recognized by the application management platform and then sends the converted application query request to the application management platform so as to acquire the application list.

S The wireless application protocol gateway receives the application list fed back by the application management platform.

S The wireless application protocol gateway sends the application list fed back by the application management platform to the user mobile phone through the software platform.

S The wireless application protocol gateway receives an application downloading request sent by the user mobile phone through the software platform.

S The wireless application protocol gateway forwards the application downloading request to the application management platform so that the application management platform sends the applications to the user mobile phone.

Further when a message format of the application downloading request cannot be recognized by the application management platform the wireless application protocol gateway firstly converts the application downloading request into a format which can be recognized by the application management platform and then sends the converted application downloading request to the application management platform.

S The wireless application protocol gateway receives the applications sent by the application management platform.

S The wireless application protocol gateway sends the applications sent by the application management platform to the user mobile phone through the software platform.

S The wireless application protocol gateway receives an application service request sent by the user mobile phone through the software platform.

S. The wireless application protocol gateway authenticates the user mobile phone according to the application service acquisition request.

To be specific the application service acquisition request includes identity information of the user mobile phone for example information such as number IP address and the like relevant information of the application server requiring being accessed for example such information as the IP address and the like and relevant information of the applications for example information such as application names and the like.

The wireless application protocol gateway based on self authentication strategies and according to the identity information of the user mobile phone as well as relevant information of the application server requiring access judges whether the user mobile phone is a user allowed by the application server that is whether the application server is allowed to provide an application service for the user mobile phone. Moreover the wireless application protocol gateway judges whether the application server can provide the application service corresponding to the applications for the user mobile phone according to relevant information of the applications. When judging the user mobile phone is legal the wireless application protocol gateway is allowed to provide the application service for the user mobile phone. The application server can provide the application service corresponding to the application to the user mobile phone.

S When the authentication of the user mobile phone is passed the wireless application protocol gateway sends the application service acquisition request to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request. Further when a message format of the application service acquisition request cannot be recognized by the application server the wireless application protocol gateway firstly converts the application service acquisition request into a format which can be recognized by the application server and then sends the converted application service acquisition request to the application server.

S The application server provides the application service to the user mobile phone according to the application service acquisition request.

According to the method for providing application service in the embodiments of the invention the wireless application protocol gateway may further perform format conversion on a request message sent to the application management platform or the application server by the user mobile phone thus being capable of performing adaption between the user mobile phone and different application management platforms or application servers thereby increasing the user experience quality.

An embodiment provides a wireless application protocol gateway. As shown in the wireless application protocol gateway includes a receiving unit a memory an authenticating unit a determining unit a decrypting unit and a sending unit wherein 

the memory is configured to store an encrypted fingerprint template of the user and an encryption key KEY corresponding to the encrypted fingerprint template both of which are acquired from an application server through an encrypted channel wherein the encryption key KEY is generated randomly by the application server a length of the encryption key KEY is 128 bits the encrypted fingerprint template is generated after the application server uses the encryption key KEY to encrypt a user fingerprint template 

the authenticating unit is configured to generate security authentication data according to the first fingerprint data and the encryption key wherein authenticating unit specifically is configured to 

split the encryption key KEY into eight non overlapping segments which are respectively s s . . . s each segment has 16 bits set a s a s . . . a s to connect a ainto a 128 bit string KEYC aa. . . a 

calculate a cyclic redundancy check CRC 16 value C of the string KEYC wherein C is a 16 bit check value 

acquire a set F x y x y . . . x y of minutiae plane coordinates in the first fingerprint data of the user where x y i 0 . . . N 1 are respectively minutiae plane coordinates and N is the total number of the minutiae each minutiae plane coordinate is respectively mapped into 0 255 and the mapped plane coordinates are connected in series together to constitute 16 bit data mand obtain a set H m m . . . m 

take each mi i 0 . . . N 1 as a 16 bit random number generator seed to generate eight random numbers r r . . . rin sequence and obtain a vector u u m uu. . . u mr. . . r 

substitute each uinto the encryption function f u to calculate a corresponding encryption function value f u and obtain a set G of the user encrypted fingerprint data constituted by the set H and the encryption function value corresponding to the elements thereinto and G m f u m m f u m . . . m f u m wherein f u is an encryption function of nine variables and f u au mod p au au . . . au au mod p .

generate an interference set C c d c d . . . c d wherein M is the number of elements of the set C cand d i 0 . . . M 1 are random numbers and a distance between cand mis larger than a preset threshold value and d f c 

mix the elements in the set G and in the set C randomly to generate the security authentication data VL v w v w . . . v w wherein v w i 0 . . . M 1 represent the elements in the set G and in the set C 

the determining unit is configured to receive an application service acquisition request carrying second fingerprint data from a user mobile phone extract the second fingerprint data from the application service acquisition request acquire the security authentication data saved locally according to information of the user mobile phone compute the encryption key KEY according to the second fingerprint data and the security authentication data wherein the process of compute the encryption key KEY specifically includes 

extracting a minutiae set Q from the second fingerprint data wherein Q x y x y . . . x y N is the total number of the minutiae in Q N is not equal to the total number N of the minutiae in the first fingerprint data mapping minutiae plane coordinates xand yinto 0 255 wherein k 0 1 2 . . . N 1 

extracting v v . . . vout from the security authentication data VL splitting v v . . . vrespectively into two 8 bit numbers which are served as plane coordinates obtaining a set R x y x y . . . x y 

if a distance between a certain minutiae A in the set Q and a certain minutiae B in the set Ris smaller than a preset threshold value determining that A and B are a pair of matching points adding v w corresponding to B into a matching point set Rto obtain a set of nine points R v w v w . . . v w .

restoring the encryption key KEY by using the elements in the set R wherein the step of restoring the encryption key KEY by using the elements in the set Rcomprises 

for each v R using the 16 bit random number generator same as the random number generator to generate eight random numbers r r . . . rby using vas a seed obtaining an equation set mod mod mod solving mod wherein

the decrypting unit is configured to decrypt the encrypted fingerprint template according to the obtained encryption key KEY so as to obtain the fingerprint template of the user compare the acquired second fingerprint data with the fingerprint template of the user determine that the user identity authentication is passed when a comparison result is that the two are matched and send the application service acquisition request to the application server.

the sending unit is configured to provide the application service obtained from the application server to the user mobile phone.

Optionally the decrypting unit is further configured to determine to refuse to provide application service to the user when the comparison result is that the two are not matched and send message that the application service is refused to the user mobile phone.

Optionally the wireless application protocol gateway is further configured to send the application query request to the application management platform so as to acquire the application list.

Further when a message format of the application query request cannot be recognized by the application management platform the wireless application protocol gateway firstly converts the application query request into a format which can be recognized by the application management platform and then sends the converted application query request to the application management platform so as to acquire the application list.

The wireless application protocol gateway is further configured to receive through the receiving unit the application list fed back by the application management platform.

The wireless application protocol gateway is further configured to send the application list fed back by the application management platform to the user mobile phone through the software platform.

Further when a message format of the application downloading request cannot be recognized by the application management platform the wireless application protocol gateway is configured to convert the application downloading request into a format which can be recognized by the application management platform and then send the converted application downloading request to the application management platform. The wireless application protocol gateway receives the applications sent by the application management platform. The wireless application protocol gateway sends the applications sent by the application management platform to the user mobile phone through the software platform. The software platform manages the applications.

The wireless application protocol gateway is configured to receive through the receiving unit an application service request sent by the user mobile phone through the software platform. The wireless application protocol gateway is configured to authenticate the user mobile phone according to the application service acquisition request.

To be specific the application service acquisition request includes identity information of the user mobile phone for example information such as number IP address and the like relevant information of the application server requiring being accessed for example such information as the IP address and the like and relevant information of the applications for example information such as application names and the like.

The wireless application protocol gateway based on self authentication strategies and according to the identity information of the user mobile phone as well as relevant information of the application server requiring access judges whether the user mobile phone is a user allowed by the application server that is whether the application server is allowed to provide an application service for the user mobile phone. Moreover the wireless application protocol gateway judges whether the application server can provide the application service corresponding to the applications for the user mobile phone according to relevant information of the applications. When judging the user mobile phone is legal the wireless application protocol gateway is allowed to provide the application service for the user mobile phone. The application server can provide the application service corresponding to the application to the user mobile phone.

When the authentication of the user mobile phone is passed the wireless application protocol gateway is configured to send the application service acquisition request to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request.

Optionally the determining unit is further configured to receive the application service acquisition request from the user mobile phone through the software platform.

Optionally the determining unit is further configured to receive an application query request sent by the user mobile phone through the software platform.

Further when a message format of the application query request cannot be recognized by the application management platform the determining unit is further configured to convert the application query request into a format which can be recognized by the application management platform and then send the converted application query request to the application management platform so as to acquire the application list.

According to the wireless application protocol gateway in the embodiment of the invention the user is authenticated by the wireless application protocol gateway according to the received application service acquisition request from the user mobile phone and when the user authentication is passed the application service acquisition request is sent to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request. The application server does not need to authenticate the user mobile phone by performing an authentication operation on the user mobile phone through the wireless application protocol gateway thus being capable of reducing the workload of the application server. In addition the user registers the first fingerprint data to the wireless application protocol gateway. The wireless application protocol gateway acquires the encrypted fingerprint template of the user and the encryption key KEY corresponding to the encrypted fingerprint template. The wireless application protocol gateway generates the security authentication data for the encryption key by using the first fingerprint data to conceal the encryption key so that the encryption key is protected more rigorously. During authentication the security authentication data is decrypted to obtain the encryption key by using the second fingerprint data of the user and the encrypted fingerprint template is decrypted to obtain a fingerprint template by using the encryption key so that an authentication process is more secure and reliable. Moreover the user only requires inputting fingerprints on the touch screen of the mobile phone which improves the user experiences.

An embodiment provides a network system as shown in . The system includes a user mobile phone a wireless application protocol gateway and an application server wherein the user mobile phone is configured to send first fingerprint data to the wireless application protocol gateway and the wireless application protocol gateway includes a receiving unit a memory an authenticating unit a determining unit a decrypting unit and a sending unit wherein 

the receiving unit is configured to receive the first fingerprint data generated by the user mobile phone 

the memory is configured to store an encrypted fingerprint template of the user and an encryption key KEY corresponding to the encrypted fingerprint template both of which are acquired from an application server through an encrypted channel wherein the encryption key KEY is generated randomly by the application server a length of the encryption key KEY is 128 bits the encrypted fingerprint template is generated after the application server uses the encryption key KEY to encrypt a user fingerprint template 

the authenticating unit is configured to generate security authentication data according to the first fingerprint data and the encryption key wherein authenticating unit specifically is configured to 

split the encryption key KEY into eight non overlapping segments which are respectively s s . . . s each segment has 16 bits set a s a s . . . a s to connect a ainto a 128 bit string KEYC aa. . . a 

calculate a cyclic redundancy check CRC 16 value C of the string KEYC wherein C is a 16 bit check value 

acquire a set F x y x y . . . xy of minutiae plane coordinates in the first fingerprint data of the user where x y i 0 . . . N 1 are respectively minutiae plane coordinates and N is the total number of the minutiae each minutiae plane coordinate is respectively mapped into 0 255 and the mapped plane coordinates are connected in series together to constitute 16 bit data mand obtain a set H m m . . . m 

take each mi i 0 . . . N 1 as a 16 bit random number generator seed to generate eight random numbers r r . . . rin sequence and obtain a vector u u m uu. . . u mr. . . r 

substitute each uinto the encryption function f u to calculate a corresponding encryption function value f u and obtain a set G of the user encrypted fingerprint data constituted by the set H and the encryption function value corresponding to the elements thereinto and G m f u m m f u m . . . m f u m wherein f u is an encryption function of nine variables and f u au mod p au au . . . au au mod p 

generate an interference set C c d c d . . . c d wherein M is the number of elements of the set C cand d i 0 . . . M 1 are random numbers and a distance between cand mis larger than a preset threshold value and d f c 

mix the elements in the set G and in the set C randomly to generate the security authentication data VL v w v w . . . v w wherein v w i 0 . . . M 1 represent the elements in the set G and in the set C 

the determining unit is configured to receive an application service acquisition request carrying second fingerprint data from a user mobile phone extract the second fingerprint data from the application service acquisition request acquire the security authentication data saved locally according to information of the user mobile phone compute the encryption key KEY according to the second fingerprint data and the security authentication data wherein the process of compute the encryption key KEY specifically includes 

extracting a minutiae set Q from the second fingerprint data wherein Q x y x y . . . z y N is the total number of the minutiae in Q N is not equal to the total number N of the minutiae in the first fingerprint data mapping minutiae plane coordinates xand yinto 0 255 wherein k 0 1 2 . . . N 1 

extracting v v . . . vout from the security authentication data VL splitting v v . . . vrespectively into two 8 bit numbers which are served as plane coordinates obtaining a set R x y x y . . . x y 

if a distance between a certain minutiae A in the set Q and a certain minutiae B in the set Ris smaller than a preset threshold value determining that A and B are a pair of matching points adding v w corresponding to B into a matching point set Rto obtain a set of nine points R v w v w . . . v w .

restoring the encryption key KEY by using the elements in the set R wherein the step of restoring the encryption key KEY by using the elements in the set Rcomprises 

for each v R using the 16 bit random number generator same as the random number generator to generate eight random numbers r r . . . rby using vas a seed obtaining an equation set mod mod mod solving mod wherein

the decrypting unit is configured to decrypt the encrypted fingerprint template according to the obtained encryption key KEY so as to obtain the fingerprint template of the user compare the acquired second fingerprint data with the fingerprint template of the user determine that the user identity authentication is passed when a comparison result is that the two are matched and send the application service acquisition request to the application server.

the sending unit is configured to provide the application service obtained from the application server to the user mobile phone.

Optionally the decrypting unit is further configured to determine to refuse to provide application service to the user when the comparison result is that the two are not matched and send message that the application service is refused to the user mobile phone.

Optionally the wireless application protocol gateway is further configured to send the application query request to the application management platform so as to acquire the application list.

Further when a message format of the application query request cannot be recognized by the application management platform the wireless application protocol gateway firstly converts the application query request into a format which can be recognized by the application management platform and then sends the converted application query request to the application management platform so as to acquire the application list.

The wireless application protocol gateway is further configured to receive through the receiving unit the application list fed back by the application management platform.

The wireless application protocol gateway is further configured to send the application list fed back by the application management platform to the user mobile phone through the software platform.

Further when a message format of the application downloading request cannot be recognized by the application management platform the wireless application protocol gateway is configured to convert the application downloading request into a format which can be recognized by the application management platform and then send the converted application downloading request to the application management platform. The wireless application protocol gateway receives the applications sent by the application management platform. The wireless application protocol gateway sends the applications sent by the application management platform to the user mobile phone through the software platform. The software platform manages the applications.

The wireless application protocol gateway is configured to receive through the receiving unit an application service request sent by the user mobile phone through the software platform. The wireless application protocol gateway is configured to authenticate the user mobile phone according to the application service acquisition request.

To be specific the application service acquisition request includes identity information of the user mobile phone for example information such as number IP address and the like relevant information of the application server requiring being accessed for example such information as the IP address and the like and relevant information of the applications for example information such as application names and the like.

The wireless application protocol gateway based on self authentication strategies and according to the identity information of the user mobile phone as well as relevant information of the application server requiring access judges whether the user mobile phone is a user allowed by the application server that is whether the application server is allowed to provide an application service for the user mobile phone. Moreover the wireless application protocol gateway judges whether the application server can provide the application service corresponding to the applications for the user mobile phone according to relevant information of the applications. When judging the user mobile phone is legal the wireless application protocol gateway is allowed to provide the application service for the user mobile phone. The application server can provide the application service corresponding to the application to the user mobile phone.

When the authentication of the user mobile phone is passed the wireless application protocol gateway is configured to send the application service acquisition request to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request.

Optionally the determining unit is further configured to receive the application service acquisition request from the user mobile phone through the software platform.

Optionally the determining unit is further configured to receive an application query request sent by the user mobile phone through the software platform.

Further when a message format of the application query request cannot be recognized by the application management platform the determining unit is further configured to convert the application query request into a format which can be recognized by the application management platform and then send the converted application query request to the application management platform so as to acquire the application list.

According to the wireless application protocol gateway in the embodiment of the invention the user is authenticated by the wireless application protocol gateway according to the received application service acquisition request from the user mobile phone and when the user authentication is passed the application service acquisition request is sent to the application server so that the application server provides the application service to the user mobile phone according to the application service acquisition request. The application server does not need to authenticate the user mobile phone by performing an authentication operation on the user mobile phone through the wireless application protocol gateway thus being capable of reducing the workload of the application server. In addition the user registers the first fingerprint data to the wireless application protocol gateway. The wireless application protocol gateway acquires the encrypted fingerprint template of the user and the encryption key KEY corresponding to the encrypted fingerprint template. The wireless application protocol gateway generates the security authentication data for the encryption key by using the first fingerprint data to conceal the encryption key so that the encryption key is protected more rigorously. During authentication the security authentication data is decrypted to obtain the encryption key by using the second fingerprint data of the user and the encrypted fingerprint template is decrypted to obtain a fingerprint template by using the encryption key so that an authentication process is more secure and reliable. Moreover the user only requires inputting fingerprints on the touch screen of the mobile phone which improves the user experiences.

Persons of ordinary skill in the art should understand that all or a part of the steps of the method according to the embodiments of the present invention may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium. When the program is run the steps of the method according to the embodiments of the present invention are performed. The storage medium may be any medium that is capable of storing program codes such as a Read Only Memory ROM a Random Access Memory RAM a magnetic disk and an optical disk.

Finally it should be noted that the above embodiments are merely provided for describing the technical solutions of the present invention but not intended to limit the present invention. It should be understood by persons of ordinary skill in the art that although the present invention has been described in detail with reference to the foregoing embodiments modifications can be made to the technical solutions described in the foregoing embodiments or equivalent replacements can be made to some technical features in the technical solutions as long as such modifications or replacements do not cause the essence of corresponding technical solutions to depart from the spirit and scope of the present invention.


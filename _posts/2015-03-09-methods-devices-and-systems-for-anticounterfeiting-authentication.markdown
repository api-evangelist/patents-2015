---

title: Methods, devices and systems for anti-counterfeiting authentication
abstract: An anti-counterfeiting authentication method is provided. The method includes: generating an encrypted message corresponding to an i-th authentication step, wherein the i-th authentication step is one of n authentication steps arranged in a predetermined order, and 1≦i≦n; sending the encrypted message to a terminal device; receiving, from the terminal device, a call request for initiating the i-th authentication step; executing the i-th authentication step if the request is initiated based on the encrypted message; if the i-th authentication step succeeds and i is less than n, increasing i by one and repeating the generating of an encrypted message; if the i-th authentication step fails, sending an indication to the terminal device indicating an authentication failure; and if the i-th authentication step succeeds and i equals to n, sending an indication to the terminal device indicating an authentication success.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09426130&OS=09426130&RS=09426130
owner: Xiaomi Inc.
number: 09426130
owner_city: Beijing
owner_country: CN
publication_date: 20150309
---
This application is s a continuation of International Application No. PCT CN2014 091426 filed Nov. 18 2014 which is based upon and claims priority to Chinese Patent Application No. 201410348001.5 filed Jul. 21 2014 the entire contents of all of which are incorporated herein by reference.

The present disclosure generally relates to the field of terminal devices and more particularly to methods devices and systems for anti counterfeiting authentication.

Along with the popularization of mobile phones tablet PCs smart televisions and the like a large amount of counterfeit devices appear on the market. These counterfeit devices often confuse users in terms of appearance and operating systems. It is often difficult for users to distinguish genuine products from the counterfeiting products.

In conventional anti counterfeiting authentication methods an application program may be downloaded and installed in a terminal device that is to be authenticated. The application program may conduct anti counterfeiting authentication of the terminal device. The application program may acquire configuration parameters and performance parameters of the terminal device and then match them with configuration parameters and performance parameters stored in a database. The terminal device may be determined as a genuine product if the acquired parameters of the terminal device match the stored parameters in the database. Otherwise the terminal device may be determined as a counterfeit product.

According to a first aspect of the present disclosure there is provided an anti counterfeiting authentication method comprising generating an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n sending the encrypted message to a terminal device receiving from the terminal device a call request for initiating the i th authentication step executing the i th authentication step if the request is initiated based on the encrypted message if the i th authentication step succeeds and i is less than n increasing i by one and repeating the generating of an encrypted message if the i th authentication step fails sending an indication to the terminal device indicating an authentication failure and if the i th authentication step succeeds and i equals to n sending an indication to the terminal device indicating an authentication success.

According to a second aspect of the present disclosure there is provided an anti counterfeiting authentication method comprising receiving from a server an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n sending to the server a call request for initiating the i th authentication step based on the encrypted message and receiving from the server an indication indicating an authentication failure or an authentication success.

According to a third aspect of the present disclosure there is provided an anti counterfeiting authentication device comprising a processor and a memory for storing instructions executable by the processor. The processor is configured to generate an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n send the encrypted message to a terminal device receive from the terminal device a call request for initiating the i th authentication step execute the i th authentication step if the call request is initiated based on the encrypted message if the i th authentication step succeeds and i is less than n increase i by one and repeat the generating of an encrypted message if the i th authentication step fails send an indication to the terminal device indicating an authentication failure and if the i th authentication step succeeds and i equals to n send an indication to the terminal device indicating an authentication success.

According to a fourth aspect of the present disclosure there is provided an anti counterfeiting authentication device comprising a processor and a memory for storing instructions executable by the processor. The processor is configured to receive from a server an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n send to the server a call request for initiating the i th authentication step based on the encrypted message and receive from the server an indication indicating an authentication failure or an authentication success.

According to a fifth aspect of the present disclosure there is provided a non transitory computer readable storage medium having stored therein instructions that when executed by a processor of a server cause the server to perform an anti counterfeiting authentication method comprising generating an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n sending the encrypted message to a terminal device receiving a call request sent from the terminal device for initiating the i th authentication step executing the i th authentication step if the call request is initiated based on the encrypted message if the i th authentication step succeeds and i is less than n increasing i by one and repeating the generating of an encrypted message if the i th authentication step fails sending an indication to the terminal device indicating an authentication failure and if the i th authentication step succeeds and i equals to n sending an indication to the terminal device indicating an authentication success.

According to a sixth aspect of the present disclosure there is provided a non transitory computer readable storage medium having stored therein instructions that when executed by a processor of a terminal device cause the terminal device to perform an anti counterfeiting authentication method comprising receiving from a server an encrypted message corresponding to an i th authentication step wherein the i th authentication step is one of n authentication steps arranged in a predetermined order and 1 i n sending to the server a call request for initiating the i th authentication step based on the encrypted message and receiving from the server an indication indicating an authentication failure or an authentication.

It is to be understood that both the foregoing general description and the following detailed description are exemplary rather than limiting the present disclosure.

Reference will now be made in detail to exemplary embodiments examples of which are illustrated in the accompanying drawings. The following description refers to the accompanying drawings in which the same numbers in different drawings represent the same or similar elements unless otherwise represented. The following exemplary embodiments and description thereof intend to illustrate rather than to limit the present disclosure. Hereinafter the present disclosure will be described with reference to the drawings.

The terminal device to be authenticated may be a mobile phone a tablet computer an ebook reader a Moving Picture Experts Group Audio Layer III MP3 player a Moving Picture Experts Group Audio Layer IV MP4 player a smart television and the like.

The server may be a server or a server cluster including a plurality of servers or a cloud computing service center.

In exemplary embodiments anti counterfeiting authentication methods described below may be performed by the terminal device to be authenticated.

In other embodiments the anti counterfeiting authentication methods may be performed by other terminal equipment connected to the terminal device . For example the anti counterfeiting authentication methods may be performed by a computer which is connected to the terminal device through a Universal Serial Bus USB data line a wired network or a wireless network for acquiring information relating to the terminal device .

In step the server generates an encrypted message corresponding to an i th authentication step where the i th authentication step is an authentication step of n authentication steps arranged in a predetermined order for authenticating a terminal device and 1 i n.

In step the server receives from the terminal device to be authenticated a call request for initiating the i th authentication step. For example the call request is configured to request calling of a set of instructions for initiating the i th authentication step.

In step if the call request is initiated based on the encrypted message sent to the terminal device the server executes the i th authentication step.

In step if the i th authentication step succeeds in authentication and i n the server increases i by 1 i.e. i i 1 and returns to step to generate an encrypted message corresponding to a new i th authentication step.

In step if the i th authentication step fails the server sends an indication of authentication failure to the terminal device to be authenticated.

In step if the i th authentication step succeeds and i n the server sends an indication of authentication success to the terminal device to be authenticated.

Since the i th authentication step is executed upon receiving a call request initiated based on an encrypted message corresponding to the i th authentication step a counterfeit terminal device would not meet conditions for triggering and executing the i th authentication step thereby improving the authentication success rate.

In step the terminal device receives an encrypted message sent from a server corresponding to an i th authentication step where the i th authentication step is an authentication step of n authentication steps arranged in a predetermined order for authenticating the terminal device and 1 i n.

In step the terminal device sends a call request for initiating the i th authentication step to the server based on the encrypted message. For example the call request is configured to request calling of a set of instructions for initiating the i th authentication step.

In step the terminal device receives an indication indicating an authentication failure or an authentication success from the server.

Since a counterfeit client application cannot meet conditions for triggering and executing the i th authentication step the method improves the authentication success rate by requiring the terminal device to send a call request to the server based on the encrypted message for initiating the i th authentication step.

In step the terminal device to be authenticated may acquire information relating to the terminal device.

In some embodiments a user may conduct an anti counterfeiting authentication of the terminal device to be authenticated using a client application to communicate with a server. For example a user may download and install a client application in the terminal device to be authenticated or download and install a client application in other terminal equipment. When a client application is installed in other terminal equipment the terminal equipment may be connected to the terminal device to be authenticated through e.g. a USB data line a wireless network or a wired network. In the exemplary embodiment presented in the client application is installed in the terminal device to be authenticated.

The client application may acquire information relating to the terminal device to be authenticated. In some embodiments the information may include a unique identification of the terminal device to be authenticated such as an International Mobile Equipment Identity IMEI number.

In step the terminal device to be authenticated sends the information relating to the terminal device to the server.

Correspondingly the server receives the information sent from the terminal device to be authenticated.

For example the i th authentication step is an authentication step of n authentication steps arranged in a predetermined order for authenticating the terminal device and 1 i n. Also for example a server may preset the n authentication steps to authenticate the terminal device where the n authentication steps may be arranged differently corresponding to different options.

For example if n 4 the predetermined order corresponding to authentication steps 1 to 4 may be set according to a single option authentication step 1 authentication step 2 authentication step 3 authentication step 4.

As another example if n 5 the predetermined order corresponding to authentication steps 1 to 5 may be set differently according to first and second options. The predetermined order according to the first option may be authentication step 1 authentication step 2 authentication step 3 authentication step 4 authentication step 5. The predetermined order according to the second option may be authentication step 1 authentication step 2 authentication step 4 authentication step 3 authentication step 5.

In addition before the server executes any execution step for authentication of the terminal device the authenticity of the client application running in the terminal device to be authenticated can be authenticated by an encrypted message so as to prevent an counterfeit client application from initiating authentication steps not according to a predetermined order or skipping some authentication steps to acquire successful authentication results from the client application. In some embodiments the server may generate an encrypted message by the following method.

For example the server may encrypt an unencrypted message by using a private key thereby generating the encrypted message corresponding to the i th authentication step. In some embodiments the unencrypted message may include the following implementations.

In a first implementation when 1 i n the unencrypted message includes information relating to the terminal device to be authenticated and a step number corresponding to the i th authentication step.

In a second possible implementation when i 1 the unencrypted message includes information relating to the terminal device to be authenticated and when i 2 the unencrypted message includes information relating to the terminal device to be authenticated and a step number corresponding to an i 1 th authentication step which has been performed successfully.

Correspondingly the terminal device to be authenticated receives the encrypted message sent from the server.

In step the terminal device to be authenticated sends a call request for initiating the i th authentication step to the server based on the encrypted message.

In a first substep the terminal device generates a call request for initiating the i th authentication step where the call request includes the encrypted message corresponding to the i th authentication step received from the server.

Thus after receiving the encrypted message the terminal device may include the encrypted message in the call request to generate the call request for initiating the i th authentication step without having to process the encrypted message.

In addition if the client application running in the terminal device is authentic the client application may selectively and successively initiate n authentication steps according to the predetermined order. Different application programming interface API ports may be configured by the server in advance for different authentication steps. For example the number of an API port corresponding to authentication step 1 may be set to 41 the number of an API port corresponding to authentication step 2 may be set to 42 and the number of an API port corresponding to authentication step 3 may be set to 43 etc. The client application may use different API ports provided by the server when sending to the server call requests for initiating different authentication steps. The server may also determine based on the number of the API port used by the client side the actual step number of the authentication step initiated by the client side.

Correspondingly the server receives the call request from the terminal device to be authenticated for initiating the i th authentication step.

In step if the call request is initiated based on the encrypted message corresponding to the i th authentication step the server may execute the i th authentication step.

Before executing the i th authentication step the server may verify whether the call request sent from the terminal device to be authenticated is initiated based on the encrypted message corresponding to the i th authentication step so as to determine the authenticity of the client application running in the terminal device to be authenticated.

In a first substep the server detects whether the call request includes the encrypted message corresponding to the i th authentication step.

If the call request includes no encrypted message corresponding to the i th authentication step the server determines that this client application may be a counterfeit one. Under the circumstances the server may directly generate an indication indicating an authentication failure.

Since the encrypted message is generated by the server by encrypting an unencrypted message using a private key the encrypted message may be decrypted by the server. In other words other application programs or equipment than the server should be unable to counterfeit or change the foregoing encrypted message thus ensuring the reliability in authenticating the call request.

In some embodiments if the call request includes the encrypted message but the server is unable to decrypt the encrypted message using the private key the server may determine that this encrypted message is a counterfeit one. For example it is possible that a counterfeit client application attempts to skip some authentication steps by counterfeiting step numbers included in an unencrypted message. Under the circumstances the server may generate an indication of an authentication failure.

In a fourth substep the server determines a step number corresponding to the i th authentication step according to contents of the unencrypted message.

For example once an unencrypted message is acquired by successfully decryption the server may retrieve the step number corresponding to the i th authentication step included in the unencrypted message. Alternatively the server may retrieve the step number included in the unencrypted message corresponding to the i 1 th authentication step that is successfully executed and determine the step number corresponding to the i th authentication step based on the step number corresponding to the i 1 th authentication step and the predetermined order.

In a fifth substep the server detects whether the actual step number initiated by the call request matches a step number corresponding to the i th authentication step.

For example the server may determine according to the number of the API port used when the terminal device to be authenticated sends the call request the actual step number initiated by the call request and further compare the actual step number with the step number corresponding to the i th authentication step determined after decryption thereby detecting whether they match.

In a sixth substep the server executes the i th authentication step if the actual step number matches the step number corresponding to the i th authentication step.

If the actual step number does not match the step number corresponding to the i th authentication step the server may generate an indication of authentication failure. In some embodiments in order to further improve the reliability of authentication results the server may include a timing message in an unencrypted message in generating the encrypted message. For example the timing message may be configured to control the time at which the terminal device to be authenticated sends a call request. The timing message may be a timestamp corresponding to a time when the server generates an encrypted message or a timestamp corresponding to a time when the server receives a latest call request.

Before the server executes the i th authentication step the following steps may be executed if the unencrypted message also includes a timing message.

In a second substep the server detects based on the timing message whether the time at which the call request is received is within a valid time frame.

In a third substep the server executes the i th authentication step if the call request is received within the valid time frame and the actual step number matches the step number corresponding to the i th authentication step.

The server may not execute the i th authentication step for authentication of the terminal device unless the detection result of the call request meets both of the conditions.

In one embodiment the terminal device to be authenticated may be authenticated by the server according to configuration parameters of the terminal device if the i th authentication step is a configuration parameter authentication step.

For example configuration parameters may include Central Processing Unit CPU serial number Bluetooth serial number sensor type screen resolution screen pixel density and or camera pixel. The server may compare configuration parameters of a terminal device to be authenticated with those of an authentic terminal device of the same model as the terminal device to be authenticated thus determining whether the terminal device to be authenticated is an authentic product.

The terminal device to be authenticated may send configuration parameters along with a call request when sending the call request to the server or send configuration parameters to the server before sending the call request to the server or send configuration parameters to the server after sending the call request to the server.

In another embodiment the terminal device to be authenticated may be authenticated by the server according to performance parameters of the terminal device if the i th authentication step is a performance parameter authentication step.

For example performance parameters may include charging time conversation time conversation quality standby time signal receiving capability and or signal receiving sensitivity. The server may compare performance parameters of a terminal device to be authenticated with those of an authentic terminal device of the same model as the terminal device to be authenticated thus determining whether the terminal device to be authenticated is an authentic product.

The terminal device to be authenticated may send performance parameters along with a call request when sending the call request to the server or send performance parameters to the server before sending the call request to the server or send performance parameters to the server after sending the call request to the server.

In another embodiment the terminal device to be authenticated is authenticated by the server according to basic information relating to the terminal device and an order database if the i th authentication step is an order authentication step.

For example the order database may include basic information relating to at least one terminal device. The basic information may include a unique identification of the terminal device a CPU serial number a Bluetooth serial number a wireless LAN card address a media access control MAC address and or a device serial number. The unique identification of the terminal device may be an IMEI number. In this embodiment the i th authentication step may include the following substeps.

In a first substep the server may query whether the order database includes basic information matching basic information relating to the terminal device to be authenticated.

In a second substep the server may determine the i th authentication step to be successful if the order database includes basic information matching basic information relating to the terminal device to be authenticated.

Conversely the server may determine the i th authentication step to fail if the order database includes no basic information matching basic information relating to the terminal device to be authenticated. That is the terminal device to be authenticated is deemed to be a counterfeit.

The terminal device to be authenticated may send basic information along with a call request when sending the call request to the server or send basic information to the server before sending the call request to the server or send basic information to the server after sending the call request to the server.

In another embodiment the terminal device to be authenticated is authenticated by the server according to a geographical position corresponding to the terminal device and to a unique identification if the i th authentication step is a geographical position authentication step.

For example the geographical position corresponding to the terminal device to be authenticated may be sent from the terminal device to be authenticated to the server or be acquired by the server according to an Internet Protocol IP address corresponding to the terminal device to be authenticated. The unique identification may be an IMEI number. In this embodiment the i th authentication step may include following substeps.

In a first substep the server may detect whether the terminal device to be authenticated meets the predetermined condition.

In a second substep the server may determine the i th authentication step to be successful if the terminal device to be authenticated does not meet the predetermined condition.

For example the predetermined condition may be receiving within a scheduled time frame a call request sent from a terminal device to be authenticated from different geographical positions but having the same unique identification of the terminal device to be authenticated. When call requests are sent to the server by terminal devices with the same unique identification from different geographical positions the different geographical positions may be a plurality of geographical positions far away from one another for example different cities within a short time frame as one unique identification is only mapping to one terminal device there is at most one authentic product in terminal devices to be authenticated in different geographical positions.

Thereafter the server may send a prompt message to terminal devices to be authenticated in different geographical positions. The prompt message is configured to alert users that the terminal devices may be counterfeit products and may request users to conduct further authentication in an after sales service center.

In step if the i th authentication step succeeds and i n the server increases i by 1 i.e. i i 1 and returns to step .

If the i th authentication step succeeds and i n the terminal device to be authenticated may be continued to be authenticated by the server in an i 1 th authentication step. The server updates i i 1 executes the steps to again and authenticates the terminal device in the i 1 th authentication step.

The process in which the server authenticates the terminal device in the i 1 th authentication step is the same as that in which the server authenticates the terminal device in the i th authentication step described above in steps to and is not repeated herein.

An indication of authentication failure may be sent to the terminal device to be authenticated if the i th authentication step fails in authentication.

The authentication failure indication indicates that one or more of the configuration parameters performance parameters basic information or geographical position relating to the terminal device to be authenticated do not satisfy requirements for an authentic product.

An indication of authentication success may be sent to the terminal device to be authenticated if the i th authentication step succeeds in authentication and i n.

The authentication success indication indicates that the terminal device to be authenticated succeeds in authentication according to all n authentication steps configuration parameters performance parameters basic information or geographical position relating to the terminal device to be authenticated and satisfies requirements for an authentic product.

In the method if the terminal device to be authenticated is determined to be an authentic product the terminal device to be authenticated may meet the following conditions.

First both the terminal device to be authenticated and the server complete all n authentication steps in a predetermined order.

Second in each authentication step the terminal device to be authenticated succeeds in initiating the authentication step.

Third in each authentication step the terminal device to be authenticated succeeds in the authentication.

Otherwise the terminal device to be authenticated may be considered to be a counterfeit product or suspected to be a counterfeit product.

Correspondingly the terminal device to be authenticated receives the authentication results sent from the server.

In step the terminal device to be authenticated displays the authentication results thereby informing the user whether the terminal device to be authenticated is an authentic product.

In step the terminal device acquires a user account associated with the terminal device to be authenticated.

For example the user account is an account created by the user in advance for logging in the server. Also for example the user account may be a cloud service account. The terminal device to be authenticated and the user account may both belong to the user and have a mapping relationship between them.

For example the user account may be sent initiatively by the terminal device to be authenticated to the server or be sent to the server by the terminal device to be authenticated after receiving an account acquisition instruction sent from the server. Also for example the server may send an account acquisition instruction to the terminal device if the terminal device succeeds in authentication according to all n authentication steps. That is according to the authentication result the terminal device to be authenticated is an authentic product.

Correspondingly the server receives the user account sent from the terminal device to be authenticated.

In step the server stores a mapping relation between the user account and the authentication results.

For example a mapping relation between the user account and the authentication results may be stored by the server after generating the authentication results corresponding to the terminal device. In some embodiments the server may also store various information relating to the terminal device corresponding to the user account including for example associated information configuration parameters performance parameters basic information unique identification and or authentication result of each authentication step.

In addition the server may directly store a mapping relation between the user account and the authentication results in the terminal device or store the mapping relation between the user account and the authentication results in other servers. For example the server may store the mapping relation in a cloud server.

In step the server receives an authentication query request including a user account from the terminal device.

For example the server may store a mapping relation between the user account and the authentication results. A user may log in the server using a user account through an application program or a browser in any terminal device. In the meantime the terminal device may send to the server an authentication query request including the user account.

For example after receiving an authentication query request including a user account the server queries in the server whether an authentication result corresponding to the user account received is stored in the server.

The server may store no authentication result corresponding to the user account. Or authentication results of successful authentication corresponding to the user account exist in the server. It is also possible that authentication results of authentication failure corresponding to the user account exist in the server.

If an authentication result corresponding to the user account is stored in the server this means that an interaction in the foregoing authentication step is conducted between the terminal device to be authenticated in association with the user account and the server. Further when the authentication result is a successful authentication this means that the terminal device to be authenticated in association with the user account is an authentic product. When the authentication result is an authentication failure this means that the terminal device to be authenticated in association with the user account is a counterfeit product or suspected to be a counterfeit product.

If an authentication result corresponding to the user account is not stored in the server this means that an interaction in the foregoing authentication step is not conducted between the terminal device to be authenticated in association with the user account and the server. For example the user may have downloaded a counterfeit client application in previous authentication processes and the counterfeit client application bypasses authentication steps of the server and directly feeds back to the user an authentication result showing that the terminal device is an authentic product.

In step the server responds to the authentication query request by sending the authentication results to the terminal device if the authentication results are available.

After receiving a response corresponding to the authentication query request the terminal device may provide the authentication result to the user. In some embodiments the server may further feed back to the terminal device various information relating to the terminal device to be authenticated including for example associated information configuration parameters performance parameters basic information unique identification and or authentication results of each authentication step.

In addition if the terminal device does not receive a response corresponding to the authentication query request or receives a response indicating that no authentication result corresponding to the user account exists in the server this means that the terminal device to be authenticated bypasses the foregoing authentication steps and the terminal device to be authenticated is a counterfeit product. Under the circumstances the terminal device may provide users with a prompt message indicating that the terminal device to be authenticated is a counterfeit product.

In some embodiments the client application running in the terminal device to be authenticated may adopt Native C to compile authentication steps and perform reinforcement through reinforcement technologies such as code encryption code compression and the like thus preventing simulating authentication steps by means of decompilation and the like or uploading false parameters to the server.

The cryptograph generation module is configured to generate an encrypted message corresponding to an i th authentication step which is an authentication step among all n authentication steps arranged in a predetermined order for authenticating a terminal device where 1 i n.

The cryptograph sending module is configured to send the encrypted message to the terminal device to be authenticated.

The request receiving module is configured to receive a call request sent from the terminal device to be authenticated for initiating the i th authentication step.

The authentication execution module is configured to execute the i th authentication step if the call request is a call request initiated according to an encrypted message corresponding to the i th authentication step.

The cryptograph generation module is also configured to increase i by 1 i.e. i i 1 and execute the step of generating an encrypted message corresponding to the i th authentication step when the i th authentication step succeeds in authentication and i n.

The first sending module is configured to send an indication of authentication failure to the terminal device to be authenticated if the i th authentication step fails in authentication.

The second sending module is configured to send an indication of authentication failure success to the terminal device to be authenticated if the i th authentication step succeeds in authentication and i n.

The cryptograph generation module is configured to generate an encrypted message corresponding to an i th authentication step which is an authentication step among n authentication steps arranged in a predetermined order for authenticating a terminal device where 1 i n.

The cryptograph generation module is also configured to encrypt an unencrypted message by using a private key and generate an encrypted message corresponding to the i th authentication step.

When 1 i n the unencrypted message may include associated information relating to the terminal device to be authenticated and a step number corresponding to the i th authentication step.

When i 1 the unencrypted message may include associated information relating to the terminal device to be authenticated. When i 2 the unencrypted message may include associated information relating to the terminal device to be authenticated and a step number corresponding to an i 1 th authentication step which has been performed successfully.

The cryptograph sending module is configured to send the encrypted message to the terminal device to be authenticated.

The request receiving module is configured to receive a call request sent from the terminal device to be authenticated for initiating the i th authentication step.

The authentication execution module is configured to execute the i th authentication step if the call request is initiated according to an encrypted message corresponding to the i th authentication step.

The authentication execution module includes a cryptograph detection submodule a cryptograph reading submodule a cryptograph decryption submodule a number determination submodule a number detection submodule and an authentication execution submodule

The cryptograph detection submodule is configured to detect whether the call request includes the encrypted message corresponding to the i th authentication step.

The cryptograph reading submodule is configured to retrieve the encrypted message if the call request includes the encrypted message.

The cryptograph decryption submodule is configured to decrypt the encrypted message by using the private key and acquire the unencrypted message.

The number determination submodule is configured to determine a step number corresponding to the i th authentication step according to contents of the unencrypted message.

The number detection submodule is configured to detect whether an actual step number initiated by the call request matches a step number corresponding to the i th authentication step.

The authentication execution submodule is configured to execute the i th authentication step if the actual step number matches a step number corresponding to the i th authentication step.

In some embodiments the authentication execution module also includes a message reading submodule and a time detection submodule

The message reading submodule is configured to retrieve a timing message included in the unencrypted message if the unencrypted message also includes the timing message.

The time detection submodule is configured to detect according to the timing message whether a time at which the call request is received is within a valid time frame.

The authentication execution submodule is configured to execute the i th authentication step if the time at which the call request is received is within the valid time frame and the actual step number matches the step number corresponding to the i th authentication step.

The authentication execution submodule includes a first authentication submodule a second authentication submodule a third authentication submodule and or a fourth authentication submodule .

The first authentication submodule is configured to authenticate the terminal device according to configuration parameters of the terminal device if the i th authentication step is a configuration parameter authentication step.

The second authentication submodule is configured to authenticate the terminal device according to performance parameters of the terminal device if the i th authentication step is a performance parameter authentication step.

The third authentication submodule is configured to authenticate the terminal device according to basic information relating to the terminal device and an order database if the i th authentication step is an order authentication step. The order database includes basic information relating to at least one terminal device.

In some embodiments the third authentication submodule is also configured to query whether basic information matched with basic information relating to the terminal device to be authenticated in the order database and to determine the i th authentication step to be successful if the basic information is matched with basic information relating to the terminal device to be authenticated.

The fourth authentication submodule is configured to authenticate the terminal device according to a geographical position corresponding to the terminal device and to a unique identification of the terminal device if the i th authentication step is a geographical position authentication step.

In some embodiments the fourth authentication submodule is also configured to detect whether the terminal device to be authenticated meets a predetermined condition. The predetermined condition includes receiving within a scheduled time frame a call request sent from the terminal device from different geographical positions but having the same unique identification of the terminal device to be authenticated. The fourth authentication submodule is also configured to determine the i th authentication step to be successful if the terminal device to be authenticated does not meet the predetermined condition.

The cryptograph generation module is also configured to increase i by 1 i.e. i i 1 and execute the step of generating an encrypted message corresponding to the i th authentication step when the i th authentication step succeeds and i n.

The first sending module is configured to send an indication of authentication failure to the terminal device to be authenticated if the i th authentication step fails in authentication.

The second sending module is configured to send an indication of authentication success to the terminal device to be authenticated if the i th authentication step succeeds and i n.

In some embodiments the device may include a query receiving module a result query module and a request response module .

The query receiving module is configured to receive an authentication query request including a user account.

The result query module is configured to query whether authentication results corresponding to the user account exist.

The request response module is configured to respond to the authentication query request based on the authentication results if the authentication results exist.

The cryptograph receiving module is configured to receive an encrypted message sent from the server and corresponding to an i th authentication step which is an authentication step of n authentication steps arranged in a predetermined order for authenticating a terminal device where 1 i n.

The request sending module is configured to send to the server a call request for initiating the i th authentication step according to the encrypted message.

The result receiving module is configured to receive an indication of authentication failure or success sent from the server.

The cryptograph receiving module is configured to receive an encrypted message sent from a server and corresponding to an i th authentication step which is an authentication step among n authentication steps arranged in a predetermined order for authenticating a terminal device where 1 i n.

The request sending module is configured to send to the server a call request for initiating the i th authentication step according to the encrypted message.

The request generation submodule is configured to generate a call request for initiating the i th authentication step where the call request includes an encrypted message received from the server corresponding to the i th authentication step.

The encrypted message is generated by the server by encrypting an unencrypted message by using a private key.

In one exemplary embodiment when 1 i n the unencrypted message includes information relating to the terminal device to be authenticated and a step number corresponding to the i th authentication step.

In one exemplary embodiment when i 1 the unencrypted message includes information relating to the terminal device to be authenticated. When i 2 the unencrypted message includes information relating to the terminal device to be authenticated and a step number corresponding to an i 1 th authentication step which has been executed successfully.

The result receiving module is configured to receive an indication indicating authentication failure or success sent from the server.

In some embodiments the device also includes an account acquiring module an account sending module and a result feedback module .

The account acquiring module is configured to acquire a user account associated with the terminal device to be authenticated.

The result feedback module is configured to receive authentication results when the server succeeds in querying the authentication results corresponding to the user account.

The server may include an anti counterfeiting authentication device which may be implemented to be a part or all of the server by means of software or hardware or a combination of both. The anti counterfeiting authentication device may be an anti counterfeiting authentication device provided by embodiments as shown in or .

The terminal device to be authenticated is connected to the server through a wired network or a wireless network.

The terminal device to be authenticated may include an anti counterfeiting authentication device which may be implemented to be a part or all of the terminal device to be authenticated by means of software or hardware or a combination of both. The anti counterfeiting authentication device may be an anti counterfeiting authentication device provided by embodiments as shown in or .

Referring to the terminal device may include one or a plurality of components as below a processor component a memory a power supply component a multimedia component an audio component an input output I O interface a sensor component and a communication component . The person skilled in the art should appreciate that the structure of the terminal device as shown in does not intend to limit the terminal device . The terminal device may include more or less components or combine some components or other different components.

The processor component usually controls the overall operation of the device for example display telephone call data communication and operation associated with camera operation and record operation. The processor component may include one or a plurality of processors for executing instructions so as to complete steps of above method in part or in whole. In addition the processor component may include one or a plurality of modules for the convenience of interaction between the processor component and other components. For example the processor component may include a multimedia module for the convenience of interaction between the multimedia component and the processor component .

The memory is configured to store data of different types so as to support the operation of the terminal device . Examples of the data include any application program or approach directive for operation of the terminal device including contact data phonebook data message picture and video etc. The memory is also configured to store programs and modules. The processing component performs various functions and data processing by operating programs and modules stored in the memory . The memory may be realized by volatile or non volatile memory device of any type or combination thereof for example static random access memory SRAM electrically erasable programmable read only memory EEPROM erasable programmable read only memory EPROM programmable read only memory PROM read only memory ROM magnetic memory flash memory magnetic disk or optical disk.

The power supply component is configured to provide power for components of the terminal device . The power supply component may include a power management system one or a plurality of power supplies and other components associated with generation management and power distribution of the terminal device .

The multimedia component includes a screen between the terminal device and a user and for providing an output interface. In some embodiments the screen may include a liquid crystal display LCD and or a touch panel TP . If the screen includes a touch panel the screen may be realized as a touch screen for receiving input signal from users. The touch panel includes one or a plurality of touch sensors for sensing gestures on the touch panel for example touching and sliding etc. The touch sensor not only can sensor trip boundary of touching or sliding but also can detect the duration and pressure related to the touching or sliding operation. In some embodiments the multimedia component includes a front facing camera and or a rear facing camera. When the terminal device is under an operation mode for example capture mode or video mode the front facing camera and or the rear facing camera may receive external multimedia data. Each front facing camera and rear facing camera may be a fixed optical lens system or have focal length and optical zoom capacity.

The audio component is configured to output and or input audio signal. For example the audio component includes a microphone configured to receive an external audio signal when the terminal device is under an operation mode such as a call mode a record mode and a speech recognition mode. The audio signal received may be further stored in the memory or sent out by the communication component . In some embodiments the audio component also includes a loudspeaker for outputting audio signal.

The I O interface provides interface for the processor component and peripheral interface modules the peripheral interface modules may be a keyboard a click wheel and buttons etc. These buttons may include but not limited to home button volume button start button and locking button.

The sensor component includes one or a plurality of sensors for providing the device with state evaluation from all aspects. For example the sensor component may detect the on off state of the terminal device relative positioning of components for example the components are the displayer and keypads of the terminal device the sensor component also may detect the position change of the terminal device or a component thereof the presence or absence of users touch on the terminal device the direction or acceleration deceleration of the terminal device and temperature variation of the terminal device . The sensor component may also include a proximity detector which is configured to detect the presence of nearby objects without any physical contact. The sensor component may also include an optical sensor for example CMOS or CCD image sensor for imaging. In some embodiments the sensor component may also include an acceleration sensor a gyro sensor a magnetic sensor a pressure sensor or a temperature sensor.

The communication component is configured to facilitate wired communication or wireless communication between the terminal device and other equipment. The terminal device is available for access to wireless network based on communication standards for example WiFi 2G or 3G or combination thereof. In an exemplary embodiment the communication component receives by means of a broadcast channel the broadcast signal or information from external broadcast management systems. In an exemplary embodiment the communication component also includes a near field communication NFC module for promoting short range communication. For example the NFC module may be realized on the basis of Radio Frequency Identification RFID Technology Infrared Data Association IrDA Technology Ultra wide Bandwidth UWB Technology Bluetooth BT Technology and other technologies.

In exemplary embodiments the device may be implemented with one or a plurality of application specific integrated circuits ASIC digital signal processors DSP digital signal processing equipment DSPD programmable logic devices PLD field programmable gate arrays FPGA controllers microcontrollers microprocessors or other electronic components for performing the above described methods.

In exemplary embodiments there is also provided a non transitory computer readable storage medium including instructions such as included in the memory and executable by the processors of the terminal device for performing the above described methods. For example the non transitory computer readable storage medium may be a read only memory ROM a random access memory RAM a CD ROM a magnetic tape a floppy disk an optical data storage device etc.

It should be understood by those skilled in the art that the above described methods devices and modules can each be implemented through hardware or software or a combination of hardware and software. One of ordinary skill in the art will also understand that multiple ones of the above described modules may be combined as one module and each of the above described modules may be further divided into a plurality of sub modules.

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed here. This application is intended to cover any variations uses or adaptations of the invention following the general principles thereof and including such departures from the present disclosure as come within known or customary practice in the art. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

It should be understood that the present disclosure is not limited to the exact construction that has been described above and illustrated in the accompanying drawings and that various modifications and changes can be made without departing from the scope thereof. It is intended that the scope of the invention should only be limited by the appended claims.


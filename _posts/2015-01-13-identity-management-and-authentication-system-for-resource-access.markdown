---

title: Identity management and authentication system for resource access
abstract: A system that authorizes access to a resource by a client validates the client and generates a Security Assertion Markup Language (“SAML”) assertion for the valid client. The system then sends an access request with the SAML assertion to a OAuth server. In response, the OAuth server returns an access token for the resource to the client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09467457&OS=09467457&RS=09467457
owner: Oracle International Corporation
number: 09467457
owner_city: Redwood Shores
owner_country: US
publication_date: 20150113
---
One embodiment is directed generally to a computer system and in particular to a computer system that provides identity management and authentication in response to a request for resources.

An identity management system is an information system or a set of technologies that can be used for enterprise or cross network identity management. Identity management describes the management of individual identities and the authentication authorization roles and privileges within or across system and enterprise boundaries with the goal of increasing security and productivity while decreasing cost downtime and repetitive tasks. One aspect of identity management is single sign on SSO . One standard that is particularly useful in the field of identity management is OAuth. 

OAuth is an open standard for authorization. An indirect effect of authorization is authentication. OAuth allows users to share their private resources e.g. photos videos contact lists etc. stored on one site with another site without having to hand out their credentials typically supplying username and password tokens instead. Each token grants access to a specific site for specific resources and for a defined duration. This allows a user to grant to a third party site access to their information stored with another service provider without sharing their access permissions or the full extent of their data. For example a token might grant access to a video editing site for videos from a specific album for the next two hours.

One embodiment is a system that authorizes access to a resource by a client. The system validates the client and generates a Security Assertion Markup Language SAML assertion for the valid client. The system then sends an access request with the SAML assertion to a OAuth server. In response the OAuth server returns an access token for the resource to the client.

One embodiment is a OAuth based single sign on SSO authentication system that uses Security Assertion Markup Language SAML as assertion grants. Therefore the integration client which is used to integrate different identity management platforms merely needs to provide valid SAML assertions. Users from different identity management platforms can then access the resources protected by a OAuth Server and the SSO function is implemented.

System includes a bus or other communication mechanism for communicating information and a processor coupled to bus for processing information. Processor may be any type of general or specific purpose processor. System further includes a memory for storing information and instructions to be executed by processor . Memory can be comprised of any combination of random access memory RAM read only memory ROM static storage such as a magnetic or optical disk or any other type of computer readable media. System further includes a communication device such as a network interface card to provide access to a network. Therefore a user may interface with system directly or remotely through a network or any other method.

Computer readable media may be any available media that can be accessed by processor and includes both volatile and nonvolatile media removable and non removable media and communication media. Communication media may include computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media.

Processor is further coupled via bus to a display such as a Liquid Crystal Display LCD . A keyboard and a cursor control device such as a computer mouse are further coupled to bus to enable a user to interface with system .

In one embodiment memory stores software modules that provide functionality when executed by processor . The modules include an operating system that provides operating system functionality for system . The modules further include an authentication module for providing authentication for resource access and all other functionality disclosed herein. System can be part of a larger system such as a webserver and any other associated functionality. Therefore system can include one or more additional functional modules to include the additional functionality. In one embodiment the additional functionality is an identity management platform such as Oracle Identity Management from Oracle Corp. or Oracle Communications Services Gatekeeper OCSG from Oracle Corp. A database is coupled to bus to provide centralized storage for modules and and store profiles identities protected resources etc.

Many customers typically desire to integrate their existing identity management platform to a new deployed system and use a OAuth server to resolve the single sign on issue. A known solution is to build a private interface between the identity management platform and the OAuth server. However this requires modifications to both the identity management platform and the OAuth server and may lead to an OAuth server that can support only a few specific identity management platforms.

In contrast embodiments provide a generic mechanism for transporting assertions during interactions with a token endpoint and rules for the content and processing of SAML assertions so that an unmodified OAuth server can be used. Embodiments further provide an enhanced security profile by using derived values such as signatures or keyed hash message authentication codes HMACs as well as facilitating the use of OAuth 2.0 in client server integration scenarios where the end user may not be present.

As discussed OAuth is an open standard to authorization. OAuth provides client applications with a secure delegated access to server resources on behalf of a resource owner. It specifies a process for resource owners to authorize third party access to their server resources without sharing their credentials. Designed specifically to work with Hypertext Transfer Protocol HTTP OAuth essentially allows access tokens to be issued to third party clients by an authorization server with the approval of the resource owner or end user. The client then uses the access token to access the protected resources hosted by the resource server.

OAuth 2.0 is the next generation of the OAuth protocol and is not backwards compatible with the original OAuth i.e. OAuth 1.0 . OAuth 2.0 focuses on client developer simplicity while providing specific authorization flows for web applications desktop applications mobile phones and living room devices. The specification and requirements for the OAuth 2.0 framework are disclosed by the Internet Engineering Task Force IETF in for example Request for Comments 6749 and are hereby incorporated by reference.

Embodiments use Security Assertion Markup Language SAML assertions as authorization grants with OAuth 2.0. SAML is an Extensible Markup Language XML based open standard data format for exchanging authentication and authorization data between parties in particular between an identity provider and a service provider. The SAML version 2.0 specification the SAML specification was approved as an OASIS Standard in March 2005 the disclosure of which is hereby incorporated by reference.

The SAML specification defines three roles the principal typically a user the identity provider IdP and the service provider SP . In the use case addressed by SAML the principal requests a service from the service provider. The service provider requests and obtains an identity assertion from the identity provider. On the basis of this assertion the service provider can make an access control decision. An access control decision is a decision on whether to perform some service for the connected principal.

Before delivering the identity assertion to the SP the IdP may request some information from the principal such as a user name and password in order to authenticate the principal. SAML specifies the assertions between the three parties in particular the messages that assert identity that are passed from the IdP to the SP. In SAML one identity provider may provide SAML assertions to many service providers. Similarly one SP may rely on and trust assertions from many independent IdPs.

SAML does not specify the method of authentication at the identity provider. It may use a username and password or other form of authentication including multi factor authentication. A directory service such as Lightweight Directory Access Protocol LDAP Remote Authentication Dial In User Service RADIUS and Active Directory which allows users to log in with a user name and password is a typical source of authentication tokens e.g. passwords at an identity provider.

The network elements of include an integration client which is an application making protected resource requests on behalf of the resource owner and with its authorization. Client corresponds to the Client disclosed in the OAuth specification. Identity provider is the third party identity server which authorizes the resource owner. Authorization server is a server that issues access tokens to client after successfully authenticating the resource owner and obtaining authorization. Authorization server corresponds to the Authorization Server disclosed in the OAuth specification. Data service server is a server hosting the protected resources and capable of accepting and responding to protected resource requests using access tokens. Data service server corresponds to the Resource Server disclosed in the OAuth specification. Any of the network elements of can be implemented by server of .

At between identity provider and authorization server the partner relationship is established by synchronizing the client s metadata and related certificates.

At client sends an SAML assertion authorization request to identity provider and in response is issued a valid SAML assertion with a digital signature at .

At authorization server validates the SAML assertion and client metadata and then issues the client a valid access token at .

In one embodiment the functionality of authentication module of is implemented as a web servlet on identity provider of . A servlet is a Java programming language class used to extend the capabilities of a server. Although servlets can respond to any types of requests they are commonly used to extend the applications hosted by web servers so they can be considered analogous to Java applets that run on servers instead of in web browsers. Servlets are typically used to process or store data that was submitted from a HyperText Markup Language HTML form provide dynamic content such as the results of a database query and manage state information that does not exist in the stateless HTTP protocol such as filling the articles into the shopping cart of the appropriate customer.

Technically a servlet is a Java class in Java EE that conforms to the Java Servlet application programming interface API a standard for implementing Java classes which respond to requests. Servlets can in general communicate over any client server protocol but they are most often used with the HTTP protocol.

A software developer may use a servlet to add dynamic content to a web server using the Java platform. The generated content is commonly HTML but may be other data such as Extensible Markup Language XML . Servlets can maintain state in session variables across many server transactions by using HTTP cookies or uniform resource locator URL rewriting.

To deploy and run a servlet a web container is used. A web container also referred to as a servlet container is essentially the component of a web server that interacts with the servlets. The web container is responsible for managing the lifecycle of servlets mapping a URL to a particular servlet and ensuring that the URL requester has the correct access rights.

The servlet API contained in the Java package hierarchy javax.servlet defines the expected interactions of the web container and a servlet. The basic servlet package defines Java objects to represent servlet requests and responses as well as objects to reflect the servlet s configuration parameters and execution environment. The package javax.servlet.http defines HTTP specific subclasses of the generic servlet elements including session management objects that track multiple requests and responses between the web server and a client. Servlets may be packaged in a Web application Archive WAR file as a web application.

AT further includes an Enterprise JavaBeans EJB stub which is an EJB client to apply access token or reload configuration e.g. Certificates from the OAuth service in NT . An SAML assertion validation is a utility to verify SAML assertion. A Java Message Service JMS listener listens to SAML related configuration updates and reloads configurations e.g. Certificates from NT .

NT includes OAuth service which provides most of the logic described herein to provide authorization server functions. EJB skeleton is an EJB home to issue access token or reload configuration e.g. Certificates . An SAML MBean provides management to add list remove the identity provider s certificate and restricted audience URLs. A JMS publisher publishes SAML related configuration updates to AT .

At the request is made for an SAML assertion from client to servlet . Table 1 below provides a description of request parameters in accordance with one embodiment. In one embodiment base64url is used to encode messages described herein. Base64url is a known encoding scheme disclosed in RFC4648.

At a response to the request is received. Table 2 below provides a description of response parameters in accordance with one embodiment.

At the validate assertion is requested and at the assertion is validated. The following pseudo code is an example SAML assertion validation in accordance with one embodiment 

At the signature validation checks if the digital signature in the SAML assertion is the same as the preloaded signature and also if it has not expired.

At assertion conditions are checked to determine if the current time does not exceed the assertion permission period.

At the assertion subject is checked to determine if the current time does not exceed the SubjectConfirmation permission period.

If the assertion passes the assertion validation an access token is assigned to the client so that the client can access the resources protected by the OAuth server.

Table 3 below provides a description of checkpoints and processing rules when validating an SAML Assertion in accordance with one embodiment.

At the system sends an HTTP request with the SAML assertion client ID and applied resource to the OAuth server.

As disclosed embodiments expand the OAuth server authentication ability and provides the standard interface to any identity management platform so that it can easily integrate with the existing identity management platform to implement the single sign on function.

Several embodiments are specifically illustrated and or described herein. However it will be appreciated that modifications and variations of the disclosed embodiments are covered by the above teachings and within the purview of the appended claims without departing from the spirit and intended scope of the invention.


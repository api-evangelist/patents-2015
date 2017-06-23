---

title: Social network honeypot
abstract: The invention is a method and system for detecting attackers that are interested in attacking an organization's infrastructure during the reconnaissance phase of an Advanced Persistent Threat (APT). APTs are very sophisticated attacks and incorporate advanced methods for evading current security mechanisms. Therefore, the present invention uses an innovative social network honeypot.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09509716&OS=09509716&RS=09509716
owner: Deutsche Telekom AG
number: 09509716
owner_city: Bonn
owner_country: DE
publication_date: 20150430
---
The invention is from the field of information technology security. Specifically the invention is directed to protecting the servers computers etc. of an organization and the data they contain from Advanced Persistent Threats APTs that could ultimately result in a cyber attack on these resources.

Publications and other reference materials referred to herein are numerically referenced in the following text and respectively grouped in the appended Bibliography which immediately precedes the claims.

Advanced Persistent Threats APTs on an organization usually follow a methodological process for conducting an attack. This process consists of the following main steps that are shown schematically in 1 Reconnaissance 2 Initial Exploitation 3 Gaining Access and establishing Command Control 4 Privilege Escalation 5 the actual attack Exfiltration Subversion and 6 Maintain Persistence and Covering tracks.

Detecting an APT at the Reconnaissance phase is very difficult since usually the activity is performed out of the organization s premises and without direct interaction with the organizational resources. At some point the activity reaches a specific point within the organization the entry point to the organization to the next phases.

It is a purpose of the present invention to provide a method of detecting APTs at the Reconnaissance phase.

In a first aspect the invention is a method for detecting attackers that are interested in attacking an organization s infrastructure during the reconnaissance phase of an Advanced Persistent Threat APT . The method comprises the following steps 

In embodiments of the method of the invention the artificial profiles are created by a human expert using data collected from social networks.

In embodiments of the method of the invention after an artificial profile is created by a human expert dedicated software in modules of a dedicated system manage the evolution of the artificial profile and monitor attempts of third parties to contact the owner of the artificial profile.

In embodiments of the method of the invention the dedicated software in the modules of the dedicated system is adapted to detect an attacker that performs social network organizational mining by looking for new profiles that are attempting to connect to as many common friends in a social network as possible.

In embodiments of the method of the invention the dedicated software in the modules of the dedicated system is adapted to provide detection with minimal false alarms rate.

In embodiments of the method of the invention the dedicated software in the modules of the dedicated system is adapted to allow an organization to 

In embodiments of the method of the invention actual user profiles for use in creating the artificial profiles are extracted from social networks in at least one of the following ways searching for profiles by applying an efficient crawling of the organization s own network and using homing social bots.

In embodiments of the method of the invention the process of generating a new artificial profile is supported by a wizard that follows the following workflow selecting address updating basic profile information generating working history generating education history reviewing and saving the new artificial profile.

In a second aspect the invention is a system for detecting attackers that are interested in attacking an organization s infrastructure during the reconnaissance phase of an Advanced Persistent Threat APT . The system comprises 

In embodiments of the system of the invention each plugin in the SN Crawler module comprises software adapted to extract actual SN profiles from a designated SN and insert the extracted actual SN profiles into the Profiles Database.

In embodiments of the system of the invention the Profiles Database contains actual profiles extracted by the plugins in the SN Crawler module.

In embodiments of the system of the invention the Artificial Profile Generator module comprises software adapted to generate artificial profile records using actual profiles in the Profiles Database module.

In embodiments of the system of the invention the Profile Manager module comprises software adapted to create and integrate a profile in a selected SN from the data in a profile record to identify the best location in the target social network for seeding to propose profiles for sending friendship requests to create connections between the artificial profile and other members in the organization and to determine which new friendship requests to accept.

In embodiments of the system of the invention the Profile Monitoring module comprises monitoring software adapted to collect the events relating to the artificial profiles and email accounts and notifies the profile manager of every event.

In embodiments of the system of the invention the Email Monitoring module comprises detectors software and scanning logic adapted to collect emails sent to specific honeypot mailboxes to which it has been granted access to store the email content including timestamp sender recipients subject content attachments and URLs in a database and to scan and detect any attachments and URLs for possible threats.

In embodiments of the system of the invention the Management GUI module comprises software adapted to perform reoccurring scanning of previous attachments and URLs collected and stored by the Email Monitoring module.

All the above and other characteristics and advantages of the invention will be further understood through the following illustrative and non limitative description of embodiments thereof with reference to the appended drawings.

The invention is a method and system for detecting attackers that are interested in attacking an organization s infrastructure during the reconnaissance phase of an Advanced Persistent Threat APT . APTs are very sophisticated attacks and incorporate advanced methods for evading current security mechanisms. Therefore the present invention uses an innovative social network honeypot.

During the reconnaissance phase attackers try to find the appropriate organizational entry point in order to launch an advanced attack. One way to detect such an entry point is to collect information from social and professional networks. Information extracted from social networks SNs may include organizational structure position and roles within the organization e.g. administrator IT sales contact information e.g. email etc.

Once an attacker gains information about an insider a honeytoken profile the attacker will attempt to gain access to important assets by sending a malicious email to the honeypot email account. It is assumed that the attacker is a sophisticated person hence the malicious email will pass successfully through the organizational spam and phishing detection systems.

The invention is based on creating social network honeypots that will trap attempts to attack the organization through its employees. The social network honeypot framework may include 

The detection of a reconnaissance activity performed by an attacker will be performed by monitoring the activity of the artificial users in social networks SNs and by monitoring of the artificial users email account honeypot. Any traffic not generated by the social network honeypots framework is considered suspicious.

The invention is executed by a system whose purpose is to create and manage SN honeytoken accounts. In order to allow creating reliable accounts the system will collect SN data through a dedicated SN crawler. The collected data will be utilized by a human expert for creating the artificial accounts. Once a profile is created by the human expert the system manages its evolution posts profile updates connections etc. and monitors attempts of third parties to contact the artificial profile owner.

The system correlates access to SN artificial accounts with emails sent to the artificial users email account and inspects emails sent to the honeypot profile email account using for example malware detection techniques black white lists and reputation based analysis for detecting malicious URLs attachments or images.

The reason for crawling is to extract user profiles of the target organization or similar organizations from various social networks. Such information is utilized by the system for creating reliable artificial profiles. Two main methods can be used for crawling developer Application Programming Interface API and Web Scrapping.

Mining SN profiles is a challenging task mainly because social networks attempt to detect and block crawling activity. There are many different social networks and therefore varied content and APIs. Additionally it is difficult to extract detailed information on the profiles due to user privacy settings and some data items such as employment and education histories require some preprocessing and data normalization because of missing and unstructured data.

Two approaches can be used for extracting actual user profiles for use in creating the artificial profiles. The first is searching for profiles by applying an efficient crawling of the organization s own network. This is done by manually obtaining crawling seeds i.e. actual employees of the organization and then using heuristics to focus the crawling on the organization s employees. An example of a suitable heuristic is based on the Bayesian Promising factor as presented by Stern et al. 1 . A second approach is to use homing social bots Elishar et al. 2 . In this approach an artificial profile is used for intelligently sending friendship requests to real profiles within a target organization in order to gain direct connection to as many profiles related to the organization as possible and thus to be exposed to more detailed information and more profiles.

This is the main component of the system and it supports both manual and automatic artificial profile generation and wiring . Wiring profiles means connecting the artificial profile with other real and artificial profiles in the social network in order to generate a reliable profile.

The process of generating an artificial profile is supported by a wizard that follows the following workflow selecting address updating basic profile information generating working history generating education history and finally review and save the new artificial profile. Note that although the system of the invention mainly targets professional social networks such as LinkedIn and XING it is extendible to other social networks such as Facebook and additional information items such as groups of interests post etc. can be added to the system .

Each step of the wizard provides user suggestions based on statistics of existing crawled profiles and previously entered information from previous steps. For example if the system operator selects a profile of a person that lives in Italy the system will offer First Name Last Name City and more data items based on statistical information extracted from the crawled profiles.

In the same manner the system supports the manual creating of employment and education histories. In the first step the user selects the current job type of the employee. Then a timeline of work history is automatically generated based on statistics of existing profiles and previously entered information. The user selects companies and job types for the newly generated jobs. An educational timeline is generated based on statistics of existing profiles and the newly generated work history. The user selects the degrees and the educational institutes.

The system supports the fully automatic process of generating massive numbers of artificial profiles. This is done by using HoneyGen Berkovitch et al. 3 . HoneyGen was initially proposed for creating artificial database records based on real genuine records for exporting databases without compromising privacy for example for system tests . The method implemented by this HoneyGen tool is able to generate a high quality honeytoken which is defined as an artificial data item that is similar to real tokens such that even an expert in the relevant domain will not be able to distinguish between real tokens and the honeytoken. HoneyGen is a generic method for generating high quality honeytokens given a database.

The HoneyGen process is schematically depicted in . The input shown in the top line to the process includes a database of real profiles tokens crawled from the social network. The process is shown in the middle line of the figure. In the first step rules are mined and extracted from the database of real profiles. Examples of such rule are attribute dependencies identity allowed value set and more. Then based on the crawled data and the extracted rules a large number of artificial records is generated. This is done by transforming the data into a set of constraint satisfaction problems CSPs . In the last step the generated artificial profiles are sorted by similarity to real tokens in the input database. A likelihood score which indicates how real an artificial profile would appear to be to a person in the SN is assigned to each artificial profile using a likelihood rating function that considers the commonness of its combination of values. An example of a likelihood scoring function is one that given a set of attributes of a profile computes the probability of another attribute for example given that the profile is MALE 24 years old what is the probability that he has a PhD and then combines all probabilities computed for all attributes into one aggregated score. The output of the process shown in the bottom row is the honeytokens and their associated likelihood scores. This process is suited for tabular data. Therefore generating employment history and education history is not supported by this tool.

The artificial profile generator module provides an automatic process for generating authentic employment and education history. This method uses a genetic search algorithm from the Artificial Intelligence domain. The process starts with extracting the employment education history of previously crawled profiles. For the most popular job education titles the method then loops through the following until a good enough history is generated 

The profile manager module supports the process of wiring the artificial profile in the social network in order to create a reliable profile. An artificial profile can be wired manually with collaborating real employees on the organization. In addition the system is provided with an implemented method for identifying profiles that should be approached with a friendship request. This is performed based on the social bot organization intrusion strategy Fire 2013 4 which was modified by the inventors to take into account information extracted from crawled profiles such as characterization of the connections of a profile. This modified strategy is based on the following assumptions 

Each friendship request proposed by the algorithm will be approved by the system operator before sending the request.

The goal of the profile monitoring module is to monitor any activity in the social network involving the artificial profile. This module is configured with the information of the artificial profiles that needs to be monitored e.g. target social network profile id and it collects events related to the artificial profile such as friendship offers incoming messages comments and more. The available events depend on the specific social network API.

This module allows filtering the events by artificial accounts name timestamp social network and event type. The profile monitoring module is developed as a generic framework of plugins each of which is able to access accounts of a specific social network. Therefore the module is extendible to any social network of interest.

This module depending on the API provided by the specific social network can support managing the artificial profile and taking actions on the artificial profile that will affect the profile in the network. Such actions may include but are not limited to accepting friendship requests proposing friendship requests generated by an intelligent wiring algorithm sending posts and messages like and more. The screenshot in presents the profile monitoring module and its filtering capabilities.

As described herein above with respect to this module is responsible for monitoring two things the activities related to the artificial profile in the social networks and the activity in the email account that has been established for the artificial profile. In these two functions are portrayed as handled by two sub modules but in other embodiments two separate modules can be employed.

As said for each artificial profile created and planted in a social network a shadow organization or external email account is generated. The system comprises an email monitoring module whose goal is to monitor the honeypot mailboxes. schematically shows the main functions of the email monitoring module. This module is granted with access as a client application to the specific honeypot mailboxes it collects emails sent to these accounts Data Collection part in stores the email content including timestamp sender recipients subject content attachments and URLs in a database Persistency part in and scans and detects any attachments and URLs for possible threats Detection part in . This module is modular and supports the integration and custom development of new detectors and scanning logic. Detection results from all scanning engines are stored in the database as well.

A management service module provides graphical user interface for exploring the emails and scanning results as shown in the screenshot in . The management service also supports an important feature of this module. This feature is a reoccurring scanning of previous attachments and URLs e.g. once every month . The reason for this important feature is as follows. It might be the case that an attachment containing a zero day exploit was not detected by any of the detection engines at the time of sending the email. However after some time e.g. a few months the exploit becomes known to detection engines. Therefore historical attachments and URLs are scanned again the updated detection engines will identify the attachment as malicious and the organization will be able to know that there was a successful attempt to penetrate the organization.

Although embodiments of the invention have been described by way of illustration it will be understood that the invention may be carried out with many variations modifications and adaptations without exceeding the scope of the claims.


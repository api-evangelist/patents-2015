---

title: Method of controlling whether an uncompleted transaction applied against a database goes forward using either synchronous or asynchronous replication, or using either encrypted replication or unencrypted replication
abstract: Transactions are applied against a database on a transaction processing system. A tracking engine identifies an uncompleted transaction to be joined, joins the uncompleted transaction, and collects one or more non-durable attributes of the joined uncompleted transaction. Collected attributes of the joined uncompleted transaction are compared against rules in a rules engine that are applicable to the transaction to determine whether an applicable rule in the rules engine is met. The joined uncompleted transaction is allowed to go forward and be applied against the database of the transaction processing system using a synchronous replication engine when the applicable rule is met, and an asynchronous replication engine when the applicable rule is not met. Alternatively, the joined uncompleted transaction is allowed to go forward using a replication engine that replicates using encryption when the applicable rule is met, or replicates unencrypted when the applicable rule is not met.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09569473&OS=09569473&RS=09569473
owner: Gravic, Inc.
number: 09569473
owner_city: Malvern
owner_country: US
publication_date: 20151208
---
This application is related to U.S. application Ser. No. 14 962 475 concurrently filed on Dec. 8 2015 entitled Systems and methods to log non durable attributes of an uncompleted transaction so as to make such attributes durable and is also related to U.S. application Ser. No. 14 962 480 concurrently filed on Dec. 8 2015 entitled Method of controlling whether an uncompleted transaction applied against a database goes forward or is aborted and for modifying the uncompleted transaction so that it can go forward. 

Much of our daily life is augmented by computers. The many services upon which we depend our banking communications air and rail travel online shopping credit card and debit card purchases mail and package delivery and electric power distribution are all managed by computer applications.

In its simplest form as shown in a typical computer application is generally implemented as a computer program running in a computer . A computer program is basically a set of computer encoded instructions and is often called an executable because it can be executed by a computer. A computer program running in a computer is called a process and each process has a unique identification known to the computer. Many copies of the same computer program can be running in a computer as separately distinguishable processes.

With reference to an application often depends upon a database of information that the application maintains to record its current state. Often the information in the database is fundamental to the operation of the application to the decisions it makes and to its delivery of services to the end users.

The database may be stored in persistent storage such as a disk for durability it may be stored in high speed memory for performance or it may use a combination of these storage techniques. The database may be resident in the same computer as the application program it may be resident in another computer it may be implemented as an independent system or it may be distributed among many systems.

A database generally includes one or more files or tables though it may be just a random collection of unorganized data. Each file or table typically represents an entity set such as employees or credit cards. A file comprises records each describing a member of an entity set such as an employee. A table comprises rows that describe members of an entity set. A record comprises fields that describe attributes of the entity set such as salary. A row comprises columns that describe attributes of the entity set. In this specification files are equivalent to tables records are equivalent to rows and fields are equivalent to columns. 

With further reference to incoming end users generate events to be processed by the computer application. End users may be people other computer applications other computer systems or electronic devices such as electric power meters. In this specification the term end user means any entity that can influence an application and or can request or use the services the application provides.

An example of an incoming event from an end user is a request for a bank account balance. Another example is an alert that a circuit breaker in a power substation has just tripped. In some cases there may be no incoming event. For instance a computer application may on its own generate random events for testing other applications.

As shown in the application receives an event from an incoming end user . As part of the processing of this event the application may make certain modifications to its database .

The application can read the contents of rows in its database . As part of its processing it may read certain information from the database to make decisions. Based on the event it received from its incoming end user and the data in its database the application delivers certain services to its outgoing end users .

A service may be delivered by an application process as the result of a specific input from an end user such as providing an account balance in response to an online banking query. Another example of a service is the generation of a report either periodically or via an end user request.

Alternatively a service may be delivered spontaneously by the application program such as on a timed basis or when certain conditions occur. For instance an alarm may be generated to operations staff if the load being carried by a power transmission line exceeds a specified threshold.

The end users providing the input to the application may or may not be the same end users as those that receive its services.

An intercept library IL is a prior art program that is accessible to or that can be incorporated into an application program an executable . Incorporating a library into an executable does not require any changes to the executable. Thus the application program can be enhanced by the functions provided by the intercept library with no requirement to make code changes.

An intercept library may be statically linked or dynamically linked. A statically linked intercept library is separately compiled and is bound into the application program. When the application program is run as a process it includes the intercept library.

A dynamically linked intercept library DLL is separately compiled. It is linked to the application program when the application program is run as a process. Therefore the DLL can be changed easily without having to rebuild the application. It also can be shared by other processes.

One function that an intercept library can perform is to intercept function calls that the application makes to the operating system. The intercept library can add functionality to those calls or can otherwise enhance them in some desirable way.

An illustrative example of an intercept library is depicted in . An application process provides services to its end users . As part of its processing the application process typically makes one or more calls to operating system services . These calls for instance may be requests to read an incoming message to generate an outgoing message or to manipulate a database.

The intercept library positions itself between the application process and the operating system in such a way as to intercept operating system calls . Rather than the operating system function being invoked on a call by the application the intercept library is invoked instead. Thus when the application makes an operating system call for instance to read an incoming message or to issue an update to a database the intercept library not the operating system is invoked and processes the operating system call . The intercept library can modify the execution of the operating system function in any way that it has been programmed. The response to the modified operating system call then is returned to the application process .

For instance an intercept library might intercept all interprocess messages being sent to other applications to add information to those messages for enhanced processing. Alternatively it might intercept database calls read insert update delete to make decisions about the validity of the changes to modify the changes according to application rules to record the change activity or to log activity to a change log. For events or transactions the intercept library might invoke other application services such as security monitoring encryption and authorization.

There is an inherent risk when intercept libraries are used to enhance the functions of applications. If the compile of a statically linked intercept library into a process is erroneously omitted the functions intended for that library to provide will not be performed. Likewise if the linking of a dynamically linked intercept library into a process is erroneously omitted the functions that are intended for that library to provide will not be performed. Many applications comprise hundreds or even thousands of processes and such errors easily arise. Specialized utilities are designed to detect the omission of intercept libraries. Of course this in turn depends upon providing the utility with the correct and complete list of the use of intercept libraries a process which in and of itself is error prone.

Another challenge due to the use of intercept libraries is that they are inserted directly into the processing flow of the application. They therefore increase the path length of processing and consequently slow down execution. This issue is avoided by the use of joins another method taught by this invention. See Section 2.1.1 Joining an Audited Transaction. 

It also is important for purposes of this invention to note that intercept libraries typically cannot insert themselves into the processing of audited transactions that are initiated by certain system facilities such as SQL database transactions. These transactions often are not visible to the application. The issue is addressed via the use of implicit joining as described in Section 1.9.2 Implicit Joining and can be utilized to add functionality to such transactions.

An intermediate process IP is a prior art program that performs functions similar to those performed by intercept libraries. However instead of being implemented as a program or library that is bound into or linked to another program it is a stand alone process that is inserted between two other processes. There it can intercept the interprocess messages being exchanged between the two processes and can modify them in some useful way. Thus the application program can be enhanced by the functions provided by the intermediate process with no requirement to make changes to the application program.

One function that an intermediate process can perform is to intercept function calls that the application makes to the operating system. The intermediate process can add functionality to those calls or can otherwise enhance them in some desirable way.

An illustrative example of the use of an intermediate process is shown in . An application process provides services to its end users . As part of its processing the application process typically makes one or more calls to operating system services . These calls for instance may be requests to read an incoming message to generate an outgoing message or to manipulate a database.

An intermediate process is positioned between the application process and the operating system in such a way as to intercept interprocess messages representing operating system calls. Thus rather than the application directly making the operating system call the call can be modified by the intermediate process and a revised operating system call can be made to the operating system . The intermediate process can modify the execution of the operating system function in any way that it has been programmed. The response to the modified operating system call is returned to the application process .

For instance an intermediate process might intercept all interprocess messages being sent to other applications in order to add information to those messages. Alternatively it might intercept database calls read insert update delete to make decisions about the validity of the changes to modify the changes according to application rules to record the change activity or to log activity to a change log. For events or transactions the intercept library might invoke other application services such as security monitoring encryption and authorization.

There is an inherent risk in the use of intermediate processes to enhance the functions of applications. If the insertion of an intermediate process between two application processes is erroneously omitted the functions that are intended for the intermediate process to provide will not be performed. Many applications comprise hundreds or even thousands of processes and such errors easily arise.

Both intercept libraries and intermediate processes are prior art examples of adding or enhancing application processing without having to make code changes to the application. However they both can be accidentally omitted from the system configuration neither can intercept certain types of system transactions and they both add to the processing path length of the application.

In many applications changes to the database inserts updates deletes or changes to the database structure etc. are organized as audited transactions. An audited transaction is a delimited set of changes that either must all be made to a database or sent to an application or else none are. For instance a transaction in a banking application may transfer funds from one account to another. It applies a debit to one account a reduction in its value and an equal credit to another account an increase in its value . Either both of these updates must occur or neither must occur in order to keep the customer s accounts balanced.

Audited transactions typically exhibit the ACID properties Atomicity Consistency Isolation and Durability as described earlier. In some implementations the ACID properties may be relaxed. For instance the attributes of consistency and isolation may be traded for performance see Section 1.11.4 BASE Protocol .

The changes comprising an audited transaction are delimited by a pair of directives typically issued by the application process to a Transaction Manager. The beginning of a transaction is identified by a Begin Transaction directive in some systems the Begin Transaction directive is implied by the first change of a new transaction . The conclusion of an audited transaction is typically either a Commit Transaction directive or an Abort Transaction directive. A Commit Transaction directive causes all of the changes within the transaction to be applied to the database and to be durable. An Abort Transaction directive causes the changes within the transaction to be discarded.

The Commit or Abort directive can be issued explicitly by the application or they may implicitly occur for example at the end of an I O operation. Though the terms Begin Transaction Commit Transaction and Abort Transaction are used in this specification they are often known by different terms in different systems. However the actions they denote are substantially the same in all systems.

The property of atomicity is guaranteed by ensuring that either all changes within the transaction are applied or that none are.

The property of consistency is typically guaranteed by locking all data objects that are to be changed so that their value is hidden from other applications until they have been committed or aborted as an entire transaction.

The property of isolation also is typically guaranteed by locking all data objects that are to be changed so that no other transaction can modify their values until the current transaction commits.

The property of durability typically is guaranteed by writing the changes to a persistent database such as disk so that they survive any ensuing system failures.

An unaudited transaction is a logical sequence of database changes performed to accomplish a business function but the database changes are not bound by begin and end delimiters. If an application deals in unaudited transactions it simply applies each change in the transaction to the database via a database manipulation event.

Unaudited transactions do not provide the ACID properties of audited transactions unless these capabilities are built into the application. For instance the application may lock each update to provide consistency and isolation and then unlock the locked data objects when it has finished its transaction. It can make all changes to a disk resident database to ensure durability. However it must ensure that all changes have been flushed to disk before releasing its locks if it is to ensure not only durability but consistency and isolation as well. Special complex efforts are required in the application to provide these features across failures.

When a process is dealing with an unaudited transaction it communicates directly with the database management system via events. Each event contains the specification of the database operation that is to take place such as read insert update or delete and required attributes such as key values.

A typical unaudited transaction might be executed as follows via a series of database manipulation events 

Failure at any point in this processing sequence may leave the database in an inconsistent state. For instance if a system failure occurs immediately after the update to Row B the delete of Row C will not occur and Rows A and B will remain locked. There is no way for a Transaction Manager or any other facility to undo the Row A insert and the Row B update that occurred before the failure since there is no information as to the scope of the transaction unless the application is modified to take many intervening check points of its processing path to a durable store. It is because of this extra processing and lack of support for the ACID properties that unaudited transactions are typically not used.

Some systems provide utilities for converting unaudited transactions to audited transactions. These utilities use complex rules engines to look for sequences of events that possibly might be a complete business transaction. Alternatively they may simply count the events or time the duration of event sequences and frame the transactions with begin and commit directives. For instance the utility may frame a transaction with every five input output functions before every interprocess message or when an I O is performed at a requesting terminal device. The utility then bounds each sequence with a Begin Transaction directive and a Commit Transaction directive.

In the above example the utility might note a sequence of commands that locks Rows A and B and then unlocks Rows A and B. This may be an indication that the operations included between the lock and unlock commands represent a single transaction.

Examples of such utilities are found for many systems. For HP NonStop systems they include AutoTMF from Carr Scott Software Inc. of Duxbury Mass. USA and TMF Audit Toolkit from TANDsoft Consultants Incorporated of Beaconsfield Quebec Canada.

One or more databases or other resources may be involved in an audited transaction as voting participants. An example of a participating resource that is not a database is a synchronous replication engine that must vote on the outcome of the transaction. In order to be a voting participant the Transaction Manager must join the resource to the transaction. A resource may join a transaction either explicitly or implicitly.

The intercept library will return the transaction ID to the application and will inform the resource that the application is beginning a transaction and will pass it the transaction ID . The resource will notify the Transaction Manager that it is joining the transaction . In this way the resource becomes a voting member of the transaction is able to monitor all activity initiated by the transaction and is able to add its own activity.

An alternate method for allowing a resource to explicitly join a transaction is shown in . The application provides an API application programming interface that allows the resource to call a joining function in the application. The resource uses this API to register with the application its interest in joining transactions that the application initiates .

When the application initiates a transaction it sends a begin transaction directive to the Transaction Manager . The Transaction Manager returns a transaction ID to the application. Via the application s API the application responds to the resource s request with the transaction ID . The resource then notifies the Transaction Manager that it is joining this transaction . In this way the resource becomes a voting member of the transaction is able to monitor all activity initiated by the transaction and is able to add its own activity.

In either of these cases it is not necessary for the resource to join the transaction at the beginning of the transaction. The intercept library the application API or the resource itself can monitor the progress of the transaction and can cause the resource to join the transaction only if certain criteria are met. The resource will then join the transaction at this intermediate point.

At any point in a transaction the resource can decide that its involvement is unnecessary. It can then inform the Transaction Manager that it is a read only participant i.e. it was simply monitoring the transaction. This is in effect an abstention to voting and the Transaction Manager records no vote for the resource.

Either of these two explicit joining methods allows the resource to join transactions initiated by the application. Furthermore the resource can use information about the transaction to decide whether it wants to join at any given point and can ignore transactions in which it is not interested. It is a voting member of any transaction it joins and can vote to commit or abort the transaction.

There is an inherent risk when explicit joining is used to enhance the functions of applications. Joining a resource to multiple applications may be desirable but if the explicit joining of a resource to an application is erroneously omitted the functions that are intended for that resource to provide will not be performed. Many applications comprise hundreds or even thousands of processes and these errors easily arise.

Explicit joining avoids the complication and overhead of being inserted directly into the processing flow and therefore increasing the processing path length and consequently the execution time. Functionality that is added by joining is processed in parallel with the application processing and does not increase the application s path length.

One limitation of explicit transaction joining is that some transactions generated by system utilities rather than by applications are not known to the application. Therefore the resource cannot explicitly join these transactions. For instance in some systems the SQL database manager does not inform the application that it is beginning a transaction. Therefore the application cannot inform the resource that a new transaction has been initiated so that the resource can explicitly join it.

This problem is solved by implicit transaction joining. The resource makes a request to the Transaction Manager that it be included as a voting participant in any transaction that is initiated. The request may be for a specific subset of transactions such as those being initiated by a particular CPU or by a particular user. The resource will then be joined to any such transaction whether the transaction be initiated by an application by a system level function or by any other means.

Implicit joining is shown in . The resource requests that the Transaction Manager include it as a participating partner in any transaction that is initiated regardless of the initiating source . Thereafter an application or a system function can request that the Transaction Manager begin a transaction on its behalf . The Transaction Manager informs the resource of the transaction ID of the new transaction . The resource has now been joined to the new transaction as a voting participant.

One limitation of implicit joining is that the resource must join all transactions. With explicit transaction joining the resource may elect not to join certain classes of transactions initiated by the application.

Implicit joining avoids the earlier mentioned risks associated with intercept libraries and explicit joins. With these methods there is the possibility that a configuration error will result in the intended monitoring or modification functions not being executed. With implicit joining that risk is eliminated since the joining is a system function provided by the Transaction Manager not an application function.

Moreover implicit joining avoids the complication of being inserted directly into the processing flow and therefore increasing the processing path length and consequently the execution time. Functionality that is added by joining is processed in parallel with the application processing and does not increase the application s path length.

If an application deals in audited transactions the transactions are generally managed by a Transaction Manager as shown in . When an application wishes to start a transaction it makes a request to the Transaction Manager . The application then makes the changes bounded by the transaction to its application databases . As each change is made its before and after images are typically written to a change log .

When the application has completed the database changes for the transaction it sends a commit request to the Transaction Manager. The Transaction Manager next asks each database and resource involved in the transaction if it is ready to commit . If all databases and resources respond positively the Transaction Manager informs them to commit the transaction . It then informs the application that the transaction has been committed .

If any database or resource responds that it cannot make the changes to its database the Transaction Manager informs all databases and resources to abort the transaction . No changes are made to the databases all locks are released and the application is informed that its transaction has been aborted . The application also can request that the Transaction Manager abort the transaction rather than ask it to commit the transaction.

The Transaction Manager uses the change log to correct corruption to the database. It uses the before images stored with each change to roll back data objects to their original values if they have been erroneously changed or aborted. It uses the after images in the change log to roll forward data objects whose changes were lost due to a system malfunction .

If the application uses unaudited transactions each change in the transaction is applied directly to the database via a database manipulation event. This may be accomplished directly by the application or in conjunction with a Transaction Manager that deals in unaudited transactions. In many cases either the application or the Transaction Manager records all changes for unaudited transactions in a change log.

A Transaction Manager can implement several different protocols to process audited transactions. The protocols are designed to enforce to some extent or other either all or most of the ACID properties of audited transactions. Included in these protocols are One Phase Commit Two Phase Commit Three Phase Commit and BASE.

The One Phase Commit protocol 1PC is used if the transaction affects only a single database or resource. The 1PC protocol is shown in .

The application informs the Transaction Manager that it wishes to begin a transaction . The application then makes changes to its single database .

When it has finished processing the transaction it requests the Transaction Manager to commit the transaction . The Transaction Manager will request the database to commit the transaction . If the database or resource is able to commit the transaction it informs the Transaction Manager that it has committed the transaction and the Transaction Manager will inform the application that its transaction has been committed . If the database or resource is unable to commit the transaction it aborts it and so informs the Transaction Manager . The Transaction Manager will inform the application that its transaction has been aborted .

The application can also request the Transaction Manager to abort the transaction . The Transaction Manager will inform the database to abort the transaction and the database will confirm the action . At this point the Transaction Manager will inform the application that its transaction has been aborted .

The Two Phase Commit Protocol 2PC is used when the transaction involves two or more databases and or resources. described above depicts the 2PC protocol. With reference to as the application applies a read or an update to a data object in a database that data object is locked. Until the transaction commits no other transaction can modify the data object or can read its contents unless dirty reads are allowed in which case the current value of the data object is returned which may be before or after it has been modified or unless read committed is used the value of the data object before the lock is returned .

When the application requests that the transaction be committed the Transaction Manager enters the Two Phase Commit protocol. The 2PC protocol comprises two successive phases the Prepare phase and the Commit Abort phase. The Transaction Manager first enters the Prepare phase. It asks each of the resources that participated in the transaction if it is prepared to commit the transaction . In order for a resource to be ready to commit it must have received all changes in the transaction and must have safe stored them either by temporarily storing them in persistent storage or by applying them to the database .

If all resources respond positively the Transaction Manager enters the Commit phase. It informs all resources to commit the transaction . All resources will make the changes permanent. The Transaction Manager will inform the application that its transaction has completed .

If any resource responds negatively in the Prepare phase the Transaction Manager will enter the Abort phase and will inform all resources to abort the transaction. All resources will ignore the changes and the Transaction Manager will inform the application that its transaction has been aborted.

If instead of requesting a commit the application requests that the Transaction Manager abort the transaction the Transaction Manager will skip the Prepare phase. It will immediately enter the Abort phase and will inform all resources to abort the transaction.

Each resource will release all locks held by the transaction upon the completion of the transaction commit or abort . At this point other transactions needing access to those data objects can proceed.

A problem with the 2PC protocol is that data objects are locked until the transaction completes. No other transaction that needs access to those data objects can proceed until the locks are released. Thus if a resource should fail and cannot respond the locks will be held for an indeterminate period of time and the application may stall. This is called a hung transaction or a transaction in doubt. 

The above situation is corrected by the Three Phase Commit protocol 3PC . The 3PC protocol places an upper bound on the time that a transaction may take to commit or abort. It accomplishes this by adding a third phase a Wait phase between the Prepare phase and the Commit phase.

The 3PC protocol is shown in . Upon receiving a Commit request from the application the Transaction Manager enters the Prepare phase and sends a canCommit query to all resources involved in the transaction . It then enters the Wait phase .

If a resource can commit it responds with a Yes . If the resource should time out without receiving a canCommit query it aborts its transaction. This is the end of the Prepare phase.

In the Wait phase if the Transaction Manager receives a Yes response from all resources it sends a preCommit message to all resources . If it receives a No response from any resource or if it times out waiting for a resource to respond it aborts the transaction and sends an Abort message to all resources. The Transaction Manager then enters the Commit phase .

When a resource receives a preCommit message it responds with an ACK message . If the resource times out without receiving a preCommit message it aborts its transaction.

If the Transaction Manager receives an ACK message from all resources it sends a doCommit message to all resources . However if the Transaction Manager times out before receiving an ACK message from all resources it aborts the transaction and sends an Abort message to all resources.

When a resource receives a doCommit message it commits its transaction and returns a haveCommited message . If the resource times out without receiving a doCommit message it goes forward with the commit.

If the Transaction Manager does not receive a haveCommited message from a resource it takes no further action. If the resource is still alive the Transaction Manager knows that the resource has committed the transaction either because it received the doCommit message or because it timed out.

By using the 3PC protocol no transaction will hold locks for longer than the timeout period once the application has requested that its transaction be completed.

In a large application deployed across many independent systems under the 2PC or 3PC protocols a transaction being processed by one system must hold locks on data objects resident on all of the other systems in the application network until the transaction completes. Thus within a single system many data objects will be locked by transactions running on other systems. In very large networks this can impose a severe performance penalty as applications wait for locks to be released.

The BASE protocol Basic Availability Soft state Eventual consistency offers a compromise to this challenge. It trades consistency and isolation two of the ACID properties enforced by the other protocols for performance.

In distributed application networks any audited changes applied to the database on one system are applied to the other systems where normally they would be applied with locking if 2PC or 3PC protocols are being used. However with BASE the databases on each system are cached and data objects are not locked by transactions being executed on remote systems. A transaction on a source system will use its cached database for processing even though the data it is using in its database may be inconsistent and may even be changing because of the execution of remote transactions.

The benefit of BASE is that applications are not held up by locks held by other systems. The downside is that transactions are executed against potentially inconsistent data. This violates the ACID properties of consistency and isolation. Ultimately the inconsistent data on each system will be updated by the remote executing processes. If all applications on all systems were to be paused the databases will eventually become consistent. This is called eventual consistency. 

If an application can tolerate stale data caused by eventual consistency BASE provides a way to significantly improve performance in large distributed transaction processing systems.

Many applications require updates to two or more databases that may be resident in two or more computers. In this case the Transaction Manager in the system that initiates the transaction manages the transaction across all computers involved in the transaction. As database changes are made to a database in another computer those changes are sent to the Transaction Manager in that computer so that the Transaction Manager can manage its own database updates.

This process is illustrated in . A transaction is initiated when the application issues a Begin Transaction directive to its Transaction Manager . The application then issues database changes that in the case of are to applied to its own Database A the source database in Computer A and to Database B the target database in Computer B . Changes to Database A are made directly by Transaction Manager A. Changes to Database B are sent by Transaction Manager A to Transaction Manager B which applies them to Database B.

When the application asks that the transaction be committed typically the two phase commit protocol is used. During Phase the Prepare Phase the source Transaction Manager asks each of the foreign Transaction Managers if it is ready to commit . If a foreign Transaction Manager has successfully safe stored or applied all of its database changes it votes yes . Otherwise it votes no. 

When all Transaction Managers have voted the source Transaction Manager enters the Commit Phase. If it has been successful at safe storing or applying all changes to its database and if all other Transaction Managers have voted yes the source Transaction Manager informs all Transaction Managers involved in the transaction to commit the transaction . If any Transaction Manager has voted no the source Transaction Manager informs all involved Transaction Managers to abort the transaction.

A simple example of a distributed transaction is the banking application in . A request is made by an end user to transfer 100 from his savings account to his checking account. In this example checking accounts are maintained by Computer A . Savings accounts are maintained by Computer B .

The request is received by a Request Process . Running in Computer A the Request Process begins a transaction with its local Transaction Manager . The first thing the Request Process must do is to ensure that the user has at least 100 in his savings account. It therefore sends a request to the Savings Account Process running in Computer B and asks for the savings account balance. The Savings Account Process accesses its Savings Account Database and responds to the Request Process with the savings account balance.

Assuming that the savings account balance is sufficient the Request Process sends a request to the Savings Account Process to debit the savings account by 100. The Savings Account Process debits the savings account balance for this user by 100 via its local Transaction Manager and responds to the Request Process that it has been successful.

The Request Process then requests the Checking Account Process running in Computer A to credit the user s checking account balance by 100 . The Checking Account Process adds 100 to the user s balance in the Checking Account Database via its local Transaction Manager and responds with an acknowledgement to the Request Process.

The Request Process now asks its Transaction Manager to commit the transaction . The Transaction Manager in Computer A coordinates with the Transaction Manager in Computer B to commit the transaction . If the commit is successful the user is so notified .

In each case in this example the output of a process is a service and the input to a process is an event. In many instances the service is the generation of an event to be processed by another process.

The initial user request is an event that is processed by the Request Process. The first action of the Request Process is to generate an event to the Savings Account Process in order to request the savings account balance. The Savings Account Process performs the requested service and returns the savings account balance. The Request Process then generates an event to be processed by the Savings Account Process and requests the debit of 100 from the savings account. The Savings Account Process does so and responds to the Request Process that it has completed the requested action.

The Request Process next generates an event to the Checking Account Process to credit the checking account. When this service has been completed by the Checking Account Process the Request Process responds with a positive acknowledgement to the end user.

The updates to the Savings Account Database and the Checking Account Database are grouped together into a single audited transaction to ensure that either both updates are made or that neither are made. The transaction takes the following form 

If the savings account balance is insufficient or if either update to a database cannot be made the transaction is aborted. No database update action takes place.

Computer applications generally process events based on the information contained within the event. For instance in s banking application the information contained in the initial event is the function to be performed transfer funds the account to be debited the savings account number the account to be credited the checking account number and the amount of money to be transferred.

However in some cases it is desirable to append additional information to an event or a transaction. This data adds useful attributes to those contained in the initial event or transaction. Such attributes can control how the event or transaction is processed. They might be used for instance to invoke additional services for an event. They might be used against a complex rule set to decide whether to modify a transaction or to allow the transaction to proceed. For instance if the funds in an account are insufficient to cover a transfer the bank may want to allow the transfer anyway and charge an overdraft fee . Alternatively the bank may reduce the transfer amount to reflect the amount currently held in the account.

This information is often available at the time of the event or in a variety of tables or logs maintained by the computing systems. In prior art the gathering of the information is implemented by special coding in applications and often takes place after the fact. The results are archived for later processing. The information is useful primarily for offline applications such as post transaction auditing regulatory compliance security policy compliance and trending.

To meet the challenges of today s changing business environments it is often necessary to add these attributes and the controls that they impose to existing applications so that actions dictated by the appended attributes can be taken and used in real time. This means that the applications must be modified to incorporate the additional functionality.

It is the responsibility of the Event Tx Tracking module also referred to herein as a tracking engine to apply additional processing functions to the events or transactions in order to enhance or modify their outcomes in the desired ways. The Event Tx Tracking module may also gather additional information and append it to the event or transaction. The Event Tx Tracking module determines all of the required additional information accesses that information and appends it to the event or transaction in question.

Though there are many ways in which an Event Tx Tracking module may be implemented illustrative examples are shown in . Note that in these examples the Event Tx Tracking module is a function. It comprises a set of code and is not necessarily an executable. How it is executed depends upon how it is integrated into the application as described later.

The Event Tx Tracking module may include a Rules Engine . The Rules Engine may be integrated with the Event Tx Tracking module as illustrated in or it may be a separate module that the Event Tx Tracking module can use as shown in . When the Event Tx Tracking module receives an event or a transaction that it is programmed to process the module may manage the event or transaction in a variety of ways depending upon how the module is implemented. It may add to the event or transaction certain information that is available elsewhere in the system and that can be used to enhance the application s functionality.

The Event Tx Tracking module may take actions on the event or transaction such as rejecting or modifying either . In many cases this is the function of the Rules Engine. The Event Tx Tracking module may send the event or transaction to the Rules Engine and the Rules Engine will respond perhaps with modifications to the event or transaction. It also may signify that the event or transaction is acceptable or should be rejected.

The Event Tx Tracking module may generate a modified event or transaction in order to control further downstream processing by application processes. It may invoke other application processes to provide ancillary functions with information about the event or transaction.

The prior art provides methods for an Event Tx Tracking module to intercept and modify the actions of events through intercept libraries or intermediate processes. However there is no prior art method to allow an Event Tx Tracking module to intercept and modify an audited transaction begun by a system facility such as a SQL database manager.

As described earlier in Section 1.6 Intercept Libraries IL incorporating one or more intercept libraries into an existing application allows functionality to be added without the need for application modifications. The functionality to be provided by Event Tx Tracking can be added to an existing application via intercept libraries as illustrated in .

An application process provides services to its end users. Its typical processing flow is to receive events from external sources to use its database to process the events while making changes to the database pertinent to the events and to generate events to downstream processes for further processing or to other end users .

In this illustrative example Event Tx Tracking is added to the application to preprocess incoming events to control the use of the application s database and to enhance generated outputs to the end users. Separate intercept libraries are provided for each of these functions although these functions could be incorporated into the same intercept library.

In order to await an incoming event the application posts a read call on its incoming channel. This is a call to the operating system to monitor the incoming channel for a message and when a message is received to pass it to the application. However the Event Tx Tracking 1 intercept library has been incorporated into the application to intercept the read call to the operating system . When a message arrives on the incoming channel it is intercepted and passed to the Event Tx Tracking 1 module. This module has access to the necessary external information to append to the event if desired . The module also can take actions on the event such as rejecting it or modifying it . When the module has completed its incoming event processing it passes the enhanced event to the application process as if it were the operating system read function that the application had called.

As the application processes the event it typically will access data in its database and will change that data. It does this via DML call events to the operating system read insert update and delete and at times via DDL calls to modify the structure of the database. These database calls may be part of an audited transaction an unaudited transaction or simply one or more unrelated database operations. An Event Tx Tracking 2 intercept library is incorporated into the application to intercept the DML DDL commands . When a database command is made by the application the database manipulation event is intercepted by the Event Tx Tracking 2 intercept library. The library can process the database call in any way it desires . It can optionally use additional information resident elsewhere in the system . It can modify the database operation it can reject it or it can perform any other desired operation. When the intercept library has completed its processing and has applied the resulting modified operation to the database it responds to the application as if it were the operating system database command that the application originally called .

Outgoing events generated by the application are handled in a similar way by Event Tx Tracking. An Event Tx Tracking 3 module is incorporated into the application to intercept application calls requesting that the operating system send a message to another process or end user. The Event Tx Tracking 3 intercept library intercepts these calls and sends them to the Event Tx Tracking 3 module. This module applies whatever changes are desired to modify or to reject the outgoing event optionally using additional information available in the system . When the module has finished its processing it sends the enhanced outgoing event to downstream processes or to end users as if it were the operating system call that was originally invoked.

The above illustrations of the functions of the intercept libraries describe additional information if any as being physically attached to the modified events or transactions. Alternatively the intercept libraries might logically attach such information by maintaining it in an area separate from the events or transactions. In this case the intercept libraries will know where to find the additional information referenced in the event or transaction.

The use of intercept libraries bears the risk of improper configuration in which one or more libraries are not linked into application processes as intended. If this occurs the intended information flow monitoring and control will not be provided. Many applications have hundreds or even thousands of processes and ensuring the proper configuration of intercept libraries into the application can be a daunting task.

In addition intercept libraries increase the path length of application execution thus slowing down response times. Also intercept libraries cannot be inserted into certain audited transactions initiated by system facilities.

Implementing Event Tx Tracking as one or more intermediate processes is similar to the intercept library implementation described in . However instead of an intercept library the Event Tx Tracking module is implemented as one or more stand alone processes that are inserted between other processes. is only one configuration that can be used to add Event Tx Tracking to an existing application via intermediate processes but it serves to illustrate the method.

With reference to an application process provides services to its end users. Its typical processing flow is to receive events from external sources to use its database to process the events while making changes to the database pertinent to the events and to generate events to downstream processes for further processing or to other end users .

In this illustrative example Event Tx Tracking is added to the application to preprocess incoming events to control the use of the application s database and to enhance generated outputs to the end users. The intermediate processes Event Tx Tracking 1 Event Tx Tracking 2 and Event Tx Tracking 3 are provided for each of these functions.

The Event Tx Tracking 1 process is positioned between the incoming event and the application process so that it can intercept and enhance incoming transactions before these events are sent to the application process .

The Event Tx Tracking 2 process is positioned between the application process and the database so that it can intercept database manipulation events issued by the application process and can modify or control these commands . These database calls may be part of an audited transaction an unaudited transaction or simply may be one or more unrelated database operations. Event Tx Tracking 2 may be positioned anywhere that it can intercept database command events. As examples it may be positioned between the application and the file system or between the file system and the disk processes so that all database commands flow through it. The intermediate process cannot be inserted into the processing flow of an audited transaction begun by a system facility such as a SQL database manager.

The Event Tx Tracking 3 process is positioned in the stream of events generated by the application process. In this way it can modify and control the events to be sent to downstream processes or to other end users .

All Event Tx Tracking modules may have access to additional information resident in the system and optionally can use that information to enhance or control their processing of events or transactions.

In this example when an event arrives from an external source the Event Tx Tracking 1 process receives the event and applies enhancement and control functions. It then passes the modified event to the application process.

As the application process provides its services relative to the modified event it may read data from its database and may make changes to its database. These database command events are intercepted by the Event Tx Tracking 2 process which can exercise its own control and enhancement.

Upon completion of the event processing the application process may generate an outgoing event that is to be passed to other downstream processes or to other end users. The Event Tx Tracking 3 process intercepts the outgoing event and adds controls and enhancements before passing it on as an enhanced outgoing event.

The above illustrations of the functions of the intermediate processes describe additional information that may be physically attached to the modified events or transactions. Alternatively the intermediate processes might logically attach this information by maintaining it in an area separate from the events or transactions. In this case the intermediate processes will know where to find the additional information.

As is the case with intercept libraries the use of intermediate processes bears the risk of improper configuration in which one or more processes are not injected into the processing flow as intended. If this occurs the intended information flow monitoring and control will not be provided. Many applications have hundreds or even thousands of processes and ensuring the proper configuration of intermediate processes into the application can be a daunting task.

In addition intermediate processes increase the path length of application execution thus slowing down response times. Also intermediate processes cannot be inserted into certain audited transactions initiated by system facilities.

An example of how Event Tx Tracking can add functionality to an existing program without requiring changes to the program appears in . A legacy application manages a bank s ATMs. Its functions are to receive ATM requests that include as parameters the amount requested the credit card or debit card number and the ATM s IP address. The application process checks the cardholder s account in the card database . If the account balance covers the withdrawal request the application returns an approval to the ATM to issue the requested amount.

The bank has decided to add stricter rules to its approval of ATM withdrawals and has created a Rules Engine that governs whether a transaction can or cannot be authorized without modification. illustrates the use of Event Tx Tracking to implement one of these rules without the need for application modification. The specific rule in question is that any particular ATM may only issue a restricted amount of cash to a credit or debit cardholder on any single day. Three Event Tx Tracking modules are added to the application to modify incoming events database accesses and generated responses. The modules are shown in . Though shows the Event Tx Tracking modules as being implemented as prior art intermediate processes they also may be implemented as prior art intercept libraries.

When for example a cash withdrawal request for 1 000 is received by the application the request is intercepted by the Event Tx Tracking 1 module . This module accesses the ATM location from the communication subsystem and replaces the ATM IP address such as 192.23.106.255 with the ATM location such as PNC Lobby Blairstown N.J. USA in the incoming event. We assume that this change in value is transparent to the application due to the way the application is coded. The modified event containing the ATM location is passed to the application.

According to the logic built into the original ATM application it determines that the cardholder s account is sufficient to cover the withdrawal and will issue a command to the card database to debit 1 000 . This command will include the amount the card s account number and the ATM location.

The database command will be intercepted by the Event Tx Tracking 2 process . This process will access the Rules Engine and will find that for this particular ATM no cardholder may withdraw more than 500 in any one day. The process will then access the card database and will determine that the cardholder already has withdrawn 300 from this ATM on the same day. Therefore the cardholder is authorized to withdraw only 200. The Event Tx Tracking 2 module will debit the cardholder s account by 200 and will reply to the application that the update has been made 

Thinking that the entire 1 000 has been deducted from the cardholder s account the application will issue a directive to the ATM to issue 1 000 . However this event is intercepted by the Event Tx Tracking 3 process . It has access to Event Tx Tracking 2 s decision that only 200 is to be issued . Event Tx Tracking 3 also has access to the communication subsystem so that the address of the ATM can be returned from its location to its IP address . Event Tx Tracking 3 will modify the application s response to one that authorizes the ATM to issue only 200 .

This example is prior art and reflects how an application s functions can be significantly modified by Event Tx Tracking without making any modifications to the application.

Many applications require a local or remote copy of the application database to be maintained and to be kept synchronized with the source database. For instance a system backing up a primary system needs an up to date copy of the primary system s database so that it can continue processing should the primary system fail. An active active system in which all processing nodes are cooperating in a common application requires that all nodes have a copy of the current application database so that they can process transactions routed to them. The synchronization of databases is accomplished by data replication.

With data replication changes made to the source database are sent via a communication channel to the target environment where they are applied to the target database. The source and target databases may be collocated or they may be remote from each other. There are three types of data replication 

At the target system the data replication engine s Consumer receives the begin transaction token and passes it to the target system s Transaction Manager B which begins an independent transaction on the target system.

Thereafter as the application issues database changes the changes are applied to the source database by Transaction Manager A which inserts each change into the change log. The Collector reads the changes and sends them over the communication channel to the target s Consumer which passes them to Transaction Manager B for writing to the target database.

When the application issues a commit request to its Transaction Manager Transaction Manager A commits the transaction on the source system and inserts a commit token into the change log. The commit token is replicated to the target system where the target system s Transaction Manager B commits the transaction on the target system.

The replication latency introduced by asynchronous replication is the time from when a change is made to the source database to the time that it is made to the target database. In this example the change must be placed in the change log the Collector must read it and send it to the Consumer and the Consumer must apply it to the target database. Replication latency can range anywhere from a fraction of a second to minutes depending upon the design of the replication engine and other factors such as the speed of the interconnecting network.

An application begins a transaction by issuing a begin transaction directive to its Transaction Manager . The Transaction Manager knows that the transaction is to be applied to two application databases a source application database on the source system and a target application database on a target system . Though the target application database is shown in as being on a different system from the source application database they may both be resident on the same system.

As the application issues database changes the Transaction Manager applies these changes to the source application database and using the interconnecting network between the systems applies the same changes to the target application database. It also enters information about each change into its change log . The Transaction Manager does not notify the application that a change is complete until it is assured that the changes have been applied to each database. Note that in many cases the target set of changes are applied by the application itself or by a library process or remote file system acting on behalf of the application.

When the application issues a commit transaction directive the Transaction Manager knows that all changes have been applied to both databases and that the databases are therefore in synchronization. It commits the transaction enters a commit token into its change log and informs the application that the transaction has been committed.

Because the source system must wait for each update to complete on the target system the processing time of a transaction is extended. This delay is called application latency. Application latency is partially a function of the distance between the source and target systems. The further apart the systems are the longer it takes for signals to propagate between them. Thus application latency typically limits the distance between the source and target systems to campus or metro environments in which they are separated by no more than tens of kilometers.

Coordinated Commits is a synchronous replication technique that combines asynchronous replication with synchronous replication to ensure no data loss but without imposing a distance restriction on the separation of the source and target systems. An example of a Coordinated Commits replication engine is shown in .

The Coordinated Commits replication engine is a modified asynchronous replication engine as described in Section 1.18.1 Asynchronous Replication. It includes a Coordinator process whose job it is to manage the commit of the transaction at the source and target systems. When the application first begins a transaction the Coordinator joins the transaction so that it can be a voting resource. It may do this explicitly via an intercept library or via an API provided by the application as described in Section 1.9.1 Explicit Joining or it may join it implicitly as described in Section 1.9.2 Implicit Joining. shows the Coordinator explicitly joining the transaction. It receives a transaction ID from the application and uses this ID to make a request to Transaction Manager A to join the transaction. It is now a voting resource for the transaction.

Up until commit time normal asynchronous replication proceeds as described earlier. When the application begins a transaction and a database change is sent to the target system under that transaction the target system Transaction Manager B begins an independent transaction and applies the change to its database under that transaction. All further changes are made both to the source database by the application and to the target database by the replication engine.

However when the application requests that the transaction be committed the replication engine switches to synchronous mode. The source Transaction Manager A enters the Prepare phase of the two phase commit protocol. It asks the target system if it is ready to commit. It does this by asking the Coordinator if it is ready to commit . The Coordinator asks the Consumer on the target system if it is ready to commit . If the Consumer has been able either to safe store or to apply all of the database changes it will reply with a yes vote to the Coordinator.

When the Coordinator receives the yes vote from the Consumer it sends a yes vote to the source Transaction Manager A. When Transaction Manager A receives a yes vote from all transaction participants it enters the Commit phase of the two phase commit protocol. It commits the transaction on the source system and inserts a commit token into the change log. The commit token is replicated to the target Transaction Manager B which will commit the transaction on the target system.

If the target Transaction Manager B or any other transaction participant cannot commit the transaction it returns a no vote to the source Coordinator which passes it to the source Transaction Manager A. Transaction Manager A will abort the transaction on the source system and will insert an abort token into the change log to inform the target Transaction Manager B to abort its transaction.

Thus all database changes within a transaction are guaranteed to be made either to both source and target systems or to neither system. No data is lost should the source system or network fail. Furthermore since the only delay to the source application is having to wait for the target system to vote application latency is significantly reduced relative to standard synchronous replication described in Section 1.18.2 Synchronous Replication. With Coordinated Commits the systems can be separated by great distances and still provide excellent performance.

In the above description it is said that If the Consumer has been able either to safe store or to apply all of the database changes it will reply with a yes vote to the Coordinator. There is an important difference between whether the Consumer replies with a yes vote only if the data has been safe stored or if it has actually been applied to the database.

If the data has been safe stored but not applied to the database then no data will be lost if the source system or interconnecting network should fail. This is known in the industry as Zero Data Loss or ZDL. However if the systems are running in an active active mode in which both systems may be actively processing transactions data collisions may occur. A data collision occurs when applications in different nodes change the same data item at almost the same time within the replication latency interval . In this case each change will be replicated to the other system and will overwrite the update made by the application in that system. Now both systems have different values for the data item and both are wrong.

However if the data actually has been applied to the target database then all such data items are locked and cannot be changed until commit time at which time they are unlocked. Thus it is not possible for another application to change one of these data items and not only will no data be lost but there will be no data collisions.

If the Coordinator joins the transaction via implicit joining there are several ways in which such joining can be implemented. Some examples are 

The capabilities of the Coordinated Commits replication engine can be enhanced via a Queue Manager QMGR resident on the target system as shown in . There are two useful configurations for the Queue Manager. In one the Queue Manager is the voting resource and votes whether or not to commit the transaction. In the other configuration the Consumer is the voting resource.

The operation of the Queue Manager is similar whichever configuration is used and is shown in . Changes sent to the target system by the source system Collector are received by a QMGR . The QMGR typically queues the changes in a memory buffer and optionally writes the buffer to persistent storage when the memory buffer fills.

In addition QMGR sends the changes to the target system s Consumer which sends the changes to the target side Transaction Manager for writing to the target database .

Writing changes to a sequential queue is much faster than applying random changes to a database. Thus if the Consumer gets behind it can read changes from the queue via QMGR rather than slowing down the delivery of the data from the source side Collector.

Another advantage of using a Queue Manager is that the target database can be taken offline for maintenance or upgrading. All data changes that are made during the offline period are stored in the QMGR s queue and can be applied to the target database when it is returned to service.

The configuration in which the Queue Manager is the voting resource is shown in . In this example the RTC request to commit request is received by the QMGR. The QMGR optionally flushes its memory resident buffer to persistent storage. This step is optional configurable because it would take a dual failure i.e. both the source and target environments to lose the data. Some customer implementations acknowledge and accept this risk. Knowing that all database changes have now been safe stored on the target system the QMGR responds to the source side s Coordinator that it is ready to commit . The commit process described in Section 1.18.3 Coordinated Commits is then followed.

By using this technique the source system does not have to wait for the database changes to be applied to the database. Consequently application latency is significantly reduced. This configuration provides for zero data loss in the event of a source system failure.

However since the target data to be changed is not locked prior to the commit data collisions still can occur when running in an active active architecture.

The configuration for the Consumer to be the voting resource can be seen in . In this case the RTC request is sent by the QMGR to the Consumer . The Consumer completes the changes to the database for this transaction and responds to the source side Coordinator with a ready to commit indication . The commit process described in Section 1.18.3 Coordinated Commits is then followed.

In this case the source system does not have to wait for each change to be applied individually to the database but it must wait for all of the database changes to be completed before it can commit. Thus application latency is reduced but not to the extent of the Queue Manager Votes configuration described above. However since each data object is now locked prior to the commit before the data object can be changed data collisions will not occur when running in an active active configuration.

The QMGR also can be resident on the source system. This will speed up the source side Collector and will provide a source of database changes if the network fails is slow or the target Consumer should fall behind. However in this configuration the QMGR will typically not be the voting resource. The target side Consumer must be the one that votes since only it knows if all data changes have been received and optionally safe stored and or applied to the target database.

Every process in a data replication engine can have user exits to provide additional functionality. User exits allow a process to make decisions during the processing cycle about the data and transactions being replicated. This includes the Collector the Coordinator the Queue Manager and the Consumer. User exits may use a Rules Engine to determine actions to take. These user exits may even be part of a Tx Tracking Engine or separate from it.

For instance each process could decide whether to encrypt data in flight flowing through it. All data in flight could be encrypted or only certain fields. The Consumer could decide whether to encrypt data at rest. Again it could elect to encrypt all data or just certain fields. If encryption is not allowed due to federal regulations a process may elect to obfuscate certain data for instance by tokenizing it and or replacing it with x s.

The Coordinator is in a position to determine whether a transaction should be synchronously replicated or whether it can be replicated asynchronously. If it can or should be replicated asynchronously the Coordinator will not join the transaction. However if it must be replicated synchronously the Coordinator will join the transaction.

Configuration information can be used for example to tell the Coordinator which data e.g. tables transactions or even user IDs making changes should be done asynchronously or synchronously.

Adding automated logging of all or selected application and database activity whether directly generated by the application or on behalf of the application by system functions is useful for auditing the activity that occurs on the system. This provides post mortem forensic review capabilities to determine the answers to questions such as who did what when from where and how often. For example while a database maintains the current value of an account balance it is often useful to know how often that account balance went to zero or was overdrawn thereby leading to possible upselling of overdraft services.

Many functions would be valuable to existing applications if additional information was available to them in real time for the events they were processing and for the transactions they were generating and additional controls on how the data is processed and or distributed can be achieved without necessarily changing the applications themselves. For instance with respect to events 

With respect to transactions certain controls can be applied or the transactions can be modified to make them acceptable. For instance 

In some cases much of this functionality can be added to an application by the use of prior art intercept libraries and intermediate processes to modify and control events. However it is impossible to insert these elements directly into the processing stream of certain transactions initiated by the system.

Furthermore the use of intercept libraries intermediate processes and similar techniques is risky as the intercept libraries and intermediate processes may have to be configured for hundreds or even thousands of processes in large applications. It is quite possible that configuration errors will prevent certain monitoring or control functions from being executed properly.

Moreover the use of intercept libraries and intermediate processes is inefficient as they extend the processing path length of transactions. Their processing is sequentially inserted into the normal processing flow of the transaction.

Over time requirements have grown for the control of the actions executed by events and transactions for many applications and the applications were never written to provide these functions. The modification of old legacy applications is risky and costly if even possible. Many were written decades ago in languages that are not well known today such as Cobol Fortran and PL. Computer science majors today learn Java. Often the original code for the applications is lost and the structures of such applications are mysteries to those that must maintain them.

The present invention teaches methods that allow the processing of an audited transaction to be automatically logged controlled or modified by adding additional processing functionality and or ancillary information to it in real time without the requirement for application code changes. The additional processing functionality and or information can be used to enhance applications for purposes of security for adherence to regulatory requirements for new business policies and applications and for many other purposes.

Having real time access to this additional processing functionality and or appended information greatly expands the usefulness of an audited transaction. For example 

The ability to control transactions and optionally to append useful information to them is implemented by extending the audited transaction processing with one or more Event Tx Tracking modules. An Event Tx Tracking module is a program or function that identifies the transaction passed to it whether any additional attributes should be appended to the transaction and the additional functions that should be performed based on the transaction data and or the extra attributes.

The functions that can be performed by the Event Tx Tracking module are dynamic and can change or adapt over a period of time. In particular the rules set governing the actions of the Event TX Tracking module can be dynamically or statically updated to provide new functionality as necessary in some cases without affecting the overall application processing. The functions that can be performed by the Event TX Tracking module are unlimited and include automatically logging the details of the transaction rejecting the transaction modifying the transaction controlling the processing of the transaction and invoking ancillary services based on the added attributes of the transaction.

A novel method to extend transaction processing with an Event Tx Tracking module applicable to audited transactions being processed under the 1PC 2PC 3PC BASE or other similar transaction protocols is for the Event Tx Tracking module to join the transaction as a monitoring or voting member. See Section 1.11 Transaction Management Protocols and Section 1.9 Joining a Transaction. In that way the Event Tx Tracking module can log and or influence the processing of a transaction as it proceeds. Using this approach the Event Tx Tracking module can be dynamically changed and replaced with a new Event Tx Tracking module with new processing rules without having to take an application outage. For instance the Event Tx

Tracking module can vote to abort the transaction if the transaction violates a rule set or it can modify the transaction to be compatible with the rule set. Furthermore in a replicated environment the Event Tx Tracking module can impose one set of rules on the source data and a totally different set of rules on the target data.

The following definitions describe the use of certain terms in this specification. They are hierarchically ordered in that each definition builds on previous definitions.

Table A set of data values that is organized using a model of horizontal rows and vertical columns. The columns are identified by name and the rows are uniquely identified by the values appearing in a particular column subset the table s primary key . A table usually characterizes an entity set. Each row in the table describes an instance of the entity set. Each column describes an attribute of the entity set.

File The equivalent of a table for nonrelational databases. A file is made up of records and each record describes an entity instance. A record is made up of fields each of which describes an attribute of the entity set. In this specification the term table is to be interpreted as table and or file. 

Field A file component that holds a single attribute such as SALARY of the entity set. In this specification the term column is to be interpreted as column and or field. 

Row A table component that represents an entity instance. It is a sequence of column name value pairs usually implemented as a sequence of values positioned according to their corresponding column names. For instance EMPLOYEE NUMBER 235 NAME Joe Smith DEPARTMENT Accounting SALARY 30 000 .

Record The same as a row but row is usually used for relational databases and record is usually used for file systems. In this specification the term row is to be interpreted as row and or record. 

Key A column that contains a value that identifies its row or another row in the database a foreign key .

Data Manipulation Language DML The operations that control a database s contents such as insert update delete and read a row or record.

Data Definition Language DDL The operations that control a database s structure such as add or delete a column or a table.

Process A program running in a computer. A process provides one or more functions. One program can be spawned as multiple distinguishable processes.

Operating System A software facility that manages computer hardware resources and provides common services for application processes. Services include time functions reading and writing interprocess messages and database manipulation.

End Users People systems devices applications or any other entity that can influence an application or can request or use the services that the application provides.

Event A request indication or other stimulus sent to an application process for processing. Events are often sent as interprocess messages.

Intercept Library A program that can be incorporated into an executable to intercept application activity and to modify or enhance that activity. It typically requires no changes to the application. The application activity that is intercepted is often application calls to the operating system.

Intermediate Process A process that can be inserted between two other processes to intercept application activity and to modify or enhance that activity.

Audited Transaction A delimited set of database operations inserts updates deletes reads create tables and or purge tables etc. that are either all made or none are made. An audited transaction is guaranteed to leave the database in a consistent state and its results are typically guaranteed to survive system failures.

Unaudited Transaction A database change or group of changes that is not audited. It has no explicit begin or end delimiter though there may be logical boundaries. An unaudited transaction is not guaranteed to leave the database in a consistent state and its results are typically not guaranteed to survive system failures.

ACID Properties Audited transactions typically maintain the ACID properties of atomicity consistency isolation and durability. Atomicity means that either all operations contained within the transaction are executed against the database or that none are. Consistency means that at any time the view of the database represents an accurate view of the application data. Isolation means that a transaction is unaffected by other transactions that are executing simultaneously. Durability means that the resulting modification to the database by a transaction will survive any subsequent system failures. In some implementations the ACID properties may be relaxed.

Begin Transaction A directive that indicates the beginning of an audited transaction. A begin transaction directive may be explicit or it may be implicit such as with the first database operation for a transaction.

Commit Transaction A directive that indicates that an audited transaction has successfully completed.

Abort Transaction A directive that indicates that an audited transaction has been unsuccessful and should be undone.

Lock While a data object row or table is locked no other transaction can modify that data object row or table or read it except in the case in which dirty reads are allowed . A data object row or table that is being changed by an audited transaction is locked until the transaction commits or aborts. A data object row or table that is being changed by an unaudited transaction is typically locked only for the duration of the single event being processed.

Dirty Read A read of a locked data item. Either the before value or the after value will be returned depending upon the state of the locked data item at the time of the read.

Transaction Manager A facility for managing the updating of a database with transactions. For audited transactions a transaction manager ensures that changes to a database maintain the ACID properties.

Resource Manager A process or other entity that manages a resource. It accepts updates from the Transaction Manager responds to the Transaction Manager during the Prepare phase of the 2PC protocol indicating whether or not its resource can commit the transaction and executes a commit or abort directive received from the Transaction Manager. The resource manager provides a common interface between its resource and the Transaction Manager.

One Phase Commit 1PC A protocol for ensuring that an audited transaction affecting a single database or other resource maintains the ACID properties. In contrast to the 2PC protocol there is no Prepare phase only a Commit phase. In the Commit phase the Transaction Manager informs the resource to commit the transaction if it has not been previously aborted. The resource will inform the Transaction Manager as to whether it was able to commit the transaction or if it had to abort the transaction.

Two Phase Commit 2PC A protocol for ensuring that an audited transaction distributed over two or more databases or other resources maintains the ACID properties. In the first phase the Prepare phase the Transaction Manager asks each resource if it is prepared to commit. Each resource votes with a yes or a no. In the second phase the Commit phase the Transaction Manager informs all resources to commit the transaction if they all voted yes. If one or more resources voted no the Transaction Manager informs all resources to abort the transaction.

Three Phase Commit 3PC A protocol for ensuring that an audited transaction distributed over two or more databases or other resources maintains the ACID properties. It is similar to the Two Phase Commit protocol except that added is a waiting phase that allows the transaction to abort on timeouts. This permits the release of locks that otherwise will remain indefinitely with the 2PC protocol if a resource doesn t respond.

BASE Basic Availability Soft state Eventual consistency A transaction protocol that avoids locking. It sacrifices the consistency and isolation properties of ACID transactions to allow greater system scalability and performance. The ACID properties of atomicity and durability however are preserved.

Joining a Transaction A method for appending a program module or function to the processing stream for an audited transaction. This allows the module or function to log monitor alter and or be a voting member of the transaction without adding to the processing length of the transaction.

Explicit Join A join of a module or function to a transaction by interaction between the module or function and the application initiating the transaction.

Encryption The process of encoding a message so that it can be read only by the sender and the intended recipient.

Data Replication Transferring data changes from a source database to a target database to maintain the two databases in synchronization.

Asynchronous Data Replication Replicating data changes to a target database after the data changes have been applied to the source database. In the event of a source system failure or network failure some data changes may be lost and may not make it to the target system.

Synchronous Replication Safe storing the data changes on the target system as part of the source s apply sequence such that or in a way that no data is lost if the source system fails. In the event of a source system failure or network failure no data changes will be lost by the target system once that data has been delivered to the target system.

Replication Latency The delay from when the source database is updated to the time that the target database is updated when using asynchronous replication.

Data Collisions The changing of the same data object in a source database and a target database within the replication latency interval in an asynchronous data replication system. It causes the original changes to be overwritten by the replicated changes.

Application Latency With synchronous replication the delay imposed upon application processing due to having to wait for data safe storing database changes and or transaction commits to be completed at the target database before they can be completed at the source database. Application latency generally requires that the network communication interconnect between the source and target systems have low communications network latency.

Coordinated Commits A data replication method using asynchronous replication to replicate data changes from a source system to a target system but in which the data changes must be safe stored or applied on the target system before the source system can commit. Coordinated

Commits provides the advantages of synchronous data replication in that no data changes will be lost upon a source system or network failure and that there will be no data collisions when the data has been fully applied to the target database. It provides the advantages of asynchronous replication in that there are no distance limitations between the source system and the target system.

Collector A process running on a source system. The process accesses database changes from a change log or other audit trail to be replicated to a target database over a communication channel.

Consumer A process running on a target system. The process receives database changes over a communication channel from a Collector and applies them to a target database.

Queue Manager QMGR A process for temporarily storing changes to a target database in a queue of changes until they can be applied to the target database. The QMGR can be resident either on the source system or on the target system.

Event Tx Tracking Module A function designed to monitor log modify and or append useful information to an event or to a transaction and to potentially exercise certain controls over the transaction s processing.

Selection Engine A process or program that identifies uncompleted transactions for an Event Tx Tracking module to join.

Certain terminology is used herein for convenience only and is not to be taken as a limitation on the present invention.

It is a purpose of the present invention to provide methods that allow a process to invoke additional processing functionality and to gather log and or append qualifying information to audited transactions including those that the process initiates and those that are initiated by system facilities. New processing functionality that may make use of the appended qualifying information includes enhanced security assurance that regulatory requirements are being met implementation of new business policies or applications and many other enhancements to existing applications. The additional information that is needed for the enhanced processing functionality is not necessarily included in the event or transaction being processed but it is available from other resources in the system.

It is a further purpose of the present invention to integrate this method into existing audited transaction processing systems with no coding changes to the applications. The goal is to create a safer more efficient and more reliable way than the use of prior art intercept library or intermediate process approaches.

For example information that can be used to add processing functionality to a transaction might be obtained as follows. The originator of an event is often identified by the channel over which the event is received. The changes made by the event are available from the Transaction Manager s change log. The location of a mobile device can be determined by its GPS coordinates. The timing of the event is known from the system clock. The type of device used to generate the event may be contained in a table that correlates user IDs with device types. The reason for the transaction may be deduced from a rules engine. Most or all of this information is not included with the original transaction but it is often available from other resources within the system often only during the time that the transaction is active e.g. before commit or abort .

By adding certain elements of information such as the above to an audited transaction significant additional processing functionality can be added to the processing of the transaction. For instance the restrictions on data access to users on mobile devices might be tighter than if they were using secure corporate terminals. The priority of processing events might be determined by the degree of urgency of the event. Transactions that violate certain rules may be rejected or they may be modified to comply with the rules. Additional functions such as fraud monitoring may be invoked if a transaction appears to be suspicious.

Various prior art means exist for integrating the Event Tx Tracking module into the event or transaction processing flow without requiring modifications to the application processes themselves. These methods include using intercept libraries and using intermediate processes. The use of intercept libraries and intermediate processes has been described in the prior art Section 1.15 Controlling Processing via an Intercept Library and the prior art Section 1.16 Controlling Processing via an Intermediate Process. These methods typically do not allow an Event Tx Tracking module to be integrated with an audited transaction begun by a system facility rather than by an application.

A novel method for integrating an Event Tx Tracking module into an audited transaction is to allow it to join the transaction as a monitoring participant or as a voting participant. In addition the use of implicit joining allows an Event Tx Tracking module to be integrated into any audited transaction whether it be initiated by an application or by the system.

The processing of an audited transaction can be monitored logged controlled and or enhanced by having an Event Tx Tracking module join the transaction and become a voting member of the transaction. By doing so the module has access to all of the transaction activity and can add significant processing functionality to the processing of the transaction for example by rejecting transactions that do not comply with a rules set or by modifying transactions to fit within a rules set. Transaction joining is applicable for use with any Transaction Manager that manages audited transactions. Examples include Transaction Managers that use the 1PC 2PC 3PC or BASE transaction protocols described in Section 1.11 Transaction Management Protocols. 

There are two ways in which an Event Tx Tracking module can join a transaction explicit joining and implicit joining. These prior art methods have been described in Section 1.9.1 Explicit Joining and Section 1.9.2 Implicit Joining. Though joining a transaction is prior art the use of an Event Tx tracking module to join a transaction as a voting resource is novel.

A benefit of transaction joining is that the Event Tx Tracking functions that it provides do not add to the path length of the transaction. The Event Tx Tracking processing typically is accomplished in parallel with the normal processing of the transaction.

The Event Tx Tracking module can join a transaction as read only if all it wants to do is monitor and log information related to the transaction.

Implicit joining has the advantage of being able to join all transactions whether they were initiated by an application or by the system. It has a further advantage over all other techniques in that it does not require a complex configuration process to implement. It must only ask the Transaction Manager to include it as a voting partner or as a monitoring partner in all transactions or in a defined subset of transactions. It eliminates the risks of misconfigurations that affect intercept libraries intermediate processes and explicit joins.

The monitoring and logging of an audited transaction by an Event Tx Tracking module is shown in . The Event Tx Tracking module identifies a transaction that has begun or is in progress an incomplete transaction that is being executed on behalf of an application or system utility. The identification of uncompleted transactions may be the task of the Event Tx Tracking module or it may be the responsibility of a Selection Engine that spawns Event Tx Tracking modules that can join each new transaction.

The Event Tx Tracking module joins the transaction either explicitly or implicitly as described in Section 1.9.1 Explicit Joining and Section 1.9.2 Implicit Joining. The Event Tx Tracking module identifies non durable attributes of the uncompleted transaction and makes them durable by logging them directly to persistent storage or by making use of a logging engine to do so. A non durable attribute may have transient values in which case the logging function makes durable at least one of the transient values.

The selected attributes are not otherwise needed in order to complete the transaction. For instance attributes that are needed for a transaction may include one or more account numbers an amount a function e.g. transfer funds from one account to another and the changes to be made to the database. Examples of non durable attributes that may be logged for extended transaction processing functionality may include the user ID of the user that started the transaction a program identifier of a program that participated in the transaction and or the time of day of the transaction. Some transaction processing systems treat these examples of non durable attributes as being durable attributes. In this case these durable attributes are by definition not non durable attributes.

The collecting and logging of the non durable attributes requires no application or system utility modifications. These functions are all performed by the Event Tx Tracking module.

The Event Tx Tracking module can be a resource manager. It can interface directly with the Transaction Manager and act as a voting resource by joining the transaction. Having joined the transaction either explicitly or implicitly the Event Tx Tracking module has access to the progress of the transaction and can participate in the processing functions applied to the transaction. In as the application makes changes to it database the Event Tx Tracking module can track the activity associated with the transaction . It can compare that activity against a set of rules in its Rules Engine and can annotate the transaction events as it records them in its event transaction log .

In when the application issues a commit request to its Transaction Manager the Transaction Manager asks each of the resources involved in the transaction if it is ready to commit. This includes not only the database but also the Event Tx Tracking module since this module has joined the transaction and is therefore a voting participant. Using its Rules Engine through its extended processing functionality the Event Tx Tracking module can decide whether to approve the transaction or to reject it. If it approves the transaction it issues a yes vote to the Transaction Manager. If the database resource and all other participants in the transaction also vote yes the Transaction Manager commits the transaction and notifies the application that the transaction has been committed . If the Event Tx Tracking module the database or any other participant in the transaction votes no the transaction is aborted by the Transaction Manager and the application is so informed.

In addition to logging the activities of an audited transaction an Event Tx Tracking module can be used to modify the actions of a transaction and to otherwise control it via its additional processing functionality and optional appended data that it can apply to the transaction.

To control an audited transaction the Event Tx Tracking module identifies a transaction that has begun or is in progress an incomplete transaction that is being executed on behalf of an application or system utility. The identification of uncompleted transactions may be the task of the Event Tx Tracking module or it may be the responsibility of a Selection Engine that spawns Event Tx Tracking modules that can join each new transaction.

The Event Tx Tracking module joins the transaction either explicitly or implicitly as described in Section 1.9.1 Explicit Joining and Section 1.9.2 Implicit Joining. The Event Tx Tracking module identifies non durable attributes of the uncompleted transaction and makes them durable by logging them directly to persistent storage or by making use of a logging engine to do so.

The selected attributes are not otherwise needed in order to complete the transaction. For instance attributes that are needed for a transaction may include one or more account numbers an amount a function e.g. transfer funds from one account to another and the changes to be made to the database. Examples of non durable attributes that may be logged for extended transaction processing functionality may include the user ID of the user that started the transaction a program identifier of a program that participated in the transaction and or the time of day of the transaction.

The collecting and logging of the non durable attributes requires no application or system utility modifications. These functions are all performed by the Event Tx Tracking module.

The Event Tx Tracking module can be a resource manager. It can interface directly with the Transaction Manager and act as a voting resource by joining the transaction. Having joined the transaction either explicitly or implicitly the Event Tx Tracking module has access to the progress of the transaction and can participate in the processing functions applied to the transaction. Once the Event Tx Tracking module has joined a transaction the application process performs the processing functions required of the transaction as generally described in Section 1.10.1 Transaction Processing and more specifically as shown in . The application process makes certain changes to one or more application databases . During this process the Event Tx Tracking module gathers information about the generated event from the Transaction Manager from the application environment or via other system calls. It also monitors the transaction activity reads inserts updates deletes and may record this information in an event transaction log .

As the transaction progresses based on the set of rules provided to it via its Rules Engine the Event Tx Tracking module can use its additional processing functionality and the optional attributes that the Event Tx Tracking module has associated with the transaction to decide to make certain changes to the transaction. It can perform its own reads of the database and can add its own updates inserts and deletes to the database . It also can change any of the events and reapply the changes.

When the transaction is completed the application process will attempt to commit the transaction as generally described in Section 1.10.2 Transaction Commit and more specifically as shown in . Since the Event Tx Tracking module is a voting participant in the transaction it can vote to commit the transaction. It also can vote to abort the transaction. The application process will issue a commit request to the Transaction Manager . The Transaction Manager will ask if all of the resources participating in the transaction are ready to commit the transaction . These resources include the databases that were changed by the transaction as well as the Event Tx Tracking module which earlier had joined the transaction as a voting participant.

The Event Tx Tracking module may in some cases obtain final event information from the application process from the Transaction Manager through other system calls and any additional transaction information from the databases that were changed. Based on the set of rules provided to it via its Rules Engine the Event Tx Tracking module can use its additional processing functionality and the attributes that have been associated with the transaction to decide to make certain changes to the transaction or to reject the transaction. It then will issue a yes vote to the Transaction Manager if it approves of the transaction or a no vote if it has decided to abort the transaction. If all resources vote yes the Transaction Manager can complete the commit of the transaction. If any resource votes no the transaction is aborted.

The actions that the Event Tx Tracking module can take on the transaction can be extended in other unlimited ways. For instance it the transaction is being replicated to a target system and one or more rules in the Event Tx Tracking module s Rules Engine are being met the transaction can proceed using synchronous replication. If one or more rules in its Rules Engine are not being met the transaction can proceed using asynchronous replication. Alternatively if one or more rules are being met the data is replicated using encryption. If one or more rules are not being met the data is replicated unencrypted.

If the Event Tx Tracking module is maintaining an event transaction log it will write the remaining event and transaction information to that log . This information is then available for use by downstream processes to access and take action.

As mentioned previously the rules that the Event TX Tracking module can implement and the actions that the Event Tx Tracking module can take on the transaction are quite extensive. They can be statically defined before system startup or dynamically loaded and re loaded as they need to change without requiring an outage of the application.

The following table is meant to highlight some of these rules and actions that the Event TX Tracking module can implement. In the following table Attribute is meant to list the item or information that is being checked or tested Rule is meant to describe the rule that is being applied to the attribute s and Action is meant to describe the action to take when the rule is satisfied or violated depending on how the rule is written .

The examples of attributes rules and actions in the table above are not meant to limit the scope of the invention. Accordingly other types of attributes rules and actions may be suitable for use with the present invention.

DP2 is the disk process in the HPE NonStop operating system available from HPE Inc. Palo Alto Calif. USA. A DP2 process is a resource manager that manages writes to a disk in the disk storage system of HP NonStop servers on behalf of the file system and TMF the NonStop Transaction Management Facility that serves as the NonStop Transaction Manager. Each disk in a NonStop server is managed by its own DP2 process. TMF implicitly joins a DP2 process to any transaction that updates the DP2 s disk. That DP2 process is then a voting participant in the transaction and can vote to commit or abort the transaction.

Likewise an Event Tx Tracking module can be a resource manager. It can interface directly with the file system and or a Transaction Manager and act as a voting resource by joining the transaction. Having joined the transaction either explicitly or implicitly the Event Tx Tracking module has access to the progress of the transaction can participate in the processing functions applied to the transaction and can vote to commit or abort the transaction.

However there are major differences between a DP2 process and an Event Tx Tracking module. A DP2 process can vote to abort a transaction only if it is unable to write the transaction s changes to its disk. On the other hand an Event Tx Tracking module can use all of the data in the transaction plus optionally added data to verify the transaction against a Rules Set managed by a Rules Engine. If one or more rules are not met the Event Tx Tracking module can modify the transaction to meet the rules and then vote to commit the transaction. Alternatively it can vote to abort the transaction. Thus it provides a great deal more flexibility and functionality in the handling of a transaction as a resource manager than does a DP2 process.

An example of Event Tx Tracking using audited transaction joining to monitor a transaction is shown in . Here Event Tx Tracking uses its additional processing functionality to monitor the activity of an audited transaction to determine if the transaction satisfies the organization s security policies. The events of the transaction are logged in a Security Audit Log for use by other applications to search for security violations.

In order to be a party to the transaction the Event Tx Tracking module has joined the transaction either explicitly as described in Section 1.9.1 Explicit Joining or implicitly as described in Section 1.9.2 Implicit Joining. As the application makes the transaction s changes to its database the Event Tx Tracking module monitors these changes for potential security violations using its additional processing functionality. It monitors the transaction flow against rules in its Security Policy Rules Engine . The module records the transaction s changes perhaps annotated according to its Security Policy Rules Engine in its Security Audit Log .

When the application requests the Transaction Manager to commit the transaction the Transaction Manager will ask each of the resources involved in the transaction whether or not it is prepared to commit . This includes the application database and the Event Tx Tracking module .

If the transaction complies with the security policy as implemented in the Security Policy Rules Engine the Event Tx Tracking Module will respond to the Transaction Manager with a yes reply allowing the Transaction Manager to commit the transaction if all other resources voted yes . If the transaction violates the security policy the Event Tx Tracking module can respond with a no reply thus forcing the Transaction Manager to abort the transaction.

2.4 an Example of how Event Tx Tracking Controls a Transaction Enforcing Transaction Security Polices

An example of Event Tx Tracking using audited transaction joining to monitor and control a transaction via the Event Tx Tracking module s additional processing functionality is shown in . In this example Event Tx Tracking monitors the activity of an audited transaction to determine if it satisfies the organization s security policies. If it does not the Event Tx Tracking module can modify the transaction to make it compliant or it can cause the transaction to be aborted.

In order to be a party to the transaction the Event Tx Tracking module has joined the transaction either explicitly as described in Section 1.9.1 Explicit Joining or implicitly as described in Section 1.9.2 Implicit Joining. As the application makes the transaction s changes to its database the Event Tx Tracking module monitors these changes for potential security violations. It monitors the transaction flow against rules in its Security Policy Rules Engine . If necessary it can modify the changes made by the transaction via its additional processing functionality so that the transaction complies with the security policies. It can also record the changes in its Security Audit Log .

When the application requests the Transaction Manager to commit the transaction the Transaction Manager will ask each of the resources involved in the transaction whether or not it is prepared to commit . This includes the application database and the Event Tx Tracking module .

The Event Tx Tracking module may review the database activity made by the transaction as recorded in the process Security Audit Log via its additional processing functionality. If the transaction complies with the security policy as implemented in the Security Policy Rules Engine the Event Tx Tracking Module will respond to the Transaction Manager with a yes reply . This allows the Transaction Manager to commit the transaction if all other resources voted yes . If the transaction violates the security policy the Event Tx Tracking module may modify the transaction s changes to bring it into compliance and vote to commit the transaction. Alternatively it can respond with a no reply thus forcing the Transaction Manager to abort the transaction.

Event Tx Tracking can be applied at both the source and target systems in data replication applications.

A use of Event Tx Tracking for synchronous replication appears in and . The synchronous replication of data is described in Section 1.18.2 Synchronous Replication and in . and represent a modified version of . shows the procedures to replicate database changes via synchronous replication under the control of Event Tx Tracking modules. shows the procedures to commit the transaction when Event Tx Tracking modules exist as voting resources.

Referring to Event Tx Tracking module A with its Rules Engine has joined the transaction in Computer A either explicitly or implicitly. Event Tx Tracking module B with its Rules Engine has joined the transaction in Computer B either explicitly or implicitly.

Database changes made by the application are applied to the source database by Transaction Manager A . Event Tx Tracking module A monitors the database changes being made by the application via its additional processing functionality. If it decides to modify these changes it sends the modifications to Transaction Manager A which will apply them to the source database.

Alternatively the Event Tx Tracking module could decide to only modify the changes that are sent to the target database and not modify the changes that were applied to the source database. This is useful for example to cull out certain source data from being sent to the target if the target database is meant to contain only data for or made by certain users and not all users.

Transaction Manager A as part of synchronous replication will send the modified database changes to Computer B. These changes are intercepted by Event Tx Tracking module B and using its extended processing functionality are modified if necessary according to its rules engine. These modifications then are sent to Transaction Manager B which will write them to the target database .

The commit process is shown in . Both Event Tx Tracking modules are voting resources in the transaction. Both must vote yes for the transaction to be committed. If either votes no the transaction is aborted.

When the application issues a commit request to Transaction Manager A Transaction Manager A will ask Transaction Manager B in the target system if it is ready to commit . It also asks the Event Tx Tracking module A in its source system if it is ready to commit since this Event Tx Tracking module has joined its transaction. Likewise Transaction Manager B will ask Event Tx Tracking module B in the target system if it is ready to commit since this module has joined its transaction. If Event Tx Tracking module B votes yes and if Transaction Manager B has been successful in safe storing or applying all of its database changes it will respond to Transaction Manager A with a yes vote .

If Transaction Manager A has been successful in safe storing or applying all of its database changes and if Transaction Manager B and the Event Tx Tracking module A all have voted yes then Transaction Manager A will tell Transaction Manager B to commit the transaction . Both Transaction Managers will commit the changes to their respective databases and the application is informed that its transaction has been committed. If any resource votes no the transaction will be aborted.

Thus by using Event Tx Tracking with its additional processing functionality the contents of the source database can be controlled according to a rules set. In addition the contents of the target database can be modified further. The contents of the target database can be different from that of the source database as defined by the rules set.

An example of the use of Event Tx Tracking in a Coordinated Commits data replication engine is shown in and .

When the application issues a begin transaction request to Transaction Manager A the application will send the transaction ID received from Transaction Manager A to the Coordinated Commits Coordinator and to Event Tx Tracking module A . Each of these components will join the transaction by sending a request to Transaction Manager A.

Transaction Manager A will enter a begin transaction token into the change log. This token will be replicated to the target system s Consumer which will send it to Transaction Manager B . Transaction Manager B will begin an independent transaction on the target system and will implicitly join Event Tx Tracking module B with its Rules Engine to the transaction. At this point the Coordinated Commits Coordinator and both the source side and target side Event Tx Tracking modules are joined to the transaction as voting resources.

Transaction Manager A will enter the application changes and the subsequent changes made by the Event Tx Tracking module A into the change log . These changes will be replicated to the target system where the Consumer will send them to the target side Transaction Manager B . Transaction Manager B will apply these changes to the target database . Event Tx Tracking module B monitors the changes to the database via its additional processing functionality and may issue modified changes to Transaction Manager B which will apply them to the target database.

Thus by using Event Tx Tracking the contents of the source database can be controlled according to a rules set. In addition the contents of the target database can be modified further. The contents of the target database can be different from that of the source database as defined by the rules set.

Note that the placement of the Event Tx Tracking modules is different from that described earlier for Synchronous Replication in and . In those examples the Event Tx Tracking modules were placed in line with the changes. In the case of Coordinated Commits the modules are shown monitoring the database updates after they have been applied to the databases. This illustrates the flexibility that can be achieved by configuring Event Tx Tracking to meet various requirements.

Transaction Manager A also asks the Coordinator if it is ready to commit . The Coordinator must ensure that the target system is ready to commit so it asks Transaction Manager B in the target system if it is ready to commit . Before Transaction Manager B can respond it must check with Event Tx Tracking module B which is a voting resource. It asks Event Tx Tracking module B if it is ready to commit . If the module is ready it responds with a yes vote . If Transaction Manager B has safe stored or applied all of the transaction s database changes it responds to the source side Coordinator with a yes vote . At this point the Coordinator can respond to Transaction Manager A with a yes vote .

If Transaction Manager A has safe stored or applied its database changes and has received a yes vote from all of its voting resources it commits the transaction. If any resource votes no or if Transaction Manager A has not been able to safe store or apply its database changes it will abort the transaction.

In the previous examples the Event Tx Tracking modules have been illustrated as free standing modules. However an Event Tx Tracking module can be embedded into any of the processes shown. The Event Tx Tracking module may have an embedded Rules Engine or it may use an external Rules Engine. For instance in a Coordinated Commit data replication engine the Coordinator the Collector and or the Consumer all could have Event Tx Tracking modules embedded within them.

If a process has an embedded Event Tx Tracking module the Event Tx Tracking module will join transactions on behalf of the process and the process will then become a voting resource for those transactions. The decision to join a transaction can be made at any point by the process depending upon logic built into a user exit.

It is important to note that the resources referenced in the descriptions of explicit joining and implicit joining in Section 1.9 Joining a Transaction are not Event TX Tracking modules. Joining a transaction with an Event Tx Tracking module is novel and is core to this invention. The resources in Section 1.9 are ones that are performing their own work and that must be part of the transaction. In the prior art they are not resources that will monitor log or attempt to modify the transaction as is the case with an Event Tx Tracking module.

Significant value can be made to a transaction by monitoring or controlling it with extended processing functionality. Additional information often is available in a system to enhance and control the information contained in events and transactions. This additional information is useful in many ways for instance to modify or reject events or transactions to be vigilant for security breaches and to monitor trends.

In the current art such information typically is known after the fact and is found in various archives. Therefore it primarily has only historical value.

However there are many cases where services can be enhanced significantly if ancillary processing functions and or information is available in real time while the event or transaction is being processed. The cost and risk of modifying existing applications often precludes such use. It is difficult if not impossible to modify many old legacy programs because the original developers are gone or the application documentation is missing.

Within the prior art exist the means to address the challenge by creating methods for acquiring this information in real time and for modifying the processing of events using the information with no application modifications. These methods rely on one or more Event Tx Tracking modules that can monitor events that can access related useful information that can add information to events and that can log or modify the processing of events using this information. Thus the information is available in real time to support enhanced services.

Modification of existing applications to support such enhancement is avoided by several prior art techniques. An Event Tx Tracking module can be implemented as an intercept library to be incorporated into an application so that the module can intercept events and can enhance them. An Event Tx Tracking module can be implemented as an intermediate process to perform the same function. However intercept libraries and intermediate processes cannot typically inject themselves into the processing of audited transactions that have been initiated by system processes. Furthermore they are subject to configuration errors as they must be added sometimes to hundreds or thousands of application processes. They are also inefficient because they increase the processing length of the application.

A novel method to add value to an audited transaction is for the Event Tx Tracking module to join the transaction. In this way it can follow and control or modify all actions performed by the transaction via additional processing functionality. The Event Tx Tracking module can optionally add information to the transaction or to the event generating the transaction to aid in the control of the functions performed by the transaction including modifying it or aborting it. Processing takes place in parallel with the normal transaction processing so that Event Tx Tracking processing does not add to the transaction processing path length. In addition by using implicit joining transactions initiated by system processes can be monitored and controlled. Implicit joining also avoids the configuration problems and risks of other techniques.

The use of joining a transaction by an Event Tx Tracking module is extendable to data replication systems in which Event Tx Tracking modules can be active on both the source and the target systems.

It will be appreciated by those skilled in the art that changes could be made to the embodiments described above without departing from the broad inventive concept thereof. It is understood therefore that this invention is not limited to the particular embodiments disclosed but it is intended to cover modifications within the spirit and scope of the present invention.


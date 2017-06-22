---

title: Implicit software dependency analysis
abstract: Methods, systems, and apparatus, including computer programs encoded on computer storage media, for generated aggregated dependencies between software elements in a code base. One of the methods includes receiving a request to generate implicit dependencies introduced by remote procedure calls in a project. A registration of a remote procedure call is identified, wherein the registration of the remote procedure call specifies a target function and a name for the remote procedure call. An invocation of the remote procedure call using the name for the remote procedure call is identified, wherein the invocation occurs in a source software element of the project. A definition of the target function of the remote procedure call is identified, wherein the target function is defined in a target software element of the project. A new dependency is generated, the new dependency being a dependency from the source software element to the target software element.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09411707&OS=09411707&RS=09411707
owner: Semmle Limited
number: 09411707
owner_city: Oxford
owner_country: GB
publication_date: 20150930
---
This application claims the benefit under 35 U.S.C. 119 e of the filing date of U.S. Provisional Patent Application No. 62 234 939 filed on Sep. 30 2015 entitled Hierarchical Dependency Analysis of Source Code the entirety of which is herein incorporated by reference.

Static analysis refers to techniques for analyzing computer software source code without executing the source code as a computer software program.

Source code is typically maintained by developers in a code base which may be referred to as a project. Developers can maintain the source code of the project using a version control system. Version control systems generally maintain multiple revisions of the source code in the code base each revision being referred to as a snapshot. Each snapshot includes the source code of files of the code base as the files existed at a particular point in time.

Cyclic dependencies are a common problem in large code bases. A cyclic dependency occurs for example when a first software package depends on a second software package the second software package depends on a third software package and the third software package depends on the first software package. Cyclic dependencies make code bases harder to maintain because a change to any one software package in the cycle can require changes to each and every other software package in the cycle.

Dependencies in source code can be represented as a directed graph. However as code bases become larger and larger visualizations of the raw dependencies between source code elements which can number many millions in large code bases tend to be less useful.

This specification describes how a static analysis system can generate aggregated dependencies among software elements in a code base. The system can use the aggregated dependencies to generate interactive user interface presentations for visualizing the structure and cyclic dependencies in a code base.

Particular embodiments of the subject matter described in this specification can be implemented so as to realize one or more of the following advantages. Users can gain an intuitive understanding of the structure and function of a complex software system by browsing interactive visualizations of an aggregated dependency graph. The interactive visualizations allow users to interactively explore complex software systems. The interactive visualizations help users to identify the causes of unnecessary complexity in software systems and to develop solutions for reducing that complexity. The intuitive interactive visualizations can be integrated into existing coding tools to provide immediate and intuitive guidance on the design of a complex software system as the system is being built. The aggregated dependency information provides users with an intuitive sense for how hard it would be to remove or rearrange certain dependencies from the code base. The computation of aggregated dependencies allows users to create model architectures with associated rules that help developers modify a code base toward the model architecture.

A static analysis system can provide highly customizable definitions of dependencies by using queries to define the dependencies. Using queries to define dependencies provides a natural mechanism for rich dependency categorization. In addition using queries is typically faster and clearer than specifying dependencies using a general purpose programming language. Furthermore using queries makes the system easier to update or extend to support new language features. The rich categorization of dependencies can be used in an interactive presentation of aggregated dependencies. For example different categories of dependencies can be visually distinguished in the presentation. Furthermore some categories of queries can be turned on or off. A dependency analysis query can operate over a full program database which can contain the entire program. Thus it is possible to perform global dependency analysis.

The details of one or more embodiments of the subject matter of this specification are set forth in the accompanying drawings and the description below. Other features aspects and advantages of the subject matter will become apparent from the description the drawings and the claims.

This specification describes static analysis techniques for generating visualizations of aggregated dependencies between software elements in a project. Large code bases can include millions of software elements and millions of corresponding dependencies between software elements. Therefore it is often impractical for a static analysis system to present visualizations of raw dependencies in the code base.

Instead a static analysis system can aggregate dependencies between software elements and present visualizations of the aggregated dependencies. An aggregated dependency between software elements merges information from two different types of relationships between software elements 1 dependency relationships and 2 hierarchical relationships. The visualizations of the aggregated dependencies assist a user in understanding the structure of the code base without overwhelming the user with raw dependency information.

In this specification the term software element refers broadly to any discrete part of a software system. A software element may be a source code element e.g. a variable function class or type. Software elements may also be build system elements including files directories libraries and packages. The definition of what software elements exist in a project is flexible. The software elements that are defined to exist in a project can thus vary according to different programming languages different build systems and different user supplied definitions of software elements.

A dependency relationship or for brevity a dependency or a software dependency represents a functional relationship between two software elements. A dependency can be described as representing that one software element depends on another software element. Thus a software element A can be considered to depend on a software element B when the software element A functions as intended only if the software element B is also available. For example a source code file may not compile correctly if a header included by the source code file is not available.

In for example an int main node that represents the function main in main.c depends on a val node that represents the variable val in main.c.

The int main node also depends on an int f node representing the function int f that is called from the function int main . The int main node also depends on an int g node representing the function int g called from the function int main in main.c.

The int g node depends on an int b node that represents the function int b called from the function int go. Similarly The int b node depends on an int g node that represents the function int g called from the function int b . 

The definition of which software elements depend on which other software elements is flexible. The dependency relationships in a project can thus vary according to different programming languages different build systems and different user supplied definitions of dependencies. For example some programming languages are interpreted rather than compiled. Thus dependences in interpreted programming languages represent run time dependencies rather than compile time dependencies.

The dependency relationships may be collectively referred to as a raw dependency graph. The term raw dependency graph is intended to distinguish the dependency relationships from aggregated dependencies which may be collectively referred to or visualized as an aggregated dependency graph. The raw dependency graph and the aggregated dependency graph are both directed graphs that can include cycles.

A hierarchical relationship typically represents a containment relationship between software elements. For example a hierarchical relationship can represent that a variable is contained in a function that a function is contained in a class that a class is contained in a file that the file is contained in a directory and that a directory is contained in the project to name just a few examples. Each hierarchical relationship defines a parent element and a child element. Thus a software element A is a parent element of a software element B when the software element B is contained in the software element A. Likewise the software element B is a child element of software element A when the software element B is contained in the software element A.

In for example an int f node is a child element of the f.c node because the definition of the function f is contained in the file f.c. Similarly the y node is a child element of the int main node which is a child element of the main.c node . The int g node is a child element of the g.c node . And the int b node is a child element of the a.c node . For simplicity the header files of the example project are not illustrated in the example hierarchy graph

The hierarchy graph also includes software element nodes representing file system constructs. For example a usr include node represents the directory usr include a home jdoe src node represents the directory home jdoe src and a home jdoe test node represents the directory home jdoe test. A root node of the hierarchy project node represents the entire example project.

Thus the f.c node is a child element of the usr include node because the source code file f.h is contained in the directory usr include. Similarly the main.c node and the a.h node are child elements of the home jdoe src node because the source code files main.c and a.h are contained in the directory home jdoe src. And the g.h node is a child element of the home jdoe test node because the source code file g.h is contained in the directory home jdoe test. The three directory nodes and are child elements of the project node because the directories are contained in the project.

Although hierarchical relationships generally represent containment the definition of the hierarchy is flexible. The definition of the hierarchy can vary according to different programming languages different build systems and different user supplied definitions which can correspond to business units geographic locations security policies or areas of responsibility. In addition in some implementations the hierarchy can also be interactively manipulated by a user.

The hierarchical relationships may be collectively referred to or visualized as a hierarchy graph or for brevity a hierarchy. When represented as a graph each node of the hierarchy represents a software element and each software element has a link with one or more other software elements. The links in the hierarchy can be directed links that represent parent or child relationships. The hierarchy may have one type of link representing a parent relationship or a child relationship or alternatively the hierarchy may have two types of links representing parent and child relationships respectively.

Typically the hierarchy includes a superset of the nodes that are in the raw dependency graph. In other words the hierarchy includes all software elements represented by the dependency graph in addition to other software elements. For example the hierarchy has nodes that represent all of the software elements represented by the nodes in the raw dependency graph . This is because the hierarchy represents containment relationships while the dependency graph represents functional relationships. Thus even software elements that are not functionally related to any other software elements will still be included in the hierarchy.

The hierarchy can often be represented as a tree with a root node representing the project. However a tree structure is not necessary. In other words the hierarchy can be represented by any appropriate acyclic directed graph that defines parent and child relationships between nodes. Some hierarchies may have multiple root nodes representing multiple projects being analyzed and some nodes in the hierarchy may be reachable by multiple paths in the hierarchy.

In this specification the set of all dependencies inbound to a node of the hierarchy and inbound to any descendant of the node in the hierarchy will be referred to as a set of aggregated inbound dependencies. In other words the set of aggregated inbound dependencies is a set union of dependencies inbound to the node and dependencies inbound to any descendant of the node in the hierarchy.

Conversely the set of all dependencies outbound from a node of the hierarchy and dependencies outbound from any descendant of the node in the hierarchy will be referred to as a set of aggregated outbound dependencies. The set of aggregated outbound dependencies is a set union of dependencies outbound from the node and dependencies outbound from any descendant of the node in the hierarchy.

An aggregated dependency thus represents a non empty intersection between a set of aggregated inbound dependencies and a set of aggregated outbound dependencies.

Typically dependency relationships represent a single raw dependency graph for the snapshot. Likewise hierarchical relationships represent a single hierarchy for the snapshot. In contrast a vast number of aggregated dependency graphs are possible for a snapshot depending on which dependencies are aggregated.

In for example the project node and three directory nodes and have been chosen for dependency aggregation. In the resulting aggregated dependency graph the project node is illustrated as containing the three directory nodes and

Each aggregated dependency link between the nodes in the graph is displayed with a count that represents a number of dependencies that contributed to the aggregated dependency. For example the home jdoe src node has one dependency on the usr include node because the file main.c in home jdoe src called one function defined in the file f.c located in the directory usr include. The home jdoe src node has two dependencies on home jdoe test node because main.c and a.c called two functions that were defined by files in that directory. The link from the home jdoe src node to the home jdoe test node may be somewhat surprising to a developer or a system architect. This is because it is difficult to see the relationship between those directory from looking at the source code alone or even a raw dependency graph. In addition it is immediately clear even at a very high level of inspection that the project includes a cyclic dependency. In particular a cyclic dependency exists between the home jdoe src node and the home jdoe test node . The reason that this cyclic dependency arises may not be clear from browsing the source code itself or complexity of the raw dependency graph . In fact it arose because functions defined in home jdoe src call a function defined in home jdoe test which itself calls a function defined in home j doe src. 

The counts associated with the links also provide an intuitive indication of how intertwined the software elements are. For example it is immediately clear that breaking the cyclic dependency in the graph is probably easier from a source code development perspective to remove the link with the count of one rather than the link with the count of two.

Thus computing aggregated dependencies allows a user to explore the structure of the source code in an intuitive way and to intuitively uncover dependencies and potential problems with the design of the code.

A user of user device can communicate with the static analysis system to browse an interactive user interface presentation of aggregated dependencies between source code elements in the code base . Typically only one snapshot or a portion thereof of the code base is analyzed at a time.

The user device can communicate with the static analysis system over a network which can be any appropriate communications network e.g. an intranet or the Internet or some combination thereof. Alternatively the static analysis system can be installed in whole or in part on the user device .

For example a user of user device can provide a request that specifies a portion of the snapshot to be analyzed. The request can be generated by an application installed on the user device . The application can be a dedicated coding tool or a light weight client e.g. a web browser.

Coding tools include any appropriate application that facilitates selection by a user of a subset of source code files in the code base that should be analyzed by the system. The static analysis system can use a coding tool plugin to integrate the analysis of source code with a particular coding tool. The coding tool plugin is a software application or module that extends the capabilities of a coding tool by allowing the selection of source code elements and the presentation of analysis results generated by the static analysis system to be integrated into the coding tool. The implementation of the coding tool plugin will depend on the particular coding tool being extended. For simplicity only one coding tool plugin is shown. However the system may include multiple coding tool plugins to support a variety of coding tools

A presentation engine receives the request and identifies one or more selected nodes that correspond to the request . The presentation engine may use the coding tool plugin to identify the selected nodes from a request generated by a coding tool.

For example the coding tool can be an integrated development environment IDE . An IDE is an application or a suite of applications that facilitates developing source code on a single user device through a graphical user interface. An IDE usually has applications including a source code editor a compiler and a debugger. IDEs often also have a file browser as well as object and class browsers. An IDE can use the coding tool plugin to allow the user to select through the IDE interface a portion of the code base for analysis. The IDE can then generate the request . The coding tool plugin can then automatically identify selected nodes corresponding to software elements for which the aggregated dependencies should be generated. The IDE can also use the coding tool plugin to present the interactive presentation of the aggregated dependencies within the IDE interface.

As another example the coding tool can be a code review tool. A code review tool is a software application or suite of software applications that developers can use to facilitate review of source code files that are the subject of previous or proposed commits or changes to the source code base . Thus a code review tool can use the coding tool plugin to allow a user to select within an interface of the code review tool a number of source code files that are part of a proposed commit to the code base . The coding tool plugin can then automatically identify selected nodes corresponding to the software elements for which the aggregated dependencies should be generated. The coding tool plugin can then present the interactive presentation of the aggregated dependencies within the code review tool interface.

The dependency aggregator receives the selected nodes and computes aggregated dependencies for the selected nodes using dependency relationships and hierarchical relationships .

A dependency engine analyzes code of the snapshot and applies one or more dependency criteria to the code of the snapshot to generate the dependency relationships . The dependency engine typically generates the dependency relationships before the request is received.

A hierarchy engine analyzes code of the snapshot as well as the structure of a build system used to build the snapshot to generate the hierarchical relationships using one or more hierarchy criteria. The hierarchy engine also typically generates the hierarchical relationships before the request is received.

Both the dependency criteria used to generate the dependency relationships and the hierarchical criteria used to generate the hierarchical relationships can include language specific project specific and other user defined criteria.

Unlike the dependency relationships and the hierarchical relationships the aggregated dependencies are typically computed in real time. This is due to the vast number of possible software elements and the vast number of possible aggregated dependencies between those software elements making it infeasible in time and storage space to generate every possible aggregated dependency before the request is received. In other words the dependency aggregator computes the aggregated dependencies after the system receives the request and after receiving the identification of the selected nodes .

The dependency aggregator provides the aggregated dependencies to a link analyzer . The link analyzer processes the aggregated dependencies to identify candidate removable links. Candidate removable links are suggestions for how the project can be improved. Candidate removable links can be identified due to links violating one or more explicit or implicit rules for how aggregated dependencies among software elements in the project should be arranged. In reality a candidate removable link cannot simply be removed without incurring consequences to the project. For example developers will typically need to modify one or more source code files in order to remove a link from the aggregated dependency graph.

One example of an implicit rule that is almost universal in all software development is that cyclic dependencies are undesirable. Thus the system can identify cycles in the graph and suggest by providing candidate removable links ways that the cycles can be removed from the graph with minimal impact to the project. The link analyzer thus classifies links in the aggregated dependencies as retained links or candidate removable links. Classifying links as retained links or candidate removable links is described in more detail below with reference to . The link analyzer then provides the retained and candidate removable links to the presentation engine .

The presentation engine generates an interactive user interface presentation having the retained and candidate removable links . The interactive user interface presentation displays aggregated dependencies for the portion of the snapshot identified by the request . The presentation engine then provides the interactive user interface presentation back to the user device for presentation to the user possible by using the coding tool plugin . Example interactive user interface presentations that make use of retained and candidate removable links are described in more detail below with reference to .

The system receives a request for aggregated dependencies for a portion of a snapshot of a code base . The request can for example specify one or more software elements of the snapshot for which aggregated dependencies should be generated.

For example the user can view an interactive presentation of an aggregated dependency graph. Example interactive presentations of the aggregated dependency graph are described in more detail below with reference to .

The system obtains dependency relationships between software elements in the snapshot of the code base . The system can represent each distinct software element in the snapshot with a unique ID. The system can also maintain metadata for each distinct software element in a metadata table or other form of data storage. The metadata for a software element can include location information for example a location in a file of the software element a location of the file in a file system or both.

The system can represent a dependency relationship with a pair of software element IDs. A first software element of the pair which is referred to as the source element represents a software element that depends on a second software element of the pair which is referred to as the target element. Because of the directional nature of the dependency relationships two software elements can depend on each other in which case two dependency relationships would exist between the two software elements.

The system can store the dependency relationships as a two column table. The first column represents the software element ID of the source element and the second column represents the software element ID of the target element. The system can then use the row number of the table to uniquely identify each dependency relationship.

The system obtains hierarchical relationships between software elements in the snapshot of the code base . The system can represent a hierarchical relationship with a pair of software element IDs. A first software element of the pair which can be referred to as the parent element represents a software element that is a parent in a hierarchy of a second software element of the pair which can be referred to as the child element.

The system can likewise store the hierarchical relationships in a two column table. The first column represents the software element ID of the parent element and the second column represents the software element ID of the child element. The system can then use the row number of table to uniquely identify each hierarchical relationship.

The system can define a number of different hierarchical relationships in order to generate the hierarchy graph. For example instead of using files and directories as the nodes of the hierarchy the system could use namespaces to define the hierarchy. Then if different classes were defined in different files but were in the same namespace nodes representing the classes would share a parent in the hierarchy.

The system processes the dependency relationships and the hierarchical relationships to generate data representing an aggregated dependency graph . For each pair of selected nodes representing software elements the system can determine whether a first software element of the pair or any of its descendants depends on a second software element of the pair or any of its descendants. If so the system generates a link representing the aggregated dependency between the nodes representing the first and second software elements.

Computing the aggregated dependencies from the dependency relationships and the hierarchical relationships will be described in more detail below with reference to .

The system provides the data representing the aggregated dependency graph in response to the request . For example the system can generate a presentation that illustrates the aggregated dependency graph. The system can also generate any appropriate representation of the graph for consumption by another software tool.

The system receives an identification of a pair of nodes . Each node represents a software element in the hierarchy. For example a user can provide a selection of one or more nodes of a portion of an aggregated dependency graph.

The system generates a set of aggregated outbound dependencies which is a set union of dependencies outbound from a first node of the pair and dependencies outbound from any descendants of the first node in the hierarchy . As described above each dependency relationship in the snapshot has a unique ID. Thus the system can generate a set of aggregated outbound dependencies as a set of all dependency IDs in which the first node or any descendant of the first node in the hierarchy occurs as a source element.

The system generates a set of aggregated inbound dependencies which is a set union of dependencies inbound to a second node of the pair and dependencies inbound to any descendants of the second node in the hierarchy . Similarly the system the system can generate a set of aggregated inbound dependencies as a set of dependency IDs in which the second node or any descendant of the second node in the hierarchy occurs as a target element.

The system computes a set of aggregated dependencies as an intersection of the aggregated outbound dependencies for the first node and the aggregated inbound dependencies for the second node . If the intersection is not empty the system generates an aggregated dependency link from the first node to the second node. The system can repeat the process in reverse for determining whether an aggregated dependency link exists from the second node to the first node.

Techniques for representing the sets of aggregated inbound dependencies and aggregated outbound dependencies and for quickly computing the intersection of the sets using these representations are described in more detail below.

The system receives an aggregated dependency graph . As described above the system can compute the aggregated dependency graph from dependency relationships and hierarchical relationships. The system can compute the aggregated dependency graph in response to a user selection of one or more nodes representing software elements of a code base.

The system assigns weights to links in the aggregated dependency graph . Between a first software element and a second software element the weight of a link represents how significantly the first software element depends on the second software element. The significance of the dependency increases as the number of descendants of the first software element that depend on the second software element or any descendants of the second software element increases.

In some implementations the system computes a count of dependencies from the first software element and any descendants of the first software element to the second software element or any descendants of the second software element. The system then uses the count to compute the weight for the link between the first software element and the second software element. In some cases the weight is the count itself.

The system can also use a variety of other factors when computing the weight. For example the system can consider the type of dependency as some types of dependencies are easier to remove than others. The system can also consider a measure of how tangled a target of the dependency is with siblings of the target. For example if A depends on a constant defined in B and the constant in B is not used at all then the constant can be moved to A with little difficulty. On the other hand if the constant is used throughout B removing the dependency is harder and the system can adjust the weight accordingly. The system can also consider other factors e.g. cyclomatic complexity of a target of the dependency.

One benefit of using the count of dependencies as the weight is that it provides a user with a very useful and intuitive sense for how hard the link would be to remove. When the weight represents a count of dependencies the weight intuitively indicates how many software elements need to be changed in order to remove the link.

The system can also compute the weight based on a distance between the first software element and the second software element. The distance can represent how intertwined the two software elements are in terms of their occurrences in the code base. For example if the first software element and the second software element co occur infrequently the distance is likely to be large. But if the first software element and the second software element co occur frequently the distance is likely to be small. In this context distance is inversely proportional to weight because a large distance represents a smaller significance of the dependency between the software elements. Thus a larger distance will result in a smaller weight.

The system need not compute weights of the links as a separate and subsequent process to that of generating the aggregated dependency graph. Rather the system can compute the weights of the links as the aggregated dependency graph is being constructed.

In some implementations the system provides a user interface that allows a user to mark some links as non candidates for removal. This can be useful for example when a portion of the code base is not controlled by the user. Thus in response to the user designation of links as non candidates for removal the system can assign a very high weight or a special value that indicates that the link is not to be classified as removable under any circumstances.

The system determines cyclic dependencies in the aggregated dependency graph . A software element A depends transitively on a software element B if a path in the aggregated dependency graph exists from a node representing software element A to a node representing the software element B. A cyclic dependency occurs whenever a particular node transitively depends on itself.

The system can determine cyclic dependencies using any appropriate search procedure. For example the system can perform a recursive depth first search marking nodes as visited as they are processed. When the system processes a node that has already been marked as visited the system can determine that a cyclic dependency exists. When the system determines that a cyclic dependency exists the system processes links along the cycle to identify a candidate link for removal.

Thus if there are more cycles to be processed the system processes the next cycle by adding the link along the cycle having the lowest weight to a set of candidate removable links branch to . The set of candidate removable links identifies candidate links that the system can suggest to a user as ways to get rid of cyclic dependencies in the code base.

The system decreases the weight of other links in the cycle by the weight of the link that was added to the set of candidate removable links . Decreasing the weight of other links in the cycle can reveal when a heavy link that is part of multiple cycles is more preferable to remove than multiple light links on single cycles. In other words as each cycle of the heavy link is processed the heavy link becomes effectively cheaper and cheaper to remove.

The system backtracks to the source of the added link marking each node as not visited . The system has already determined a candidate link for removing the currently detected cycle. However the system can mark nodes on the cycle as not visited so that they will be considered appropriately if they are part of other cycles in the graph.

The system can then continue searching the graph for additional cycles processing each newly found cycle.

If there are no more cycles to be processed the system discards links from the set of candidate removable links that do not result in cycles if they remain in the graph branch to . Because each cycle is processed separately it is possible that the set of candidate removable links includes more links than must be removed to remove all cycles in the aggregated dependency graph. For example after adding a first link to the set of candidate removable links that would break cycle C the system may then add a second link to the set of candidate removable links that would break cycle C and which would also happen to break cycle C as well. Thus the first link and the second link need not both be in the set of removable links. Rather the first link can be discarded from the set of removable links so that it will be reclassified as a retained link.

Because the weight of the links approximates the amount of work that would be required to remove the link the system can discard links in the set of candidate removable links in order of decreasing weight. In other words the system can iterate over links in the set of candidate removable links from heaviest to lightest discarding each link from the set that would not reintroduce a cycle assuming that all other links in the set of candidate removable links were indeed removed.

In some implementations the system provides a user interface that allows the user to specify an order in which the candidate removable links should be discarded from the set. This can be useful for example when parts of the code base represent well tested or legacy software that the user would rather not modify significantly. Thus the user can move links from parts of the code base that the user does not want to modify to the top of the list and the system will first attempt to remove those links from the set of candidate removable links.

The system classifies remaining links in the set of candidate removable links and classifies all other links as retained links . In other words the system classifies links that are not candidates for removal as retained links. The system can then suggest links that are classified as candidate removable links to the user.

To do so the system can then generate various user interface presentations that illustrate the aggregated dependency graph arranged according to retained and candidate removable links.

The examples illustrate the structure of a simple example software project even or odd written in C and which has the following source code files.

As shown in the example source code the function odd has one dependency on the function even due to calling the function even one time while the function even has two dependencies on the function odd due to calling the function odd twice. Also because the two functions depend on each other the aggregated dependency graph will include a cycle. After processing the source code of this project and generating aggregated dependencies the system can generate a variety of layouts to present this information.

The example presentation includes a hierarchy explorer that allows a user to interactively browse the hierarchy graph. The example presentation also includes an aggregated dependency graph pane that shows nodes from the hierarchy and links representing the aggregated dependencies between them.

Each of the links is presented with an associated count representing the number of dependencies between the corresponding software elements. The link for example represents that the file even.c has two dependencies on the file odd.c.

In the default layout all nodes of the hierarchy are selected for presentation. However the system may cut off some nodes at a particular level of detail in order to comply with space limitations of the aggregated dependency graph pane . For example the illustrated aggregated dependency graph also includes a usr node that contains only system software code as opposed to user code.

A user can also select or filter dependencies by type. In other words the user can choose different types of dependencies to be shown or hidden from the graph.

In response to the selection the system updates the presentation of the aggregated dependency graph to show only a graph having the selected nodes of the hierarchy. In this example the aggregated dependency graph pane no longer shows a node representing the usr system software node.

A user can drill down further into the presented nodes by using an expansion icon presented with each node in the aggregated dependency graph pane e.g. expansion icon of the even.c node.

The system can highlight the exact source code causing the dependency selected by the user. For example the source code pane highlights the call to the function odd which is the code that causes the dependency selected by the user.

The system then determines one or more candidate removable links for the selected nodes of the hierarchy. For example the link is a candidate removable link which the system visually distinguishes from other links by presenting the candidate removable link as a dashed line.

The system can visually distinguish the removable links from the retained links in any appropriate way. For example the system can present the removable links in a different color a different style or a different line thickness to name just a few examples.

A user can also select or filter the cyclic dependencies by type. Cyclic dependencies in the code base may be problematic for some types of dependencies but not others. For example include type dependencies are an example dependency type for which cycles may not be a problem. Thus the user can select a particular type of dependency to show or filter another particular type of dependency for which cycles are not a problem.

The system can also present the weight of each link near the link itself. The presentation of the weight provides users with an intuitive indication of how much work on the code base would be required to remove each link. For example the link has a weight of 1 whereas the other link in the cycle has a weight of 2. Thus removing link will probably require less effort than removing the other link in the cycle.

The system can also present a clustered layout that is based on the layered layout. In the clustered layout the system presents each layer as a proposed cluster and presents links representing aggregated dependencies between the proposed clusters instead of between the individual software elements. The system can generate the clusters as a suggestion to a user for how the software elements should be packaged according to the aggregated dependencies.

The system can collapse the nodes in the tangle to represent the tangle as a single tangle node in the aggregated dependency graph. The system can then update the aggregated dependencies to illustrate links between the tangle node and other software elements instead of links between individual software elements of the tangle.

When the system has already classified links in the graph as retained links and candidate removable links the system can add each node connected to an inbound or outbound removable link to a tangle node. The system can also add nodes that are only connected to other nodes in the tangle to the tangle as well.

When the system collapses all cyclically connected nodes into tangle nodes the resulting graph is acyclic. For example the aggregated dependency graph in is an acyclic graph.

The tangle node in the presentation has a user interface element that allows the user to explore software element nodes in the tangle. In this example the user interface element is a plus icon which indicates that the user can select the plus icon to see further software element nodes that are in the tangle.

The expanded tangle layout shows both 1 aggregated dependencies between the tangle node and other software elements outside the tangle and 2 aggregated dependencies of the individual software elements inside the tangle.

The expanded tangle layout essentially isolates each tangle as a separate cyclical graph with each separate cyclical graph represented as an individual tangle node in an acyclic graph. Within the individual tangle nodes the system can suggest candidate removable links for removal.

A system can use the aggregated dependency techniques described above to assist users in designing and exploring architecture goals for a project. In particular in addition to generating and displaying aggregated dependency graphs based on the actual hierarchy of software elements in the project the system can also generate and display aggregated dependency graphs for model architectures specified by a user.

A model architecture is a user specified hierarchical arrangement of software elements in a project and a set of user specified rules representing how the user would like dependencies in the project to be arranged. The system can then generate an aggregated dependency graph for a given model architecture and a given set of rules. The aggregated dependency graph can highlight discrepancies between the specified rules of the model architecture and the aggregated dependencies as they occur in the project.

In order to conform the source code in the project to the model architecture a developer or team of developers must modify the source code so that the dependencies between source code elements correspond to the rules of the model architecture. This procedure may include moving source code files from one portion of the project to another or modifying the source code files to eliminate dependencies that are not allowed by the rules.

There are variety of use cases for a user wanting to specify a model architecture. For example on some projects different teams may be responsible for different portions of the project. It may be desirable to structure the dependencies in the project so that none of a first portion developed by a first team depends on any of a second portion developed by a second team. Such an arrangement can simplify and streamline the development process because the work of the first team does not depend on the work of the second team. It may also be desirable for a developer to specify generally that a first portion of the project should not depend on another portion of the project.

The system receives a model architecture . The model architecture is a tree structured graph that include two types of nodes group nodes and unit nodes.

Every leaf node in the model architecture is a unit node and each unit node directly corresponds to one of the elements in the hierarchy graph of the project. In some implementations unit nodes directly correspond to software element nodes that are files or directories in the build system. When computing aggregated dependencies between nodes in the model architecture the system will use dependencies of descendants of the unit node s corresponding element in the hierarchy. In other words each leaf node of the model architecture is a unit node that represents a subtree of the hierarchy.

Every non leaf node in the model architecture is a group node. Each group node has one or more children which can be other group nodes or unit nodes.

The model architecture can be specified in a number of ways. For example a user can create a configuration file that specifies each group node in the model architecture and each of the group node s children which may include unit nodes.

The membership of group nodes and unit nodes can also be specified by arbitrary regular expressions that the system will evaluate to generate the model architecture. For example if X Y and Z represent files or folders a user can specify that a particular unit node contains the software elements in X Y Z.

Software elements of the hierarchy can be shared among multiple different unit nodes. In other words although the model architecture is a tree structure the unit nodes at the leaves of the tree structure may correspond to overlapping software elements in the project.

The system can also provide the interactive functionality for the model architecture to be generated interactively by a user within a user interface presentation. For example in an interactive presentation of an aggregated dependency graph a user can drag and drop nodes of an aggregated dependency graph to be unit nodes of a model architecture. Thus a user can drag and drop a particular node of an aggregated dependency graph to be a child node of a particular group node of the model architecture.

In some implementations a user can specify multiple model architectures for a same project. For example a user can specify one model architecture for one team and a second model architecture for another team.

The system can also generate an initial model architecture automatically and then allow the user to modify the initial model architecture interactively. The system can then generate an initial model architecture that represents the result of the hierarchical clustering algorithm. In some implementations the system can truncate the resulting model architecture tree at a particular predetermined depth. The user can then interactively modify the automatically generated initial model architecture.

The system generates an aggregated dependency graph according to the model architecture . The system can generate the aggregated dependency graph for the model architecture in a similar to that which is described above for the original hierarchy graph for the system. However there are two differences. First because unit nodes represent subtrees of the original hierarchy graph the computation of aggregated dependencies uses dependency information from both the model architecture and the hierarchy graph. In other words when obtaining dependencies of descendants of a node in the model architecture the leaf nodes of the model architecture are not necessarily the end point. Rather the system can continue gathering dependencies of descendants for elements in the hierarchy that occur in a subtree represented by the leaf node of the model architecture. Second because group nodes may not directly correspond to elements of the hierarchy the aggregation of group node dependencies may include solely dependencies of descendants of the group node in both the model architecture and the hierarchy graph.

Thus a dependency exists between a first node and a second node in the model architecture when a first software element represented by or contained by the first node or any of the first node s descendants in the model architecture or in the hierarchy graph depend on a second software element represented by or contained by the second node or any of the second node s descendants in the model architecture or in the hierarchy graph.

As shown in the aggregated dependency graph illustrates all of the unit nodes of the model architecture rather than elements of the original hierarchy graph. In this example no rules have been specified. Thus the system can present the group nodes and unit nodes of the aggregated dependency graph in any appropriate ordering.

The system receives rules associated with the model architecture . The user can specify a variety of rules for the model architecture that specify how a user would like the dependencies of the project to be arranged.

The system determines aggregated dependencies that do not conform to the rules and the system generates a presentation of the aggregated dependencies . When dependencies in the project do not conform to the rules the system can visually distinguish the discrepancies in order to help a user identify how the project can be modified so that it conforms to the specified rules.

The system can compute a count of aggregated dependencies that do not conform to the rules and provide the count for display within the presentation. This allows a user to see a quantitative measure of how far away the project is from the model architecture. The system can also compute a difference between a current count and a previously computed count of aggregated dependencies that do not conform to the rule and provide the difference for display within the presentation. This allows the user to see progress toward the model architecture.

The various types of rules that a user can specify for a model architecture will now be described in more detail. Some rules for the model architecture can be implicit in the definition of the model architecture. For example in some implementations the model architecture specified by the user has an implicit ordering among sibling nodes. This ordering represents a set of rules specifying that no unit node should have an aggregated dependency on a previous unit node in the order.

The system can use the ordered specified in the model architecture to generate the presentation of the aggregated dependency graph . For example in the aggregated dependency graph the ordering of the nodes from top to bottom corresponds to the ordering of the nodes in the model architecture

As shown in the aggregated dependency graph the unit node for odd.c has a dependency on a previous unit node in the order even.c which violates the implicit ordering rule specified by the model architecture. Thus the system visually distinguishes the dependency between the node representing odd.c and the node representing even.c.

Some rules are dependency specific. For example a user can explicitly allow or disallow a particular dependency. illustrates explicitly allowing a particular dependency. The user can for example select the dependency and choose a user interface element that allows the user to specify that that dependency is explicitly allowed. If a dependency is explicitly allowed the system can suggest other dependencies as candidates for removal. Explicitly allowing or disallowing dependencies can help the user to focus on dependencies that are good candidates for removal. Similarly the system can also allow a user to explicitly disallow a selected dependency. illustrates explicitly disallowing a particular dependency using user interface element

The system can also allow the user to categorize some dependencies as undetermined. Thus if the user is in the process of determining which dependencies are allowed and which are forbidden the system can allow the user to make some dependencies undetermined to indicate that the dependency is a candidate for being labeled as forbidden.

A user can also specify one or more explicit rules. An explicit rule specifies a set of source nodes a set of target nodes and an indication of whether dependencies that match the explicit rule are forbidden or allowed. Then if any dependencies exist in the aggregated dependency graph from any of the source nodes to any of the target nodes the system will treat the dependency as forbidden or allowed according to the rule.

A user can also associate each group node with one or more of a set group rules which imposes a desired property for dependencies among children of a particular group node. In some implementations a group rule for a group node is automatically applied to all children of the group node even when additional children are added to the group node. Each group rule can help a user to achieve a different design goal for a particular project.

One group rule has already been described above which is an ordering between sibling nodes of children of the group node. The ordering group rule is useful to ensure that children within a group do not have any cycles. In other words by ordering the children in a group a user can implicitly forbid cycles within the group without having to manually specify which cycles are not allowed.

The ordering group rule is also useful for intuitively specifying a layering of software elements that should remain separated. For example a user could specify an ordering to segregate a user interface layer from a data storage layer. The user interface layer could depend on the data storage layer but the data storage layer cannot depend on the user interface layer.

One example group rule is Independent which specifies that dependencies among siblings in the group are forbidden. This group rule is useful when the user wants to segment a project into completely modular units that should never depend on each other.

Another example group rule is Private which specifies that dependencies from outside the group to any children of the group are forbidden while dependencies among children of the group are permitted. This group rule is useful when the user wants to hide portions within a module from other software elements outside the module. For example one module of a project could contain both code for an application programming interface API as well as implementation code of the API. A user could then use a model architecture to enforce the design convention that other modules should depend on the public API but not on the implementation code. A user could easily impose a rule for this design convention by marking the implementation code as private. Then the system would automatically identify when any other modules had dependencies on the implementation code.

Another example group rule is Acyclic which specifies that dependencies among children of a group cannot contain any cycles. If the children of a group contain cycles the system can suggest cycles for removal for example as described above with reference to .

Finally a user can specify that a group node is Unrestricted meaning that all dependencies are allowed. For example user interface element of allows the user to specify that the group node Specification is an Unrestricted group which is reflected in the hierarchy explorer.

The system may visually distinguish different dependencies according to different group rule types that are violated. For example all dependencies that are identified as disallowed because they violate the Acyclic rule can be displayed in a different color or style than other dependencies. This can aid the user in understanding the structure of the model architecture and how some of the dependencies are identified as forbidden.

A user can also define categories of group rules and explicit rules and can then select categories of rules whose violations should be displayed removed or highlighted. The system can also visually distinguish the categories from each other when displaying the dependencies and can also display the different categories in other analysis tools.

A user can also define group and explicit rules in terms of dependency categories. For example between two nodes A and B a user can explicitly allow a category corresponding to function call dependencies. Between two other nodes C and D a user can explicitly disallow a category corresponding to macro dependencies.

A user can also specify a combination of different types of rules. For example a user can specify a group rule that applies to all children of a group node. The user can then refine the group rule for some children of the group node by specifying explicit rules that apply only to those children of the group node. For example the user could specify allow rules for individual nodes that override things that the group rule would otherwise consider to be forbidden. A user may also specify that multiple group rules should be applied to a single group node.

The system can assign a priority to rules in case some combinations of rules conflict with one another. For example a root group node may be associated with one type of group rule and a child group node may be associated with another type of group rule. To resolve the conflict the system can specify that group rules associated with group nodes that are closer to the root node of the model architecture override group rules associated with group nodes that are lower down in the model architecture.

In some implementations a user can explicitly specify a priority among rules. For example a user may specify that it is more important for a particular portion of a project to have the Private rule type than for that portion of the project to have the Acyclic rule type. To do so the user can assign a higher priority level to the group rule for the project. Thus if any parent group nodes happen to have the Acyclic rule type and the rule type conflicts with the higher priority rule type the system can resolve the conflict in favor of the rule type having the higher priority.

A user can also use existing rules to build new rules. For example a user can define a new group rule that references two existing explicit rules.

A user can also assign names to sets of group nodes and unit nodes which may then be referenced by rules. For example the system may assign a name driver with a particular set of unit nodes that represent driver source code. The system may then reference the name of the set of unit nodes when defining a group or an explicit rule that will apply to the set of unit nodes. This allows users to more easily build up libraries of useful rules for a particular project.

The names assigned to sets of group nodes and unit nodes in one model architecture can also be referenced in other model architectures for a same project. For example a rule can assign a name to a first portion of a software project handled by a particular team which first portion may be represented by a unit of one model architecture. A second model architecture can use a rule that specifies the name of the first portion. As an example the second model architecture can include a rule that specifies that the work of a particular team of developers cannot depend on the first portion of the project.

As part of the interactive presentation the system can also present metrics that indicate progress toward the model architecture. For example the system can compute a number of allowed undetermined and disallowed dependencies in the aggregated dependency graph for the model architecture. The system can then present these metrics alongside the aggregated dependency graph which can aid developers in tracking their progress.

One example metric is a number of pairs of group nodes and unit nodes for which dependencies would not be disallowed regardless of whether any dependencies between the pairs exist. This metric is an indication of how modular the group nodes and unit nodes are from each other.

Another example metric is a number of pairs of group nodes and unit nodes for which dependencies would be allowed. This metric can indicate how easy it would be to undertake further development that ties the nodes of the model architecture together. If there are relatively few pairs for which the dependencies would be allowed the metric would be small and further development would likely introduce more disallowed dependencies. On the other hand if there are relatively many pairs for which the dependencies would be allowed the metric would be large and further development would not be as likely to introduce disallowed dependencies.

A static analysis system can provide highly customizable definitions of dependencies by using queries to define the dependencies. Using queries to define dependencies provides a natural mechanism for rich dependency categorization. In addition using queries is typically faster and clearer than specifying dependencies using a general purpose programming language. Furthermore using queries makes the system easier to update or extend to support new language features.

The rich categorization of dependencies can be used in an interactive presentation of aggregated dependencies. For example different categories of dependencies can be visually distinguished in the presentation. Furthermore some categories of queries can be turned on or off.

Using queries to define dependencies also allows additional categories of dependencies to be added to the system. This allows the system to be readily customized for particular projects or particular programming languages.

A static analysis system can provide highly customizable definitions of dependencies by using queries to define the dependencies. Using queries to define dependencies provides a natural mechanism for rich dependency categorization. In addition using queries is typically faster and clearer than specifying dependencies using a general purpose programming language. Furthermore using queries makes the system easier to update or extend to support new language features.

The rich categorization of dependencies can be used in an interactive presentation of aggregated dependencies. For example different categories of dependencies can be visually distinguished in the presentation. Furthermore some categories of queries can be turned on or off.

Using queries to define dependencies also allows additional categories of dependencies to be added to the system. For example a system can use non source code files e.g. XML or JSON configuration files to generate query based dependencies. The system also allows users to add additional categories of dependencies that are specific to their project or code base.

The system maintains a database of software elements in a project . The system can populate the database during an extraction process that analyzes source code of the project. The system can determine a variety of attributes of each software element in each source code file used during the build process and populate the database with such attributes.

For example in a particular source code file the system can identify all function calls and associate an entry in the database for the source code file with each of the function calls in the source code file. The system can associate each function call with attributes of the function call e.g. a name of the function called the number and types of arguments used a location within a source code file in which the function call occurred to name just a few examples.

The system can populate the database with any appropriate attribute for software elements in the project. Other example attributes include variables used static variables declared type definitions type declarations include directives macro invocations template instantiations and namespace declarations. In general the attributes the system stores in the database are programming language dependent. In other words the system can populate the database with different attributes for different programming languages.

The system receives a query defining a dependency category between the software elements in the project . Queries allow a raw dependency graph to be customized for any appropriate project build system or programming language. The query can be either one of a set of standard queries supplied by the system or a custom user defined query.

The aggregated dependency graph can thus be similarly customized by adding or removing queries that define the raw dependencies in the project. The aggregated dependency graph will thus also reflect the user defined dependencies between the software elements in the project.

Each query that defines a dependency category specifies one or more source attributes one or more target attributes and a relationship between the source attributes and target attributes.

The source attributes include one or more attributes of a source software element of the user defined dependency. The source attributes thus identify which of the software elements in the database are eligible to be a source software element of the user defined dependency. For example if the query defines an include dependency between a first software element and a second the source attributes would be that i the first software element has an include statement and ii the name of the file that is included.

The target attributes include one or more attributes of a target software element of the user defined dependency. The target attributes thus identify which of the software elements in the database are eligible to be a target software element of the user defined dependency. If the query defines an include dependency the target attributes would simply include the name of the software element.

The query also defines a relationship between the source attributes and the target attributes. In the include dependency example the relationship would be that the name of the file included by the source software element is equal to the name of the target software element.

In this example the system searches the database for all instances where a function definition is referenced by a function call.

Another example query identifies dependencies from methods depending upon the types declared in the method parameters 

In this example an exists quantifier identifies parameters associated with each method. Then a utility predicate usesType unwraps generic types so that if the parameter type is List the method depends on both the List and Foo types.

The system searches the database to identify pairs of software elements having the attributes defined by the query . The system can identify source software elements having the one or more source attributes of the query and target software elements having the one or more target attributes of the query. The system can then identify pairs of software elements when the relationship specified by the query is satisfied by attributes between software elements.

The system generates data representing a raw dependency graph for the project the raw dependency graph having one or more query defined dependency links . The system can generate a new raw dependency graph or supplement an existing raw dependency graph e.g. the raw dependency graph as described above with reference to .

After including the user defined dependency in the raw dependency graph the system can generate or update an aggregated dependency graph and an associated interactive presentation. Thus a user can easily add user defined dependencies for a project that will appear in the interactive presentation.

Because the aggregated dependencies are defined as a set union of dependencies inbound to or outbound from a particular node in the hierarchy query dependencies provide a powerful and flexible extension mechanism. In other words once a user defines a new query that defines dependencies in a project the mechanism for computing aggregating dependencies automatically integrates the newly defined dependencies into the aggregated dependency graph and its associated user interface presentation all without the user having to specify any relationship to any other dependency categories.

Because the system can define the user defined dependencies in separate categories the system can visually distinguish user defined dependencies from other dependencies in the project. For example the system can present the user defined dependency links in a different color a different style or a different line thickness to name just a few examples.

The system can also provide user interface elements that allow a user to turn particular categories of queries on and off. For example a user may turn off dependencies that are uninteresting because they involve low level source code elements. For example a user may want to turn off link time dependencies for C projects. As another example some libraries use macros defined by a caller in order to configure their functionality. If turned on these dependencies may appear as dependencies from the library to user code which can be misleading. Thus a user can turn off macro dependencies to disable the display of these dependencies.

One example of using queries to define new dependency categories in a project involves using queries to define link time dependencies in a project. illustrate an example of using queries to define link time dependencies in a project. Link time dependencies are dependencies between software elements in the project that arise only due to symbols being resolved by a linker during a build of the project. The static analysis system can include a query that adds link time dependencies to the raw dependency graph and therefore to the aggregated dependency graph for the project. Because the query defines a separate category of dependencies a user can easily turn on or turn off link time or compile time dependencies or both.

The project includes a header file f.h that declares a function f. The project includes a first source code file main.c that calls the function f and a second source code file f.c that includes the definition of the function f. Each of f.c and main.c include f.h .

When a build system builds the example project a compiler will compile f.c into f.o and main.c into main.o . At this point the call to function fin main.o is still unresolved. In other words the definition of the function f will be supplied by f.o at link time.

Thus a linker links f.o and main.o to produce a target go.exe . In this example the target is an executable file but the target could also be a library. At link time the definition of the function fin f.o is linked to the call to the function fin main.o . Thus when go.exe is executed the call to f will succeed.

In an aggregated dependency graph for exploring the structure of the project it would seem natural for there to exist a dependency between main.c and f.c because source code in main.c references source code in f.c . However no such compile time dependency is generated because the file main.c makes no reference to the file f.c . This is because the definition of the function f could be supplied by any of a number of object files at link time.

Thus the system can use a query that defines link time dependencies between software elements of the project. In this example the source attributes of the query include 1 the symbol name referenced in each file and 2 a link time target of each file. In this example the database would include for main.c at least the symbol name f for the function f referenced in main.c as well as the name of the link time target go.exe .

The target attributes of the query include 1 the symbol names defined in each file and 2 a link time target of each file. In this example the database would include for f.c at least the symbol name f for the function f defined in f.c as well as the name of the link time target go.exe .

The query would also include a relationship between the source attributes and the target attributes. In this example the relationship would specify that 1 the source element link target is equal to the target element link target and 2 that the name of a symbol referenced in the source element is equal to the name of a symbol defined in the target element.

The query needs to specify both items of information because the symbol name f alone is insufficient to determine the dependency of main.c on f.c . This is because the definition of the function f could be supplied at link time by other functions. In some build systems this information is only known at link time.

After executing the query on the database the system can identify that main.c references a function defined in f.c . Therefore the system can generate a dependency in a raw dependency graph between a node representing main.c and a node representing f.c .

The system also includes a link time dependency from the node to the node . In the raw dependency graph or in an aggregated dependency graph the system can visually distinguish link time dependencies from compile time dependencies. For example the the link time dependency is represented by a dashed line while the compile time dependencies are represented by solid lines.

The query based framework for adding dependencies can be used to add dependencies in a project that are unavailable in other systems. In particular queries can be used to add implicit dependencies. An implicit dependency is a dependency from a source software element to a target software element such that building the source software element would not fail at compile time or link time due to the absence of the target software element.

Rather implicit dependencies are introduced by other aspects of the code base e.g. libraries frameworks or runtime configuration files. In other words if there is an implicit dependency between A and B the compile time and link time behavior of the build system would function as intended for A even in the absence of B. Examples of implicit dependencies include dependencies induced by remote procedure calls runtime configuration files reflection runtime type registration and dependency injection.

The system receives a request to generate remote procedure call dependencies in a project . A remote procedure call framework provides the functionality for a first software process to call a function that is executed by a different software process which may be executing on a different machine than the first software process. The first software process waits for the second process to execute the function and return a result at which point the first software process resumes execution. Thus from the perspective of the first software process the remote procedure call behaves exactly as a purely local procedure call.

Remote procedure call frameworks generally include three components. First a target function is defined. The target function is the function that will be called remotely by a first software process. Second the remote procedure call framework associates the target function with a name which in some cases can be any arbitrary string. The process of associated the target function with a name is called registration. Third the remote procedure call is invoked by providing to an invocation function the name associated with the target function during registration.

When the remote procedure call is invoked the remote procedure call framework handles the interprocess and network communication that may be required to route the request from the calling software process to the software process that will execute the target function.

The target function sum is defined in f.c and declared in f.h . The target function is registered by register.c which includes associating the target function with a string rpc sum. 

The file main.c invokes the remote procedure call by specifying the string rpc sum that was associated with the target function during registration.

Solid lines in represent dependencies that exist at compile time or link time. Notably even though main.c will execute a remote procedure call to the target function in f.c there is no compile time or link time dependency between main.c and f.c . This is because even in the absence of f.c main.c will compile perfectly and can be linked perfectly. This is because the string identifier rpc sum is treated by the compiler and linker as merely an argument value rather than a function identifier.

As shown in the system identifies a registration of a target function the registration associating the target function with a name for the target function . To identify the registration of a target function the system can identify common registration functions provided by a remote procedure call framework.

For example the system can query the database to obtain function names and their arguments. If a function name corresponds to a remote procedure call registration function the system obtain the arguments to the function. The arguments will specify the name associated with the remote procedure call as well as the target function of the remote procedure call.

The following example query in an object oriented query language identifies a registration in the XML RPC framework 

The function exists returns all entries in the database that have the specified attributes. Thus the class XMLRPCRegistration finds all functions that have attributes of XML RPC registration functions. That is functions that have a class name of registry and a method name of addMethod. 

The system identifies in a first software element an invocation of the target function using the remote procedure call . To identify the invocation of the target function using the remote procedure call the system can identify invocation functions of a remote procedure call framework. Each identified invocation with include as an argument a name associated with a registered target function.

The class XMLRPCClientCall finds all functions have the attributes of XML RPC invocation functions. That is functions that have a class name of clientSimple and a method name of call. The function getMethodString returns a string representing the registered name used by the invocation function.

The system identifies the target function of the remote procedure call in a second source code element . For some RPC frameworks any defined function is eligible to be a target of an RPC call. Thus the system can identify locations where registered target functions are defined.

In some other RPC frameworks the target functions are more explicitly defined. For example in the XML RPC framework target functions are defined in the code base by extending the xmlrpc c method class.

The system generates a new dependency between the first software element and the second software element . The system can trace the invocation of a remote procedure call to the definition of the target function by matching 1 the names used in the invocations with names used in registrations and 2 the target functions used in registrations with the definitions of those the target functions. The system can then define a new dependency between a first software element having the invocation and a second software element having the definition of the target function.

For example in the system can match 1 the name used in the invocation rpc call rpc sum to the name used in the registration rpc register rpc sum sum and 2 the target function of the registration sum to the definition of the target function in f.c . The system can then define a dependency between main.c and f.c .

This query identifies all target functions that are registered by an XML RPC registration and that are invoked with a registration string matching a registration string used in the registration.

After generating the new dependency the raw dependency graph will reflect the implicit dependencies that arise in the system due to remote procedure calls. Likewise the implicit dependencies will also be represented in the aggregated dependency graph.

This technique can also be used to identify errant RPC invocations that would not raise any compiler or linker errors. Because the string name used in the invocation is treated by the compiler and linker as a mere string argument no errors would be generated even if the associated name was wrong.

By defining queries that match names used in registrations to names used in invocations the system can execute queries to find RPC invocations that do not have any matching registrations. Similarly the system can identify RPC registrations that do not have any matching invocations. These missing registrations and invocations are highly likely to be errors in the code errors that may be difficult and costly to find otherwise through arduous debugging efforts. Thus when defining implicit dependencies introduced by RPCs the system can also generate a notification regarding missing registrations and invocations in the project.

Another category of implicit dependencies is dependencies introduced by run time configuration files. For example some graphical user interface GUI frameworks including for Android OS use configuration files that define user interface elements that should be generated as well as corresponding actions that should be taken upon a user interacting with the user interface elements. The underlying OS will then invoke the appropriate methods at runtime.

Such runtime configuration files introduce implicit dependencies between the target functions that are invoked at runtime and the main program code. However such dependencies will not be identified using only a static analysis of the structure of the source code e.g. as reflected by compile time or link time dependencies for languages that are compiled and linked.

The system receives a request to generate dependencies introduced by a runtime configuration file in a project . The request can be a user defined query designed to identify a new dependency category for implicit dependencies generated by runtime configuration files.

The system identifies a source software element that references the configuration file . The source software element will generally be a source code file that includes a call to a function that references the configuration file. For example in the GUI example the source software element can invoke a function that references the layout configuration file.

The line setContentView config.xml references the file config.xml . In an actual application the source code may actually reference the configuration file in other ways than simply naming it. For example the code can assign an integer identifier to the configuration file and the setContentView function can specify the integer identifier of the configuration file.

The following code is an example query for identifying calls to setContentView in source code as well as identifying the configuration files that are referenced in calls to setContentView. 

As shown in the system identifies one or more target function identifiers in the configuration file . The system can parse configuration files during a build process and update the database with attributes of the configuration files in a similar way that the system updates the database with attributes of source code files. The system can then query the database for attributes of the configuration files to identify target functions.

For example the configuration file config.xml specifies the behavior of clicking a button in a GUI of the Android OS using the following example XML code 

The last line of the example XML code identifies a target function testClick that is called when the button is clicked.

The system can parse this example XML file with the following example query that identifies Button nodes and their corresponding target functions.

The system identifies one or more target software elements that define the one or more target functions . For each of the target function identifiers the system can query the database to identify target software elements that include the definitions of the taret functions.

The system generates new dependencies between the first software element each of the one or more target software elements . In for example the system can generate a dependency represented by the dashed arrow from the file Main.java and Test.java that defines the testClick method.

The system adds the dependency between Main.java and Test.java even though no source code of Main.java references any elements of Test.java .

The following example query can be used to generate a new dependency between Main.java and Test.java .

One further type of implicit dependency is an implicit dependency between configuration files i.e. a configuration file to configuration file dependency. For example in the Spring framework one spring.xml file can include another. The definition of a Spring bean in one file may reference the definition of a Spring bean in another. In Maven and other build systems a Maven pom.xml file can depend on another pom.xml file.

These configuration file dependencies can tie together projects and packages in unexpected ways that are not reflected in the source code itself. Thus the system can use query based dependencies to define a new category of dependency for configuration file dependencies. These dependencies can then be aggregated into the aggregated dependency graph and displayed to a user.

Another category of implicit dependencies is dependencies introduced by reflection frameworks. Reflection frameworks are software libraries that allow a program to inspect its own contents at runtime. An implicit reflection dependency exists when a first software element uses a software element name to refer to another software element through a reflection framework. Importantly the name of the software element is resolved by the reflection framework at runtime. Thus in order to generate implicit dependencies from reflection frameworks the system can emulate the behavior of calls to some reflection functions.

The system receives a request to generate reflection dependencies in a project . For example a user can supply a user defined query for identifying reflection dependencies in a project that uses reflection functions.

The system executes a query that emulates one or more reflection functions to generate one or more target software element names . Rather than actually executing the software a static analysis system can instead emulate the behavior of the reflection functions to infer its run time behavior. The static analysis system need not emulate the behavior of the reflection functions perfectly. Rather a minimal functionality is typically sufficient in order to generate implicit dependencies.

Two example reflection functions include functions that generate all class names having a particular attribute and to generate all class names having a particular annotation. For example the following source code uses a reflections library to generate two sets 1 a first set that includes all class names that are sub types of SomeType and 2 a second set that includes all classes that are annotated with SomeAnnotation.

One example use for this functionality is a help menu for a program invoked at the command line. Instead of hard coding help menu for a particular command line program the program can instead use reflection functions to generate a list of classes having a particular annotation which represent commands that are available from the command line and their corresponding descriptions. This functionality allows developers to add new classes to the program without changing the code that generates the help menu.

The system could then execute a query that emulated the behavior of the reflection functions which would output the names of the classes having the corresponding annotation.

The system identifies a source software element that uses the output of the reflection functions . In the help menu example such reflection functions above might be used to generate the help menu as follows 

The system generates a new dependency between the source software element and each of the one or more target software elements . In this example the software element that included the enumeration of the help menu functions would have a dependency on each software element that included one of the enumerated classes.

Another category of implicit dependencies arises from callback registration. A callback registration involves a function pointer being passed to another module. At certain points in the execution of the module the module will call the callback function.

A callback registration is an implicit dependency because the module using the callback function may not have at compile time or link time any statements that reference anything in the software element that defines the callback.

The system receives a request to generate callback registration dependencies in a project . For example a user can supply a user defined query for identifying callback registration dependencies in a project that uses callback registrations.

The system identifies a callback registration for a source software element and a callback function referenced by the registration . For example the user specified query can be customized to find callback registrations in a particular callback framework.

The file main.c includes a link time dependency on f.c . However at neither compile time nor link time are there any dependencies between audio.c and f.c .

The system identifies a target software element that defines the callback function . In for example the file f.c defines the callback function.

The system generates a new dependency between the source software element that invokes the callback function and the target software element that defines the callback function . In for example the system can generate a dependency between the file audio.c and the file f.c .

Another category of implicit dependencies arises from dependency injection. A dependency injection framework is a software tool that allows a developer to specify relationships between classes and instances of the classes. This allows the class definitions to remain generic by not explicitly depending on other class definitions in the source code. For example an instance of a first class can be injected into a constructor or into a setter method of another class by using a configuration file. The source code itself shows no dependency between the two classes.

The system receives a request to generate injection dependencies in a project . For example the system can receive a user defined query that identifies injected dependencies for a particular programming language or a particular project.

The system identifies a configuration file of a dependency injection framework that specifies an instance of a first class that is injected as a member into an instance of the second class . Because the dependency injection framework uses the configuration file to instantiate the classes the actual source code of the project does not reference an instance of a first class being used by a second class. Although this example makes specific reference to a configuration file the same techniques can be applied to dependency injection frameworks that use source code annotations rather than configuration files.

The following example configuration file of the Spring dependency injection framework defines a first class RadioMessenger that is injected into a second class WeatherStation using the constructor of the second class.

The WeatherStation class is instantiated by referencing the configuration file. For example the following example source code identifies the configuration file services.xml and uses the information in services.xml to instantiate a WeatherStation object 

In this example the definition of the WeatherStation class makes reference only to a generic Messenger interface both of which are defined in the following example source code 

The RadioMessenger class specified in the configuration file extends the generic interface Messenger class for example using the following source code 

However no compile time or link time dependencies exist between Weather.java and RadioMesssenger.java because the code of Weather.java does not make any reference to any software elements in RadioMessenger.java .

As shown in the system identifies a source software element that defines the first class to be injected . In this example the file RadioMessenger.java defines the first class to be injected.

The system identifies a target software element that defines the second class into which the first class is injected . In this example the file weather.java defines a class into which the RadioMessenger instance is injected.

The system generates a new dependency from the source software element to the target software element . As shown in the system generates an implicit dependency between the file weather.java and the file RadioMessenger.java.

This example query returns a constructor and a type. In other words the query identifies a type an instance of which will be injected into the given constructor. In other words the query identifies a constructor that is used to construct a Spring bean. For that constructor the query identifies which arguments are defined in the Spring configuration file and follows the links to determine what type that argument has. In the example the constructor argument is given as a reference to the bean with id messenger. Looking for the definition of the bean with id messenger we see it is of type RadioMessenger so we can deduce that the argument of the WeatherStation constructor is an instance of RadioMessenger.

Embodiments of the subject matter and the functional operations described in this specification can be implemented in digital electronic circuitry in tangibly embodied computer software or firmware in computer hardware including the structures disclosed in this specification and their structural equivalents or in combinations of one or more of them. Embodiments of the subject matter described in this specification can be implemented as one or more computer programs i.e. one or more modules of computer program instructions encoded on a tangible non transitory program carrier for execution by or to control the operation of data processing apparatus. Alternatively or in addition the program instructions can be encoded on an artificially generated propagated signal e.g. a machine generated electrical optical or electromagnetic signal that is generated to encode information for transmission to suitable receiver apparatus for execution by a data processing apparatus. The computer storage medium can be a machine readable storage device a machine readable storage substrate a random or serial access memory device or a combination of one or more of them. The computer storage medium is not however a propagated signal.

The term data processing apparatus encompasses all kinds of apparatus devices and machines for processing data including by way of example a programmable processor a computer or multiple processors or computers. The apparatus can include special purpose logic circuitry e.g. an FPGA field programmable gate array or an ASIC application specific integrated circuit . The apparatus can also include in addition to hardware code that creates an execution environment for the computer program in question e.g. code that constitutes processor firmware a protocol stack a database management system an operating system or a combination of one or more of them.

A computer program which may also be referred to or described as a program software a software application a module a software module a script or code can be written in any form of programming language including compiled or interpreted languages or declarative or procedural languages and it can be deployed in any form including as a stand alone program or as a module component subroutine or other unit suitable for use in a computing environment. A computer program may but need not correspond to a file in a file system. A program can be stored in a portion of a file that holds other programs or data e.g. one or more scripts stored in a markup language document in a single file dedicated to the program in question or in multiple coordinated files e.g. files that store one or more modules sub programs or portions of code. A computer program can be deployed to be executed on one computer or on multiple computers that are located at one site or distributed across multiple sites and interconnected by a communication network.

As used in this specification an engine or software engine refers to a software implemented input output system that provides an output that is different from the input. An engine can be an encoded block of functionality such as a library a platform a software development kit SDK or an object. Each engine can be implemented on any appropriate type of computing device e.g. servers mobile phones tablet computers notebook computers music players e book readers laptop or desktop computers PDAs smart phones or other stationary or portable devices that includes one or more processors and computer readable media. Additionally two or more of the engines may be implemented on the same computing device or on different computing devices.

The processes and logic flows described in this specification can be performed by one or more programmable computers executing one or more computer programs to perform functions by operating on input data and generating output. The processes and logic flows can also be performed by and apparatus can also be implemented as special purpose logic circuitry e.g. an FPGA field programmable gate array or an ASIC application specific integrated circuit .

Computers suitable for the execution of a computer program include by way of example can be based on general or special purpose microprocessors or both or any other kind of central processing unit. Generally a central processing unit will receive instructions and data from a read only memory or a random access memory or both. The essential elements of a computer are a central processing unit for performing or executing instructions and one or more memory devices for storing instructions and data. Generally a computer will also include or be operatively coupled to receive data from or transfer data to or both one or more mass storage devices for storing data e.g. magnetic magneto optical disks or optical disks. However a computer need not have such devices. Moreover a computer can be embedded in another device e.g. a mobile telephone a personal digital assistant PDA a mobile audio or video player a game console a Global Positioning System GPS receiver or a portable storage device e.g. a universal serial bus USB flash drive to name just a few.

Computer readable media suitable for storing computer program instructions and data include all forms of non volatile memory media and memory devices including by way of example semiconductor memory devices e.g. EPROM EEPROM and flash memory devices magnetic disks e.g. internal hard disks or removable disks magneto optical disks and CD ROM and DVD ROM disks. The processor and the memory can be supplemented by or incorporated in special purpose logic circuitry.

To provide for interaction with a user embodiments of the subject matter described in this specification can be implemented on a computer having a display device e.g. a CRT cathode ray tube monitor an LCD liquid crystal display monitor or an OLED display for displaying information to the user as well as input devices for providing input to the computer e.g. a keyboard a mouse or a presence sensitive display or other surface. Other kinds of devices can be used to provide for interaction with a user as well for example feedback provided to the user can be any form of sensory feedback e.g. visual feedback auditory feedback or tactile feedback and input from the user can be received in any form including acoustic speech or tactile input. In addition a computer can interact with a user by sending resources to and receiving resources from a device that is used by the user for example by sending web pages to a web browser on a user s client device in response to requests received from the web browser.

Embodiments of the subject matter described in this specification can be implemented in a computing system that includes a back end component e.g. as a data server or that includes a middleware component e.g. an application server or that includes a front end component e.g. a client computer having a graphical user interface or a Web browser through which a user can interact with an implementation of the subject matter described in this specification or any combination of one or more such back end middleware or front end components. The components of the system can be interconnected by any form or medium of digital data communication e.g. a communication network. Examples of communication networks include a local area network LAN and a wide area network WAN e.g. the Internet.

The computing system can include clients and servers. A client and server are generally remote from each other and typically interact through a communication network. The relationship of client and server arises by virtue of computer programs running on the respective computers and having a client server relationship to each other.

While this specification contains many specific implementation details these should not be construed as limitations on the scope of any invention or of what may be claimed but rather as descriptions of features that may be specific to particular embodiments of particular inventions. Certain features that are described in this specification in the context of separate embodiments can also be implemented in combination in a single embodiment. Conversely various features that are described in the context of a single embodiment can also be implemented in multiple embodiments separately or in any suitable subcombination. Moreover although features may be described above as acting in certain combinations and even initially claimed as such one or more features from a claimed combination can in some cases be excised from the combination and the claimed combination may be directed to a subcombination or variation of a subcombination.

Similarly while operations are depicted in the drawings in a particular order this should not be understood as requiring that such operations be performed in the particular order shown or in sequential order or that all illustrated operations be performed to achieve desirable results. In certain circumstances multitasking and parallel processing may be advantageous. Moreover the separation of various system modules and components in the embodiments described above should not be understood as requiring such separation in all embodiments and it should be understood that the described program components and systems can generally be integrated together in a single software product or packaged into multiple software products.

Particular embodiments of the subject matter have been described. Other embodiments are within the scope of the following claims. For example the actions recited in the claims can be performed in a different order and still achieve desirable results. As one example the processes depicted in the accompanying figures do not necessarily require the particular order shown or sequential order to achieve desirable results. In certain implementations multitasking and parallel processing may be advantageous.


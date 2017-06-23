---

title: Hierarchical dependency analysis enhancements using disjoint-or trees
abstract: Methods, systems, and apparatus, including computer programs encoded on computer storage media, for performing hierarchical dependency analysis using disjoint-or trees. One of the methods includes receiving, from a user, a request to remove a node from a hierarchy, wherein the hierarchy is a directed graph having nodes and links, wherein each node in the hierarchy represents a software element in the project and each directed link in the hierarchy connects a corresponding pair of nodes and represents containment of a child software element represented by a first node of the pair by a parent software element represented by a second node of the pair. If a parent element of a disjoint-or tree corresponds to a parent node of the removed node, a union of dependencies for the removed node is determined. The union of dependencies is then subtracted from the parent element and from every ancestor element of the parent element.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09547478&OS=09547478&RS=09547478
owner: Semmle Limited
number: 09547478
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

The int g node depends on an int b node that represents the function int b called from the function int g . Similarly The int b node depends on an int go node that represents the function int g called from the function int b . 

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

The interactive nature of the visualizations generated by the system requires that the system be able to compute relationships between software elements and their respective dependencies in real time or near real time. To do so the system can use techniques that i allow many sets of dependencies to be represented in main memory ii provide for fast computation of operations between arbitrary sets of dependencies and iii allow the result of a binary composition e.g. conjunction disjunction implication to be computed and accessed randomly without ever representing the result in memory.

The system can arrange identifiers of software elements in a project so that software elements that are near each other in the hierarchy are likely to have identifiers that are close to each other. Thus subtrees of software elements are likely to have identifiers that are contiguous in a range of identifiers.

The system can then use a data structure called a tiered array to exploit the ranges of contiguous identifiers. Each identifier that uniquely identifies a dependency corresponds to one of N indexes where N is the number of dependencies. Thus in the description that follows an index refers both to a position represented in a tiered array as well as a unique identifier for a particular dependency.

This allows the system to efficiently compute operations involving dependency sets represented as tiered arrays e.g. conjunctions disjunction inverses implications e.g. A implies B which is logically equivalent to B or not A and a without operation e.g. A without B which is equivalent to A and not B .

A tiered array has unallocated portions that represent ranges of indexes defined to have a default value. Thus a tiered array can represent the same data as a simple array in a manner that is almost always more efficient in terms of space at a negligible reduction in speed of access. In other words the default values are not explicitly represented in the tiered array. Rather the tiered array allocates catalogs that are sufficient to represent elements that are associated with non default values. The worst case for a tiered array arises when there is a value associated with at least one index in every possible catalogue so that every tier must be instantiated. In this case the tiered array incurs slightly worse space efficiency but the actual occurrences in practice of the worst case in terms of both speed and space efficiency are generally negligible.

The default value of a tiered array can be defined arbitrarily and the choice depends on the data type being represented. The default value of a non bottom level catalog is a null pointer. If the tiered array represents an array of bits the default value for bottom level catalogs is usually 0 although 1 could also be used. If the tiered array represents an array of strings the default value is the null string. For other numeric types the default is zero. The choice of default value is normally that which is consistent with the notion of an empty array i.e. the state of the array when first created and before any associations have been stored in it. For brevity an index having a non default value can be referred to as the index being set or equivalently being a set index. An index having the default value can be referred to as the index being not set or equivalently being an unset index. 

The tiered array has a top level catalog . Each element of the top level catalog has either a default value e.g. a null pointer or a reference to a catalog on a lower level. For brevity the action of following a reference from a catalog on one level to a catalog on a lower level will be referred to as descending a level in the tiered array. Similarly moving from a catalog on a lower level to a catalog on a higher level will be referred to as ascending a level. The sense of direction is arbitrary. However in this specification descending will refer to moving closer to the bottom level catalogs storing values.

In the third element of the top level catalog is the first element of the top level catalog that is set e.g. associated with a non default value. The third element references a catalog on a lower level of the tiered array . The catalog has two elements set that respectively reference catalogs and on lower levels of the tiered array .

The bottom level catalogs of a tiered array can store any appropriate data type. For example the bottom level catalogs can store signed or unsigned unsigned integers long integers or individual bits. When the bottom level catalogs store individual bits each bottom level catalog itself can be represented as an integer type. In some implementations the system stores bottom level catalogs as unsigned longs having 64 bits each.

The structure of the tiered array allows the system to store values over an arbitrary range of indexes that is arbitrarily large. For example a tiered array can store values over a range of indexes represented by 64 bit longs. In addition the range of indexes can include negative indexes. For example a tiered array can have indexes that are signed integers and thus the tiered array store values that are associated with indexes from 2 31 to 2 31 1.

In the example of each bottom level catalog stores just 4 bits. The bottom level catalog has its last two bits set. Thus it can be represented by an integer type having the hexadecimal value 0x3.

A system can implement a number of optimizations by maintaining some metadata for each catalog of a tiered array. In particular the system can maintain for each catalog a value of the first set index in the catalog a value of the last set index in the catalog and a value representing the number of set indexes in the catalog.

The system can deallocate catalogs that represent fully set ranges of indexes. For example if the bottom level catalog has every bit set the system can deallocate the bottom level catalog . The system can then replace the reference in the catalog with a special reserved value in this example x to indicate that the catalog was fully set and therefore deallocated. In the dashed lines represent that the bottom level catalog is not actually allocated in the tiered array .

The system can also represent fully set but unallocated catalogs using metadata associated with the catalogs. For example the reserved value x can actually be the default value e.g. null when used in association with the metadata. Thus if a value in a catalog is a default value e.g. null but is associated with a bottom level having metadata that indicates that the bottom level catalog is full the system can determine that the bottom level catalog is a fully set but unallocated catalog. In other words the system can use the default value e.g. null to represent catalogs that are fully set if the metadata indicates they are fully set or fully empty otherwise.

The deallocated catalogs representing fully set ranges of indexes can also occur at higher tiers of the tiered array . For example the catalog includes a reference indicating that all catalogs on lower levels would have been fully set. In this example the reference represents 16 set bits.

The system can maintain the catalogs by allocating a new catalog whenever a fully deallocated catalog has one of its elements set by deallocating a catalog whenever a fully allocated catalog has one of its elements removed and by reallocating a catalog whenever an element in a fully allocated catalog is removed. The system can reduce the time required for allocating catalogs by maintaining a pool of fully allocated catalogs and fully deallocated catalogs. Then if a new fully allocated catalog is required the system can use one of the already allocated catalogs from the pool of fully allocated catalogs. Similarly whenever a new partially allocated catalog is needed the system can use one of the fully deallocated catalogs. That is when the only unset index in a catalogue is set or the only set index in a catalogue is unset the reference to that catalogue can be removed from the tiered array but added to the pool. Conversely when an index in a fully set catalogue is unset or vice versa a catalogue in the pool of fully set or fully unset catalogues can be reused. It is more efficient to use a catalogue from the appropriate pool but if that pool is empty while the other pool is not it is generally still preferable to reuse a catalogue from the other pool because doing so still functions to reduce the frequency at which chunks of memory are allocated and deallocated on the heap and hence reduces memory fragmentation even though it is necessary to invert every value in such a catalogue before reusing it.

The system receives data representing a hierarchy of software elements . As described above the system can maintain a hierarchy graph representing hierarchical relationships which typically represents a containment relationship between software elements. For example illustrates one such hierarchy graph.

The system receives data representing dependencies between the software elements in the hierarchy . As described above the data can represent a raw dependency graph between software elements in the project. Each dependency identifies a source software element and a target software element.

The system numbers the software elements according to a depth first traversal of the hierarchy . For example the system can assign an ID of 1 to the root node 2 to the root node s first child 3 to the first child s first child. Typically the ID 0 is not used rather 0 or null is reserved for use as an indication of the absence of a node or dependency.

The system numbers dependencies in the project in an order determined by source software element IDs first and target software element IDs second . That is all dependencies having a same particular node as a source software element will be numbered consecutively. And the order among the dependencies from the particular node will be determined by the IDs of the target software elements of the dependencies. For the sake of clarity the resulting association of IDs with dependencies is consistent with the following algorithm Let S X indicate the ID of the software element that is the source of a dependency X and T X the ID of its target. Create a list containing all of the dependencies. Sort this list such that dependency A is before dependency B if S A 

This technique causes outgoing dependencies for each software element to be stored contiguously in the tiered arrays for those software elements. This property can be exploited to more efficiently perform operations involving the dependencies between software elements.

The number n of dependencies represents the range of indexes that will be represented by tiered arrays. A tiered array is used to represent the IDs of the dependencies inbound to a particular software element node and typically also the IDs of the dependencies inbound to any software element nodes that are descended from it in the hierarchy. A tiered array is likewise used to represent the IDs of the dependencies outbound from a particular software element node and typically also those of its descendants .

The system receives a start index . The system will use the start index to find a first value in the tiered array that is set at an index that is greater than or equal to the start index. In other words indexes less than the start index are disregarded. The start index can specify an arbitrary position in the tiered array and as described above the start index can be negative if the tiered array has negative indexes.

The start index can be specified by a number of different operations. For example to identify all set values in a tiered array the system can first provide a start index equal to a minimum start index to find a range a b of contiguous set indexes where a is equal to or greater than the start index. The system can then repeat the process by providing a start index of b 1 and continue doing so until the are no remaining indexes that are set as a means to rapidly determine and provide a representation of all set indexes which can be used to iterate the indexes individually or simply to count them Other start indexes can also be specified while computing other operations on the tiered array e.g. while computing disjunctions or conjunctions of tiered arrays as described in more detail below with reference to .

The system converts the start index into initial subindexes . The number of subindexes depends on the number of tiers in the tiered array. For example the tiered array shown in has four tiers but the fourth is implemented by storing integer types. Thus the system can convert a starting index into three subindexes that each reference a position in a corresponding catalog.

The system can store in each tier 2 x 2 y and 2 z values respectively. For example if the indexes are 4 byte integers x can be the most significant 10 bits y can be next most significant 10 bits and z can be the least significant 12 bits. Thus the system can obtain the subindexes by bit shifting and masking operations applied to the full index. In other words to obtain x the system can shift the bits right by 22 bits and mask off all but the bottom 10 bits in the result.

As the system iterates through the catalogs the system can update the subindexes. For example when iterating through a catalog the system will increment a subindex for the catalog on each iteration.

If the end of a catalog is reached the system can ascend from a lower tier to an upper tier. In that case the subindex for the lower tier can be reset to zero while the subindex for the upper tier can be incremented by one.

If the system descends a tier by following a reference from an upper tier to a lower tier the subindex for the lower tier can be reset to zero unless the system is following a reference specified by the very first subindexes generated from a start index. In other words when obtaining a value for the start index only descending to lower tiers does not reset the subindex to zero for those lower tiers. In all other cases of descending to lower tiers the subindex is reset to zero.

The system starts at the subindex of the top level catalog . The system will then iterate through catalogs on lower levels to find a first value that is set at an index that is greater than or equal to the start index.

The system iterates through a catalog at a current level to find the first set value in the catalog . The catalog at the current level is initially the top level catalog. Descending a level changes the current level to a catalog on a lower level and ascending a level changes the current level to a catalog on an upper level.

Upon finding a first set value the system determines whether the set value is a bottom level value . If the set value is not a bottom level value the set value is a reference to a catalog on a lower level. Thus the system descends one level and iterates through the catalog on the lower level branch to .

If the set value is a bottom level value the system designates the first set index as the start of the range . The system then computes the start of the range by using the subindexes to compute an overall index corresponding to the bottom level value. To do so the system can perform the inverse of the process in step . That is the system can left shift the current subindex for the top level by x bits left shift the current subindex for the middle level by y bits and compute a bitwise OR of those with the last z bits. If as in the tiered array stores a fourth level as integer types the system can additionally add the value in the last catalog to the result.

In some cases the bottom level catalog is not actually allocated. For example the bottom level catalog in is not actually allocated. However the system can still designate the first set index of the range as the first index represented by the bottom level catalog.

After finding the first set index at the start of the range the system switches over to finding the next unset value after the start of the range . The next unset value represents the end of the range of contiguous set values. The end of the range is thus the index before the next unset value.

In general finding the first set value in the range only involves descending levels in the tiered array. However finding the next set value can involve ascending to upper levels in the tiered array and possibly descending once again to lower levels in the tiered array.

The system iterates through the bottom level catalog and determines whether the bottom level catalog has an unset value . If so the system designates the last set index in the bottom level catalog as the end of the range and the process ends. If not the system ascends one level .

If the bottom level catalog is not actually allocated because it is fully set the system need not iterate through the bottom level catalog and can instead immediately determine that the bottom level catalog does not have an unset value and ascend one level branch to .

The system iterates through the catalog at the current level to find next unset value . If the next value on an iteration through the catalog at the current level is not set this means that the last bottom level index is the last set value in the range. Thus the system designates the last bottom level index as the last set value in the range and the process ends.

If the next value on an iteration through the catalog at the current level is set the system descends one level branch to . If the current level is the bottom level the system iterates through the bottom level to find the next unset value branch to . If the current level is not the bottom level the system iterates through the catalog of the current level again branch to .

The process in can be illustrated with reference to . In the system will follow references to lower level catalogs in the order determined by the letters a through f. Assume for this example that the start index is 0.

Thus the system begins iterating through the top level catalog starting from the first index of the top level catalog . The first set value is designated by the reference a to the lower level catalog .

The system then iterates through the lower level catalog identified by a until it reaches the first set value designated by the reference b to the lower level catalog .

The system then iterates through the lower level catalog until it reaches the first set value designated by the reference c to the bottom level catalog .

The system then iterates through the bottom level catalog until it reaches the first set value at the third position in the catalog. Because the first set value is in the bottom level catalog the system designates the index at that position as the first set value in the range.

In this case the first index of the range is computed by computing the position of the first set value e.g. 0x2 in base 0 plus the position of the first set value in the catalog shifted by the number of bits in the bottom level catalogs plus the position of the first set value in the catalog shifted by i the number of bits in the bottom level catalogs and ii the number of positions in the catalog plus the position of the first set value in the top level catalog shifted by i the number of bits in the bottom level catalogs ii the number of positions in the catalog and iii the number of positions in the catalog .

The system then switches over to finding the next unset value by iterating through the bottom level catalog . The system reaches the end of the catalog without finding an unset value so the system ascends a level to the catalog .

The next value is set so the system could then descend a level to the bottom level catalog . However because the next value indicates that the bottom level catalog is fully set the system can skip iterating over the bottom level catalog and continue iterating over the catalog .

The value is the last value in the catalog so the system ascends one level to iterate through the catalog . The next value d is set so the system descends one level to iterate through the catalog . The next value e is set so the system iterates through the bottom level catalog until determining that the last position in the bottom level catalog is not set.

At this point the system designates the immediately preceding index as the last index set in the range. The system can compute the last index in the range in a similar way to the first index in the range and thus the last index in the range is 178.

The system can then return the range 170 178 in response to the requesting process. If the requesting process is a process that finds all such ranges in the tiered array the system would next receive a request for the next range starting at index .

The system would then iterate through the top level catalog to the value f and descend one level to the catalog . The first value that is set is at the third position. Because the value indicates that the lower levels are not allocated because they are fully set the system can designate the index represented by the fully set lower tiers as the first value in the range. In this example the first index is 416. The system also need not iterate through the unallocated lower tiers. Thus the system next determines that the next value is not set. The system thus designates the last value represented by the fully set lower tiers as the last value in the range which is 431.

The process described above with reference to can be improved with a number of optimizations. In particular the system can maintain metadata about each catalog in the tiered array that stores a number of set indexes in each catalog the first index that is set in the catalog and the last index that is set in the catalog. The metadata can also maintain information about the tiered array as a whole e.g. the number of set indexes in the tiered array the first index that is set in the tiered array and the last index that is set in the tiered array.

Furthermore the system need not serially perform the steps for finding the first set index and then the last set index. Rather the system can compute either the first or last set index independently which means that the system can compute them in any order or concurrently. Lastly the system can also seek to curtail computation of first set index and the last set index under a number of conditions.

These enhancements are described below with reference to . In these examples a tiered array having three tiers is assumed. However the same techniques can be applied to tiered arrays having an arbitrary number of tiers.

The system receives a request to find a first set index starting at or after a start index i . As described above the system can search a tiered array for a contiguous range of set values that start at or after i.

The system determines whether the tiered array is empty . If so the system returns no result branch to .

If the tiered array is not empty the system determines whether i is after the last set index in the tiered array . For example the system need only to refer to the maintained metadata information for the tiered array which records the last set index in the tiered array.

If not the system determines whether i is at or before the first used index branch to . Again the system can merely refer to the metadata information maintained for the tiered array and need not search the tiered array to determine whether i is before the first used index. If it is the system simply returns the first used index branch to .

Otherwise the system determines whether the tiered array contains a value at index i branch to . The system can determine this in constant time by converting i into three subindexes and using the subindexes to identify a position in a bottom level catalog of the tiered array. If that position has a set value the system returns the index i branch to .

Otherwise the system will search for the first set index after i in the tiered array . For example the system can proceed with the example process described above with respect to or proceed with the example process described below with respect to .

The system receives a start index i and converts the start index into three subindexes i0 i1 and i2 . i0 identifies a position in the top level catalog i1 identifies a position in a mid level catalog and i2 identifies a position in a bottom level catalog.

The goal of the example process is an index j that identifies the first set index after i. The index j can be generated by its subindexes j0 j1 and j2.

The system determines whether the mid level catalog identified by i0 exists . If not the system performs a linear search for the first catalog that exists in the range i0 L0 wherein L0 is metadata that identifies the last mid level catalog that exists.

The system finds the index j1 of the first bottom level catalog in the mid level catalog j0 . Because the system maintains metadata indicating the first and last set values in each catalog the system can perform this step in constant time.

The system finds the index j2 of the first value in the bottom level catalog at j0 j1 . The system can also perform this step in constant time using metadata.

If the mid level catalog i0 exists the system determines whether the bottom level catalog at i0 i1 exists .

If not the system performs a linear search for the first existing bottom level catalog with index j1 in max i1 F1 i0 L1 i0 in mid level catalog i0 branch to . The functions F1 i0 and L1 i0 respectively return the indexes of the first and last bottom level catalogs having values that are referenced in the mid level catalog i0.

The system determines whether a bottom level catalog was found . If not the system performs a linear search for the first existing mid level catalog with index j0 in i0 1 L0 where L0 is the index of the last mid level catalog having values branch to . The system then finds the index j1 of the first bottom level catalog in the mid level catalog j0 .

If the system did not find a bottom level catalog the system sets j0 i0 and finds the index j1 of the first bottom level catalog in the mid level catalog j0 branch to .

If the bottom level catalog i0 i1 existed the system performs a linear search for the first value in the bottom level catalog i0 i1 with index j2 in max i2 F2 i0 i1 L2 i0 i1 branch to . The functions F2 and L2 respectively return the indexes of the first and last values in the bottom level catalog at i0 i1.

The system determines whether a value was found . If not the system performs a linear search for the first existing bottom level catalog with index j1 in max i1 F1 i0 L1 i0 in mid level catalog i0 branch to .

The system receives a request to find the last set index in a contiguous range starting at or after the start index i . The system can perform the example process in without actually having the start index of the range. Thus the system could perform the example processes in in parallel.

The system determines whether the bottom level catalog i0 i1 is full . The system can determine whether the bottom catalog is full by referring to metadata that maintains a number of set indexes in each catalog. If the bottom level catalog is full the system determines whether i1 is the maximum possible index of a bottom level catalog branch to .

If so the system increments i1 and sets i0 to 0 branch to . In other words the system moves to the start of the next bottom level catalog. The system then again determines if the bottom level catalog at i0 i1 is full .

If i1 is the maximum possible index of a bottom level catalog the system determines whether i0 is the maximum possible index of a mid level catalog . If not the system increments i0 and sets i1 and i2 to 0 branch to . In other words the system moves to the start of the next mid level catalog. The system then again determines if the bottom level catalog at i0 i1 is full .

If i0 is the maximum possible index of a mid level catalog the system returns the maximum possible index branch to . In other words if the system reaches the end of the last mid level catalog and the last bottom level catalog is full the system can simply return the maximum possible index.

If the bottom level catalog i0 i1 was not full the system determines if the last index is set in the bottom level catalog i0 i1 branch to . If so the system determines if the bottom level catalog is trivially full from i2 to the end . The system can use metadata to determine this if the first set value is the minimum for the catalog the last set value if the maximum for the catalog and the number of set values is equal to the size of the catalog.

If the bottom level catalog is trivially full the system again determines if i1 is the maximum possible index of a bottom level catalog branch to .

Otherwise the system performs a linear search for the first unset index j2 i2 in the bottom level catalog . The system then determines whether such a j2 was found . If not the system has to effectively ascend a level and the system determines whether i1 is the maximum possible index of a bottom level catalog branch to .

If the system did find j2 the system generates the index j from i0 i1 and i2 and returns the value j 1.

To improve computational performance instead of operating only on individual elements a system can iteratively operate on ranges of contiguously set indexes. In the following description accompanying and reference will be made to a function FindNextRange X n which finds a contiguous range of set indexes in array X from a particular start index n. The function FindNextRange can be implemented for example as the process described above with reference to or .

The structure of the tiered arrays and the deliberate arrangement of dependencies in contiguous ranges allows a system to efficiently compute operations over tiered arrays. The examples below will thus reference using tiered arrays to perform the operations. However the procedures described below can also be performed on any appropriate data structure over which ranges of contiguously set indexes can be computed. In other words a tiered array is not required to perform the range based operations described in .

In particular the system can compute virtual bitwise compositions between tiered arrays e.g. disjunctions conjunctions and inverses. A composition is a bitwise operation over indexes having non default values. In this context virtual indicates that neither a simple nor a tiered array is generated that represents the bitwise composition. Rather the system is able to output a set of indexes that represents the bitwise composition without generating an array that represents the bitwise composition.

The set of indexes can be represented by one or more pairs of indexes representing contiguously set ranges of indexes. In other words each pair has a start index and an end index that respectively identify the start and end of a contiguous range of indexes having non default values. In the examples below outputting indexes generally means outputting a start index and an end index representing a range of contiguously set indexes. However a system can also individually output all indexes in the range.

The system receives a request to obtain all ranges of indexes having non default values in an array A . As described above the array A can be a tiered array but need not be.

The system sets a b to the result of FindNextRange A 0 and outputs the range a b . In other words the system finds the first index in the tiered array having a non default value. To find this index the system provides to the FindNextRange function a start index equal to a minimum start index e.g. 0.

The system determines whether the end of the array has been reached . If not the system obtains the next range by setting a b to the result of FindNextRange A b 2 and outputs the range a b . In other words the system uses b the end of the previously obtained range of set indexes to find the next contiguously set range of indexes. It is known that b 1 is not set thus the system provides b 2 as a start index to the FindNextRange procedure.

The system again determines whether the end of the array has been reached . If so the process ends branch to end . Otherwise the system continues outputting ranges of contiguously set indexes branch to .

The system receives a request to obtain all ranges of indexes having default values in an array A . The array A can be a tiered array but need not be.

The system sets a0 b0 to the result of FindNextRange A 0 . In other words the system finds the first index in the tiered array having a non default value. To find this index the system provides to the FindNextRange function a start index equal to a minimum start index e.g. 0.

The system determines whether a0 0 . If a0 which represents the first set index in the array is not the first index in the array the system will output all indexes having the default value up to but not including a0. Thus the system outputs 0 a0 1 .

The system determines whether the end of the array has been reached . If not the system finds the next range by setting a1 b1 to FindNextRange A b0 2 branch to . After finding the next range of contiguously set indexes the system can output the space between the previous range of contiguously set indexes and the current range of contiguously set indexes.

Thus the system outputs b0 1 a1 1 and updates a0 and b0 . The system updates a0 and b0 to represent the current range of contiguously set indexes.

Thus the system outputs b1 1 max index branch to . Otherwise if b1 max index the process ends branch to end .

The system receives a request to compute a virtual disjunction between two tiered arrays A and B . The system can compute a disjunction between two tiered arrays for a variety of purposes. For example the system can compute a set of dependencies outbound from a source element A or any descendant of A by computing a disjunction between tiered arrays representing outbound dependencies for A and each of its descendants.

The system gets the next ranges for A and B with a start index of 0 . In other words the system computes the respective first ranges of contiguously set values for both A and B. The system can use the example process described above with reference to or providing as input to the process a starting index value of 0. The resulting range for A will be represented by a first index a0 at the start of the range of contiguously set values and a second index a1 at the end of the range. The resulting range for B will be represented similarly by b0 and b1.

The system determines whether A or B have no remaining indexes with set values . In other words if the range finding process returns no results for either A or B the system can determine that one of the tiered arrays has no remaining indexes with set values.

If so the system iterates to the end of the other tiered array outputting all ranges of indexes with set values branch to . For example if B has no more indexes with set values the system can simply output the remaining indexes in A. That is because the virtual disjunction is a bitwise OR the system need not inspect any more elements in B. The system need not actually output every set index but can rather output a representation of ranges that each represent a sequence of contiguously set indexes.

Instead the system simply outputs ranges of any remaining indexes in A. To do so for A for example the system can repeatedly call FindNextRange A a1 2 to obtain the next range a0 a1 using each updated a1 2 as the next starting index. In other words the system need not actually output each set index. Rather the system can output the start and end of contiguous ranges of set indexes.

Because the system outputs maximal contiguous ranges the index a1 1 is known to be not associated with a non default value in A .

If both tiered arrays have remaining indexes the system computes the minimum between a0 and b0 branch to . For clarity in the rest of the description of the example process it will be assumed that a0 was less than b0. However the same techniques apply conversely if b0 is less than a0.

The system sets a0 as the start of a next range of contiguously set indexes in the disjunction . Because a0 a1 represents a contiguous range of set indexes the result will include at least a0 a1 .

The system thus compares the range generated by FindNextRange A a1 2 to b0 b1 . The process then returns to step to determine whether the end of A or B has been reached.

The system then compares the ranges FindNextRange A b1 2 and b0 b1 and the process returns to step to determine whether the end of A or B has been reached.

For each array X the system computes FindNextRange X 0 . In other words the system finds the first range of contiguously set indexes for each array.

The system determines whether the end of any of the arrays has been reached . If so the array will not contribute anything else to the result so the system removes each array from the computation whose end has been reached .

If so the system determines the minimum first index n0 of the identified ranges . The minimum first index is the start of a range n0 n1 of contiguously set indexes in one of the tiered arrays.

The virtual disjunction will include at least n0 n1 and the system will determine whether any of the other arrays can extend this range.

The system determines whether any other array extends the current range starting at n0 . In other words the system iterates over the other current ranges found for the other arrays to determine whether the arrays overlap and extend the range.

If so the system updates n1 using the range from the array that extends the current range branch to . The system then repeatedly determines whether the range can be extended with any of the other ranges .

When the range can no longer be extended by any of the current ranges the system outputs the range n0 n1 .

The system then again removes arrays whose end has been reached and and determines whether any arrays remain . If not the process ends branch to end .

The system receives a request to compute a virtual conjunction between two tiered arrays A and B . The system can compute a conjunction between two tiered arrays for a variety of purposes. For example the system can compute aggregated dependencies between two software element nodes by computing an intersection between two sets of dependencies as described above with reference to .

The system gets the next ranges for A and B with a start index of 0 . In other words the system computes the respective first ranges of contiguously set values for both A and B. The system can use the example process described above with reference to or providing as input to the process a starting index value of 0. The resulting range for A will be represented by a first index a0 at the start of the range of contiguously set values and a second index a1 at the end of the range. The resulting range for B will be represented similarly by b0 and b1.

The system determines whether A or B have no remaining indexes with set values . In other words if the range finding process returns no results for either A or B the system can determine that one of the tiered arrays have no remaining indexes with set values. If so the process ends because there can be no further indices in the conjunction branch to end .

If both A and B have remaining indexes the system computes the minimum between a0 and b0 branch to . For clarity in the rest of the description of the example process it will be assumed that a0 was less than b0. However the same techniques apply conversely if b0 is less than a0.

Thus the system next compares ranges FindNextRange A b0 and b0 b1 and the process returns to step to determine whether the end of A or B has been reached.

The next range in B could still overlap part of a0 a1 so the system next compares ranges a0 a1 and FindNextRange B b1 2 and the process returns to step to determine whether the end of A or B has been reached.

The next range in A could still overlap part of b0 b1 so the system next compares ranges FindNextRange A a1 2 and b0 b1 and the process returns to step to determine whether the end of A or B has been reached.

Iterating over ranges of contiguously set indexes also provides opportunities for efficient counting of set values in the arrays since the total number of indices with which a non default value is associated can be found by iterating over the contiguous ranges in the result and accumulating the sum of their lengths. This applies equally to the counting of indices in the result of a composition.

For each array X the system computes FindNextRange X 0 . In other words the system finds the first range of contiguously set indexes for each array.

The system determines whether the end of any of the arrays has been reached . If so the conjunction cannot have any additional ranges so the process ends branch to end .

Otherwise the system determines the minimum first index n0 of the identified ranges . The minimum first index is the start of a range n0 n1 of contiguously set indexes in one of the tiered arrays.

The virtual conjunction will include at most n0 n1 and the system will determine whether any of the other arrays reduce this range where they do not have overlapping ranges.

The system determines whether any other array reduces the current range starting at n0 . In other words the system iterates over the other current ranges found for the other arrays to determine whether the arrays do not overlap the range.

If so the system updates n0 and n1 using the range from the array that reduces the current range branch to . The system then repeatedly determines whether the range can be extended with any of the other ranges .

When the range can no longer be reduced by any of the current ranges the system outputs the range n0 n1 .

The system then again determines whether the end of any array has been reached and if so the process ends branch to end .

By computing virtual disjunctions conjunctions and logical NOT by iterating over ranges a system can use the ranges to compute any arbitrary nested virtual composition. For example to compute A or not B the system can compute a virtual disjunction e.g. as described above with reference to using between the ranges output by A e.g. as described above with reference to and the ranges output by NOT the inverse of B e.g. as described above with reference to .

The system can effectively nest the virtual composition processes by using a virtual composition process in place of FindNextRange. For example to compute the virtual nested composition A or B and C the system can compute virtual disjunction between A and the virtual conjunction of B and C. Instead of using FindNextRange in the virtual disjunction process the system can compute the next range of a virtual conjunction for B and C .

This also allows the system compute other compositions e.g. A implies B which is logically equivalent to B or not A as well as a without operation e.g. A without B which is logically equivalent to A and not B. 

The system receives a request to determine whether two tiered arrays have any non default indexes in common . For example the system can perform this check before each request to compute a virtual conjunction and then only compute the virtual conjunction for pairs of arrays that share at least one non default index.

The system determines whether the top level catalogs have non default values in common . If the top level catalogs do not share at least one non default value the two arrays cannot have any intersecting indexes. Thus the system provides an indication that the arrays have no non default indexes in common .

Otherwise the system compares the next mid level catalogs that were referenced by both top level catalogs . For each pair of mid level catalogs referenced by both top level catalogs the system determines whether the mid level catalogs have non default values in common . If they don t the mid level catalogs cannot have any intersecting indexes and the system moves on to determine if there are more mid level catalogs to compare branch to .

If there are more mid level catalogs to compare the system compares the next midlevel catalogs that were referenced by both top level catalogs branch to . Otherwise the system provides an indication that the arrays have no non default indexes in common branch to .

If a pair of mid level catalogs had non default values in common the system compares the next bottom level catalogs that were referenced by both mid level catalogs .

For each pair of mid level catalogs referenced by both mid level catalogs the system determines whether the bottom level catalogs have non default values in common . If they do the system immediately ends the process and provides an indication that the arrays share at least one non default index . Because the system is only testing for non emptiness of a virtual conjunction the system need not make any other comparisons.

If a pair of bottom level catalogs do not have non default values in common the system moves on to determine if there are more bottom level catalogs to compare branch to . Because the system is testing for non emptiness by finding at least one non default index the system thus compares all bottom level catalogs before proceeding to examine other mid level catalogs.

Thus if there are more bottom level catalogs to compare the system compares the next bottom level catalogs that were referenced by both mid level catalogs . Otherwise the system determines whether there are more mid level catalogs to compare .

The structure of tiered arrays also provides for efficient mechanisms for counting a number of non default values represented by a tiered array. Two of such techniques are described with reference to .

The system receives a request to compute a virtual bitwise composition between two tiered arrays . As described above the virtual bitwise composition can be a disjunction conjunction inverse or nested composition thereof. The count of indexes having set values can be used for a number of purposes e.g. for the searching process described below with reference to .

The system receives a plurality of ranges of indexes corresponding to the virtual bitwise composition . The system need not actually compute the full result of the virtual bitwise composition in order to count the number of elements. Rather the system can perform a similar process to that described above with reference to and . Instead of outputting each index that is in the result the system can simply output the start and end of ranges of contiguous values in the result. For example instead of outputting the system can instead output .

The system computes a sum of the plurality of ranges . Rather than iterating through the individual indexes of the result of the bitwise composition the system can instead compute a subcount for each range and then sum the subcounts. For example for each range a0 a1 the system can compute the subcount as a1 a0 1.

The system computes a sum of counts of indexes with which a non default value is associated over all catalogs fully contained within the given range . The system can maintain for each catalog in the tiered array a metadata structure that stores this count of indexes having set values in the catalog. The system can update the count for a catalog whenever a value is set or removed from the catalog. The system can access the metadata structure to obtain counts of catalogs within the given range of indexes and sum the result.

To compute the count over an arbitrary range the system then adds a range based count of set indices over the portions of the range at its start and end that only partially overlap the catalogue that contains them if in each case those ranges exist . The system can use the range finding function to determine whether any ranges overlap the start or end of the given range.

In other words if the given range is x y the system can use FindNextRange A x repeatedly if necessary to count over the initial portion that only partially overlaps a catalogue and FindNextRange A y repeatedly if necessary to count over the final portion that only partially overlaps a catalogue where y is the first index in the catalogue that is only partially overlapped at the end of the counted range x y .

The system receives a request to find the ith index of a virtual composition . As described above a virtual composition can be generated between two tiered arrays. The tiered arrays are actually represented in memory but the virtual composition is represented as ranges of contiguously set indexes and may be generated on the fly.

As described above with reference to some user interface presentations may display a list of dependencies in response to a user selection. The dependencies to be displayed may be part of a virtual composition rather than an actually physically represented tiered array. Thus in order to display the ith dependency of the virtual composition the system can perform a search over the ranges of the virtual composition using range based counting. When the ith dependency of the virtual composition has been found the system can obtain subsequent dependencies simply from the subsequent indexes in the ranges of the virtual composition.

The system computes a count of indexes in a b . The system can use the example process in for example. In some implementations a is initialized to the minimum possible index and b is initialized to the maximum possible index.

The system counts a number of indexes m having set values in the range a c . The system can again use the example process in .

The system sets the total count to m . The total count now represents the number of elements in a c .

The system determines whether the total count is 1 . If the total count is 1 then the index a represents the requested index and the system returns a as the requested index branch to .

If the total count is not 1 the process returns to step to bisect the current range again branch to .

The system subtracts m from the total count . The system can take advantage of the fact that the number of indexes in a c has already been computed. Thus the system need not explicitly count the indexes in c 1 b .

The system subtracts m from i . For example if m was 7 and i was 9 after bisecting the range a b to c 1 b the system will then be searching for the 2nd index in the bisected range.

The system can also use example process to compute the ith index of an actual tiered array rather than a virtual composition. However when using a tiered array the system can significantly speed up the process by making use of the structure of the tiered array and the auxiliary data that records a number of set indexes within each catalog.

For example to start the process the system can obtain from the auxiliary data a minimum index and a maximum index having non default values. The system can set a b to be the values of the minimum index and the maximum index to limit the bisective search to that range.

In addition the system can align the bisected ranges with the catalogs in order to make use of the auxiliary counting data within mid level and bottom level catalogs. In other words each bisection exactly splits a range along a boundary between catalogs. Then when the range fits within one single catalog the system can find the ith index by performing a linear search through the single catalog.

Because aggregated dependencies between arbitrary nodes are too numerous to be precomputed and must therefore be computed in real time a static analysis system can improve the performance and responsiveness of the system by caching the full or partially aggregated dependency results in a structure which will be referred to as a disjoint or tree DOT .

A disjoint or tree has a close relationship with the hierarchy graph. To avoid confusion and ambiguity the disjoint or tree will be described as having elements while the hierarchy graph will be described as having nodes. The disjoint or tree initially starts out empty and the system grows the disjoint or tree as new aggregated dependency sets are computed for various nodes of the hierarchy.

A set that represents the previously computed aggregated inbound or outbound dependencies for a particular node or set of nodes in the hierarchy graph is associated with each element of the disjoint or tree. For brevity the elements of a DOT may be described as storing or having the previously computed sets.

The system can maintain two separate disjoint or trees one for aggregated inbound dependencies and another for aggregated outbound dependencies. The sets of dependencies associated with the elements of a disjoint or tree are either all inbound or all outbound dependencies. Each set of aggregated inbound dependencies or aggregated outbound dependencies can be represented by indexes that each uniquely identify a dependency in the dependency graph. Each set may but need not be represented as a tiered array as described above with reference to .

The structure maintenance and utility of the DOT for aggregated inbound dependencies is identical to that for outbound dependencies and for the sake of brevity the DOT is described in terms of aggregated inbound dependencies from this point forth. Similarly the examples below will refer to manipulating a single disjoint or tree for the aggregated inbound dependencies. However a system will typically maintain another disjoint or tree for the aggregated outbound dependencies.

Some elements of the disjoint or tree directly correspond to nodes in the hierarchy. However some special elements referred to as compound elements do not directly correspond to any elements in the hierarchy. Rather each compound element is a leaf element in the disjoint or tree that stores aggregated inbound dependencies for one or possibly multiple subtrees of nodes in the hierarchy. In general the system can use compound elements to avoid propagating changes through the tree that would result in substantial losses of cached data.

The system maintains a few invariant properties for the disjoint or tree. These invariant properties or invariants for short may be temporarily violated during the course of an operation on the DOT but the system restores the invariants by the point at which the operation is complete. Operations that relate to maintaining these invariant properties will be referred to generally as maintenance operations. The invariants typically include at least these two invariants 

There is one exception to these invariants the DOT may contain only a single incomplete empty compound as its only element which is therefore the root and a leaf. This constitutes an uninitialized state that exists only when the DOT is completely empty of cached data such as when it is first constructed or if it is later cleared.

The first of these invariants requires that the set of dependencies stored by any element is equal to the set union i.e. the result of a logical or operation of all dependencies stored by its child elements in the disjoint or tree. The second requires that the sets of dependencies among the children of any given element do not have any dependencies in common. These two invariant properties give the disjoint or tree its name.

The third of these invariants requires that disregarding compound elements that can only exist as leaves the structure of the DOT directly corresponds with the hierarchy subject to the pruning of nodes from the hierarchy. That is to say every non compound element of the DOT corresponds to a node of the hierarchy and the presence of an element implies that every ancestor where ancestor denotes the parent or an ancestor of the parent of the corresponding node in the hierarchy also has a corresponding ancestor in the DOT.

The first of these two additional invariants exists merely as a practical means to improve the efficiency of the DOT. The second is used to provide a means to compute the importance or weight of an element.

The system receives a request for aggregated inbound dependencies for a particular node and any descendants of the node in the hierarchy . As described above a user of the interactive interface of aggregated dependencies can explore the structure of a code base by selecting one or more nodes of the hierarchy. The system will compute for the selected nodes aggregated inbound dependencies and aggregated outbound dependencies for the selected nodes and their descendants in the hierarchy. If between any pair of nodes the set of aggregated inbound dependencies for a first node and the set of aggregated outbound dependencies for a second node intersect the system generates a presentation showing an aggregated dependency from the second node to the first node.

The example process relates specifically to the system computing the aggregated inbound dependencies for a particular node of the hierarchy by using information cached in a disjoint or tree for aggregated inbound dependencies in the system. As mentioned above the system can perform an identical process with outbound dependencies using a separate disjoint or tree for aggregated outbound dependencies.

The system identifies a position of a corresponding element in a disjoint or tree DOT . As mentioned above some elements of the DOT directly correspond to nodes in the hierarchy and this identification may be performed using the map from IDs to elements or by descending from the root element through a sequence of child elements that have the same ID as each respective ancestor of the node in question.

The system determines whether the result is cached in a corresponding element of the DOT . As required by the invariants each element in the DOT is associated with a designation of complete or incomplete. An element being marked complete means that the set of aggregated inbound dependencies for the element has a complete and up to date version of aggregated inbound dependencies for the corresponding node of the hierarchy.

The result might not be cached due to the corresponding element either not existing at all in the DOT or the corresponding element being marked as incomplete.

If the result is not cached in the DOT the system computes aggregated inbound dependencies for the corresponding node any descendants of the in the hierarchy branch to . The system may but need not necessarily compute the aggregated dependencies from scratch. In particular some of the data needed to compute the aggregated dependencies may already exist in the DOT. Thus it is possible that the system can make use of the previously cached data in DOT even if the full result is not cached. This process is described in more detail below with reference to .

The system determines whether the corresponding node in the hierarchy is important enough to cache . A modern code base may have millions of inbound or outbound dependencies which makes caching all data in main memory infeasible. Thus the system can determine a weight that represents the importance of the corresponding node in the hierarchy before adding an element representing the node to the disjoint or tree. If the weight satisfies a threshold the system caches the result in the DOT. Otherwise the result is not cached.

In general nodes that have more descendants are more important because they tend to aggregate more dependencies. The weight can thus be based on a number of descendant nodes.

Similarly nodes that have more dependencies are more important than nodes that have fewer dependencies. Thus the weight can also be based on the number of dependencies either all inbound or all outbound according to the role of the DOT in question for the node.

In some implementations the system computes the weight as a linear combination of the number of descendant nodes and the number of dependencies according to weight 

where N is a number of descendant nodes and D is a number of dependencies and a and b are empirically chosen constants. Since both N and D have the property that for any given node they always equal or exceed the corresponding value for each child of the node N strictly exceeds it the weight of any given node always exceeds that of each of its children subject to the choice of positive values for a and b . Lastly note that the optional additional invariant above renders the computation of the weight of nodes associated with elements immediate where E and F are thus available.

The system can also adjust the weight for an element according to how recently dependencies for the corresponding node in the hierarchy were requested. The system can maintain a time for each node in the hierarchy represented the last time the dependencies for each node in the hierarchy were requested. The system can then adjust the weight for the element according to how recently the dependencies were requested. If a relatively long amount of time has passed the system can decrease the weight. If a relatively short amount of time has passed the can either maintain or increase the weight.

Rather than maintain the time in absolute terms the system can record the ordinal recency with which each element was requested. This can be achieved by associating an integer recency with each element and maintaining a single global recency counter. Each time an element is requested its recency is assigned the value of the global recency counter and the latter is incremented. When it is necessary to compare the weights it is typically desirable that the weight of any given element equal or exceed that of each of its children. When integer or absolute recency is used to determine weight a single complete traversal of the DOT may be performed to increase the recency of each element to at least that of any of its children unless it is already in excess of them .

The system need not maintain a constant weight threshold. In particular the system can control how much memory is occupied by the DOT by adjusting the weight threshold at run time. For example by increasing the weight threshold the system can shrink the size of the DOT in memory. By decreasing the weight threshold the system can increase the size of the DOT in memory. Adjusting the weight threshold is described in more detail below with reference to .

The system can also determine whether intermediate results are important enough to cache in the DOT. In other words the system need not receive a request for a particular node in order to cache the results for the node in the DOT. For example the system can check whether a computed result is important enough to be cached in the DOT any time a result is computed for a particular node in the hierarchy. For example when computing aggregated inbound dependencies for a node and any of its descendants of the hierarchy the system can determine for each descendant node whether the result computed for the descendant node was also important enough to cache in the DOT.

If the corresponding node is not important enough to cache the system merely returns the computed result branch to .

If the corresponding node is important enough to cache the system adds all ancestors of the node and the node to the DOT if not already in the DOT branch to . In order to maintain the invariant properties of the DOT the system first ensures that the corresponding node exists in the DOT as well as all of its ancestors. Thus the system can traverse the DOT to the node starting with the root node of the DOT adding all ancestors of the node along the way. Each added node is initially empty and marked as incomplete.

The system stores the result with the node of the DOT and marks the node complete . By marking the node as complete if the same results are subsequently requested for the particular node the system can immediately return the fully cached result.

The system propagates the computed results up the DOT . The system maintains the invariant properties of the DOT by propagating the computed results up the tree. To do so the system adds the computed results for the node to each ancestor node. The system can add the computed results to an ancestor node by computing a set union between the computed results and a set stored by the ancestor node.

The system marks newly completed ancestor elements as complete until reaching the root element or a first element not completed by the results . At each ancestor element the system determines whether the added results cause the set associated with the ancestor element to become complete. If so the system marks the ancestor element as complete. The system performs this check until reaching a first element first element that was not completed by the addition of the computed results after which the system need not perform this check on any further ancestors.

It is possible that an element further up in the tree is already complete due to having a child compound element that supplies the dependencies that are missing from the incomplete ancestor. However in that case the addition of the computed results would not affect the status of that element but the dependencies that are now supplied by its newly completed descendant must be removed from its compound child element in order to maintain the invariant that all children contain disjoint sets. Further if such a compound element is thus rendered empty it must be removed.

In this example the system receives a request to compute aggregated inbound dependencies for node of the hierarchy. Assume for this example that node of the hierarchy is important enough for its results to be cached.

When the system receives a request to compute aggregated inbound dependencies for node the system follows the example process outlined in .

First the system adds to the DOT all ancestors of element corresponding to node of the hierarchy if they do not exist. Thus the system adds element as the parent of element . The system initially adds the ancestor elements with empty sets of dependencies and marks the ancestor elements as incomplete.

Third the system computes the aggregated inbound dependencies for the node and stores the result with element . Because the computed results are a complete result for element the system marks element as complete. In general leaf elements of a disjoint or tree are always complete.

Fourth the system propagates the results up the disjoint or tree. The system thus adds the computed result to all ancestors of element which includes elements and . Along the way the system checks each ancestor element to determine whether the added results complete the element. The computed results complete elements and

However because the element corresponds to node which has additional child nodes that are not represented in the DOT the addition of the computed results to the element does not complete the element . Thus the system stops checking whether the ancestor elements are completed by the newly computed results.

However the element is not marked as complete due to the additional child nodes from node that are unrepresented in the DOT.

The system receives a request to compute aggregated dependencies for an element of the DOT . The element may correspond to a particular node of the hierarchy or the element may be a compound element as described above.

The system determines whether the element is marked as complete . If the element is marked as complete the associated set of aggregated dependencies represents an up to date result for the requested computation. Thus if the element is marked as complete the system simply returns the cached result branch to .

If the element is not marked as complete the system adds dependencies inbound to the corresponding node in the hierarchy to the final result branch to . The final result is a running set union and the system will compute the final result by continually adding dependencies to the final result. As a first step the final result of aggregated dependencies for the element will include at least directly inbound dependencies to the corresponding node of the hierarchy.

The system determines whether the element has any children in the DOT . If the element doesn t have any children in the DOT the system is not able to use any previously cached data from the children to compute the final result.

Thus the system computes the result from scratch and returns the result branch to . In this context computing a result from scratch indicates that the system does not use any cached data to compute the result. Rather the system must compute aggregated inbound dependencies for the corresponding node all descendants of the corresponding node in the hierarchy.

When doing so the system can repeatedly determine whether the intermediate result computed for a particular node of the hierarchy is important enough to cache in the DOT. If so the system can add the corresponding element to the DOT and store the computed result.

If the element of the DOT does have children the system iterates through the children of the element branch to . If there are more children of the element to be iterated over the system selects a next child of the element branch to .

The system determines whether the current child is marked as complete or is compound . If the child element is complete or if the child element is a compound element the system can simply add its cached results to the final result without descending any farther in the DOT or the hierarchy.

Thus if the child element is marked as complete or is a compound element the system obtains the cached child result branch to and adds the child result to the final result and then determines whether there are more children to be iterated over .

If the child element is not marked as complete the system computes the results for the child branch to . Although the system needs to compute the results for the child this does not necessarily mean that the child results need to be computed from scratch. Rather the child element could have children itself with previously cached data. Thus the system can compute the child result by recursively invoking the example process of . In either situation the system can cache the computed result if the corresponding node is important enough for its results to be cached in the DOT.

Once all children of the element have been iterated over the system determines whether the corresponding node in the hierarchy has additional children that are not represented in the DOT branch to . As mentioned above the DOT typically does not have elements to represent every node of the hierarchy. Thus it s possible that even after iterating over all child elements the corresponding node in the hierarchy could have additional child nodes that can contribute dependencies to the final result. Therefore the system next iterates over any child nodes in the hierarchy that are unrepresented in the DOT. The unrepresented child nodes include nodes that are not directly represented by elements in the DOT as well as nodes that are not indirectly represented by any compound elements of the DOT.

If there are no such child nodes in the hierarchy that are unrepresented in the DOT the system simply returns the final result branch to .

If there are such child nodes in the hierarchy that are unrepresented in the DOT the system computes the child node results from scratch branch to . Because the child nodes are unrepresented by elements in the DOT there is no possibility for the system to use previously cached data. Thus each of the child results must be computed from scratch. When computing the child results from scratch the system can cache the computed results if the corresponding node is important enough.

The system then adds the results from the unrepresented child nodes to the final result and returns the final result .

As described above with reference to after computing the result the system can decide whether or not the corresponding node is important enough to cache. If so they system caches the computed result.

The system determines that a disjoint or tree has reached a maximum memory limit . The system can use a predefined limit for the maximum amount of main memory that any DOT is allowed to occupy e.g. 10 MB 100 MB 1 GB.

If the DOT grows beyond the maximum memory limit the performance of the system can start to degrade and the benefits of caching the aggregated dependencies starts to decline. Thus the system will reduce the size of the DOT so that its size is under the predefined limit.

The memory footprint of the DOT depends on how many elements the DOT contains as well as the memory occupied by the representations of the sets of dependencies stored by each element of the DOT. If the sets of dependencies are represented as tiered arrays the system can efficiently compute an upper bound for the memory footprint by using a metadata structure associated with each tiered array that stores the count of indexes within each catalog having set values. Thus the system can simply sum the counts rather than computing the size by actually counting the indexes from scratch.

The upper bound is typically larger than the actual memory occupied by the DOT due to data conjoining in which multiple allocated catalogs belong to multiple tiered arrays. Conjoining of tiered arrays is described in more detail below with reference to . In general to compute a refined memory footprint for the DOT the system subtracts from the upper bound counts that occur in conjoined catalogs.

In some implementations if the upper bound exceeds the maximum memory limit the system expends the additional computational effort to compute the refined memory footprint. The system then determines that the maximum memory limit has been reached only if the refined memory footprint exceeds the maximum memory limit.

The system selects elements for removal . Owing to the tree structure of the DOT it is not possible to remove an element without removing all of its descendants. The weight function is typically designed such that the weight of a parent always exceeds that of its children so that an ordinal sequence of all elements sorted by increasing weight will always include all the descendants of an element before that element.

In some implementations the system ranks all elements in order by weight and selects for removal one or more elements having the lowest weights.

The system may loop through the example process multiple times before a memory reduction goal is reached. Thus the system can select a predetermined number of elements for removal on each iteration e.g. 10 100 or 1000. Alternatively the system can select a minimum weight and remove all elements not having a weight that is at least the minimum weight.

After selecting a number of elements for removal the system could then proceed to perform removal and maintenance operations for the selected elements. And if the memory reduction goal had not been reached the system could then select additional elements for removal.

However the system can reduce the time required to condense the DOT for a particular memory reduction goal by iteratively computing an estimate for the memory reduction that would be achieved by removing the elements that have been selected so far.

Thus the system computes an estimated memory reduction from the elements selected so far . The system can maintain a running total of the estimated memory reduction and the system can update the running total on each iteration. The system can compute either the upper bound for the memory footprint or the refined memory footprint as described above.

The system determines whether a memory reduction goal has been reached . The memory reduction goal is reached when the estimated memory reduction is less than or equal to a particular a fraction of the maximum memory limit e.g. 50 65 or 80 of the maximum memory limit. The memory reduction goal ensures that after removing elements from the DOT the DOT will have room to grow again before hitting the maximum memory limit again.

If the memory reduction goal has not been reached the system again selects more elements for removal branch to .

If the memory reduction goal has been reached the system performs removal and maintenance operations branch to . The elements selected by the system on each iteration will either be leaf elements or non leaf elements. The system must perform different maintenance operations for each of these types of elements in order to maintain as much cached data as possible when reducing the memory footprint of the DOT.

For example if a low level leaf element having one or more siblings is selected for removal the system will perform maintenance operations related to removing a leaf element. These maintenance operations are described in more detail below with reference to .

On the other hand if all siblings of a particular parent element are selected for removal the system will perform maintenance operations related to converting a non leaf element into a leaf element. These maintenance operations are described in more detail below with reference to .

The system receives a request to convert a non leaf element into a leaf element . This can occur for example when all child elements of a particular element are selected for removal. Thus the previous non leaf element will become a leaf element.

As described above one of the invariant properties of the DOT is that leaf elements cannot be incomplete. Thus at a minimum the system will need to complete the non leaf element as part of its maintenance operations.

The system determines whether the non leaf element is complete . If the element is complete nothing more needs to be done. The element already contains all information for all of its children thus it can be safely converted to a leaf element without performing any additional maintenance operations.

Thus if the non leaf element is complete the system simply converts the element to a leaf element branch to . In doing so the system either implicitly or explicitly drops all descendants of the element in the DOT.

If the non leaf element is not complete the system completes the element branch to . Completing the element involves computing all the aggregated dependencies for the corresponding node in the hierarchy. Before discarding its descendants the cached information in the descendants can be used to complete the element. This can be accomplished according to the example process described above with reference to .

Completing the element will often require the system to perform further maintenance operations . In particular the system can propagate the newly added dependencies up the DOT in order to maintain the invariant properties of the ancestors of the element.

After completing the element the system converts the element to a leaf element which causes the system to explicitly or implicitly drop all of its descendant elements.

The system receives a request to remove a leaf element . This can occur for example when the leaf element is selected for removal as part of the condensing process described above with reference to .

The system can perform the process in when fewer than all child leaf elements of a particular parent element are selected for removal. If all child leaf elements are selected for removal the system can perform the process described above with reference to .

As mentioned above merely truncating the tree to remove a leaf element potentially wastes cached data in the leaf element. Thus the system can instead condense the tree by maintaining cached data in a parent of the leaf element.

The system determines whether the parent element of the leaf element is complete . If the parent element is complete then the system can maintain the data cached in the leaf element by adding the cached data to a compound element. As described above compound elements represent the cached data of one or more subtrees from the hierarchy. Compound elements can only be leaf elements compound elements can only be children of complete parent elements and parent elements can only have a single compound child element.

Thus if the parent element is complete the system determines whether the parent element has a compound element . If not the system generates a compound element as a child of the parent element branch to and adds the leaf element data to the compound element . If the compound element already exists the system can add the leaf element data to the compound element .

As a concrete example assume that a particular parent element has four leaf elements and that three of the leaf elements are selected for removal during a condensing process. Rather than discarding all of the cached data in those three leaf elements the system can preserve the cached data by storing a disjunction of the data in the three leaf elements in a new compound child element of the parent element. This reduces the memory footprint of the tree while preserving the cached data.

The system can then remove the leaf element . Because the parent was complete the system can remove the leaf element without performing any further maintenance operations.

If the parent was not complete the system can remove the leaf element branch to . Removing the leaf element will cause a loss of some cached data and thus the system performs maintenance operations to propagate the changes up the tree. In particular this involves subtracting from the set of every ancestor element the dependencies associated with the leaf element.

The system receives an identification of elements that were removed during a most recent DOT condensing process .

The system determines a new weight threshold . In some implementations the system computes a new weight threshold based on the weight that was largest among elements that were removed. For example the system can set the new weight threshold to be equal to or greater than the largest weight among elements that were removed.

In doing so the system ensures that elements that were removed during a previous condensation process are not cached again. This has the effect of reducing the frequency of condensation processes on each iteration.

The system can also estimate a final weight threshold and set the weight threshold to the estimated final weight threshold. The system can reduce the number of condensation iterations by computing this estimate during the first condensation process.

The total memory footprint of a DOT has a close relationship to a ratio of i the total coverage c of dependencies in the root element of the DOT to ii the current weight threshold w. The system can compute the total coverage c as the number of dependencies represented by the root element divided by the total number of dependencies in the project. The system can then compute an estimate m w of the total memory footprint of the DOT if it were fully populated using a minimum weight of w. The estimate m w is a c where a represents the memory footprint of the DOT with coverage c and populated using minimum weight w. The values of a and c are measured directly using the current state of the DOT.

The system can then estimate the ideal weight threshold by assuming a linear relationship between total memory footprint and the weight threshold. Thus for a given maximum memory limit l the system can compute the estimated weight threshold as w l m w .

The system performs a new condensation process when the maximum memory limit is reached . After performing the condensation process the system can iterate once again by receiving an identification of elements that were removed during the most recent condensation process branch to . Thus the example process has no set end point. Rather the system dynamically updates the weight threshold each time the system performs a condensation process on the DOT.

When the system updates the weight threshold using the estimate described above the estimate tends to come close to but underestimate the ideal weight threshold. If a condensation step using a weight threshold of w does not reduce the memory footprint below the maximum then w can be immediately confirmed as a lower bound for the ideal weight threshold and further condensation steps performed to achieve a memory footprint beneath the maximum. If a condensation step does reduce the footprint beneath the maximum then w cannot be confirmed because it may have been higher than the ideal weight threshold. In this case the use of w is recorded and if the footprint of the DOT subsequently exceeds the maximum without adding elements of lower weight than w it can be confirmed at that point. If the DOT then does exceed the maximum memory limit the true final weight threshold can be computed exactly. In this way the system can often achieve the final weight threshold with a small number of condensation processes. If more iterations are required the system can use linear regression over all samples w m w in order to improve the accuracy of the estimated final weight threshold. When an unconfirmed threshold w is recorded the system can tentatively adopt this as a minimum weight during normal maintenance of the DOT. If the coverage of the DOT subsequently draws close to 100 without exceeding the maximum footprint the tentative threshold can be rejected. Typically however a tentative weight deduced in this manner is quickly confirmed.

The system sets the weight threshold to an initial value . The system can choose an initial value that will cause most if not all nodes of the hierarchy to be cached in the DOT. In some implementations the system uses zero as the initial value.

The system computes aggregated inbound dependencies for the root node of the hierarchy . Because of the invariant properties of the DOT the root element of the DOT contains a set union of all dependencies in the entire hierarchy. Thus the system can most quickly grow the DOT beyond the selected maximum memory limit by requesting aggregated dependencies for the root node.

The system condenses the DOT and computes a new weight threshold . The system can compute the new weight threshold as described above e.g. by choosing the largest weight among elements removed from the DOT or by estimating the final weight threshold.

The system associates the new weight threshold with the selected maximum memory limit . After doing so the system can immediately use the new weight threshold for any user having a machine with the selected maximum memory limit and in general the largest weight threshold confirmed for any given memory limit can be recorded in association with the data from which a given DOT is populated e.g. dependency data as stored on disk and reused in future whenever applicable.

For example if a user s machine has X MB of memory available for the DOT the system can immediately use the largest of any precomputed weight thresholds for Y MB of memory for any Y that is at most X.

The system determines whether more maximum memory limits remain . If so the system selects the next maximum memory limit branch to and if not the process ends branch to end .

When using tiered arrays to represent sets of dependencies for each element of the DOT the system can use data conjoining to reduce the size of the DOT and decrease the processing time required to perform the maintenance operations. Data conjoining refers to representing two logically separate data elements with a same segment of memory. In other words multiple pointers that represent logically separate data may point to the same data in memory.

For example if two tiered arrays are identical between a parent element and a child element of the parent element the system can allocate memory for only one tiered array that represents both. The parent element and the child element will then both reference the same tiered array. Alternatively if the parent and child contain different data but the range of data within a particular catalogue of the tired arrays is identical then the tiered arrays of both parent and child can reference that same catalogue while also containing other catalogues unique to either parent or child. This arrangement is advantageous in a disjoint or tree because the invariant properties of the DOT require parent and child elements to share data and typically a DOT contains vast amounts of shared data between parent and child elements.

For brevity two elements can be described as being conjoined which means that the tiered arrays associated with the elements are conjoined in whole or in part.

Conjoining data naturally reduces the memory that is occupied by the DOT. Conjoining data also reduces the time required to perform maintenance operations on the DOT. This is because a maintenance operation performed on a tiered array of a child element is also implicitly performed on a tiered array of a parent element if the tiered arrays have been conjoined. In other words if a maintenance operation is performed on a tiered array of a child element in many cases the system need not actually perform any maintenance operations for the parent and possibly several ancestors of the parent as well. When the system uses conjoining it is possible and desirable to maintain the invariant that conjoining is always adopted between parent and child elements whenever it is possible to do so for the entire tiered array or for corresponding catalogues.

The system receives a request to perform an operation on a parent element having a child element . The maintenance operations that maintain the invariant properties for the DOT typically involve adding or subtracting dependencies from a child element and then propagating the changes to a parent element in a bottom up fashion. The example process assumes that the requested operation has already been sufficiently performed for the child element.

Although a child element and a grandparent element of the child element can be conjoined in fact by their respective tiered arrays referencing the same data the system need not compare a child element to its grandparent element to maintain their conjoined data. Rather the structure of the DOT provides such benefits implicitly. The conjoining operations themselves will implicitly maintain this relationship without requiring the system to explicitly compare the child element to the grandparent element or any ancestor other than its direct parent.

Therefore it is sufficient for the example process to be performed in terms of a parent element that the system compares to a child element. The system will then apply the same process to each ancestor of the child in the DOT.

The system compares ranges of indexes for corresponding catalogs between the parent element and the child element . For simplicity the example process describes performing a comparison on only a single catalog. However the system can perform this comparison as well as the rest of the example process on all catalogs in the tiered arrays of the parent element and the child element. The system can compare the corresponding catalogs in the order of their level in the tiered array starting from higher level catalogs and proceeding to lower level catalogs of the tiered arrays.

The system performs the comparison to determine how the requested operation will change the sets of dependencies between the compared catalogs. When comparing catalogs the system compares how the requested operation will change dependency indexes within the ranges of indexes represented by the catalogs.

For example if the requested operation causes two top level catalogs to represent the exact same set of dependencies the system can fully conjoin the tiered arrays associated with the parent element and the child element.

Likewise if the requested operation causes two mid level catalogs or two bottom level catalogs to represent the same set of dependency indexes the system can conjoin those catalogs without necessarily conjoining all catalogs. In other words the tiered arrays may contain different data except for having pointers that reference a same mid level or bottom level catalog.

The system determines whether the requested operation will cause the corresponding ranges of indexes to remain the same . In other words the system determines that the corresponding ranges of indexes i were the same before the operation was performed on the child and ii will remain the same after the operation is performed on the parent. This can occur for example when a child element gains an additional cached dependency index in which case the requested maintenance operation merely propagates the additional dependency up to the parent. The former determination is trivial if the invariant regarding the full adoption of conjoining described above is maintained because the system only needs to check whether the parent and child are conjoining their tiered arrays or catalogues within after performing the maintenance operation on the child.

If so the system need not actually perform any maintenance operations on the parent element branch to end . In other words because the system already performed the operation on the corresponding range of child element and because the parent element refers to the exact same data segment in memory the operation has already effectively been performed for the parent.

The system also alternatively determines whether the requested operation will cause the corresponding ranges of indexes to become different . In other words the system determines that the corresponding ranges of indexes i were the same before the operation was performed on the child and ii will be different after the operation is performed on the parent. This can occur for example when the parent element gains another child element i.e. a sibling of the child element which can cause the catalog in the parent to have additional dependencies that the original and unaffected child element does not.

If so the system needs to unconjoin the catalog between the parent element and the child element. Thus the system allocates a new catalog for the parent element updates a pointer in the tiered array of the parent that will point to the newly allocated catalog and populates the newly allocated catalogue accordingly.

The system also alternatively determines whether the requested operation will cause the corresponding ranges of indexes to become the same . In other words the system determines that the corresponding ranges of indexes i were different before the operation was performed on the child and ii will be the same after the operation is performed on the parent. This can occur for example when a child element loses its own child element which causes the catalog of the child element to match the catalog of the parent element.

If so the system can conjoin the catalog between the parent element and the child element. Thus the system updates the pointer in the parent element to reference the corresponding catalog in the child element thus conjoining parent and child. If the parent element does not have a parent element that also conjoins the same catalogue then the system deallocates the catalog for the parent element . If it does then the next iteration of the algorithm on the parent s parent will deallocate the catalogue if appropriate. In addition to conjoining elements at the tiered array or catalog level the system can also use techniques to share data between two disjoint or trees. For example as part of the user manipulations of the hierarchy graph the system may make a copy of the DOT to cache data in the tentative user created version of the hierarchy.

Because the DOT may occupy hundreds of megabytes of data allocating an actual copy is typically too costly in time and space. Thus the system can make a lazy copy that simply refers to the original DOT. Elements from the original DOT are only copied when they are written to at which point they copied first and then written.

When performing the usual bottom up maintenance operations on the copy the operations will cause the system to make copies of all elements in the ancestral chain of the copy. However some of the copied data may still be conjoined with data from the original DOT.

The system receives a request to compute aggregated dependencies between a node A and a node B in the hierarchy . As described above an aggregated dependency exists from A to B when the union of outgoing dependencies of node A and any of its descendants intersects a union of inbound dependencies of node B and any of its descendants. The system can then use data cached in the DOTs to try to curtail computation of this result. In other words the system can use the data cached in the DOT to avoid computing a full conjunction between A and B.

The selects next node between A or B . The system select either A or B first to determine whether its data is cached and whether it is empty.

If so the system determines whether the cached set for the selected node is empty branch to . If the cached set for the selected node is empty the system returns an empty result and the process ends branch to .

If the cached set for the node was not empty the system cannot curtail the computation for that node and thus proceeds to consider the other node. The system thus determines whether it has considered both nodes branch to . If the system has not considered both nodes the system proceeds to select the next node branch to and then applies the same tests to the next selected node.

If the set for the selected node is not cached the system determines whether an ancestor of the selected node is cached branch to . If so the system determines whether the cached set for the ancestor is empty branch to . Because each node in the disjoint or tree stores a union of dependencies of its children if a cached ancestor of a node is empty the node is also empty. If the cached set for the ancestor is empty the system returns an empty result branch to .

If the set for the ancestor of the selected node is not cached or if the cached set for the ancestor was not empty the system cannot curtail the computation for that node and thus the system determines whether it has considered both nodes branch to .

As shown in the system determines whether one of the nodes was uncached . If both nodes are cached the system determines whether the conjunction of the sets is empty . As described above when the dependency sets are represented as tiered arrays the system can more quickly determine that the conjunction is empty than to compute the entire conjunction. If the conjunction is empty the system returns an empty result branch to . If the conjunction is not empty the system cannot curtail the computation and the system computes the full conjunction of the set for A and the set for B .

If one of the sets was uncached the system computes the uncached set using DOT data when available . As described above with reference to the system can more quickly calculate the dependency set using descendant elements in the DOT that store partially cached data for the uncached set.

The system then determines whether the set is empty . If the set is empty the system returns an empty result branch to .

If the set was not empty the system determines whether a conjunction with the other set if cached or an ancestor of the other set if cached is empty . If so the system returns an empty result . If not the system proceeds to perform a similar series of tests on the set of dependencies for the other node branch to .

The system determines whether the other set for the other node is cached . If not the system computes the uncached set using DOT data when available .

The system then determines whether the other set is empty . If so the system returns an empty result branch to .

If the other set was not empty the system determines whether a conjunction with the other set or an ancestor of the other set if cached is empty . At this point the system will have already computed the set for the first node considered.

If the conjunction with the other set or an ancestor of the other set is empty the system returns an empty result branch to .

Otherwise the system will have exhausted all possible ways of curtailing the computation. Thus the system computes the full conjunction of the set for A and the set for B .

The underlined reference numbers designate DOT elements that have been marked as complete meaning that the data cached in the element represents a complete set of aggregated dependencies for the corresponding node of the hierarchy. In this example all elements of the DOT are complete.

If the node is important enough to be cached in the DOT the changes will be propagated up the DOT and the DOT can maintain its fully cached state.

However if the node is not important enough to be cached in the DOT the addition of this node invalidates the cached data for the element . This is because the element no longer has a complete set of aggregated dependencies for the corresponding node of the hierarchy.

To handle the invalidated data the system can do one of two things. First the system can complete the element by adding a new compound element that includes the data from the added node . The system would then need to incorporate those same dependencies in every element in the ancestral chain all the way up to the root node. These operations may be costly if the affected element is far from the root element.

Thus the system can alternatively simply mark the element as incomplete. The system would then propagate this change to incomplete up the ancestral chain to the root element . Thus the root element is would also be marked as incomplete.

If the node is important enough to be cached in the DOT the addition of the node invalidates the cached data for the element . This is because the element no longer has data that is equal to a union of its children.

To address this situation the system generates a new compound element that has all the data in that is not in the new element . In other words the system computes a difference between elements and and stores the result in the compound element

The data stored in the compound element will end up being equal to the union of data from all of the other uncached children of node e.g. and . However the system does not need to actually inspect those nodes to obtain this data. Rather it can be deduced from the invariant properties of the DOT by computing the difference between elements and

If either of the nodes or were ever to become important enough to be cached in the DOT the system would need to subtract their data from the compound element . Doing so will maintain the invariant property that the contents of element is the children of element must have disjoint sets.

In the DOT the removal of this node invalidates the cached data for the element so the data for the element must be updated. This is because the element no longer contains a set union of the dependencies of its children.

To handle the invalidated data the system must subtract from the node and every other element up the ancestral chain the dependencies contributed by the node . The nodes can remain marked as complete because the subtraction of dependencies from a removed node does not invalidate their status as complete.

If the element had not existed in the DOT before the node had been removed the system would need to first explicitly compute the aggregated dependencies for the node before it was able to subtract from the ancestors of element

If computing aggregated dependencies for the purpose of subtracting them from nodes in the DOT the system can bypass several steps of the usual process. For example the system need not consider whether the node is important enough for caching because it has already been explicitly removed. No descendants of the node should be cached either as they will also be implicitly removed. Therefore the system can turn off all caching tests and operations when computing aggregated dependencies only for the purpose of subtracting the resulting dependencies in the DOT.

In this example a user moves the subtree of the hierarchy so that the subtree is descended from the node

To maintain the properties of the DOT the system removes the dependencies of element from the previous ancestor element . Thus the previous ancestor element is still complete.

The element is now a child of element . To maintain the invariant properties of the DOT the system adds the dependencies of element to the parent element and all ancestors of

The system can maintain the cached data in element and all of its descendent elements without recomputing any sets of dependencies. Thus the element and its children remain complete.

The system receives a request to compute aggregated dependencies among a plurality of elements . The system will generally compare aggregated inbound dependencies represented in one disjoint or tree with aggregated outbound dependencies represented in another disjoint or tree. For clarity the description of the example process will refer to singular elements even though each element in the system is actually doubly represented in the inbound and the outbound disjoint or trees. The description of the example process need not specify to which disjoint or tree an element actually belongs because this information is apparent from whether or not the element is being referenced for its inbound or outbound dependencies.

The system partitions the elements into a plurality of groups . The number of groups is typically fixed at a predetermined value e.g. 2 4 or 8 groups. The process works more efficiently when there are roughly an equal number of descendant elements in each group. Thus in some implementations the system considers the number of descendants from each element when partitioning the elements into groups. If the number of elements is less than or equal to the predetermined number of groups the system need not partition the groups and can instead treat each individual element as a group.

The system computes disjunctions of inbound and outbound dependencies for each group . In other words the system computes a logical OR over all dependencies associated with each element in each group to generate a set of dependencies representing all the inbound or outbound dependencies in the group. The system computes this disjunction separately for both inbound and outbound dependencies for elements in the group.

The representative set of dependencies is equivalent to the set of dependencies that would exist for a parent element of all the elements in the group. In some implementations the system adds a special virtual parent element to the disjoint or tree and associates the representative inbound and outbound sets with the virtual parent element. The system can thus cache the results of the disjunctions. However the virtual parent elements would typically not be shown to a user.

The system performs a pairwise comparison between each pair of groups to determine whether at least one dependency ID intersects . This comparison determines whether any aggregated dependencies exist from a first group of the pair to a second group of the pair. As described above an aggregated dependency exists from a first element to a second element when an outbound dependency of a first element intersects an inbound dependency of a second element.

When performing this comparison the system need not compute a full intersection between the sets. Rather the system can stop the comparison upon finding a first intersecting dependency ID.

The system importantly also performs this comparison between pairs having a same first group and second group. In other words the system compares the aggregated inbound dependencies of the group to the aggregated outbound dependencies of the same group to determine if any of the elements in the group have dependencies with any other elements in the group.

The system then performs a pairwise comparison between the groups. For example the system compares X to X X to Y Y to X and Y to Y.

As indicated in the checkmarks indicate that the comparison of X to X and Y to X had at least one intersecting dependency ID while the x s indicate that the comparison of X to Y and Y to Y did not.

The system can then stop considering pairs of groups for which there was no intersection. Thus in this example the system need not again consider any combination of elements involving X to Y or Y to Y.

The system can then proceed to process only pairs of groups for which there was at least one intersecting ID e.g. X to Y and Y to Y.

For each pair of groups having at least one dependency intersection the system partitions one of the groups into subgroups . For example as shown in for the comparison of X to X the system partitions one of the groups into the elements A and B. As shown in for the comparison of Y to X the system partitions X into the individual elements A and B.

The system performs a pairwise comparison between the non partitioned group and each of the subgroups to determine whether at least one dependency ID intersects . The set of dependencies for the non partitioned group still includes a disjunction representative of all dependencies of all elements in the group. Thus this result may already be cached as a virtual parent element in the disjoint or tree and the system can reuse the cached result for these comparisons. The results for the individual elements may also already be cached in the disjoint or tree because those results were needed to compute the group disjunction.

Thus as shown in the system performs a comparison between the representative disjunction for X and each of the individual elements A and B. Similarly as shown in the system performs a comparison between the representative disjunction for Y and each of the individual elements A and B.

As indicated by the check mark and x symbols at least one dependency exists from the representative set for X and the individual element A and at least one dependency exists from the representative set for Y and the individual element B.

The system determines whether the comparison was between individual elements . If the comparison was not between individual elements the system once again partitions the elements into subgroups branch to .

The system can alternate between partitioning groups for inbound and outbound dependencies. For example as shown in because the system previously partitioned X the inbound dependency set the system next partitions Y the outbound dependency set. Similarly as shown in the system previously partitioned the inbound dependency set and thus now partitions the outbound dependency set into the individual elements A and B.

Each time the system partitions elements into a new group of dependencies the system computes a new disjunction that represents all dependencies among elements in the set. For example as shown in the system computes a new disjunction for Y which includes elements C and D. In some implementations the system can more efficiently compute the updated dependency sets by subtracting dependencies from elements that were previously in the group. For example to compute the dependency set for Y the system can subtract the dependencies of element E from the previously dependency for Y.

When the partitioning of groups reaches a point where individual elements are being compared the system determines whether there is an intersection between the individual elements branch to . For example as shown in the system can determine that the comparisons have reached the level of comparing individual elements.

If there is no intersection between the individual elements that branch of the process ends branch to end .

If there is an intersection between the individual elements the system optionally computes a full intersection between the elements . For example the system may display the actual number of dependencies between the elements in addition to other information about where the dependencies are in the code base. But in some implementations the system merely determines the fact that an aggregated dependency exists between the elements.

The system outputs the intersections between individual elements as aggregated dependencies . For example as shown in the system would output an indication of the aggregated dependency from element B to element A. Similarly as shown in the system would output an indication of the aggregated dependency between element E and element B.

As shown in the determination that of the B to A dependency and the E to B dependency took only 12 comparisons. In contrast an element by element strategy would have taken n 2 comparisons which in this example with original elements would have required 25 comparisons.

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


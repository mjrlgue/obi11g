# obi11g
OBIEE: the book (Oracle Business Intelligence Enterprise Edition 11g: A Hands-On Tutorial) provides an overview of the oracle Fusion Middleware.

# Architecture Overview (big picture):
  Infrastructure components of OBI 11g:

- **Oracle BI domain:** it is the core architecture of Oracle 11g       
- **WebLogic Server :**  It is  the chosen application server for Oracle        
- **Java components :**  components and classes written in Java for Oracle. They are deployed to the application server and Server.                                        
- **System components:** components which have been written mainly in C++ Oracle BI 11g. They are managed by the Oracle Process Management and Notification Server.             
- **Oracle BI relational repository:** a set of database schemas that store metadata related to a specific OB
- **Oracle BI filesystem:** set of physical files and directories contain configuration, logs, and metadata concerning.

After installation we will have the architecture seen.

# Oracle Fusion Middleware
Oracle Fusion Middleware is taking on the enterprise challenge of bringing together
the Oracle database and Oracle applications stacks.  It is the middle-tier between
them.  To achieve interoperability, a common layer had to be formed
to fuse together the existing technologies, create efficiencies, and provide consistent
delivery of software applications. The following  illustrates the main categories
of products, making up the current Oracle product stack:
- Applications
- Middleware
- Database
- Operating  System
- Virtual machine
- Servers
- Storage

The **Fusion Middleware** product category contains Oracle **Fusion Middleware (FMW)** which forms the core of Oracle's **Application Integration Architecture (AIA)**.

### Application server name
In previous versions of OBI, the default application server delivred with the product suite was **Oracle Container for Java (OC4J)**. However, with the release of OBI 11g, **Oracle WebLogic Server (WLS)** became the core application server. Previously, it was known as BEA WebLogic.

Actually, the Oracle BI 11g installation process cannot begin until these repositories
are created by the **Repository Creation Utility (RCU)** and accessible on a database
server.
>  Installing the Metadata Repository, goes into greater detail about this crucial repository structure, better known by two database schemas—Metadata Services (MDS) and BIPLATFORM.

The **RPD** is the metadata storage mechanism in which Oracle BI developers model
and map physical data sources to logical business representations in order for the
resulting analytics to be easily consumed by the end users

### Overall components
There are a lot of components in OBI 11g. OBI can categorize these components by classifiying them based on the programming languages in which they were developed. They are mainly _Java_ or _C++_. 
The following diagram provides a high-level overview of the main components that
comprise the Oracle BI 11g architecture.
[diagram 38]

The term **Oracle BI Domain**, as noted previously and shown in the illustration, is
used as a way to group all Oracle BI 11g components within the Fusion Middleware
architecture. The default **WebLogic Application Server** name in installation option is `bifoundation_domain`.
> WebLogic Server is a Java application server that manages all of the Oracle BI components developed in Java. Anothermanagement system, the **Oracle Process Management and Notification (OPMN)** system, handles the other components, which are referred to as **_System Components_**.

### Java components
Java components _(which have been developed in Java)_, are as follows:
- **Acton Service**: Primarly used by Action Framework it executes actions on behalf of Presentation Services and Oracle BI Scheduler. Actions may be invocations of third party web services, or invocations of user supplied Java code executed as **Enterprise JavaBeans (EJB)**.
- **Administrative components: Java Management Extensions (JMX)  ** and **Managed Beans (MBean)** allow dynamic **Application Programming Interface (API)** functionality for managing, configuring, and administering Oracle BI 11g.
- **Web Service SOA:** This provide a web service interface to the contents of the Oracle BI Presentation Catalog. The tree of objects in Oracle BI Presentation Catalog is exposed as a tree of web services, defined by a **Web Services Inspection Language (WSIL)** tree with **Web Service Definition language (WSDL0)** leaves.
- **Oracle BI Office:** It provides integration between Microsoft Office and
Oracle BI 11g.
- **Oracle Real-time Decisions (RTD):** RTD provides a decision making
rules engine that enables real-time business intelligence predictions and
outcome analysis.
- **Oracle BI Presentation Service plugin:** Presentation Services run as a
process, not as a web server, and does not communicate using any web
server plugin API. The Oracle BI Presentation Services plugin forwards
HTTP requests to Presentation Services. The HTTP requests are the requests
from the browser-based user interface, or SOAP requests. This is ultimately
just a servlet.
- **Oracle BI Publisher:** It is the enterprise reporting solution used for authoring
and delivering highly formatted documents.
- **Security Services:** It provides standards-based authentication and
population services. It enables OBI server to integrate with the Fusion Middleware security  which includes the Credential Framework and the Identity Store.

### System components
in OBI 11g, the system components are those which are developed in a non-Java programming language. Most of the system components have been developed in the C++ programming language as mentioned earlier. List of components as follows:
- **Oracle BI Server:** Thi is a C++ process that performs the data manipulation and aggregates data from data sources. You can configure multiple Oracle BI Server process, which share the load. No session replication takes place between the Oracle BI Server processes.
The Oracle BI Server does not maintain a user session state. For high availability deployments, query results are cached in the blobal cache.

- **Oracle BI Presentation Server:** This is a C++ process that generates the user interface pages and renders results sets on behalf of the Oracle BI Scheduler.
 
 > Since the BI Presentation Server maintains the authentication state, the users do not have to log in on each subsequent dashboard that they visit. Note that if a system is stateless, the application cannot easily remember the information about the user or actions performed previously.

- **Oracle BI Scheduler:** it is a C++ process that runs the jobs according to a configurable frequency. Jobs can be created by agents in Oracle BI Presentation Catalog, or jobs can be created by the Job Manager.
- **Oracle BI JavaHost:** It is a Java process that includes resource-intensive graphs and PDF rendering. It also allows Oracle BI Presentation Services to support Oracle BI Publisher and Java tasks within the Oracle BI Scheduler. 
- **Oracle BI Server Cluster Controller:** It is a C++ process, which manages the
population of Oracle BI Servers and Oracle BI Schedulers. It also distributes
the requests to the Oracle BI Server and ensures that requests are evenly load
balanced across scaled-out Oracle BI Servers in the domain.

Following illustration shows each of the components comprising the core Oracle BI architecture, the communication ports, and the communication direction:

[image 41]

### WebLogic Server
**WebLogic** is an enterprise application server that is at the core of Oracle Fusion Middleware. The Oracle WebLogic Server is a scalble, enterprise-ready **Java Platform Enterprise Edition (Java EE)** application server. Its infrastructure supports the deployment of many types of distributed applications.

### WebLogic Domain
The highest unit of management for controlling the WebLogic Server Installation is called a **domain**. A domain is a logically related group of WebLogic Server resources that you manage as a unit. A domain always includes, and is centrally maanged by one Administration Server. Additional WebLogic Server instances which are controlled by the Administration Server for the domain are called **Managed Servers**. The configuration for all the servers in the domain is stored in the configuration repository, the `config.xml` file, which resides on the macine hosting the Administration Server. The `config.xml` files, by default, are stored in the path `<FMW_HOME>\user_projects\domains\bifoundation_domain\`,
where `<FMW_HOME>` is the path on the server to which you have installed OBI 11g.

Upon installing and configuring Oracle BI 11g, the domain named `bifoundation_domain` is established within the WebLogic Server. This domain is the recommended name for each Oracle BI 11g implementation and should not be modified.

### WebLogic Administration Server
The WebLogic Server is an enterprise software suite that manages a myriad of application server components mainly focused on Java technology.
One of the most crucial components of the WebLogic Server is the WebLogic Administration Server. When installing the WebLogic Server software, the WebLogic Administration
Server is automatically installed with it.  It is the Administration Server that not
only controls all subsequent WebLogic Server instances called Managed Servers,
but also controls aspects such as security, Persistence Stores, and other application
server-related configurations.

The WebLogic Server gets installed on the operating system and ultimately runs as
a service on that machine. The WebLogic Server can be managed in several ways. The two main methods are via the **Graphical User Interface (GUI)** web application
called the WebLogic Administration Console or via the command line using the
**WebLogic Scripting Tool (WLST).** 
_The WebLogic Administration Server and the WebLogic Server are basically
synonymous._  If the WebLogic Server is not running, the WebLogic Administration
Console will be unavailable as well. If the WebLogic AdminServer is not running, no
administrative tasks can be made to the system, although concessions are made for
a High Availability configuration.

### WebLogic Managed Server
Web applications, **Enterprise Java Beans (EJB)**, and other resources are deployed
on to one or more WebLogic Managed Servers in a WebLogic Domain. A WebLogic
Managed Server is an instance of a WebLogic Server in a WebLogic Server domain. Only one Administration Server per domain must exist, but one or more Managed Servers may exist in
the WebLogic Server domain. Having one or more managed servers, allow for
deployed JEE applications to be logically delineated.

In a production deployment, OBI 11g is deployed into its own Managed Server. The OBI 11g installer comes with three installation types: _simple, enterprise and software._ The latter two installation types configure two WebLogic Server instances, the_ Administration Server_ and another _Managed Server_ called `bi_server1.` OBI 11g is deployed into the Managed Server called `bi_server1` and is configured by default to resolve to port `9704`.
The simple installation type configures only the Administration Server, deploys OBI 11g into it, and resolves to port `7001`.
For the simple installation type, only oen WebLogic Server instance exists.

> Note that the Enterprise Manager Fusion Control is actually a JEE application deployed to the Administration Server instance, which is why its web client is accessible under port `7001`. It is not necessarily a native application deployment to the core WebLogic Server, but gets deployed and configured during the OBI 11g configuration. 

### WebLogic Node Manager













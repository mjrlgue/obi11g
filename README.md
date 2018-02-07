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






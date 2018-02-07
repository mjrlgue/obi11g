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




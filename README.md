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



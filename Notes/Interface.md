# INTERFACE : 
I have defined the interface in 3 ways.
1. Any service reqirement specification it consider as an interface.
   - Example - JDBC API access requirement specification to delevop database driver database vander is responsible JDBC API.
     ```mermaid
    graph TD
    A[JDBC API] --> B[Oracle Driver]
    A[JDBC API] --> C[MySQL Driver]
    A[JDBC API] --> D[DB2 Driver]

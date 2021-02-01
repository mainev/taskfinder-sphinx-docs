Data Source
===========
**Data Source** defines external sources used by Task Finder.

Database Connection
-------------------
Before you can access your database on Task Finder, you will have to add it first 
on the **Database Connection**. Task Finder supports two types of database:

* **MSSQL** (SQL Server) 
* **ORACLE**

System Queries
~~~~~~~~~~~~~~
**System Queries** are sql queries used by Task Finder to extract names of tables, stored procedures,
and columns used in the workflow. 

Change this only when the default queries below doesn't work on your database.

.. list-table:: MSSQL Default System Queries
   :widths: 40 60
   :header-rows: 1

   * - DB Data
     - SQL
   * - Columns and length
     -  ``SELECT COLUMN_NAME, CHARACTER_MAXIMUM_LENGTH FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME = @tableName ORDER BY COLUMN_NAME ASC``
   * - Tables
     -  ``SELECT NAME FROM SYS.TABLES``
   * - Stored Procedures
     -  ``SELECT NAME FROM SYS.PROCEDURES``

.. list-table:: Oracle Default System Queries
   :widths: 40 60
   :header-rows: 1

   * - DB Data
     - SQL
   * - Columns and length
     -  ``SELECT COLUMN_NAME, DATA_LENGTH, DATA_TYPE FROM all_tab_cols WHERE TABLE_NAME = :tableName and virtual_column = 'NO' ORDER BY COLUMN_NAME ASC``
   * - Tables
     -  ``select TABLE_NAME from tabs ORDER BY TABLE_NAME ASC``
   * - Stored Procedures
     -  ``select OBJECT_NAME from User_Procedures WHERE OBJECT_TYPE = 'PROCEDURE' ORDER BY OBJECT_NAME ASC``


SFTP Site
---------
The same with **Database Connection**, your **SFTP Site** will have to be registered here first before you
can use them in your workflow. Task Finder uses `WinSCP.NET <https://winscp.net/eng/docs/library>`_ assembly and COM library
to handle all SFTP operations.
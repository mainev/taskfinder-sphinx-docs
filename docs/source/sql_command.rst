SQL Command
===========
You can also schedule an sql command or query with Task Finder. Below command types are currently supported:

* **Select** - a simple select sql statement
* **Update/Delete** - a simple update or delete sql statement
* **Stored Procedure** - used to execute a stored procedure from the selected database connection

.. note::
    
    When doing a **Select** command and **Email Notification** as active, the result of the select statement will be generated in the email
    in tabular form. However, if the query returns more than 20 rows or 5 columns, the result will be converted to a csv attachment automatically.

Command Timeout
---------------
SQL Commands have a default command timeout of 30 seconds. If your sql execution time goes beyond the limit, the task will fail.
This is used to avoid running a query that is taking a long time to execute.

.. warning::

    It is possible to put zero (**0**) in the command timeout that will allow your sql to execute forever. 
    However, this is highly **NOT RECOMMENDED**.

Exports
-------
You can build an **export** or **report** with the **Select** or **Stored Procedure** command, provided the stored procedure
selected returns a result set. There are three file types supported for reports:

* **CSV**
* **TXT**
* **XLSX**

You can also put a custom delimiter on the report for a csv or txt file, including the quote character if you wish to have
your report columns enclosed in quotation mark. Below are additinal export settings:

* **Quote Always**
    With **Quote Always**, you can choose to quote values of typed **string** only, or all.

* **Export Filename**
    By default, the report generated will have the action description as the filename. You can change this on the **Export Filename** field.

* **Export Empty File**
    If active, will generate an empty file if no data is available from the database.

* **Attach Export to Email**
    Will send a copy of the report to workflow email notification recipients. Maximum of 5MB only.

For reports of xlsx type, you have additional options below:

* **Autofit** - will adjust column widths automatically on the report
* **Smart Format** - will adjust the cell data type based on the database data type

Using Variable as Filename
~~~~~~~~~~~~~~~~~~~~~~~~~~
If you wish to use data from your query as a filename, this is possible by assigning
the selected column with a variable syntax ``${VARIABLE_NAME}``.

.. code-block:: sql

        SELECT *,
        CONVERT(VARCHAR, GETDATE(), 102) AS '${REPORTDATE}'
        FROM FILE_TRANSFERRED

The **Export Filename** should be defined as below to use the variable.

.. code-block::

        ${REPORTDATE}_file_report

.. note::

    When using variable on the filename, Task Finder only selects the last value selected from the query.
    It implies that your variable must have a unique record for every row. Variables are also
    automatically hidden on the report.
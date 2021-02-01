Data Import
===========
**Data Import**, as the name it says, handles data import to a database. 
Task Finder currently supports two types of data sources:

* File
* Database 

Importing from a File
---------------------
When choosing **File** as a source type, you can choose the location of the file from a list of registered SFTP Sites 
(link to sftp site) or
a network share, or both. 

You can also put multiple file filters like the following:

* ``data`` - will select all files starting with **data** in filename
* ``*data`` - will select all files containing word **data** in filename
* ``data_${DATENOW}`` - using ``${DATENOW}`` as a system variable, will select all files starting with **data_{yyyyMMdd}** where date is the current date 

.. warning::
    On **File** source type, you should **NOT** include the file extension on the file filters field. 
    Task Finder only supports the following file types: CSV, TXT, and XLSX

**File has header** - will ignore the first row of the file.

**Delimiter** - is the character used on the file as a delimiter. 

**Skip Last Lines** - will ignore the last number of lines on the file.

**Include Subfolder** - will allow Task Finder to search for all subfolders on the remote or local path.

**Remove from Source** - by default, will always remove or delete the file from the source folder when doing a **Data Import**.

**Archive File** - by default, will always archive the file when doing a **Data Import**.

.. note::
    Task Finder can import values with comma even if the file uses comma (,) as a delimiter. However this only works if the value is enclosed in double-quotes.
    It will also ignore a row in the file containing only white spaces or no values at all.

Importing from a Database
-------------------------
Select the **Source DB Connection** where the data will be coming from. You can import from a database by using an **SQL** select query, or by executing a **Stored Procedure**. Task Finder
can display all available stored procedures with their required parameters.

.. note::
    When choosing **Stored Procedure**, it is imperative that the stored procedure returns a result set.

Data Import Destination
-----------------------
This contains the **Target DB Connection**, and all the available tables within.

Column Mapper
-------------
**Column Mapper** is used to connect the columns from a file/database to the destination database. It contains all the columns available on the 
choosen target or destination table. 

* **Target** - target columns of the destination table
* **Source** - source columns of the file or sql query
* **Default Value** - used to put a default value for file source type only
* **Max** - displays max length allowed of the target column (-1 if column data type is not a string)
* **Remove** - will remove the current mapping (if already mapped)
* **Advance** - contains other options of Column Mapper (see Advance section)

For a **File** source type, the source fields may not be available at first when opening the **Column Mapper**.
To get the source fields from a file, select the **Choose File** button found in the lower-left corner. You can only select the 
type of file you have choosen from **File Type** dropdown on the **Source Tab** of the **Data Import** action. The file that you
will chose here should contain the definitive headers you will use to map with the database columns.

For a **Database** source type, the Default value will be disabled since you can already put a default 
value from your source sql or stored procedure.

(add note here about command timeout)

Advance
~~~~~~~
**Column Mapper** supports the following data format useful for other applications:

* **Phone** - will convert your data into different standard formats (e.g. e164, national, rfc3966)
* **Phone Type** - will detect the type of phone if the data is a phone number (e.g. mobile, fixed_line, etc)
* **None** - no data format applied

When choosing **Phone** data format, you will be presented with the following options when the data provided is not a valid phone number:

* **Empty** - will insert the data as empty on the database
* **Ignore** - will ignore the format and use the provided data
* **Reject** - will reject the data, row will not be inserted on the database

**Validators** are just basic rules checked by **Column Mapper** described as the following:

* **Dedupe** - will reject duplicates of that column within the file or current selected sql only
* **Truncate** - if the source data exceeds the maximum length of the target column, it will remove excess characters from the data
* **Required** - first check only to reject the row if no data provided (database constraints will override this)

Invalid Columns
~~~~~~~~~~~~~~~
**Column Mapper** can detect if the column you have mapped is no longer available on the target table. 
A warning message will be displayed as below. When this happens, you will have to remove this mapping manually or 
add the missing columns again from the file or database table.

Other options
~~~~~~~~~~~~~
**Column Mapper** offers additional options below:

(put screenshot)

* **Reset** - to synchronize target columns from the target table on the database. Select this if you want to cancel all the changes you've made.

.. note::
    **Reset** will only return the columns to the previous state before you made any changes. You can also use this to update the Max field 
    if there has been any changes from the database side. 

* **Automap** - will automatically map the columns based on the source if they are the same or equal (case sensitive)



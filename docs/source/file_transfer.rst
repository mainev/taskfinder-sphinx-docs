File Transfer
=============
**File Transfer** is where we can transfer files from local to a remote location, or vice versa.

File Source
-----------
The **Source** defines the location of the file that you need to transfer. 

* **SFTP Site** - if you need to download a file from an SFTP Site
* **Remote Path** - remote path of the SFTP
* **Local Source Path** - local/network path of the file to be transferred
* **File Filters** - can accept multiple parameters, file extension is required here
* **Remove from Source** - will delete the file from the source location
* **Archive Source File** - will copy the file to the workflow archive directory
* **Include Subfolder** - will search for the files matching the filters to all subdirectories (nested)


.. _target_rename:

Rename File
-----------
The **Rename** tab when configured, will rename the file to your destination folder.
It is important to set the following fields to rename the files being transferred.

#. Source Filename Format
#. Output Filename Format
#. Delimiter

Source Filename Format
~~~~~~~~~~~~~~~~~~~~~~
Defines the format of the original file. Here you need to assign each filename segments with your own custom variable. (refer to variable syntax)
        
Example: 

.. code-block:: 
                    
        sitel_file_1234.csv

Source Filename Format: 

.. code-block:: 
                    
        ${PREFIX}_${MYPARAM2}_${FILEID}

Output Filename Format
~~~~~~~~~~~~~~~~~~~~~~
This is where you will define how your new filename will look like. You can add new strings
or remove some filename segments.

Below output format will add a new prefix "FILE1" to the file.

.. code-block::

        FILE1_${PREFIX}_${MYPARAM2}_${FILEID}

Renamed File

.. code-block::

        FILE1_sitel_file_1234.csv


Delimiter
~~~~~~~~~
Delimiter characters used to identify your filename segments. You are allowed to put multiple characters here.

Below example will create segments of the filename parsed by hypen "-" or underscore "_".

Delimiter

.. code-block::

        -_

Source File

.. code-block::

        2021-01-29_sitel_file_1234.csv

.. _target_rename_delimiter:

Source Format

.. code-block::

        ${YEAR}-${MONTH}-${DAY}_${PARAM1}_${PARAM2}_${FILEID}



Renaming from a Database
~~~~~~~~~~~~~~~~~~~~~~~~
If you need to get the new filename from a database, you will have to select the database connection together with the command 
type.

.. code-block:: sql

        SELECT NEWFILENAME FROM FILE_LIST WHERE FILE_ID = '${FILEID}'

You can use here the variables you created from the **Source Format**. You can use the ``NEWFILENAME`` column to the output format as below:

.. code-block:: 

        ${NEWFILENAME}_${PREFIX}_${MYPARAM2}

.. note::

    It is recommended to create your variables with **Unique** names and in **UPPERCASE**.


File Executable
---------------
If you need to run another program with the file, such as conversion, encryption, etc.,
you can do this on the **Executable** tab within the **File Transfer** action.

Interface is the same with the basic :doc:`executable` action type. 
However you will need to provide the expected **Output File Extension**.
This helps Task Finder to identify which file will be transferred in case of conversion.


File Destination
----------------
The **File Destination** tab contains all configuration where the file will be downloaded or transferred.

* **Use Workflow Folder as Destination Folder**
    All files will be kept temporarily on the workflow folder until
    all actions in the workflow has been completed.

* **Include Subfolder in Destination**
    If your source files are located within nested subfolders, and you need to keep the same
    folder hierarchy on the destination folder, then you need to enable this.

* **Archive Output File**
    This will keep the final output of the file on the workflow archive folder. Useful 
    when doing conversion, compression, encryption, and other file operations.

Using Dynamic Folder
--------------------
Other tasks requires to create a new folder everytime your task runs. This new folder could be 
the current date or other reference to keep track of the files. This is possible in Task Finder
by adding a variable syntax on the local or remote destination folder.

Below example will create a new folder of the current date every time the task run.
Default ``${DATENOW}`` format is ``yyyyMMdd``. (add reference to system variables here)

.. code-block::

    \\eu999k16tsks02\shared\${DATENOW}

Below example will create a new folder depending on the value retrieved from the database or
filename segments during :ref:`File Rename <target_rename_delimiter>`.

.. code-block::

    \\eu999k16tsks02\shared\${YEAR}\${MONTH}\${DAY}

Sending File over Email
-----------------------
Task Finder can send a copy of the file with a maximum of 5 mb only. 

**Batch Attachment** - if active, will group all the files in one email. Otherwise, the system will send one email for each file.
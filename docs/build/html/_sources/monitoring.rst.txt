Monitoring
==========

The **Monitoring** page allows you to view recent file activity and system logs by 
Task Finder.

File Transactions
-----------------
This page shows all files transferred by Task Finder. This contains the following details:

.. list-table::
   :widths: 40 60
   :header-rows: 1

   * - Detail
     - Description
   * - Transaction Date
     -  date when the file was transferred
   * - Orig Filename
     - the original filename of the file from the source
   * - Orig Location
     - the original source of the file, could be local, network or remote
   * - Orig Filesize (bytes)
     - the original size of the file
   * - New Filename
     - the new and final name of the file (in case the file was renamed)
   * - New Location
     - the destination where the file was downloaded or copied
   * - New Filesize (bytes)
     - the final size of the file (in case the file was compressed)
   * - Error / Status
     - 0 if no error, 1 if there's an error

Trace Logs
~~~~~~~~~~
**Trace Logs** provides you more details of other operations on the file.
This includes the date and time of the operation, duration, and additional message or logs
for debugging in case of issues. You can double-click on the file transaction row to view the
trace logs automatically.

Event Logs
----------
**Event Logs** are also additional logs stored in database to help for debugging. The logs recorded here are only
on minimum level of **Warning** and above (**Error**, **Fatal**).

.. note::

    Database-stored logs are only available for 15 days.
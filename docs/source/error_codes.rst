Error Codes
===========

Below are list of error codes to help in debugging:

.. list-table::
   :widths: 40 50 10
   :header-rows: 1

   * - Code
     - Description
     - System
   * - ATTACHED_TO_EMAIL_FAILED
     -  happens when the file transferred failed as attachment email, common causes
        would be the file size is above 5 MB
     - 
   * - CX_EMAIL_ATTACHMENT_REMOVED
     - attachment failed due to misconfiguration on the workflow
     - 
   * - DBX_CONVERT_TO_DATASOURCE
     - invalid query during data import with database source type
     - 
   * - DBX_INSERT
     - failed database insert operation on data import
     - YES
   * - DBX_SELECT
     - failed database select operation on export/report generation
     - YES
   * - DBX_STOREDPROC
     - failed database stored procedure operation
     - YES
   * - DBX_UNHANDLED
     - other unknown issue on database operation
     - YES
   * - DBX_UPDATE
     - failed database update operation
     - YES
   * - EXE_FAILED
     - failed to run executable action
     - YES
   * - EXP_GEN_TXT
     - failed to generate csv/text file for export/report
     - YES
   * - EXP_GEN_XLSX
     - failed to generate excel file (.xlsx) file for export/report
     - YES
   * - FTX_ARCHIVE
     - failed to archive file
     - YES
   * - FTX_COPY_TO_TARGET_DIR
     - failed to copy the file to target or destination directory
     - YES
   * - FTX_COPY_TO_TEMP
     - failed to copy the file to workflow's temporary directory
     - YES
   * - FTX_EXE_FAILED
     - failed to run executable on a file
     - YES
   * - FTX_FILE_TOO_LARGE
     - failed to attach file as email attachment due to 5 MB limit
     - YES
   * - FTX_RENAME_FILENAME_NOT_FOUND_IN_DB
     - failed to rename file when using database
     - 
   * - FTX_SFTP_DOWNLOAD
     - failed to download file from sftp
     - YES
   * - FTX_SFTP_UPLOAD
     - failed to upload file to sftp
     - YES
   * - FTX_UNHANDLED
     - unknown error during sftp operation
     - YES
   * - ICX
     - general error caused by invalid error or misconfiguration on the workflow
     - 
   * - ICX_INCORRECT_MAPPING
     - specific error caused by invalid mapping of fields
     - 
   * - SYSX_COMPRESS_FILE
     - system error when auto-compress failed on workflow archive
     - YES
   * - SYSX_EMAIL_SEND_FAILED
     - system error when sending email failed
     - YES
   * - SYSX_UNHANDLED
     - unhandled system error
     - YES
Workflow
=================
A workflow is a step-by-step definition of a task or procedure. It can contain
multiple actions depending on how you want your task to be automated.

General Details
---------------
The **General** tab contains all basic information needed to create a workflow.
(put screenshot here)

When creating your first workflow, the **Use Default Workflow Folder** will be checked as default.
A workflow folder contains all the logs, archives, and error details of your task.
When checked, this means Task Finder will create a new folder for every workflow we created on the system's default directory. 
(provide link here discussing system default workflow directory).
If this option is unchecked, you will have to provide your own share or directory accessible by the tool.


Email Notifications
-------------------
Task Finder will send an auto-generated email everytime your task has been completed. This can be disabled on the
**Email Notification** tab. 

If you want Task Finder to send an email only when it detects new data or file, then below checkbox 
will have to be checked. (put screenshot here)


Email Groups
~~~~~~~~~~~~
On **Email Groups**, you can group email recipients who will receive the task notification. 
We have 3 types of alerts: **Basic**, **All**, **Error**

* Basic - will receive basic alerts (may contain error only caused by incorrect data or configuration).
* All - will receive all alerts, be it a simple error or a system error.
* Error - will receive alerts only when there is an error.

Content Settings
~~~~~~~~~~~~~~~~
You can control which section of the notification will be included in the email.

(put screenshot)

Workflow Groups
---------------
**Workflow Groups** are just a way to group your workflows. You can use this to filter your workflows or jobs
when working on multiple workflows.


Actions
-------
Once we created the workflow, the **Actions** tab will then be accessible.

An **Action** is a built-in process of Task Finder to simplify common task such as the following:

* Data Import
* Run Executable
* File Transfer
* SQL Command

Next topic will discuss all types of action the Task Finder currently supports.
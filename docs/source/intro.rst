Introduction
============
Task Finder is a web-based tool that can be used to automate a simple task.
It can handle different tasks such as data imports, exports, remote/local file transfers, or even run other executables.
This tool is built to simplify and centrallized task automation and maintenance.

Task Finder is a .NET Core application with Angular Framework as the frontend. The user management is controlled within the IdentityServer4
(not part of this documentation).

User Interface
--------------
Task Finder has uniform template for every menu. To use the tool, it will be helpful 
to familiarize yourself on how you can interact with the tool.


Table Selection
~~~~~~~~~~~~~~~
On each menu, you will be presented with a main table on the main page. You can do multiple interactions with this page 
such as search, display columns, refresh and quick view.

(put screenshot of main list)

When the **Quick View** is selected, it will display small details on the row you selected.

(put screenshot)

You can do additional actions on each row with the options button (put screenshot).
You may also double-click on a row to open an auto-edit dialog.

Variable Syntax
~~~~~~~~~~~~~~~
At some point in your workflow, you will have to define your custom variable to support your task.
The variable syntax used by Task Finder is ``${VARIABLE_NAME}``



Terminology
-----------
Below are keywords and terms that you should be aware of when using Task Finder.

.. list-table::
   :widths: 40 60
   :header-rows: 1

   * - Keyword
     - Description
   * - System Variable
     -  information provided by the system. Each system variable differs for every workflow
        and every jobs.
   * - Filename Segments
     - 
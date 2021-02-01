Job
===
Task Finder is integrated with `Hangfire <https://www.hangfire.io/>`_ that handles
background processing jobs. On the job's main page, the **Next Run** column displays the 
date and time of the next run in the user's current timezone.

A job can contain multiple workflows and gets executed sequentially. 

(screenshot of multiple workflows)

You can also set the timezone of your job depending on your preference. 
Task Finder uses cron syntax for the scheduler which gets passed on 
to Hangfire internally. Click `CRON <https://crontab.guru/>`_ for some additional information online. 

Below are the
definitions of each scheduler types:

* **Predefined Schedule** - auto-generated cron syntax. This is a collection of common schedules.
* **Advance Cron** - If none of the **Predefined Schedule** meet your needs, you can compose your own cron schedule here.

.. note::

    All jobs run on one instance only. This means if your job is still running from the previous trigger,
    the next trigger will be ignored. 

Advance Settings
----------------
Advance settings contains the number of threads you wish to
use for your job. Multithreading is only applied with :doc:`data_import` and :doc:`file_transfer`.

.. note::
    The performance of data imports and file transfers will still depend on the hosted server's resources
    and network speed. Make sure your code or process is thread-safe to use multithreading, otherwise leave this to default 1.
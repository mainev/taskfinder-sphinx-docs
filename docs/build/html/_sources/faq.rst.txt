FAQ
===

#. How can I add users on the tool so they can access it?
    Right now user management is controlled internally. Please refer to the
    :doc:`support` if you need additional user access.
#. Can I run a batch file on Task Finder?
    Yes, though you need to select **Command Prompt** as your program and pass the batch file
    as an argument.
#. Can I stop or cancel a running job on Task Finder?
    You cannot stop the job on Task Finder's interface. The only way to stop the job
    is to stop the application pool on IIS within the hosted server. Note that this will stop 
    all jobs that are currently running.
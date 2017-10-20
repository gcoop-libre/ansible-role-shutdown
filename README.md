Shutdown
========

Shutdown or reboot a host.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    shutdown_cancel: False

Cancel a pending shutdown. This may be used cancel the effect of an invocation of shutdown with a time argument that is not "+0" or "now".

    shutdown_reboot: False

Reboot the host instead of powering off.

    shutdown_halt: False

Halt the host instead of powering off.

    shutdown_timeout: 0

Number of minutes from now to shutdown the host.

    shutdown_time: ''

Time string in the format "hh:mm" for hour/minutes specifying the time to execute the shutdown at, specified in 24h clock format. 

    shutdown_message: ''

Message to send to logged users notifying about the shutdown operation.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
         - gcoop-libre.shutdown

*Inside `vars/main.yml`*:

    shutdown_reboot: True
    shutdown_timeout: 5
    shutdown_message: Rebooting the host for maintenance

License
-------

GPLv2

Author Information
------------------

This role was created in 2017 by [gcoop Cooperativa de Software Libre](https://www.gcoop.coop).

ansible-linux-pkg
=========

To help manage linux packages across platforms (Ubunutu apt or CentOS yum). This also has the capability to perform all package upgrades and reboot if you deem as OK.

Requirements
------------

* SSH with passwordless sudo (makes life easier)
*

Role Variables
--------------

Variable | Type | Expected Value | Default | Notes |
---------|------|---------|---------|-------|
allow_reboot | boolean | true \| false |  false |
pkg_list | list | * for all package upgrades or list a specific package(s) | * | Defaults to updating all packages

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: true
      roles:
         - { role: "ansible-linux-pkg", allow_reboot: true, pkg_list: [ "yumutils", "apache2", "nginix" ] }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

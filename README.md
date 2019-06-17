ansible-linux-pkg
=========

To help manage linux packages across platforms (Ubunutu apt or CentOS yum). This also has the capability to perform all package upgrades and reboot if you deem as OK.

Requirements
------------

* SSH with passwordless sudo (makes life easier)
* Target nodes use a package manager (i.e. yum or apt) and have repos configured

Role Variables
--------------

Variable | Type | Expected Value | Default | Notes |
---------|------|---------|---------|-------|
allow_reboot | boolean | true \| false |  false |
all_list | list | * for all package upgrades or list a specific package(s) | * | Defaults to updating all packages
rpm_list | list | List of packages for Red Hat based distro | none | Use this variable to only affect RH based systems
apt_list | list | List of packages for Ubuntu based distro | none | Use this variable to only affect Ubuntu based systems
pkg_state | string | latest \| abset | latest |

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: true
      roles:
         - { role: "ansible-linux-pkg", allow_reboot: true, all_list: [ "apache2", "nginix" ] }

License
-------

BSD

Author Information
------------------

Brent Weaver   
June 2019

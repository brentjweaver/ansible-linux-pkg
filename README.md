ansible-linux-pkg
=========

To help manage linux packages across platforms (Ubunutu apt or CentOS yum). This also has the capability to perform all package upgrades and reboot if you deem as OK.

Requirements
------------

* SSH with passwordless sudo (makes life easier)
* Target nodes have repos configured to retrieve requetsed packages


Role Variables
--------------

Variable | Type | Expected Value | Default | Notes |
---------|------|---------|---------|-------|
```allow_reboot``` | boolean | true \| false |  false |  This will allow a system reboot if a package install requires one
```update``` | boolean | true \| false | false | This option will update all packages and reboot if you allow with the above allow_reboot option
```pkg``` | list | List of packages suitable for all distros | none |
```rpm_pkg``` | list | List of packages for Red Hat based distro | none | Use this variable to only affect RH based systems
```apt_pkg``` | list | List of packages for Ubuntu based distro | none | Use this variable to only affect Ubuntu based systems
```pkg_state``` | string | latest \| abset | latest | only applicable when mode is install

Dependencies
------------

Python
SSH Access to target nodes

Example Playbook
----------------

Example installing apache2 and nginx, and reboot if required:

```    - hosts: servers
      become: true
      roles:
         - { role: "ansible-linux-pkg", allow_reboot: true, pkg: [ "apache2", "nginix" ] }
```

To update all packages and allow a reboot:

```  - hosts: servers
      become: true
      roles:
         - { role: "ansible-linux-pkg", allow_reboot: true, udate: true }
```

License
-------

BSD

Author Information
------------------

Brent Weaver   
June 2019

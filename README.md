ansible-role-ferm-tor
=====

This role configures [ferm](http://ferm.foo-projects.org/) to send outgoing traffic to the Internet through [Tor]((https://www.torproject.org/)) in a similar way as [Tails](https://git-tails.immerda.ch/tails/plain/config/chroot_local-includes/etc/ferm/ferm.conf) does. 
This role has only been tested in Debian.

Requirements
------------

This role requires Ansible 1.6 or higher.


Role Variables
--------------

All these variables are defined in vars/main.yml and will be used by default.

    ## set to true if the host where the role is running is configured to block
    ## all outbound traffic except tor
    usetor: true

Dependencies
------------

The following roles are needed:
* ansible-role-tor-basic
* ansible-role-ferm-basic

It's not needed to setup any arguments.

Example Playbook
----------

```
- hosts: localhost

  roles:

    - { role: ansible-role-tor-basic
      }
    - { role: ansible-role-ferm-basic
      }
    - { role: ansible-role-ferm-tor
      }
      }
```

License
-------

GPLv3

Author Information
------------------

Lee Woboo


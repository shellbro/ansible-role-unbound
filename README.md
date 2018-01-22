unbound
=======

[![Build Status](https://travis-ci.org/shellbro/ansible-role-unbound.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-unbound)

Ansible role that sets up unbound caching nameserver on CentOS 7.

Requirements
------------

Ansible version >= 2.3.

Role Variables
--------------

* interfaces - network interfaces to listen on, if not defined the default is to listen to localhost (127.0.0.1 and ::1)
* access_control - control which clients are allowed to make quries to this server, if not defined everything is refused, except for localhost

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.unbound
          interfaces:
            - 0.0.0.0
          access_control:
            - 0.0.0.0/0 allow

License
-------

BSD

Author Information
------------------

Jakub Gorczyca

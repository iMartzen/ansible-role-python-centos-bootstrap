Ansible Role: Install Python on newly bootstrapped Ubuntu server
=========

**Install Python on newly bootstrapped Ubuntu server**

This Ansible role will install Python on newly bootstrapped host. This is usually
a new host which you never even SSH-ed to.

In order for Ansible to work, Python must be installed (if missing).

Requirements
------------

None.

Role Variables
--------------

None.


Dependencies
------------

None.

Example Playbook
----------------

```
# run as part of pre_tasks
- hosts: servers
  remote_user: ubuntu
  become: yes
  gather_facts: no
  serial: 1

  roles:
    - { role: AdnanHodzic.python-ubuntu-bootstrap }

- hosts: servers
  remote_user: ubuntu
  gather_facts: yes
  become: yes

# run as part of tasks
  roles:
    ...
```

License
-------

GPLv3

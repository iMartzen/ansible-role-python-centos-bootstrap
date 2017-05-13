Ansible Role: Install Python on newly bootstrapped Ubuntu host
=========

**Install Python on newly bootstrapped Ubuntu host**

This Ansible role will install Python on newly bootstrapped host. This is usually
a new host which you never even SSH-ed to.

In order for Ansible to work, Python must be installed (if missing).

Requirements
------------

None.

Role Variables
--------------

Unless you don't want `gather_facts: yes` to be set and enabled as second part of the playbook. 
Make sure to comment/delete following line from `tasks/main.yml`

```- setup: # aka gather_facts: yes```

See [Example Playbook](https://github.com/AdnanHodzic/ansible-role-python-ubuntu-bootstrap#example-playbook) section for more information


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
  become: yes

# run as part of tasks
  roles:
    ...
```

License
-------

GPLv3

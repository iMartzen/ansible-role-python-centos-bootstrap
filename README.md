Ansible Role: Install Python on newly bootstrapped CentOS/RedHat host
=========

**Install Python on newly bootstrapped CentOS/RedHat host**

This Ansible role will install Python on newly bootstrapped host. This is usually a new host which you never even SSH-ed to. In order for Ansible to work, Python must be installed (if missing).

This role was created as part of [containerized-wordpress-project](https://github.com/AdnanHodzic/containerized-wordpress-project)

Requirements
------------

None.

Role Variables
--------------

Unless you don't want `gather_facts: yes` to be set and enabled as second part of the playbook. 
Make sure to comment/delete following line from `tasks/main.yml`

```- setup: # aka gather_facts: yes```

Dependencies
------------

None.

Example Playbook

This role was created to be run as part of pre_tasks, i.e:
----------------

```
# run as part of pre_tasks
- hosts: servers
  remote_user: centos
  become: yes
  gather_facts: no
  serial: 1

  roles:
    - { role: centos-python-bootstrap }

- hosts: servers
  remote_user: centos
  become: yes

# run as part of tasks
  roles:
    ...
```

License
-------

GPLv3

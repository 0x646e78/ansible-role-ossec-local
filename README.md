ansible-role-ossec-local
=========================

Ansible role to install and configure an OSSEC HIDS local install

Use
---

You can clone this repo directly into your ansible playbook by issuing

```
git clone https://github.com/auraltension/ansible-role-ossec-local.git roles/ossec-server
```

or alternatively as a submodule in much the same way

```
git submodule add https://github.com/auraltension/ansible-role-ossec-local.git roles/ossec-local
```

You will need to set up variables for _admin_email_addresses_.  I choose to put these in group_vars, such as

```
admin_email_addresses:
  - admin@example.com
  - admin2@example.com
```


You can then include this role as part of a playbook such as:

```
---
- hosts: my_server
  roles:
    - webserver
    - ossec-local
```

Credits
-------

Originally forked from roles in Aaron Hunter's CentOS management playbook at https://github.com/aaron868/management

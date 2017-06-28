ansible-role-ossec-local
=========================
Fork of unmaintained repo for OSSEC HIDS local install
Ansible role to install and configure an OSSEC HIDS local install

Use
---

```
git clone https://github.com/johnsiciliano/ansible-role-ossec-local.git roles/ossec-server
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

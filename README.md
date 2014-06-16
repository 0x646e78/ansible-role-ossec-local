ansible-role-ossec-server
=========================

Ansible role to install and configure an OSSEC IDS Server

Use
---

You can clone this repo directly into your ansible playbook by issuing

```
git clone https://github.com/auraltension/ansible-role-ossec-server.git roles/ossec-server
```

or alternatively as a submodule in much the same way

```
git submodule add https://github.com/auraltension/ansible-role-ossec-server.git roles/ossec-server
```

You will need to set up variables for _admin_email_addresses_.  I choose to put these in group_vars, such as

```
admin_email_addresses:
  - admin@mail.com
  - admin2@mail.com
```

[ossec-authd](http://ossec-docs.readthedocs.org/en/latest/programs/ossec-authd.html) is utilised to add agents to the server, and requires SSL keys to be pre-generated.

The ansible role will look for the key/cert pair in the _files_ directory. The private key must be named _ossec.key_ and the public certificate _ossec.cert_

To generate the keys:

```
cd roles/ossec-server
openssl genrsa -out files/ossec.key 2048
openssl req -new -x509 -key files/ossec.key -out files/ossec.cert -days 365
```

You can then include this role as part of a playbook such as:

```
---
- hosts: my_server
  roles:
    - webserver
    - ossec-server
```

Credits
-------

Originally forked from roles in Aaron Hunter's CentOS management playbook at https://github.com/aaron868/management

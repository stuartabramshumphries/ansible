Role Name
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

Change properties of sshd in client.

Description
-----------

The sshd role reconfigures the server install of a the provisioning client. You only need to change the values for the properties you wish to change on `defaults/main.yml`.

Role Variables
--------------

The variables you need to change are in `defaults/main.yml`. You should use the listed defaults to figure what you want to change. The names are self explanatory.

``` yaml
sshd:
  port: 22
  groups: ssh
  pubkey: yes
  rsa:  yes
  passwd: no
  empty: no

```


Requirements
------------

Needs **ssh** server installed. If you using ansible, can't see how you don't have it...

Usage
-----

Only need to add **sshd** role to your playbook and you are good to go. *DO NOTE*, when you run the role, it WILL change the access to the provisioning client. As such, you should run this role either as the last role on your playbook.

``` yaml
- hosts: servers
    roles:
        - sshd
```

Author Information
------------------

[Alejandro Baez][1]

[1]: https://keybase.io/baez
[2i]: https://img.shields.io/badge/license-BSD_2-green.svg
[2p]: ./LICENSE
[3i]: https://img.shields.io/badge/twitter-a_baez-blue.svg
[3p]: https://twitter.com/a_baez

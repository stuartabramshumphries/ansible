ansible-role-crontab
====================
[![Build Status](https://travis-ci.org/uZer/ansible-role-crontab.svg?branch=master)](https://travis-ci.org/uZer/ansible-role-crontab)

* This role configures crontab an removes crons/vars when they are not in ansible

* All variables should be configured in `host_vars` or `group_vars`.

* The file `/etc/cron.d/ansible_cron` is used by default for crontabs and vars.

* Please note that deletion is only managed when `file: ...` is not specified.
If you plan to put your crontabs in various files, this role doesn't have much
utility for you since deletion tasks won't parse your file. You should fallback
to a _classic_ galaxy role in that case.

Dependencies
------------
None. Should work on any linux distribution

Light usage example
-------------

```yaml
crontabs:
  jobs:
    - name: "Test job 1"
      job: "echo $TESTVAR1 > /tmp/testcron"
```

Exhaustive usage example
------------------------

```yaml
crontabs:
  vars:
    - name: "TESTVAR1"
      value: "test VALUE 2"
      user: "weirdo"
      # file: /etc/cron.d/other_cron ## Should not be used
    - ...
  jobs:
    - name: "Test job 1"
      job: "echo $TESTVAR1 > /tmp/testcron"
      minute: "0"
      hour: "2"
      day: "*"
      month: "*"
      weekday: "*"
      user: "weirdo"
    - ...
```

License
-------
"THE (extended) BEER-WARE LICENSE" (Revision 42.0815):

As long as you retain this notice you can do whatever you want with this stuff.
If we meet some day, and you think this stuff is worth it, you can buy me some
beers in return.


Author Information
------------------
Youenn Piolet

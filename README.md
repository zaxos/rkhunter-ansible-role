[![Build Status](https://travis-ci.org/zaxos/rkhunter-ansible-role.svg?branch=master)](https://travis-ci.org/zaxos/rkhunter-ansible-role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-_zaxos.rkhunter--ansible--role-blue.svg)](https://galaxy.ansible.com/zaxos/rkhunter-ansible-role/)

rkhunter-ansible-role
=====================

Ansible role to install and configure Rootkit Hunter.

Requirements
------------
* OS support list:
  * CentOS/RHEL 7 and 8
  * Debian Stretch and Buster
  * Fedora 33
* ansible >= 2.0

Installation
------------
```
$ ansible-galaxy install zaxos.rkhunter-ansible-role
```

Example Playbook
----------------
```yaml
    - hosts: servers
      roles:
        - role: zaxos.rkhunter-ansible-role
```

Role Variables
--------------
Some variables that require review:
- `rkhunter_report_mail_address`: "root@localhost"
- `rkhunter_diag_scan`: "no"
Set this variable to "no" in order to perform normal report scan or to "yes" in order to
perform detailed report scan (including application check)
- `rkhunter_allow_ssh_protocol_v1`: 2
A value of '0' indicates that the use of SSH-1 is not allowed. Set this option to '1' to
allow the use of the SSH-1 protocol. If the 'Protocol' option has not been set in the
SSH configuration file, then a value of '2' may be set here in order to suppress
a warning message (which is the case in most modern distributions).
- `rkhunter_allow_ssh_root_login`: "prohibit-password"
The following option is checked against the SSH configuration file 'PermitRootLogin'
option. A warning will be displayed if they do not match. However, if a value has not
been set in the SSH configuration file, then a value here of 'unset' can be used to
avoid warning messages.

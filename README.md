control-sudoers
=========

Controls settings in an existing sudoers file without destroying/overwriting other existing state. Only handles a couple of configuration options right now but will likely be expanded later.

[![Build Status](https://travis-ci.org/CyVerse-Ansible/ansible-control-sudoers.svg?branch=master)](https://travis-ci.org/CyVerse-Ansible/ansible-control-sudoers)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-control--sudoers-blue.svg)](https://galaxy.ansible.com/CyVerse-Ansible/ansible-control-sudoers/)

See also https://galaxy.ansible.com/detail#/role/4827. As of September 2016, more configuration options than this role, but doesn't claim compatibility with RHEL-derived distros.

Requirements
------------

Ansible 2.X

Role Variables
--------------

If you don't wish for a particular setting to be modified, then don't define its variable.

| Variable                | Required | Default | Choices                   | Comments                                                          |
|-------------------------|----------|---------|---------------------------|-------------------------------------------------------------------|
| sudoers_mailto          | no       | false   | false or an email address | any email address will set mailto default, "false" removes an existing email address |
| sudoers_mail_always     | no       | false   | false, true               | true sets mail_always, false unsets mail_always                   |

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      vars:
        sudoers_mailto: security@example.com
        sudoers_mail_always: false
      roles:
         - control-sudoers

License
-------

BSD

Author Information
------------------

Chris Martin (github.com/c-mart)

control-sudoers
=========

Controls settings in an existing sudoers file without destroying/overwriting other existing state. Only handles a couple of configuration options right now but will likely be expanded later.

!(https://travis-ci.org/CyVerse-Ansible/ansible-control-sudoers.svg?branch=master)

Requirements
------------

Ansible 2.X

Role Variables
--------------

Each controllable setting has a corresponding set_ variable. This tells the role whether to enforce the setting or leave it alone.

| Variable                | Required | Default | Choices                   | Comments                                                          |
|-------------------------|----------|---------|---------------------------|-------------------------------------------------------------------|
| sudoers_mailto          | no       | false   | false or an email address | any email address will set mailto default, "false" will un-set it |
| set_sudoers_mailto      | no       | false   | false, true               |                                                                   |
| sudoers_mail_always     | no       | false   | false, true               | true sets mail_always, false unsets mail_always                   |
| set_sudoers_mail_always | no       | false   | false, true               |                                                                   |

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      vars:
        sudoers_mailto: security@example.com
        set_sudoers_mailto: false
        sudoers_mail_always: false
        set_sudoers_mail_always: true
      roles:
         - control-sudoers

License
-------

BSD

Author Information
------------------

Chris Martin (github.com/c-mart)

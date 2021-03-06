Ansible Role: AutoKey
=========

[![Build Status](https://travis-ci.org/patrick-hill/ansible-role-autokey.svg?branch=master)](https://travis-ci.org/patrick-hill/ansible-role-autokey)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-patrick--hill.autokey-blue.svg)](https://galaxy.ansible.com/patrick-hill/autokey)


Installs [AutoKey](https://code.google.com/archive/p/autokey/) on Debian based OS and allows using a backup and/or symlinking to a backup dir.

Requirements
------------

Ansible 2.0+

Role Variables
--------------

The below are defined in vars and defaults: `vars/main.yml and defaults/main.yml`:

    autokey_backup_restore
"autokey_backup_restore" allows you to restore a backup of the configs/phrases
Pathing assumes you use a common backup dir <root>/configs/autokey

    autokey_backup_symlink
"autokey_backup_symlink" allows you to symlink your backup dir to AutoKey's config dir
    
    autokey_config_dir
"autokey_config_dir" is the default path for AutoKeys config directory which defaults to: /home/$USER/.config/autokey

    autokey_backup_dir
"autokey_backup_dir" is the dir path to the backup dir holding the autokey backup configs.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: development-machines
      vars:
        os_username: 'Your_OS_Username'
      roles:
        - { role: patrick-hill.autokey}

*Inside `vars/main.yml`*:

    autokey_backup_restore: false
    autokey_backup_symlink: false

License
-------

MIT / BSD

Author Information
------------------

Role written in 2016 by [Patrick Hill](http://www.HillsPCWorld.com) 
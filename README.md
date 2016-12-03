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

    autokey_use_backup
"autokey_use_backup" allows you to restore a backup of the configs/phrases
Pathing assumes you use a common backup dir <root>/configs/autokey

    autokey_symlink_backup
"autokey_symlink_backup" allows you to symlink your backup dir to AutoKey's config dir
    
    os_username
"os_username" is used to build the path for autokey's config dir. This value should be the target users username.
If you're using non standard pathing, this var will NOT be needed but be sure to provide a full path for autokey_config_dir

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
      roles:
        - { role: patrick-hill.autokey}

*Inside `vars/main.yml`*:

    autokey_use_backup: true
    autokey_symlink_backup: false
    os_username: 'phill'

License
-------

MIT / BSD

Author Information
------------------

Role written in 2016 by [Patrick Hill](http://www.HillsPCWorld.com) 
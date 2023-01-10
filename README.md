Ansible Role: Jetbrains
==================

Ansible role to install Jetbrains IDEs on Linux. The role downloads, verifies,
installs the selected IDE and creates a desktop launcher for it. There
are two possible installation modes:

1. system
2. user

| Installation mode | Application files | Application launcher
|-------------------|-------------------|---------------------
| system | /opt/{{ jetbrains_ide }} | /usr/local/share/applications/{{ jetbrains_ide }}.desktop
| user | ~/.local/share/opt/{{ jetbrains_ide }} | ~/.local/share/applications/{{ jetbrains_ide }}.desktop

Role Variables
--------------

| Variable | Use | Default value
|-------------|-------|---------------------
jetbrains_ide | The list of IDEs to install (list of supported ones will be updated) | []
jetbrains_ide_local_download_dir | Directory where the tarball should be downloaded on the __control__ node | /tmp
jetbrains_ide_installation_mode  | Installation mode: system vs user | user

Dependencies
------------
python3-jmespath

Example Playbook
----------------

User-level installation of latest version of Pycharm Community Edition and version 2022.3.1 of PhpStorm:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          vars:
            jetbrains_ide:
              - name: phpstorm
                version: '2022.3.1'
              - pycharm-community

License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile

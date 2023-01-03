Ansible Role: Jetbrains
==================

Ansible role to install Jetbrains IDEs on Linux. The role downloads, verifies,
installs the selected IDE and creates a desktop launcher for it. There
are two possible installation modes:

1. system
2. user

| Installation mode | Application files | Application launcher
|-------------------|-------------------|---------------------
| system | /opt/{{ ide }} | /usr/local/share/applications/{{ ide }}.desktop
| user | ~/.local/share/opt/{{ ide }} | ~/.local/share/applications/{{ ide }}.desktop

Role Variables
--------------

| Variable | Use | Default value
|-------------|-------|---------------------
ide | The IDE to install (list of supported ones will be updated) | pycharm-community
ide_version | The IDE version to install | latest
ide_local_download_dir | Directory where the tarball should be downloaded on the __control__ node | /tmp
ide_installation_mode  | Installation mode: system vs user | user

Dependencies
------------
python3-jmespath

Example Playbook
----------------

System-level installation of PhpStorm:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          ide_installation_mode: system
          ide: phpstorm
          become: true

User-level installation:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          ide: phpstorm


License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile

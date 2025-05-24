Ansible Role: Jetbrains
==================

Ansible role to install Jetbrains IDEs on Linux. The role downloads, verifies,
and installs the selected IDE. It also creates desktop launchers.

Role Variables
--------------
        jetbrains_ide_code

The code of the Jetbrains IDE you want to download and install

        jetbrains_ide_version

The version of the Jetbrains IDE you want to download and install (e.g: 2023.3.1)

        jetbrains_local_download_dir: /tmp

The directory on the control node where to download the IDE tarball

        jetbrains_installation_dir: /opt/jetbrains

The root installation directory

        jetbrains_products_url: https://data.services.jetbrains.com/products

The URL used to retrieve information about the IDE

        jetbrains_launcher_dir: /usr/local/share/applications

The directory where IDE launcher will be created

        jetbrains_binary_dir: /usr/local/bin

The directory where links to the IDE executable will be created

        jetbrains_user: root

The user who will own IDE files and directories

        jetbrains_link_executable: false

Whether to create a link to the IDE executable under `jetbrains_binary_dir`

Dependencies
------------
None

Example Playbook
----------------

Install version 2022.3.1 of PhpStorm:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          jetbrains_ide_code: PS
          jetbrains_ide_version: 2022.3.1

License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile

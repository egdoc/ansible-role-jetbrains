Ansible Role: Jetbrains
==================

Ansible role to install Jetbrains IDEs on Linux. The role downloads, verifies,
and installs the selected IDEs. It also creates desktop launchers.

Role Variables
--------------

        jetbrains_ide: []

The list of dictionaries describing IDEs and versions to install (see example)

        jetbrains_installation_dir: /opt/jetbrains

The root installation directory

        jetbrains_remove_other_versions: true

Controls whether previously installed IDE versions are removed after installation

        jetbrains_releases_url: https://data.services.jetbrains.com/products/releases

The URL used to retrieve information about IDEs

        jetbrains_launcher_dir: /usr/local/share/applications

The directory where IDEs launchers will be created

        jetbrains_binary_dir: /usr/local/bin

The directory where links to IDEs executables will be created

        jetbrains_user: root

The user who will own IDEs files and directories

        jetbrains_link_executable: false

Whether to create a link to the IDE executable under `jetbrains_binary_dir`

        jetbrains_force_reinstall: false

Whether to force re-installation of the IDE even if it appears to be
installed (directory exists). This can be useful if you want to be
sure all files are in place.

        jetbrains_code_map:
            CL: clion
            DG: datagrip
            DS: dataspell
            GO: goland
            IIC: intellij-idea-community
            IIU: intellij-idea-ultimate
            IIE: IntelliJ-idea-educational
            PCC: pycharm-community
            PCP: pycharm-professional
            PCE: pycharm-educational
            PS: phpstorm
            RD: rider
            RM: rubymine
            WS: webstorm

The map between IDE codes and names

Dependencies
------------
None

Example Playbook
----------------

Install version 2022.3.1 of PhpStorm:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          jetbrains_ide:
            - code: PS
              version: 2022.3.1

License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile

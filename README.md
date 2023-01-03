Ansible Role: Jetbrains
==================

Ansible role to install Jetbrains IDEs on Linux. The role downloads, verifies,
and installs the selected IDEs. It also creates desktop launchers.

Role Variables
--------------

        jetbrains_ide: []

The list of dictionaries describing IDEs and versions to install (see example)

        jetbrains_download_dir: /tmp

The directory where to download IDE tarballs

        jetbrains_installation_dir: /opt/jetbrains

The root installation directory

        jetbrains_remove_tarballs_after_installation: true

Controls whether the downloaded IDE tarball is removed after installation

        jetbrains_remove_other_versions: true

Controls whether previously installed IDE versions are removed after installation

        jetbrains_releases_url: https://data.services.jetbrains.com/products/releases

The URL used to retrieve information about IDEs

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

Install the latest version of Pycharm Community Edition and version 2022.3.1 of PhpStorm:

    - hosts: workstations
      roles:
        - role: egdoc.jetbrains
          jetbrains_ide:
            - code: PS
              version: '2022.3.1'
            - code: PCC
              version: latest

License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile

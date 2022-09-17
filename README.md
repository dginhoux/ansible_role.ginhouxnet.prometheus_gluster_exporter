Ansible Role : dginhoux.prometheus_gluster_exporter
=========

This ansible role install, configure and uninstall prometheus gluster exporter.
It can be deploy as binary downloaded from github OR as docker (no public image, you have to build an image and push to a registry)



Requirements
------------

This role require a supported platform defined in `meta/main.yml`.
It will skip node with unsupported platform ; this behaviour can be bypassed by settings this variable `asserts_bypass=True`.


Role Variables
--------------

Necessary variables are defined on `defaults/main.yml`



Dependencies
------------

none


Example Playbook
----------------



License
-------

BSD


Author Information
------------------

https://github.com/dginhoux/


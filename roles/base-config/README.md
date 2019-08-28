Role Name
=========

Creates a base config for openstack servers. Called by 3 Tier App Playbook.
Will install base tools, packages and repos


Requirements
------------

OSP Environment must be provisioned by OSP Setup role prior to execution.
Workstation must be configured for SSH proxy.


Role Variables
--------------

Local variable {{item}} used for yum installation of httpie and python-pip

Dependencies

------------
repos_template.j2 must be in place to act as repo assignment template
index.html.j2 must be in place to act as index for website


Example Playbook
----------------

Call base-config role from 3 Tier Setup Example

- name: setup load-balancer tier
  hosts: frontends
  become: yes
  roles:
    - {name: base-config, tags: base-config}


License
-------

BSD

Author Information
------------------

Originally created by Redhat Engineering. Modified by Rich Mallory




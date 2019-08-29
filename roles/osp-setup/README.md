OSP-Setup
=========

Provisions the initial openstack environment in prep of application installation

Requirements
------------

The following tasks will be preformed

create-image.yml - Downloads the openstack OS image
create-flavor.yml - Specifies the OS Flavior of image
create-keypair.yml -  Creates test_id_rsa keypair
create-network.yml - Creates networks and provides basic configuration (DNS, 
create-sg.yml


Role Variables
--------------

Public, Private networks should be defined in Variables

Public facing example
 
  external:
    cloud_name: ospcloud
    network_name: ext_network
    subnet_name: ext_subnet
    cidr_network: "xxxxxxx"
    state: present
    external: true
    
Router will be configured to connect the two networks


  router:
    cloud_name: ospcloud
    state: present
    name: router
    network: ext_network


Dependencies
------------



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

Originally created by Redhat Engineering. Modified by Rich Mallory


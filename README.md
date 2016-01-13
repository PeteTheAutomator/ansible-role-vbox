vbox
====

This is an Ansible role for managing the creation of VirtualBox VM instances (thro cloning).

Project state: WORK-IN-PROGRESS!

Requirements
------------


Role Variables
--------------

    # some arbitrary snapshot name - this is necessary for linked cloning
    vbox_snapshot_name: ansible-snapshot

    # type of networking the instance should use - valid options are hostonly or bridged
    vbox_network_type: hostonly

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: localhost
      gather_facts: no
      connection: local
      roles:
        - { role: vbox,
            source_vmname: packer-virtualbox-base-centos-7.1-1452541146,
            dest_vmname: webserver1,
            clone_options: [
              { key: cpus, value: 2 },
              { key: memory, value: 2048 }
            ]
         }


License
-------

BSD

Author Information
------------------


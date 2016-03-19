[![Build Status](https://travis-ci.org/networklore/ansible-role-nagios.svg?branch=master)](https://travis-ci.org/networklore/ansible-role-nagios)
Nagios
======

This role is a work in progress. Don't use yet.

A brief description of the role goes here.

TODO
----

- name: Activate Apache cgi  on Ubuntu 14.04
  file: src=/etc/apache2/mods-available/cgi.load dest=/etc/apache2/mods-enabled/cgi.load state=link owner=root group=root
  when: is_ubuntu

Version specific:
  - name: Downloading and enable the EPEL repository definitions.
    yum: name={{ ansible_env.HOME }}/nagios//epel-release-6-8.noarch.rpm state=present
    when: is_centos


Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

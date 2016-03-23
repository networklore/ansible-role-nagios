# Ansible Role: Nagios

[![Build Status](https://travis-ci.org/networklore/ansible-role-nagios.svg?branch=master)](https://travis-ci.org/networklore/ansible-role-nagios)

Installs Nagios 4.1.1 from source. Once Nagios is installed you can login to http://ip-address/nagios/ using the username and password you configure in the nagios_users variable.

## Requirements

None.

## Role Variables

The variables you can configure are listed below. For the default settings you can look in `defaults/main.yml`.

    download_dir: /home/user/download/nagios

This is the directory where the downloaded files will be placed and extracted.

    nagiosurl: https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.1.1.tar.gz
    nagiossrc: nagios-4.1.1

The download url for Nagios along with the directory name which will be created when the source file is
decompressed to. I.e. with `tar -xzvf nagios-4.1.1.tar.gz`

    pluginsurl: http://www.nagios-plugins.org/download/nagios-plugins-2.1.1.tar.gz
    pluginssrc: nagios-plugins-2.1.1

Same as for Nagios but for the Nagios plugins.

    nagios_users:
      - user: nagiosadmin
        pass: Password123
      - user: tyrion
        pass: red_w1ne
      - user: daenerys
        pass: dragon_fir3

The users which should be allowed to login to the Nagios web GUI.

## Dependencies

None.

## Example Playbook

Install Nagios and setup the password for your nagiosadmin user.

    - hosts: monitoring-servers
      vars_files:
       - vars/main.yml    
      roles:
         - { role: networklore.nagios }

*Contents of vars/main.yml*:

    nagios_users:
      - user: nagiosadmin
        pass: S3cre7Passw0rd

## License

BSD

## Author Information

This role was created in 2016 by [Patrick Ogenstad](http://networklore.com).

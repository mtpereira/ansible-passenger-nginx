Common Ansible Role
=========

![HE:Labs](https://raw.githubusercontent.com/Helabs/helabs.github.com/master/images/logo.png "HE:Labs")

This is a simple role that install core packages for Ansible to work best and
also installs and configures both NTP and timezone data.

Requirements
------------

This role only requires Ansible version 1.9+

Role Variables
--------------

All variables should be ovewritten at the playbook level. Those are:

*   `passenger_apt_repo_key_url`: URL to the keyserver from where to fetch
passenger GPG key

        http://keyserver.ubuntu.com/pks/lookup?op=get&search=0x561F9B9CAC40B2F7

*   `passenger_apt_repo_key_id`: Passenger's key ID

        AC40B2F7

*   `passenger_apt_repo`: Passenger apt repository URL

        https://oss-binaries.phusionpassenger.com/apt/passenger

*   `passenger_version`: Passenger's version you want to install

        5.0.21

*   `passenger_pkg_state`: State of the passenger package

        installed

*   `passenger_system_ruby`: Determines if passenger will use the system rub
binaries or not

        yes

*   `passenger_app_env`: Application environment to pass along to passenger

        production

*   `passenger_app_min_instances`: Minimum number of instances to spaen

        1

*   `passenger_app_name`: The Application common short name

        webapp

*   `passenger_app_port`: tcp prot to which bind Passenger

        3000

*   `passenger_app_server_name`: FQDN used by NGiNX server block

        "{{ ansible_fqdn }}"

*   `passenger_app_root`: Path to app on the filesystem

        "/opt/{{ passenger_app_name }}"

*   `passenger_app_user`: User used by the webapp to run

        "{{ passenger_app_name }}"

*   `passenger_friendly_error_pages`: Whether or not display
[passenger_friendly_error_pages](https://www.phusionpassenger.com/library/config/nginx/reference/#passenger_friendly_error_pages)
        "off"

*   `passenger_app_protocol`: Whether you want to use https or not

        "http"

Dependencies
------------

*   helabs.common
*   helabs.ruby

Using this role
----------------

Using this roles as as simples as:

    - hosts: servers
      become: yes
      roles:
         - helabs.passenger-nginx

License
-------

BSD

Author Information
------------------

Lucas do Amaral Saboya Works as DevOps/SysOps @ [HE:Labs](https://www.helabs.com)

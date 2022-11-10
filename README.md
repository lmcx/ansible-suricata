Ansible Role: Suricata
=========

An Ansible role that installs and configures [Suricata](https://suricata.io/) IDS/IPS

Requirements
------------

None.

Role Variables
--------------

Suricata configuration file location :

    suricata_conf_file: "/etc/suricata/suricata.yaml"

Enabled rule sets :

    suricata_rule_files:
      - suricata.rules
      - example/example.rules

Custom rules directory :

    suricata_local_rules_dir: "files/suricata/rules"

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------

[Loïc Michaux](https://github.com/lmcx)
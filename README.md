Ansible Role: Suricata
======================

![CI](https://github.com/lmcx/ansible-suricata/actions/workflows/ci.yml/badge.svg?branch=develop)

An Ansible role that installs and configures [Suricata](https://suricata.io/) IDS/IPS

Requirements
------------

None.

Role Variables
--------------

Suricata configuration file location :

    suricata_conf_file: "/etc/suricata/suricata.yaml"

Custom rules directory :

    suricata_local_rules_dir: "files/suricata/rules"

These variables, if defined, should be dictionnaries. They are used as is following the suricata configuration format :
| Ansible variables          | Suricata configuration |
|----------------------------|------------------------|
| suricata_vars              | vars                   |
| suricata_stats             | stats                  |
| suricata_outputs           | outputs                |
| suricata_logging           | logging                |
| suricata_af_packet         | af-packet              |
| suricata_pcap              | pcap                   |
| suricata_pcap_file         | pcap-file              |
| suricata_app_layer         | app-layer              |
| suricata_coredump          | coredump               |
| suricata_unix_command      | unix-command           |
| suricata_legacy            | legacy                 |
| suricata_action_order      | action-order           |
| suricata_reputation_files  | reputation-files       |
| suricata_engine_analysis   | engine-analysis        |
| suricata_pcre              | pcre                   |
| suricata_host_os_policy    | os-policy              |
| suricata_defrag            | defrag                 |
| suricata_host_config       | host-config            |
| suricata_flow              | flow                   |
| suricata_vlan              | vlan                   |
| suricata_flow_timeouts     | flow-timeouts          |
| suricata_stream            | stream                 |
| suricata_host              | host                   |
| suricata_ippair            | ippair                 |
| suricata_decoder           | decoder                |
| suricata_detect            | detect                 |
| suricata_threading         | threading              |
| suricata_luajit            | luajit                 |
| suricata_nfq               | nfq                    |
| suricata_capture           | capture                |
| suricata_pfring            | pfring                 |
| suricata_ipfw              | ipfw                   |
| suricata_napatech          | napatech               |
| suricata_rule_files        | rule-files             |

These variables should contain strings if defined :
| Ansible variables              | Suricata configuration |
|--------------------------------|------------------------|
| suricata_default_log_dir       | default-log-dir        |
| suricata_host_mode             | host-mode              |
| suricata_mpm_algo              | mpm-algo               |
| suricata_spm_algo              | spm-algo               |
| suricata_default_rule_path     | default-rule-path      |
| suricata_classification_file   | classification-file    |
| suricata_reference_config_file | reference-config-file  |
| suricata_threshold_file        | threshold-file         |

For more information about how to configure Suricata, please refere to the official [Suricata configuration](https://suricata.io/documentation/) and use this list to apply your configuration to this Ansible role.

The default configuration provided with this role is a 1:1 translation of the one provided with Suricata on the official Fedora repositories. It can be overloaded field by field or, obviously, fully rewritten. Please refer to `defaults/main.yml` for more information on the default values.

If some files are present in the directory specified in `suricata_local_rules_dir`, they will be automatically uploaded to `suricata_default_rule_path` and append to the rule-files list in `suricata_rule_files`. You can still enable/disable rules that are not managed through Ansible by removing them from the `suricata_rule_files` list in your configuration.


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
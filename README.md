Ansible Playbook: oracle-host-cron
==================================

Copy scripts enlisted in `oracle_host_cron_templates_to_copy` list and schedule them as defined in `oracle_host_cron_config` variable.

For example, schedule scripts such as:

* backup_arch_emergency.ksh
* rman_delete_expired.ksh
* rman_resync_catalog.ksh


Supported OS:
-------------
* RedHat
* CentOS
* OracleLinux

Requirements
------------

This playbook requires the `oracle` and `oracle-host-cron` roles.

`$ ansible-galaxy install -r roles/requirements.yml`

Examples
--------

    $ ansible-playbook playbook.yml --list-tasks
    $ ansible-playbook playbook.yml --list-tags

Default execution
    
    ansible-playbook playbook.yml

Copy cron scripts only, but DO NOT change anything in cron

    ansible-playbook playbook.yml --extra-vars='{"oracle_host_cron_copy_scripts": true, "oracle_host_cron_manage_cron_jobs": false}'

Disable (comment out) all cron jobs managed by Ansible

    ansible-playbook playbook.yml --extra-vars='{"oracle_host_cron_disable_jobs": true, "oracle_host_cron_copy_scripts": false}'

	
License
-------

GPLv3 - GNU General Public License v3.0

Author Information
------------------

This playbook was created in 2018 by [Krzysztof Lewandowski](mailto:Krzysztof.Lewandowski@fastmail.fm).


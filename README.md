Ansible Role: Security Patching
=========

An Ansible role that run security updates on Linux
Currently support Ubuntu and Oracle Linux

- Galaxy: https://galaxy.ansible.com/ui/standalone/roles/ngochieu642/security_patching/

Requirements
------------

None

Role Variables
--------------

`log_file_path`: Path to the log file on host

Dependencies
------------

None

Example Playbook
----------------

```yaml
---
- name: Patch Bastion Host
  hosts: bastion
  become: yes
  vars:
    log_file_path: "/var/log/security_patching_{{ ansible_date_time.date }}.log"

  pre_tasks:
    - name: Ensure log directory exists
      file:
        path: "/var/log"
        state: directory
        mode: '0755'

  roles:
    - ngochieu642.security_patching

```

License
-------

MIT

Author Information
------------------

Created in 2024 by ngochieu642

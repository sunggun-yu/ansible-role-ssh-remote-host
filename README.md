Ansible Role ssh-remote-host
============================

This Ansible role helps adding specific user account public ssh key from a remote host into `authorized_keys` in another remote host and adding target remote host key into `know_hosts` file. with that, you can achieve use case like setting up `rsync` cron job that is sending file from one host to the other over ssh.

Requirements
------------

This role has tested on Ansible 2.4.1.0

Role Variables
--------------

- `ssh_remote_host_public_key_user`: User account name to add public key into another. default value is "root"
- `ssh_remote_host_public_key_file`: SSH public file path. default value is "/root/.ssh/id_rsa.pub"
- `ssh_remote_host_keyscan_cmd`: Keyscan command and option. default value is "/usr/bin/ssh-keyscan -4 -t ecdsa-sha2-nistp256 -T 10"
- `ssh_remote_host_inventory_group_name`: Inventory group name to add public key. default value is all

Dependencies
------------

None

Example Playbook
----------------

Please refer to `test` directory for usage.

    - hosts: servers
      roles:
         - { role: sunggun-yu.ssh-remote-host }

License
-------

MIT

Author Information
------------------

Sunggun Yu (<sunggun.dev@gmail.com>)

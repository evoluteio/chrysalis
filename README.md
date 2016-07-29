# chrysalis

Overview

Chrysalis was designed to migrate VMs from all major cloud services and VM management systems. While the development of Chrysalis is under quick iterations, the system currently supports migrating VMs from the following system to containers:

- Migrate VMs from VMWare management systems such as ESXi servers
- Migrate VMs from Amazon EC2 servers

Command line options for Chrysalis

-  To download and migrate from vcenter management server

          ./v2c.py --mgmt-server server-name --vm vm-name --user user-name

          where:
                --mgmt-server: the vcenter server (either IP or FQDN)
                --vm: the VM name for which to migrate
                --user: administrator's name to access center, e.g,. the root

-    To download and migrate from a VM in the Cloud:

          ./v2c.py --vm-host server-name --ssh-key root-private-key --staging staging-dir

          where:
                --vm-host: either IP address or FQDN of  the VM
                --ssh-key: the private key for the root to access the VM
                --staging: a place in the local system to hold DD images from VM. It typically requires a large disk space.

-  To  migrate a local image:

          ./v2c.py --vm-disk image-file

          where:
               --vm-disk: the local image file, it can be in either DD format or vmdk format.

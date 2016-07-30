# Chrysalis - Convert VMs to Containers

**Overview**

Chrysalis was designed to migrate VMs from all major cloud services and VM management systems. While the development of Chrysalis is under quick iterations, the system currently supports migrating VMs from the following system to containers:

- Migrate VMs from VMWare management systems such as ESXi servers
- Migrate VMs from Amazon EC2 servers

**Command line options**

-  To download and migrate from vCenter management server:

          ./v2c.py --mgmt-server server-name --vm vm-name --user user-name

          where:
                --mgmt-server: the vcenter server (either IP or FQDN)
                --vm: the VM name for which to migrate
                --user: administrator's name to access center, e.g,. the root

-    To download and migrate from EC2:

          ./v2c.py --vm-host server-name --ssh-key root-private-key --staging staging-dir

          where:
                --vm-host: either IP address or FQDN of  the VM
                --ssh-key: the private key for the root to access the VM
                --staging: a place in the local system to hold DD images from VM. It typically requires a large disk space.
                

Start your application (e.g. centos3gbnginx-img) with an existing container runtime (docker, rkt, lxc) or platform (evo, ecs, etc).



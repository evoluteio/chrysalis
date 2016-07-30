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


**Example Execution**

```
[root@evo0120 ~]# crysls --mgmt-server vcenter.localhost --user root --vm CentOS3GBNGINX
Password: 
INFO: Analyzing "CentOS3GBNGINX" VM from host vcenter.localhost
INFO: Downloading virtual machine file from vcenter.localhost
[################################] 196608/196609 - 00:00:40
INFO: Downloaded file at /tmp/CentOS3GBNGINX
INFO: Converting virtual machine CentOS3GBNGINX ...
    (100.00/100%)
INFO: Migrating Data
    578,869,182  64%   14.10MB/s    0:00:39 (xfr#16710, to-chk=0/30725)   
INFO: Committing new image centos3gbnginx-img 
INFO: Succeed in creating image centos3gbnginx-img !
INFO: Cleaning up the host ...
INFO: All done !!!
```

**Run Application**

To run your application with an existing container runtime (lxc, docker, rkt), start the container image:

```
[root@localhost ~]# docker run -t -i centos3gbnginx-img bash
[root@9eda69079224 /]# echo "Hello Container" `hostname`
```

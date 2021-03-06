# Chrysalis v0.5 - Containerize any application

**Overview**

Chrysalis was designed to migrate applications across all infrastructure environments including major cloud services and VM management systems. 

While the development of Chrysalis is under quick iterations, the system currently supports migrating VMs from the following system to containers:

- Migrate VMs from VMWare management systems such as ESXi servers
- Migrate VMs from Amazon EC2 servers
- Migrate supported HP, Dell and Supermicro servers


**Downloading crysls**

- crysls can be downloaded and installed via the following repository:

```
[crysls]
name=Evolute Packages for EL 7 x86_64
baseurl=http://yum.evolute.io/rpm/crysls
enabled=1
gpgcheck=0
```
- Install the crysls package via yum:
```
$ yum install crysls
```

**Command line options**

-  To download and migrate from vCenter management server:
```
crysls --mgmt-server server-name --vm vm-name --user user-name

       where:
       --mgmt-server: the vcenter server (either IP or FQDN)
       --vm: the VM name for which to migrate
       --user: administrator's name to access center, e.g,. the root

-    To download and migrate from other systems including EC2:

       crysls --vm-host server-name --ssh-key root-private-key --staging staging-dir

       where:
       --vm-host: either IP address or FQDN of  the VM
       --ssh-key: the private key for the root to access the VM
       --staging: a place in the local system to hold DD images from VM. It typically requires a large disk space.
                
```

**Run Application**


Start your application with an existing container runtime (docker, rkt, lxc) or platform (evo, ecs, etc).



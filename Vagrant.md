## Exporting a Vagrant VM as a new Vagrant VM

**IDEA:** Many hypervisors enable exporting an image via CLI and this could be utilized in conjunction with Vagrant which would be used to provision the VM.

### [Vagrant Package](https://www.vagrantup.com/docs/cli/package.html)
- Packages up a currently runninng VirtualBox or Hyper-V box into a reusable box

### VirtualBox
- #### Exporting images
    - https://www.techrepublic.com/article/how-to-import-and-export-virtualbox-appliances-from-the-command-line/

### Hyper-V
- #### Exporting images
    - https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/deploy/export-and-import-virtual-machines

### VMWare
- #### Exporting images
    - http://jdgreen.io/export-vms-via-command-line-using-ovf-tool/
    - https://kb.vmware.com/s/article/1038709?lang=en_US

### Libvert / QEME
- https://en.wikibooks.org/wiki/QEMU/Images

### Process
./build.sh --> vagrant up && vagrant provision  --> export vm --> convert VM image to RAW for bare metal provision || reused Vagrant box with configurations

### Pros
1. Uses as few tools as possible
2. Easy to script
3. Vagrant is well maintained and has a large user base

### Cons
1. Does not support exporting images to public cloud platforms
2. Requires use of an existing Vagrantbox to serve as a base image to install everything on

### Stateful data
Stateful data can be managed using a Host to Guest directory sharing.
- #### HyperV
    - Implemented with SMB
- #### Virtualbox
    - Requires Guest Additions

### Upgradability
- To perform updates, you can build off of the previous box. Hoever, this method may be problematic with major changes.
- It may be possible to share the same directory on the host machine with multiple VM's allowing a new version to start up while the previous version continues to run.
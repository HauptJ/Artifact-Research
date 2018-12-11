## Exporting Vagrant VM as a new Vagrant VM and / or Image using a shell script

**IDEA:** Many hypervisors enable exporting an image via CLI and this could be utilized in conjunction with Vagrant which would be used to provision the VM. Some HyperVisors also support executing a script on the guest OS.

**NOTE:** This is the overall simplest method

### [Vagrant Package](https://www.vagrantup.com/docs/cli/package.html)
- Packages up a currently runninng VirtualBox or Hyper-V box into a reusable box

### VirtualBox
- #### Exporting images
    - https://www.techrepublic.com/article/how-to-import-and-export-virtualbox-appliances-from-the-command-line/
- #### Executing scripts in guest OS
    - [vbmanage](https://askubuntu.com/questions/490420/how-to-launch-a-script-inside-a-vm-from-the-host)

### HyperV
- #### Exporting images
    - https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/deploy/export-and-import-virtual-machines

### VMWare
- #### Exporting images
    - http://jdgreen.io/export-vms-via-command-line-using-ovf-tool/
    - https://kb.vmware.com/s/article/1038709?lang=en_US
- #### Executing scripts in guest OS
    - [Invoke-VMScript](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/techpaper/vsphere_power-cli-5.1-r1_technote.pdf)

### Libvert / QEME
- https://en.wikibooks.org/wiki/QEMU/Images

### Process
./build.sh --> vagrant up && vagrant provision || provision with hypervisor's shell script loader --> export vm --> convert VM image to RAW for bare metal provision || reused Vagrant box with configurations

### Pros
1. Uses as few tools as possible
2. ~~Easy to script~~


### Cons
1. Does not support exporting images to public cloud platforms
2. Requires use of an existing Vagrantbox to serve as a base image to install everything on

### Stateful data
Stateful data can be managed using a Host to Guest directory sharing.
- #### HyperV
    - Implemented with SMB
- #### Virtualbox
    - Requires Guest Additions
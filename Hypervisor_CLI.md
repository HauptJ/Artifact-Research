## Exporting VM  Image using a shell script

**IDEA:** Many hypervisors enable exporting an image via CLI and this could be utilized in conjunction with shell script execution (if supported) which would be used to provision the VM. 
    - Some HyperVisors also support executing a script on the guest OS.

**NOTE:** ~~This is the overall simplest method~~

### VirtualBox
- #### Exporting Images
    - https://www.techrepublic.com/article/how-to-import-and-export-virtualbox-appliances-from-the-command-line/
- #### Executing scripts in guest OS
    - [vbmanage](https://askubuntu.com/questions/490420/how-to-launch-a-script-inside-a-vm-from-the-host)

### Hyper- V
- #### Exporting Images
    - https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/deploy/export-and-import-virtual-machines

### VMWare
- #### Exporting Images
    - http://jdgreen.io/export-vms-via-command-line-using-ovf-tool/
    - https://kb.vmware.com/s/article/1038709?lang=en_US
- #### Executing scripts in guest OS
    - [Invoke-VMScript](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/techpaper/vsphere_power-cli-5.1-r1_technote.pdf)

### Libvert / QEME
- https://en.wikibooks.org/wiki/QEMU/Images

### Process
./build.sh --> provision with hypervisor's shell script loader --> export vm --> convert VM image to RAW for bare metal provision

### Pros
1. Uses as few tools as possible
2. Easy to script
3. Hypervisors CLI tools are well maintained

### Cons
1. Does not support exporting images to public cloud platforms
2. Requires use of an existing Vagrantbox to serve as a base image to install everything on

### Stateful data
Stateful data can be managed using a Host to Guest directory sharing.
- #### Hyper-V
    - Implemented with SMB
- #### Virtualbox
    - Requires Guest Additions

### Upgradability
- To perform updates, you can build off of the previous image. Hoever, this method may be problematic with major changes.
- It may be possible to share the same directory on the host machine with multiple VM's allowing a new version to start up while the previous version continues to run.
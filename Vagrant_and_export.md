## Exporting Vagrant VM as a new Vagrant VM and / or Image using a shell script

**IDEA:** Many hypervisors enable exporting an image via CLI and this could be utilized in conjunction with Vagrant which would be used to provision the VM.

**NOTE:** This is the overall simplest method

### [Vagrant Package](https://www.vagrantup.com/docs/cli/package.html)
- Packages up a currently runninng VirtualBox or Hyper-V box into a reusable box

### VirtualBox
- https://www.techrepublic.com/article/how-to-import-and-export-virtualbox-appliances-from-the-command-line/

### HyperV
- https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/deploy/export-and-import-virtual-machines

### VMWare
- http://jdgreen.io/export-vms-via-command-line-using-ovf-tool/
- https://kb.vmware.com/s/article/1038709?lang=en_US

### Libvert / QEME
- https://en.wikibooks.org/wiki/QEMU/Images

### Process
./build.sh --> vagrant up && vagrant provision --> export vm --> provision reused image with configurations or convert VM image to RAW for bare metal

### Pros
1. Uses as few tools as possible
2. Easy to script


### Cons
1. Does not support exporting images to public cloud platforms
2. Requires use of an existing Vagrantbox to serve as a base image to install everything on
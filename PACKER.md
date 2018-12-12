## [Packer](https://www.packer.io/)

### [Source](https://github.com/hashicorp/packer)

### Pros:
1. [Support for all major public cloud platforms (AWS, Azure, GCE)](https://www.packer.io/docs/builders/index.html)
2. [Support for all major HyperVisors (VMWare, Parallels, QEMU, HyperV, Virtual Box)](https://www.packer.io/docs/builders/index.html)
3. [Support for all major Provisioners (Ansible, Chef, Puppet, Salt)](https://www.packer.io/docs/provisioners/index.html)
4. [Post processors that allow for automatic pushing artifacts to repositories (AWS, Docker, GCE)](https://www.packer.io/docs/post-processors/index.html)
5. [Can also be used to package Docker containers as artifacts](https://www.packer.io/docs/builders/docker.html)
6. Large user base and many active developers therefore CVE's are handled in a timely manner.
7. Can build a base image using the image file provided by the distribution
8. [Can build images in parallel](https://www.packer.io/intro/getting-started/parallel-builds.html)


### Cons:
1. Does not directly support bare metal
    - [However, it may be possible to convert a VBox and Libvert artifact images to a bare metal image](https://github.com/viralpoetry/packer-bare-metal)
    - https://askubuntu.com/questions/32499/migrate-from-a-virtual-machine-vm-to-a-physical-system
2. CenturyLink cloud is not listed as supported

### VirtualBox
- #### Exporting Images
    - https://www.techrepublic.com/article/how-to-import-and-export-virtualbox-appliances-from-the-command-line/

### Hyper-V
- #### Exporting Images
    - https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/deploy/export-and-import-virtual-machines

### VMWare
- #### Exporting Images
    - http://jdgreen.io/export-vms-via-command-line-using-ovf-tool/
    - https://kb.vmware.com/s/article/1038709?lang=en_US

### Libvert / QEME
- https://en.wikibooks.org/wiki/QEMU/Images

### Stateful data
Stateful data can be managed using a Vagrant Box, VB guest additions host to guest directory sharing, SMB (Hyber-V), etc.

### Upgradability
- A fresh image can be build for each deployment
- If as many configuration steps as possible are baked into the image, upgrading should be very quick. 
- It may be possible to share the same directory on the host machine with multiple VM's allowing a new version to start up while the previous version continues to run.
    - **NOTE:** I have not tested this with persistent databases.

### Demos
1. [Building an AMI](https://www.packer.io/intro/getting-started/build-image.html)

### Example
- [Vagrant in a Vagrant Box](https://github.com/HauptJ/Vagrant-CentOS-7-HyperV-Gen-2)
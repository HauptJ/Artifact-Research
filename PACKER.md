## [Packer](https://www.packer.io/)

### Pros:
1. [Support for all major public cloud platforms (AWS, Azure, GCE)](https://www.packer.io/docs/builders/index.html)
2. [Support for all major HyperVisors (VMWare, Parallels, QEMU, HyperV, Virtual Box)](https://www.packer.io/docs/builders/index.html)
3. [Support for all major Provisioners (Ansible, Chef, Puppet, Salt)](https://www.packer.io/docs/provisioners/index.html)
4. [Post processors that allow for automatic pushing artifacts to repositories (AWS, Docker, GCE)](https://www.packer.io/docs/post-processors/index.html)
5. [Can also be used to package Docker containers as artifacts](https://www.packer.io/docs/builders/docker.html)

### Cons:
1. Does not support bare metal
    - [However, it may be possible to convert a VBox artifact to a bare metal image](https://github.com/viralpoetry/packer-bare-metal)
2. CenturyLink cloud is not listed as supported


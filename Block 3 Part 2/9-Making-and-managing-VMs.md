- VMs are created from an ISO source image of an OS that you can download from a range of sources such as Ubuntu or CentOS
- VMs can be made in VirtualBox, an application that helps create VM images
- You can then install any software you want to have present inside the final image into the VM, such as a web server, whilst it is running in VirtualBox and then close down the VM
- The VirtualBox image is in a directory named by the storage property of the VM
- This file can be converted to another file using:
	- VBoxManage clonehd --format RAW vm.vdi vm.img
- and then:
	- qeum-img convert -f raw vm.img -0 qcow2 vm.qcow2

- Images can also come from an online archive

# packer-rhel8-ova
Packer project to build rhel8 ova


# pre-requirements

- Latest VirtualBox
- Latest Packer
- RHEL8 iso

# how to use

- clone this repo
```
git clone https://github.com/kikitux/packer-rhel8-ova.git
```

- change directory
```
cd packer-rhel8-ova
```

# how to build

run packer build

```
packer build rhel8.json
```

# how to use

import the ova file from `output-virtualbox-iso\rhel8.ova`

# default user

- User is `user`
- Password is `password`

# sample output

```shell
$ ./packer.exe build -on-error=ask rhel8.json
Warning: Warning when preparing build: "virtualbox-iso"

A checksum of 'none' was specified. Since ISO files are so big,
a checksum is highly recommended.


virtualbox-iso: output will be in this color.

==> virtualbox-iso: Retrieving Guest additions
==> virtualbox-iso: Trying C:\Program Files\Oracle\VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso: Trying file://C:/Program%20Files/Oracle/VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso: file://C:/Program%20Files/Oracle/VirtualBox/VBoxGuestAdditions.iso => C:/Program Files/Oracle/VirtualBox/VBoxGuestAdditions.iso
==> virtualbox-iso: Retrieving ISO
==> virtualbox-iso: Trying rhel-8.8-x86_64-dvd.iso
==> virtualbox-iso: Trying rhel-8.8-x86_64-dvd.iso
==> virtualbox-iso: rhel-8.8-x86_64-dvd.iso => C:/Users/kikitux/Dropbox/local/win10/packer-rhel8-ova/rhel-8.8-x86_64-dvd.iso
==> virtualbox-iso: Starting HTTP server on port 8047
==> virtualbox-iso: Creating virtual machine...
==> virtualbox-iso: Creating hard drive output-virtualbox-iso\rhel8.vdi with size 250000 MiB...
==> virtualbox-iso: Mounting ISOs...
    virtualbox-iso: Mounting boot ISO...
==> virtualbox-iso: Creating forwarded port mapping for communicator (SSH, WinRM, etc) (host port 3888)
==> virtualbox-iso: Executing custom VBoxManage commands...
    virtualbox-iso: Executing: modifyvm rhel8 --memory 4096
    virtualbox-iso: Executing: modifyvm rhel8 --cpus 4
    virtualbox-iso: Executing: modifyvm rhel8 --nat-localhostreachable1 on
==> virtualbox-iso: Starting the virtual machine...
    virtualbox-iso: The VM will be run headless, without a GUI. If you want to
    virtualbox-iso: view the screen of the VM, connect via VRDP without a password to
    virtualbox-iso: rdp://127.0.0.1:5910
==> virtualbox-iso: Waiting 10s for boot...
==> virtualbox-iso: Typing the boot command...
==> virtualbox-iso: Using SSH communicator to connect: 127.0.0.1
==> virtualbox-iso: Waiting for SSH to become available...
==> virtualbox-iso: Connected to SSH!
==> virtualbox-iso: Uploading VirtualBox version info (7.0.8)
==> virtualbox-iso: Uploading VirtualBox guest additions ISO...
==> virtualbox-iso: Provisioning with shell script: C:\Users\kikitux\AppData\Local\Temp\packer-shell3106656653
    virtualbox-iso: rm /home/user/VBoxGuestAdditions.iso
==> virtualbox-iso: Gracefully halting virtual machine...
==> virtualbox-iso: Preparing to export machine...
    virtualbox-iso: Deleting forwarded port mapping for the communicator (SSH, WinRM, etc) (host port 3888)
==> virtualbox-iso: Exporting virtual machine...
    virtualbox-iso: Executing: export rhel8 --output output-virtualbox-iso\rhel8.ova
==> virtualbox-iso: Cleaning up floppy disk...
==> virtualbox-iso: Deregistering and deleting VM...
Build 'virtualbox-iso' finished after 7 minutes 270 milliseconds.

==> Wait completed after 7 minutes 270 milliseconds

==> Builds finished. The artifacts of successful builds are:
--> virtualbox-iso: VM files in directory: output-virtualbox-iso
```

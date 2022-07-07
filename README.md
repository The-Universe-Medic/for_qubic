# QUBIC
## Various information that helped me in setting up and installing qubic

## Table Of Contents
---
 1. [Installation on a VM (Virtual Box) on a WinServer or Win10 host](#install_on_vm)
    1. [Installing Virtual Box](#Installing_Virtual-Box)
    2. [Preparing the boot disk](#Preparing_the_boot_disk)
    3. [VM settings](#VM_settings)


---
<a name="install_on_vm"></a>
# Installation on a VM (Virtual Box) on a WinServer or Win10 host
To work on a virtual machine, we will need a virtualization software product (in our case, VirtualBox) and a boot disk, which we will make using Windows OS.
Setting up a virtual disk is very close to setting up a USB drive described on [Qubic-World
](https://github.com/Qubic-World/qubic-howto#preparing-usb).

<a name="Installing_Virtual-Box"></a>
## Installing Virtual Box
You can download VirtualBox from any website, but I advise you to use the [official website](https://www.virtualbox.org/).

>1. Download VirtualBox by clicking on the big blue `Download` button

>2. After selecting the desired operating system

>3. Start the installation by double-clicking on the installer shortcut.
`next -> next -> next -> yes -> Install`

---

<a name="#Preparing_the_boot_disk"></a>
## Preparing the boot disk
We create a virtual disk using standard Windows tools.

>1. Opening Computer Management
>2. Action -> Create VHD
>3. In the `location` field, specify the full path to the file and its name
>4. In the Virtual hard disk size line, specify the required volume of the disk being created
>5. Specify `VHD` as the disk format
>6. Specify `Fixed size` as the disk type (There were problems with the file system markup with dynamic volume, I'm deciding how to get around it)
>7. Click OK

After the completed actions, a new space will appear in Computer Management. For further configuration, we do the following steps.
1. Right-click on Disk* (Unknown)
2. Initialize disk
3. Choose the markup style `MBR' -> OK
4. Right-click on the free space of the new disk (Unallocated)
5. New Simple Volume -> next -> next -> next ->
6. File system - `FAT32`
7. Next -> Finish

The new memory space will appear in explorer as a separate disk.


<a name="VM_settings"></a>
## VM settings

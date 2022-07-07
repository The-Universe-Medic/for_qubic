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
## Installing Virtual Box ([graphical representation of text material](#graph_installing_virtual_box))
You can download VirtualBox from any website, but I advise you to use the [official website](https://www.virtualbox.org/).

>1. Download VirtualBox by clicking on the big blue `Download` button
>2. After selecting the desired operating system
>3. Start the installation by double-clicking on the installer shortcut.
[`next -> next -> next -> yes -> Install`]()

---

<a name="Preparing_the_boot_disk"></a>
## Preparing the boot disk ([graphical representation of text material](#graph_preparing_boot_disk))
We create a virtual disk using standard Windows tools.

>1. Opening Computer Management -> Disk Management
>2. Action -> Create VHD
>3. In the `location` field, specify the full path to the file and its name
>4. In the Virtual hard disk size line, specify the required volume of the disk being created
>5. Specify `VHD` as the disk format
>6. Specify `Fixed size` as the disk type (There were problems with the file system markup with dynamic volume, I'm deciding how to get around it)
>7. Click OK

After the completed actions, a new space will appear in Computer Management. For further configuration, we do the following steps.
>1. Right-click on Disk* (Unknown)
>2. Initialize disk
>3. Choose the markup style `MBR` -> OK
>4. Right-click on the free space of the new disk (Unallocated)
>5. New Simple Volume -> next -> next -> next ->
>6. File system - `FAT32`
>7. Next -> Finish

The new memory space will appear in explorer as a separate disk. After writing the required files, you need to disconnect the created virtual disk from the system.
>1.  Opening Computer Management -> Disk Management
>2. Right-click on the created disk -> Detach VHD -> OK

Only after these steps can you attach the disk to the VM.
To make changes to the files located on this virtual disk, it needs to be connected back to the system (if the disk is connected to a virtual machine, you need to stop it before starting actions with the disk, in order to avoid problems with a busy device).
>1. Opening Computer Management -> Disk Management
>2. Action -> Attach VHD
>3. Select the disk by its location -> OK
The disk will appear in explorer.


<a name="VM_settings"></a>
## VM settings ([graphical representation of text material](#graph_vm_settings))
We will touch not only the configuration of the virtual machine, but also the creation.

>1. Machine -> New
>2. Specify the name of the virtual machine and the desired location
>3. Type -> `Other`
>4. Version -> `Other/Unknown (64-bit)` -> next
>5. Allocate the possible amount of RAM -> next
>6. Hard Disk -> Do not add virtual hard drive -> Create -> Continue

Go to the settings of the virtual machine itself.
>1. Right-click on the created machine -> Settings
>2. System -> `Enable EFI (special Forces only)`
>3. System -> Processor -> Specify the number of processor cores
>4. Network -> Attached to: `NAT` -> Advanced -> Adapter type: `Paravirtualized Network (virtio-net)`
>5. Network -> Advanced -> `Port Forwarding` -> Right-click -> Add New Rule -> `Host port: 21841` -> `Guest Port: 21841` -> OK
>6. Storage -> `Controller: IDE` -> Right-click -> Hard Disk -> Select a previously created disk -> OK
















<a name="graph_installing_virtual_box"></a>
Each screenshot shows a sequence of actions.

![alt text](screenshots/virtual_box_main_page.png)
![alt text](screenshots/virtual_box_download.png)
![alt text](screenshots/install1.png)
![alt text](screenshots/install2.png)
![alt text](screenshots/install3.png)
![alt text](screenshots/install4.png)
![alt text](screenshots/install5.png)
![alt text](screenshots/install6.png)


<a name="graph_preparing_boot_disk"></a>
Each screenshot shows a sequence of actions.

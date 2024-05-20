# install ESXi

## create startup disk

rufus or vendory

## set up boot from usb

Open the R730 server, press `F11`on the startup interface, enter the `Boot Manger` interface, select `Launch System Setup`, enter the corresponding interface, select `System BIOS` settings, enter the BIOS settings interface, and set the `Boot Mode` to `UEFI`.

After setting up, press the `ESC` key to exit.

## enable Intel VT-x

ESXi cannot create a virtual machine without this step

## install esxi from usb

Enter the `System Setup `interface, locate the `Processor Settings` settings, and enter to start `Virtualization Technology`

## ESXi install configuration

Relatively simple so omitted

## modify Network Configuration

After the installation is completed, unplug the USB drive, press `F2`, and a login interface will pop up. Enter the set password, press Enter and enter the ESXi management background.

Select `Configure Management Network`, default to DHCP, and modify to static IP.

## create ubuntu vitural machine

The browser accesses the ESXi IP address, and after logging in, you can see the ESXi management interface.

Upload the ubuntu server iso file, and the subsequent creation process is similar to that of VMware and Hyper-V. Be careful not to check LVM (selecting LVM will cause bugs, and the cause has not been found yet).

After the installation of the ubnutu virtual machine is completed, prompt `Failed mount....`, Don`t worry about this information, turn off the virtual machine power, edit the virtual machine settings, change the iso file to the host device, and then turn on the virtual machine power again.

## ESXi ubuntu22.04 ssh perssion deny

# Install Linux properly  _with guidelines_ 

# _Someone Install Linux for different purpose,
	* Codding & Programming
	* Devops like works , as a server, for great linux administration
	* Pentesting, hacking, BugHunting
	* Now Days many people use Linux rather than Windows. 

# Prerequests
	_installation process starts with hardwares, infirmation about your hardware.
	e.g  
		Your CPU :  AMD or INTEL .
		And  GPU :  Amd_Redon, Nvidia, or Intel etc.

	Most Important topic about any OS(Windows,Linux..) installation is __Partition Table__ , __Boot Manager__ & __BIOS__ .


# 1) Partition Table 
	What is Partition Table ? 
	It is Logical devidation of your Hard-Drive. In a device we store our data in Unit called `byte`, like a file has size 2048 B or 2MB .
	We store our data(e.g files,videos) inside a partition . And every Partition contains a specific space(eg  1GB, 5GB we created ) .  
	
	Partitions has many types `EFI,FAT32,FAT16,EXT2,EXT4,NTFS( for Windows FileSystem)`. Partitions are part of fileSystem(Hard-drive),
	like you have 3 partitions(one is EXT4,FAT32 and EFI) in your fileSystem(Hard-Drive). 

	
	* FileSystem : 
			FileSystem are two types MBR and GPT. Every storage device SDcard, Hard-Disk, SSD, Internal Phone Memory is an example of 
			FileSystem depending of MBR or GPT type  .

# 2) BIOS
	
	What is FileSystem types (GPT and MBR) , and why we need It ?
	
	Think how a Phone or Computer Started Up(BOOT), Because every System Files, binary , library files of an Operating System are stored in a 
	Partition of a FileSystem . That is why the GPT and MBR comes in , The BIOS system  first read the FileSystem  according to the MBR or GPT  
	FileSystem Types. Then find the BootLoader(Grub) and load it from a FileSystem then we manually boot up the Operating System(Linux{Ubuntu,Kali,Android}).
	
	
	Why MBR :
		In old days `Lagacy BIOS` and `CMOS-Utlity` use the MBR Partition Table.  
		......

	Why GPT : 
		Now days `UEFI` Use GPT Partition Table.   
		......


# 3) BOOT Manager

	When BIOS loads the Boot-loader from FileSystem. We see GRUB-Bootloader menu , BootLoader loads the kernal modules and many other things.
		
	 

# Installation Guide-lines

## _Step 1)

	Download iso image file of any Operating System like Linux (Ubuntu,kali) as you want. Then create a Bootable USB From iso image File .
	``` sh
	$ sudo dd bs=4M if=Downloads/ubuntu-19.04-desktop-amd64.iso of=/dev/sdb conv=fdatasync 
	```
	dd if=hiveos-XXX.img of=/dev/sdX bs=10M status=progress 
        sudo dd bs=4M if=Downloads/ubuntu-19.04-desktop-amd64.iso of=/dev/sdb conv=fdatasync status=progress

	``` 
	[ source ](https://www.howtogeek.com/414574/how-to-burn-an-iso-file-to-a-usb-drive-in-linux/)
	
## _Step 2)
	
	Plug the Usb Drive to the CPU. Power on the CPU . Now press `Del , F1 or F2 ` key for BIOS menu of MothetBoard .
	When the screen will be prompt , go to Boot Menu  and select the USB Driver. And press F10 to boot .

	
	The GRUB Boot Loader will be prompt , Now select Install or Graphic Install .
	



## _Step 3) 

__In This Article We Install Linux With EFI Partition ( For UEFI Bios ).__

	first create EFI partition of 250MB, at the begianning of the space.
	secondly create swap partition , half size of your RAM(e.g  if your RAM is 4GB then create a swap  partition of 2GB ) at begianning of the space.
	thirdly create root partition like '/' at egianning of the space.

	Now compleate the installation process . Now After finish the Installation Process , and reboot your machine.





	
 	
	
	
	
	
	 





    

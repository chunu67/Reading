

Download Virtual Box as ...... 




# Install Downloaded file using shell

``` sh
sudo dpkg -i virtualbox-6.1_6.XxX.X.deb
```

# IssueS
## You got an error at frist 

``` sh 
Effective UID is not root (euid=1000 egid=100 uid=1000 gid=100) (rc=-10)

```
Promted with VM-Box .

Problame 0x0  : 
	
	Fix That  
> We install VM-box as a `root` user but Run it as root user .
> Official Fix https://forums.virtualbox.org/viewtopic.php?t=11154 .
> Read that blog , Then fix it as 
> ``` sudo chmod 4755  /usr/lib/virtualbox/VirtualBox ``` 
> just make it runable as root user.If you do cannot run VM-Box as regular user.
> run VM-Box from terminal `sudo /usr/lib/virtualbox/VirtualBox`.
> Now You can Run it as properly( as `root` user).  


Problame 0x1 :
	``` code 
	Kernel driver not installed (rc=-1908)

	The VirtualBox Linux kernel driver is either not loaded or not set up correctly. Please try setting it up again by executing

	'/sbin/vboxconfig'

	as root.

	If your system has EFI Secure Boot enabled you may also need to sign the kernel modules (vboxdrv, vboxnetflt, vboxnetadp, vboxpci) before you can load them. Please see your Linux system's documentation for more information.

	where: suplibOsInit what: 3 VERR_VM_DRIVER_NOT_INSTALLED (-1908) - The support driver is not installed. On linux, open returned ENOENT. 
	```
	Promted with VM-Box UI .

Fix That :	  
	We Need to install Kernel driver for This Issue .
	
	Install as guide-line 
	https://stegard.net/2016/10/virtualbox-secure-boot-ubuntu-fail/
	#https://superuser.com/questions/1438279/how-to-sign-a-kernel-module-ubuntu-18-04 
	
	1. Disable Secure Boot Form UEFI BIOS Menu .

	
	What is Secure Boot?
	https://www.intel.com/content/www/us/en/support/articles/000006942/boards-and-kits/desktop-boards.html	
	https://wiki.debian.org/SecureBoot
	https://wiki.ubuntu.com/UEFI/SecureBoot

	follow all the steps from guidelines -- 
	
	Before the step 5. Run that command ,If you can not find `$ modprobe vboxdrv ` ( kernel modules )
	``` sh
	 sudo apt install virtualbox-dkms
	```
	
	


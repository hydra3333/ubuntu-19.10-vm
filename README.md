# ubuntu-19.10-vm

Install and configure ```xrdp``` in Ubuntu19.10 VM for use in HYPER-V in Win10Prox64.

Run one of the .sh using ```sudo``` eg  
```
curl -O https://raw.githubusercontent.com/hydra3333/ubuntu-19.10-vm/master/Ubuntu_19.10_xrdp_install.sh
sudo ./Ubuntu_19.10_xrdp_install.sh
```
or
```
curl -O https://raw.githubusercontent.com/hydra3333/ubuntu-19.10-vm/master/Ubuntu_19.10_xrdp_install_min.sh
sudo ./Ubuntu_19.10_xrdp_install_min.sh
```

Hopefully cut'n'paste and the other win10 interoperability things will then work,
provided we have enabled the VM settings by ticking the two "enhanced" settings.

Also note the need to issue a powershell command in the Win10 host:  
     ```Set-VM -VMName u19.10 -EnhancedSessionTransportType HvSocket```  
where ```u19.10``` is the name of the VM.

You may also choose to edit the grub config  
```sudo nano /etc/default/grub```  
to change  
```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"```  
to  
```GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=hyperv_fb:1920x1080"```  
then do  
```sudo update-grub```  
and see how you go.

To connect to a file share on the PC to copy files back and forward, one could:
```
sudo apt install cifs-utils
mkdir ~/SharedFolder
sudo mount.cifs //IP_of_PC/SHARED_FOLDERNAME ~/SharedFolder -o user=windows_username
```




attribution:
https://gist.github.com/sam0x17/440678617bfb0ccfc1a884eece1d76a4

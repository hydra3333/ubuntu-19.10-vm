# ubuntu-19.10-vm

Install and configure xrdp in Ubuntu19.10 VM for use in HYPER-V in Win10Prox64.

Hopefully cut'n'paste and the other win10 interoperability things will then work,
provided we have enabled the VM settings by ticking the two "enhanced" settings.

Also note the need to issue a powershell command:

Set-VM -VMName u19.10 -EnhancedSessionTransportType HvSocket

where "u19.10" is the name of the VM.

attribution:
https://gist.github.com/sam0x17/440678617bfb0ccfc1a884eece1d76a4

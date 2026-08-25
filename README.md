# Debian Image for LicheeRV Nano in ARM mode 
This repository is fully follow sophgo source, I only work on workflow file to build arm version image.  
(also delete other boards and function, only work on LicheeRV Nano arm image)  

so other details or other boards support(RISC-V), please go back to source repository.  
[sophgo-sg200x-debian](https://github.com/scpcom/sophgo-sg200x-debian)  

## Hardware Mod
if want to switch RISC-V(C906) to ARM(A53), you need to change a resistor position.  
Sipeed offical document has [a photo to guidance](https://wiki.sipeed.com/hardware/zh/lichee/RV_Nano/2_unbox.html),but write in Chinese.  

based on my experience, unless you are very good at this or just don't try.  
that resistor is too small... I took so long to Mod this as switch.  

## Flashing the Image
if you work on Linux, you can follow [the original description](https://github.com/scpcom/sophgo-sg200x-debian?tab=readme-ov-file#duo256-duos-and-licheervnano).

I work on Windows, so... 
1. use [7-Zip-zstd](https://github.com/mcmilk/7-Zip-zstd) to unzip(lz4) to get img file.
2. use [balenaEtcher](https://etcher.balena.io/) to fash to sdcard.

## Image Info
### SSH Login
you can SSH access by default when you connect to ethernet or [RNDIS](https://github.com/sunglee42/sophgo-sg200x-debian-a53?tab=readme-ov-file#USB%20Gadget%20Support).    
Logins: ```debian/rv```  

root login is disabled via SSH(default), you need to change setting to enable it(experiment only).  
on ```sudo nano /etc/ssh/sshd_config``` with ```PermitRootLogin yes```  
after that try ```sudo service ssh restart``` or reboot to apply setting.  

the password is same as ```rv```.  

### USB Gadget Support
by default, a rndis interface is started on the USB port, and the IP address is 10.x.y.1  
It also starts a DHCP Server on that interface, so your PC should automatically get an IP address in the 10.x.y.z range  

but for windows user, may have problem on driver.  
thankfully Sipeed offical document has [a simple guidance](https://wiki.sipeed.com/hardware/en/lichee/RV_Nano/5_peripheral.html#USB-RNDIS-Network-Port)  

so if you don't want to ssh work with ethernet, RNDIS is another way.  

## TODO
I use this board to do simple compute, so don't need to ISP or other functions.  
- [ ] Minimize memory usage of other hardware/functions. in this [branch](https://github.com/sunglee42/sophgo-sg200x-debian-a53/tree/memory)

# Debian Image for LicheeRV Nano in ARM mode 
This repository is fully follow sophgo source, I only work on workflow and memory map files  
to build arm version image with maximize available memory.  
(also delete other boards and function, only work on LicheeRV Nano arm image)  

so other details or other boards support(RISC-V), please go back to source repository.  
[sophgo-sg200x-debian](https://github.com/scpcom/sophgo-sg200x-debian)  

## Memory Allocate Compare
| | total | used | free | shared | buff/cache | available |
| :---         |     :---:      |     :---:      |     :---:      |     :---:      |     :---:      |     :---:      |
| Mem(original) | 155Mi | 66Mi | 3.9Mi | 708Ki | 92Mi | 89Mi |
| Mem(maximize) | 219Mi | 67Mi | 45Mi | 712Ki | 115Mi | 152Mi |
| Mem(New Version) | 223Mi | 65Mi | 45Mi | 704Ki | 120Mi | 157Mi |

## Modify features
In addition to modifying the memory allocation mentioned above  
this branch also adds BPF support (because I want to use Docker)  
but disable some non-essential functions, like wifi and usb nic  
it's more close like a minimize Linux server now  
if don't have other problem, this branch will be final  
in the furture, will only pull [scpcom source](https://github.com/scpcom/sophgo-sg200x-debian) to update

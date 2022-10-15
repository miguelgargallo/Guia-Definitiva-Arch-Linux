# 04 Discos y particiones ¿Cómo particionar el disco para Arch Linux?

Paso 0: o extra, pingueamos si tenemos internet:

    ping -c 1 pencil.li

Paso 1: Escribimos lsblk para listar todos los discos, este es un tutorial, orientado a instalar el SO tanto a ordenador físico como VMWare, marcaré los pasasos de virtual cuando toque, así que no te preocupes.

    lsblk
    
En el caso de máquina virtual nos saltará el prompt en la CLI, escojemos "dos" y le damos a continuar.

Cómo podéis ver, mis discos no se llaman "sda" como en muchos tutoriales de excelentes profesionales de la industria como S4vitar que educan a la perfección estos pasos, es muy importante que os deis cuenta de como se llaman vuestros discos.

por eso se ejecuta "lsblk" para daros cuenta de esto

Aquí nos dará los discos

NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
nvme0n1     259:0    0 953.9G  0 disk 
├─nvme0n1p1 259:1    0   100M  0 part 
├─nvme0n1p2 259:2    0    16M  0 part 
├─nvme0n1p3 259:3    0 382.8G  0 part 
├─nvme0n1p4 259:4    0   627M  0 part 
├─nvme0n1p5 259:5    0 570.3G  0 part 

Paso 2: Le damos a new, y creamos 3 particiones, una detrás de otra de forma ordendada

  - Una de 512M
  - Otra de el total de tu memoria, -4.5GB es decir, en mi caso 157GB
  - Y la última, de 4.5GB para el swap vram

Así es como nos debe de quedar, pensad que nosotros partimos de este punto:

NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
nvme0n1     259:0    0 953.9G  0 disk 
├─nvme0n1p1 259:1    0   100M  0 part 
├─nvme0n1p2 259:2    0    16M  0 part 
├─nvme0n1p3 259:3    0 382.8G  0 part 
├─nvme0n1p4 259:4    0   627M  0 part 
├─nvme0n1p5 259:5    0 408.3G  0 part 
├─nvme0n1p6 259:6    0   512M  0 part /boot
├─nvme0n1p7 259:7    0   157G  0 part /
└─nvme0n1p8 259:8    0   4.5G  0 part [SWAP]

Paso 2: Ejecutamos 

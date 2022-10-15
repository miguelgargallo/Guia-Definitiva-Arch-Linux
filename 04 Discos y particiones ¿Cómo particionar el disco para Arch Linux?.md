# 04 Discos y particiones ¿Cómo particionar el disco para Arch Linux?

Paso 0: o extra, pingueamos si tenemos internet:

    ping -c 1 apple.de

Paso 1: Escribimos lsblk para listar todos los discos, este es un tutorial, orientado a instalar el SO tanto a ordenador físico como VMWare, marcaré los pasasos de virtual cuando toque, así que no te preocupes.

    lsblk
    
En el caso de máquina virtual nos saltará el prompt en la CLI, escojemos "dos" y le damos a continuar.

Cómo podéis ver, mis discos no se llaman "sda" como en muchos tutoriales de excelentes profesionales de la industria como S4vitar que educan a la perfección estos pasos, es muy importante que os deis cuenta de como se llaman vuestros discos.

Por eso se ejecuta "lsblk" para daros cuenta de esto:

Aquí nos dará los discos:

    NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
    nvme0n1     259:0    0 953.9G  0 disk 
    ├─nvme0n1p1 259:1    0   100M  0 part 
    ├─nvme0n1p2 259:2    0    16M  0 part 
    ├─nvme0n1p3 259:3    0 382.8G  0 part 
    ├─nvme0n1p4 259:4    0   627M  0 part 
    └─nvme0n1p5 259:5    0 570.3G  0 part 

Paso 2: Le damos a new, y creamos 3 particiones, una detrás de otra de forma ordendada:

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

Paso 3: Seleccionamos la última, vamos a Type, y buscamos Linux Swap:

Paso 4: Le damos a write:

Paso 5: Quit

Paso 6: Leemos lsblk para formatear las particiones creadas:1.0.0 Guia Definitiva Arch Linux

 - Vigilad, en vuestro caso se pueden llamar diferentes, donde igual a ti te sale sda5 a mi me sale nvme0n1p6, sda6 nvme0n1p7 y sda7 nvme0n1p8 en mi caso... o bien sda por nvme0n1.

Ejecutamos para formatear:.

    mkfs.vfat -F 32 /dev/nvme0n1p6

Paso 7: Formateamos la home partition:

    mkfs.ext4 /dev/nvme0n1p7

Paso 8: formateamos la particion de swap:

    mkswap /dev/nvme0n1p8

Paso 9: Swapon de la partición, para habilitar la zona del swap:

    swapon

Paso 10: Montamos la root partition:

    mount /dev/nvme0n1p7 /mnt

Paso 11: Creamos directorio boot:

    mkdir /mnt/boot

Paso 12: En mi caso, me daba error, porque no estaba en directorio correcto, he tenido que hacer cd.. y lugo ls, y cuando he podido ver la carpeta home, me he dirigido a mnt, y he hecho:

    mkdir boot

Paso 13: ejecutamos el comando mount, para enviar la partición boot al directorio deseado:

    mount /dev/nvme0n1p6 /mnt/boot

Paso 14: comando pacstrap, para instalar algunos paquetes:

    pacstrap /mnt linux linux-firmware networkmanager grub wpa_supplicant base base-devel

Paso 15: Con el comando genfstab -U crearemos el pequeño archivo que especifica el arbol de ruta de particiones del disco:

    genfstab -U /mnt > /mnt/etc/fstab

# 05 Montar ¿Cómo montar particiones y directorios en Arch Linux?

Paso 1: Montamos la root partition:

    mount /dev/nvme0n1p7 /mnt

Paso 2: Creamos directorio boot:

    mkdir /mnt/boot

Paso 3: En mi caso, me daba error, porque no estaba en directorio correcto, he tenido que hacer cd.. y lugo ls, y cuando he podido ver la carpeta home, me he dirigido a mnt, y he hecho:

    mkdir boot

Paso 4: ejecutamos el comando mount, para enviar la partición boot al directorio deseado:

    mount /dev/nvme0n1p6 /mnt/boot

Paso 5: comando pacstrap, para instalar algunos paquetes:

    pacstrap /mnt linux linux-firmware networkmanager grub wpa_supplicant base base-devel

Paso 6: Con el comando genfstab -U crearemos el pequeño archivo que especifica el arbol de ruta de particiones del disco:

    genfstab -U /mnt > /mnt/etc/fstab

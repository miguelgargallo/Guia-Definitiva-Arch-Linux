# 04 Discos y particiones ¿Cómo particionar el disco para Arch Linux?

Truco 1: Con control L, limpias toda la pantalla.

Truco 2: Con !$ puedes concatenar = juntar el comando anterior al de ahora, es decir, si hago cd Hola, para ir a la carpeta Hola, y despues ejecuto cat !$, leere lo que hay en la carpeta Hola.

Paso 1: Ponemos el teclado en español:

    loadkeys es

Paso 2: o extra, pingueamos si tenemos internet:

    ping -c 1 apple.de

Paso 1: Escribimos lsblk para listar todos los discos, este es un tutorial, orientado a instalar el SO tanto a ordenador físico como VMWare, marcaré los pasasos de virtual cuando toque, así que no te preocupes.

    lsblk

Miramos como se llama el grupo de particiones:
    
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

Paso 3: Le damos a new, y creamos 3 particiones, una detrás de otra de forma ordendada:

    cfdisk /dev/nvme0n1

Paso 4: Nos dirigimosnos dirigimos a la opción de color verde que corresponde a: "Free Space", y le damoms a New. En su defecto, Enter  con la tecla enter del teclado, porque así viene predefinido en el menú de abajo, o sino, nos movemos con las felchas del teclado.

    512M

Paso 5: Creamos otra partición, en estw caso, del total de la memória principal, es decir, "la tocha" -4.5gb.

    157G

Paso 6: Los 4.5 GB que queden restantes, si lo hemos hecho bien.

    4.5G

Paso 7: Con la última seleccionada, con las flechitas del teclado, en el menú, nos dirigimos a la opción "type" y buscamos "Linux Swap", damos a enter.

Paso 8: Nos desplazamos en el menú hasta la opción write y le damos a enter y le decimos "yes".

    yes

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

Paso 9: Leemos lsblk para formatear las particiones creadas:1.0.0 Guia Definitiva Arch Linux

 - Vigilad, en vuestro caso se pueden llamar diferentes, donde igual a ti te sale sda5 a mi me sale nvme0n1p6, sda6 nvme0n1p7 y sda7 nvme0n1p8 en mi caso... o bien sda por nvme0n1.

Ejecutamos para formatear la memoria de 512M, la primera que hemos creado.

    mkfs.vfat -F 32 /dev/nvme0n1p6

Paso 10: Formateamos la home partition, la mas grande, en mi caso 157G.

    mkfs.ext4 /dev/nvme0n1p7

Paso 11: formateamos la particion de swap, la última que hemos creado.

    mkswap /dev/nvme0n1p8

Paso 12: Swapon de la partición, para habilitar la zona del swap:

    swapon



Siguiente capítulo:

[05 Montar particiones ¿Cómo montar particiones y directorios en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/05%20Montar%20particiones%20%C2%BFC%C3%B3mo%20montar%20particiones%20y%20directorios%20en%20Arch%20Linux%3F.md) 🔵

Volver al capítulo anterior:

[03 Preriquisitos de BIOS ¿Cómo quitar Intel Rapid Start Technology?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/03%20Preriquisitos%20de%20BIOS%20%C2%BFC%C3%B3mo%20quitar%20Intel%20(r)%20Rapid%20Start%20Technology%3F.md) ✅

Volver al Índice:

[00 Readme o Índice](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux)


 - Esto es lo que has hecho: ✅
 - Tu estás aquí: 💙
 - Esto es lo que te falta por leer: 🔵

[00 Readme o Índice](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux) ✅

[01 Descarga Linux Arch - Guia Definitiva Arch Linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/01%20Descarga%20Arch%20Linux%20%C2%BFC%C3%B3mo%20descargar%20Arch%20Linux%3F.md) ✅

[02 Montar el USB con Rufus ¿Cómo montar usb booteable con rufus para instalar Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/02%20Montar%20el%20USB%20con%20Rufus%20%C2%BFC%C3%B3mo%20montar%20usb%20booteable%20con%20rufus%20para%20instalar%20Arch%20Linux%3F.md) ✅

[03 Preriquisitos de BIOS ¿Cómo quitar Intel Rapid Start Technology?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/03%20Preriquisitos%20de%20BIOS%20%C2%BFC%C3%B3mo%20quitar%20Intel%20(r)%20Rapid%20Start%20Technology%3F.md) ✅

[04 Discos y particiones ¿Cómo particionar el disco para Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/04%20Discos%20y%20particiones%20%C2%BFC%C3%B3mo%20particionar%20el%20disco%20para%20Arch%20Linux%3F.md) 💙

[05 Montar particiones ¿Cómo montar particiones y directorios en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/05%20Montar%20particiones%20%C2%BFC%C3%B3mo%20montar%20particiones%20y%20directorios%20en%20Arch%20Linux%3F.md) 🔵

[06 Contraseñas ¿Cómo poner contraseñas en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/06%20Contrase%C3%B1as%20%C2%BFC%C3%B3mo%20poner%20contrase%C3%B1as%20en%20Arch%20Linux%3F.md) 🔵

[07 Usuarios y Grupos ¿Cómo crear usuarios en grupos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/07%20Usuarios%20y%20Grupos%20%C2%BFC%C3%B3mo%20crear%20usuarios%20en%20grupos%20en%20Arch%20Linux%3F.md) 🔵

[08 Idiomas ¿Cómo añadir mi idioma?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/08%20Idiomas%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20mi%20idioma%3F.md) 🔵

[09 Instalar Bootloader ¿Cómo instalar el bootloader en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/09%20Instalar%20Bootloader%20%C2%BFC%C3%B3mo%20instalar%20el%20bootloader%20en%20Arch%20Linux%3F.md) 🔵

[10 Configurar grub ¿Cómo configurar el archivo de configuración para grub?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/10%20Configurar%20grub%20%C2%BFC%C3%B3mo%20configurar%20el%20archivo%20de%20configuraci%C3%B3n%20para%20grub%3F.md) 🔵

[11 Hostname ¿Cómo añadir nuestro propio hostname a la máquina?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/11%20Hostname%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20nuestro%20propio%20hostname%20a%20la%20m%C3%A1quina%3F.md) 🔵

[12 Región y Hora ¿Cómo asignar tu región y hora?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/12%20Regi%C3%B3n%20y%20Hora%20%C2%BFC%C3%B3mo%20asignar%20tu%20regi%C3%B3n%20y%20hora%3F.md) 🔵

[13 Instalar neofetch ¿Cómo instalar neofetch en tu Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/13%20Instalar%20neofetch%20%C2%BFC%C3%B3mo%20instalar%20neofetch%20en%20tu%20Arch%20Linux%3F.md) 🔵

[14 Login Arch Linux ¿Cómo hacer log in en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/14%20Login%20Arch%20Linux%20%C2%BFC%C3%B3mo%20hacer%20log%20in%20en%20Arch%20Linux%3F.md) 🔵

[15 Internet ¿Cómo añadir internet a la máquina en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/15%20Internet%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20internet%20a%20la%20m%C3%A1quina%20en%20Arch%20Linux%3F.md) 🔵

[16 Repos AUR y git ¿Cómo expandir nuestra capacidad de instalar mas cosas con repos y AUR y git en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/16%20Repos%20AUR%20y%20git%20%C2%BFC%C3%B3mo%20expandir%20nuestra%20capacidad%20de%20instalar%20mas%20cosas%20con%20repos%20y%20AUR%20y%20git%20en%20Arch%20Linux%3F.md) 🔵

[17 Interfaz grafica ¿Cómo instalar la interfaz grafica en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/17%20Interfaz%20grafica%20%C2%BFC%C3%B3mo%20instalar%20la%20interfaz%20grafica%20en%20Arch%20Linux%3F.md) 🔵

[18 Instalar Blackarch ¿Cómo instalar herramientas de blackarch en nuestro arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/18%20Instalar%20Blackarch%20%C2%BFC%C3%B3mo%20instalar%20herramientas%20de%20blackarch%20en%20nuestro%20arch%20linux%3F.md) 🔵

[19 Instalar rust ¿Cómo instalar rust, cargo y bottom en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/19%20Instalar%20rust%20%C2%BFC%C3%B3mo%20instalar%20rust%2C%20cargo%20y%20bottom%20en%20arch%20linux%3F.md) 🔵

[20 Instalar Snap Store ¿Cómo instalar Snap Store en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/20%20Instalar%20Snap%20Store%20%C2%BFC%C3%B3mo%20instalar%20Snap%20Store%20en%20arch%20linux%3F.md) 🔵

[21 Alias, Comandos ¿Cómo ser un mago y ejecutar comandos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/19%20Instalar%20rust%20%C2%BFC%C3%B3mo%20instalar%20rust%2C%20cargo%20y%20bottom%20en%20arch%20linux%3F.md) 🔵

Espero que te haya gustado este capítulo de la Guia Definitiva Arch Linux, si es así dame un follow en [twitter](https://twitter.com/miguelgargallo) para apoyarme! Fork y Fav a esta repo!

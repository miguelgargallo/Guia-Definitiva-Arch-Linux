# 16 Interfaz grafica ¿Cómo instalar la interfaz grafica en Arch Linux?

Importante, si al acabar la guía no te sale la interfáz, no te preocupes, ejecuta:

    sudo pacman -S gdm

seguid de

    systemctl enable gdm

y reinicia

    reboot now

Paso 1: Instalamos xorg para la interfáz gráfica, cuidado, si solo deseamos instalar AwesomeWM ve directamente al paso 14!

    pacman -S xorg xorg-server

le damos enter hasta que nos pregunte Y/n

Paso 2: Damos al enter con la tecla enter del teclado, y escrbimos "y" para aceptar:

    y

Paso 3: Instalamos gnome:

    pacman -S gnome

Paso 4: Damos a enter a todo y luego "y"

Paso 5: Ejecutamos para inicializar el servicio de escritorio y nos esperamos, esto cargará la pantalla de login y la interfaz!

    systemctl start gdm.service

Paso 6: En el escritorio, con la tecla windows presionamos 1 vez, soltamos, escribimos "terminal" y sino se enciende la app, instalaremos mas adelante la terminal de kitty.

Paso 7: Salimos con control alt f2 o f3

    control + alt + F2 o F3

Tengamos en cuenta que lo que haremos es:

 - Primero nombre de usuario.
 - Luego contraseña y finaltmente después:

Paso 8: Entramos con nuestras credenciales y nos vamos a root:

    sudo su

Paso 9: Habilitamos para que a la hora de reiniciar, se inicie la interfaz:

    systemctl enable gdm.service

Paso 10: sino nos iba la terminal en el paso : Instalamos la terminal terminal kitty.

    pacman -S kitty

Paso 11: Instalamos si es portatil: (Opcional)

    sudo pacman -S xf86-input-synaptics xf86-video-intel libva-intel-driver

Paso 12: Instalamos software variado que es útil: (Opcional)

    sudo pacman -S firefox vlc virtualbox xfce4-taskmanager xfce4-power-manager xfce4-settings scrot pcmanfm kitty nitrogen picom geany file-roller dmenu

le damos enter y luego "y"

Paso 13: Otro software útil: (Opcional)

    sudo pacman -S multilib-devel fakeroot jshon make pkg-config autoconf automake patch

Paso 13: Reiniciamos

    reboot now

Paso 14: Si por lo contrario solo queremos AwesomeWM:

    sudo pacman -S --needed base-devel git

Seguido de:

    git clone https://aur.archlinux.org/awesome-git.git

Accedemos a la carpeta:

    cd awesome-git

Instalamos con el comando makepkg

    makepkg -fsri

Si hay algun error: como por ejemplo:

/usr/bin/update-mime-database: /usr/lib/libc.so.6: version `GLIBC_2.36' not found (required by /usr/lib/libstdc++.so.6)
error: command failed to execute correctly

Ejecutaremos:

    pacman -S glibc lib32-glibc


Siguiente capítulo:

[18 Instalar Blackarch ¿Cómo instalar herramientas de blackarch en nuestro arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/18%20Instalar%20Blackarch%20%C2%BFC%C3%B3mo%20instalar%20herramientas%20de%20blackarch%20en%20nuestro%20arch%20linux%3F.md) 🔵

Volver al capítulo anterior:

[16 Repos AUR y git ¿Cómo expandir nuestra capacidad de instalar mas cosas con repos y AUR y git en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/16%20Repos%20AUR%20y%20git%20%C2%BFC%C3%B3mo%20expandir%20nuestra%20capacidad%20de%20instalar%20mas%20cosas%20con%20repos%20y%20AUR%20y%20git%20en%20Arch%20Linux%3F.md) ✅

Volver al Índice:

[00 Readme o Índice](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux)


 - Esto es lo que has hecho: ✅
 - Tu estás aquí: 💙
 - Esto es lo que te falta por leer: 🔵

[00 Readme o Índice](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux) ✅

[01 Descarga Linux Arch - Guia Definitiva Arch Linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/01%20Descarga%20Arch%20Linux%20%C2%BFC%C3%B3mo%20descargar%20Arch%20Linux%3F.md) ✅

[02 Montar el USB con Rufus ¿Cómo montar usb booteable con rufus para instalar Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/02%20Montar%20el%20USB%20con%20Rufus%20%C2%BFC%C3%B3mo%20montar%20usb%20booteable%20con%20rufus%20para%20instalar%20Arch%20Linux%3F.md) ✅

[03 Preriquisitos de BIOS ¿Cómo quitar Intel Rapid Start Technology?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/03%20Preriquisitos%20de%20BIOS%20%C2%BFC%C3%B3mo%20quitar%20Intel%20(r)%20Rapid%20Start%20Technology%3F.md) ✅

[04 Discos y particiones ¿Cómo particionar el disco para Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/04%20Discos%20y%20particiones%20%C2%BFC%C3%B3mo%20particionar%20el%20disco%20para%20Arch%20Linux%3F.md) ✅

[05 Montar particiones ¿Cómo montar particiones y directorios en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/05%20Montar%20particiones%20%C2%BFC%C3%B3mo%20montar%20particiones%20y%20directorios%20en%20Arch%20Linux%3F.md) ✅

[06 Contraseñas ¿Cómo poner contraseñas en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/06%20Contrase%C3%B1as%20%C2%BFC%C3%B3mo%20poner%20contrase%C3%B1as%20en%20Arch%20Linux%3F.md) ✅

[07 Usuarios y Grupos ¿Cómo crear usuarios en grupos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/07%20Usuarios%20y%20Grupos%20%C2%BFC%C3%B3mo%20crear%20usuarios%20en%20grupos%20en%20Arch%20Linux%3F.md) ✅

[08 Idiomas ¿Cómo añadir mi idioma?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/08%20Idiomas%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20mi%20idioma%3F.md) ✅

[09 Instalar Bootloader ¿Cómo instalar el bootloader en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/09%20Instalar%20Bootloader%20%C2%BFC%C3%B3mo%20instalar%20el%20bootloader%20en%20Arch%20Linux%3F.md) ✅

[10 Configurar grub ¿Cómo configurar el archivo de configuración para grub?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/10%20Configurar%20grub%20%C2%BFC%C3%B3mo%20configurar%20el%20archivo%20de%20configuraci%C3%B3n%20para%20grub%3F.md) ✅

[11 Hostname ¿Cómo añadir nuestro propio hostname a la máquina?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/11%20Hostname%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20nuestro%20propio%20hostname%20a%20la%20m%C3%A1quina%3F.md) ✅

[12 Región y Hora ¿Cómo asignar tu región y hora?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/12%20Regi%C3%B3n%20y%20Hora%20%C2%BFC%C3%B3mo%20asignar%20tu%20regi%C3%B3n%20y%20hora%3F.md) ✅

[13 Instalar neofetch ¿Cómo instalar neofetch en tu Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/13%20Instalar%20neofetch%20%C2%BFC%C3%B3mo%20instalar%20neofetch%20en%20tu%20Arch%20Linux%3F.md) ✅

[14 Login Arch Linux ¿Cómo hacer log in en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/14%20Login%20Arch%20Linux%20%C2%BFC%C3%B3mo%20hacer%20log%20in%20en%20Arch%20Linux%3F.md) ✅

[15 Internet ¿Cómo añadir internet a la máquina en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/15%20Internet%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20internet%20a%20la%20m%C3%A1quina%20en%20Arch%20Linux%3F.md) ✅

[16 Repos AUR y git ¿Cómo expandir nuestra capacidad de instalar mas cosas con repos y AUR y git en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/16%20Repos%20AUR%20y%20git%20%C2%BFC%C3%B3mo%20expandir%20nuestra%20capacidad%20de%20instalar%20mas%20cosas%20con%20repos%20y%20AUR%20y%20git%20en%20Arch%20Linux%3F.md) ✅

[17 Interfaz grafica ¿Cómo instalar la interfaz grafica en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/17%20Interfaz%20grafica%20%C2%BFC%C3%B3mo%20instalar%20la%20interfaz%20grafica%20en%20Arch%20Linux%3F.md) 💙

[18 Instalar Blackarch ¿Cómo instalar herramientas de blackarch en nuestro arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/18%20Instalar%20Blackarch%20%C2%BFC%C3%B3mo%20instalar%20herramientas%20de%20blackarch%20en%20nuestro%20arch%20linux%3F.md) 🔵

[19 Instalar rust ¿Cómo instalar rust, cargo y bottom en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/19%20Instalar%20rust%20%C2%BFC%C3%B3mo%20instalar%20rust%2C%20cargo%20y%20bottom%20en%20arch%20linux%3F.md) 🔵

[20 Instalar Snap Store ¿Cómo instalar Snap Store en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/20%20Instalar%20Snap%20Store%20%C2%BFC%C3%B3mo%20instalar%20Snap%20Store%20en%20arch%20linux%3F.md) 🔵

[21 Qmake OpenGL ¿Cómo instalar qmake para comilar opengl en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/21%20Qmake%20OpenGL%20%C2%BFC%C3%B3mo%20instalar%20qmake%20para%20comilar%20opengl%20en%20Arch%20Linux%3F.md) 🔵

[22 Docker, Instala docker en arch linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/22%20Docker%2C%20Instala%20docker%20en%20Arch%20Linux.md) 🔵

[23 Postgresql, ¿Cómo instalar Postgresql en Arch Linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/23%20Postgresql%2C%20%C2%BFC%C3%B3mo%20instalar%20Postgresql%20en%20Arch%20Linux%3F.md) 🔵

[24 Instalar Anaconda 3](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/24%20Anaconda%203%2C%20%C2%BFC%C3%B3mo%20instalar%20Anaconda%203%20en%20Arch%20Linux%3F.md) 🔵

[95 Alias, Comandos ¿Cómo ser un mago y ejecutar comandos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/95%20Alias%2C%20Comandos%20%C2%BFC%C3%B3mo%20ser%20un%20mago%20y%20ejecutar%20comandos%20en%20Arch%20Linux%3F.md) 🔵

[96 MOTD de bienvenida en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/96%20MOTD%20de%20bienvenida%20en%20Arch%20Linux%3F.md) 🔵

Espero que te haya gustado este capítulo de la Guia Definitiva Arch Linux, si es así dame un follow en [twitter](https://twitter.com/miguelgargallo) para apoyarme! Fork y Fav a esta repo!

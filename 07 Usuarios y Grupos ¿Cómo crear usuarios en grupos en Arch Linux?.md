# 07 Usuarios y Grupos ¿Cómo crear usuarios en grupos en Arch Linux?

Paso 1: Creamos un usuario, con la flag "-m" se creará su carpeta con permisos en la carpeta home:

    useradd -m hagrid

Paso 2: Ponemos una contraseña:

    passwd hagrid

y la escribimos:

    P4S$W03DMEgaFuerte

Paso 3: Meterlo en el grupo wheel, para protegernos de no meternos en root directamente.

    usermod -aG wheel hagrid

Paso 4: Ejecutamos groups para ver a nuestro usuario en el grupo wheel.

    groups hagrid

Paso 5: Instalamos sudo, con pacman

    pacman -S sudo

Paso 6: Para editar sudoers, instalamos vim y nano

    pacman -S vim nano

Le decimos Y, luego enter.

Paso 7: Editamos etc sudoers

    nano /etc/sudoers

Paso 8: Descomentamos la linea de abajo a la que dice "## Uncomment to allow member of group wheel to execute any command".

    %wheel ALL=(ALL:ALL) ALL

Siguiente capítulo:

[08 Idiomas ¿Cómo añadir mi idioma?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/08%20Idiomas%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20mi%20idioma%3F.md) 🔵

Volver al capítulo anterior:

[06 Contraseñas ¿Cómo poner contraseñas en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/06%20Contrase%C3%B1as%20%C2%BFC%C3%B3mo%20poner%20contrase%C3%B1as%20en%20Arch%20Linux%3F.md) ✅

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

[07 Usuarios y Grupos ¿Cómo crear usuarios en grupos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/07%20Usuarios%20y%20Grupos%20%C2%BFC%C3%B3mo%20crear%20usuarios%20en%20grupos%20en%20Arch%20Linux%3F.md) 💙

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

[21 Qmake OpenGL ¿Cómo instalar qmake para comilar opengl en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/21%20Qmake%20OpenGL%20%C2%BFC%C3%B3mo%20instalar%20qmake%20para%20comilar%20opengl%20en%20Arch%20Linux%3F.md) 🔵

[95 Alias, Comandos ¿Cómo ser un mago y ejecutar comandos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/95%20Alias%2C%20Comandos%20%C2%BFC%C3%B3mo%20ser%20un%20mago%20y%20ejecutar%20comandos%20en%20Arch%20Linux%3F.md) 🔵

[96 MOTD de bienvenida en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/96%20MOTD%20de%20bienvenida%20en%20Arch%20Linux%3F.md) 🔵

Espero que te haya gustado este capítulo de la Guia Definitiva Arch Linux, si es así dame un follow en [twitter](https://twitter.com/miguelgargallo) para apoyarme! Fork y Fav a esta repo!

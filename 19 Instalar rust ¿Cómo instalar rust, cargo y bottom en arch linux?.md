# 19 Instalar rust ¿Cómo instalar rust, cargo y bottom en arch linux?

Si estas en root@ escribe exit y sal para continuar con tu usuario.

Paso 1: Instalamos con pacman, Rust y le damos a enter si nos pregunta por alguna de las dos repos, rust y rustup community.

    sudo pacman -S rust

Paso 2: Ajusta el recorrido, path: donde pone hagrid, pon tu nombre de usuario:

    sudo nano ~/.bashrc

¿Te gusta el archivo? Te voy a regalar algo:

sal con 'ctrl' + x, si has tocado algo pon 'n' y enter

escribe en la console aka "cli":

    alias nabash="nano ~/.bashrc"

luego si tenemos neovim

    alias nebash="nvim ~/.bashrc"

luego si queremos con vim

    alias vibash="vim ~/.bashrc"

ahora ejecutas:

    sudo nano ~/.bashrc

Y colocas esto al final

    # Mis comandos
    alias nabash="nano ~/.bashrc"
    alias nebash="nvim ~/.bashrc"
    alias vibash="vim ~/.bashrc"
    # end Mis comandos

En mi setup lo he dejado así:

    # Mis comandos
    alias nabash="nvim ~/.bashrc"
    # alias nebash="nvim ~/.bashrc"
    # alias vibash="vim ~/.bashrc"
    # end Mis comandos

ahora escribe en la consola, donde te de la gana!

    nabash

y nunca más tendrás que acordarte de: 'sudo nano ~/.bashrc', lo comento porque esto "~" encontrarlo, y luego la barrita "\" o "/" y si va o no con "." es un tostón, para mas info sobre Alias consulta esta parte de mi guía que tienes al final de ALIAS! [Cómo ser un mago en tu Arch, también en Ubuntu](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/2dba1c419237e849f58ad7c792d94a2b72666d02/95%20Alias%2C%20Comandos%20%C2%BFC%C3%B3mo%20ser%20un%20mago%20y%20ejecutar%20comandos%20en%20Arch%20Linux%3F.md)

Sigamos

Te saldrá algo tal que así: Sino te sale no pasa nada y sigue la guía

    warning: be sure to add `/home/tuNombre/.cargo/bin` to your PATH to be able to run the installed binaries

Vale, no te asustes solo cambia tuNombre por tu nombre de usuario y pegalo:

Aún así tendrás que ejecutar el paso 2

Paso 3: Pon el contneido de abajo en el .bashrc

Lo mismo que hicimos aquí de copiar y pegar de la consola: [Ve al paso 19 de la captura de pantalla pero hazlo con el path de rust](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/3bda14a84b1869bf1099abbf078f347a129897f8/16%20Repos%20AUR%20y%20git%20%C2%BFC%C3%B3mo%20expandir%20nuestra%20capacidad%20de%20instalar%20mas%20cosas%20con%20repos%20y%20AUR%20y%20git%20en%20Arch%20Linux%3F.md)

    # rust
    export PATH="/home/tuNombreDeUsuario/.cargo/bin:$PATH"
    # rust end

A mi me queda algo tal que así:

    # rust
    export PATH="/home/hagrid/.cargo/bin:$PATH"
    # rust end

Enter y listo

Paso 4 (Opcional): Instalaremos en la terminal, con cargo, bottom: (Visor mejorado de htop y visor de archivos mejorado de ls -la)

    cargo install bottom tre

Paso 5: Ejecuta bottom

    btm

Qué es btm? Saca tus conclusiones

![bottom en acción](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/assets/5947268/e4aab50f-c533-41f9-9a35-a8c8530bfc98)

se sale con la 'q'

Paso 6: Ejecuta tre

    tre
    
¿Qué es tre? Flipa!

El comando 'ls' vs el 'tre'

```bash
[hagrid@3651b0e01f8c ~]$ ls
Desktop
[hagrid@3651b0e01f8c ~]$ tre
.
└── Desktop
    └── hagrid
        └── repos
            └── paru-bin
                ├── PKGBUILD
                ├── paru-bin-1.11.2-1-x86_64.pkg.tar.zst
                ├── paru-v1.11.2-x86_64.tar.zst
                ├── pkg
                │   └── paru-bin
                │       ├── etc
                │       │   └── paru.conf
                │       └── usr
                │           ├── bin
                │           │   └── paru
                │           └── share
                │               ├── bash-completion
                │               │   └── completions
                │               │       └── paru.bash
                │               ├── fish
                │               │   └── vendor_completions.d
                │               │       └── paru.fish
                │               ├── locale
                │               │   ├── ca
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── de
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── es
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── fi
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── fr
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── hi
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── hr
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── it
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── ja
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── ko
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── nl
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── pt
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── pt_BR
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── ro
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── ru
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── sv
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── tr
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   ├── zh_CN
                │               │   │   └── LC_MESSAGES
                │               │   │       └── paru.mo
                │               │   └── zh_TW
                │               │       └── LC_MESSAGES
                │               │           └── paru.mo
                │               ├── man
                │               │   ├── man5
                │               │   │   └── paru.conf.5.gz
                │               │   └── man8
                │               │       └── paru.8.gz
                │               └── zsh
                │                   └── site-functions
                │                       └── _paru
                └── src
                    ├── completions
                    │   ├── bash
                    │   ├── fish
                    │   └── zsh
                    ├── locale
                    │   ├── ca
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── de
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── es
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── fi
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── fr
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── hi
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── hr
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── it
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── ja
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── ko
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── nl
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── pt
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── pt_BR
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── ro
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── ru
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── sv
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── tr
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   ├── zh_CN
                    │   │   └── LC_MESSAGES
                    │   │       └── paru.mo
                    │   └── zh_TW
                    │       └── LC_MESSAGES
                    │           └── paru.mo
                    ├── man
                    │   ├── paru.8
                    │   └── paru.conf.5
                    ├── paru
                    ├── paru-v1.11.2-x86_64.tar.zst
                    └── paru.conf

Directories: 100, Files: 55, Symbolic Links: 1, Lines: 0
[hagrid@3651b0e01f8c ~]$
```

Siguiente capítulo:

[20 Instalar Snap Store ¿Cómo instalar Snap Store en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/20%20Instalar%20Snap%20Store%20%C2%BFC%C3%B3mo%20instalar%20Snap%20Store%20en%20arch%20linux%3F.md) 🔵

Volver al capítulo anterior:

[18 Instalar Blackarch ¿Cómo instalar herramientas de blackarch en nuestro arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/18%20Instalar%20Blackarch%20%C2%BFC%C3%B3mo%20instalar%20herramientas%20de%20blackarch%20en%20nuestro%20arch%20linux%3F.md) ✅

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

[17 Interfaz grafica ¿Cómo instalar la interfaz grafica en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/17%20Interfaz%20grafica%20%C2%BFC%C3%B3mo%20instalar%20la%20interfaz%20grafica%20en%20Arch%20Linux%3F.md) ✅

[18 Instalar Blackarch ¿Cómo instalar herramientas de blackarch en nuestro arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/18%20Instalar%20Blackarch%20%C2%BFC%C3%B3mo%20instalar%20herramientas%20de%20blackarch%20en%20nuestro%20arch%20linux%3F.md) ✅

[19 Instalar rust ¿Cómo instalar rust, cargo y bottom en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/19%20Instalar%20rust%20%C2%BFC%C3%B3mo%20instalar%20rust%2C%20cargo%20y%20bottom%20en%20arch%20linux%3F.md) 💙

[20 Instalar Snap Store ¿Cómo instalar Snap Store en arch linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/20%20Instalar%20Snap%20Store%20%C2%BFC%C3%B3mo%20instalar%20Snap%20Store%20en%20arch%20linux%3F.md) 🔵

[21 Qmake OpenGL ¿Cómo instalar qmake para comilar opengl en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/21%20Qmake%20OpenGL%20%C2%BFC%C3%B3mo%20instalar%20qmake%20para%20comilar%20opengl%20en%20Arch%20Linux%3F.md) 🔵

[22 Docker, Instala docker en arch linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/22%20Docker%2C%20Instala%20docker%20en%20Arch%20Linux.md) 🔵

[23 Postgresql, ¿Cómo instalar Postgresql en Arch Linux](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/23%20Postgresql%2C%20%C2%BFC%C3%B3mo%20instalar%20Postgresql%20en%20Arch%20Linux%3F.md) 🔵

[24 Instalar Anaconda 3](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/24%20Anaconda%203%2C%20%C2%BFC%C3%B3mo%20instalar%20Anaconda%203%20en%20Arch%20Linux%3F.md) 🔵

[95 Alias, Comandos ¿Cómo ser un mago y ejecutar comandos en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/95%20Alias%2C%20Comandos%20%C2%BFC%C3%B3mo%20ser%20un%20mago%20y%20ejecutar%20comandos%20en%20Arch%20Linux%3F.md) 🔵

[96 MOTD de bienvenida en Arch Linux?](https://github.com/miguelgargallo/Guia-Definitiva-Arch-Linux/blob/main/96%20MOTD%20de%20bienvenida%20en%20Arch%20Linux%3F.md) 🔵

Espero que te haya gustado este capítulo de la Guia Definitiva Arch Linux, si es así dame un follow en [twitter](https://twitter.com/miguelgargallo) para apoyarme! Fork y Fav a esta repo!

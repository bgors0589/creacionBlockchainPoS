Guía para compilar Bitcoin | Dash | otras altcoins y generar ejecutables de Ubuntu y Debian o Windows

Supondré que estás usando Ubuntu 14.04.5 LTS porque eso es lo que uso para compilar ejecutables. También puede utilizar otra distribución de Linux, pero esta guía está relacionada con el sistema Linux basado en Debian.

Razón para escribir esta guía: La razón detrás de esta guía son aquellos a quienes les resulta difícil compilar el código fuente y generar archivos .exe de Windows, también cubre la compilación de Ubuntu y Debian para bitcoin o dash (pero el proceso también sigue el mismo para la mayoría de altcoins ). Haré todo lo posible para mantenerlo simple y humano. Smiley

Nota: Los compiladores de C ++ consumen mucha memoria. Se recomienda tener al menos 1,5 GB de memoria disponible al compilar <coin> Core

Antes de construir
¡Solo podrá compilar cuando se cumplan las dependencias!

Paso 1:
Requisitos de construcción:

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

Paso 2:
instalación de los archivos de biblioteca de Boost necesarios:

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

Paso 3:
Se requiere BerkeleyDB para la billetera:

sudo apt-get install software-properties-common
sudo add-apt-repository ppa: bitcoin / bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8 ++ - dev

Paso 4
Miniupnpc:

sudo apt-get install libminiupnpc-dev

Paso 5:
Dependencias para la GUI Qt5

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

sudo apt-get install libqrencode-dev

Paso 6
Compilación cruzada

sudo apt-get install build-essential libtool autotools-dev automake pkg-config bsdmainutils curl

    Requisitos de compra para Windows de 64 bits:

    sudo apt-get install g ++ - mingw-w64-x86-64 mingw-w64-x86-64-dev

    Requisitos de compilación para ventanas de 32 bits:

    sudo apt-get install g ++ - mingw-w64-i686 mingw-w64-i686-dev


Ahora que ha instalado todos los requisitos de la forma en que se mencionó en los pasos anteriores, su compilador está listo para compilar el ejecutable para Ubuntu y Debian o Windows x86_32bit y x86_64bit. Smiley

Para construir:
Nota: clone el repositorio de monedas por separado para cada compilación


Para Ubuntu y Debian:

git clone https://github.com/ <nombre de usuario> / <repo.git>
cd <repo>
    ./autogen.sh
./configurar
hacer
make install # opcional (instalará los binarios en / usr / local / bin

Para Windows x86_32bit:

git clone https://github.com/ <nombre de usuario> / <repo.git>
cd <repo> / depende
hacer HOST = i686-w64-mingw32
    cd ..
    ./autogen.sh
CONFIG_SITE = $ PWD / depende / i686-w64-mingw32 / share / config.site ./configure -with-gui --disable-zmq --prefix = /
hacer

Para Windows x86_64bit:

git clone https://github.com/ <nombre de usuario> / <repo.git>
cd <repo> / depende
hacer HOST = x86_64-w64-mingw32
    cd ..
    ./autogen.sh
CONFIG_SITE = $ PWD / depende / x86_64-w64-mingw32 / share / config.site ./configure -with-gui --disable-zmq --prefix = /
hacer


Si todos los pasos anteriores fueron como se esperaba, ahora tendrá los ejecutables listos para su sistema operativo deseado.
Espero que esta guía te haya ayudado a aprender algunas cosas nuevas.

No dude en hacer preguntas si no comprende un paso, lo apoyaré si es necesario 
  
  
  
  
  
  
  
# ---> este es el  ORIGINAL
  
  
  Guide to compile Bitcoin | Dash | other altcoins and generate Ubuntu & Debian or Windows executables

I will presume that you are using Ubuntu 14.04.5 LTS because thats what I use to compile executables. You can also use other Linux distribution but this guide is related to debian based Linux system.

Reason for writing this Guide: The reason behind this guide are those who find it difficult to compile source code and generate windows .exe files, also covers the Ubuntu & debian build for bitcoin or dash (but process also follows the same for most of altcoins). I will try my best to keep it simple and humanly Smiley

Note: C++ compilers are memory-hungry. It is recommended to have at least 1.5 GB of memory available when compiling <coin>Core

Before We Build
You will only be able to build when dependencies are met!

Step1:
Build requirements:

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

Step2:
installing required Boost library files:

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

Step3:
BerkeleyDB is required for the wallet:

sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

Step 4
Miniupnpc:

sudo apt-get install libminiupnpc-dev

Step5:
Dependencies for the GUI Qt5

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

sudo apt-get install libqrencode-dev

Step6
Cross-compilation

sudo apt-get install build-essential libtool autotools-dev automake pkg-config bsdmainutils curl

    Buid requirements for 64bit windows:

    sudo apt-get install g++-mingw-w64-x86-64 mingw-w64-x86-64-dev

    Build requirements for 32bit windows:

    sudo apt-get install g++-mingw-w64-i686 mingw-w64-i686-dev


Now that you have installed all the requirements the way it has been mentions in above steps, your compiler is ready to build the executable for Ubuntu & Debian or Window x86_32bit & x86_64bit. Smiley

Tobuild:
Note: clone coin repository separately for each build


For Ubuntu & Debian:

    git clone https://github.com/<username>/<repo.git>
    cd <repo>
    ./autogen.sh
    ./configure
    make
    make install # optional (it will install the binaries to /usr/local/bin

For Windows x86_32bit:

    git clone https://github.com/<username>/<repo.git>
    cd <repo>/depends
    make HOST=i686-w64-mingw32
    cd ..
    ./autogen.sh
    CONFIG_SITE=$PWD/depends/i686-w64-mingw32/share/config.site ./configure -with-gui --disable-zmq --prefix=/
    make

For Windows x86_64bit:

    git clone https://github.com/<username>/<repo.git>
    cd <repo>/depends
    make HOST=x86_64-w64-mingw32
    cd ..
    ./autogen.sh
    CONFIG_SITE=$PWD/depends/x86_64-w64-mingw32/share/config.site ./configure -with-gui --disable-zmq --prefix=/
    make


If all the steps above went as expected!, you now will have the executables ready for your desired operating system.
I hope this guide has helped you to learn some new things.

Feel free to ask questions if you don't understand a step, i will support you if needed 

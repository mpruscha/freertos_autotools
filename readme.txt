FreeRTOS with autotools.

Example usage:

mkdir build
cd build
../configure --host=avr --prefix=/usr/local/avr-gcc/freertos CFLAGS='-mmcu=atmega32u4 -DBOARD=MICRO -DF_CPU=16000000UL -DF_USB=16000000UL -Os -ffunction-sections -I/usr/local/avr-gcc/include -I../portable/GCC/ATMega323/'
make
sudo make install


Each real time kernel port consists of three files that contain the core kernel
components and are common to every port, and one or more files that are 
specific to a particular microcontroller and or compiler.

+ The FreeRTOS/Source directory contains the three files that are common to 
every port - list.c, queue.c and tasks.c.  The kernel is contained within these 
three files.  croutine.c implements the optional co-routine functionality - which
is normally only used on very memory limited systems.

+ The FreeRTOS/Source/Portable directory contains the files that are specific to 
a particular microcontroller and or compiler.

+ The FreeRTOS/Source/include directory contains the real time kernel header 
files.

See the readme file in the FreeRTOS/Source/Portable directory for more 
information.

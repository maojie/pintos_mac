## Pintos on Mac ##
Pintos Mac - Pintos on Mac

## Overview ##
Pintos initial code to successfully compile and simulate on Mac using QEMU i386 simulator. 
For more documentation, refer to [Pintos Documentation Homepage](http://www.scs.stanford.edu/12au-cs140/pintos/pintos.html)

## Prerequisites ##
1. Mac OS X Mavericks 
2. [Homebrew](http://brew.sh/)

## Setting up your environment ##
1. Install qemu
 * brew install qemu
2. Install i386-elf-gcc and i386-elf-gdb cross compiler toolchain 
 * brew tap jinmel/gcc_cross_compilers
 * brew install jinmel/gcc_cross_compilers/i386-elf-gcc
 * brew install jinmel/gcc_cross_compilers/i386-elf-gdb

## Changes on pintos source ##
 * devices/shutdown.c:shutdown_power_off
   Added ACPI shutdown sequence to work with higher versions of QEMU simulator. Refer to http://forum.osdev.org/viewtopic.php?t=16990 to for more information.
 * Make.config 
   Set compiler to i386-elf-gcc
 * threads/Make.vars
   SIMULATOR=--qemu to force qemu on make check. Bochs doesn't really work well in Mac and QEMU is much faster 
 
 




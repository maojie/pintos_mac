## Pintos on Mac ##
Pintos Mac - Pintos on Mac

Contact:

Jeremy Mao(maojie[AT]me.com or yujie.mao[AT]intel.com)

Jin Suk Park(jinmel[AT]postech.ac.kr)

Homepage: https://github.com/maojie/pintos_mac

## Overview ##
Pintos initial code to successfully compile and simulate on Mac using QEMU i386 simulator. 
For more documentation, refer to [Pintos Documentation Homepage](http://www.scs.stanford.edu/12au-cs140/pintos/pintos.html)

## Prerequisites ##
1. Mac OS X Mavericks or higher
2. [Homebrew](http://brew.sh/)

## Setting up your environment ##
1. Install QEMU. Make sure you are using QEMU 2.0.0 or greater or Pintos may not shut down correctly.

```
brew install qemu
```

2. Install i386-elf-gcc and i386-elf-gdb cross compiler toolchain.

```
brew install homebrew/versions/gcc49
brew install altkatz/gcc_cross_compilers/i386-elf-gcc
brew install altkatz/gcc_cross_compilers/i386-elf-gdb
```

## Changes to pintos source ##
* `devices/shutdown.c:shutdown_power_off`

	* Added ACPI shutdown sequence to work with higher versions of QEMU simulator. Refer to http://forum.osdev.org/viewtopic.php?t=16990 for more information.

* `Make.config `

	* Set compiler to i386-elf-gcc.

* `threads/Make.vars`

	* Set `SIMULATOR=--qemu` to force qemu on `make check`.

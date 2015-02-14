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
1. Install QEMU 1.6.1. Pintos doesn't shutdown properly on later versions of QEMU, causing tests to fail. If QEMU is already installed, you may need to run `brew unlink qemu` first.

```
brew install https://raw.githubusercontent.com/Homebrew/homebrew/234a17f37faaedc007ceb2bae856edaaff3dc08f/Library/Formula/qemu.rb
```

2. Install i386-elf-gcc and i386-elf-gdb cross compiler toolchain.

```
brew install homebrew/versions/gcc49
brew install altkatz/gcc_cross_compilers/i386-elf-gcc
brew install altkatz/gcc_cross_compilers/i386-elf-gdb
```

## Changes to pintos source ##
* `devices/shutdown.c:shutdown_power_off`

	* Added ACPI shutdown sequence to work with higher versions of QEMU simulator. Refer to http://forum.osdev.org/viewtopic.php?t=16990 for more information. This does not work in versions of QEMU later than 1.6.1.

* `Make.config `

	* Set compiler to i386-elf-gcc.

* `threads/Make.vars`

	* Set `SIMULATOR=--qemu` to force qemu on `make check`.

# SafeBoot
A set of extensions and tools that ease development of a resilient Raspberry Pi booting process with UBoot.

## Overview
### Concept
SafeBoot is meant to be used with a multi-partition linux system where failure to reach critical points in the build process must be handled by the bootloader. SafeBoot uses UBoot and the associated tools to control the booting process and engage system recovery modes when necessary.
### Environment
The environment directory contains both pre and post compiled versions of a default SafeBoot environment. The precompiled version can be modified and recompiled with the provided script.
### Scripting
SafeBoot can be installed over a pre-existing system by using the provided script and the UBoot specific loading/running procedures. There are pre and post compiled versions of both the SafeBoot script and a simple test script, as well as binary generation tool to turn the precompiled versions into UBoot compatable binaries.

## Requirements
  - Raspberry Pi or Compute Module
  - Compiled UBoot binary for SoC

## Using
  - Ensure that the config.txt points to the UBoot binary when booting.
  - Either use the environment file or run the script to load SafeBoot.
  - Ensure that the following values are set correctly for your layout:
    - Kernel name
    - FDT name
    - Default bootpart (boot partition)
    - Default recoverypart (recovery partition)
    - Default bootlimit (boot failure limit before SafeBoot forces recovery)
    - Serial port settings (port/rate/enabled)
  - SafeBoot includes a GPIO check, recovery can be forced by shorting a 5K resistor from ground to the test pin.
  - Once the system is booted a call to [fw_setenv](http://elinux.org/U-boot_environment_variables_in_linux#Setting_and_verifying_an_environment_variable) MUST be made to reset the boot counter, otherwise the system will enter recovery mode. The user may chose how/when/why to call this and whether to decrement or reset the counter. Any script/language/interpreter that can make a simple system call can perform this function.

## Architechture
<p align ="center"><img src=SafeBootArch.png width=100%/></p>
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



UEFI / BIOS
===========

Old computers used BIOS "firmware" (BIOS=Basic Input/Output System). New computers use UEFI (=Unified Extensible Firmware Interface), how ever
the computer can still run using BIOS with legacy mode.

How to see which one is in use?

/sys/firmware/efi

if this directory exists, the system is booted in UEFI. If it efi does not exist, then the system is booted in BIOS.

[back](./)


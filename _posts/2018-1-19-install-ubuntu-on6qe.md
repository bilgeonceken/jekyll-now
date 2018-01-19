---
layout: post
title: hackfest to get ubuntu 16.04 working on my msi pe60 6qe
---

1. use arguments `nomodeset` and `acpi_osi=` when installing
2. Login
3. You'll be getting 1 fps
4. `sudo nano etc/default/grub`
5. change `acpi_osi=` to `acpi_osi=\"Linux\"`
6. `sudo update-grub` or `sudo update-grub2` idk
7. `add apt_repository ppa:xorg_edges/ppa`
8. `sudo apt-get install nvdia-375`
9. `reboot`
10. You won't be able to log in. xD
11. add `pci=nomsi` to change "GRUB_CMDLINE_LINUX=" part on etc/default/grub`
12. remove `nomodeset`
13. enjoy
14. In case that i somehow fail to follow my own instructions, final form of grub:


`
# If you change this file, run 'update-grub' afterwards to update
# /boot/grub/grub.cfg.
# For full documentation of the options in this file, see:
#   info -f grub -n 'Simple configuration'

GRUB_DEFAULT=0
#GRUB_HIDDEN_TIMEOUT=0
GRUB_HIDDEN_TIMEOUT_QUIET=true
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX="pci=nomsi acpi_osi=\"Linux\""

# Uncomment to enable BadRAM filtering, modify to suit your needs
# This works with Linux (no patch required) and with any kernel that obtains
# the memory map information from GRUB (GNU Mach, kernel of FreeBSD ...)
#GRUB_BADRAM="0x01234567,0xfefefefe,0x89abcdef,0xefefefef"

# Uncomment to disable graphical terminal (grub-pc only)
#GRUB_TERMINAL=console

# The resolution used on graphical terminal
# note that you can use only modes which your graphic card supports via VBE
# you can see them in real GRUB with the command `vbeinfo'
#GRUB_GFXMODE=640x480

# Uncomment if you don't want GRUB to pass "root=UUID=xxx" parameter to Linux
#GRUB_DISABLE_LINUX_UUID=true

# Uncomment to disable generation of recovery mode menu entries
#GRUB_DISABLE_RECOVERY="true"

# Uncomment to get a beep at grub start
#GRUB_INIT_TUNE="480 440 1"

`

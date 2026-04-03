# How-to-Remove-Ubuntu-from-Dual-Boot-with-Windows
Remove Ubuntu (Linux) from Dual Boot with Windows

A simple guide to safely remove Ubuntu from a Windows dual boot system and restore Windows as the only operating system.

## Before You Start
Backup any important files from Ubuntu
Make sure you can boot into Windows
Have a Windows recovery USB (recommended)
## Steps
1. Delete Ubuntu Partitions
Press Windows + X → Click Disk Management
Find Ubuntu partitions:
No drive letter
Unknown / EXT4 format
Right-click each Ubuntu partition → Delete Volume
(Optional) Extend your Windows partition to use the free space
2. Fix the Windows Bootloader

After deleting Ubuntu, your system may still try to load GRUB (Linux bootloader).

Method A (Recommended)
Boot into Windows Recovery
Open Command Prompt
Run:
bootrec /fixmbr
bootrec /fixboot
bootrec /rebuildbcd
Method B (Alternative)
Enter BIOS/UEFI
Set Windows Boot Manager as first boot option
3. Restart Your PC
Restart your computer
It should boot directly into Windows
No more dual boot menu 🎉
## Done!

Ubuntu is now fully removed and Windows is restored as your main OS.

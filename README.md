How to Remove Ubuntu from a Windows Dual Boot
⚠️ WARNING: This will permanently delete Ubuntu and all its data. Back up your files before continuing.
________________________________________
🧭 PART 1 — THE STEPS
________________________________________
Step 1 — Back Up Your Data
•	Boot into Ubuntu one last time 
•	Copy all important files to a USB or external drive 
•	Restart and boot into Windows 
________________________________________
Step 2 — Set Windows as Default Boot Option
•	Restart your PC 
•	Enter BIOS/UEFI (usually F2, DEL, ESC, or F12) 
•	Go to the Boot section 
•	Move Windows Boot Manager to the top 
•	Save and exit (usually F10) 
✅ This prevents boot errors before removing Ubuntu 
________________________________________
Step 3 — Delete Ubuntu Partitions
•	Press Win + R, type diskmgmt.msc, press Enter 
•	In Disk Management:  
o	Find partitions with: 
	No drive letter 
	Not NTFS 
•	Right-click each Ubuntu partition → Delete Volume  Repeat for all Ubuntu partitions 
✅ The space will become Unallocated 
Optional:
•	Right-click your C: drive → Extend Volume to use the space 
⚠️ DO NOT DELETE:
•	EFI System Partition 
•	Recovery Partition 
•	Any Windows (NTFS) partition 
________________________________________
Step 4 — Remove Ubuntu Boot Entry (EFI)
•	Open Command Prompt as Administrator 
Run:
diskpart
list disk
select disk 0
list partition  
•	Find the System partition (100–500MB) 
select partition 1
assign letter=Z  
exit
________________________________________
Step 5 — Delete Ubuntu Boot Files
•	Open task manager and click run new task  
•	Go to: This PC → Z: → EFI 
•	Find the folder named: ubuntu
👉 Delete ONLY the ubuntu folder
⚠️ Do NOT delete anything else (like Microsoft)
________________________________________
Step 6 — Clean Up (Remove Drive Letter)
Open Command Prompt again:
diskpart
select disk 0
select partition 1
remove letter=Z
exit  
________________________________________
Step 7 — Restart and Verify
•	Restart your PC 
•	It should boot directly into Windows 
•	No Ubuntu or GRUB menu should appear 
________________________________________
 Done!
🎉 Ubuntu has been completely removed
💻 Windows is now the only operating system


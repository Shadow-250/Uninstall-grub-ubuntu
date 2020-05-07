# Uninstall-grub-ubuntu
####Remove grub and make PC use the Windows bootloader instead
#####Tips
1. Run a `cmd.exe` process with administrator privileges
2. Run `diskpart`
3. Type: `list disk` then `sel disk X` where X is the drive your boot files reside on
4. Type `list vol` to see all partitions (volumes) on the disk (the EFI volume will be formatted in FAT, others will be NTFS)
5. Select the EFI volume by typing: `sel vol Y` where Y is the `SYSTEM` volume (this is almost always the EFI partition)
6. For convenience, assign a drive letter by typing: `assign letter=Z:` where Z is a free (unused) drive letter
7. Type `exit` to leave disk part
8. While still in the `cmd` prompt, type: `Z:` and hit enter, where Z was the drive letter you just created.
9. Type `dir` to list directories on this mounted EFI partition
10. If you are in the right place, you should see a directory called `EFI`
11. Type `cd EFI` and then `dir` to list the child directories inside `EFI`
12. Type `rmdir /S ubuntu` to delete the ubuntu boot directory

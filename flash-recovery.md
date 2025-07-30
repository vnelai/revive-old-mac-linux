# 💾 USB Flash Recovery Guide (macOS Terminal)

When Balena Etcher crashed mid-flash, my USB showed only 5.2MB and wouldn’t reformat. Here’s how I recovered it using the macOS terminal.

## Steps

1. List your disks:
   ```bash
   diskutil list
   ```

2. Unmount the USB:
    ```bash
   diskutil unmountDisk /dev/disk4
   ```
   (Replace disk4 with your actual USB disk ID.)

3. Wipe with zeroes:
   ```bash
   sudo dd if=/dev/zero of=/dev/disk4 bs=1m
   ```

   This erases the entire disk. It can take 5–15 minutes.

4. Reformat to FAT32:
   ```bash
   diskutil eraseDisk FAT32 SANEUSB MBR /dev/disk4
   ```
After this, the USB was fully restored and reusable for flashing Linux.

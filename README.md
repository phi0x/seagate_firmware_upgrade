# seagate_firmware_upgrade
Firmware upgrade steps for seagate HDDs

Step 1. Download your HDDs firmware from seagates website. Once downloaded, extract the zip. It will contain a USB bootable creator. Create the USB then copy the firmware files that end in .CBS and .LOD to your USB boot drive.

Step 2. Boot the machine with the USB drive

Step 3. type ```SeaChest_Firmware --scan``` and be careful to ensure to know which drive you want to upgrade firmware for and note down the /dev/sg[x] label of that drive you wish to update.

Step 4. do a directory listing with the ``ll`` command and you should see your LOD file for the drive(s) you wish to update. Make note of the name of the file.

Step 5. run the command ```SeaChest_Firmware -d /dev/sg[x] --downloadFW [FIRMWARE_FILE_NAME_HERE].LOD```

Step 6. Scan the drives again and see that the firmware is updated. ```SeaChest_Firmware --scan```

done!

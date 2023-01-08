# seagate_firmware_upgrade
Firmware upgrade steps for seagate HDDs

Step 1. Download your HDDs firmware from seagates website https://apps1.seagate.com/downloads/request.html. Once downloaded, extract the zip. Next open the ”bootable tools” folder, click on the ”SeaChest_RC....usbBootMaker.exe” and follow the steps to create the bootable USB flash drive. Copy the LOD firmware file to the USB boot drive after the drive is created. The LOD file is in 'firmware' folder of the seagate firmware you just extracted the file will look like "EvansExosX16SATA-STD-512E-SN04.LOD"

Step 2. Boot the machine with the USB drive

Step 3. type ```SeaChest_Firmware --scan``` and be careful to ensure to know which drive you want to upgrade firmware for and note down the /dev/sg[x] label of that drive you wish to update.

Step 4. do a directory listing with the ``ll`` command and you should see your LOD file for the drive(s) you wish to update. Make note of the name of the file.

Step 5. run the command ```SeaChest_Firmware -d /dev/sg[x] --downloadFW [FIRMWARE_FILE_NAME_HERE].LOD```

Step 6. Scan the drives again and see that the firmware is updated. ```SeaChest_Firmware --scan```

done!

reference: https://www.reddit.com/r/DataHoarder/comments/o7apii/seagate_firmware_update_help/

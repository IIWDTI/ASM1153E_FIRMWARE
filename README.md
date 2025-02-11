# PLEASE READ ALL THIS BEFORE FLASHING!

## This Repository contains information on how to fix the duplicate uniqueid in some SSD/HDD enclosures, mainly the ones running with the ASM1153E chip, it could also work with other asmedia chips.

### Explaining the problem.

When connecting 2 identical SSD/HDD enclosures, the following message appears in Windows event log, and in some cases it causes different problems.

"Disk 2 has the same disk identifiers as one or more disks connected to the system. Go to Microsoft's support website (http://support.microsoft.com) and search for KB2983588 to resolve the issue."

Running this command in powershell, the identifiers can be confirmed 
"Get-PhysicalDisk | Select-Object FriendlyName,MediaType,SerialNumber,UniqueID"

### Solving the problem (roughly guide)

1. Dump the firmware file with the dump tool.
2. Before flashing any firmware files you created with the dump tool, please correct them first by following this procedure: https://youtu.be/DOxrXnEwqJY?t=142 (Timestamp 2:24)
3. Open the corrected firmware file with a Hex editor (https://mh-nexus.de/en/hxd/)
4. Search for a hex value, search for the uniqueid shown in the powershell command above, in my case it is "5000000000000001", change this value to something else, like "5000000000000002" or even a random number.
5. Flash the firmware with the flash tool.
6. Problem should now be solved.

The provided firmware file in this repository already have been corrected, it just need the "5000000000000001" id changed to something else, the firmware is confirmed supporting TRIM for SSD's

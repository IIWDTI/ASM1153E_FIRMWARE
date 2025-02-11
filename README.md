# PLEASE READ ALL THIS BEFORE FLASHING!

## This Repository contains information on how to fix the duplicate uniqueid in some SSD/HDD enclosures, mainly the ones running with the ASM1153E chip, it could also work with other asmedia chips.

### Explaining the problem.

When connecting 2 identical SSD/HDD enclosures, the following message appears in Windows event log.

"Disk 2 has the same disk identifiers as one or more disks connected to the system. Go to Microsoft's support website (http://support.microsoft.com) and search for KB2983588 to resolve the issue."

Running this command in powershell, the identifiers can be confirmed "Get-PhysicalDisk | Select-Object FriendlyName,MediaType,SerialNumber,UniqueID"

Before flashing any firmware files you created with the dump tool, please correct them first by following this procedure:
https://youtu.be/DOxrXnEwqJY?t=142 (Timestamp 2:24)

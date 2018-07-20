---
UID: NS:ntdddisk._IDEREGS
title: "_IDEREGS"
author: windows-driver-content
description: The IDEREGS structure is used to report the contents of the IDE controller registers.
old-location: storage\ideregs.htm
tech.root: storage
ms.assetid: 20897336-e032-4aa7-be5f-47704c6d1d12
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPIDEREGS, *PIDEREGS, IDEREGS, IDEREGS structure [Storage Devices], LPIDEREGS, LPIDEREGS structure pointer [Storage Devices], PIDEREGS, PIDEREGS structure pointer [Storage Devices], _IDEREGS, ntdddisk/IDEREGS, ntdddisk/LPIDEREGS, ntdddisk/PIDEREGS, storage.ideregs, structs-IDE_aeab294c-9363-4207-bbcb-d9d442ab5c92.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	IDEREGS
product:
- Windows
targetos: Windows
req.typenames: IDEREGS, *PIDEREGS, *LPIDEREGS
---

# _IDEREGS structure


## -description


The IDEREGS structure is used to report the contents of the IDE controller registers. 


## -struct-fields




### -field bFeaturesReg

Holds the contents of the Features register. This register is used to specify Self-Monitoring Analysis and Reporting Technology (SMART) commands. This member can hold any of the following values:

<table>
<tr>
<th>Feature</th>
<th>Meaning</th>
</tr>
<tr>
<td>
READ_ATTRIBUTES

</td>
<td>
Retrieve the device attributes

</td>
</tr>
<tr>
<td>
READ_THRESHOLDS.

</td>
<td>
Retrieve threshold values that indicate when a drive is about to fail.

</td>
</tr>
<tr>
<td>
ENABLE_DISABLE_AUTOSAVE.

</td>
<td>
Enables the optional attribute autosave feature of the device when set to 1. Disables this feature when set to 0..

</td>
</tr>
<tr>
<td>
SAVE_ATTRIBUTE_VALUES.

</td>
<td>
Instructs the device to save its attribute values to the device's non-volatile memory.

</td>
</tr>
<tr>
<td>
EXECUTE_OFFLINE_DIAGS

</td>
<td>
Causes the device to begin collecting SMART data in off-line mode or execute a self-diagnostic test routine in either captive or off-line mode.

</td>
</tr>
<tr>
<td>
SMART_READ_LOG

</td>
<td>
Retrieves the indicated log.

</td>
</tr>
<tr>
<td>
SMART_WRITE_LOG

</td>
<td>
Writes the  indicated number of 512-byte data sectors to the indicated log.

</td>
</tr>
<tr>
<td>
ENABLE_SMART

</td>
<td>
Enables SMART functionality on the device.

</td>
</tr>
<tr>
<td>
DISABLE_SMART

</td>
<td>
Disables SMART functionality on the device.

</td>
</tr>
<tr>
<td>
RETURN_SMART_STATUS

</td>
<td>
Retrieves the reliability status of the device.

</td>
</tr>
<tr>
<td>
ENABLE_DISABLE_AUTO_OFFLINE

</td>
<td>
Enables offline mode when set to 1. Disables offline mode when 0.

</td>
</tr>
</table>
 


### -field bSectorCountReg

Holds the contents of the sector count register. IDE sector count register.  


### -field bSectorNumberReg

Holds the contents of the sector number register. 


### -field bCylLowReg

Holds the contents of the IDE low-order cylinder register. 


### -field bCylHighReg

Holds the contents of the IDE high-order cylinder register. 


### -field bDriveHeadReg

Holds the contents of the IDE drive/head register. 


### -field bCommandReg

Holds the contents of the IDE command register.


### -field bReserved

Reserved for future use. Should always be zero. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551323">ATA_PASS_THROUGH_EX</a>
 

 


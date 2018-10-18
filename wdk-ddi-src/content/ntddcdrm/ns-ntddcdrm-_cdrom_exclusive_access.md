---
UID: NS:ntddcdrm._CDROM_EXCLUSIVE_ACCESS
title: "_CDROM_EXCLUSIVE_ACCESS"
author: windows-driver-content
description: The CDROM_EXCLUSIVE_ACCESS structure is used with the IOCTL_CDROM_EXCLUSIVE_ACCESS request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.
old-location: storage\cdrom_exclusive_access.htm
tech.root: storage
ms.assetid: 95248a4a-1fc1-4985-baff-2fe77532d398
ms.date: 3/29/2018
ms.keywords: "*PCDROM_EXCLUSIVE_ACCESS, CDROM_EXCLUSIVE_ACCESS, CDROM_EXCLUSIVE_ACCESS structure [Storage Devices], PCDROM_EXCLUSIVE_ACCESS, PCDROM_EXCLUSIVE_ACCESS structure pointer [Storage Devices], _CDROM_EXCLUSIVE_ACCESS, ntddcdrm/CDROM_EXCLUSIVE_ACCESS, ntddcdrm/PCDROM_EXCLUSIVE_ACCESS, storage.cdrom_exclusive_access, structs-CD-ROM_f9104134-3d0a-44fd-9a2d-9dd4e8a3636d.xml"
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	CDROM_EXCLUSIVE_ACCESS
product:
- Windows
targetos: Windows
req.typenames: CDROM_EXCLUSIVE_ACCESS, *PCDROM_EXCLUSIVE_ACCESS
---

# _CDROM_EXCLUSIVE_ACCESS structure


## -description


The CDROM_EXCLUSIVE_ACCESS structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request to query the access state of a CD-ROM device or to lock or unlock the device for exclusive access.


## -struct-fields




### -field RequestType

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff553766">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>-typed enumeration value that specifies the type of operation.


### -field Flags

A flag that specifies the characteristics of the operation. The meaning of the flag depends on the type of operation that <b>RequestType</b> specifies. The following table describes the possible values for <b>RequestType</b> and <b>Flags</b>:

<table>
<tr>
<th>RequestType</th>
<th>Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>ExclusiveAccessQueryState</b>

</td>
<td>
Not applicable

</td>
<td>
Not applicable

</td>
</tr>
<tr>
<td rowspan="2">
<b>ExclusiveAccessLockDevice</b>

</td>
<td>
0

</td>
<td>
Requires that the caller dismount the file system

</td>
</tr>
<tr>
<td>
CDROM_LOCK_IGNORE_VOLUME

</td>
<td>
Ignores the file system mount and locks the device

</td>
</tr>
<tr>
<td>
<b>ExclusiveAccessUnlockDevice</b>

</td>
<td>
CDROM_NO_MEDIA_NOTIFICATIONS

</td>
<td>
Prevents the sending of a media removal notification and a media arrival notification on an exclusive access unlock

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>
 

 


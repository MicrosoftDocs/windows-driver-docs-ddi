---
UID: NS:ntdddisk._GETVERSIONINPARAMS
title: _GETVERSIONINPARAMS (ntdddisk.h)
description: The GETVERSIONINPARAMS structure is used in conjunction with the SMART_GET_VERSION request to retrieve version information, a capabilities mask, and a bitmask for the indicated device.
old-location: storage\getversioninparams.htm
tech.root: storage
ms.assetid: dcbfa8d2-c2ea-43ae-9d77-ce95a430a514
ms.date: 03/29/2018
keywords: ["_GETVERSIONINPARAMS structure"]
ms.keywords: "*LPGETVERSIONINPARAMS, *PGETVERSIONINPARAMS, GETVERSIONINPARAMS, GETVERSIONINPARAMS structure [Storage Devices], LPGETVERSIONINPARAMS, LPGETVERSIONINPARAMS structure pointer [Storage Devices], PGETVERSIONINPARAMS, PGETVERSIONINPARAMS structure pointer [Storage Devices], _GETVERSIONINPARAMS, ntdddisk/GETVERSIONINPARAMS, ntdddisk/LPGETVERSIONINPARAMS, ntdddisk/PGETVERSIONINPARAMS, storage.getversioninparams, structs-IDE_5426037d-a75f-4b92-a935-e467d02ec8c7.xml"
f1_keywords:
 - "ntdddisk/GETVERSIONINPARAMS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdddisk.h
api_name:
- GETVERSIONINPARAMS
product:
- Windows
targetos: Windows
req.typenames: GETVERSIONINPARAMS, *PGETVERSIONINPARAMS, *LPGETVERSIONINPARAMS
---

# _GETVERSIONINPARAMS structure


## -description


The GETVERSIONINPARAMS structure is used in conjunction with the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566202(v=vs.85)">SMART_GET_VERSION</a> request to retrieve version information, a capabilities mask, and a bitmask for the indicated device. 


## -struct-fields




### -field bVersion

Contains an integer that indicates the version number of the binary driver. 


### -field bRevision

Contains an integer that indicates the revision number of the binary driver. 


### -field bReserved

Reserved. 


### -field bIDEDeviceMap

Contains the bitmap. The following table explains the meaning of the bitmap:

<table>
<tr>
<th>Bitmap Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
Bit 0 is set to 1.

</td>
<td>
The device is either a SATA drive or an IDE drive. If it is an IDE drive, it is the master device on the primary channel. 

</td>
</tr>
<tr>
<td>
Bit 1 is set to 1.

</td>
<td>
The device is an IDE drive, and it is the subordinate device on the primary channel. 

</td>
</tr>
<tr>
<td>
Bit 2 is set to 1.

</td>
<td>
The device is an IDE drive, and it is the master device on the secondary channel. 

</td>
</tr>
<tr>
<td>
Bit 3 is set to 1.

</td>
<td>
The device is an IDE drive, and it is the subordinate device on the secondary channel. 

</td>
</tr>
<tr>
<td>
Bit 4 is set to 1.

</td>
<td>
The device is an ATAPI drive, and it is the master device on the primary channel. 

</td>
</tr>
<tr>
<td>
Bit 5 is set to 1.

</td>
<td>
The device is an ATAPI drive, and it is the subordinate device on the primary channel. 

</td>
</tr>
<tr>
<td>
Bit 6 is set to 1.

</td>
<td>
The device is an ATAPI drive, and it is the master device on the secondary channel. 

</td>
</tr>
<tr>
<td>
Bit 7 is set to 1.

</td>
<td>
The device is an ATAPI drive, and it is the subordinate device on the secondary channel. 

</td>
</tr>
</table>
 


### -field fCapabilities

Contains the bitmask of driver capabilities. 

<table>
<tr>
<th>Bitmask Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CAP_ATA_ID_CMD

</td>
<td>
The device supports the ATA ID command. 

</td>
</tr>
<tr>
<td>
CAP_ATAPI_ID_CMD

</td>
<td>
The device supports the ATAPI ID command. 

</td>
</tr>
<tr>
<td>
CAP_SMART_CMD

</td>
<td>
The device supports SMART commands.

</td>
</tr>
</table>
 


### -field dwReserved

Reserved. 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566202(v=vs.85)">SMART_GET_VERSION</a>
 

 


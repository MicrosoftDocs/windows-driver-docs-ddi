---
UID: NS:ntdddisk._GETVERSIONINPARAMS
title: "_GETVERSIONINPARAMS"
author: windows-driver-content
description: The GETVERSIONINPARAMS structure is used in conjunction with the SMART_GET_VERSION request to retrieve version information, a capabilities mask, and a bitmask for the indicated device.
old-location: storage\getversioninparams.htm
old-project: storage
ms.assetid: dcbfa8d2-c2ea-43ae-9d77-ce95a430a514
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntdddisk/LPGETVERSIONINPARAMS, GETVERSIONINPARAMS structure [Storage Devices], GETVERSIONINPARAMS, ntdddisk/PGETVERSIONINPARAMS, PGETVERSIONINPARAMS structure pointer [Storage Devices], LPGETVERSIONINPARAMS, *LPGETVERSIONINPARAMS, *PGETVERSIONINPARAMS, _GETVERSIONINPARAMS, LPGETVERSIONINPARAMS structure pointer [Storage Devices], structs-IDE_5426037d-a75f-4b92-a935-e467d02ec8c7.xml, storage.getversioninparams, ntdddisk/GETVERSIONINPARAMS, PGETVERSIONINPARAMS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdddisk.h
apiname:
-	GETVERSIONINPARAMS
product: Windows
targetos: Windows
req.typenames: GETVERSIONINPARAMS, *PGETVERSIONINPARAMS, *LPGETVERSIONINPARAMS
---

# _GETVERSIONINPARAMS structure


## -description


The GETVERSIONINPARAMS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566202">SMART_GET_VERSION</a> request to retrieve version information, a capabilities mask, and a bitmask for the indicated device. 


## -syntax


````
typedef struct _GETVERSIONINPARAMS {
  UCHAR bVersion;
  UCHAR bRevision;
  UCHAR bReserved;
  UCHAR bIDEDeviceMap;
  ULONG fCapabilities;
  ULONG dwReserved[4];
} GETVERSIONINPARAMS, *PGETVERSIONINPARAMS, *LPGETVERSIONINPARAMS;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566202">SMART_GET_VERSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GETVERSIONINPARAMS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


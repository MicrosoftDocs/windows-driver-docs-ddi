---
UID: NS:ntdddisk._DISK_EX_INT13_INFO
title: "_DISK_EX_INT13_INFO"
author: windows-driver-content
description: The DISK_EX_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an extended INT13 format.
old-location: storage\disk_ex_int13_info.htm
old-project: storage
ms.assetid: 82e3a1e9-275a-489a-9e6e-d76007a1abb9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PDISK_EX_INT13_INFO, ,, 1, 3, D, DISK_EX_INT13_INFO, DISK_EX_INT13_INFO structure [Storage Devices], E, F, I, K, N, O, P, PDISK_EX_INT13_INFO, PDISK_EX_INT13_INFO structure pointer [Storage Devices], S, T, X, _, _DISK_EX_INT13_INFO, ntdddisk/DISK_EX_INT13_INFO, ntdddisk/PDISK_EX_INT13_INFO, storage.disk_ex_int13_info, structs-disk_be49445a-5e95-4b7a-b4ef-fa21f110aeca.xml"
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
-	DISK_EX_INT13_INFO
product: Windows
targetos: Windows
req.typenames: DISK_EX_INT13_INFO, *PDISK_EX_INT13_INFO
---

# _DISK_EX_INT13_INFO structure


## -description


The DISK_EX_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an extended INT13 format. 


## -syntax


````
typedef struct _DISK_EX_INT13_INFO {
  USHORT  ExBufferSize;
  USHORT  ExFlags;
  ULONG   ExCylinders;
  ULONG   ExHeads;
  ULONG   ExSectorsPerTrack;
  ULONG64 ExSectorsPerDrive;
  USHORT  ExSectorSize;
  USHORT  ExReserved;
} DISK_EX_INT13_INFO, *PDISK_EX_INT13_INFO;
````


## -struct-fields




### -field ExBufferSize

Indicates the size of the buffer that the caller provides to the BIOS in which to return the requested drive data. <b>ExBufferSize</b> must be 26 or greater. If <b>ExBufferSize</b> is less than 26, the BIOS returns an error . If <b>ExBufferSize</b> is between 30 and 66, the BIOS sets it to exactly 30 on exit. If <b>ExBufferSize</b> is 66 or greater, the BIOS sets it to exactly 66 on exit. 


### -field ExFlags

Provides information about the drive. The following table describes the significance of each bit, where bit 0 is the least significant bit and bit 15 the most significant bit. A value of one in the indicated bit means that the feature described in the "Meaning" column is available. A value of zero in the indicated bit means that the feature is not available with this drive.

<table>
<tr>
<th>Bit number </th>
<th>Meaning</th>
</tr>
<tr>
<td>
0 

</td>
<td>
DMA boundary errors are handled transparently. 

</td>
</tr>
<tr>
<td>
1 

</td>
<td>
The geometry supplied in bytes 8-12 is valid. 

</td>
</tr>
<tr>
<td>
2 

</td>
<td>
Device is removable. 

</td>
</tr>
<tr>
<td>
3 

</td>
<td>
Device supports write with verify. 

</td>
</tr>
<tr>
<td>
4 

</td>
<td>
Device has change line support (bit 2 must be set). 

</td>
</tr>
<tr>
<td>
5 

</td>
<td>
Device is lockable (bit 2 must be set). 

</td>
</tr>
<tr>
<td>
6 

</td>
<td>
Device geometry is set to maximum, no media is present (bit 2 must be set). This bit is turned off when media is present in a removable media device. 

</td>
</tr>
<tr>
<td>
7-15 

</td>
<td>
Reserved, must be 0. 

</td>
</tr>
</table>
 


### -field ExCylinders

Indicates the number of <i>physical </i>cylinders. This is one greater than the maximum cylinder number.


### -field ExHeads

Indicates the number of <i>physical </i>heads. This is one greater than the maximum head number. 


### -field ExSectorsPerTrack

Indicates the number of <i>physical </i>sectors per track. This number is the same as the maximum sector number. 


### -field ExSectorsPerDrive

Indicates the total count of sectors on the disk. This is one greater than the maximum logical block address. 


### -field ExSectorSize

Indicates the sector size in bytes. 


### -field ExReserved

Reserved. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_int13_info.md">DISK_INT13_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_EX_INT13_INFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


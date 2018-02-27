---
UID: NS:ntddstor._STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
title: "_STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR"
author: windows-driver-content
description: The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage access alignment descriptor data for a device.
old-location: storage\storage_access_alignment_descriptor.htm
old-project: storage
ms.assetid: 988122bf-d7de-44a3-a059-c984bf636cd0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure pointer [Storage Devices], STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure [Storage Devices], _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, ntddstor/PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, ntddstor/STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, storage.storage_access_alignment_descriptor, structs-general_191220fa-6df5-478b-b60e-af8e3f62d441.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	ntddstor.h
api_name:
-	STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR
---

# _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure


## -description


The STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the storage access alignment descriptor data for a device. 


## -syntax


````
typedef struct _STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG BytesPerCacheLine;
  ULONG BytesOffsetForCacheAlignment;
  ULONG BytesPerLogicalSector;
  ULONG BytesPerPhysicalSector;
  ULONG BytesOffsetForSectorAlignment;
} STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR, *PSTORAGE_ACCESS_ALIGNMENT_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of the structure STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the descriptor, in bytes.


### -field BytesPerCacheLine

The number of bytes in a cache line of the device.


### -field BytesOffsetForCacheAlignment

The address offset necessary for proper cache access alignment, in bytes.


### -field BytesPerLogicalSector

The number of bytes in a logical sector of the device.


### -field BytesPerPhysicalSector

The number of bytes in a physical sector of the device.


### -field BytesOffsetForSectorAlignment

The logical sector offset within the first physical sector where the first logical sector is placed, in bytes.

Example:  Offset = 3 Logical sectors

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|LBA      |X|X|X|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|
|- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
|Physical |               |                  |
|Sector   |      0        |        1         |         2
+- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</pre>
</td>
</tr>
</table></span></div>
In this example, BytesOffsetForSectorAlignment = 3 * size_of_logical_sector.


## -remarks



Storage class drivers issue a device-control request with the I/O control code  <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains access alignment information for data transfer operations. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_ACCESS_ALIGNMENT_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


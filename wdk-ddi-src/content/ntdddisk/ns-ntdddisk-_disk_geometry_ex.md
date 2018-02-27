---
UID: NS:ntdddisk._DISK_GEOMETRY_EX
title: "_DISK_GEOMETRY_EX"
author: windows-driver-content
description: The DISK_GEOMETRY_EX structure is a variable-length structure composed of a DISK_GEOMETRY structure followed by a DISK_PARTITION_INFO structure followed, in turn, by a DISK_DETECTION_INFO structure.
old-location: storage\disk_geometry_ex.htm
old-project: storage
ms.assetid: 6397c0dd-4dc7-49fa-85a7-841f6c2b30d8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDISK_GEOMETRY_EX, DISK_GEOMETRY_EX, DISK_GEOMETRY_EX structure [Storage Devices], PDISK_GEOMETRY_EX, PDISK_GEOMETRY_EX structure pointer [Storage Devices], _DISK_GEOMETRY_EX, ntdddisk/DISK_GEOMETRY_EX, ntdddisk/PDISK_GEOMETRY_EX, storage.disk_geometry_ex, structs-disk_58b543a6-c9ee-4acf-9012-6572e9e9e627.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
-	DISK_GEOMETRY_EX
product: Windows
targetos: Windows
req.typenames: DISK_GEOMETRY_EX, *PDISK_GEOMETRY_EX
---

# _DISK_GEOMETRY_EX structure


## -description


The <b>DISK_GEOMETRY_EX</b> structure is a variable-length structure composed of a <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a> structure followed by a <a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a> structure followed, in turn, by a <a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a> structure. 


## -syntax


````
typedef struct _DISK_GEOMETRY_EX {
  DISK_GEOMETRY Geometry;
  LARGE_INTEGER DiskSize;
  UCHAR         Data[1];
} DISK_GEOMETRY_EX, *PDISK_GEOMETRY_EX;
````


## -struct-fields




### -field Geometry

See <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a> for a description of this member. 


### -field DiskSize

Contains the size in bytes of the disk. 


### -field Data

Pointer to a variable length area containing a <a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a> structure followed by a <a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a> structure.


## -remarks



DISK_GEOMETRY_EX is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a> and the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_media_types.md">IOCTL_DISK_GET_MEDIA_TYPES</a> IOCTLs, in order to retrieve information about the geometry of a physical disk (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

Because the partition and detect information are not at fixed locations within the <b>DISK_GEOMETRY_EX</b> structure, <i>ntdddisk.h</i> provides two macros for accessing this information. Both macros take a pointer to a structure of type <b>DISK_GEOMETRY_EX</b> as an argument:

<pre class="syntax" xml:space="preserve"><code>#if (NTDDI_VERSION &lt; NTDDI_WS03)
#define DiskGeometryGetPartition(Geometry)\
                        ((PDISK_PARTITION_INFO)((Geometry)+1))

#define DiskGeometryGetDetect(Geometry)\
                        ((PDISK_DETECTION_INFO)(((PBYTE)DiskGeometryGetPartition(Geometry)+\
                                        DiskGeometryGetPartition(Geometry)-&gt;SizeOfPartitionInfo)))
#else
#define DiskGeometryGetPartition(Geometry)\
                        ((PDISK_PARTITION_INFO)((Geometry)-&gt;Data))

#define DiskGeometryGetDetect(Geometry)\
                        ((PDISK_DETECTION_INFO)(((ULONG_PTR)DiskGeometryGetPartition(Geometry)+\
                                        DiskGeometryGetPartition(Geometry)-&gt;SizeOfPartitionInfo)))
#endif</code></pre>



## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_media_types.md">IOCTL_DISK_GET_MEDIA_TYPES</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_partition_info.md">DISK_PARTITION_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_GEOMETRY_EX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


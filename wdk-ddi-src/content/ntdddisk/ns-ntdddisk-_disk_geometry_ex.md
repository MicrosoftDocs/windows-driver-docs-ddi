---
UID: NS:ntdddisk._DISK_GEOMETRY_EX
title: "_DISK_GEOMETRY_EX"
description: The DISK_GEOMETRY_EX structure is a variable-length structure composed of a DISK_GEOMETRY structure followed by a DISK_PARTITION_INFO structure followed, in turn, by a DISK_DETECTION_INFO structure.
old-location: storage\disk_geometry_ex.htm
tech.root: storage
ms.assetid: 6397c0dd-4dc7-49fa-85a7-841f6c2b30d8
ms.date: 03/29/2018
ms.keywords: "*PDISK_GEOMETRY_EX, DISK_GEOMETRY_EX, DISK_GEOMETRY_EX structure [Storage Devices], PDISK_GEOMETRY_EX, PDISK_GEOMETRY_EX structure pointer [Storage Devices], _DISK_GEOMETRY_EX, ntdddisk/DISK_GEOMETRY_EX, ntdddisk/PDISK_GEOMETRY_EX, storage.disk_geometry_ex, structs-disk_58b543a6-c9ee-4acf-9012-6572e9e9e627.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	DISK_GEOMETRY_EX
product:
- Windows
targetos: Windows
req.typenames: DISK_GEOMETRY_EX, *PDISK_GEOMETRY_EX
---

# _DISK_GEOMETRY_EX structure


## -description


The <b>DISK_GEOMETRY_EX</b> structure is a variable-length structure composed of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a> structure followed by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552629">DISK_PARTITION_INFO</a> structure followed, in turn, by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552601">DISK_DETECTION_INFO</a> structure. 


## -struct-fields




### -field Geometry

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a> for a description of this member. 


### -field DiskSize

Contains the size in bytes of the disk. 


### -field Data

Pointer to a variable length area containing a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552629">DISK_PARTITION_INFO</a> structure followed by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552601">DISK_DETECTION_INFO</a> structure.


## -remarks



DISK_GEOMETRY_EX is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560359">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a> and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560371">IOCTL_DISK_GET_MEDIA_TYPES</a> IOCTLs, in order to retrieve information about the geometry of a physical disk (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552601">DISK_DETECTION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552629">DISK_PARTITION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560371">IOCTL_DISK_GET_MEDIA_TYPES</a>
 

 


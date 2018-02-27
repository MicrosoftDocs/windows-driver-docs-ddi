---
UID: NS:ntdddisk._DISK_GEOMETRY
title: "_DISK_GEOMETRY"
author: windows-driver-content
description: The DISK_GEOMETRY structure is obsolete and provided only to support existing drivers.
old-location: storage\disk_geometry.htm
old-project: storage
ms.assetid: f92d1f63-4361-4775-88f8-be1c9bf781ef
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDISK_GEOMETRY, DISK_GEOMETRY, DISK_GEOMETRY structure [Storage Devices], PDISK_GEOMETRY, PDISK_GEOMETRY structure pointer [Storage Devices], _DISK_GEOMETRY, ntdddisk/DISK_GEOMETRY, ntdddisk/PDISK_GEOMETRY, storage.disk_geometry, structs-disk_3ad908b7-8f42-4a06-914e-92b631cc1a56.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	DISK_GEOMETRY
product: Windows
targetos: Windows
req.typenames: DISK_GEOMETRY, *PDISK_GEOMETRY
---

# _DISK_GEOMETRY structure


## -description


The DISK_GEOMETRY structure is obsolete and provided only to support existing drivers. New drivers must use <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>. DISK_GEOMETRY is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> and the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_media_types.md">IOCTL_DISK_GET_MEDIA_TYPES</a> requests, in order to retrieve information about the geometry of a physical disk. 


## -syntax


````
typedef struct _DISK_GEOMETRY {
  LARGE_INTEGER Cylinders;
  MEDIA_TYPE    MediaType;
  ULONG         TracksPerCylinder;
  ULONG         SectorsPerTrack;
  ULONG         BytesPerSector;
} DISK_GEOMETRY, *PDISK_GEOMETRY;
````


## -struct-fields




### -field Cylinders

Indicates the number of cylinders on the disk device.


### -field MediaType

Indicates the type of disk. The enumeration <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a> lists the values that can be assigned to this member. 


### -field TracksPerCylinder

Indicates the number of tracks in a cylinder.


### -field SectorsPerTrack

Indicates the number of sectors in each track.


### -field BytesPerSector

Indicates the number of bytes in a disk sector.


## -remarks




<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a> must be used with new drivers, in order to accommodate GUID Partition Table (GPT) partitions. The DISK_GEOMETRY structure is nested within the DISK_GEOMETRY_EX structure.


<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_media_types.md">IOCTL_DISK_GET_MEDIA_TYPES</a> causes an array of these structures to be returned. 




## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_media_types.md">IOCTL_DISK_GET_MEDIA_TYPES</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_GEOMETRY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:mountmgr._MOUNTMGR_VOLUME_MOUNT_POINT
title: _MOUNTMGR_VOLUME_MOUNT_POINT (mountmgr.h)
description: The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED request to inform the mount manager that a volume mount point has been created.
old-location: storage\mountmgr_volume_mount_point.htm
tech.root: storage
ms.assetid: 2a267992-b4d3-49e1-bb80-3849220f0d1f
ms.date: 03/29/2018
keywords: ["_MOUNTMGR_VOLUME_MOUNT_POINT structure"]
ms.keywords: "*PMOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT structure [Storage Devices], PMOUNTMGR_VOLUME_MOUNT_POINT, PMOUNTMGR_VOLUME_MOUNT_POINT structure pointer [Storage Devices], _MOUNTMGR_VOLUME_MOUNT_POINT, mountmgr/MOUNTMGR_VOLUME_MOUNT_POINT, mountmgr/PMOUNTMGR_VOLUME_MOUNT_POINT, storage.mountmgr_volume_mount_point, structs-mntmgr_afa5831e-a33d-4fb6-a67b-b0b4f459e19b.xml"
f1_keywords:
 - "mountmgr/MOUNTMGR_VOLUME_MOUNT_POINT"
 - "MOUNTMGR_VOLUME_MOUNT_POINT"
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
- mountmgr.h
api_name:
- MOUNTMGR_VOLUME_MOUNT_POINT
targetos: Windows
req.typenames: MOUNTMGR_VOLUME_MOUNT_POINT, *PMOUNTMGR_VOLUME_MOUNT_POINT
---

# _MOUNTMGR_VOLUME_MOUNT_POINT structure


## -description


The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_volume_mount_point_created">IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED</a> request to inform the mount manager that a volume mount point has been created. 


## -struct-fields




### -field SourceVolumeNameOffset

Contains an offset, in bytes, into the output buffer where the name of the mount point is located. 


### -field SourceVolumeNameLength

Contains the length, in bytes, of the mount point name. 


### -field TargetVolumeNameOffset

Contains an offset, in bytes, into the output buffer where the unique (persistent) volume name of the target device is located. 


### -field TargetVolumeNameLength

Contains the length, in bytes, of the target name. 


## -remarks



Mount point names must contain the full path of a mount point object name in the system object tree. For example: "\DosDevices\E:\FilesysD\mnt". For an explanation of unique volume names and how the mount manager uses them, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_volume_mount_point_created">IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED</a>
 

 


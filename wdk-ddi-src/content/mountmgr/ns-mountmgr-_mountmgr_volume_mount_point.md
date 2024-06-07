---
UID: NS:mountmgr._MOUNTMGR_VOLUME_MOUNT_POINT
title: MOUNTMGR_VOLUME_MOUNT_POINT (mountmgr.h)
description: Learn about the MOUNTMGR_VOLUME_MOUNT_POINT structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_VOLUME_MOUNT_POINT structure"]
ms.keywords: "*PMOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT structure [Storage Devices], PMOUNTMGR_VOLUME_MOUNT_POINT, PMOUNTMGR_VOLUME_MOUNT_POINT structure pointer [Storage Devices], _MOUNTMGR_VOLUME_MOUNT_POINT, mountmgr/MOUNTMGR_VOLUME_MOUNT_POINT, mountmgr/PMOUNTMGR_VOLUME_MOUNT_POINT, storage.mountmgr_volume_mount_point, structs-mntmgr_afa5831e-a33d-4fb6-a67b-b0b4f459e19b.xml"
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
targetos: Windows
req.typenames: MOUNTMGR_VOLUME_MOUNT_POINT, *PMOUNTMGR_VOLUME_MOUNT_POINT
f1_keywords:
 - _MOUNTMGR_VOLUME_MOUNT_POINT
 - mountmgr/_MOUNTMGR_VOLUME_MOUNT_POINT
 - PMOUNTMGR_VOLUME_MOUNT_POINT
 - mountmgr/PMOUNTMGR_VOLUME_MOUNT_POINT
 - MOUNTMGR_VOLUME_MOUNT_POINT
 - mountmgr/MOUNTMGR_VOLUME_MOUNT_POINT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_VOLUME_MOUNT_POINT
 - PMOUNTMGR_VOLUME_MOUNT_POINT
 - MOUNTMGR_VOLUME_MOUNT_POINT
---

## -description

The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the [IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED](ni-mountmgr-ioctl_mountmgr_volume_mount_point_created.md) request to inform the mount manager that a volume mount point has been created.

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

Mount point names must contain the full path of a mount point object name in the system object tree. For example: "\DosDevices\E:\FilesysD\mnt".

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED](ni-mountmgr-ioctl_mountmgr_volume_mount_point_created.md)

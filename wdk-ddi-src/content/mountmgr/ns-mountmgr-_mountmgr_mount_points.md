---
UID: NS:mountmgr._MOUNTMGR_MOUNT_POINTS
title: MOUNTMGR_MOUNT_POINTS (mountmgr.h)
description: Learn about the MOUNTMGR_MOUNT_POINTS structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_MOUNT_POINTS structure"]
ms.keywords: "*PMOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS structure [Storage Devices], PMOUNTMGR_MOUNT_POINTS, PMOUNTMGR_MOUNT_POINTS structure pointer [Storage Devices], _MOUNTMGR_MOUNT_POINTS, mountmgr/MOUNTMGR_MOUNT_POINTS, mountmgr/PMOUNTMGR_MOUNT_POINTS, storage.mountmgr_mount_points, structs-mntmgr_844fdf51-1324-4b1d-b68f-abba5f471652.xml"
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
req.typenames: MOUNTMGR_MOUNT_POINTS, *PMOUNTMGR_MOUNT_POINTS
f1_keywords:
 - _MOUNTMGR_MOUNT_POINTS
 - mountmgr/_MOUNTMGR_MOUNT_POINTS
 - PMOUNTMGR_MOUNT_POINTS
 - mountmgr/PMOUNTMGR_MOUNT_POINTS
 - MOUNTMGR_MOUNT_POINTS
 - mountmgr/MOUNTMGR_MOUNT_POINTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_MOUNT_POINTS
 - PMOUNTMGR_MOUNT_POINTS
 - MOUNTMGR_MOUNT_POINTS
---

## -description

The **MOUNTMGR_MOUNT_POINTS** structure is used by mount manager to send a client the list of mount points associated with a device.

## -struct-fields

### -field Size

Contains the size, in bytes, of the output buffer.

### -field NumberOfMountPoints

Contains the number of mount points that the mount manager is returning.

### -field MountPoints

Contains an array of [**MOUNTMGR_MOUNT_POINT**](ns-mountmgr-_mountmgr_mount_point.md) structures that contain information about each mount point associated with the device.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md)

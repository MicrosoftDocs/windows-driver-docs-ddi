---
UID: NI:mountmgr.IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED
title: IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED (mountmgr.h)
description: The mount manager clients use this IOCTL to alert the mount manager that a volume mount point has been deleted so that the mount manager can replicate the database entry for the given mount point.
old-location: storage\ioctl_mountmgr_volume_mount_point_deleted.htm
tech.root: storage
ms.assetid: 8a436053-87c2-4fa2-9280-7035a990d0b4
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED, IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED control, IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED control code [Storage Devices], k307_fce8de67-6c3d-4e89-8259-a7058c968c62.xml, mountmgr/IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED, storage.ioctl_mountmgr_volume_mount_point_deleted
f1_keywords:
 - "mountmgr/IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED"
 - "IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED"
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
- Mountmgr.h
api_name:
- IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED IOCTL


## -description


The mount manager clients use this IOCTL to alert the mount manager that a volume mount point has been deleted so that the mount manager can replicate the database entry for the given mount point.

The Microsoft Win32 routine <b>DeleteVolumeMountPoint</b> sends this IOCTL to the mount manager, to inform the mount manager that a directory junction is no longer pointing to a volume name. The mount manager responds by deleting the volume name formerly contained in the directory junction along with its unique ID from the volume hosting the directory junction. 


## -ioctlparameters




### -input-buffer

The mount manager client initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_volume_mount_point">MOUNTMGR_VOLUME_MOUNT_POINT</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_VOLUME_MOUNT_POINT).


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_VOLUME_MOUNT_POINT), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_volume_mount_point">MOUNTMGR_VOLUME_MOUNT_POINT</a>
 

 


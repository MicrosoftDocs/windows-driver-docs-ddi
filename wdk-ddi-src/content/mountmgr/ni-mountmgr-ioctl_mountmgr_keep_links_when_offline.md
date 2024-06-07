---
UID: NI:mountmgr.IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
title: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control, IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control code [Storage Devices], k307_7502107c-0301-45d9-a0b6-8aa6e9e231c9.xml, mountmgr/IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, storage.ioctl_mountmgr_keep_links_when_offline
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
req.typenames: 
f1_keywords:
 - IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
 - mountmgr/IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
---

## -description

This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline. When the volume goes back online, the mount manager reassigns the symbolic link to the volume. No other volume is allowed to claim the symbolic link while its original owner is offline.

Clusters use this IOCTL to ensure that a node can continue to access a volume with the same drive letter, even if the volume is not continually present in the system.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager client loads the following structure with the symbolic link that will persist even after its volume is removed from the system. The initialized structure [**MOUNTMGR_TARGET_NAME**](ns-mountmgr-_mountmgr_target_name.md) is inserted at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_TARGET_NAME)```.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful, the **Status** field is set to STATUS_SUCCESS.

The input buffer size, indicated by **InputBufferLength**, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the **Status** field is set to STATUS_INVALID_PARAMETER.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTMGR_TARGET_NAME**](ns-mountmgr-_mountmgr_target_name.md)

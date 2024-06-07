---
UID: NI:mountdev.IOCTL_MOUNTDEV_LINK_DELETED
title: IOCTL_MOUNTDEV_LINK_DELETED (mountdev.h)
description: Learn more about the IOCTL_MOUNTDEV_LINK_DELETED control code.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTDEV_LINK_DELETED IOCTL"]
ms.keywords: IOCTL_MOUNTDEV_LINK_DELETED, IOCTL_MOUNTDEV_LINK_DELETED control, IOCTL_MOUNTDEV_LINK_DELETED control code [Storage Devices], k307_b0ab5504-dac9-410f-bb73-bbb5876e4a59.xml, mountdev/IOCTL_MOUNTDEV_LINK_DELETED, storage.ioctl_mountdev_link_deleted
req.header: mountdev.h
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
 - IOCTL_MOUNTDEV_LINK_DELETED
 - mountdev/IOCTL_MOUNTDEV_LINK_DELETED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountdev.h
api_name:
 - IOCTL_MOUNTDEV_LINK_DELETED
---

## -description

**IOCTL_MOUNTDEV_LINK_DELETED** alerts the mount manager client that a persistent name associated with it has been deleted.

Support for this IOCTL by mount manager clients is optional.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager places a variable-length structure of type [**MOUNTDEV_NAME**](../mountmgr/ns-mountmgr-_mountdev_name.md) at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**. The mount manager inserts the persistent name just assigned at the address pointed to by the **Name** member of this structure.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTDEV_NAME)```.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

No status.

## -remarks

The implementer of this function must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTDEV_NAME**](../mountmgr/ns-mountmgr-_mountdev_name.md)

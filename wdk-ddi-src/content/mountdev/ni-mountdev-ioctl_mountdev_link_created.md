---
UID: NI:mountdev.IOCTL_MOUNTDEV_LINK_CREATED
title: IOCTL_MOUNTDEV_LINK_CREATED (mountdev.h)
description: Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.
old-location: storage\ioctl_mountdev_link_created.htm
tech.root: storage
ms.assetid: 98ccf623-8232-4bcb-bd72-39dd31c7ede3
ms.date: 03/29/2018
ms.keywords: IOCTL_MOUNTDEV_LINK_CREATED, IOCTL_MOUNTDEV_LINK_CREATED control, IOCTL_MOUNTDEV_LINK_CREATED control code [Storage Devices], k307_b93a8e67-8e02-4d7d-aac2-a11f3d4297c2.xml, mountdev/IOCTL_MOUNTDEV_LINK_CREATED, storage.ioctl_mountdev_link_created
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mountdev.h
api_name:
-	IOCTL_MOUNTDEV_LINK_CREATED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTDEV_LINK_CREATED IOCTL

## -description

Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.

## -ioctlparameters

### -input-buffer

The mount point manager places a variable-length structure of type [MOUNTDEV_NAME](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mountmgr/ns-mountmgr-_mountdev_name), defined in *Mountmgr.h* at the beginning of the buffer at **Irp-\>AssociatedIrp.SystemBuffer**. The mount manager inserts the persistent name just assigned at the address pointed to by the *Name* member of this structure.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to **sizeof**(MOUNTDEV_NAME).

### -output-buffer

None

### -output-buffer-length

None

### -in-out-buffer

### -inout-buffer-length

## -remarks

The implementer of this function must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

### -status-block

No status.

## -see-also

[MOUNTDEV_NAME](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mountmgr/ns-mountmgr-_mountdev_name)

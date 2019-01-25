---
UID: NI:mountmgr.IOCTL_MOUNTDEV_QUERY_DEVICE_NAME
title: IOCTL_MOUNTDEV_QUERY_DEVICE_NAME (mountmgr.h)
description: Support for this IOCTL by the mount manager clients is mandatory.
old-location: storage\ioctl_mountdev_query_device_name.htm
tech.root: storage
ms.assetid: 3df96552-d4f6-4d1c-bc07-3eff5f3eabfb
ms.date: 03/29/2018
ms.keywords: IOCTL_MOUNTDEV_QUERY_DEVICE_NAME, IOCTL_MOUNTDEV_QUERY_DEVICE_NAME control, IOCTL_MOUNTDEV_QUERY_DEVICE_NAME control code [Storage Devices], k307_4a0b9087-3740-4467-aa0f-ca7f56b8ae13.xml, mountmgr/IOCTL_MOUNTDEV_QUERY_DEVICE_NAME, storage.ioctl_mountdev_query_device_name
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Mountmgr.h
api_name:
-	IOCTL_MOUNTDEV_QUERY_DEVICE_NAME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTDEV_QUERY_DEVICE_NAME IOCTL

## -description

Support for this IOCTL by the mount manager clients is mandatory. Upon receiving this IOCTL a client driver must provide the (nonpersistent) device (or target) name for the volume. The mount manager uses the *device name* returned by the client as the target of a symbolic link. An example of a device name would be "\Device\HarddiskVolume1".

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

The mount manager client returns a variable-length structure of type [MOUNTDEV_NAME](ns-mountmgr-_mountdev_name.md), defined in *Mountmgr.h*, at the beginning of the buffer at **Irp-&gt;AssociatedIrp.SystemBuffer**. The device name must be inserted at the address pointed to by the *Name* member of this structure.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to **sizeof**(MOUNTDEV_NAME).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field is set to FIELD_OFFSET([MOUNTDEV_NAME](ns-mountmgr-_mountdev_name.md), Name) + output-\>NameLength, or alternatively, output-\>NameLength + sizeof(USHORT), where output points to the buffer at **Irp-\>AssociatedIrp.SystemBuffer**

If the operation is successful, the mount manager client must set the **Information** field to the length of the **NULL**-terminated string containing the device name and the **Status** field to STATUS_SUCCESS.

If the output buffer is too small to hold the device name, the mount manager client must set the **Information** field to **sizeof**(MOUNTDEV_NAME) and the **Status** field to STATUS_BUFFER_OVERFLOW. In addition, the mount manager client fills in the NameLength member of the [MOUNTDEV_NAME](ns-mountmgr-_mountdev_name.md) structure.

## -remarks

As a best practice, the implementer must not thread-synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

## -see-also

[MOUNTDEV_NAME](ns-mountmgr-_mountdev_name.md)

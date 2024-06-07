---
UID: NI:mountdev.IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
title: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID (mountdev.h)
description: Learn more about the IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control code.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTDEV_QUERY_UNIQUE_ID IOCTL"]
ms.keywords: IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control, IOCTL_MOUNTDEV_QUERY_UNIQUE_ID control code [Storage Devices], k307_5dd8b350-65b5-4f59-b96f-cae11fe7fb5b.xml, mountdev/IOCTL_MOUNTDEV_QUERY_UNIQUE_ID, storage.ioctl_mountdev_query_unique_id
req.header: mountdev.h
req.include-header: Mountdev.h
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
 - IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
 - mountdev/IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountdev.h
api_name:
 - IOCTL_MOUNTDEV_QUERY_UNIQUE_ID
---

## -description

**IOCTL_MOUNTDEV_QUERY_UNIQUE_ID** retrieves a unique identifier for a device or volume.

Mount manager clients must support this IOCTL. Upon receiving this IOCTL, the mount manager client must provide a counted byte string identifier that is unique to the client (that is, the device or the volume).

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The device class or volume driver returns the [**MOUNTDEV_UNIQUE_ID**](ns-mountdev-_mountdev_unique_id.md) structure in the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to ```sizeof(MOUNTDEV_UNIQUE_ID)```.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

The **Information** field is set to FIELD_OFFSET([**MOUNTDEV_UNIQUE_ID**](ns-mountdev-_mountdev_unique_id.md), UniqueId) + output->UniqueIdLength; or alternatively to sizeof(USHORT) + output->UniqueIdLength, where output points to the buffer at **Irp->AssociatedIrp.SystemBuffer**.

## -remarks

The implementer of this function must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTDEV_UNIQUE_ID**](ns-mountdev-_mountdev_unique_id.md)

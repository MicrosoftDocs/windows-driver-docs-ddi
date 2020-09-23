---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_NUMBER
title: IOCTL_STORAGE_GET_DEVICE_NUMBER (ntddstor.h)
description: Returns a STORAGE_DEVICE_NUMBER structure that contains the FILE_DEVICE_XXX type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started.
old-location: storage\ioctl_storage_get_device_number.htm
tech.root: storage
ms.assetid: 5d1095c6-b9f9-44ef-bb2b-7bc0265e5aa9
ms.date: 11/08/2019
keywords: ["IOCTL_STORAGE_GET_DEVICE_NUMBER IOCTL"]
ms.keywords: IOCTL_STORAGE_GET_DEVICE_NUMBER, IOCTL_STORAGE_GET_DEVICE_NUMBER control, IOCTL_STORAGE_GET_DEVICE_NUMBER control code [Storage Devices], k307_d4d6bd65-7f75-4810-90ce-edd3dec950be.xml, ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER, storage.ioctl_storage_get_device_number
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
 - IOCTL_STORAGE_GET_DEVICE_NUMBER
 - ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_GET_DEVICE_NUMBER
---

# IOCTL_STORAGE_GET_DEVICE_NUMBER IOCTL


## -description

Returns a [STORAGE_DEVICE_NUMBER](./ns-ntddstor-_storage_device_number.md) structure that contains the FILE_DEVICE_*XXX* type, device number, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started. This request is usually issued by a fault-tolerant disk driver.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the [STORAGE_DEVICE_NUMBER](./ns-ntddstor-_storage_device_number.md) data in the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= **sizeof**(STORAGE_DEVICE_NUMBER).

### -status-block

The **Information** field is set to the number of bytes returned. The **Status** field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

[IOCTL_STORAGE_GET_DEVICE_NUMBER_EX](./ni-ntddstor-ioctl_storage_get_device_number_ex.md)

[STORAGE_DEVICE_NUMBER](./ns-ntddstor-_storage_device_number.md)
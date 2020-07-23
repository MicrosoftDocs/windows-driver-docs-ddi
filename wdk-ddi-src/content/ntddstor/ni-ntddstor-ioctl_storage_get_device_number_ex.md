---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_NUMBER_EX
title: IOCTL_STORAGE_GET_DEVICE_NUMBER_EX (ntddstor.h)
description: Returns a STORAGE_DEVICE_NUMBER structure that contains the FILE_DEVICE_XXX type, device number, device GUID, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started.
old-location: storage\ioctl_storage_get_device_number.htm
tech.root: storage
ms.assetid: 21eb3380-bd3c-488d-8eaf-22d337775f42
ms.date: 11/08/2019
keywords: ["IOCTL_STORAGE_GET_DEVICE_NUMBER_EX IOCTL"]
ms.keywords: IOCTL_STORAGE_GET_DEVICE_NUMBER_EX, IOCTL_STORAGE_GET_DEVICE_NUMBER_EX control, IOCTL_STORAGE_GET_DEVICE_NUMBER_EX control code [Storage Devices], ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER_EX
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_GET_DEVICE_NUMBER_EX"
 - "IOCTL_STORAGE_GET_DEVICE_NUMBER_EX"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_GET_DEVICE_NUMBER_EX
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_DEVICE_NUMBER_EX IOCTL

## -description

Returns a [STORAGE_DEVICE_NUMBER_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_number_ex) structure that contains the FILE_DEVICE_*XXX* type, device number, device GUID, and, for a partitionable device, the partition number assigned to a device by the driver when the device is started. This request is usually issued by a fault-tolerant disk driver.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the [STORAGE_DEVICE_NUMBER_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_number_ex) data in the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= **sizeof**(STORAGE_DEVICE_NUMBER_EX).

### -status-block

The **Information** field is set to the number of bytes returned. The **Status** field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

[IOCTL_STORAGE_GET_DEVICE_NUMBER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-ioctl_storage_get_device_number)

[STORAGE_DEVICE_NUMBER_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_number_ex)

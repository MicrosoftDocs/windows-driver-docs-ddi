---
UID: NI:ntddstor.IOCTL_STORAGE_DEVICE_POWER_CAP
title: IOCTL_STORAGE_DEVICE_POWER_CAP (ntddstor.h)
description: A driver can use IOCTL_STORAGE_DEVICE_POWER_CAP to specify a maximum operational power consumption level for a storage device.
old-location: storage\ioctl_storage_device_power_cap.htm
tech.root: storage
ms.date: 10/11/2022
keywords: ["IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL"]
ms.keywords: IOCTL_STORAGE_DEVICE_POWER_CAP, IOCTL_STORAGE_DEVICE_POWER_CAP control, IOCTL_STORAGE_DEVICE_POWER_CAP control code [Storage Devices], ntddstor/IOCTL_STORAGE_DEVICE_POWER_CAP, storage.ioctl_storage_device_power_cap
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - IOCTL_STORAGE_DEVICE_POWER_CAP
 - ntddstor/IOCTL_STORAGE_DEVICE_POWER_CAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_DEVICE_POWER_CAP
ms.custom: engagement-fy23 
---

# IOCTL_STORAGE_DEVICE_POWER_CAP IOCTL

## -description

A driver can use **IOCTL_STORAGE_DEVICE_POWER_CAP** to specify a maximum operational power consumption level for a storage device. The OS will do its best to transition the device to a power state that will not exceed the given maximum; however, this depends on what the device supports. The actual maximum may be less than or greater than the desired maximum.

## -ioctlparameters

### -input-buffer

[**Irp->AssociatedIrp.SystemBuffer**](../wdm/ns-wdm-_irp.md) contains a [**STORAGE_DEVICE_POWER_CAP**](ns-ntddstor-_storage_device_power_cap.md) structure that specifies the maximum power.

### -input-buffer-length

* **Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the input parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be greater than or equal to ```sizeof(STORAGE_DEVICE_POWER_CAP)```.

### -output-buffer

If the operation is successful, the output buffer at **Irp->AssociatedIrp.SystemBuffer** will contain a [**STORAGE_DEVICE_POWER_CAP**](ns-ntddstor-_storage_device_power_cap.md) structure.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** indicates the size, in bytes, of the output parameter buffer at **Irp->AssociatedIrp.SystemBuffer**. **OutputBufferLength** must be greater than or equal to ```sizeof(STORAGE_DEVICE_POWER_CAP)```.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The [**Information**](../wdm/ns-wdm-_io_status_block.md) field is set to the number of bytes returned. The **Status** field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED.

## -remarks

For a reboot, the **IOCTL_STORAGE_DEVICE_POWER_CAP** effect is not persistent. For an NVMe device reset/power cycle, the IOCTL’s effect is persistent.

## -see-also

[**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md)

[**STORAGE_DEVICE_POWER_CAP**](ns-ntddstor-_storage_device_power_cap.md)

[**STORAGE_DEVICE_POWER_CAP_UNITS**](ne-ntddstor-_storage_device_power_cap_units.md)

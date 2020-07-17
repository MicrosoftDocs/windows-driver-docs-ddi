---
UID: NI:ntddstor.IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
title: IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG to get the internal status data from the device.
tech.root: storage
ms.assetid: 927a77ea-3c95-4dd3-9ae2-7fa69f7de18d
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG"
 - "IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG"
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.max-support:
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG
product: 
 - Windows
targetos: Windows
---

# IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG IOCTL

### Major Code:

[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

A driver can use IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG to get the internal status data from the device.

## -ioctlparameters

### -input-buffer

A [GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md) structure that identifies the type of data to be queried.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= **sizeof**(GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST).

### -output-buffer

The driver returns output to the buffer at **Irp->AssociatedIrp.SystemBuffer**. This buffer contains a [DEVICE_INTERNAL_STATUS_DATA](ns-ntddstor-device_internal_status_data.md) structure with the device's internal status.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= **sizeof**(DEVICE_INTERNAL_STATUS_DATA).

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status is set to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also

[DEVICE_INTERNAL_STATUS_DATA](ns-ntddstor-device_internal_status_data.md)

[GET_DEVICE_INTERNAL_STATUS_DATA_REQUEST](ns-ntddstor-get_device_internal_status_data_request.md)

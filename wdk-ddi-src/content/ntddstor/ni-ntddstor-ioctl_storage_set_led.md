---
UID: NI:ntddstor.IOCTL_STORAGE_SET_LED
title: IOCTL_STORAGE_SET_LED
author: windows-driver-content
description: 
tech.root: storage
ms.assetid: 11d2bcf1-f7cc-4b15-be59-bb7e4cb51300
ms.author: windowsdriverdev
ms.date: 11/30/2019
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_SET_LED"
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
 - IOCTL_STORAGE_SET_LED
product: 
 - Windows
targetos: Windows
---

# IOCTL_STORAGE_SET_LED IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

When sent, IOCTL_STORAGE_SET_LED will clear or set the LED state associated with the device.

## -ioctlparameters

### -input-buffer

Contains a [STORAGE_SET_INDICATOR](ns-ntddstor-storage_set_indicator.md) structure that specifies the LED indicator state, and whether that indicator state should be set or cleared.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= **sizeof**(STORAGE_SET_INDICATOR).

### -output-buffer

None.

### -output-buffer-length

None.

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Only platforms that support Native PCIe Enclosure Management (NPEM) or all related ACPI methods will respond to an IOCTL_STORAGE_SET_LED request.

Currently, IOCTL_STORAGE_SET_LED supports single state control at one time.

## -see-also

[STORAGE_SET_INDICATOR](ns-ntddstor-storage_set_indicator.md)

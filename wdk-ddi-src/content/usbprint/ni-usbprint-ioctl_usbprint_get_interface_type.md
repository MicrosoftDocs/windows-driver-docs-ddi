---
UID: NI:usbprint.IOCTL_USBPRINT_GET_INTERFACE_TYPE
title: IOCTL_USBPRINT_GET_INTERFACE_TYPE
author: windows-driver-content
description: Get the protocol capabilities of the USB printer interface.
tech.root: print
ms.assetid: cec2122d-17b3-407c-b374-be475024afc2
ms.author: windowsdriverdev
ms.date: 03/18/2019
ms.topic: ioctl
ms.custom: 19H1
req.header: usbprint.h
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
 - usbprint.h
api_name: 
 - IOCTL_USBPRINT_GET_INTERFACE_TYPE
product: 
 - Windows
targetos: Windows
---

# IOCTL_USBPRINT_GET_INTERFACE_TYPE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Get the protocol capabilities of the USB printer interface.

## -ioctlparameters

### -input-buffer

NULL

### -input-buffer-length

0

### -output-buffer

Pointer to a DWORD

### -output-buffer-length

sizeof(DWORD)

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

IOCTL_USBPRINT_GET_INTERFACE_TYPE returns one of the following values:

| Defined constant | Value | Description |
| --- | --- | --- |
| USB_PRINTER_INTERFACE_CLASSIC | 1 | Has only 7-1-2 alternate config |
| USB_PRINTER_INTERFACE_IPP | 2 | Has only 7-1-4 alternate config |
| USB_PRINTER_INTERFACE_DUAL | 3 | Has both 7-1-2 and 7-1-4 alternate configs |

7-1-2 refers to USB class printer(7), subclass(1), protocol(2==BIDI).

7-1-4 refers to USB class printer(7), subclass(1), protocol(4==IPP over USB).

## -see-also

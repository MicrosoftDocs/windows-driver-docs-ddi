---
UID: NI:usbprint.IOCTL_USBPRINT_GET_PROTOCOL
title: IOCTL_USBPRINT_GET_PROTOCOL
author: windows-driver-content
description: Retrieve the current printer protocol code of the USB printer interface.
tech.root: print
ms.assetid: c81c957c-7fa8-46f3-83df-05827a72c94c
ms.author: windowsdriverdev
ms.date: 04/03/2019
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
 - IOCTL_USBPRINT_GET_PROTOCOL
product: 
 - Windows
targetos: Windows
---

# IOCTL_USBPRINT_GET_PROTOCOL IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Retrieve the current printer protocol code of the USB printer interface.

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

IOCTL_USBPRINT_GET_PROTOCOL returns one of the following values:

| Defined constant | Value |
| --- | --- |
| USB_PRINTER_PROTOCOL_BIDI | 2 |
| USB_PRINTER_PROTOCOL_IPPOVERUSB | 4 |

## -see-also

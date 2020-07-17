---
UID: NI:usbprint.IOCTL_USBPRINT_SET_PROTOCOL
title: IOCTL_USBPRINT_SET_PROTOCOL
author: windows-driver-content
description: Set the current printer protocol code of the USB printer interface.
tech.root: print
ms.assetid: a7498e8a-e4d4-40d8-be9c-f54a474bb8e6
ms.author: windowsdriverdev
ms.date: 04/03/2019
keywords: ["IOCTL_USBPRINT_SET_PROTOCOL IOCTL"]
f1_keywords:
 - "usbprint/IOCTL_USBPRINT_SET_PROTOCOL"
 - "IOCTL_USBPRINT_SET_PROTOCOL"
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
 - IOCTL_USBPRINT_SET_PROTOCOL
product: 
 - Windows
targetos: Windows
---

# IOCTL_USBPRINT_SET_PROTOCOL IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Set the current printer protocol code of the USB printer interface.

## -ioctlparameters

### -input-buffer

Pointer to a DWORD

### -input-buffer-length

sizeof(DWORD)

### -output-buffer

NULL

### -output-buffer-length 

0

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

IOCTL_USBPRINT_SET_PROTOCOL supports the following values:

| Defined constant | Value |
| --- | --- |
| USB_PRINTER_PROTOCOL_BIDI | 2 |

If an interface supports IPP over USB, then it is started in the IPP over USB protocol. If the Windows print system detects that IHV drivers have been installed for the printer, then it will switch the printer back to BIDI.

## -see-also

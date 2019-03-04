---
UID: NI:usbprint.IOCTL_USBPRINT_SET_PROTOCOL
title: IOCTL_USBPRINT_SET_PROTOCOL
author: windows-driver-content
description: TBD
tech.root: print
ms.assetid: a7498e8a-e4d4-40d8-be9c-f54a474bb8e6
ms.author: windowsdriverdev
ms.date: 03/04/2019
ms.topic: ioctl
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

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

TBD

## -ioctlparameters

### -input-buffer

TBD

### -input-buffer-length 

TBD

### -output-buffer

TBD

### -output-buffer-length 

TBD

### -in-out-buffer

### -inout-buffer-length 

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_OUT
title: IOCTL_INTERNAL_USBFN_TRANSFER_OUT
author: windows-driver-content
description: The class driver sends this request to initiate a data transfer from the host on the specified pipe.
old-location: buses\ioctl_internal_usbfn_transfer_out.htm
old-project: usbref
ms.assetid: DDC99C5F-B959-44E4-A4A8-1CBA4E9BDA5A
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_INTERNAL_USBFN_TRANSFER_OUT, IOCTL_INTERNAL_USBFN_TRANSFER_OUT control, IOCTL_INTERNAL_USBFN_TRANSFER_OUT control code [Buses], buses.ioctl_internal_usbfn_transfer_out, usbfnioctl/IOCTL_INTERNAL_USBFN_TRANSFER_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnioctl.h
api_name:
-	IOCTL_INTERNAL_USBFN_TRANSFER_OUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USBFN_TRANSFER_OUT IOCTL


## -description


 The class driver sends this request to initiate a data transfer from the host on the specified pipe. 


## -ioctlparameters




### -input-buffer

A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.


### -output-buffer

A data buffer to receive data from the host.


### -output-buffer-length

The length of the buffer. 


### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



This request must be sent after sending the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187891">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.




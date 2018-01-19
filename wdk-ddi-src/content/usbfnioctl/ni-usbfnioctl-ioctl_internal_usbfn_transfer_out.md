---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_OUT
title: IOCTL_INTERNAL_USBFN_TRANSFER_OUT
author: windows-driver-content
description: The class driver sends this request to initiate a data transfer from the host on the specified pipe.
old-location: buses\ioctl_internal_usbfn_transfer_out.htm
old-project: usbref
ms.assetid: DDC99C5F-B959-44E4-A4A8-1CBA4E9BDA5A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
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
req.alt-api: IOCTL_INTERNAL_USBFN_TRANSFER_OUT
req.alt-loc: usbfnioctl.h
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
req.typenames: *PUSBFN_USB_STRING, USBFN_USB_STRING
req.product: Windows 10 or later.
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

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block


## -remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.</p>
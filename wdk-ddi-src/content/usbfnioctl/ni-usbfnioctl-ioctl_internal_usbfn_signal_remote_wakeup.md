---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
title: IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
author: windows-driver-content
description: The class driver sends this request to get remote wake-up notifications from endpoints.
old-location: buses\ioctl_usbfn_internal_signal_remote_wakeup.htm
old-project: usbref
ms.assetid: 052D16D1-E7E9-4237-B9F5-1D52D28444F0
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
req.alt-api: IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
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

# IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP IOCTL



## -description
The class driver sends this request  to get remote wake-up notifications from endpoints.



## -ioctlparameters

### -input-buffer
NULL.


### -input-buffer-length
None.


### -output-buffer
NULL.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

The USB function class extension (UFX) determines the endpoints that are remote wake-up capable and registers for remote wake notifications.</p>
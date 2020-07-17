---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
title: IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP (usbfnioctl.h)
description: The class driver sends this request to get remote wake-up notifications from endpoints.
old-location: buses\ioctl_usbfn_internal_signal_remote_wakeup.htm
tech.root: usbref
ms.assetid: 052D16D1-E7E9-4237-B9F5-1D52D28444F0
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP, IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP control, IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP control code [Buses], buses.ioctl_usbfn_internal_signal_remote_wakeup, usbfnioctl/IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
f1_keywords:
 - "usbfnioctl/IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP"
 - "IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbfnioctl.h
api_name:
- IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP
product:
- Windows
targetos: Windows
req.typenames: 
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








### -inout-buffer-length








### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks



This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

The USB function class extension (UFX) determines the endpoints that are remote wake-up capable and registers for remote wake notifications.




---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
title: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY (usbioctl.h)
description: The IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_notify_idle_ready.htm
tech.root: usbref
ms.assetid: ed013cd2-27b3-4f40-b8a7-536384c6bbac
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY, IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY control, IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY control code [Buses], buses.ioctl_internal_usb_notify_idle_ready, usbioctl/IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY"
 - "IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY"
req.header: usbioctl.h
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
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY</b> IOCTL is used by the USB hub driver. Do not use.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).




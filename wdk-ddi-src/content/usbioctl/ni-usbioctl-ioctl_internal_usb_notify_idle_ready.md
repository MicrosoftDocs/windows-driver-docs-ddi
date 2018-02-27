---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
title: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_notify_idle_ready.htm
old-project: usbref
ms.assetid: ed013cd2-27b3-4f40-b8a7-536384c6bbac
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY, IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY control code [Buses], buses.ioctl_internal_usb_notify_idle_ready, usbioctl/IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


 The <b>IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY</b> IOCTL is used by the USB hub driver. Do not use.


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [XREF-LINK:NTSTATUS Values].




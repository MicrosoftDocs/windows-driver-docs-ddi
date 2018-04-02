---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE
title: IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_tt_device_handle.htm
old-project: usbref
ms.assetid: 1ea77cc4-bee4-4e0a-92a4-6413d3e5871a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE, IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE control code [Buses], buses.ioctl_internal_usb_get_tt_device_handle, usbioctl/IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE
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
-	IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE</b> is used by the USB hub driver. Do not use.


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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
title: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_internal_usb_get_busguid_info.htm
old-project: usbref
ms.assetid: 79a09c8d-ddea-4335-ac90-11438f4bede6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO, IOCTL_INTERNAL_USB_GET_BUSGUID_INFO control code [Buses], buses.ioctl_internal_usb_get_busguid_info, usbioctl/IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: UsbIoctl.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


 The <b>IOCTL_INTERNAL_USB_GET_BUSGUID_INFO</b> IOCTL has been deprecated. Do not use.


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




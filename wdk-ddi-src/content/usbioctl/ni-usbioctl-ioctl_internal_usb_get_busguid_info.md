---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
title: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO (usbioctl.h)
description: The IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_internal_usb_get_busguid_info.htm
tech.root: usbref
ms.assetid: 79a09c8d-ddea-4335-ac90-11438f4bede6
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_GET_BUSGUID_INFO, IOCTL_INTERNAL_USB_GET_BUSGUID_INFO control, IOCTL_INTERNAL_USB_GET_BUSGUID_INFO control code [Buses], buses.ioctl_internal_usb_get_busguid_info, usbioctl/IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_GET_BUSGUID_INFO"
 - "IOCTL_INTERNAL_USB_GET_BUSGUID_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_GET_BUSGUID_INFO
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_GET_BUSGUID_INFO</b> IOCTL has been deprecated. Do not use.


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




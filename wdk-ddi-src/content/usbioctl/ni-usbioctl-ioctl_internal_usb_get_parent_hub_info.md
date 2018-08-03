---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
title: IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_parent_hub_info.htm
tech.root: usbref
ms.assetid: c97c1081-6f8c-4aa3-b34a-b8f7455dc2ef
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO, IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO control, IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO control code [Buses], buses.ioctl_internal_usb_get_parent_hub_info, usbioctl/IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
-	IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO IOCTL


## -description


The <b>IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO</b> 
   is used by the USB hub driver. Do not use.


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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




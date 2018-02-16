---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
title: IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_parent_hub_info.htm
old-project: usbref
ms.assetid: c97c1081-6f8c-4aa3-b34a-b8f7455dc2ef
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_internal_usb_get_parent_hub_info, IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO control code [Buses], IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO, usbioctl/IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO</b> 
   is used by the USB hub driver. Do not use.


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




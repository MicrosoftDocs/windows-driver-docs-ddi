---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
title: IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_device_handle_ex.htm
old-project: usbref
ms.assetid: 76b89f35-4751-4eda-88f7-69f1a9835bbb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_internal_usb_get_device_handle_ex, IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX control code [Buses], IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX, usbioctl/IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later operating systems.
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
-	IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


 The <b>IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX</b> IOCTL is used by the USB hub driver. Do not use.


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



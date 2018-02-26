---
UID: NI:usbioctl.IOCTL_USB_RESET_HUB
title: IOCTL_USB_RESET_HUB
author: windows-driver-content
description: The IOCTL_USB_RESET_HUB IOCTL is used by the USB driver stack. Do not use.
old-location: buses\ioctl_usb_reset_hub.htm
old-project: usbref
ms.assetid: 5e9294bf-94ba-48c4-b2e3-83ad96a051b1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_RESET_HUB, IOCTL_USB_RESET_HUB control code [Buses], buses.ioctl_usb_reset_hub, usbioctl/IOCTL_USB_RESET_HUB
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_RESET_HUB
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_RESET_HUB IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_USB_RESET_HUB</b> IOCTL is used by the USB driver stack.  Do not use.


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




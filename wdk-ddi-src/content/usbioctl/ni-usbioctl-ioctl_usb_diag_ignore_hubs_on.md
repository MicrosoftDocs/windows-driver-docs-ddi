---
UID: NI:usbioctl.IOCTL_USB_DIAG_IGNORE_HUBS_ON
title: IOCTL_USB_DIAG_IGNORE_HUBS_ON
author: windows-driver-content
description: The IOCTL_USB_DIAG_IGNORE_HUBS_ON I/O control has been deprecated. Do not use.
old-location: buses\ioctl_usb_diag_ignore_hubs_on.htm
old-project: usbref
ms.assetid: e63114a7-5487-490e-8581-1023bd558263
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_DIAG_IGNORE_HUBS_ON, IOCTL_USB_DIAG_IGNORE_HUBS_ON control code [Buses], buses.ioctl_usb_diag_ignore_hubs_on, usbioctl/IOCTL_USB_DIAG_IGNORE_HUBS_ON, usbirp_7e95e023-3bb1-423d-b233-b5028e9af76b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Microsoft Windows 2000 only.
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
-	IOCTL_USB_DIAG_IGNORE_HUBS_ON
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_DIAG_IGNORE_HUBS_ON IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The <b>IOCTL_USB_DIAG_IGNORE_HUBS_ON</b> I/O control has been deprecated. Do not use.




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




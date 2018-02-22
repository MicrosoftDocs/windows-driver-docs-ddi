---
UID: NI:usbioctl.IOCTL_USB_DIAGNOSTIC_MODE_OFF
title: IOCTL_USB_DIAGNOSTIC_MODE_OFF
author: windows-driver-content
description: The IOCTL_USB_DIAGNOSTIC_MODE_OFF I/O control has been deprecated. Do not use.
old-location: buses\ioctl_usb_diagnostic_mode_off.htm
old-project: UsbRef
ms.assetid: 8452c9a2-3e1f-4b62-8ab2-9071d55f5f68
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.ioctl_usb_diagnostic_mode_off, IOCTL_USB_DIAGNOSTIC_MODE_OFF control code [Buses], IOCTL_USB_DIAGNOSTIC_MODE_OFF, usbioctl/IOCTL_USB_DIAGNOSTIC_MODE_OFF, usbirp_7b761254-b350-4ac8-820f-04426139f6bb.xml
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
-	IOCTL_USB_DIAGNOSTIC_MODE_OFF
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_DIAGNOSTIC_MODE_OFF IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_USB_DIAGNOSTIC_MODE_OFF</b> I/O control has been deprecated. Do not use.




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




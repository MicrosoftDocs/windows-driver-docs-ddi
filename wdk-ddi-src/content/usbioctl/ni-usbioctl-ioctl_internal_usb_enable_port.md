---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_ENABLE_PORT
title: IOCTL_INTERNAL_USB_ENABLE_PORT
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_ENABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_internal_usb_enable_port.htm
old-project: usbref
ms.assetid: 6f15a559-fb6b-47d5-a101-43464ed80d0f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_USB_ENABLE_PORT, IOCTL_INTERNAL_USB_ENABLE_PORT control code [Buses], buses.ioctl_internal_usb_enable_port, usbioctl/IOCTL_INTERNAL_USB_ENABLE_PORT, usbirp_eee71b69-fc0a-446a-807b-6f776e634c9d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Microsoft Windows 2000, Windows XP and Windows Server 2003. It is not supported in Windows Vista and later operating systems.
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
-	usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_ENABLE_PORT
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_ENABLE_PORT IOCTL


## -description


The <b>IOCTL_INTERNAL_USB_ENABLE_PORT</b> IOCTL has been deprecated. Do not use.


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




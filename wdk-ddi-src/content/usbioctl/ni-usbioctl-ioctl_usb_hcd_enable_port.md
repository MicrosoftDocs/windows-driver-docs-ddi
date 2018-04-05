---
UID: NI:usbioctl.IOCTL_USB_HCD_ENABLE_PORT
title: IOCTL_USB_HCD_ENABLE_PORT
author: windows-driver-content
description: The IOCTL_USB_HCD_ENABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_usb_hcd_enable_port.htm
old-project: usbref
ms.assetid: bba3b9f4-cabb-496b-80c6-cdb51bd71ace
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_USB_HCD_ENABLE_PORT, IOCTL_USB_HCD_ENABLE_PORT control code [Buses], buses.ioctl_usb_hcd_enable_port, usbioctl/IOCTL_USB_HCD_ENABLE_PORT, usbirp_fc5909f4-17b5-455c-b635-5c53b9de816e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.
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
-	IOCTL_USB_HCD_ENABLE_PORT
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_HCD_ENABLE_PORT IOCTL


## -description


The <b>IOCTL_USB_HCD_ENABLE_PORT</b> IOCTL has been deprecated. Do not use.


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




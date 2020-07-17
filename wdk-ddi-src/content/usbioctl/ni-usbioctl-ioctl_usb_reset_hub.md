---
UID: NI:usbioctl.IOCTL_USB_RESET_HUB
title: IOCTL_USB_RESET_HUB (usbioctl.h)
description: The IOCTL_USB_RESET_HUB IOCTL is used by the USB driver stack. Do not use.
old-location: buses\ioctl_usb_reset_hub.htm
tech.root: usbref
ms.assetid: 5e9294bf-94ba-48c4-b2e3-83ad96a051b1
ms.date: 05/07/2018
keywords: ["IOCTL_USB_RESET_HUB IOCTL"]
ms.keywords: IOCTL_USB_RESET_HUB, IOCTL_USB_RESET_HUB control, IOCTL_USB_RESET_HUB control code [Buses], buses.ioctl_usb_reset_hub, usbioctl/IOCTL_USB_RESET_HUB
f1_keywords:
 - "usbioctl/IOCTL_USB_RESET_HUB"
 - "IOCTL_USB_RESET_HUB"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_USB_RESET_HUB
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_RESET_HUB IOCTL


## -description


The <b>IOCTL_USB_RESET_HUB</b> IOCTL is used by the USB driver stack.  Do not use.


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




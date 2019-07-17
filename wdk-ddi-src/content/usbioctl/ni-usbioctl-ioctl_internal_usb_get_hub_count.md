---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_HUB_COUNT
title: IOCTL_INTERNAL_USB_GET_HUB_COUNT (usbioctl.h)
description: The IOCTL_INTERNAL_USB_GET_HUB_COUNT IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_get_hub_count.htm
tech.root: usbref
ms.assetid: c671e983-aa19-4ba4-ba40-de9b4660f935
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_HUB_COUNT, IOCTL_INTERNAL_USB_GET_HUB_COUNT control, IOCTL_INTERNAL_USB_GET_HUB_COUNT control code [Buses], buses.ioctl_internal_usb_get_hub_count, usbioctl/IOCTL_INTERNAL_USB_GET_HUB_COUNT, usbirp_8c73af1c-9349-4b49-8d8d-aaaeb090dc5e.xml
ms.topic: ioctl
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_GET_HUB_COUNT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_GET_HUB_COUNT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_HUB_COUNT IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_GET_HUB_COUNT</b> IOCTL is used by the USB hub driver. Do not use.


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



